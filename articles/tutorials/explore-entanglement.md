---
title: Esplora l'intreccio con Q#
description: Informazioni su come scrivere un programma Quantum in Q# . Sviluppare un'applicazione Stato di Bell usando Quantum Development Kit (QDK)
author: geduardo
ms.author: v-edsanc
ms.date: 05/29/2020
ms.topic: tutorial
uid: microsoft.quantum.write-program
no-loc:
- Q#
- $$v
ms.openlocfilehash: ac9c060c157ba5ee3bc66852c42298ac8adcb3b3
ms.sourcegitcommit: 685a8ab16d7e6a25e63a168d6e7c385fa6e876cc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2020
ms.locfileid: "91492337"
---
# <a name="tutorial-explore-entanglement-with-q"></a>Esercitazione: Esplorare l'entanglement con Q#\#

Questa esercitazione illustra come scrivere un Q# programma che manipola e misura qubits e illustra gli effetti della superposizione e del groviglio.

Verrà scritta un'applicazione denominata Bell per illustrare l'entanglement quantistico.
Il nome Bell fa riferimento agli stati di Bell, che sono stati quantistici specifici di due qubit che vengono usati per rappresentare gli esempi più semplici di sovrapposizione e di entanglement quantistico.

## <a name="pre-requisites"></a>Prerequisiti

Se si è pronti per iniziare a scrivere codice, seguire questa procedura prima di procedere: 

* [Installare](xref:microsoft.quantum.install) Quantum Development Kit usando il linguaggio e l'ambiente di sviluppo preferiti.
* Se il QDK è già installato, assicurarsi di aver eseguito l'[aggiornamento](xref:microsoft.quantum.update) alla versione più recente

È anche possibile seguire la descrizione senza installare QDK, esaminando le panoramiche del Q# linguaggio di programmazione e i primi concetti di quantum computing.

## <a name="in-this-tutorial-youll-learn-how-to"></a>In questa esercitazione si apprenderà come:

> [!div class="checklist"]
> * Creare e combinare operazioni in Q\#
> * Consente di creare operazioni per inserire qubits nella superposizione, impigliarli e misurarli.
> * Dimostrare l'intrico di Quantum con un Q# programma eseguito in un simulatore. 

## <a name="demonstrating-qubit-behavior-with-the-qdk"></a>Dimostrazione del comportamento di qubit con QDK

Mentre i bit classici contengono un singolo valore binario come 0 o 1, lo stato di un [qubit](xref:microsoft.quantum.glossary#qubit) può essere una **sovrapposizione** di 0 e 1.  A livello concettuale, lo stato di un qubit può essere considerato come una direzione in uno spazio astratto (noto anche come vettore).  Uno stato qubit può essere in una delle direzioni possibili. I due **stati classici** sono le due direzioni, che rappresentano la probabilità del 100% di misurare 0 e del 100% di misurare 1.

L'azione di misurazione genera un risultato binario e modifica lo stato del qubit.
La misurazione produce un valore binario, ovvero 0 o 1.  Il qubit passa dall'essere in sovrapposizione (qualsiasi direzione) a uno degli stati classici.  Successivamente, la ripetizione della stessa misurazione senza alcuna operazione genera lo stesso risultato binario.  

Più qubit possono anche trovarsi in uno stato di [**entanglement**](xref:microsoft.quantum.glossary#entanglement).  Quando si esegue la misurazione di un qubit con entanglement, vengono aggiornate anche le informazioni sullo stato degli altri qubit.

A questo punto si è pronti per dimostrare in che modo Q# esprime questo comportamento.  Si inizierà con il programma più semplice possibile e lo si svilupperà per mostrare la sovrapposizione quantistica e l'entanglement quantistico.

## <a name="creating-a-no-locq-project"></a>Creazione di un Q# progetto

La prima cosa da fare è creare un nuovo Q# progetto. In questa esercitazione verrà usato l'ambiente in base alle [ Q# applicazioni con vs code](xref:microsoft.quantum.install.standalone).

Per creare un nuovo progetto, in VS Code: 

1. Fare clic su **Visualizza** -> **Riquadro comandi** e selezionare **Q#: Create New Project**(ASA: Crea nuovo progetto).
2. Click **Standalone console application** (Applicazione console autonoma).
3. Passare al percorso in cui salvare il progetto e fare clic su **Create Project** (Crea progetto).
4. Al termine dell'operazione, fare clic su **Open new project** (Apri nuovo progetto) in basso a destra.

In questo caso è stato chiamato il progetto `Bell` . Vengono generati due file: `Bell.csproj` , il file di progetto e `Program.qs` , un modello di Q# applicazione che verrà usato per scrivere l'applicazione. Il contenuto di `Program.qs` deve essere:

```qsharp
   namespace Bell {

      open Microsoft.Quantum.Canon;
      open Microsoft.Quantum.Intrinsic;
    

      @EntryPoint()
      operation HelloQ() : Unit {
          Message("Hello quantum world!");
      }
   }
```

## <a name="write-the-q-application"></a>Scrivere l' \# applicazione Q
 
L'obiettivo è quello di preparare due qubits in uno stato quantico specifico, dimostrando come operare su qubits con Q# per modificare il proprio stato e dimostrare gli effetti della superposizione e del groviglio. Questa operazione verrà compilata in base a un elemento per introdurre gli Stati, le operazioni e la misurazione di qubit.

### <a name="initialize-qubit-using-measurement"></a>Inizializzare qubit usando la misurazione

Nel primo frammento di codice riportato di seguito viene illustrato come utilizzare qubits in Q# .  Verranno introdotte due operazioni, [`M`](xref:microsoft.quantum.intrinsic.m) [`X`](xref:microsoft.quantum.intrinsic.x) che trasformano lo stato di un qubit. In questo frammento di codice viene definita un'operazione `SetQubitState` che accetta come parametro un qubit e un altro parametro, `desired`, che rappresenta lo stato in cui deve trovarsi il qubit.  L'operazione `SetQubitState` esegue una misura del qubit tramite l'operazione `M`.  In Q# una misura qubit restituisce sempre `Zero` o `One` .  Se la misurazione restituisce un valore diverso da quello desiderato, `SetQubitState` "capovolge" qubit, ovvero esegue un' `X` operazione, che modifica lo stato qubit in un nuovo stato in cui le probabilità di una misurazione `Zero` che restituisce e `One` sono invertite. In questo modo, `SetQubitState` inserisce sempre il qubit di destinazione nello stato desiderato.

Sostituire il contenuto di `Program.qs` con il codice seguente:


```qsharp
   namespace Bell {
       open Microsoft.Quantum.Intrinsic;
       open Microsoft.Quantum.Canon;

       operation SetQubitState(desired : Result, q1 : Qubit) : Unit {
           if (desired != M(q1)) {
               X(q1);
           }
       }
   }
```

Questa operazione può ora essere chiamata per impostare un qubit su uno stato classico, restituendo `Zero` il 100% delle volte o restituendo `One` il 100% delle volte.
`Zero` e `One` sono costanti che rappresentano gli unici due risultati possibili della misura di un qubit.

L'operazione `SetQubitState` misura il qubit. Se il qubit è nello stato desiderato, lo `SetQubitState` lascia da solo. in caso contrario, eseguendo l' `X` operazione, lo stato di qubit viene modificato in base allo stato desiderato.

#### <a name="about-no-locq-operations"></a>Informazioni sulle Q# operazioni

Un' Q# operazione è una subroutine Quantum. Ovvero una routine chiamabile che contiene chiamate ad altre operazioni Quantum.

Gli argomenti di un'operazione vengono specificati come tuple, racchiuse tra parentesi.

Il tipo restituito dell'operazione viene specificato dopo i due punti. In questo caso, l' `SetQubitState` operazione non ha alcun tipo restituito, quindi è contrassegnata come restituzione `Unit` . Si tratta dell' Q# equivalente di `unit` in F #, che è approssimativamente analogo a `void` in C# e di una tupla vuota in Python ( `()` , rappresentata dall'hint di tipo `Tuple[()]` ).

Sono state usate due operazioni Quantum nella prima Q# operazione:

* [`M`](xref:microsoft.quantum.intrinsic.m)Operazione, che misura lo stato di qubit
* [`X`](xref:microsoft.quantum.intrinsic.x)Operazione, che capovolge lo stato di un qubit

Un'operazione quantistica trasforma lo stato di un qubit. In alcuni casi si parla di gate quantistici anziché di operazioni, per analogia con i gate logici classici. Questo risale alle fasi iniziali del calcolo quantistico quando gli algoritmi erano semplicemente un costrutto teorico e venivano visualizzati come diagrammi in modo analogo ai diagrammi di circuito nell'informatica classica.

### <a name="counting-measurement-outcomes"></a>Conteggio dei risultati di misurazione

Per illustrare l'effetto dell'operazione `SetQubitState`, viene quindi aggiunta un'operazione `TestBellState`. Questa operazione accetta come input `Zero` o `One`, chiama l'operazione `SetQubitState` un determinato numero di volte con tale input e conta il numero di volte in cui la misura del qubit ha restituito `Zero` e il numero di volte in cui ha restituito `One`. Naturalmente, in questa prima simulazione dell'operazione `TestBellState`, si prevede che l'output mostri che tutte le misure del qubit impostato con `Zero` come input del parametro restituiranno `Zero` e tutte le misure di un qubit impostato con `One` come input del parametro restituiranno `One`. Successivamente, verrà aggiunto il codice a `TestBellState` per dimostrare la superposizione e l'aggancio.

Aggiungere l'operazione seguente al file `Program.qs`, all'interno dello spazio dei nomi, dopo la fine dell'operazione `SetQubitState`:

```qsharp
   operation TestBellState(count : Int, initial : Result) : (Int, Int) {

       mutable numOnes = 0;
       using (qubit = Qubit()) {

           for (test in 1..count) {
               SetQubitState(initial, qubit);
               let res = M(qubit);

               // Count the number of ones we saw:
               if (res == One) {
                   set numOnes += 1;
               }
           }
            
           SetQubitState(Zero, qubit);
       }

       // Return number of times we saw a |0> and number of times we saw a |1>
       Message("Test results (# of 0s, # of 1s): ");
       return (count - numOnes, numOnes);
   }
```
Si noti che è stata aggiunta una riga prima `return` di per stampare un messaggio esplicativo nella console con la funzione ( `Message` ) [Microsoft. Quantum. intrinsec. Message]

Questa operazione (`TestBellState`) verrà ripetuta ciclicamente per `count` iterazioni, imposterà un valore `initial` specificato in un qubit e quindi misurerà (`M`) il risultato. Raccoglierà le statistiche sul numero di zeri e di uno misurati e li restituirà al chiamante. Esegue inoltre un'altra operazione necessaria. Reimposta il qubit su uno stato noto (`Zero`) prima di restituirlo, per consentire ad altri di allocare questo qubit in uno stato noto. Questo passaggio è richiesto dall'istruzione `using`.

#### <a name="about-variables-in-q"></a>Informazioni sulle variabili in Q\#

Per impostazione predefinita, le variabili in Q# non sono modificabili. il relativo valore non può essere modificato dopo l'associazione. Viene usata la parola chiave `let` per indicare l'associazione di una variabile non modificabile. Gli argomenti dell'operazione sono sempre non modificabili.

Se occorre una variabile il cui valore può essere modificato, ad esempio `numOnes` nell'esempio, è possibile dichiarare la variabile con la parola chiave `mutable`. È possibile modificare il valore di una variabile modificabile usando un'istruzione `set`.

In entrambi i casi, il tipo di una variabile viene dedotto dal compilatore. Q# non richiede alcuna annotazione di tipo per le variabili.

#### <a name="about-using-statements-in-q"></a>Informazioni sulle `using` istruzioni in Q\#

L' `using` istruzione è inoltre speciale per Q# . Viene usata per allocare i qubit per l'uso in un blocco di codice. In Q# tutti i qubits vengono allocati e rilasciati in modo dinamico, anziché essere risorse fisse per l'intera durata di un algoritmo complesso. Un'istruzione `using` alloca un set di qubit all'inizio e rilascia tali qubit alla fine del blocco.

## <a name="run-the-code-from-the-command-prompt"></a>Eseguire il codice dal prompt dei comandi

Per eseguire il codice, è necessario indicare al compilatore *che* è possibile eseguire quando si specifica il `dotnet run` comando. Questa operazione viene eseguita con una semplice modifica apportata al Q# file aggiungendo una riga con `@EntryPoint()` direttamente prima di callable: l' `TestBellState` operazione in questo caso. Il codice completo deve essere:

```qsharp
namespace Bell {
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Intrinsic;

    operation SetQubitState(desired : Result, target : Qubit) : Unit {
        if (desired != M(target)) {
            X(target);
        }
    }

    @EntryPoint()
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                SetQubitState(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }

            SetQubitState(Zero, qubit);
        }

    // Return number of times we saw a |0> and number of times we saw a |1>
    Message("Test results (# of 0s, # of 1s): ");
    return (count - numOnes, numOnes);
    }
}
```

Per eseguire il programma, è necessario specificare `count` `initial` gli argomenti e dal prompt dei comandi. Si sceglierà ad esempio `count = 1000` e `initial = One` . Immettere il comando seguente:

```dotnetcli
dotnet run --count 1000 --initial One
```

Ed è necessario osservare l'output seguente:

```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

Se si prova a usare `initial = Zero` , è necessario osservare quanto segue:

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

## <a name="prepare-superposition"></a>Preparare la sovrapposizione

Si esaminerà ora il modo in cui vengono illustrate le Q# modalità di inserimento di qubits in superposition.  Tenere presente che lo stato di un qubit può essere in una sovrapposizione di 0 e 1.  A tale scopo, verrà usata l'operazione `Hadamard`. Se il qubit è in uno degli stati classici (in cui una misura restituisce sempre `Zero` o sempre `One`), l'operazione `Hadamard` o `H` imposterà il qubit su uno stato in cui una misura del qubit restituirà `Zero` il 50% delle volte e `One` il 50% delle volte.  A livello concettuale, il qubit può essere considerato a metà tra `Zero` e `One`.  Ora, quando si simula l'operazione `TestBellState`, si osserverà che i risultati restituiranno approssimativamente un numero uguale di `Zero` e `One` dopo la misura.  

### <a name="x-flips-qubit-state"></a>`X` capovolge lo stato qubit

Prima di tutto si proverà a capovolgere il qubit (se il qubit è in `Zero` stato, verrà invertito `One` e viceversa). A tale scopo, si esegue un'operazione `X` prima di misurarlo in `TestBellState`:

```qsharp
X(qubit);
let res = M(qubit);
```

I risultati sono ora invertiti:

```dotnetcli
dotnet run --count 1000 --initial One
```

```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

Verranno ora esaminate le proprietà Quantum del qubits.

### <a name="h-prepares-superposition"></a>`H` prepara la superposizione

È sufficiente sostituire l'operazione `X` nell'esecuzione precedente con un'operazione `H` o un'operazione di Hadamard. Anziché invertire il qubit da 0 a 1, verrà solo invertito a metà. Le righe sostituite in `TestBellState` ora hanno un aspetto simile al seguente:

```qsharp
H(qubit);
let res = M(qubit);
```

A questo punto, il risultato diventa più interessante:

```dotnetcli
dotnet run --count 1000 --initial One
```

```output
Test results (# of 0s, # of 1s):
(496, 504)
```

```dotnetcli
dotnet run --count 1000 --initial Zero
```

```output
Test results (# of 0s, # of 1s):
(506, 494)
```

Ogni volta che si esegue una misura, viene richiesto un valore classico, ma il qubit si trova a metà tra 0 e 1, quindi si ottiene (statisticamente) 0 per metà delle volte e 1 per metà delle volte.
Questa operazione è nota come **sovrapposizione** e offre la prima osservazione reale dello stato quantistico.

## <a name="prepare-entanglement"></a>Preparare l'entanglement

Esaminiamo ora come esprimere i Q# modi per impigliare qubits.
In primo luogo, si imposta il primo qubit sullo stato iniziale e quindi si usa l'operazione `H` per posizionarlo in sovrapposizione.  Quindi, prima di misurare il primo qubit, viene usata una nuova operazione ( `CNOT` ), che sta per essere *controllata*.  Il risultato dell'esecuzione di questa operazione su due qubits è il capovolgimento della seconda qubit se il primo qubit è `One` .  A questo punto, i due qubit sono correlati (in entanglement).  Le statistiche per il primo qubit sono rimaste invariate (probabilità 50-50 di `Zero` o `One`), ma ora quando viene misurato il secondo qubit, è __sempre__ uguale a quanto misurato per il primo qubit. Il gate `CNOT` ha eseguito l'entanglement dei due qubit, così qualsiasi cosa accade a uno di essi, accade anche all'altro. Se sono state invertite le misure, ovvero se è stato misurato il secondo qubit prima del primo, si verificherà lo stesso risultato. La prima misura sarà casuale e la seconda si troverà nel passaggio del blocco con quanto individuato per la prima.

Per prima cosa è necessario allocare due qubits anziché uno in `TestBellState` :

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

Questo consentirà di aggiungere una nuova operazione (`CNOT`) prima di misurare (`M`) in `TestBellState`:

```qsharp
SetQubitState(initial, q0);
SetQubitState(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

È stata aggiunta un'altra operazione `SetQubitState` per inizializzare il primo qubit per assicurarsi che sia sempre nello stato `Zero` quando si inizia.

È anche necessario reimpostare il secondo qubit prima di rilasciarlo.

```qsharp
SetQubitState(Zero, q0);
SetQubitState(Zero, q1);
```

La routine completa ha ora un aspetto simile al seguente:

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                SetQubitState(initial, q0);
                SetQubitState(Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }

            SetQubitState(Zero, q0);
            SetQubitState(Zero, q1);
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
                SetQubitState(initial, q0);
                SetQubitState(Zero, q1);

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
            
            SetQubitState(Zero, q0);
            SetQubitState(Zero, q1);
        }

        // Return times we saw |0>, times we saw |1>, and times measurements agreed
        Message("Test results (# of 0s, # of 1s, # of agreements)");
        return (count-numOnes, numOnes, agree);
    }
```

Il nuovo valore restituito (`agree`) tiene traccia di ogni volta che la misurazione del primo qubit corrisponde alla misurazione del secondo qubit.

Esecuzione del codice ottenuto:

```dotnetcli
dotnet run --count 1000 --initial One
```
```output
(505, 495, 1000)
```
```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s, # of agreements)
(507, 493, 1000)
```

Come dichiarato nella panoramica, le statistiche per il primo qubit sono rimaste invariate (probabilità 50-50 di uno 0 o 1), ma ora quando viene misurato il secondo qubit, è __sempre__ uguale a quanto misurato per il primo qubit perché sono correlati (in entanglement).

## <a name="next-steps"></a>Passaggi successivi

L'esercitazione relativa alla [ricerca di Grover](xref:microsoft.quantum.quickstarts.search) Mostra come compilare ed eseguire la ricerca Grover, uno degli algoritmi di calcolo quantistica più diffusi e offre un esempio interessante di Q# programma che può essere usato per risolvere i problemi reali con l'elaborazione quantistica.  

[Introduzione a Quantum Development Kit](xref:microsoft.quantum.welcome) suggerisce altri modi per apprendere Q# e programmare la programmazione quantistica.
