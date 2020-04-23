---
title: Test e debug dei programmi Q .
description: Informazioni su come usare unit test, fatti e asserzioni ed eseguire il dump delle funzioni per testare ed eseguire il debug di programmi quantistici.
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: caf15b7273b7efed1da87a2edd62c06cd4357593
ms.sourcegitcommit: b6b8459eb654040f1e19f66411b29fc9e48e95c9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "82030583"
---
# <a name="testing-and-debugging"></a>Test e debug

Come per la programmazione classica, è essenziale essere in grado di verificare che i programmi quantistici agiscano come previsto, e di essere in grado di diagnosticare un programma quantistico che non è corretto.
In questa sezione vengono illustrati gli strumenti offerti da Q per il test e il debug di programmi quantistici.

## <a name="unit-tests"></a>Unit test

Un approccio comune per testare i programmi classici consiste nello scrivere programmi di piccole dimensioni denominati *unit test* che eseguono codice in una libreria e ne confrontano l'output con un output previsto.
Ad esempio, potremmo voler `Square(2)` garantire `4`che restituisca , dato che sappiamo *a priori* che .

Il sistema Q è supporta la creazione di unit test per programmi quantistici e che possono essere eseguiti come test all'interno del framework di unit test [xUnit.](https://xunit.github.io/)

### <a name="creating-a-test-project"></a>Creazione di un progetto di testCreating a Test Project

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Aprire Visual Studio 2019. Vai al `File` menu `New`  >  `Project...`e seleziona .
Nell'angolo superiore destro `Q#`cercare e `Q# Test Project` selezionare il modello.

#### <a name="command-line--visual-studio-code"></a>[Riga di comando/Visual Studio Code](#tab/tabid-vscode)

Dalla riga di comando preferita, eseguire il comando seguente:
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

Il nuovo progetto disporrà di un singolo file, `Tests.qs`che offre una comoda posizione per definire i nuovi unit test di Q.
Inizialmente questo file contiene `AllocateQubit` uno unit test di esempio che controlla che{0}un qubit appena allocato si trova nello stato di errore e stampa un messaggio:

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            Assert([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

:new: qualsiasi operazione o funzione di Q `Unit` che `Unit` accetta un argomento di `@Test("...")` tipo e restituisce può essere contrassegnata come unit test tramite l'attributo . L'argomento di `"QuantumSimulator"` tale attributo, precedente, specifica la destinazione su cui viene eseguito il test. Un singolo test può essere eseguito su più destinazioni. Ad esempio, aggiungere `@Test("ResourcesEstimator")` `AllocateQubit`un attributo sopra . 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
Salvare il file ed eseguire tutti i test. Dovrebbero essere presenti due unit test, uno in cui AllocateQubit viene eseguito su QuantumSimulator e uno in cui viene eseguito nel ResourceEstimator. 

Il compilatore Q, riconosce le destinazioni predefinite "QuantumSimulator", "ToffoliSimulator" e "ResourcesEstimator" come destinazioni di esecuzione valide per gli unit test. È inoltre possibile specificare qualsiasi nome completo per definire una destinazione di esecuzione personalizzata. 

### <a name="running-q-unit-tests"></a>Esecuzione di unit test Q

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Come configurazione una tantera per `Test` soluzione, `Test Settings`  >  `Default Processor Architecture`  > passare al menu e selezionare `X64`.

> [!TIP]
> L'impostazione dell'architettura del processore predefinita`.suo`per Visual Studio viene archiviata nel file delle opzioni della soluzione ( ) per ogni soluzione.
> Se si elimina questo file, sarà `X64` necessario selezionare nuovamente come architettura del processore.

Compilare il progetto, `Test` accedere `Windows`  >  `Test Explorer`al menu e selezionare . `AllocateQubit`apparirà nell'elenco dei test `Not Run Tests` nel gruppo. Selezionare `Run All` o eseguire questo test individuale, e dovrebbe passare!

#### <a name="command-line--visual-studio-code"></a>[Riga di comando/Visual Studio Code](#tab/tabid-vscode)

Per eseguire i test, passare alla cartella `Tests.csproj`del progetto (la cartella che contiene ) ed eseguire il comando:

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

Gli unit test possono essere filtrati in base al nome e/o all'obiettivo di esecuzione:

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

La funzione <xref:microsoft.quantum.intrinsic.message> intrinseca ha tipo `(String -> Unit)` e consente la creazione di messaggi di diagnostica.

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Dopo aver eseguito un test in Esplora test e aver fatto clic sul test, verrà visualizzato un pannello con le informazioni sull'esecuzione del test: stato Superato/Non superato, tempo trascorso e collegamento "Output". Se si fa clic sul collegamento "Output", l'output di test si aprirà in una nuova finestra.

![uscita di prova](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[Riga di comando/Visual Studio Code](#tab/tabid-vscode)

Lo stato superato/non superato per ogni `dotnet test`test viene stampato nella console da .
Per i test non superati, gli output vengono stampati anche nella console per diagnosticare l'errore.

***

## <a name="facts-and-assertions"></a>Fatti e asserzioni

Poiché le funzioni in Q , non hanno effetti collaterali _logici,_ qualsiasi altro `()` _tipo_ di effetti di esecuzione di una funzione il cui tipo di output è la tupla vuota non può mai essere osservato dall'interno di un programma Di O.
In altre parte, un computer di destinazione `()` può scegliere di non eseguire alcuna funzione che restituisce con la garanzia che questa omissione non modificherà il comportamento di qualsiasi codice Q .
In questo modo `()` le funzioni `Unit`che restituiscono (ad esempio) uno strumento utile per l'incorporamento di asserzioni e la logica di debug nei programmi Q. 

Consideriamo un semplice esempio:

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

In questo `fail` caso, la parola chiave indica che il calcolo non deve procedere, generando un'eccezione nel computer di destinazione che esegue il programma Q.
Per definizione, un errore di questo tipo non può essere osservato dall'interno `fail` di Q , poiché non viene eseguito alcun ulteriore codice Q , dopo il raggiungimento di un'istruzione.
Così, se procediamo `PositivityFact`passato una chiamata a , possiamo essere certi dal fatto che il suo input è stato positivo.

Si noti che è `PositivityFact` possibile [`Fact`](xref:microsoft.quantum.diagnostics.fact) implementare <xref:microsoft.quantum.diagnostics> lo stesso comportamento dell'utilizzo della funzione dallo spazio dei nomi:Note that we can implement the same behavior as using the function from the namespace:

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

*Le asserzioni*, d'altra parte, vengono utilizzate in modo simile ai fatti, ma possono dipendere dallo stato del computer di destinazione. Di conseguenza, sono definiti come operazioni, mentre i fatti sono definiti come funzioni (come sopra).
Per comprendere la distinzione, considerare il seguente utilizzo di un fatto all'interno di un'asserzione:

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

Qui, stiamo usando <xref:microsoft.quantum.environment.getqubitsavailabletouse> l'operazione per restituire il numero di qubit disponibili per l'uso.
Poiché questo dipende chiaramente dallo stato globale del programma `AssertQubitsAreAvailable` e dal suo ambiente di esecuzione, anche la nostra definizione di deve essere un'operazione.
Tuttavia, è possibile utilizzare tale `Bool` stato globale per `Fact` restituire un valore semplice come input per la funzione.

Sulla base di queste idee, [il preludio](xref:microsoft.quantum.libraries.standard.prelude) offre due asserzioni particolarmente utili ed <xref:microsoft.quantum.intrinsic.assert> <xref:microsoft.quantum.intrinsic.assertprob> entrambe modellate come operazioni su . `()` Queste asserzioni prendono ciascuna un operatore Pauli che descrive una particolare misurazione dell'interesse, un registro quantistico su cui deve essere eseguita una misurazione e un risultato ipotetico.
Sulle macchine bersaglio che funzionano tramite simulazione, non siamo vincolati dal [teorema](https://en.wikipedia.org/wiki/No-cloning_theorem)di non clonazione e possiamo eseguire tali misurazioni senza disturbare il registro passato a tali asserzioni.
Un simulatore può quindi, analogamente alla funzione precedente, interrompere il `PositivityFact` calcolo se l'esito ipotetico non viene osservato nella pratica:

```qsharp
using (register = Qubit()) 
{
    H(register);
    Assert([PauliX], [register], Zero);
    // Even though we do not have access to states in Q#,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

Sull'hardware quantistico fisico, dove il teorema no-cloning `AssertProb` impedisce `()` l'esame dello stato quantistico, le `Assert` operazioni e ritornano semplicemente senza altri effetti.

Lo <xref:microsoft.quantum.diagnostics> spazio dei nomi `Assert` fornisce diverse altre funzioni della famiglia che ci permettono di controllare le condizioni più avanzate. 

## <a name="dump-functions"></a>Funzioni di dump

Per facilitare la <xref:microsoft.quantum.diagnostics> risoluzione dei problemi relativi ai programmi quantistici, <xref:microsoft.quantum.diagnostics.dumpmachine> lo <xref:microsoft.quantum.diagnostics.dumpregister>spazio dei nomi offre due funzioni che possono eseguire il dump in un file dello stato corrente del computer di destinazione: e . L'output generato di ciascuno dipende dal computer di destinazione.

### <a name="dumpmachine"></a>DumpMachine

Il simulatore quantistico full-state distribuito come parte del Quantum Development Kit scrive nel file la [funzione d'onda](https://en.wikipedia.org/wiki/Wave_function) dell'intero sistema quantistico, come una matrice unidimensionale di numeri complessi, in cui ogni elemento rappresenta l'ampiezza della probabilità di misurare b_ lo stato di base computazionale . b_1b_0 per bit,\{b_i\}di z. Ad esempio, in un computer in cui sono stati allocati solo due qubit e nello stato quantistico , "inizio",{00} "inizio" , "se",{2} "sepsi" o "frac"{1}, "sqrt" e "sqt"{2}- "frac" (1 , "i", "fine",{10}"fine" e "chiamata" <xref:microsoft.quantum.diagnostics.dumpmachine> genera questo output:

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

La prima riga fornisce un commento con gli ID dei qubit corrispondenti nell'ordine significativo.
Il resto delle righe descrive l'ampiezza di probabilità di misurare il vettore di stato di base , in entrambi i formati cartesiano e polare. In dettaglio per la prima riga:

* **`∣0❭:`** questa riga corrisponde `0` allo stato di base computazionale
* **`0.707107 +  0.000000 i`**: l'ampiezza di probabilità in formato cartesiano.
* **` == `**: `equal` il segno si separa entrambe le rappresentazioni equivalenti.
* **`**********  `**: Rappresentazione grafica della grandezza, il `*` numero di è proporzionato alla probabilità di misurare questo vettore di stato.
* **`[ 0.500000 ]`**: il valore numerico della grandezza
* **`    ---`**: rappresentazione grafica della fase dell'ampiezza (vedi sotto).
* **`[ 0.0000 rad ]`**: il valore numerico della fase (in radianti).

Sia la grandezza che la fase vengono visualizzate con una rappresentazione grafica. La rappresentazione di magnitudo è dritta: mostra una barra di `*`, maggiore è la probabilità che più grande sarà la barra. Per la fase, mostriamo i seguenti simboli per rappresentare l'angolo in base agli intervalli:

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

Gli esempi `DumpMachine` seguenti illustrano alcuni stati comuni:The following examples show for some common states:

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
  > L'ID di un qubit viene assegnato in fase di esecuzione e non è necessariamente allineato con l'ordine in cui è stato allocato il qubit o la sua posizione all'interno di un registro qubit.


#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

  > [!TIP]
  > È possibile calcolare un id qubit in Visual Studio inserendo un punto di interruzione nel codice e controllando il valore di una variabile qubit, ad esempio:You can figure out a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:
  > 
  > ![show qubit id in Visual Studio](~/media/qubit_id.png)
  >
  > il qubit `0` con `register2` index`3`on has id `1` , il`2`qubit con index has id .

#### <a name="command-line--visual-studio-code"></a>[Riga di comando/Visual Studio Code](#tab/tabid-vscode)

  > [!TIP]
  > È possibile calcolare un id <xref:microsoft.quantum.intrinsic.message> qubit utilizzando la funzione e passando la variabile qubit nel messaggio, ad esempio:
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > che potrebbe generare questo output:
  >```
  > 0=q:3; 1=q:2
  >```
  > il che significa che `0` il `register2` qubit`3`con index on `1` has`2`id , il qubit con index has id .


***

<xref:microsoft.quantum.diagnostics.dumpmachine>fa parte <xref:microsoft.quantum.diagnostics> dello spazio dei nomi, pertanto `open` per poterlo utilizzare è necessario aggiungere un'istruzione:

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

<xref:microsoft.quantum.diagnostics.dumpregister>funziona <xref:microsoft.quantum.diagnostics.dumpmachine>come , tranne per il fatto che ci vuole anche una serie di qubit per limitare la quantità di informazioni solo a quella rilevante per i qubit corrispondenti.

Come <xref:microsoft.quantum.diagnostics.dumpmachine>per , le <xref:microsoft.quantum.diagnostics.dumpregister> informazioni generate da dipendono dal computer di destinazione. Per il simulatore quantistico full-state scrive nel file la funzione d'onda fino a una fase globale <xref:microsoft.quantum.diagnostics.dumpmachine>del sottosistema quantistico generato dai qubit forniti nello stesso formato di .  {1}Ad esempio, riprendere un computer con solo due qubit allocati e nello stato quantistico .{2}{00} {2} {10} ( ( ( . . . . . . . . . . . . . . . . . . .{1}. .{2}. .{0} . .{2} . .{1} {2}{0} <xref:microsoft.quantum.diagnostics.dumpregister> `qubit[0]` . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

e <xref:microsoft.quantum.diagnostics.dumpregister> la `qubit[1]` chiamata genera questo output:

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

In generale, lo stato di un registro che è impigliato con un altro registro è uno stato misto piuttosto che uno stato puro. In questo <xref:microsoft.quantum.diagnostics.dumpregister> caso, restituisce il seguente messaggio:

```
Qubits provided (0;) are entangled with some other qubit.
```

L'esempio seguente mostra come <xref:microsoft.quantum.diagnostics.dumpregister> è <xref:microsoft.quantum.diagnostics.dumpmachine> possibile usare entrambi e nel codice Q:

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

Oltre alle `Assert` `Dump` funzioni e alle operazioni, Qè supporta un sottoinsieme di funzionalità di debug standard di Visual Studio: [l'impostazione](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints)di punti di interruzione di riga, [l'esecuzione del codice tramite F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) e l'ispezione [dei valori delle variabili classiche](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) sono tutte possibili durante l'esecuzione del codice nel simulatore.

Il debug nel codice di Visual Studio sfrutta le funzionalità di debug fornite dall'estensione di codice di Visual Studio per Visual Studio basata su OmniSharp e richiede l'installazione della [versione più recente.](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) 
