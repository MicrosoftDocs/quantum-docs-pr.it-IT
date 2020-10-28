---
title: Strutture dei dati nelle Q# librerie standard
description: Informazioni sulle strutture dei dati, i generatori di Oracle e i generatori dinamici nelle Q# librerie standard Microsoft.
author: QuantumWriter
uid: microsoft.quantum.libraries.data-structures
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: c3ce5d531618c269d15be3e4eb58ecbb597a022c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692245"
---
# <a name="data-structures-and-modeling"></a>Strutture e modellazione dei dati #

## <a name="classical-data-structures"></a>Strutture di dati classiche ##

Insieme ai tipi definiti dall'utente per la rappresentazione di concetti quantistici, la Canon fornisce anche operazioni, funzioni e tipi per lavorare con i dati classici usati nel controllo dei sistemi quantum.
Ad esempio, la <xref:Microsoft.Quantum.Arrays.Reversed> funzione accetta come input una matrice e restituisce la stessa matrice in ordine inverso.
Questa operazione può quindi essere usata in una matrice di tipo `Qubit[]` per evitare di dover applicare i controlli $ \operatorname{swap} $ non necessari quando si esegue la conversione tra rappresentazioni quantistiche di numeri interi.
Analogamente, nella sezione precedente è stato illustrato che i tipi del modulo `(Int, Int -> T)` possono essere utili per la rappresentazione di raccolte di accesso casuale, quindi la <xref:Microsoft.Quantum.Arrays.LookupFunction> funzione fornisce un modo pratico per costruire tali tipi dai tipi di matrice.

### <a name="pairs"></a>Coppie ###

La canonica supporta la notazione in stile funzionale per le coppie, completando l'accesso alle tuple mediante la decostruzione:

```qsharp
let pair = (PauliZ, register); // type (Pauli, Qubit[])
ApplyToEach(H, Snd(pair)); // No need to deconstruct to access the register.
```

### <a name="arrays"></a>Matrici ###

La canonica fornisce diverse funzioni per la modifica delle matrici.
Queste funzioni sono con parametri di tipo e possono quindi essere usate con matrici di qualsiasi Q# tipo.
Ad esempio, la <xref:Microsoft.Quantum.Arrays.Reversed> funzione restituisce una nuova matrice i cui elementi sono in ordine inverso rispetto al relativo input.
Questa operazione può essere utilizzata per modificare la modalità di rappresentazione di un registro Quantum durante la chiamata di operazioni:

```qsharp
let leRegister = LittleEndian(register);
// QFT expects a BigEndian, so we can reverse before calling.
QFT(BigEndian(Reversed(leRegister!)));
// This is how the LittleEndianAsBigEndian function is implemented:
QFT(LittleEndianAsBigEndian(leRegister));
```

Analogamente, la <xref:Microsoft.Quantum.Arrays.Subarray> funzione può essere usata per riordinare o usare subset degli elementi di una matrice:

```qsharp
// Applies H to qubits 2 and 5.
ApplyToEach(H, Subarray([2, 5], register));
```

In combinazione con il controllo di flusso, le funzioni di manipolazione di matrici come <xref:Microsoft.Quantum.Arrays.Zipped> possono fornire un modo efficace per esprimere i programmi Quantum:

```qsharp
// Applies X₃ Y₁ Z₇ to a register of any size.
ApplyToEach(
    ApplyPauli(_, register),
    Map(
        EmbedPauli(_, _, Length(register)),
        Zipped([PauliX, PauliY, PauliZ], [3, 1, 7])
    )
);
```

## <a name="oracles"></a>Oracoli ##

Nella letteratura relativa alla [fase di stima](https://en.wikipedia.org/wiki/Quantum_phase_estimation_algorithm) e di [amplificazione dell'ampiezza](https://en.wikipedia.org/wiki/Amplitude_amplification) il concetto di Oracle viene visualizzato spesso.
Il termine Oracle si riferisce a una subroutine del quantum blackbox che agisce su un set di qubits e restituisce la risposta come una fase.
Spesso questa subroutine può essere considerata come un input per un algoritmo Quantum che accetta Oracle, oltre ad altri parametri, e applica una serie di operazioni Quantum e che tratta una chiamata a questa subroutine Quantum come se fosse un controllo fondamentale.
Ovviamente, per implementare effettivamente l'algoritmo più ampio, è necessario fornire una scomposizione concreta del Oracle in controlli fondamentali, ma tale scomposizione non è necessaria per comprendere l'algoritmo che chiama Oracle.
In Q# questa astrazione viene rappresentata usando tali operazioni sono valori di prima classe, in modo che le operazioni possano essere passate alle implementazioni di algoritmi quantistici in modo nero.
I tipi definiti dall'utente, inoltre, vengono utilizzati per etichettare le diverse rappresentazioni Oracle in modo indipendente dai tipi, rendendo difficile la congestione accidentale di tipi diversi di operazioni black box.

Tali Oracle vengono visualizzati in diversi contesti, inclusi esempi noti, ad esempio gli algoritmi [di ricerca e di simulazione quantistica di Grover](https://en.wikipedia.org/wiki/Grover%27s_algorithm) .
In questo articolo vengono illustrati i Oracle necessari solo per due applicazioni, ovvero l'amplificazione dell'ampiezza e la stima della fase.
Prima di procedere alla valutazione della fase, verranno illustrati prima i Oracle di amplificazione di ampiezza.

### <a name="amplitude-amplification-oracles"></a>Oracle di amplificazione dell'ampiezza ###

L'algoritmo di amplificazione dell'ampiezza mira a eseguire una rotazione tra uno stato iniziale e uno stato finale applicando una sequenza di riflessioni dello stato.
Affinché l'algoritmo funzioni, è necessaria una specifica di entrambi questi Stati.
Queste specifiche sono fornite da due Oracle.
Questi Oracle funzionano suddividendo gli input in due spazi, un sottospazio "di destinazione" e un sottospazio "iniziale".
Gli Oracle identificano tali spazi subordinati, in modo analogo al modo in cui gli operatori Pauli identificano due spazi, applicando una fase $ \pm $1 a questi spazi.
La differenza principale consiste nel fatto che questi spazi non devono essere a metà spazi nell'applicazione.
Si noti anche che questi due sottospazi non si escludono in genere a vicenda: saranno presenti vettori che sono membri di entrambi gli spazi.
Se questa situazione non fosse vera, l'amplificazione dell'ampiezza non avrebbe alcun effetto, quindi è necessario che il sottospazio iniziale abbia una sovrapposizione diversa da zero con il sottospazio di destinazione.

Il primo Oracle necessario per l'amplificazione dell'ampiezza sarà $P \_ $0, definito in modo da avere l'azione seguente.  Per tutti gli Stati $ \ket{x} $ nel sottospazio "iniziale" $P \_ 0 \ket{x} =-\ket{x} $ e per tutti gli Stati $ \ket{y} $ che non sono presenti in questo sottospazio $P \_ 0 \ket{y} = \ket{y} $.
Il Oracle che contrassegna il sottospazio di destinazione, $P _1 $, assume esattamente lo stesso formato.
Per tutti gli Stati $ \ket{x} $ nel sottospazio di destinazione (ad esempio, per tutti gli stati in cui si vuole che venga restituito l'algoritmo), $P _1 \ KET {x} =-\ket{x} $.
Analogamente, per tutti gli Stati $ \ket{y} $ che non si trovano nel sottospazio di destinazione $P _1 \ KET {y} = \ket{y} $.
Queste due riflessioni vengono quindi combinate per formare un operatore che agisce su un singolo passaggio di amplificazione dell'ampiezza, $Q =-P_0 P_1 $, dove il segno meno generale è importante da considerare nelle applicazioni controllate.
L'amplificazione dell'ampiezza continua quindi con uno stato iniziale, $ \ket{\psi} $ che si trova nel sottospazio iniziale e quindi esegue $ \ket{\psi} \mapsto Q ^ m \ket{\psi} $.
L'esecuzione di tale iterazione garantisce che se uno inizia con uno stato iniziale con sovrapposizione di $ \sin ^ 2 (\theta) $ con lo spazio contrassegnato, dopo $m iterazioni $ questa sovrapposizione diventa $ \sin ^ 2 ([2m + 1] \theta) $.
Per questo motivo, in genere si vuole scegliere $m $ come parametro gratuito, in modo che $ [2m + 1] \theta = \ PI/2 $; Tuttavia, queste scelte rigide non sono altrettanto importanti per alcune forme di amplificazione dell'ampiezza, ad esempio l'amplificazione dell'ampiezza a punti fissi.
Questo processo consente di preparare uno stato nel sottospazio contrassegnato usando un numero minore di query per la funzione di contrassegno e la funzione di preparazione dello stato di quadratico in un dispositivo rigorosamente classico.
Questo è il motivo per cui l'amplificazione dell'ampiezza è un blocco predefinito significativo per molte applicazioni di quantum computing.

Per comprendere come usare l'algoritmo, è utile fornire un esempio che fornisce una costruzione di Oracle.  Si consiglia di eseguire l'algoritmo di Grover per le ricerche nel database in questa impostazione.
Nella ricerca di Grover l'obiettivo consiste nel trasformare lo stato $ \ket{+} ^ {\otimes n} = H ^ {\otimes n} \ket {0} $ in uno (potenzialmente) molti stati contrassegnati.
Per semplificare ulteriormente, esaminiamo il caso in cui l'unico stato contrassegnato è $ \ket {0} $.
Sono stati quindi progettati due Oracle: uno che contrassegna solo lo stato iniziale $ \ket{+} ^ {\otimes n} $ con un segno meno e un altro che contrassegna lo stato contrassegnato come $ \ket {0} $ con un segno meno.
Quest'ultimo può essere implementato usando l'operazione di elaborazione seguente, usando le operazioni del flusso di controllo in Canon:

```qsharp
operation ReflectAboutAllZeros(register : Qubit[]) : Unit 
is Adj + Ctl {

    // Apply $X$ gates to every qubit.
    ApplyToEach(X, register);

    // Apply an $n-1$ controlled $Z$-gate to the $n^{\text{th}}$ qubit.
    // This gate will lead to a sign flip if and only if every qubit is
    // $1$, which happens only if each of the qubits were $0$ before step 1.
    Controlled Z(Most(register), Tail(register));

    // Apply $X$ gates to every qubit.
    ApplyToEach(X, register);
}
```

Questo Oracle è quindi un caso speciale dell' <xref:Microsoft.Quantum.Canon.RAll1> operazione, che consente la rotazione di una fase arbitraria invece del caso di Reflection $ \Phi = \Pi $.
In questo caso, `RAll1` è simile all' <xref:Microsoft.Quantum.Intrinsic.R1> operazione di preludio, in quanto ruota circa $ \ket{11\cdots1} $ anziché lo stato qubit singolo $ \ket {1} $.

Il Oracle che contrassegna il sottospazio iniziale può essere costruito in modo analogo.
In pseudocodice:

1. Applicare $H $ Gates a ogni qubit.
2. Applicare $X $ Gates a ogni qubit.
3. Applicare una $n-$1 controllata $Z $-Gate al $n ^ {\Text{TH}} $ qubit.
4. Applicare $X $ Gates a ogni qubit.
5. Applicare $H $ Gates a ogni qubit.

Questa volta viene inoltre illustrato l'utilizzo <xref:Microsoft.Quantum.Canon.ApplyWith> di insieme all' <xref:Microsoft.Quantum.Canon.RAll1> operazione descritta in precedenza:

```qsharp
operation ReflectAboutInitial(register : Qubit[]) : Unit
is Adj + Ctl {
    ApplyWithCA(ApplyToEach(H, _), ApplyWith(ApplyToEach(X, _), RAll1(_, PI()), _), register);
}
```

Possiamo quindi combinare questi due oracoli insieme per ruotare tra i due Stati e trasformare in modo deterministico $ \ket{+} ^ {\otimes n} $ in $ \ket {0} $ usando diversi livelli di Hadamard Gate proporzionali a $ \sqrt{2 ^ n} $ (ie $m \propto \sqrt{2 ^ n} $) rispetto ai livelli approssimativamente $2 ^ n $, necessari per preparare in modo non deterministico lo {0} stato di $ \ket $ preparando e misurando lo stato iniziale fino a quando non viene osservato il risultato $0 $.

### <a name="phase-estimation-oracles"></a>Oracle di stima della fase ###

Per la stima della fase, i Oracle sono piuttosto più naturali.
Lo scopo della valutazione della fase è progettare una subroutine in grado di eseguire il campionamento dagli autovalori di una matrice unitaria.
Questo metodo è indispensabile nella simulazione quantistica perché per molti problemi fisici nella chimica e nell'analisi scientifica dei materiali questi autonomi offrono le energie di stato del sistema quantistica che forniscono informazioni utili sui diagrammi di fase di materiali e dinamiche di reazione per le molecole.
Ogni versione della valutazione della fase richiede un unità di input.
Questo unitario è comunemente descritto da uno dei due tipi di Oracle.

> [!TIP]
> Entrambi i tipi di Oracle descritti di seguito sono trattati negli esempi.
> Per ulteriori informazioni sugli Oracle con query continue, vedere l'esempio [ **PhaseEstimation**](https://github.com/microsoft/Quantum/tree/main/samples/characterization/phase-estimation).
> Per ulteriori informazioni sugli Oracle con query discrete, vedere l' [esempio **IsingPhaseEstimation**](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/phase-estimation).

Il primo tipo di Oracle, che viene chiamato una query discreta Oracle e che rappresenta con il tipo definito dall'utente <xref:Microsoft.Quantum.Oracles.DiscreteOracle> , comporta semplicemente una matrice unitaria.
Se $U $ è l'unitario i cui autonomi si desidera stimare, Oracle per $U $ è semplicemente uno stato di una subroutine che implementa $U $.
Ad esempio, è possibile che si prenda $U $ come Oracle $Q $ defined per la stima dell'ampiezza.
Gli autovalori di questa matrice possono essere usati per stimare la sovrapposizione tra gli stati iniziale e di destinazione, $ \sin ^ 2 (\theta) $, usando quadratico un minor numero di campioni di quelli necessari altrimenti.
In questo modo si ottiene l'applicazione della valutazione della fase usando l'Oracle di Grover $Q $ come input il moniker della stima dell'ampiezza.
Un'altra applicazione comune, ampiamente utilizzata nella metrologia quantistica, comporta la stima di un angolo di rotazione ridotto.
In altre parole, si desidera stimare $ \theta $ per un controllo di rotazione sconosciuto nel formato $R _z (\theta) $.
In questi casi, la subroutine con cui si interagirà per apprendere questo valore fisso di $ \theta $ per il Gate è $ $ \begin{align} U & = R_z (\theta) \\ \\ & = \begin{Bmatrix} e ^ {-i \theta/2} & 0 \\ \\ 0 & e ^ {i \ Theta/2} \end{Bmatrix}.
\end{align} $ $

Il secondo tipo di Oracle usato nella stima della fase è la query continua Oracle, rappresentata dal <xref:Microsoft.Quantum.Oracles.ContinuousOracle> tipo.
Una query continua Oracle per la stima della fase assume il formato $U (t) $ dove $t $ è un numero reale noto in modo classico.
Se si lascia che $U $ sia un unitario fisso, l'Oracle della query continua assume il formato $U (t) = U ^ t $.
Questo consente di eseguire query su matrici quali $ \sqrt{U} $, che non possono essere implementate direttamente nel modello di query discreto.

Questo tipo di Oracle è utile quando non si esegue il sondaggio di un particolare gruppo, ma si desidera apprendere le proprietà del generatore dell'unità.
Nella simulazione Quantum dinamica, ad esempio, l'obiettivo è quello di definire circuiti Quantum che siano strettamente approssimativi $U (t) = e ^ {-i H t} $ per una matrice Hermitiane $H $ ed Evolution Time $t $.
Gli autovalori di $U (t) $ sono direttamente correlati agli autovalori di $H $.
Per verificarlo, si consideri un autovettore di $H $: $H \ket{E} = E\ket {E} $, quindi è facile vedere dalla definizione della serie Power della matrice esponenziale che $U (t) \ket{E} = e ^ {i\phi} \ KET {E} = e ^ {-iEt} \ket{E} $.
In questo modo, la stima del eigenphase di $U (t) $ restituisce il autovalore $E $ presumendo che autovettore $ \ket{E} $ sia l'input nell'algoritmo di stima della fase.
Tuttavia, in questo caso il valore $t $ può essere scelto a discrezione dell'utente, perché per qualsiasi valore sufficientemente piccolo di $t $ il autovalore $E $ può essere invertito in modo univoco tramite $E =-\ Phi/t $.
Poiché i metodi di simulazione Quantum offrono la possibilità di eseguire un'evoluzione frazionaria, questo concede agli algoritmi di stima della fase una maggiore libertà durante l'esecuzione di query sull'unità, in particolare quando il modello di query discrete consente solo unitaries nel formato $U ^ j $ a applicato per Integer $j $ The Continuous query Oracle consente di approssimarsi a unitaries nel formato $U ^ t $ per qualsiasi $t valore reale
Questo è importante per comprimere tutte le ultime once di efficienza al di fuori degli algoritmi di stima della fase perché consente di scegliere con precisione l'esperimento che fornirebbe la maggior parte delle informazioni su $E $; mentre i metodi basati su query discrete devono effettuare l'operazione con la compromissione scegliendo il numero intero migliore di query nell'algoritmo.

Come esempio concreto, si consideri il problema della stima non dell'angolo di rotazione di un controllo, ma della frequenza di elaborazione di un sistema Quantum rotante.
L'unitario che descrive tali Dynamics Quantum è $U (t) = R_z (2 \ Omega t) $ per il tempo di Evolution $t $ e la frequenza sconosciuta $ \omega $.
In questo contesto, è possibile simulare $U (t) $ per qualsiasi $t $ utilizzando un singolo $R _z $ Gate e, di conseguenza, non è necessario limitarsi solo alle query discrete per l'unità.
Un modello continuo di questo tipo ha anche la proprietà che le frequenze maggiori di $2 \ PI $ possono essere apprese dai processi di stima della fase che usano le query continue perché le informazioni sulle fasi che verrebbero altrimenti mascherate dai tagli di rami della funzione logaritmo possono essere rivelate dai risultati di esperimenti eseguiti su valori non commisurati di $t $.
Per risolvere i problemi, ad esempio i modelli di query continua per la valutazione della fase, Oracle non solo è appropriato ma è preferibile anche al modello di query discreto.
Per questo motivo, Q# presenta funzionalità per entrambe le forme di query e consente all'utente di decidere in base a un algoritmo di stima della fase per adattarsi alle proprie esigenze e al tipo di Oracle disponibile.

## <a name="dynamical-generator-modeling"></a>Modellazione dinamica del generatore ##

Generatori di Time-Evolution descrive il modo in cui gli Stati si evolvono nel tempo. Ad esempio, le dinamiche di uno stato quantico $ \ket{\psi} $ sono regolate dall'equazione Schrödinger $ $ \begin{align} i\frac {d \ket{\psi (t)}} {d t} & = H \ket{\psi (t)}, \end{align} $ $ con una matrice Hermitiane $H $, nota come hamiltoniana, come il generatore di movimento. Dato uno stato iniziale $ \ket{\psi (0)} $ at time $t = $0, la soluzione formale a questa equazione al momento $t $ può essere, in linea di principio, scritta $ $ \begin{align} \ket{\psi (t)} = U (t) \ket{\psi (0)}, \end{align} $ $ in cui l'esponenziale della matrice $U (t) = e ^ {-i H t} $ è noto come operatore di evoluzione temporale unitario. Sebbene ci si concentri sui generatori di questo modulo nel seguente modo, viene evidenziato che il concetto si applica in modo più ampio, ad esempio alla simulazione di sistemi quantistici aperti, o a equazioni differenziali più astratte.

Uno degli obiettivi principali della simulazione dinamica consiste nell'implementare l'operatore Time-Evolution in uno stato quantico codificato in qubits di un computer Quantum.  In molti casi, l'Hamiltoniana può essere suddivisa in una somma di alcune $d $ più semplici termini

$ $ \begin{align} H & = \sum ^ {d-1} _ {j = 0} H_j, \end{align} $ $

laddove l'evoluzione del tempo per ogni termine è facile da implementare in un computer Quantum. Se, ad esempio, $H _j $ è un $X Pauli _1X_2 operatore $ che agisce sul primo e il secondo elemento del registro qubit `qubits` , il time-Evolution per ogni tempo $t $ può essere implementato semplicemente chiamando l'operazione con la `Exp([PauliX,PauliX], t, qubits[1..2])` firma `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)` . Come illustrato più avanti nella simulazione di hamiltoniana, una soluzione prevede di approssimarsi all'evoluzione del tempo per $H $ con una sequenza di operazioni più semplici

$ $ \begin{align} U (t) & = \left (e ^ {-iH \_ 0 t/r} e ^ {-IH \_ 1 t/r} \cdots e ^ {-IH \_ {d-1} t/r} \right) ^ {r} + \mathcal{O} (d ^ 2 \ max_j \\ | H \_ j \\ | ^ 2 t ^ 2/r), \end{align} $ $

dove il valore integer $r > $0 controlla l'errore di approssimazione.

La libreria di modellazione generatore dinamica fornisce un Framework per codificare sistematicamente i generatori complicati in termini di generatori più semplici. Una descrizione di questo tipo può quindi essere passata, ad esempio, dalla libreria di simulazione per implementare l'evoluzione del tempo in base a un algoritmo di simulazione scelto, con molti dettagli gestiti automaticamente.

> [!TIP]
> La libreria del generatore dinamica descritta di seguito è illustrata negli esempi. Per un esempio basato sul modello Ising, vedere l' [esempio **IsingGenerators**](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/generators).
> Per un esempio basato su idrogeno molecolare, vedere gli esempi di [**H2SimulationCmdLine**](https://github.com/microsoft/Quantum/tree/main/samples/simulation/h2/command-line) e [**H2SimulationGUI**](https://github.com/microsoft/Quantum/tree/main/samples/simulation/h2/gui) .

### <a name="complete-description-of-a-generator"></a>Descrizione completa di un generatore ###

Al livello principale, una descrizione completa di un'Hamiltoniana è contenuta nel `EvolutionGenerator` tipo definito dall'utente con due componenti:

```qsharp
newtype EvolutionGenerator = (EvolutionSet, GeneratorSystem);
```

Il `GeneratorSystem` tipo definito dall'utente è una descrizione classica dell'hamiltoniana.

```qsharp
newtype GeneratorSystem = (Int, (Int -> GeneratorIndex));
```

Il primo elemento `Int` della tupla archivia il numero di termini $d $ nell'Hamiltoniana e il secondo elemento `(Int -> GeneratorIndex)` è una funzione che esegue il mapping di un indice Integer in $ \{ 0, 1,..., d-1 \} $ a un `GeneratorIndex` tipo definito dall'utente che identifica in modo univoco ogni termine primitivo nell'Hamiltoniana. Si noti che, esprimendo la raccolta di termini nell'Hamiltoniana come funzione anziché come matrice `GeneratorIndex[]` , questo consente un calcolo immediato di, `GeneratorIndex` che risulta particolarmente utile quando si descrive hamiltonians con un numero elevato di termini.

Fondamentalmente, non viene imposta una convenzione sui termini primitivi identificati da `GeneratorIndex` sono facili da simulare. Ad esempio, i termini primitivi potrebbero essere operatori di Pauli come descritto in precedenza, ma possono anche essere fermioniche annientamento e operatori di creazione usati comunemente nella simulazione della chimica quantistica. Di per sé, un oggetto `GeneratorIndex` non ha alcun significato perché non descrive il modo in cui l'evoluzione del tempo per il termine a cui fa riferimento può essere implementata come un circuito Quantum.

Questo problema viene risolto specificando un `EvolutionSet` tipo definito dall'utente che esegue il mapping di qualsiasi oggetto `GeneratorIndex` , disegnato da un set canonico, a un operatore unitario, `EvolutionUnitary` , espresso come un circuito Quantum. `EvolutionSet`Definisce la convenzione di struttura di un oggetto `GeneratorIndex` e definisce anche il set di possibili `GeneratorIndex` .

```qsharp
newtype EvolutionSet = (GeneratorIndex -> EvolutionUnitary);
```

### <a name="pauli-operator-generators"></a>Generatori di operatori Pauli ###

Un esempio concreto e utile di generatori è costituito da hamiltonians che sono una somma di operatori Pauli, ognuno dei quali può avere un coefficiente diverso.
$ $ \begin{align} H & = \sum ^ {d-1} _ {j = 0} a_j H_j, \end{align} $ $ dove ogni $ \hat H_j $ viene ora disegnato dal gruppo Pauli. Per tali sistemi, viene fornito l'oggetto `PauliEvolutionSet()` di tipo `EvolutionSet` che definisce una convenzione per il modo in cui un elemento del gruppo Pauli e un coefficiente possono essere identificati da un oggetto `GeneratorIndex` , che presenta la firma seguente.

```qsharp
newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```

Nella codifica, il primo parametro `Int[]` specifica una stringa di Pauli, dove $ \Hat I\rightarrow $0, $ \Hat X\rightarrow $1, $ \Hat Y\rightarrow $2 e $ \Hat Z\rightarrow $3. Il secondo parametro `Double[]` archivia il coefficiente della stringa Pauli nell'Hamiltoniana. Si noti che viene usato solo il primo elemento della matrice. Il terzo parametro `Int[]` indicizza il qubits su cui agisce questa stringa di Pauli e non deve avere elementi duplicati. Pertanto, il termine hamiltoniana $0,4 \hat X_0 \hat Y_8 \hat I_2 \hat Z_1 $ può essere rappresentato come

```qsharp
let generatorIndexExample = GeneratorIndex(([1,2,0,3], [0.4]]), [0,8,2,1]);
```

`PauliEvolutionSet()`È una funzione che esegue il mapping di qualsiasi `GeneratorIndex` di questo form a un oggetto `EvolutionUnitary` con la firma seguente.

```qsharp
newtype EvolutionUnitary = ((Double, Qubit[]) => Unit is Adj + Ctl);
```

Il primo parametro rappresenta un intervallo di tempo, che verrà moltiplicato per il coefficiente in `GeneratorIndex` , dell'evoluzione unitaria. Il secondo parametro è il registro qubit su cui agisce l'unità. 

### <a name="time-dependent-generators"></a>Generatori di Time-Dependent ###

In molti casi, si è interessati anche alla modellazione di generatori dipendenti dal tempo, come potrebbe verificarsi nell'equazione Schrödinger $ $ \begin{align} i\frac {d \ket{\psi (t)}} {d t} & = \hat H (t) \ket{\psi (t)}, \end{align} $ $ dove il generatore $ \hat H (t) $ ora dipende dal tempo. L'estensione dai generatori di tempo indipendenti sopra a questo caso è semplice. Invece di avere un oggetto fisso che `GeneratorSystem` descrive l'Hamiltoniana per tutti gli orari $t $, abbiamo invece il `GeneratorSystemTimeDependent` tipo definito dall'utente.

```qsharp
newtype GeneratorSystemTimeDependent = (Double -> GeneratorSystem);
```

Il primo parametro è un parametro di pianificazione continua $s \In [0, 1] $ e le funzioni di questo tipo restituiscono un oggetto `GeneratorSystem` per tale pianificazione. Si noti che il parametro Schedule può essere correlato in modo lineare al parametro del tempo fisico, ad esempio $s = t/T $, per un tempo totale di simulazione $T $. In generale, tuttavia, questa situazione non è necessaria.

Analogamente, una descrizione completa di questo generatore richiede un oggetto `EvolutionSet` , quindi viene `EvolutionSchedule` definito un tipo definito dall'utente.

```qsharp
newtype EvolutionSchedule = (EvolutionSet, GeneratorSystemTimeDependent);
```
