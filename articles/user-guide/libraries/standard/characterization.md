---
title: Caratterizzazione e statistiche del quantum
description: Informazioni sulla modalità di utilizzo delle statistiche di misurazione dalle stime della fase per stimare i valori dei risultati nella programmazione quantistica.
author: bradben
uid: microsoft.quantum.libraries.characterization
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8dddc15354c32808e7ad1310bce233ee3dc93fe8
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835639"
---
# <a name="quantum-characterization-and-statistics"></a>Caratterizzazione e statistiche del quantum #

È fondamentale essere in grado di caratterizzare gli effetti delle operazioni per sviluppare algoritmi quantistici utili.
Si tratta di una sfida complessa perché ogni misura di un sistema quantico restituisce al massimo una quantità di informazioni.
Per apprendere un autovalore, lasciare da solo uno stato quantico, i risultati di molte misurazioni devono essere Uniti in modo che l'utente possa raccogliere i molti bit di informazioni necessari per rappresentare questi concetti.
Gli Stati Quantum sono soprattutto vexing perché il [teorema di non clonazione](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem) indica che non esiste alcun modo per apprendere uno stato quantico arbitrario da una singola copia dello stato, perché questa operazione consente di creare copie dello stato.
Questa offuscamento dello stato del quantum dall'utente si riflette nel fatto che non Q# espone o addirittura definisce lo stato dei programmi quantistici. *is*
In questo modo si avvicina la caratterizzazione quantistica considerando le operazioni e gli Stati come Black-Box; Questo approccio condivide molto in comune con la pratica sperimentale di caratterizzazione quantistica, verifica e convalida (QCVV).

La caratterizzazione è diversa da molte altre librerie illustrate in precedenza.
L'obiettivo è quello di ottenere meno informazioni classiche sul sistema, anziché eseguire una trasformazione unitaria su un vettore di stato.
Queste librerie devono quindi combinare l'elaborazione di informazioni sia classica che quantistica.


## <a name="iterative-phase-estimation"></a>Valutazione della fase iterativa ##

La visualizzazione della programmazione quantistica in termini di caratterizzazione quantistica suggerisce un'alternativa utile alla stima della fase quantistica.
Ovvero, anziché preparare un $n registro $-qubit in modo che contenga una rappresentazione binaria della fase come la stima della fase quantistica, è possibile visualizzare la stima della fase come processo mediante il quale un agente *classico* apprende le proprietà di un sistema Quantum attraverso le misurazioni.
Si procede come nel caso di Quantum usando il contraccolpo della fase per trasformare le applicazioni di un'operazione di colore nero in rotazioni in base a un angolo sconosciuto, ma misurerà il qubit ancilla che viene ruotato a ogni passaggio immediatamente dopo la rotazione.
Questo ha il vantaggio di richiedere un solo qubit aggiuntivo per eseguire il contraccolpo della fase descritto nel caso quantum, in quanto viene quindi appresa la fase dai risultati della misurazione in ogni fase in modo iterativo.  
Ogni metodo proposto di seguito utilizza una strategia diversa per la progettazione di esperimenti e metodi di elaborazione dei dati diversi per apprendere la fase.  Ognuno di essi ha un vantaggio univoco, dal momento che presenta limiti di errore rigorosi, alle capacità di incorporare informazioni precedenti, tollerare errori o eseguire in memoria computer limitted classici.

In una descrizione della stima della fase iterativa, si considererà un $U unitario $ dato come operazione Black Box.
Come descritto nella sezione relativa ai Oracle in [strutture di dati](xref:microsoft.quantum.libraries.data-structures), i Q# modelli Canon tali operazioni vengono eseguite dal <xref:microsoft.quantum.oracles.discreteoracle> tipo definito dall'utente, definito dal tipo di tupla `((Int, Qubit[]) => Unit : Adjoint, Controlled)` .
In concreto, se `U : DiscreteOracle` , `U(m)` implementa $U ^ m $ per `m : Int` .

Con questa definizione, ogni passaggio della stima della fase iterativa procede preparando una qubit ausiliaria nello stato $ \ket{+} $ insieme allo stato iniziale $ \ket{\Phi} $ che si presuppone sia un [autovettore](xref:microsoft.quantum.concepts.matrix-advanced) di $U (m) $, ad esempio $U (m) \ket{\Phi} = e ^ {im\phi} \ KET {\ Phi} $.  
Viene quindi usata un'applicazione controllata di `U(m)` che prepara lo stato $ \left (R \_ 1 (m \Phi) \ket{+} \right) \ket{\Phi} $.
Come nel caso del quantum, l'effetto di un'applicazione controllata del Oracle `U(m)` è esattamente lo stesso dell'applicazione $R _1 $ per la fase sconosciuta in $ \ket{+} $, in modo da poter descrivere gli effetti di $U $ in questo modo più semplice.
Facoltativamente, l'algoritmo ruota quindi il qubit del controllo applicando $R _1 (-m\theta) $ per ottenere uno stato $ \ket{\psi} = \left (R \_ 1 (m [\Phi-\theta]) \ket{+} \right) \ket{\Phi} $ $.
Il qubit ausiliario usato come controllo per `U(m)` viene quindi misurato in $X $ base per ottenere un singolo classico `Result` .

A questo punto, la ricostruzione della fase dai `Result` valori ottenuti tramite la stima della fase iterativa è un problema classico di inferenza statistica.
La ricerca del valore di $m $ che ingrandisce le informazioni acquisite, dato un metodo di inferenza fisso, rappresenta semplicemente un problema nelle statistiche.
Questa operazione viene sottolineata in modo da descrivere brevemente la stima della fase iterativa a un livello teorico nel formalismo per la stima dei parametri Bayes prima di procedere con la descrizione degli algoritmi statistici disponibili in Q# Canon per la risoluzione di questo problema di inferenza classico.

### <a name="iterative-phase-estimation-without-eigenstates"></a>Valutazione della fase iterativa senza autostati ###

Se viene fornito uno stato di input che non è un autostato, ovvero se $U (m) \ket{\Phi \_ j} = e ^ {im\phi \_ j} $, il processo di valutazione della fase Guida in modo non deterministico lo stato del quantum verso un singolo autostato di energia.  Il autostato in cui si converge a è il autostato che con maggiore probabilità produrrà l'oggetto osservato `Result` .

In particolare, un singolo passaggio di PE esegue la trasformazione non unitaria seguente in uno stato \begin{align} \ sum_j \sqrt{\Pr (\Phi \_ j)} \ket{\Phi \_ j} \mapsto \sum \_ j\frac {\ sqrt {\ PR (\Phi \_ j)} \sqrt{\Pr (\Text{result} | \Phi \_ j)} \Ket{\Phi \_ j}} {\sqrt{\Pr (\Phi \_ j) \sum \_ j \Pr (\Text{result} | \Phi \_ j)}}.
\end{align} poiché questo processo viene iterato su più `Result` valori, autostati che non hanno valori massimi di $ \ prod_k \Pr (\Text{result} \_ k | \Phi \_ j) $ verranno eliminati in modo esponenziale.
Di conseguenza, il processo di inferenza tenderà a convergere agli Stati con un singolo autovalore se gli esperimenti vengono scelti correttamente.

Bayes ' teorema suggerisce inoltre che lo stato risultante dalla stima della fase sia scritto nel formato \begin{align} \frac{\sqrt{\Pr (\Phi \_ j)} \sqrt{\Pr (\Text{result} | \Phi \_ j)} \ket{\Phi \_ j}} {\sqrt{\Pr (\Phi \_ j) \Sum \_ j \Pr (\Text{result} | \Phi \_ j)}} = \ sum_j \sqrt{\Pr (\Phi \_ j | \Text{result})} \ket{\Phi \_ j}.
\end{align} here $ \Pr (\Phi \_ j | \Text{result}) $ può essere interpretted come probabilità che venga attribuita a ogni ipotesi relativa al autostati dato:

1. conoscere lo stato del Quantum prima della misurazione,
2. conoscenza della autostati di $U $ e,
3. conoscenza degli autovalori di $U $.

L'apprendimento di questi tre elementi è spesso esponenzialmente difficile in un computer classico.
L'utilità della valutazione della fase si verifica, a un certo punto, dal fatto che può eseguire tale attività di apprendimento quantico senza conoscerne alcuno.
La stima della fase per questo motivo viene visualizzata all'interno di una serie di algoritmi Quantum che forniscono velocità esponenziali.

### <a name="bayesian-phase-estimation"></a>Valutazione della fase Bayes ###

> [!TIP]
> Per ulteriori informazioni sulla stima della fase bayesiano, vedere l'esempio [**PhaseEstimation**](https://github.com/microsoft/Quantum/tree/main/samples/characterization/phase-estimation) .

Il concetto di stima della fase Bayes è semplice.
Si raccolgono le statistiche di misurazione dal protocollo di stima della fase e quindi si elaborano i risultati usando l'inferenza Bayes e si fornisce una stima del parametro.
Questa elaborazione consente di stimare il valore di autovalore e l'incertezza nella stima.
Consente inoltre di eseguire esperimenti adattivi e di utilizzare le informazioni precedenti.
Lo svantaggio principale dei metodi è che è richiesto dal punto di vista del calcolo.

Per comprendere il funzionamento del processo di inferenza Bayes, considerare il caso di elaborazione di un singolo `Zero` risultato.
Si noti che $X = \ket{+} \bra{+}-\ket {-} \bra {-} $, in modo che $ \ket{+} $ sia l'unico autostato positivo di $X $ corrispondente a `Zero` .
La probabilità di osservare `Zero` una [ `PauliX` misura](xref:microsoft.quantum.concepts.pauli) sul primo qubit dato uno stato di input $ \ket{\psi}\ket{\Phi} $ è quindi \begin{Equation} \Pr (\texttt{zero} | \psi) = \left | \braket{+ | \psi} \right | ^ 2.
\end{Equation} nel caso della stima della fase iterativa, è necessario che $ \ket{\psi} = R_1 (m [\Phi-\theta]) \ket{+} $, in modo che \begin{align} \Pr (\texttt{Zero} | \Phi; m, \theta) & = \left | \braket{+ | R_1 (m [\Phi-\theta]) | +} \right | ^ 2 \\ \\ & = \left | \frac12 \left (\bra {0} + \bra {1} \right) \left (\ket {0} + e ^ {i m [\Phi-\theta]} \ket {1} \right) \right | ^ 2 \\ \\ & = \left | \frac{1 + e ^ {i m [\phi-\theta]}} {2} \right | ^ 2 \\ \\ & = \cos ^ 2 (m [\Phi-\theta]/2) \tag{★} \label{EQ: fase-est-probabilità}.
\end{align}, ovvero la stima della fase iterativa consiste nell'apprendimento della frequenza di oscillazione di una funzione sinusoidale, data la possibilità di capovolgere un Coin con una distorsione fornita da tale sinusoide.
Seguendo la terminologia classica tradizionale, viene chiamato $ \eqref{EQ: fase-est-probabilità} $ la *funzione di probabilità* per la stima della fase iterativa.

Osservando una `Result` dalla funzione di probabilità di stima della fase iterativa, è possibile usare la regola Bayes per prescrivere ciò che si dovrebbe ritenere che la fase stia seguendo tale osservazione.
In concreto, \begin{Equation} \Pr (\Phi | d) = \frac{\Pr (d | \Phi) \Pr (\Phi)} {\int \Pr (d | \Phi) \Pr (\Phi) {\mathrm d} \Phi} \Pr (\Phi), \end{Equation} in cui $d \In \\ {\texttt{zero}, \texttt{One} \\ } $ è a `Result` e dove $ \Pr (\Phi) $ descrive le convinzioni precedenti di $ \Phi $.
In questo modo, la natura iterativa della stima della fase iterativa è esplicita, in quanto la distribuzione posteriore $ \Pr (\Phi | d) $ descrive le proprie convinzioni immediatamente prima dell'osservazione del successivo `Result` .

In qualsiasi momento durante questa procedura, è possibile segnalare la fase $ \hat{\Phi} $ dedotta dal controller classico come \begin{Equation} \hat{\Phi} \mathrel{: =} \expect [\Phi | \Text{data}] = \int \Phi \Pr (\Phi | \Text{Data}) {\mathrm d} \Phi, \end{Equation} dove $ \Text{data} $ sta per l'intero record di tutti `Result` i valori ottenuti.

L'inferenza bayesiano esatta è in pratica ingestibile.
Per scoprire che si vuole conoscere una variabile $n $ bit $x $.
La distribuzione precedente $ \Pr (x) $ supporta più di $2 ^ n $ ipotetici valori di $x $.
Ciò significa che se è necessaria una stima accurata della $x $ then la stima della fase Bayes potrebbe richiedere tempi di elaborazione e memoria proibitivi.
Sebbene per alcune applicazioni, ad esempio la simulazione quantistica, l'accuratezza limitted richiesta non Ostia ad altri metodi, ad esempio l'algoritmo Shor, non è in grado di utilizzare l'inferenza bayesiano esatta entro il suo passaggio di stima della fase.  Per questo motivo, vengono fornite anche le implementazioni per i metodi Bayes approssimativi, ad esempio la [stima della fase di Walk casuale (RWPE)](xref:microsoft.quantum.research.characterization.randomwalkphaseestimation) e anche approcci non Bayes come la [stima della fase affidabile](xref:microsoft.quantum.characterization.robustphaseestimation).

### <a name="robust-phase-estimation"></a>Stima della fase affidabile ###

Un massimo di una ricostruzione Bayes a *posteriori* di una fase stimata dai risultati della misurazione è esponenzialmente difficile nel peggiore dei casi. In questo modo, la maggior parte degli algoritmi di stima della fase più pratici sacrificano una certa qualità nella ricostruzione, in cambio di una quantità di post-elaborazione classica che invece si ridimensiona in base al numero di misurazioni effettuate.

Uno di questi esempi con una fase di post-elaborazione classica efficiente è l' [algoritmo di stima della fase affidabile](https://arxiv.org/abs/1502.02677), con la firma e gli input citati in precedenza. Si presuppone che le caselle nere di input $U $ siano inserite in un pacchetto come `DiscreteOracle` tipo e pertanto solo le query con potenze integer del $U controllato $. Se lo stato di input nel `Qubit[]` registro è autostato $U \ket{\psi} = e ^ {i\phi} \ KET {\ psi} $, l'algoritmo di stima della fase affidabile restituisce una stima $ \hat{\Phi}\In [-\Pi, \Pi) $ di $ \Phi $ come `Double` .

La funzionalità più importante della valutazione delle fasi affidabili, che è condivisa con la maggior parte delle altre varianti utili, consiste nel fatto che la qualità della ricostruzione di $ \hat{\Phi} $ è in un certo senso Heisenberg-Limited. Ciò significa che se la deviazione di $ \hat{\Phi} $ dal valore true è $ \sigma $, $ \sigma $ esegue il ridimensionamento inversamente proporzionale al numero totale di query $Q $ effettuate a controllata-$U $, ad esempio $ \sigma = \mathcal{O} (1/Q) $. La definizione della deviazione varia ora tra algoritmi di stima diversi. In alcuni casi, potrebbe significare che con almeno $ \mathcal{O} (1) $ probabilità, l'errore di stima $ | \hat{\Phi}-\Phi | \_ \circ\le \sigma $ su una misura circolare $ \circ $. Per una stima della fase affidabile, la deviazione è esattamente la varianza $ \sigma ^ 2 = \mathbb{E} \_ \hat{\Phi} [(\mod \_ {2 \ PI} (\hat{\Phi}-\Phi + \Pi)-\Pi) ^ 2] $ Se si esegue il wrapping di fasi periodiche in un singolo intervallo finito $ (-\Pi, \Pi] $. Più precisamente, la deviazione standard nella stima della fase affidabile soddisfa le disuguaglianze $ $ \begin{align} 2,0 \Pi/Q \Le \sigma \Le 2 \ PI/2 ^ {n} \Le 10.7 \ PI/Q, \end{align} $ $ dove viene raggiunto il limite inferiore nel limite di asintoticamente large $Q $ e il limite superiore è garantito anche per piccole dimensioni di campionamento.  Si noti che $n $ selezionato dall' `bitsPrecision` input, che definisce in modo implicito $Q $.

Altri dettagli pertinenti includono, ad esempio, il sovraccarico di spazio ridotto di soli $1 $ ancilla qubit o che la procedura non è adattiva, ovvero la sequenza richiesta di esperimenti Quantum è indipendente dai risultati della misurazione intermedia. In questo ed esempi imminenti in cui la scelta dell'algoritmo di stima della fase è importante, è necessario fare riferimento alla documentazione, ad esempio @"microsoft.quantum.characterization.robustphaseestimation" e alle pubblicazioni a cui si fa riferimento, per ottenere ulteriori informazioni e per la loro implementazione.

> [!TIP]
> Sono disponibili molti esempi in cui viene usata la stima della fase affidabile. Per la stima della fase nell'estrazione dell'energia dello stato di base di un sistema fisico diverso, vedere l'esempio di [ **simulazione H2** ](https://github.com/microsoft/Quantum/tree/main/samples/simulation/h2/command-line), l' [esempio **SimpleIsing** ](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/simple)e l'esempio di [ **modello Hubbard** ](https://github.com/microsoft/Quantum/tree/main/samples/simulation/hubbard).


### <a name="continuous-oracles"></a>Oracle continui ###

È anche possibile generalizzare dal modello Oracle usato in precedenza per consentire Oracle a tempo continuo, modellati in base al tipo di canone <xref:microsoft.quantum.oracles.continuousoracle> .
Si consideri che invece di un singolo operatore unitario $U $, abbiamo una famiglia di operatori unitari $U (t) $ per $t \in \mathbb{R} $, in modo che $U (t) U/s $ = $U (t + s) $.
Si tratta di una dichiarazione più vulnerabile rispetto al caso discreto, dal momento che è possibile costruire un oggetto <xref:microsoft.quantum.oracles.discreteoracle> limitando $t = m \, \delta t $ per alcuni \delta $ $ corretti.
Per [teorema di Stone](https://en.wikipedia.org/wiki/Stone%27s_theorem_on_one-parameter_unitary_groups), $U (t) = \exp (i H t) $ per un operatore $H $, dove $ \exp $ è la matrice esponenziale, come descritto in [matrici avanzate](xref:microsoft.quantum.concepts.matrix-advanced).
Un autostato $ \ket{\Phi} $ di $H $ tale che $H \ket{\Phi} = \Phi \ket{\Phi} $ è quindi anche un autostato di $U (t) $ per tutti $t $, \begin{Equation} U (t) \ket{\Phi} = e ^ {i \Phi t} \ket{\Phi}.
\end{equation}

È possibile applicare esattamente la stessa analisi descritta per la [stima della fase Bayes](#bayesian-phase-estimation) e la funzione probabilità è esattamente la stessa per questo modello Oracle più generale: $ $ \Pr (\texttt{zero} | \Phi; t, \theta) = \cos ^ 2 \ Left (\frac{t [\Phi-\theta]} {2} \right).
$ $ Inoltre, se $U $ è una simulazione di un generatore dinamico, come nel caso della [simulazione hamiltoniana](xref:microsoft.quantum.libraries.applications#hamiltonian-simulation), viene interpretato $ \Phi $ come energia.
Quindi, l'uso della stima della fase con le query continue consente di apprendere lo [spettro di energia simulato di molecole](https://arxiv.org/abs/quant-ph/0604193), [materiali](https://arxiv.org/abs/1510.03859) o [teorie sui campi](https://arxiv.org/abs/1111.3633v2) senza compromettere la scelta degli esperimenti richiedendo $t $ come valore integer.

### <a name="random-walk-phase-estimation"></a>Valutazione della fase di Walk casuale ###

Q# fornisce un'approssimazione utile della stima della fase Bayes progettata per l'uso vicino ai dispositivi Quantum che operano condizionando un percorso casuale sul record di dati ottenuto dalla stima della fase iterativa.
Questo metodo è sia adattivo che completamente deterministico, consentendo una scalabilità quasi ottimale degli errori nella fase stimata $ \hat{\Phi} $ con sovraccarico di memoria molto bassa.

Il protocollo usa un metodo di inferenza Bayes approssimativo che presuppone che la distribuzione precedente sia gaussiana.
Questo presupposto di Gauss consente di usare una formula analitica per l'esperimento che riduce al minimo la varianza posteriore.
L'algoritmo, quindi, in base al risultato di tale esperimento, sposta la stima di $ \Phi $ Left o right in base a una quantità predeterminata e compatta la varianza in base a una quantità predeterminata.
Questa media e varianza forniscono tutte le informazioni necessarie per specificare un gaussiana prima di $ \Phi $ per l'esperimento successivo.
Gli errori di misurazione imprevisti o il risultato reale che si trova sulla parte finale del precedente, possono causare un errore di questo metodo.
Il ripristino da un errore viene effettuato eseguendo esperimenti per verificare se la media e la deviazione standard correnti sono appropriate per il sistema.
In caso contrario, l'algoritmo esegue un passaggio inverso del percorso e il processo continua.
La possibilità di eseguire un'istruzione all'indietro consente inoltre all'algoritmo di apprendere anche se la deviazione standard iniziale precedente è inapropriately Small.

## <a name="calling-phase-estimation-algorithms"></a>Algoritmi di stima della fase chiamante ##

Ogni operazione di stima della fase fornita con il Q# canone accetta un set di input diverso parametrizzazione la qualità richiesta dalla stima finale $ \hat{\Phi} $.
Questi diversi input, tuttavia, condividono tutti diversi input in comune, in modo che l'applicazione parziale sui parametri di qualità produce una firma comune.
Ad esempio, l' <xref:microsoft.quantum.characterization.robustphaseestimation> operazione descritta nella sezione successiva presenta la firma seguente:

```qsharp
operation RobustPhaseEstimation(bitsPrecision : Int, oracle : DiscreteOracle, eigenstate : Qubit[])  : Double
```

L' `bitsPrecision` input è univoco per `RobustPhaseEstimation` , mentre `oracle` e `eigenstate` sono in comune.
Quindi, come illustrato in **H2Sample**, un'operazione può accettare un algoritmo di stima della fase iterativo con un input del modulo `(DiscreteOracle, Qubit[]) => Unit` per consentire a un utente di specificare algoritmi di stima della fase arbitraria:

```qsharp
operation H2EstimateEnergy(
    idxBondLength : Int,
    trotterStepSize : Double,
    phaseEstAlgorithm : ((DiscreteOracle, Qubit[]) => Double))
: Double
```

Questi algoritmi di stima della fase miriade sono ottimizzati per diverse proprietà e parametri di input, che devono essere riconosciuti per eseguire la scelta migliore per l'applicazione di destinazione. Ad esempio, alcuni algoritmi di stima della fase sono adattivi, vale a dire che i passaggi futuri sono controllati in modo classico dai risultati della misurazione dei passaggi precedenti. Alcuni richiedono la possibilità di exponentiate il proprio Oracle unitario nero in base a poteri reali arbitrari, mentre altri richiedono solo le potenze di tipo Integer ma sono in grado di risolvere solo un modulo di stima della fase $2 \ PI $. Alcuni richiedono molte qubits ausiliarie e altre ne richiedono solo una.

Analogamente, l'uso della valutazione della fase di Walk casuale procede in modo molto simile a quello di altri algoritmi forniti con la Canon:

```qsharp
operation ApplyExampleOracle(
    eigenphase : Double,
    time : Double,
    register : Qubit[])
: Unit is Adj + Ctl {
    Rz(2.0 * eigenphase * time, register[0]);
}

operation EstimateBayesianPhase(eigenphase : Double) : Double {
    let oracle = ContinuousOracle(ApplyExampleOracle(eigenphase, _, _));
    using (eigenstate = Qubit()) {
        X(eigenstate);
        // The additional inputs here specify the mean and variance of the prior, the number of
        // iterations to perform, how many iterations to perform as a maximum, and how many
        // steps to roll back on an approximation failure.
        let est = RandomWalkPhaseEstimation(0.0, 1.0, 61, 100000, 1, oracle, [eigenstate]);
        Reset(eigenstate);
        return est;
    }
}
```
