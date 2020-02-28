---
title: 'Applicazioni nelle librerie standard Q #'
description: 'Informazioni su due applicazioni fondamentali in quantum computing: simulazione Hamiltoniana e algoritmo di ricerca di Shor.'
author: QuantumWriter
uid: microsoft.quantum.libraries.applications
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: b7c46b634c6d691c067c0dd995301395408c85ca
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907223"
---
# <a name="applications"></a>Applicazioni #

## <a name="hamiltonian-simulation"></a>Simulazione hamiltoniana ##

La simulazione dei sistemi quantistici è una delle applicazioni più interessanti del calcolo quantistico.
In un computer classico, la difficoltà di simulare la meccanica quantistica, in generale, è scalabile con la dimensione $N $ della relativa rappresentazione di vettori di stato.
Poiché questa rappresentazione cresce in modo esponenziale con il numero di $n $ qubits $N = 2 ^ n $, una caratteristica nota anche come [Curse of dimensionance](xref:microsoft.quantum.concepts.multiple-qubits), la simulazione quantistica sull'hardware classico è intratta.

Tuttavia, la situazione può essere molto diversa nell'hardware del quantum. La variante più comune della simulazione quantistica è detta problema di simulazione hamiltoniana indipendente dal tempo. Ne viene fornita una con una descrizione dell'Hamiltoniana del sistema $H $, che è una matrice Hermitiane e di uno stato quantum iniziale $ \ket{\psi (0)} $ codificato in base a $n $ qubits in un computer Quantum. Poiché gli Stati Quantum nei sistemi chiusi si evolvono nell'equazione Schrödinger $ $ \begin{align} i\frac {d \ket{\psi (t)}} {d t} & = H \ket{\psi (t)}, \end{align} $ $ lo scopo è quello di implementare il time-Evolution operator $U (t) = e ^ {-iHt} $ a un orario fisso $t $ , dove $ \ket{\psi (t)} = U (t) \ket{\psi (0)} $ risolve l'equazione Schrödinger.
Analogamente, il problema della simulazione hamiltoniana dipendente dal tempo risolve la stessa equazione, ma con $H (t) $ Now una funzione di tempo.

La simulazione hamiltoniana è un componente fondamentale di molti altri problemi di simulazione quantistica e le soluzioni al problema della simulazione hamiltoniana sono algoritmi che descrivono una sequenza di controlli Quantum primitivi per la sintesi di un elemento unitario approssimativo $ \tilde{U} $ con errore $\\| \tilde{U}-U (t)\\| \Le \epsilon $ nella [norma spettrale](xref:microsoft.quantum.concepts.matrix-advanced). La complessità di questi algoritmi dipende molto fortemente dal modo in cui una descrizione dell'Hamiltoniana di interesse viene resa accessibile da un computer Quantum. Nel caso peggiore, ad esempio, se $H $ che agisce su $n $ qubits venisse fornito come un elenco di $2 ^ n \times 2 ^ n $ numeri, uno per ogni elemento della matrice, semplicemente leggendo i dati sarebbe già necessario un tempo esponenziale. Nel migliore dei casi, è possibile che si presupponga l'accesso a un unitario nero che $O \ket{t}\ket{\psi (0)} = \ket{t}U (t) \ket{\psi (0)} $ in modo banale risolve il problema. Nessuno di questi modelli di input è particolarmente interessante, ovvero il primo, perché non è migliore degli approcci classici e il secondo come la scatola nera nasconde la complessità del controllo primitivo della relativa implementazione, che può essere esponenziale nel numero di qubits.

### <a name="descriptions-of-hamiltonians"></a>Descrizioni di hamiltonians ###

Sono pertanto necessari presupposti aggiuntivi del formato dell'input. È necessario che venga raggiunto un equilibrio preciso tra i modelli di input che sono sufficientemente descrittivi per includere hamiltonians interessanti, ad esempio quelli per i sistemi fisici realistici o problemi di calcolo interessanti, e modelli di input sufficientemente restrittivi. per essere implementabili in modo efficiente in un computer Quantum. In letteratura è possibile trovare una varietà di modelli di input non semplici che variano dal quantum al classico. 

Come esempi di modelli di input Quantum, la [simulazione hamiltoniana basata sul campione](http://www.nature.com/articles/s41534-017-0013-7) presuppone l'accesso nero alle operazioni Quantum che producono copie di una matrice di densità $ \rho $, che vengono adottate come hamiltoniana $H $. Nel [modello di accesso unitario](https://arxiv.org/abs/1202.5822) si presuppone che l'Hamiltoniana si decompongono invece in una somma di unitaries $ $ \begin{align} H & = \sum ^ {d-1}\_{j = 0} a\_j \hat{U}\_j, \end{align} $ $ dove $a\_j > 0 $ sono coefficienti e $ \hat{U}\_j $ sono unitaries. Si presuppone quindi che uno disponga di un accesso nero all'unità Oracle $V = \sum ^ {d-1}\_{j = 0} \ket{j}\bra{j}\otimes \hat{U}\_j $ che seleziona il $ \hat{U} desiderato\_j $, e Oracle $A \ket{0}= \sum ^ {d-1}\_{j = 0} \sqrt{a\_j/\ Sum ^ {d-1}\_{k = 0} \Alpha\_j} \ket{j} $ che creano uno stato quantico che codifica questi coefficienti. Nel caso della simulazione di un' [Hamiltoniana di tipo sparse](https://arxiv.org/abs/quant-ph/0301023), si presuppone che l'Hamiltoniana sia una matrice di tipo sparse con un solo elemento $d = \mathcal{O} (\Text{POLYLOG} (N)) $ diverso da zero in ogni riga. Inoltre, si presuppone l'esistenza di circuiti Quantum efficienti che restituiscono la posizione di questi elementi diversi da zero, nonché i relativi valori. La complessità degli [algoritmi di simulazione hamiltoniana](xref:microsoft.quantum.more-information) viene valutata in termini di numero di query su queste caselle nere e la complessità del controllo primitivo dipende quindi molto dalla difficoltà di implementazione di queste caselle nere.

> [!NOTE]
> La notazione Big-O viene comunemente usata per descrivere il ridimensionamento della complessità degli algoritmi. Date due funzioni reali $f, g $, l'espressione $g (x) = \mathcal{O} (f (x)) $ significa che esiste una costante positiva assoluta $x\_0, c > 0 $ tale che $g (x) \Le c f (x) $ per tutti $x \ge x\_$0. 

Nella maggior parte delle applicazioni pratiche che devono essere implementate in un computer Quantum, queste caselle nere devono essere implementabili in modo efficiente, ovvero con $ \mathcal{O} (\Text{POLYLOG} (N)) $ primitive Quantum Gates. In modo più efficiente, simulable hamiltonians deve avere una descrizione abbastanza semplice e di tipo sparse. In una formula di questo tipo si presuppone che l'Hamiltoniana venga suddivisa in una somma di Hermitiane parti $ $ \begin{align} H & = \sum ^ {d-1} _ {j = 0} H_j.
\end{align} $ $, inoltre, si presuppone che ogni parte, un'Hamiltoniana $H\_j $, sia facile da simulare. Ciò significa che l'unità $e ^ {-iH\_j t} $ per qualsiasi ora $t $ può essere implementata esattamente tramite $ \mathcal{O} (1) $ primitive Quantum Gates. Questa situazione si verifica, ad esempio, nel caso speciale in cui ogni $H\_j $ sono operatori locali di Pauli, vale a dire che si tratta di prodotti tensori di $ \mathcal{O} (1) $ non-Identity Pauli Operators che agiscono sulla chiusura spaziale di qubits. Questo modello è particolarmente applicabile ai sistemi fisici con interazione vincolata e locale, in quanto il numero di termini è $d = \mathcal{O} (\Text{POLYLOG} (N)) $ e può essere chiaramente scritto, ovvero una descrizione classica, in tempo polinomi.

> [!TIP]
> Hamiltonians che si decompongono in una somma di parti possono essere descritte utilizzando la libreria di rappresentazione dinamica del generatore. Per ulteriori informazioni, vedere la sezione relativa alla rappresentazione dinamica del generatore in [strutture di dati](xref:microsoft.quantum.libraries.data-structures).

### <a name="simulation-algorithms"></a>Algoritmi di simulazione ###

Un algoritmo di simulazione quantistica converte una determinata descrizione di un'Hamiltoniana in una sequenza di controlli Quantum primitivi che, nel suo complesso, hanno un'evoluzione approssimativa del tempo in base all'Hamiltoniana.

Nel caso speciale in cui l'Hamiltoniana si scompone in una somma di parti hermitiane, la decomposizione Trotter-Suzuki è un algoritmo particolarmente semplice e intuitivo per la simulazione di hamiltonians che si decompongono in una somma di componenti Hermitiane. Un integratore di questo gruppo, ad esempio, si avvicina a $ $ \begin{align} U (t) & = \left (e ^ {-iH\_0 t/r} e ^ {-iH\_1 t/r} \cdots e ^ {-iH\_{d-1} t/r} \right) ^ {r} + \mathcal{O} (d ^ 2 \ max_j\\| H\_j\\| ^ 2 t ^ 2/r), \end{align} $ $ usando un prodotto di $r d termini. 

> [!TIP]
> Le applicazioni dell'algoritmo di simulazione Trotter-Suzuki sono incluse negli esempi.
> Per il modello Ising usando solo le operazioni intrinseche fornite da ogni computer di destinazione, vedere l' [esempio **SimpleIsing** ](https://github.com/microsoft/Quantum/blob/master/samples/simulation/ising/simple).
> Per il modello Ising usando la struttura di controllo della libreria Trotter-Suzuki, vedere l' [esempio **IsingTrotter** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/trotter-evolution).
> Per l'idrogeno molecolare usando la struttura di controllo della libreria Trotter-Suzuki, vedere l'esempio di [ **simulazione H2** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/command-line).

In molti casi, si desidera implementare l'algoritmo di simulazione, ma non sono interessati ai dettagli della relativa implementazione. Ad esempio, l'integratore di secondo ordine si avvicina a $ $ \begin{align} U (t) & = \left (e ^ {-iH\_0 t/2R} e ^ {-iH\_1 t/2R} \cdots e ^ {-iH\_{d-1} t/2R} e ^ {-iH\_{d-1} t/2R} \cdots e ^ {-iH\_1 t/2R} e ^ {-iH\_0 t/2R} \right) ^ {r} + \mathcal{O} (d ^ 3 \ max_j\\| H\_j\\| ^ 3 t ^ 3/r ^ 2), \end{align} $ $ usando un prodotto di $2RD $ termini. Gli ordini di dimensioni maggiori comporteranno un numero ancora maggiore di termini e varianti ottimizzate potrebbero richiedere ordinamenti altamente non semplici sugli esponenziali. Altri algoritmi avanzati possono anche comportare l'uso di ancilla qubits nei passaggi intermedi. Quindi, gli algoritmi di simulazione vengono impacchettati in Canon come tipo definito dall'utente

```qsharp
newtype SimulationAlgorithm = ((Double, EvolutionGenerator, Qubit[]) => Unit is Adj + Ctl);
```

Il primo parametro `Double` è l'ora della simulazione, il secondo parametro `EvolutionGenerator`, illustrato nella sezione relativa alla rappresentazione dinamica del generatore di [strutture di dati](xref:microsoft.quantum.libraries.data-structures), è una descrizione classica di un'Hamiltoniana indipendente dal tempo, in cui vengono fornite istruzioni su come ogni termine nell'Hamiltoniana può essere simulato da un circuito Quantum. I tipi di questo form approssimano l'operazione unitaria $e ^ {-iHt} $ sul terzo parametro `Qubit[]`, ovvero il registro che archivia lo stato del quantum del sistema simulato. Analogamente, per il caso dipendente dal tempo, viene definito un tipo definito dall'utente con un tipo di `EvolutionSchedule`, ovvero una descrizione classica di un'Hamiltoniana dipendente dal tempo.

```qsharp
newtype TimeDependentSimulationAlgorithm = ((Double, EvolutionSchedule, Qubit[]) => Unit : Adjoint, Controlled);
```

Ad esempio, la scomposizione Trotter-Suzuki può essere chiamata usando le funzioni Canon seguenti, con i parametri `trotterStepSize` la modifica della durata della simulazione in ogni esponenziale e la `trotterOrder` per l'ordine dell'integratore desiderato.

```qsharp
function TrotterSimulationAlgorithm(
    trotterStepSize : Double, 
    trotterOrder : Int) 
: SimulationAlgorithm {
    ...
}

function TimeDependentTrotterSimulationAlgorithm(
    trotterStepSize : Double, 
    trotterOrder : Int) 
: TimeDependentSimulationAlgorithm {
    ...
}
```

> [!TIP]
> Le applicazioni della libreria di simulazione sono descritte negli esempi. Per la stima della fase nel modello Ising usando `SimulationAlgorithm`, vedere l' [esempio **IsingPhaseEstimation** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/phase-estimation).
> Per la preparazione dello stato adiabatica nel modello Ising usando `TimeDependentSimulationAlgorithm`, vedere l' [esempio **AdiabaticIsing** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/adiabatic).


### <a name="adiabatic-state-preparation--phase-estimation"></a>Valutazione della fase di preparazione dello stato adiabatica & ###

Un'applicazione comune della simulazione hamiltoniana è la preparazione dello stato adiabatica. In questo caso, ne viene fornito uno con due hamiltonians $H\_{\Text{Start}} $ e $H\_{\Text{end}} $ e uno stato quantico $ \ket{\psi (0)} $ che è uno stato di base dell'Hamiltoniana iniziale $H\_{\Text{Start}} $. In genere, $H\_{\Text{Start}} $ viene scelto in modo che $ \ket{\psi (0)} $ sia facile da preparare da uno stato di base computazionale $ \ket{0\cdots 0} $. L'interpolazione tra questi hamiltonians nel problema della simulazione dipendente dal tempo è sufficientemente lenta, ma è possibile che si concluda, con una probabilità elevata, in uno stato di base dell'$H hamiltoniana finale\_{\Text{end}} $. Sebbene la preparazione di buone approssimazioni a stati di base hamiltoniana possa procedere in questo modo chiamando sugli algoritmi di simulazione hamiltoniana dipendenti dal tempo come subroutine, altri approcci concettualmente diversi, ad esempio il quantum variazione eigensolver sono possibili.

Un'altra applicazione onnipresente nella chimica quantistica è la stima dell'energia di stato di base di hamiltonians che rappresenta i passaggi intermedi della reazione chimica. Uno schema di questo tipo può, ad esempio, basarsi sulla preparazione dello stato di adiabatica per creare lo stato di base e quindi incorporare la simulazione hamiltoniana indipendente dal tempo come subroutine nella caratterizzazione della valutazione della fase per estrarre questa energia con un errore finito e probabilità di esito positivo. 

L'astrazione degli algoritmi di simulazione come i tipi definiti dall'utente `SimulationAlgorithm` e `TimeDependentSimulationAlgorithm` ci permette di incorporare facilmente le proprie funzionalità in algoritmi quantistici più sofisticati. In questo modo viene motivato a eseguire la stessa operazione per le subroutine di uso comune.

Si definisce quindi la funzione comoda

```qsharp
function InterpolatedEvolution(
        interpolationTime : Double, 
        evolutionGeneratorStart : EvolutionGenerator,
        evolutionGeneratorEnd : EvolutionGenerator,
        timeDependentSimulationAlgorithm : TimeDependentSimulationAlgorithm)
: (Qubit[] => Unit is Adj + Ctl) {
        ...
}
 
```

Viene restituita un'operazione unitaria che implementa tutti i passaggi della preparazione dello stato di adiabatica. Il primo parametro `interpolatedTime` definisce il tempo di interpolazione lineare tra l'Hamiltoniana iniziale descritta dal secondo parametro `evolutionGeneratorStart` e l'Hamiltoniana finale descritto dal terzo parametro `evolutionGeneratorEnd`. Il quarto parametro `timeDependentSimulationAlgorithm` è la scelta dell'algoritmo di simulazione. Si noti che se `interpolatedTime` è sufficientemente lunga, uno stato iniziale di base rimane uno stato di base istantaneo dell'Hamiltoniana per l'intera durata della simulazione dipendente dal tempo e termina quindi nello stato di base dell'Hamiltoniana finale.

Viene anche definita un'operazione utile che esegue automaticamente tutti i passaggi di un tipico esperimento di chimica quantistica. Ad esempio, sono disponibili gli elementi seguenti, che restituisce una stima di energia dello stato prodotto dalla preparazione dello stato adiabatica:

```qsharp
operation EstimateAdiabaticStateEnergy(
    nQubits : Int,
    statePrepUnitary : (Qubit[] => Unit),
    adiabaticUnitary : (Qubit[] => Unit),
    qpeUnitary: (Qubit[] => Unit is Adj + Ctl),
    phaseEstAlgorithm : ((DiscreteOracle, Qubit[]) => Double))
: Double {
...
}
```

`nQubits` è il numero di qubits usato per codificare lo stato quantum iniziale. `statePrepUnitary` prepara lo stato di avvio dalla base computazionale $ \ket{0\cdots 0} $. `adiabaticUnitary` è l'operazione unitaria che implementa la preparazione dello stato adiabatica, ad esempio prodotta dalla funzione `InterpolatedEvolution`. `qpeUnitary` è l'operazione unitaria utilizzata per eseguire la stima della fase sullo stato del quantum risultante. `phaseEstAlgorithm` è la scelta dell'algoritmo di stima della fase.

> [!TIP]
> Le applicazioni di preparazione dello stato di adiabatica sono descritte negli esempi. Per il modello Ising usando un'implementazione manuale della preparazione dello stato adiabatica rispetto all'uso della funzione `AdiabaticEvolution`, vedere l' [esempio **AdiabaticIsing** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/adiabatic).
> Per la stima della fase e la preparazione dello stato adiabatica nel modello Ising, vedere l' [esempio **IsingPhaseEstimation** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/phase-estimation).

> [!TIP]
> La [simulazione dell'idrogeno molecolare](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/command-line) è un esempio interessante e breve. Il modello e i risultati sperimentali segnalati in [Malley et. al.](https://arxiv.org/abs/1512.06860) richiede solo matrici Pauli e assume il formato $ \hat H = g\_{0}I\_0I\_1 + g\_1 {Z\_0} + g\_2 {Z\_1} + g\_3 {Z\_0} {Z\_1} + g\_4 {Y\_0} {Y\_1} + g\_5 {X\_0} {X\_1} $. Si tratta di un'hamiltoniana efficace che richiede solo 2 qubits, in cui le costanti $g $ vengono calcolate dalla distanza $R $ tra i due atomi idrogeno. Utilizzando le funzioni Canon, Paulis viene convertito in unitaries e si evolve in brevi periodi di tempo utilizzando la scomposizione Trotter-Suzuki. È possibile creare una corretta approssimazione allo stato $H _2 $ Ground senza usare la preparazione dello stato adiabatica, quindi l'energia dello stato di base può essere trovata direttamente usando la stima della fase della Canon.

## <a name="shors-algorithm"></a>Algoritmo di Shor ##
L'algoritmo di Shor rimane uno degli sviluppi più significativi in quantum computing, perché ha dimostrato che i computer Quantum potevano essere usati per risolvere problemi importanti e attualmente più classici.
L'algoritmo di Shor offre un modo rapido per fattorizzare numeri elevati usando un computer quantistico, un problema denominato *factoring*.
La sicurezza di molti crittosistemi presenti si basa sul presupposto che non esista alcun algoritmo rapido per il factoring.
Di conseguenza, l'algoritmo di Shor ha avuto un impatto profondo sul modo in cui si pensa alla sicurezza in un mondo di post-Quantum.

L'algoritmo di Shor può essere considerato come un algoritmo ibrido.
Il computer quantum viene usato per eseguire un'attività complessa a livello di calcolo, nota come periodo di ricerca.
I risultati dell'individuazione del periodo vengono quindi elaborati in modalità classica per stimare i fattori.
Questi due passaggi vengono esaminati di seguito.

### <a name="period-finding"></a>Ricerca periodica ###

Avendo visto il funzionamento della trasformazione e della stima della fase del quantum (vedere [algoritmi quantistici](xref:microsoft.quantum.libraries.standard.algorithms)), è possibile usare questi strumenti per risolvere un problema di calcolo di livello classico, denominato *ricerca periodica*.  Nella sezione successiva si vedrà come applicare il periodo di ricerca al factoring.

Dato due numeri interi $a $ e $N $, in cui $a < N $, l'obiettivo della ricerca del periodo, detto anche ricerca dell'ordine, consiste nell'individuare l' _ordine_ $r $ di $a $ modulo $N $, dove $r $ è definito come valore intero meno positivo in modo che $a ^ r \equiv 1 \Text{mod} N $.  

Per trovare l'ordine usando un computer Quantum, è possibile usare l'algoritmo di stima della fase applicato all'operatore unitario seguente $U _a $: $ $ U_a \ket{x} \equiv \ket{(AX) \Text{mod} N}. $ $ i autovettori di $U _a $ sono per Integer $s $ e $0 \ Leq s \leq r-$1, $ $ \ket{x_s} \equiv 1/\sqrt{r} \sum\_{k = 0} ^ {r-1} e ^ {\frac{-2\pi i SK} {r}} \ket{a ^ k\text {mod} N}, $ $ sono _autostati_ di $U _A $.
Gli autovalori di $U _a $ sono $ $ U\_\ket{x\_s} = e ^ {2 \ PI i s/r} \ket{x\_s}. $$

La valutazione della fase genera quindi gli autovalori $e ^ {2 \ PI i s/r} $ da cui $r $ possono essere apprese in modo efficiente usando [frazioni continue](https://en.wikipedia.org/wiki/Continued_fraction) da $s/r $.

Il diagramma di circuito per l'individuazione del periodo Quantum è:

![Diagramma di circuito per la ricerca del periodo quantico](./../../media/QPE.svg)

I $2n $ qubits vengono inizializzati in $ \ket{0}$ e $n $ qubits vengono inizializzati in $ \ket{1}$.
Il lettore può anche chiedersi perché il registro Quantum per il autostati venga inizializzato su $ \ket{1}$.
Poiché non si conosce l'ordine $r $ in anticipo, non è possibile preparare gli Stati di $ \ket{x_s} $ direttamente.
Per fortuna, si scopre che $1/\ sqrt {r} \sum\_{s = 0} ^ {r-1} \ket{x\_s} = \ket{1}$.
Non è necessario preparare effettivamente $ \ket{x} $!
È possibile preparare solo un registro Quantum di $n $ qubits nello stato $ \ket{1}$. 

Il circuito contiene il QFT e varie attività di controllo.
Il QFT Gate è stato descritto [in precedenza](xref:microsoft.quantum.libraries.standard.algorithms).
La $U controllata _a $ Gate esegue il mapping di $ \ket{x} $ a $ \ket{(AX) \Text{mod} N} $ se il controllo qubit è $ \ket{1}$ ed esegue il mapping di $ \ket{x} $ a $ \ket{x} $ in caso contrario.

Per ottenere $ (a ^ NX) \Text{mod} N $, è possibile applicare semplicemente la $U controllata _ {a ^ N} $, dove si calcola $a ^ n \Text{mod} N $ classiche per inserire il circuito Quantum.  
I circuiti per ottenere tale aritmetica modulare sono stati descritti nella [documentazione aritmetica quantistica](./algorithms.md#arithmetic), in particolare è necessario un circuito di elevamento a potenza modulare per implementare le operazioni di $U\_{a ^ i} $.

Sebbene il circuito precedente corrisponda alla [stima della fase quantistica](xref:microsoft.quantum.characterization.quantumphaseestimation) e Abilita in modo esplicito l'individuazione degli ordini, è possibile ridurre il numero di qubits necessari. È possibile seguire il metodo di Beauregard per l'individuazione degli ordini come descritto [nella pagina 8 di arXiv: quanti-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)oppure usare una delle routine di stima della fase disponibili in Microsoft. Quantum. characteration. Ad esempio, la [stima della fase affidabile](xref:microsoft.quantum.characterization.robustphaseestimation) usa anche un qubit aggiuntivo.
 
### <a name="factoring"></a>Factoring ###
L'obiettivo del factoring consiste nel determinare i due fattori principali di Integer $N $, dove $N $ è un numero $n $ bit.  
Il factoring è costituito dai passaggi descritti di seguito. I passaggi sono suddivisi in tre parti: una routine di pre-elaborazione classica (1-4); routine di calcolo quantistica per trovare l'ordine di $a mod \Text{} N $ (5); e una routine di postelaborazione classica per derivare i fattori principali dall'ordine (6-9).

La routine di pre-elaborazione classica prevede i passaggi seguenti:
1. Se $N $ è pari, restituire il fattore principale $2 $.
2. Se $N = p ^ q $ per $p \geq1 $, $q \geq2 $, restituire il fattore principale $p $.  Questo passaggio viene eseguito in modalità classica.
3. Scegliere un numero casuale $a $ tale che $1 < un < N-$1.
4. Se $ \Text{GCD} (a, N) > 1 $, restituisce il fattore principale $ \Text{GCD} (a, N) $. Questo passaggio viene calcolato usando l'algoritmo di Euclide.
Se non viene restituito alcun fattore principale, si procede alla routine Quantum:
5. Chiamare l'algoritmo di ricerca del periodo quantico per calcolare l'ordine $r $ of $a \Text{mod} N $. Usare $r $ nella routine di postelaborazione classica per determinare i fattori principali:
6. Se $r $ è dispari, tornare al passaggio di pre-elaborazione (3).
7. Se $r $ è pari e $a ^ {r/2} =-1 \ text {mod} N $, tornare al passaggio di pre-elaborazione (3).
8. Se $ \Text{GCD} (a ^ {r/2} + 1, N) $ è un fattore non semplice di $N $, restituisce $ \Text{GCD} (a ^ {r/2} + 1, N) $.
9. Se $ \Text{GCD} (a ^ {r/2}-1, N) $ è un fattore non semplice di $N $, restituisce $ \Text{GCD} (a ^ {r/2}-1, N) $.


L'algoritmo di factoring è probabilistico: è possibile che con la probabilità sia presente almeno una metà che $r $ sarà pari e $a ^ {r/2} \neq-1 \Text{mod} N $, producendo così un fattore di primo livello.  Per [informazioni](xref:microsoft.quantum.more-information)dettagliate, vedere il [documento originale di Shor](https://doi.org/10.1109/SFCS.1994.365700) o uno dei testi di *calcolo Quantum di base* in.
Se non viene restituito un fattore principale, si ripete semplicemente l'algoritmo dal passaggio (1).  Dopo $n $ tentativi, la probabilità che ogni tentativo abbia esito negativo è maggiore di $2 ^ {-n} $.
Quindi, dopo aver ripetuto l'algoritmo, un numero ridotto di volte l'esito positivo è praticamente sicuro.
