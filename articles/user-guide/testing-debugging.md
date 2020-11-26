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
# <a name="testing-and-debugging"></a><span data-ttu-id="d4ff9-103">Test e debug</span><span class="sxs-lookup"><span data-stu-id="d4ff9-103">Testing and debugging</span></span>

<span data-ttu-id="d4ff9-104">Come per la programmazione classica, è essenziale poter controllare che i programmi Quantum funzionino come previsto e per poter diagnosticare un comportamento non corretto.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose incorrect behavior.</span></span>
<span data-ttu-id="d4ff9-105">Questa sezione include gli strumenti offerti da Q# per il test e il debug di programmi Quantum.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="d4ff9-106">Unit test</span><span class="sxs-lookup"><span data-stu-id="d4ff9-106">Unit Tests</span></span>

<span data-ttu-id="d4ff9-107">Un approccio comune al test dei programmi classici è quello di scrivere piccoli programmi denominati *unit test*, che eseguono codice in una libreria e confrontano l'output con un output previsto.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-107">One common approach to testing classical programs is to write small programs called *unit tests*, which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="d4ff9-108">Ad esempio, è possibile assicurarsi che venga `Square(2)` restituito `4` perché si conosce *un valore precedente a* $2 ^ 2 = $4.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-108">For example, you can ensure that `Square(2)` returns `4` since you know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="d4ff9-109">Q# supporta la creazione di unit test per i programmi Quantum e che può essere eseguito come test nel Framework di unit test di [xUnit](https://xunit.github.io/) .</span><span class="sxs-lookup"><span data-stu-id="d4ff9-109">Q# supports creating unit tests for quantum programs, and which can run as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="d4ff9-110">Creazione di un progetto di test</span><span class="sxs-lookup"><span data-stu-id="d4ff9-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="d4ff9-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="d4ff9-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="d4ff9-112">Aprire Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="d4ff9-113">Passare al menu **file** e selezionare **nuovo > progetto...**. Nell'angolo in alto a destra cercare `Q#` e selezionare il modello di **Q# progetto di test** .</span><span class="sxs-lookup"><span data-stu-id="d4ff9-113">Go to the **File** menu and select **New > Project...**. In the upper right corner, search for `Q#`, and select the **Q# Test Project** template.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="d4ff9-114">Riga di comando/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="d4ff9-114">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="d4ff9-115">Dalla riga di comando preferita, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="d4ff9-115">From your favorite command line, run the following command:</span></span>
```dotnetcli
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="d4ff9-116">Il nuovo progetto include un unico file `Tests.qs` , che offre una posizione pratica per definire nuovi Q# unit test.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-116">Your new project has a single file `Tests.qs`, which provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="d4ff9-117">Inizialmente, questo file contiene un unit test `AllocateQubit` di esempio che verifica che un qubit appena allocato si trovi nello {0} stato $ \ket $ e stampa un messaggio:</span><span class="sxs-lookup"><span data-stu-id="d4ff9-117">Initially, this file contains one sample unit test `AllocateQubit` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            AssertMeasurement([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

<span data-ttu-id="d4ff9-118">Qualsiasi Q# operazione o funzione che accetta un argomento di tipo `Unit` e restituisce `Unit` può essere contrassegnata come unit test tramite l' `@Test("...")` attributo.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-118">Any Q# operation or function that takes an argument of type `Unit` and returns `Unit` can be marked as a unit test via the `@Test("...")` attribute.</span></span> <span data-ttu-id="d4ff9-119">Nell'esempio precedente, l'argomento dell'attributo, `"QuantumSimulator"` , specifica la destinazione in cui viene eseguito il test.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-119">In the previous example, the argument to that attribute, `"QuantumSimulator"`, specifies the target on which the test runs.</span></span> <span data-ttu-id="d4ff9-120">Un singolo test può essere eseguito su più destinazioni.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-120">A single test can run on multiple targets.</span></span> <span data-ttu-id="d4ff9-121">Ad esempio, aggiungere un attributo `@Test("ResourcesEstimator")` prima di `AllocateQubit` .</span><span class="sxs-lookup"><span data-stu-id="d4ff9-121">For example, add an attribute `@Test("ResourcesEstimator")` before `AllocateQubit`.</span></span> 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
<span data-ttu-id="d4ff9-122">Salvare il file ed eseguire tutti i test.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-122">Save the file and run all tests.</span></span> <span data-ttu-id="d4ff9-123">A questo punto dovrebbero essere presenti due unit test, uno `AllocateQubit` in cui viene eseguito in `QuantumSimulator` e uno in cui viene eseguito in `ResourcesEstimator` .</span><span class="sxs-lookup"><span data-stu-id="d4ff9-123">There should now be two unit tests, one where `AllocateQubit` runs on the `QuantumSimulator`, and one where it runs in the `ResourcesEstimator`.</span></span> 

<span data-ttu-id="d4ff9-124">Il Q# compilatore riconosce le destinazioni predefinite `"QuantumSimulator"` , `"ToffoliSimulator"` , e `"ResourcesEstimator"` come destinazioni di esecuzione valide per gli unit test.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-124">The Q# compiler recognizes the built-in targets `"QuantumSimulator"`, `"ToffoliSimulator"`, and `"ResourcesEstimator"` as valid run targets for unit tests.</span></span> <span data-ttu-id="d4ff9-125">È anche possibile specificare un nome completo per definire una destinazione di esecuzione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-125">It is also possible to specify any fully qualified name to define a custom run target.</span></span> 

### <a name="running-no-locq-unit-tests"></a><span data-ttu-id="d4ff9-126">Esecuzione di Q# unit test</span><span class="sxs-lookup"><span data-stu-id="d4ff9-126">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="d4ff9-127">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="d4ff9-127">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="d4ff9-128">Per la configurazione unica per soluzione, passare al menu **test** e selezionare **impostazioni test > architettura del processore predefinita > x64**.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-128">As a one-time per-solution setup, go to the **Test** menu and select **Test Settings > Default Processor Architecture > X64**.</span></span>

> [!TIP]
> <span data-ttu-id="d4ff9-129">L'impostazione predefinita dell'architettura del processore per Visual Studio è archiviata nel file di opzioni soluzione ( `.suo` ) per ogni soluzione.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-129">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="d4ff9-130">Se si elimina questo file, è necessario selezionare **x64** come architettura del processore.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-130">If you delete this file, then you need to select **X64** as your processor architecture again.</span></span>

<span data-ttu-id="d4ff9-131">Compilare il progetto, aprire il menu **test** e selezionare **Windows > Esplora test**.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-131">Build the project, open the **Test** menu, and select **Windows > Test Explorer**.</span></span> <span data-ttu-id="d4ff9-132">**AllocateQubit** viene visualizzato nell'elenco dei test nel gruppo **test non eseguiti** .</span><span class="sxs-lookup"><span data-stu-id="d4ff9-132">**AllocateQubit** displays in the list of tests in the **Not Run Tests** group.</span></span> <span data-ttu-id="d4ff9-133">Selezionare **Esegui tutto** o eseguire questo test singolo.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-133">Select **Run All** or run this individual test.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="d4ff9-134">Riga di comando/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="d4ff9-134">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="d4ff9-135">Per eseguire i test, passare alla cartella del progetto (la cartella che contiene `Tests.csproj` ) ed eseguire il comando:</span><span class="sxs-lookup"><span data-stu-id="d4ff9-135">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and run the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="d4ff9-136">L'output dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="d4ff9-136">You should get output similar to the following:</span></span>

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

<span data-ttu-id="d4ff9-137">Gli unit test possono essere filtrati in base al nome o alla destinazione di esecuzione:</span><span class="sxs-lookup"><span data-stu-id="d4ff9-137">Unit tests can be filtered according to their name or the run target:</span></span>

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


<span data-ttu-id="d4ff9-138">\*\*_</span><span class="sxs-lookup"><span data-stu-id="d4ff9-138">\*\*_</span></span>

<span data-ttu-id="d4ff9-139">La funzione intrinseca <xref:Microsoft.Quantum.Intrinsic.Message> è `(String -> Unit)` di tipo e consente la creazione di messaggi di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-139">The intrinsic function <xref:Microsoft.Quantum.Intrinsic.Message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="d4ff9-140">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="d4ff9-140">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="d4ff9-141">Dopo aver eseguito un test in Esplora test e aver fatto clic sul test, viene visualizzato un pannello con le informazioni sull'esecuzione dei test: stato superato/non superato, tempo trascorso e collegamento all'output.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-141">After you run a test in Test Explorer and click on the test, a panel displays with information about test run: Pass/fail status, elapsed time, and a link to the output.</span></span> <span data-ttu-id="d4ff9-142">Fare clic su _ *output*\* per aprire l'output del test in una nuova finestra.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-142">Click _ *Output*\* to open the test output in a new window.</span></span>

![output del test](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="d4ff9-144">Riga di comando/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="d4ff9-144">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="d4ff9-145">Lo stato di superamento/errore per ogni test viene stampato nella console da `dotnet test` .</span><span class="sxs-lookup"><span data-stu-id="d4ff9-145">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="d4ff9-146">Per i test con esito negativo, anche gli output vengono stampati nella console per facilitare la diagnosi dell'errore.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-146">For failing tests, the outputs are also printed to the console to help diagnose the failure.</span></span>

<span data-ttu-id="d4ff9-147">\*\*_</span><span class="sxs-lookup"><span data-stu-id="d4ff9-147">\*\*_</span></span>

## <a name="facts-and-assertions"></a><span data-ttu-id="d4ff9-148">Fact e asserzioni</span><span class="sxs-lookup"><span data-stu-id="d4ff9-148">Facts and Assertions</span></span>

<span data-ttu-id="d4ff9-149">Poiché le funzioni in Q# non hanno effetti collaterali _logici_ , non è mai possibile osservare, dall'interno di un Q# programma, altri tipi di effetti dall'esecuzione di una funzione il cui tipo di output è la tupla vuota `()` .</span><span class="sxs-lookup"><span data-stu-id="d4ff9-149">Because functions in Q# have no _logical_ side effects, you can never observe, from within a Q# program, any other kinds of effects from running a function whose output type is the empty tuple `()`.</span></span>
<span data-ttu-id="d4ff9-150">In altre condizioni, un computer di destinazione può scegliere di non eseguire alcuna funzione che restituisce `()` con la garanzia che questa omissione non modificherà il comportamento di un codice di questo genere Q# .</span><span class="sxs-lookup"><span data-stu-id="d4ff9-150">That is, a target machine can choose not to run any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="d4ff9-151">Questo comportamento rende le funzioni `()` che restituiscono (ad esempio `Unit` ) uno strumento utile per incorporare le asserzioni e la logica di debug nei Q# programmi.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-151">This behavior makes functions returning `()` (such as `Unit`) a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

<span data-ttu-id="d4ff9-152">Si prenda in considerazione un semplice esempio:</span><span class="sxs-lookup"><span data-stu-id="d4ff9-152">Let's consider a simple example:</span></span>

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="d4ff9-153">In questo caso, la parola chiave `fail` indica che il calcolo non deve continuare e genera un'eccezione nel computer di destinazione che esegue il Q# programma.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-153">Here, the keyword `fail` indicates that the computation should not proceed, and raises an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="d4ff9-154">Per definizione, non è possibile osservare un errore di questo tipo in Q# , perché il computer di destinazione non esegue più il Q# codice dopo aver raggiunto un' `fail` istruzione.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-154">By definition, a failure of this kind cannot be observed from within Q#, as the target machine no longer runs the Q# code after reaching a `fail` statement.</span></span>
<span data-ttu-id="d4ff9-155">Quindi, se si procede con una chiamata a `PositivityFact` , è possibile garantire che l'input sia positivo.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-155">Thus, if we proceed past a call to `PositivityFact`, we can be assured that its input was positive.</span></span>

<span data-ttu-id="d4ff9-156">Si noti che è possibile implementare lo stesso comportamento dell' `PositivityFact` utilizzo della [`Fact`](xref:Microsoft.Quantum.Diagnostics.Fact) funzione dallo <xref:Microsoft.Quantum.Diagnostics> spazio dei nomi:</span><span class="sxs-lookup"><span data-stu-id="d4ff9-156">Note that we can implement the same behavior as `PositivityFact` using the [`Fact`](xref:Microsoft.Quantum.Diagnostics.Fact) function from the <xref:Microsoft.Quantum.Diagnostics> namespace:</span></span>

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

<span data-ttu-id="d4ff9-157">_Assertions \*, d'altra parte, vengono usati in modo analogo ai fatti, ma possono dipendere dallo stato del computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-157">_Assertions\*, on the other hand, are used similarly to facts but may depend on the state of the target machine.</span></span> <span data-ttu-id="d4ff9-158">In modo analogo, sono definite come operazioni, mentre i fact sono definiti come funzioni (come nell'esempio precedente).</span><span class="sxs-lookup"><span data-stu-id="d4ff9-158">Correspondingly, they are defined as operations, whereas facts are defined as functions (as in the previous example).</span></span>
<span data-ttu-id="d4ff9-159">Per comprendere la distinzione, prendere in considerazione il seguente utilizzo di un fact all'interno di un'asserzione:</span><span class="sxs-lookup"><span data-stu-id="d4ff9-159">To understand the distinction, consider the following use of a fact within an assertion:</span></span>

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

<span data-ttu-id="d4ff9-160">Qui viene utilizzata l'operazione <xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse> per restituire il numero di qubits disponibili per l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-160">Here, we are using the operation <xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse> to return the number of qubits available to use.</span></span>
<span data-ttu-id="d4ff9-161">Poiché dipende dallo stato globale del programma e dall'ambiente di esecuzione, anche la definizione di `AssertQubitsAreAvailable` deve essere un'operazione.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-161">As this depends on the global state of the program and its run environment, our definition of `AssertQubitsAreAvailable` must be an operation as well.</span></span>
<span data-ttu-id="d4ff9-162">Tuttavia, è possibile usare tale stato globale per produrre un `Bool` valore semplice come input per la `Fact` funzione.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-162">However, we can use that global state to yield a simple `Bool` value as input to the `Fact` function.</span></span>

<span data-ttu-id="d4ff9-163">[Il preludio](xref:microsoft.quantum.libraries.standard.prelude), che si basa su queste idee, offre due asserzioni particolarmente utili <xref:Microsoft.Quantum.Diagnostics.AssertMeasurement> ed <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> entrambe modellate come operazioni su `()` .</span><span class="sxs-lookup"><span data-stu-id="d4ff9-163">[The prelude](xref:microsoft.quantum.libraries.standard.prelude), building on these ideas, offers two especially useful assertions, <xref:Microsoft.Quantum.Diagnostics.AssertMeasurement> and <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> both modeled as operations onto `()`.</span></span> <span data-ttu-id="d4ff9-164">Ognuna di queste asserzioni accetta un operatore Pauli che descrive una particolare misurazione di interesse, un registro Quantum su cui viene eseguita una misura e un risultato ipotetico.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-164">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="d4ff9-165">I computer di destinazione che funzionano con la simulazione non sono associati [al teorema di clonazione](https://en.wikipedia.org/wiki/No-cloning_theorem)e possono eseguire tali misure senza compromettere il registro che passa a tali asserzioni.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-165">Target machines which work by simulation are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register that passes to such assertions.</span></span>
<span data-ttu-id="d4ff9-166">Un simulatore può quindi, analogamente alla `PositivityFact` funzione precedente, arrestare il calcolo se il risultato ipotetico non viene osservato in pratica:</span><span class="sxs-lookup"><span data-stu-id="d4ff9-166">A simulator can then, similar to the `PositivityFact` function previous, stop computation if the hypothetical outcome is not observed in practice:</span></span>

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

<span data-ttu-id="d4ff9-167">Su hardware quantum fisico, in cui il teorema di non clonazione impedisce l'esame di uno stato quantico, le `AssertMeasurement` `AssertMeasurementProbability` operazioni e restituiscono semplicemente `()` senza alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-167">On physical quantum hardware, where the no-cloning theorem prevents examination of a quantum state, the `AssertMeasurement` and `AssertMeasurementProbability` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="d4ff9-168">Lo <xref:Microsoft.Quantum.Diagnostics> spazio dei nomi fornisce diverse funzioni della `Assert` famiglia, con cui è possibile controllare condizioni più avanzate.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-168">The <xref:Microsoft.Quantum.Diagnostics> namespace provides several more functions of the `Assert` family, with which you can check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="d4ff9-169">Funzioni dump</span><span class="sxs-lookup"><span data-stu-id="d4ff9-169">Dump Functions</span></span>

<span data-ttu-id="d4ff9-170">Per semplificare la risoluzione dei problemi relativi ai programmi Quantum, lo <xref:Microsoft.Quantum.Diagnostics> spazio dei nomi offre due funzioni che consentono di eseguire il dump in un file dello stato corrente del computer di destinazione: <xref:Microsoft.Quantum.Diagnostics.DumpMachine> e <xref:Microsoft.Quantum.Diagnostics.DumpRegister> .</span><span class="sxs-lookup"><span data-stu-id="d4ff9-170">To help troubleshooting quantum programs, the <xref:Microsoft.Quantum.Diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:Microsoft.Quantum.Diagnostics.DumpMachine> and <xref:Microsoft.Quantum.Diagnostics.DumpRegister>.</span></span> <span data-ttu-id="d4ff9-171">L'output generato di ogni dipende dal computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-171">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="d4ff9-172">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="d4ff9-172">DumpMachine</span></span>

<span data-ttu-id="d4ff9-173">Il simulatore Quantum a stato intero distribuito come parte del quantum Development Kit scrive nel file la [funzione Wave](https://en.wikipedia.org/wiki/Wave_function) dell'intero sistema Quantum, come matrice unidimensionale di numeri complessi, in cui ogni elemento rappresenta l'ampiezza della probabilità di misurazione dello stato di base computazionale $ \ket{n} $, dove $ \ket{n} = \ket{b_ {n-1}... b_1b_0} $ per BITS $ \{ b_i \} $.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-173">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="d4ff9-174">Ad esempio, in un computer con solo due qubits allocati e nello stato quantico $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} , \end{align} $ $ Call <xref:Microsoft.Quantum.Diagnostics.DumpMachine> genera questo output:</span><span class="sxs-lookup"><span data-stu-id="d4ff9-174">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:Microsoft.Quantum.Diagnostics.DumpMachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="d4ff9-175">La prima riga fornisce un commento con gli ID dei qubits corrispondenti nell'ordine significativo.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-175">The first row provides a comment with the ids of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="d4ff9-176">Il resto delle righe descrive l'ampiezza di probabilità della misurazione del vettore di stato di base $ \ket{n} $ nei formati cartesiani e polari.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-176">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="d4ff9-177">In dettaglio per la prima riga:</span><span class="sxs-lookup"><span data-stu-id="d4ff9-177">In detail for the first row:</span></span>

* <span data-ttu-id="d4ff9-178">**`∣0❭:`** Questa riga corrisponde allo `0` stato di base di calcolo</span><span class="sxs-lookup"><span data-stu-id="d4ff9-178">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="d4ff9-179">**`0.707107 +  0.000000 i`**: ampiezza della probabilità in formato cartesiano.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-179">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="d4ff9-180">**` == `**: il `equal` segno separa entrambe le rappresentazioni equivalenti.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-180">**` == `**: the `equal` sign separates both equivalent representations.</span></span>
* <span data-ttu-id="d4ff9-181">**`**********  `**: Rappresentazione grafica della grandezza, il numero di `*` è proporzionale alla probabilità di misurare questo vettore di stato.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-181">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="d4ff9-182">**`[ 0.500000 ]`**: valore numerico della grandezza</span><span class="sxs-lookup"><span data-stu-id="d4ff9-182">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="d4ff9-183">**`    ---`**: Rappresentazione grafica della fase dell'ampiezza (vedere il seguente output).</span><span class="sxs-lookup"><span data-stu-id="d4ff9-183">**`    ---`**: A graphical representation of the amplitude's phase (see the following output).</span></span>
* <span data-ttu-id="d4ff9-184">**`[ 0.0000 rad ]`**: valore numerico della fase (in radianti).</span><span class="sxs-lookup"><span data-stu-id="d4ff9-184">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="d4ff9-185">Sia la grandezza che la fase vengono visualizzate con una rappresentazione grafica.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-185">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="d4ff9-186">La rappresentazione di magnitude è semplice: Mostra una barra di `*` , più grande è la probabilità maggiore sarà la barra.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-186">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="d4ff9-187">Per la fase vengono mostrati i simboli seguenti per rappresentare l'angolo in base agli intervalli:</span><span class="sxs-lookup"><span data-stu-id="d4ff9-187">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

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

<span data-ttu-id="d4ff9-188">Gli esempi seguenti illustrano `DumpMachine` alcuni stati comuni:</span><span class="sxs-lookup"><span data-stu-id="d4ff9-188">The following examples show `DumpMachine` for some common states:</span></span>

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
  > <span data-ttu-id="d4ff9-189">L'ID di un qubit viene assegnato in fase di esecuzione e non è necessariamente allineato con l'ordine in cui è stato allocato qubit o la relativa posizione all'interno di un registro qubit.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-189">The id of a qubit is assigned at runtime and is not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019"></a>[<span data-ttu-id="d4ff9-190">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="d4ff9-190">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="d4ff9-191">È possibile individuare un ID qubit in Visual Studio inserendo un punto di interruzione nel codice e controllando il valore di una variabile qubit, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d4ff9-191">You can locate a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![Mostra ID qubit in Visual Studio](~/media/qubit_id.png)
  >
  > <span data-ttu-id="d4ff9-193">qubit con index `0` on `register2` ha ID = `3` , qubit con index con `1` ID = `2` .</span><span class="sxs-lookup"><span data-stu-id="d4ff9-193">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="d4ff9-194">Riga di comando/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="d4ff9-194">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="d4ff9-195">È possibile individuare un ID qubit usando la <xref:Microsoft.Quantum.Intrinsic.Message> funzione e passando la variabile qubit nel messaggio, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d4ff9-195">You can locate a qubit id by using the <xref:Microsoft.Quantum.Intrinsic.Message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="d4ff9-196">che può generare questo output:</span><span class="sxs-lookup"><span data-stu-id="d4ff9-196">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="d4ff9-197">il che significa che qubit con index `0` on `register2` ha ID = `3` , qubit con index con `1` ID = `2` .</span><span class="sxs-lookup"><span data-stu-id="d4ff9-197">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


<span data-ttu-id="d4ff9-198">\*\*_</span><span class="sxs-lookup"><span data-stu-id="d4ff9-198">\*\*_</span></span>

<span data-ttu-id="d4ff9-199">Poiché <xref:Microsoft.Quantum.Diagnostics.DumpMachine> fa parte dello  <xref:Microsoft.Quantum.Diagnostics> spazio dei nomi, è necessario aggiungere un' `open` istruzione per accedervi:</span><span class="sxs-lookup"><span data-stu-id="d4ff9-199">Since <xref:Microsoft.Quantum.Diagnostics.DumpMachine> is part of the  <xref:Microsoft.Quantum.Diagnostics> namespace, you must add an `open` statement to access it:</span></span>

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


### <a name="dumpregister"></a><span data-ttu-id="d4ff9-200">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="d4ff9-200">DumpRegister</span></span>

<span data-ttu-id="d4ff9-201"><xref:Microsoft.Quantum.Diagnostics.DumpRegister> funziona come <xref:Microsoft.Quantum.Diagnostics.DumpMachine> , ad eccezione del fatto che accetta anche una matrice di qubits per limitare la quantità di informazioni solo a quella pertinente per il qubits corrispondente.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-201"><xref:Microsoft.Quantum.Diagnostics.DumpRegister> works like <xref:Microsoft.Quantum.Diagnostics.DumpMachine>, except that it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="d4ff9-202">Come per <xref:Microsoft.Quantum.Diagnostics.DumpMachine> , le informazioni generate da <xref:Microsoft.Quantum.Diagnostics.DumpRegister> dipendono dal computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-202">As with <xref:Microsoft.Quantum.Diagnostics.DumpMachine>, the information generated by <xref:Microsoft.Quantum.Diagnostics.DumpRegister> depends on the target machine.</span></span> <span data-ttu-id="d4ff9-203">Per il simulatore Quantum a stato completo scrive nel file la funzione Wave fino a una fase globale del sottosistema Quantum generato dal qubits specificato nello stesso formato di <xref:Microsoft.Quantum.Diagnostics.DumpMachine> .</span><span class="sxs-lookup"><span data-stu-id="d4ff9-203">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:Microsoft.Quantum.Diagnostics.DumpMachine>.</span></span>  <span data-ttu-id="d4ff9-204">Ad esempio, riportare un computer con solo due qubits allocati e nello stato quantico $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} =-e ^ {-i \ PI/4} ((\frac {1} {\sqrt {2} } \ket {0} -\frac{(1 + i)} {2} \ket {1} ) \otimes \frac{-(1 + i)} {\sqrt {2} } \ket {0} ), \end{align} $ $ Calling <xref:Microsoft.Quantum.Diagnostics.DumpRegister> per `qubit[0]` genera questo output:</span><span class="sxs-lookup"><span data-stu-id="d4ff9-204">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:Microsoft.Quantum.Diagnostics.DumpRegister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     _******************* [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="d4ff9-205">e <xref:Microsoft.Quantum.Diagnostics.DumpRegister> la chiamata a per `qubit[1]` genera questo output:</span><span class="sxs-lookup"><span data-stu-id="d4ff9-205">and calling <xref:Microsoft.Quantum.Diagnostics.DumpRegister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="d4ff9-206">In generale, lo stato di un registro con un altro registro è uno stato misto anziché uno stato puro.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-206">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="d4ff9-207">In questo caso, <xref:Microsoft.Quantum.Diagnostics.DumpRegister> restituisce il messaggio seguente:</span><span class="sxs-lookup"><span data-stu-id="d4ff9-207">In this case, <xref:Microsoft.Quantum.Diagnostics.DumpRegister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="d4ff9-208">Nell'esempio seguente viene illustrato come è possibile utilizzare sia <xref:Microsoft.Quantum.Diagnostics.DumpRegister> che <xref:Microsoft.Quantum.Diagnostics.DumpMachine> nel Q# codice:</span><span class="sxs-lookup"><span data-stu-id="d4ff9-208">The following example shows you how you can use both <xref:Microsoft.Quantum.Diagnostics.DumpRegister> and <xref:Microsoft.Quantum.Diagnostics.DumpMachine> in your Q# code:</span></span>

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

## <a name="debugging"></a><span data-ttu-id="d4ff9-209">Debug</span><span class="sxs-lookup"><span data-stu-id="d4ff9-209">Debugging</span></span>

<span data-ttu-id="d4ff9-210">Oltre alle `Assert` `Dump` funzioni e alle operazioni, Q# supporta un sottoinsieme di funzionalità di debug standard di Visual Studio: l'impostazione di punti di [interruzione di riga](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), l'esecuzione di [codice con F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)e il [controllo dei valori delle variabili classiche](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) sono tutti possibili quando si esegue il codice nel simulatore.</span><span class="sxs-lookup"><span data-stu-id="d4ff9-210">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger), and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible when running your code on the simulator.</span></span>

<span data-ttu-id="d4ff9-211">Il debug in Visual Studio Code sfrutta le funzionalità di debug fornite da C# per Visual Studio Code estensione con tecnologia OmniSharp e richiede l'installazione della [versione più recente](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span><span class="sxs-lookup"><span data-stu-id="d4ff9-211">Debugging in Visual Studio Code leverages the debugging capabilities provided by the C# for Visual Studio Code extension powered by OmniSharp and requires installing the [latest version](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span></span> 
