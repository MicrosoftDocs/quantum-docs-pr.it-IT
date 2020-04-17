---
title: Introduzione al calcolo quantistico con Q#
description: Informazioni su come scrivere un programma quantistico in Q#. Sviluppare un'applicazione Stato di Bell usando Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 10/07/2019
ms.topic: tutorial
uid: microsoft.quantum.write-program
ms.openlocfilehash: 8d3b2d7c8da39a961f4eedcc5989ad3a1e134ade
ms.sourcegitcommit: 7d350db4b5e766cd243633aee7d0a839b6274bd6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "77906730"
---
# <a name="quantum-basics-with-q"></a>Introduzione al calcolo quantistico con Q#

Questa esercitazione dell'avvio rapido illustra come scrivere un programma Q# che modifica e misura i qubit e mostra gli effetti della sovrapposizione e dell'entanglement.  Questa guida illustra l'installazione del QDK, la compilazione del programma e l'esecuzione del programma in un simulatore quantistico.  

Verrà scritta un'applicazione denominata Bell per illustrare l'entanglement quantistico.  Il nome Bell fa riferimento agli stati di Bell, che sono stati quantistici specifici di due qubit che vengono usati per rappresentare gli esempi più semplici di sovrapposizione e di entanglement quantistico. 

## <a name="pre-requisites"></a>Prerequisiti

Se si è pronti per iniziare a scrivere codice, seguire questa procedura prima di procedere: 

* [Installare](xref:microsoft.quantum.install) Quantum Development Kit usando il linguaggio di programmazione e l'ambiente di sviluppo preferiti.
* Se il QDK è già installato, assicurarsi di aver eseguito l'[aggiornamento](xref:microsoft.quantum.update) alla versione più recente

È anche possibile seguire l'esercitazione senza installare il QDK e ottenere una panoramica del linguaggio di programmazione Q# e dei concetti di base del calcolo quantistico.

## <a name="demonstrating-qubit-behavior-with-q"></a>Dimostrazione del comportamento dei qubit con Q#

Ricordare la semplice [definizione di un qubit](xref:microsoft.quantum.overview.what#the-qubit).  Mentre i bit classici contengono un singolo valore binario come 0 o 1, lo stato di un qubit può essere una **sovrapposizione** di 0 e 1 contemporaneamente.  Concettualmente, un qubit può essere considerato come una direzione nello spazio (nota anche come vettore).  Un qubit può trovarsi in una qualsiasi delle direzioni possibili. I due **stati classici** sono le due direzioni, che rappresentano la probabilità del 100% di misurare 0 e del 100% di misurare 1.  Questa rappresentazione è anche visualizzata in modo più formale dalla [sfera di Bloch](/quantum/concepts/the-qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).


L'azione di misurazione genera un risultato binario e modifica lo stato del qubit. La misurazione genera un valore binario, ovvero 0 o 1.  Il qubit passa dall'essere in sovrapposizione (qualsiasi direzione) a uno degli stati classici.  Successivamente, la ripetizione della stessa misurazione senza alcuna operazione genera lo stesso risultato binario.  

Più qubit possono anche trovarsi in uno stato di **entanglement**. Quando si esegue la misurazione di un qubit con entanglement, vengono aggiornate anche le informazioni sullo stato degli altri qubit.

A questo punto è possibile dimostrare in che modo Q# esprime questo comportamento.  Si inizierà con il programma più semplice possibile e lo si svilupperà per mostrare la sovrapposizione quantistica e l'entanglement quantistico.

## <a name="setup"></a>Configurazione

Le applicazioni sviluppate con Quantum Development Kit di Microsoft sono costituite da due parti:

1. Uno o più algoritmi quantistici, implementati usando il linguaggio di programmazione quantistico Q#.
1. Un programma host, implementato in un linguaggio di programmazione come Python o C# o che funge da punto di ingresso principale e richiama le operazioni Q# per eseguire un algoritmo quantistico.

#### <a name="python"></a>[Python](#tab/tabid-python)

1. Scegliere una posizione per l'applicazione

1. Creare un file denominato `Bell.qs`. Questo file conterrà il codice Q#.

1. Creare un file denominato `host.py`. Questo file conterrà il codice host Python.

#### <a name="c-command-line"></a>[Riga di comando C#](#tab/tabid-csharp)

1. Creare un nuovo progetto Q#:

    ```bash
    dotnet new console -lang Q# --output Bell
    cd Bell
    ```

    Verrà visualizzato un file `.csproj`, un file Q# denominato `Operations.qs` e un file di programma host denominato `Driver.cs`

1. Rinominare il file Q#

    ```bash
    mv Operation.qs Bell.qs
    ```

#### <a name="visual-studio"></a>[Visual Studio](#tab/tabid-vs2019)

1. Creare un nuovo progetto

   * Aprire Visual Studio.
   * Scegliere **Nuovo** -> **Progetto...** dal menu **File**
   * In Esplora risorse di Modello di progetto digitare `Q#` nel campo di ricerca e selezionare il modello `Q# Application`
   * Assegnare il nome `Bell` al progetto

1. Rinominare il file Q#

   * Passare a **Esplora soluzioni**
   * Fare clic con il pulsante destro sul file `Operations.qs`
   * Rinominarlo in `Bell.qs`

* * *

## <a name="write-a-q-operation"></a>Scrivere un'operazione Q#

L'obiettivo prevede la preparazione di due qubit in uno stato quantico specifico, per dimostrare come operare sui qubit con Q# per modificarne lo stato e mostrare gli effetti della sovrapposizione e dell'entanglement. Si procederà un pezzo alla volta per dimostrare gli stati dei qubit, le operazioni e la misura.

**Panoramica:**  Nel primo codice riportato di seguito viene illustrato come usare i qubit in Q#.  Verranno illustrate due operazioni, `M` e `X`, che trasformano lo stato di un qubit. 

In questo frammento di codice viene definita un'operazione `Set` che accetta come parametro un qubit e un altro parametro, `desired`, che rappresenta lo stato in cui deve trovarsi il qubit.  L'operazione `Set` esegue una misura del qubit tramite l'operazione `M`.  In Q# una misura di qubit restituisce sempre `Zero` o `One`.  Se la misura restituisce un valore diverso da quello desiderato, "inverte" il qubit, ovvero, esegue un'operazione `X`, che modifica lo stato del qubit in un nuovo stato in cui le probabilità di una misura che restituisce `Zero` e `One` sono invertite.  Per illustrare l'effetto dell'operazione `Set`, viene quindi aggiunta un'operazione `TestBellState`.  Questa operazione accetta come input `Zero` o `One`, chiama l'operazione `Set` un determinato numero di volte con tale input e conta il numero di volte in cui la misura del qubit ha restituito `Zero` e il numero di volte in cui ha restituito `One`. Naturalmente, in questa prima simulazione dell'operazione `TestBellState`, si prevede che l'output mostri che tutte le misure del qubit impostato con `Zero` come input del parametro restituiranno `Zero` e tutte le misure di un qubit impostato con `One` come input del parametro restituiranno `One`.  Successivamente, verrà aggiunto il codice a `TestBellState` per dimostrare la sovrapposizione e l'entanglement.


### <a name="q-operation-code"></a>Codice dell'operazione Q#

1. Sostituire il contenuto del file Bell.qs con il codice seguente:

    ```qsharp
    namespace Quantum.Bell {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation Set(desired : Result, q1 : Qubit) : Unit {
            if (desired != M(q1)) {
                X(q1);
            }
        }
    }
    ```

    Questa operazione può ora essere chiamata per impostare un qubit su uno stato classico, restituendo `Zero` il 100% delle volte o restituendo `One` il 100% delle volte.  `Zero` e `One` sono costanti che rappresentano gli unici due risultati possibili della misura di un qubit.

    L'operazione `Set` misura il qubit.
    Se il qubit si trova nello stato desiderato, `Set` lo lascia invariato. In caso contrario, esegue l'operazione `X` che modifica lo stato del qubit impostandolo sullo stato desiderato.

### <a name="about-q-operations"></a>Informazioni sulle operazioni Q#

Un'operazione Q# è una subroutine quantistica, vale a dire una routine chiamabile che contiene operazioni quantistiche.

Gli argomenti di un'operazione vengono specificati come tuple, racchiuse tra parentesi.

Il tipo restituito dell'operazione viene specificato dopo i due punti. In questo caso, l'operazione `Set` non restituisce alcun risultato, quindi viene contrassegnata come se avesse restituito `Unit`. Si tratta dell'equivalente Q# di `unit` in F#, che è approssimativamente analogo a `void`in C# e a una tupla vuota (`Tuple[()]`) in Python.

Nella prima operazione Q# sono state usate due operazioni quantistiche:

* L'operazione [M](xref:microsoft.quantum.intrinsic.m), che misura lo stato del qubit
* L'operazione [X](xref:microsoft.quantum.intrinsic.x), che inverte lo stato del qubit

Un'operazione quantistica trasforma lo stato di un qubit. In alcuni casi si parla di gate quantistici anziché di operazioni, per analogia con i gate logici classici. Questo risale alle fasi iniziali del calcolo quantistico quando gli algoritmi erano semplicemente un costrutto teorico e venivano visualizzati come diagrammi in modo analogo ai diagrammi di circuito nell'informatica classica.

### <a name="add-q-test-code"></a>Aggiungere codice di test Q#

1. Aggiungere l'operazione seguente al file `Bell.qs`, all'interno dello spazio dei nomi, dopo la fine dell'operazione `Set`:

    ```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                Set(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            Set(Zero, qubit);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
    ```

    Questa operazione (`TestBellState`) verrà ripetuta ciclicamente per `count` iterazioni, imposterà un valore `initial` specificato in un qubit e quindi misurerà (`M`) il risultato. Raccoglierà le statistiche sul numero di zeri e di uno misurati e li restituirà al chiamante. Esegue inoltre un'altra operazione necessaria. Reimposta il qubit su uno stato noto (`Zero`) prima di restituirlo, per consentire ad altri di allocare questo qubit in uno stato noto. Questo passaggio è richiesto dall'istruzione `using`.

### <a name="about-variables-in-q"></a>Informazioni sulle variabili in Q#

Per impostazione predefinita, le variabili in Q# sono non modificabili e non è quindi possibile modificarne il valore dopo che sono state associate. Viene usata la parola chiave `let` per indicare l'associazione di una variabile non modificabile. Gli argomenti dell'operazione sono sempre non modificabili.

Se occorre una variabile il cui valore può essere modificato, ad esempio `numOnes` nell'esempio, è possibile dichiarare la variabile con la parola chiave `mutable`. È possibile modificare il valore di una variabile modificabile usando un'istruzione `set`.

In entrambi i casi, il tipo di una variabile viene dedotto dal compilatore. Q# non richiede alcuna annotazione di tipo per le variabili.

### <a name="about-using-statements-in-q"></a>Informazioni sulle istruzioni `using` in Q#

L'istruzione `using` rappresenta un'istruzione speciale per Q#. Viene usata per allocare i qubit per l'uso in un blocco di codice. In Q# tutti i qubit vengono allocati e rilasciati in modo dinamico, anziché essere risorse fisse per l'intera durata di un algoritmo complesso. Un'istruzione `using` alloca un set di qubit all'inizio e rilascia tali qubit alla fine del blocco.

## <a name="create-the-host-application-code"></a>Creare il codice dell'applicazione host

#### <a name="python"></a>[Python](#tab/tabid-python)

1. Aprire il file `host.py` e aggiungere il codice seguente:

    ```python
    import qsharp

    from qsharp import Result
    from Quantum.Bell import TestBellState

    initials = (Result.Zero, Result.One)

    for i in initials:
      res = TestBellState.simulate(count=1000, initial=i)
      (num_zeros, num_ones) = res
      print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4}')
    ```

#### <a name="c"></a>[C#](#tab/tabid-csharp)

1. Sostituire il contenuto del file `Driver.cs` con il codice seguente:

    ```csharp
    using System;

    using Microsoft.Quantum.Simulation.Core;
    using Microsoft.Quantum.Simulation.Simulators;

    namespace Quantum.Bell
    {
        class Driver
        {
            static void Main(string[] args)
            {
                using (var qsim = new QuantumSimulator())
                {
                    // Try initial values
                    Result[] initials = new Result[] { Result.Zero, Result.One };
                    foreach (Result initial in initials)
                    {
                        var res = TestBellState.Run(qsim, 1000, initial).Result;
                        var (numZeros, numOnes) = res;
                        System.Console.WriteLine(
                            $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4}");
                    }
                }

                System.Console.WriteLine("Press any key to continue...");
                Console.ReadKey();
            }
        }
    }
    ```

#### [](#tab/tabid-vs2019)

* * *

### <a name="about-the-host-application-code"></a>Informazioni sul codice dell'applicazione host

#### <a name="python"></a>[Python](#tab/tabid-python)

L'applicazione host Python è costituita da tre parti:

* Calcolo degli argomenti necessari per l'algoritmo quantistico. Nell'esempio `count` è impostato su 1000 e `initial` è il valore iniziale del qubit.
* Esecuzione dell'algoritmo quantistico tramite la chiamata al metodo `simulate()` dell'operazione Q# importata.
* Elaborazione del risultato dell'operazione. Nell'esempio `res` riceve il risultato dell'operazione. In questo caso, il risultato è una tupla del numero di zeri (`num_zeros`) e del numero di uno (`num_ones`) misurati dal simulatore. La tupla viene decostruita per ottenere i due campi e vengono stampati i risultati.

#### <a name="c"></a>[C#](#tab/tabid-csharp)

L'applicazione host C# è costituita da quattro parti:

* Costruzione di un simulatore quantistico. Nell'esempio `qsim` è il simulatore.
* Calcolo degli argomenti necessari per l'algoritmo quantistico. Nell'esempio `count` è impostato su 1000 e `initial` è il valore iniziale del qubit.
* Esecuzione dell'algoritmo quantistico. Ogni operazione Q# genera una classe C# con lo stesso nome. Questa classe contiene un metodo `Run` che esegue l'operazione in modalità **asincrona**. L'esecuzione è asincrona perché l'esecuzione nell'hardware effettivo sarà asincrona. Poiché il metodo `Run` è asincrono, viene recuperata la proprietà `Result`. L'esecuzione rimarrà così bloccata fino a quanto l'attività non viene completata e non viene restituito il risultato in modo sincrono.
* Elaborazione del risultato dell'operazione. Nell'esempio `res` riceve il risultato dell'operazione. In questo caso, il risultato è una tupla del numero di zeri (`numZeros`) e del numero di uno (`numOnes`) misurati dal simulatore. In C# questo risultato viene restituito come ValueTuple. La tupla viene decostruita per ottenere i due campi, vengono stampati i risultati e si attende la pressione di un tasto.

#### [](#tab/tabid-vs2019)

* * *

## <a name="build-and-run"></a>Compilazione ed esecuzione

#### <a name="python"></a>[Python](#tab/tabid-python)

1. Eseguire il comando seguente nel terminale:

    ```
    python host.py
    ```

    Questo comando esegue l'applicazione host, che simula l'operazione Q#.

Il risultato sarà:

```Output
Init:0    0s=1000 1s=0   
Init:1    0s=0    1s=1000
```

#### <a name="command-line--visual-studio-code"></a>[Riga di comando/Visual Studio Code](#tab/tabid-csharp)

1. Eseguire il comando seguente nel terminale:

    ```bash
    dotnet run
    ```

    Questo comando scarica automaticamente tutti i pacchetti necessari, compila l'applicazione e quindi la esegue dalla riga di comando.

1. In alternativa, premere **F1** per aprire il riquadro comandi e selezionare **Debug: Avvia senza eseguire debug.**
Potrebbe essere richiesto di creare un nuovo file ``launch.json`` che descrive come avviare il programma.
Il file ``launch.json`` predefinito funziona in genere correttamente per la maggior parte delle applicazioni.

Il risultato sarà:

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

#### <a name="visual-studio"></a>[Visual Studio](#tab/tabid-vs2019)

1. È sufficiente premere `F5` per avviare ed eseguire il programma.

Il risultato sarà:

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

Il programma verrà chiuso dopo aver premuto un tasto.

* * *

## <a name="prepare-superposition"></a>Preparare la sovrapposizione

**Panoramica**: a questo punto verranno esaminate le modalità di espressione di Q# per posizionare i qubit in sovrapposizione.  Tenere presente che lo stato di un qubit può essere in una sovrapposizione di 0 e 1.  A tale scopo, verrà usata l'operazione `Hadamard`. Se il qubit è in uno degli stati classici (in cui una misura restituisce sempre `Zero` o sempre `One`), l'operazione `Hadamard` o `H` imposterà il qubit su uno stato in cui una misura del qubit restituirà `Zero` il 50% delle volte e `One` il 50% delle volte.  A livello concettuale, il qubit può essere considerato a metà tra `Zero` e `One`.  Ora, quando si simula l'operazione `TestBellState`, si osserverà che i risultati restituiranno approssimativamente un numero uguale di `Zero` e `One` dopo la misura.  

In primo luogo, si tenterà semplicemente di invertire il qubit (se il qubit si trova nello stato `Zero` passerà a `One` e viceversa). A tale scopo, si esegue un'operazione `X` prima di misurarlo in `TestBellState`:

```qsharp
X(qubit);
let res = M(qubit);
```

I risultati (dopo aver premuto `F5`) sono ora invertiti:

```Output
Init:Zero 0s=0    1s=1000
Init:One  0s=1000 1s=0
```

Tuttavia, quanto osservato finora è un'operazione classica. Ora verrà generato un risultato quantistico. È sufficiente sostituire l'operazione `X` nell'esecuzione precedente con un'operazione `H` o un'operazione di Hadamard. Anziché invertire il qubit da 0 a 1, verrà solo invertito a metà. Le righe sostituite in `TestBellState` ora hanno un aspetto simile al seguente:

```qsharp
H(qubit);
let res = M(qubit);
```

A questo punto, il risultato diventa più interessante:

```Output
Init:Zero 0s=484  1s=516
Init:One  0s=522  1s=478
```

Ogni volta che si esegue una misura, viene richiesto un valore classico, ma il qubit si trova a metà tra 0 e 1, quindi si ottiene (statisticamente) 0 per metà delle volte e 1 per metà delle volte. Questa operazione è nota come __sovrapposizione__ e offre la prima osservazione reale dello stato quantistico.

## <a name="prepare-entanglement"></a>Preparare l'entanglement

**Panoramica:**  a questo punto, osserviamo come Q# esprime i modi per eseguire l'entanglement dei qubit.  In primo luogo, si imposta il primo qubit sullo stato iniziale e quindi si usa l'operazione `H` per posizionarlo in sovrapposizione.  Quindi, prima di misurare il primo qubit, viene usata una nuova operazione (`CNOT`), che sta per Controlled-Not.  Il risultato dell'esecuzione di questa operazione su due qubit è l'inversione del secondo qubit se il primo qubit è `One`.  A questo punto, i due qubit sono correlati (in entanglement).  Le statistiche per il primo qubit sono rimaste invariate (probabilità 50-50 di `Zero` o `One`), ma ora quando viene misurato il secondo qubit, è __sempre__ uguale a quanto misurato per il primo qubit. Il gate `CNOT` ha eseguito l'entanglement dei due qubit, così qualsiasi cosa accade a uno di essi, accade anche all'altro. Se sono state invertite le misure, ovvero se è stato misurato il secondo qubit prima del primo, si verificherà lo stesso risultato. La prima misura sarà casuale e la seconda si troverà nel passaggio del blocco con quanto individuato per la prima.

Per prima cosa è necessario allocare 2 qubit invece di uno in `TestBellState`:

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

Questo consentirà di aggiungere una nuova operazione (`CNOT`) prima di misurare (`M`) in `TestBellState`:

```qsharp
Set(initial, q0);
Set(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

È stata aggiunta un'altra operazione `Set` per inizializzare il primo qubit per assicurarsi che sia sempre nello stato `Zero` quando si inizia.

È anche necessario reimpostare il secondo qubit prima di rilasciarlo.

```qsharp
Set(Zero, q0);
Set(Zero, q1);
```

La routine completa ha ora un aspetto simile al seguente:

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set (initial, q0);
                Set (Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
```

Se viene eseguita,si otterrà esattamente lo stesso risultato 50-50 ottenuto in precedenza. Tuttavia, l'aspetto interessante è il modo in cui il secondo qubit reagisce alla prima misurazione. Questa statistica verrà aggiunta con una nuova versione dell'operazione `TestBellState`:

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int, Int) {
        mutable numOnes = 0;
        mutable agree = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set(initial, q0);
                Set(Zero, q1);

                H(q0);
                CNOT(q0, q1);
                let res = M(q0);

                if (M(q1) == res) {
                    set agree += 1;
                }

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes, agree);
    }
```

Il nuovo valore restituito (`agree`) tiene traccia di ogni volta che la misurazione del primo qubit corrisponde alla misurazione del secondo qubit. È anche necessario aggiornare l'applicazione host di conseguenza:

#### <a name="python"></a>[Python](#tab/tabid-python)

```python
import qsharp

from qsharp import Result
from Quantum.Bell import TestBellState

initials = {Result.Zero, Result.One} 

for i in initials:
    res = TestBellState.simulate(count=1000, initial=i)
    (num_zeros, num_ones, agree) = res
    print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4} agree={agree: <4}')
```

#### <a name="c"></a>[C#](#tab/tabid-csharp)

```csharp
            using (var qsim = new QuantumSimulator())
            {
                // Try initial values
                Result[] initials = new Result[] { Result.Zero, Result.One };
                foreach (Result initial in initials)
                {
                    var res = TestBellState.Run(qsim, 1000, initial).Result;
                    var (numZeros, numOnes, agree) = res;
                    System.Console.WriteLine(
                        $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4} agree={agree,-4}");
                }
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
```

#### [](#tab/tabid-vs2019)

* * *

A questo punto, quando viene eseguita, si ottiene un risultato sorprendente:

```Output
Init:Zero 0s=499  1s=501  agree=1000
Init:One  0s=490  1s=510  agree=1000
```

Come dichiarato nella panoramica, le statistiche per il primo qubit sono rimaste invariate (probabilità 50-50 di uno 0 o 1), ma ora quando viene misurato il secondo qubit, è __sempre__ uguale a quanto misurato per il primo qubit perché sono correlati (in entanglement).

Congratulazioni, è stata completata la scrittura del primo programma quantistico.

## <a name="whats-next"></a>Quali sono le operazioni successive?

L'esercitazione dell'avvio rapido sulla [Ricerca di Grover](xref:microsoft.quantum.quickstarts.search) mostra come creare ed eseguire la ricerca di Grover, uno degli algoritmi di calcolo quantistico più diffusi, e offre un esempio interessante di un programma Q# che può essere usato per risolvere problemi reali con il calcolo quantistico.  

[Introduzione a Quantum Development Kit](xref:microsoft.quantum.welcome) consiglia altri modi per imparare a usare Q# e la programmazione quantistica.

