---
title: Test e debug
description: Informazioni su come usare unit test, fact e asserzioni e funzioni dump per testare ed eseguire il debug di programmi Quantum.
author: tcNickolas
ms.author: mamykhai
ms.date: 06/01/2020
ms.topic: article
uid: microsoft.quantum.guide.testingdebugging
no-loc:
- Q#
- $$v
ms.openlocfilehash: 17a67f0a6fa7ffb9436828178acd93e1cb87a8cd
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96233990"
---
# <a name="testing-and-debugging"></a>Test e debug

Come per la programmazione classica, è essenziale poter controllare che i programmi Quantum funzionino come previsto e per poter diagnosticare un comportamento non corretto.
Questa sezione include gli strumenti offerti da Q# per il test e il debug di programmi Quantum.

## <a name="unit-tests"></a>Unit test

Un approccio comune al test dei programmi classici è quello di scrivere piccoli programmi denominati *unit test*, che eseguono codice in una libreria e confrontano l'output con un output previsto.
Ad esempio, è possibile assicurarsi che venga `Square(2)` restituito `4` perché si conosce *un valore precedente a* $2 ^ 2 = $4.

Q# supporta la creazione di unit test per i programmi Quantum e che può essere eseguito come test nel Framework di unit test di [xUnit](https://xunit.github.io/) .

### <a name="creating-a-test-project"></a>Creazione di un progetto di test

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Aprire Visual Studio 2019. Passare al menu **file** e selezionare **nuovo > progetto...**. Nell'angolo in alto a destra cercare `Q#` e selezionare il modello di **Q# progetto di test** .

#### <a name="command-line--visual-studio-code"></a>[Riga di comando/Visual Studio Code](#tab/tabid-vscode)

Dalla riga di comando preferita, eseguire il comando seguente:
```dotnetcli
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

Il nuovo progetto include un unico file `Tests.qs` , che offre una posizione pratica per definire nuovi Q# unit test.
Inizialmente, questo file contiene un unit test `AllocateQubit` di esempio che verifica che un qubit appena allocato si trovi nello {0} stato $ \ket $ e stampa un messaggio:

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            AssertMeasurement([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

Qualsiasi Q# operazione o funzione che accetta un argomento di tipo `Unit` e restituisce `Unit` può essere contrassegnata come unit test tramite l' `@Test("...")` attributo. Nell'esempio precedente, l'argomento dell'attributo, `"QuantumSimulator"` , specifica la destinazione in cui viene eseguito il test. Un singolo test può essere eseguito su più destinazioni. Ad esempio, aggiungere un attributo `@Test("ResourcesEstimator")` prima di `AllocateQubit` . 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
Salvare il file ed eseguire tutti i test. A questo punto dovrebbero essere presenti due unit test, uno `AllocateQubit` in cui viene eseguito in `QuantumSimulator` e uno in cui viene eseguito in `ResourcesEstimator` . 

Il Q# compilatore riconosce le destinazioni predefinite `"QuantumSimulator"` , `"ToffoliSimulator"` , e `"ResourcesEstimator"` come destinazioni di esecuzione valide per gli unit test. È anche possibile specificare un nome completo per definire una destinazione di esecuzione personalizzata. 

### <a name="running-no-locq-unit-tests"></a>Esecuzione di Q# unit test

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Per la configurazione unica per soluzione, passare al menu **test** e selezionare **impostazioni test > architettura del processore predefinita > x64**.

> [!TIP]
> L'impostazione predefinita dell'architettura del processore per Visual Studio è archiviata nel file di opzioni soluzione ( `.suo` ) per ogni soluzione.
> Se si elimina questo file, è necessario selezionare **x64** come architettura del processore.

Compilare il progetto, aprire il menu **test** e selezionare **Windows > Esplora test**. **AllocateQubit** viene visualizzato nell'elenco dei test nel gruppo **test non eseguiti** . Selezionare **Esegui tutto** o eseguire questo test singolo.

#### <a name="command-line--visual-studio-code"></a>[Riga di comando/Visual Studio Code](#tab/tabid-vscode)

Per eseguire i test, passare alla cartella del progetto (la cartella che contiene `Tests.csproj` ) ed eseguire il comando:

```bash
$ dotnet restore
$ dotnet test
```

L'output dovrebbe essere simile al seguente:

```
Build started, please wait...
Build completed.

Test run for C:\Users\chgranad.REDMOND\tmp\Tests\bin\Debug\netcoreapp2.0\Tests.dll(.NETCoreApp,Version=v2.0)
Microsoft (R) Test Execution Command Line Tool Version 15.3.0-preview-20170628-02
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
[xUnit.net 00:00:00.5864002]   Discovering: Tests
[xUnit.net 00:00:00.7073844]   Discovered:  Tests
[xUnit.net 00:00:00.7453826]   Starting:    Tests
[xUnit.net 00:00:00.9590439]   Finished:    Tests

Total tests: 1. Passed: 1. Failed: 0. Skipped: 0.
Test Run Successful.
Test execution time: 1.9607 Seconds
```

Gli unit test possono essere filtrati in base al nome o alla destinazione di esecuzione:

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


**_

La funzione intrinseca <xref:Microsoft.Quantum.Intrinsic.Message> è `(String -> Unit)` di tipo e consente la creazione di messaggi di diagnostica.

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Dopo aver eseguito un test in Esplora test e aver fatto clic sul test, viene visualizzato un pannello con le informazioni sull'esecuzione dei test: stato superato/non superato, tempo trascorso e collegamento all'output. Fare clic su _ *output** per aprire l'output del test in una nuova finestra.

![output del test](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[Riga di comando/Visual Studio Code](#tab/tabid-vscode)

Lo stato di superamento/errore per ogni test viene stampato nella console da `dotnet test` .
Per i test con esito negativo, anche gli output vengono stampati nella console per facilitare la diagnosi dell'errore.

**_

## <a name="facts-and-assertions"></a>Fact e asserzioni

Poiché le funzioni in Q# non hanno effetti collaterali _logici_ , non è mai possibile osservare, dall'interno di un Q# programma, altri tipi di effetti dall'esecuzione di una funzione il cui tipo di output è la tupla vuota `()` .
In altre condizioni, un computer di destinazione può scegliere di non eseguire alcuna funzione che restituisce `()` con la garanzia che questa omissione non modificherà il comportamento di un codice di questo genere Q# .
Questo comportamento rende le funzioni `()` che restituiscono (ad esempio `Unit` ) uno strumento utile per incorporare le asserzioni e la logica di debug nei Q# programmi. 

Si prenda in considerazione un semplice esempio:

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

In questo caso, la parola chiave `fail` indica che il calcolo non deve continuare e genera un'eccezione nel computer di destinazione che esegue il Q# programma.
Per definizione, non è possibile osservare un errore di questo tipo in Q# , perché il computer di destinazione non esegue più il Q# codice dopo aver raggiunto un' `fail` istruzione.
Quindi, se si procede con una chiamata a `PositivityFact` , è possibile garantire che l'input sia positivo.

Si noti che è possibile implementare lo stesso comportamento dell' `PositivityFact` utilizzo della [`Fact`](xref:Microsoft.Quantum.Diagnostics.Fact) funzione dallo <xref:Microsoft.Quantum.Diagnostics> spazio dei nomi:

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

_Assertions *, d'altra parte, vengono usati in modo analogo ai fatti, ma possono dipendere dallo stato del computer di destinazione. In modo analogo, sono definite come operazioni, mentre i fact sono definiti come funzioni (come nell'esempio precedente).
Per comprendere la distinzione, prendere in considerazione il seguente utilizzo di un fact all'interno di un'asserzione:

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

Qui viene utilizzata l'operazione <xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse> per restituire il numero di qubits disponibili per l'utilizzo.
Poiché dipende dallo stato globale del programma e dall'ambiente di esecuzione, anche la definizione di `AssertQubitsAreAvailable` deve essere un'operazione.
Tuttavia, è possibile usare tale stato globale per produrre un `Bool` valore semplice come input per la `Fact` funzione.

[Il preludio](xref:microsoft.quantum.libraries.standard.prelude), che si basa su queste idee, offre due asserzioni particolarmente utili <xref:Microsoft.Quantum.Diagnostics.AssertMeasurement> ed <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> entrambe modellate come operazioni su `()` . Ognuna di queste asserzioni accetta un operatore Pauli che descrive una particolare misurazione di interesse, un registro Quantum su cui viene eseguita una misura e un risultato ipotetico.
I computer di destinazione che funzionano con la simulazione non sono associati [al teorema di clonazione](https://en.wikipedia.org/wiki/No-cloning_theorem)e possono eseguire tali misure senza compromettere il registro che passa a tali asserzioni.
Un simulatore può quindi, analogamente alla `PositivityFact` funzione precedente, arrestare il calcolo se il risultato ipotetico non viene osservato in pratica:

```qsharp
using (register = Qubit()) 
{
    H(register);
    AssertMeasurement([PauliX], [register], Zero);
    // Even though we do not have access to states in Q#,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

Su hardware quantum fisico, in cui il teorema di non clonazione impedisce l'esame di uno stato quantico, le `AssertMeasurement` `AssertMeasurementProbability` operazioni e restituiscono semplicemente `()` senza alcun effetto.

Lo <xref:Microsoft.Quantum.Diagnostics> spazio dei nomi fornisce diverse funzioni della `Assert` famiglia, con cui è possibile controllare condizioni più avanzate. 

## <a name="dump-functions"></a>Funzioni dump

Per semplificare la risoluzione dei problemi relativi ai programmi Quantum, lo <xref:Microsoft.Quantum.Diagnostics> spazio dei nomi offre due funzioni che consentono di eseguire il dump in un file dello stato corrente del computer di destinazione: <xref:Microsoft.Quantum.Diagnostics.DumpMachine> e <xref:Microsoft.Quantum.Diagnostics.DumpRegister> . L'output generato di ogni dipende dal computer di destinazione.

### <a name="dumpmachine"></a>DumpMachine

Il simulatore Quantum a stato intero distribuito come parte del quantum Development Kit scrive nel file la [funzione Wave](https://en.wikipedia.org/wiki/Wave_function) dell'intero sistema Quantum, come matrice unidimensionale di numeri complessi, in cui ogni elemento rappresenta l'ampiezza della probabilità di misurazione dello stato di base computazionale $ \ket{n} $, dove $ \ket{n} = \ket{b_ {n-1}... b_1b_0} $ per BITS $ \{ b_i \} $. Ad esempio, in un computer con solo due qubits allocati e nello stato quantico $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} , \end{align} $ $ Call <xref:Microsoft.Quantum.Diagnostics.DumpMachine> genera questo output:

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

La prima riga fornisce un commento con gli ID dei qubits corrispondenti nell'ordine significativo.
Il resto delle righe descrive l'ampiezza di probabilità della misurazione del vettore di stato di base $ \ket{n} $ nei formati cartesiani e polari. In dettaglio per la prima riga:

* **`∣0❭:`** Questa riga corrisponde allo `0` stato di base di calcolo
* **`0.707107 +  0.000000 i`**: ampiezza della probabilità in formato cartesiano.
* **` == `**: il `equal` segno separa entrambe le rappresentazioni equivalenti.
* **`**********  `**: Rappresentazione grafica della grandezza, il numero di `*` è proporzionale alla probabilità di misurare questo vettore di stato.
* **`[ 0.500000 ]`**: valore numerico della grandezza
* **`    ---`**: Rappresentazione grafica della fase dell'ampiezza (vedere il seguente output).
* **`[ 0.0000 rad ]`**: valore numerico della fase (in radianti).

Sia la grandezza che la fase vengono visualizzate con una rappresentazione grafica. La rappresentazione di magnitude è semplice: Mostra una barra di `*` , più grande è la probabilità maggiore sarà la barra. Per la fase vengono mostrati i simboli seguenti per rappresentare l'angolo in base agli intervalli:

```
[ -π/16,   π/16)       ---
[  π/16,  3π/16)        /-
[ 3π/16,  5π/16)        / 
[ 5π/16,  7π/16)       +/ 
[ 7π/16,  9π/16)      ↑   
[ 8π/16, 11π/16)    \-    
[ 7π/16, 13π/16)    \     
[ 7π/16, 15π/16)   +\     
[15π/16, 19π/16)   ---    
[17π/16, 19π/16)   -/     
[19π/16, 21π/16)    /     
[21π/16, 23π/16)    /+    
[23π/16, 25π/16)      ↓   
[25π/16, 27π/16)       -\ 
[27π/16, 29π/16)        \ 
[29π/16, 31π/16)        \+
[31π/16,   π/16)       ---
```

Gli esempi seguenti illustrano `DumpMachine` alcuni stati comuni:

### `∣0❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

### `∣1❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣1❭:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
```

### `∣+❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
∣1❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
```

### `∣-❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
∣1❭:    -0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]  ---     [  3.14159 rad ]
```


  > [!NOTE]
  > L'ID di un qubit viene assegnato in fase di esecuzione e non è necessariamente allineato con l'ordine in cui è stato allocato qubit o la relativa posizione all'interno di un registro qubit.


#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

  > [!TIP]
  > È possibile individuare un ID qubit in Visual Studio inserendo un punto di interruzione nel codice e controllando il valore di una variabile qubit, ad esempio:
  > 
  > ![Mostra ID qubit in Visual Studio](~/media/qubit_id.png)
  >
  > qubit con index `0` on `register2` ha ID = `3` , qubit con index con `1` ID = `2` .

#### <a name="command-line--visual-studio-code"></a>[Riga di comando/Visual Studio Code](#tab/tabid-vscode)

  > [!TIP]
  > È possibile individuare un ID qubit usando la <xref:Microsoft.Quantum.Intrinsic.Message> funzione e passando la variabile qubit nel messaggio, ad esempio:
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > che può generare questo output:
  >```
  > 0=q:3; 1=q:2
  >```
  > il che significa che qubit con index `0` on `register2` ha ID = `3` , qubit con index con `1` ID = `2` .


**_

Poiché <xref:Microsoft.Quantum.Diagnostics.DumpMachine> fa parte dello  <xref:Microsoft.Quantum.Diagnostics> spazio dei nomi, è necessario aggiungere un' `open` istruzione per accedervi:

```qsharp
namespace Samples {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;

    operation Operation () : Unit {
        using (qubits = Qubit[2]) {
            H(qubits[1]);
            DumpMachine("dump.txt");
        }
    }
}
```


### <a name="dumpregister"></a>DumpRegister

<xref:Microsoft.Quantum.Diagnostics.DumpRegister> funziona come <xref:Microsoft.Quantum.Diagnostics.DumpMachine> , ad eccezione del fatto che accetta anche una matrice di qubits per limitare la quantità di informazioni solo a quella pertinente per il qubits corrispondente.

Come per <xref:Microsoft.Quantum.Diagnostics.DumpMachine> , le informazioni generate da <xref:Microsoft.Quantum.Diagnostics.DumpRegister> dipendono dal computer di destinazione. Per il simulatore Quantum a stato completo scrive nel file la funzione Wave fino a una fase globale del sottosistema Quantum generato dal qubits specificato nello stesso formato di <xref:Microsoft.Quantum.Diagnostics.DumpMachine> .  Ad esempio, riportare un computer con solo due qubits allocati e nello stato quantico $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} =-e ^ {-i \ PI/4} ((\frac {1} {\sqrt {2} } \ket {0} -\frac{(1 + i)} {2} \ket {1} ) \otimes \frac{-(1 + i)} {\sqrt {2} } \ket {0} ), \end{align} $ $ Calling <xref:Microsoft.Quantum.Diagnostics.DumpRegister> per `qubit[0]` genera questo output:

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     _******************* [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

e <xref:Microsoft.Quantum.Diagnostics.DumpRegister> la chiamata a per `qubit[1]` genera questo output:

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

In generale, lo stato di un registro con un altro registro è uno stato misto anziché uno stato puro. In questo caso, <xref:Microsoft.Quantum.Diagnostics.DumpRegister> restituisce il messaggio seguente:

```
Qubits provided (0;) are entangled with some other qubit.
```

Nell'esempio seguente viene illustrato come è possibile utilizzare sia <xref:Microsoft.Quantum.Diagnostics.DumpRegister> che <xref:Microsoft.Quantum.Diagnostics.DumpMachine> nel Q# codice:

```qsharp
namespace app
{
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;

    operation Operation () : Unit {

        using (qubits = Qubit[2]) {
            X(qubits[1]);
            H(qubits[1]);
            R1Frac(1, 2, qubits[1]);
            
            DumpMachine("dump.txt");
            DumpRegister("q0.txt", qubits[0..0]);
            DumpRegister("q1.txt", qubits[1..1]);

            ResetAll(qubits);
        }
    }
}
```

## <a name="debugging"></a>Debug

Oltre alle `Assert` `Dump` funzioni e alle operazioni, Q# supporta un sottoinsieme di funzionalità di debug standard di Visual Studio: l'impostazione di punti di [interruzione di riga](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), l'esecuzione di [codice con F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)e il [controllo dei valori delle variabili classiche](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) sono tutti possibili quando si esegue il codice nel simulatore.

Il debug in Visual Studio Code sfrutta le funzionalità di debug fornite da C# per Visual Studio Code estensione con tecnologia OmniSharp e richiede l'installazione della [versione più recente](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp). 