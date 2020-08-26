---
title: Scrivere e simulare programmi a livello di qubit in Q#
description: Esercitazione dettagliata sulla scrittura e la simulazione di un programma Quantum che opera a livello di singolo qubit
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 10/06/2019
uid: microsoft.quantum.circuit-tutorial
ms.topic: tutorial
no-loc:
- Q#
- $$v
ms.openlocfilehash: 39b2d762c0efbfa4bb3a60a1dcee6bcbe2bd91a9
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863340"
---
# <a name="tutorial-write-and-simulate-qubit-level-programs-in-q"></a>Esercitazione: scrivere e simulare programmi a livello di qubit in Q\#

Introduzione all'esercitazione su Quantum Development Kit per la scrittura e la simulazione di un programma Quantum di base che opera sui singoli qubits. 

Sebbene Q# sia stato creato principalmente come linguaggio di programmazione di alto livello per i programmi Quantum su larga scala, può essere usato altrettanto facilmente per esplorare il livello inferiore dei programmi quantistici: indirizzamento diretto a qubits specifici.
La flessibilità di Q# consente agli utenti di approcciare i sistemi quantistici da un livello di astrazione di questo tipo e in questa esercitazione viene approfondita la qubits.
In particolare, diamo uno sguardo al cofano della [trasformazione Quantum Fourier](https://en.wikipedia.org/wiki/Quantum_Fourier_transform), una subroutine che è parte integrante di molti algoritmi quantistici più grandi.

Si noti che questa visualizzazione di basso livello dell'elaborazione delle informazioni sui quantum è spesso descritta in termini di "[circuiti quantistici](xref:microsoft.quantum.concepts.circuits)", che rappresentano l'applicazione sequenziale delle attività di controllo per qubits specifici di un sistema.

Quindi, le operazioni a singolo e multiqubit che si applicano in modo sequenziale possono essere facilmente rappresentate in un "diagramma di circuito".
In questo caso, si definirà un' Q# operazione per eseguire la completa trasformazione Quantum a tre qubit, che presenta la rappresentazione seguente come circuito:

<br/>
<img src="../media/qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

## <a name="prerequisites"></a>Prerequisiti

* [Installare](xref:microsoft.quantum.install) Quantum Development Kit usando il linguaggio e l'ambiente di sviluppo preferiti.
* Se il QDK è già installato, assicurarsi di aver eseguito l'[aggiornamento](xref:microsoft.quantum.update) alla versione più recente


## <a name="in-this-tutorial-youll-learn-how-to"></a>In questa esercitazione si apprenderà come:

> [!div class="checklist"]
> * Definire operazioni Quantum in Q#
> * Chiamare Q# le operazioni direttamente dal prompt dei comandi o usando un programma host classico
> * Simulare un'operazione Quantum dall'allocazione qubit all'output di misurazione
> * Osservare il modo in cui il zero simulato del sistema quantistica evolve durante l'operazione

L'esecuzione di un programma Quantum con Microsoft Quantum Development Kit in genere è costituita da due parti:
1. Il programma stesso, che viene implementato utilizzando il Q# linguaggio di programmazione Quantum, quindi viene richiamato per l'esecuzione in un computer Quantum o un simulatore Quantum. Sono costituiti da 
    - Q# operazioni: subroutine che agiscono sui registri Quantum e 
    - Q# funzioni: subroutine classiche usate nell'algoritmo Quantum.
2. Il punto di ingresso usato per chiamare il programma Quantum e specificare il computer di destinazione in cui deve essere eseguito.
    Questa operazione può essere eseguita direttamente dal prompt dei comandi o tramite un programma host scritto in un linguaggio di programmazione classico come Python o C#.
    Questa esercitazione include istruzioni per qualsiasi metodo preferito.

## <a name="allocate-qubits-and-define-quantum-operations"></a>Allocare qubits e definire operazioni Quantum

La prima parte di questa esercitazione consiste nel definire l' Q# operazione `Perform3qubitQFT` , che esegue la trasformazione Quantum Fourier su tre qubits. 

Inoltre, si userà la [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) funzione per osservare il modo in cui il zero simulato del nostro sistema qubit evolve nell'intera operazione.

Il primo passaggio consiste nel creare il Q# progetto e il file.
I passaggi per questa operazione dipendono dall'ambiente che verrà usato per chiamare il programma ed è possibile trovare i dettagli nelle rispettive [guide di installazione](xref:microsoft.quantum.install).

Verranno illustrati in dettaglio i componenti del file, ma il codice è disponibile anche come blocco completo di seguito.

### <a name="namespaces-to-access-other-no-locq-operations"></a>Spazi dei nomi per accedere ad altre Q# operazioni
All'interno del file viene innanzitutto definito lo spazio dei nomi al `NamespaceQFT` quale sarà possibile accedere dal compilatore.
Per fare in modo che l'operazione utilizzi le Q# operazioni esistenti, si aprono gli `Microsoft.Quantum.<>` spazi dei nomi pertinenti.

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    // operations go here
}
```

### <a name="define-operations-with-arguments-and-returns"></a>Definire operazioni con argomenti e restituzione
Definire quindi l' `Perform3qubitQFT` operazione:

```qsharp
    operation Perform3qubitQFT() : Unit {
        // do stuff
    }
```

Per il momento, l'operazione non accetta argomenti e non restituisce alcun elemento---in questo caso viene scritto che restituisce un `Unit` oggetto, che è simile a `void` in C# o a una tupla vuota, `Tuple[()]` , in Python.
In seguito verrà modificata per restituire una matrice di risultati di misurazione, a cui il punto `Unit` verrà sostituito da `Result[]` . 

### <a name="allocate-qubits-with-using"></a>Allocare qubits con `using`
All'interno dell' Q# operazione, viene innanzitutto allocato un registro di tre qubits con l' `using` istruzione:

```qsharp
        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

        }
```

Con `using` , i qubits vengono allocati automaticamente nello stato $ \ket {0} $. Per verificarlo [`Message(<string>)`](xref:microsoft.quantum.intrinsic.message) , è possibile usare e [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) , che stampano una stringa e lo stato corrente del sistema nella console.

> [!NOTE]
> Le `Message(<string>)` `DumpMachine()` funzioni e ( [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) rispettivamente da e) vengono [`Microsoft.Quantum.Diagnostics`](xref:microsoft.quantum.diagnostics) stampate direttamente nella console. Proprio come un calcolo quantistico reale, Q# non consente di accedere direttamente agli Stati qubit.
> Tuttavia, come `DumpMachine` stampa lo stato corrente del computer di destinazione, può fornire informazioni utili per il debug e l'apprendimento quando viene usato insieme al simulatore di stato completo.


### <a name="applying-single-qubit-and-controlled-gates"></a>Applicazione di controlli Single-qubit e controlli

Si applicano quindi le attività di controllo che comprendono l'operazione stessa.
Q# contiene già molti controlli Quantum di base come operazioni nello [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) spazio dei nomi e non si tratta di un'eccezione. 

All'interno Q# di un'operazione, le istruzioni che richiamabili saranno ovviamente eseguite in ordine sequenziale.
Il primo Gate da applicare è quindi [`H`](xref:microsoft.quantum.intrinsic.h) (Hadamard) alla prima qubit:

<br/>
<img src="../media/qft_firstH.PNG" alt="Circuit diagram for three qubit QFT through first Hadamard" width="120">

Per applicare un'operazione a un qubit specifico da un registro (ovvero un singolo `Qubit` da una matrice `Qubit[]` ) si usa la notazione di indice standard.
Quindi, l'applicazione [`H`](xref:microsoft.quantum.intrinsic.h) di al primo qubit del registro `qs` assume il formato seguente:

```qsharp
            H(qs[0]);
```

Oltre ad applicare il `H` Gate (Hadamard) a singoli qubits, il circuito QFT è costituito principalmente da [`R1`](xref:microsoft.quantum.intrinsic.r1) rotazioni controllate.
Un' `R1(θ, <qubit>)` operazione in generale lascia {0} invariato il componente $ \ket $ di qubit, applicando una rotazione di $e ^ {i\theta} $ al componente $ \ket {1} $.

#### <a name="controlled-operations"></a>Operazioni controllate

Q# rende estremamente semplice condizionare l'esecuzione di un'operazione su uno o più controlli qubits.
In generale, si limita a anteporre la chiamata a `Controlled` e gli argomenti dell'operazione cambiano come segue:

 `Op(<normal args>)` $ per $ `Controlled Op([<control qubits>], (<normal args>))` .

Si noti che il controllo qubits deve essere fornito come matrice, anche se si tratta di un singolo qubit.

Dopo la `H` , si noterà che i cancelli successivi sono le attività di `R1` controllo che agiscono sulla prima qubit (e controllate dal secondo/terzo):

<br/>
<img src="../media/qft_firstqubit.PNG" alt="Circuit diagram for three qubit QFT through first qubit" width="310">

Questi vengono chiamati con

```qsharp
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));
```

Si noti che viene usata la [`PI()`](xref:microsoft.quantum.math.pi) funzione dello [`Microsoft.Quantum.Math`](xref:microsoft.quantum.math) spazio dei nomi per definire le rotazioni in termini di pi greco radianti.
Si divide inoltre per un `Double` (ad esempio `2.0` ) perché la divisione per un numero intero `2` genera un errore di tipo. 

> [!TIP]
> `R1(π/2)` e `R1(π/4)` sono equivalenti alle `S` `T` operazioni e (anche in `Microsoft.Quantum.Intrinsic` ).


Dopo aver applicato le `H` operazioni pertinenti e le rotazioni controllate al secondo e al terzo qubits:

```qsharp
            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);
```

è necessario applicare un controllo solo [`SWAP`](xref:microsoft.quantum.intrinsic.swap) per completare il circuito:

```qsharp
            SWAP(qs[2], qs[0]);
```

Questa operazione è necessaria perché la natura della trasformazione Quantum Fourier restituisce l'qubits in ordine inverso, quindi gli scambi consentono una perfetta integrazione della subroutine in algoritmi di dimensioni maggiori.

Quindi, abbiamo terminato di scrivere le operazioni a livello di qubit della trasformazione Quantum Fourier nell' Q# operazione:

<img src="../media/qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

Tuttavia, non è possibile chiamarlo ancora un giorno.
I nostri qubits si trovavano nello stato $ \ket {0} $ quando sono stati allocati e, in modo analogo, in Q# questo caso, dobbiamo lasciarli invariati (o meglio!).

### <a name="deallocate-qubits"></a>Deallocare qubits

Viene chiamato [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) di nuovo per visualizzare lo stato di post-operazione e infine si applica [`ResetAll`](xref:microsoft.quantum.intrinsic.resetall) al registro qubit per reimpostare il qubits su $ \ket {0} $ prima di completare l'operazione:

```qsharp
            Message("After:");
            DumpMachine();

            ResetAll(qs);
```

Per richiedere che tutti i qubits deallocati siano impostati in modo esplicito su $ \ket {0} $, è una funzionalità di base di Q# , perché consente ad altre operazioni di conoscerne lo stato esattamente quando iniziano a usare gli stessi qubits (una risorsa limitata).
Inoltre, ciò garantisce che non siano presenti altri qubits nel sistema.
Se la reimpostazione non viene eseguita alla fine di un `using` blocco di allocazione, verrà generato un errore di Runtime.

Il Q# file completo dovrebbe essere simile al seguente:

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    operation Perform3qubitQFT() : Unit {

        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("After:");
            DumpMachine();

            ResetAll(qs);
        }
    }
}
```


Con il Q# file e l'operazione completa, il programma Quantum è pronto per essere chiamato e simulato.

## <a name="execute-the-program"></a>Eseguire il programma

Dopo aver definito l' Q# operazione in un `.qs` file, è ora necessario chiamare tale operazione e osservare i dati classici restituiti.
Per il momento, non viene restituito alcun elemento (tenere presente che l'operazione definita in precedenza restituisce `Unit` ), ma quando in seguito si modifica l' Q# operazione per restituire una matrice di risultati di misurazione (), si affronterà `Result[]` questo problema.

Sebbene il Q# programma sia onnipresente in tutti gli ambienti utilizzati per la chiamata, il modo in cui questa operazione sarà ovviamente variabile. Di conseguenza, è sufficiente seguire le istruzioni nella scheda corrispondente al programma di installazione: uso dell' Q# applicazione o uso di un programma host in Python o C#.

#### <a name="command-prompt"></a>[Prompt dei comandi](#tab/tabid-cmdline)

L'esecuzione del Q# programma dal prompt dei comandi richiede solo una piccola modifica al Q# file.

È sufficiente aggiungere `@EntryPoint()` a una riga che precede la definizione dell'operazione:

```qsharp
    @EntryPoint()
    operation Perform3qubitQFT() : Unit {
        // ...
```

Per eseguire il programma, aprire il terminale nella cartella del progetto e immettere

```dotnetcli
dotnet run
```

Al momento dell'esecuzione, gli `Message` output e `DumpMachine` indicati di seguito vengono visualizzati nella console.


#### <a name="python"></a>[Python](#tab/tabid-python)

Creare un file host Python: `host.py` .

Il file host viene creato nel modo seguente: 
1. In primo luogo, viene importato il `qsharp` modulo, che registra il caricatore del modulo per l' Q# interoperabilità. 
    In questo modo Q# gli spazi dei nomi (ad esempio `NamespaceQFT` , definiti nel Q# file) verranno visualizzati come moduli Python, da cui è possibile importare Q# le operazioni.
2. Importare quindi le Q# operazioni che vengono richiamate direttamente---in questo caso, `Perform3qubitQFT` .
    È necessario importare solo il punto di ingresso in un Q# programma (ad esempio, _non_ operazioni come `H` e `R1` , che vengono chiamate da altre Q# operazioni ma mai dall'host classico).
3. Per simulare Q# operazioni o funzioni, usare il modulo `<Q#callable>.simulate(<args>)` per eseguirle nel `QuantumSimulator()` computer di destinazione. 

> [!NOTE]
> Se volevamo chiamare l'operazione su un computer diverso, ad esempio, useremo `ResourceEstimator()` semplicemente `<Q#callable>.estimate_resources(<args>)` .
> In generale, le Q# operazioni sono indipendenti dai computer in cui vengono eseguite, ma alcune funzionalità come `DumpMachine` potrebbero comportarsi in modo diverso.

4. Quando si esegue la simulazione, la chiamata all'operazione restituirà i valori definiti nel Q# file.
    Per il momento non viene restituito alcun risultato, ma in un secondo momento verrà visualizzato un esempio di assegnazione ed elaborazione di questi valori.
    Con i dati risultanti in mano e completamente classici, possiamo eseguire qualsiasi operazione.

Il `host.py` file completo dovrebbe essere il seguente:

```python
import qsharp
from NamespaceQFT import Perform3qubitQFT

Perform3qubitQFT.simulate()
```

Eseguire il file Python e stamparlo nella console dovrebbero essere visualizzati gli `Message` output e `DumpMachine` seguenti. 


#### <a name="c"></a>[C#](#tab/tabid-csharp)

Seguendo le stesse istruzioni disponibili nella [Guida all'installazione](xref:microsoft.quantum.install.cs), creare un file host C# e rinominarlo in `host.cs` .

L'host C# è costituito da quattro parti:
1. Costruzione di un simulatore quantistico.
    Nel codice riportato di seguito si tratta della variabile `qsim` .
2. Calcolo degli argomenti necessari per l'algoritmo quantistico.
    Nessuno in questo esempio.
3. Esecuzione dell'algoritmo quantistico. 
    Ogni Q# operazione genera una classe C# con lo stesso nome. 
    Questa classe contiene un metodo `Run` che esegue l'operazione in modalità **asincrona**.
    L'esecuzione è asincrona perché l'esecuzione nell'hardware effettivo sarà asincrona. 
    Poiché il `Run` metodo è asincrono, viene chiamato il `Wait()` metodo. l'esecuzione viene bloccata fino al completamento dell'attività e il risultato viene restituito in modo sincrono. 
4. Elabora il risultato restituito dell'operazione.
    Per il momento, l'operazione non restituisce alcun risultato.


```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                Perform3QubitQFT.Run(qsim).Wait();
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}

```
Eseguire l'applicazione e l'output deve corrispondere a quello riportato di seguito.
Il programma verrà chiuso dopo aver premuto un tasto.
***

```Output
Initial state |000>:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
After:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
```

Quando viene chiamato sul simulatore di stato completo, `DumpMachine()` fornisce queste rappresentazioni mutliple del zero dello stato del quantum. Gli stati possibili di un sistema $n $-qubit possono essere rappresentati da uno o più Stati di base del calcolo di $2 ^ n $, ognuno con un coefficiente complesso corrispondente (semplicemente un'ampiezza e una fase).
Gli Stati di base di calcolo corrispondono a tutte le stringhe binarie possibili di lunghezza $n $---ovvero tutte le combinazioni possibili di qubit stati $ \ket {0} $ e $ \ket {1} $, dove ogni cifra binaria corrisponde a un singolo qubit.

La prima riga fornisce un commento con gli ID dei qubits corrispondenti nell'ordine significativo.
Qubit `2` è il "più significativo" significa semplicemente che nella rappresentazione binaria del vettore di stato base $ \ket{i} $ lo stato di qubit `2` corrisponde alla cifra più a sinistra. Ad esempio, $ \ket {6} = \ket {110} $ include qubits `2` e `1` both in $ \ket {1} $ e qubit `0` in $ \ket {0} $.


Il resto delle righe descrive l'ampiezza di probabilità della misurazione del vettore di stato di base $ \ket{i} $ nei formati cartesiani e polari.
In dettaglio per la prima riga dello stato di input $ \ket {000} $:
* **`|0>:`** Questa riga corrisponde allo `0` stato di base computazionale (dato che la post-allocazione dello stato iniziale era $ \ket {000} $, ci si aspetterebbe che questo sia l'unico stato con l'ampiezza della probabilità a questo punto).
* **`1.000000 +  0.000000 i`**: ampiezza della probabilità in formato cartesiano.
* **` == `**: il `equal` segno separa entrambe le rappresentazioni equivalenti.
* **`********************`**: Rappresentazione grafica della grandezza, il numero di `*` è proporzionale alla probabilità di misurare questo vettore di stato. 
* **`[ 1.000000 ]`**: valore numerico della grandezza
* **`    ---`**: Rappresentazione grafica della fase dell'ampiezza.
* **`[ 0.0000 rad ]`**: valore numerico della fase (in radianti).

Sia la grandezza che la fase vengono visualizzate con una rappresentazione grafica. La rappresentazione di magnitude è semplice: Mostra una barra di `*` e maggiore è la probabilità, maggiore sarà la barra. Per la fase, vedere [testing and Debugging: dump functions](xref:microsoft.quantum.guide.testingdebugging#dump-functions) per le possibili rappresentazioni dei simboli basate sugli intervalli di angoli.


Quindi, l'output stampato indica che i nostri cancelli programmati hanno trasformato lo stato da

$ $ \ket{\psi} \_ {Initial} = \ket {000} $ $

su 

$ $ \begin{align} \ket{\psi} \_ {Final} &= \frac {1} {\sqrt {8} } \left (\ket + {000} \ket {001} + \ket {010} + \ket {011} + \ket {100} + \ket {101} + \ket {110} + \ket {111} \right) \\ \\ &= \frac {1} {\sqrt{2 ^ n}} \sum \_ {j = 0} ^ {2 ^ n-1} \ket{j}, \end{align} $ $

Questo è esattamente il comportamento della trasformazione di Fourier qubit 3. 

Per informazioni sul modo in cui sono interessati gli altri Stati di input, si consiglia di provare a eseguire le operazioni di qubit prima della trasformazione.

## <a name="adding-measurements"></a>Aggiunta di misure

Sfortunatamente, una pietra miliare della meccanica quantistica indica che un sistema Quantum reale non può disporre di tale `DumpMachine` funzione. Al contrario, è necessario estrarre le informazioni attraverso le misurazioni, che in genere non solo forniscono lo stato quantum completo, ma possono anche modificare drasticamente il sistema stesso.
Ci sono molti tipi di misurazioni Quantum, ma ci si concentrerà sulla più elementare: misurazioni proiezioni su un singolo qubits.
Una volta eseguita la misurazione in base a una determinata base (ad esempio, la base di calcolo $ \{ \ket {0} , \ket {1} \} $), lo stato qubit viene proiettato sullo stato di base misurato---quindi eliminando eventuali superposizioni tra i due.

Per implementare le misurazioni in un Q# programma, viene usata l' `M` operazione (from `Microsoft.Quantum.Intrinsic` ), che restituisce un `Result` tipo.

In primo luogo, l' `Perform3QubitQFT` operazione viene modificata per restituire una matrice di risultati di misurazione, `Result[]` , anziché `Unit` .

```qsharp
    operation Perform3QubitQFT() : Result[] {
```

#### <a name="define-and-initialize-result-array"></a>Definire e inizializzare la `Result[]` matrice

Prima di allocare anche qubits, ad esempio prima dell' `using` istruzione, viene dichiarata e associata la matrice di lunghezza 3 (una `Result` per ogni qubit): 

```qsharp
        mutable resultArray = new Result[3];
```

La `mutable` parola chiave prefacing `resultArray` consente la riassociazione della variabile in un secondo momento nel codice---ad esempio quando si aggiungono i risultati della misurazione.

#### <a name="perform-measurements-in-a-for-loop-and-add-results-to-array"></a>Eseguire misure in un `for` ciclo e aggiungere risultati alla matrice

Dopo le operazioni di trasformazione di Fourier all'interno del `using` blocco, inserire il codice seguente:

```qsharp
            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }
```
La [`IndexRange`](xref:microsoft.quantum.arrays.indexrange) funzione chiamata su una matrice, ad esempio la matrice di qubits, `qs` restituisce un intervallo sugli indici della matrice. In questo esempio viene usato nel `for` ciclo per misurare in modo sequenziale ogni qubit usando l' `M(qs[i])` istruzione.
Ogni tipo misurato `Result` ( `Zero` o `One` ) viene quindi aggiunto alla posizione di indice corrispondente in `resultArray` con un'istruzione Update-and-reassign.

> [!NOTE]
> La sintassi di questa istruzione è univoca per Q# , ma corrisponde alla riassegnazione della variabile simile `resultArray[i] <- M(qs[i])` visualizzata in altri linguaggi, ad esempio F # e R.

La parola chiave `set` viene sempre utilizzata per riassegnare le variabili associato utilizzando `mutable` .

#### <a name="return-resultarray"></a>Ritorno `resultArray`

Con le tre qubits misurate e i risultati aggiunti a `resultArray` , è possibile reimpostare e deallocare il qubits come prima.
Dopo la `using` chiusura del blocco, inserire

```qsharp
        return resultArray;
```
per restituire in definitiva l'output dell'operazione. 

### <a name="understanding-the-effects-of-measurement"></a>Informazioni sugli effetti della misurazione

Modificare la posizione delle `DumpMachine` funzioni in modo da restituire lo stato prima e dopo le misurazioni.
Il codice dell'operazione finale dovrebbe essere simile al seguente: 

```qsharp
    operation Perform3QubitQFT() : Result[] {

        mutable resultArray = new Result[3];

        using (qs = Qubit[3]) {

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("Before measurement: ");
            DumpMachine();

            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }

            Message("After measurement: ");
            DumpMachine();

            ResetAll(qs);
        }
        return resultArray;
    }
}
```

Se si utilizza il prompt dei comandi, la matrice restituita verrà semplicemente stampata direttamente nella console alla fine dell'esecuzione.
In caso contrario, aggiornare il programma host per elaborare la matrice restituita.

#### <a name="command-prompt"></a>[Prompt dei comandi](#tab/tabid-cmdline)

Per comprendere meglio la matrice restituita che verrà stampata nella console, è possibile aggiungere un'altra `Message` nel Q# file immediatamente prima dell' `return` istruzione:

```qsharp
        Message("Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
        return resultArray;
```

Eseguire il progetto. l'output dovrebbe essere simile al seguente:

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]
```

#### <a name="python"></a>[Python](#tab/tabid-python)

Aggiornare il programma Python a quanto segue:

```python
import qsharp
from NamespaceQFT import Perform3QubitQFT

measurementResult = Perform3QubitQFT.simulate()
print("\n")
print("Measured post-QFT state: [qubit0, qubit1, qubit2]")
print(measurementResult)

# reversing order to show corresponding basis state in binary form
binaryCompBasisState = ""
for i in measurementResult:
    binaryCompBasisState = str(i) + binaryCompBasisState
print("Corresponding basis state in binary:")
print("|" + binaryCompBasisState + ">")
```

Eseguire il file. l'output dovrebbe essere simile al seguente:

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[1, 1, 0]

Corresponding basis state in binary:
|011>
```

#### <a name="c"></a>[C#](#tab/tabid-csharp)

Ora che l'operazione sta restituendo un risultato, sostituire la chiamata al metodo `Wait()` con il recupero della `Result` Proprietà. Viene comunque eseguita la stessa sincronicità descritta in precedenza ed è possibile associare direttamente questo valore alla variabile `measurementResult` .

```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                var measurementResult = Perform3QubitQFT.Run(qsim).Result;
                System.Console.WriteLine(
                    $"Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
                System.Console.WriteLine(
                    measurementResult);

                // reversing order to show corresponding basis state in binary form
                string binaryCompBasisState = String.Empty;

                foreach (Result i in measurementResult)
                {
                    string iString = i.ToString();
                    binaryCompBasisState = iString + binaryCompBasisState;
                }
                binaryCompBasisState = "|" + binaryCompBasisState + ">";
                System.Console.WriteLine(
                    $"Corresponding basis state in binary:");
                System.Console.WriteLine(
                    binaryCompBasisState);
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}
```

Eseguire il progetto. l'output dovrebbe essere simile al seguente:

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]

Corresponding basis state in binary:
|ZeroOneOne>

Press any key to continue...
```
***

Questo output illustra alcuni aspetti diversi:
1. Se si confronta il risultato restituito con la pre-misurazione `DumpMachine` , è evidente che _non_ viene illustrata la sovrapposizione post-QFT rispetto agli Stati di base.
    Una misura restituisce solo uno stato di base, con una probabilità determinata dall'ampiezza di tale stato nel zero del sistema.
2. Dal post-misurazione `DumpMachine` si noterà che la misurazione _modifica_ lo stato stesso, proiettando l'oggetto dalla superposizione iniziale sugli stati di base allo stato di base singolo che corrisponde al valore misurato.

Se dovessimo ripetere questa operazione più volte, le statistiche dei risultati iniziano a illustrare la superposizione ponderata uguale dello stato post-QFT che consente di ottenere un risultato casuale in ogni scatto.
_Tuttavia_, oltre a essere inefficienti e comunque imperfetti, questo produce comunque solo le ampiezze relative degli Stati di base, non le fasi relative tra di esse.
Quest'ultimo non è un problema in questo esempio, ma le fasi relative vengono visualizzate se si specifica un input più complesso per il QFT di $ \ket {000} $.

#### <a name="partial-measurements"></a>Misurazioni parziali 
Per esplorare il modo in cui la misurazione di un solo qubits del registro può influire sullo stato del sistema, provare ad aggiungere quanto segue all'interno del `for` ciclo, dopo la riga di misurazione:
```qsharp
                let iString = IntAsString(i);
                Message("After measurement of qubit " + iString + ":");
                DumpMachine();
```

Si noti che per accedere alla `IntAsString` funzione sarà necessario aggiungere 
```qsharp
    open Microsoft.Quantum.Convert;
```
con il resto delle istruzioni dello spazio dei nomi `open` .

Nell'output risultante verrà visualizzata la proiezione graduale negli spazi subspazi quando ogni qubit viene misurato.


## <a name="use-the-no-locq-libraries"></a>Usare le Q# librerie
Come indicato nell'introduzione, gran parte del Q# suo potere si basa sul fatto che consente di astrarre le preoccupazioni legate alla gestione dei singoli qubits.
Se invece si vuole sviluppare programmi Quantum applicabili a scalabilità completa, è preferibile sapere se un' `H` operazione viene eseguita prima o dopo una particolare rotazione rallenterà il problema. 

Le Q# librerie contengono l'operazione [QFT](xref:microsoft.quantum.canon.qft) , che è possibile eseguire e applicare solo per un numero qualsiasi di qubits.
Per fare un tentativo, definire una nuova operazione nel Q# file con lo stesso contenuto di `Perform3QubitQFT` , ma con tutti gli elementi dal primo `H` al `SWAP` sostituito da due semplici righe:
```qsharp
            let register = BigEndian(qs);    //from Microsoft.Quantum.Arithmetic
            QFT(register);                   //from Microsoft.Quantum.Canon
```
La prima riga crea semplicemente un' [`BigEndian`](xref:microsoft.quantum.arithmetic.bigendian) espressione della matrice allocata di qubits, `qs` , che è l'elemento che l'operazione [QFT](xref:microsoft.quantum.canon.qft) accetta come argomento.
Corrisponde all'ordinamento dell'indice di qubits nel registro.

Per accedere a queste operazioni, aggiungere `open` istruzioni per i rispettivi spazi dei nomi all'inizio del Q# file:
```qsharp
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Arithmetic;
```

Modificare ora il programma host in modo da chiamare il nome della nuova operazione (ad esempio `PerformIntrinsicQFT` ) e conferire un vortice.

Per visualizzare i reali vantaggi derivanti dall'utilizzo delle Q# operazioni della libreria, modificare il numero di qubits in un valore diverso da `3` :
```qsharp
        mutable resultArray = new Result[4]; 

        using (qs = Qubit[4]) {
            //...
        }
```
È quindi possibile applicare il QFT appropriato per un determinato numero di qubits, senza doversi preoccupare del pasticcio di nuove `H` operazioni e rotazioni in ogni qubit.

Si noti che il simulatore Quantum impiega più tempo per l'esecuzione quando si aumenta il numero di qubits---precisamente il motivo per cui si cerca l'hardware Quantum reale.













