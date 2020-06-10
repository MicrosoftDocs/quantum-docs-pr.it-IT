---
title: Test e debug
description: Informazioni su come usare unit test, fact e asserzioni e funzioni dump per testare ed eseguire il debug di programmi Quantum.
author: tcNickolas
ms.author: mamykhai@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.guide.testingdebugging
ms.openlocfilehash: dd6c7ae8a016423f26c37f3eedf0ae9c1d126b78
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630037"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="09b05-103">Test e debug</span><span class="sxs-lookup"><span data-stu-id="09b05-103">Testing and debugging</span></span>

<span data-ttu-id="09b05-104">Come per la programmazione classica, è essenziale poter controllare che i programmi Quantum funzionino come previsto e per essere in grado di diagnosticare un programma quantum non corretto.</span><span class="sxs-lookup"><span data-stu-id="09b05-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose a quantum program that is incorrect.</span></span>
<span data-ttu-id="09b05-105">Questa sezione include gli strumenti offerti da Q # per il test e il debug di programmi Quantum.</span><span class="sxs-lookup"><span data-stu-id="09b05-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="09b05-106">Unit test</span><span class="sxs-lookup"><span data-stu-id="09b05-106">Unit Tests</span></span>

<span data-ttu-id="09b05-107">Un approccio comune al test dei programmi classici è quello di scrivere piccoli programmi denominati *unit test* che eseguono codice in una libreria e confrontano l'output con un output previsto.</span><span class="sxs-lookup"><span data-stu-id="09b05-107">One common approach to testing classical programs is to write small programs called *unit tests* which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="09b05-108">È ad esempio possibile che si desideri assicurarsi che venga `Square(2)` restituito `4` , dal momento che è noto *un valore precedente* a $2 ^ 2 = $4.</span><span class="sxs-lookup"><span data-stu-id="09b05-108">For instance, we may want to ensure that `Square(2)` returns `4`, since we know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="09b05-109">Q # supporta la creazione di unit test per i programmi Quantum e che può essere eseguito come test nel Framework di unit test di [xUnit](https://xunit.github.io/) .</span><span class="sxs-lookup"><span data-stu-id="09b05-109">Q# supports creating unit tests for quantum programs, and which can be executed as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="09b05-110">Creazione di un progetto di test</span><span class="sxs-lookup"><span data-stu-id="09b05-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="09b05-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="09b05-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="09b05-112">Aprire Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="09b05-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="09b05-113">Passare al `File` menu e selezionare `New`  >  `Project...` .</span><span class="sxs-lookup"><span data-stu-id="09b05-113">Go to the `File` menu and select `New` > `Project...`.</span></span>
<span data-ttu-id="09b05-114">Nell'angolo in alto a destra cercare `Q#` e selezionare il `Q# Test Project` modello.</span><span class="sxs-lookup"><span data-stu-id="09b05-114">In the upper right corner, search for `Q#`, and select the `Q# Test Project` template.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="09b05-115">Riga di comando/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="09b05-115">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="09b05-116">Dalla riga di comando preferita, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="09b05-116">From your favorite command line, run the following command:</span></span>
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="09b05-117">Il nuovo progetto avrà un unico file `Tests.qs` , che offre una posizione comoda per definire nuovi unit test Q #.</span><span class="sxs-lookup"><span data-stu-id="09b05-117">Your new project will have a single file `Tests.qs`, which provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="09b05-118">Inizialmente questo file contiene un unit test `AllocateQubit` di esempio che verifica che un qubit appena allocato si trovi nello {0} stato $ \ket $ e stampa un messaggio:</span><span class="sxs-lookup"><span data-stu-id="09b05-118">Initially this file contains one sample unit test `AllocateQubit` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            Assert([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

<span data-ttu-id="09b05-119">: New: qualsiasi funzione o operazione Q # che accetta un argomento di tipo `Unit` e restituisce `Unit` può essere contrassegnata come unit test tramite l' `@Test("...")` attributo.</span><span class="sxs-lookup"><span data-stu-id="09b05-119">:new: Any Q# operation or function that takes an argument of type `Unit` and returns `Unit` can be marked as a unit test via the `@Test("...")` attribute.</span></span> <span data-ttu-id="09b05-120">L'argomento dell'attributo `"QuantumSimulator"` precedente specifica la destinazione in cui viene eseguito il test.</span><span class="sxs-lookup"><span data-stu-id="09b05-120">The argument to that attribute, `"QuantumSimulator"` above, specifies the target on which the test is executed.</span></span> <span data-ttu-id="09b05-121">Un singolo test può essere eseguito su più destinazioni.</span><span class="sxs-lookup"><span data-stu-id="09b05-121">A single test can be executed on multiple targets.</span></span> <span data-ttu-id="09b05-122">Ad esempio, aggiungere un attributo `@Test("ResourcesEstimator")` sopra `AllocateQubit` .</span><span class="sxs-lookup"><span data-stu-id="09b05-122">For example, add an attribute `@Test("ResourcesEstimator")` above `AllocateQubit`.</span></span> 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
<span data-ttu-id="09b05-123">Salvare il file ed eseguire tutti i test.</span><span class="sxs-lookup"><span data-stu-id="09b05-123">Save the file and execute all tests.</span></span> <span data-ttu-id="09b05-124">A questo punto dovrebbero essere presenti due unit test, uno in cui AllocateQubit viene eseguito in QuantumSimulator e uno in cui viene eseguito nel ResourceEstimator.</span><span class="sxs-lookup"><span data-stu-id="09b05-124">There should now be two unit tests, one where AllocateQubit is executed on the QuantumSimulator, and one where it is executed in the ResourceEstimator.</span></span> 

<span data-ttu-id="09b05-125">Il compilatore Q # riconosce le destinazioni predefinite "QuantumSimulator", "ToffoliSimulator" e "ResourcesEstimator" come destinazioni di esecuzione valide per gli unit test.</span><span class="sxs-lookup"><span data-stu-id="09b05-125">The Q# compiler recognizes the built-in targets "QuantumSimulator", "ToffoliSimulator", and "ResourcesEstimator" as valid execution targets for unit tests.</span></span> <span data-ttu-id="09b05-126">È anche possibile specificare un nome completo per definire una destinazione di esecuzione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="09b05-126">It is also possible to specify any fully qualified name to define a custom execution target.</span></span> 

### <a name="running-q-unit-tests"></a><span data-ttu-id="09b05-127">Esecuzione di unit test Q #</span><span class="sxs-lookup"><span data-stu-id="09b05-127">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="09b05-128">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="09b05-128">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="09b05-129">Per la configurazione unica per soluzione, passare a `Test` menu e selezionare `Test Settings`  >  `Default Processor Architecture`  >  `X64` .</span><span class="sxs-lookup"><span data-stu-id="09b05-129">As a one-time per-solution setup, go to `Test` menu and select `Test Settings` > `Default Processor Architecture` > `X64`.</span></span>

> [!TIP]
> <span data-ttu-id="09b05-130">L'impostazione predefinita dell'architettura del processore per Visual Studio è archiviata nel file di opzioni soluzione ( `.suo` ) per ogni soluzione.</span><span class="sxs-lookup"><span data-stu-id="09b05-130">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="09b05-131">Se si elimina questo file, sarà necessario selezionare `X64` nuovamente come architettura del processore.</span><span class="sxs-lookup"><span data-stu-id="09b05-131">If you delete this file, then you will need to select `X64` as your processor architecture again.</span></span>

<span data-ttu-id="09b05-132">Compilare il progetto, andare al `Test` menu e selezionare `Windows`  >  `Test Explorer` .</span><span class="sxs-lookup"><span data-stu-id="09b05-132">Build the project, go to the `Test` menu and select `Windows` > `Test Explorer`.</span></span> <span data-ttu-id="09b05-133">`AllocateQubit`viene visualizzato nell'elenco dei test del `Not Run Tests` gruppo.</span><span class="sxs-lookup"><span data-stu-id="09b05-133">`AllocateQubit` will show up in the list of tests in the `Not Run Tests` group.</span></span> <span data-ttu-id="09b05-134">Selezionare `Run All` o eseguire questo test singolo e dovrebbe essere superato.</span><span class="sxs-lookup"><span data-stu-id="09b05-134">Select `Run All` or run this individual test, and it should pass!</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="09b05-135">Riga di comando/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="09b05-135">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="09b05-136">Per eseguire i test, passare alla cartella del progetto (la cartella che contiene `Tests.csproj` ) ed eseguire il comando:</span><span class="sxs-lookup"><span data-stu-id="09b05-136">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and execute the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="09b05-137">L'output dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="09b05-137">You should get output similar to the following:</span></span>

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

<span data-ttu-id="09b05-138">Gli unit test possono essere filtrati in base al nome e/o alla destinazione di esecuzione:</span><span class="sxs-lookup"><span data-stu-id="09b05-138">Unit tests can be filtered according to their name and/or the execution target:</span></span>

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

<span data-ttu-id="09b05-139">La funzione intrinseca <xref:microsoft.quantum.intrinsic.message> è `(String -> Unit)` di tipo e consente la creazione di messaggi di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="09b05-139">The intrinsic function <xref:microsoft.quantum.intrinsic.message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="09b05-140">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="09b05-140">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="09b05-141">Dopo aver eseguito un test in Esplora test e aver fatto clic sul test, verrà visualizzato un pannello con le informazioni sull'esecuzione dei test: stato superato/non riuscito, tempo trascorso e collegamento "output".</span><span class="sxs-lookup"><span data-stu-id="09b05-141">After you execute a test in Test Explorer and click on the test, a panel will appear with information about test execution: Passed/Failed status, elapsed time and an "Output" link.</span></span> <span data-ttu-id="09b05-142">Se si fa clic sul collegamento "output", l'output del test viene aperto in una nuova finestra.</span><span class="sxs-lookup"><span data-stu-id="09b05-142">If you click the "Output" link, test output will open in a new window.</span></span>

![output del test](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="09b05-144">Riga di comando/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="09b05-144">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="09b05-145">Lo stato di superamento/errore per ogni test viene stampato nella console da `dotnet test` .</span><span class="sxs-lookup"><span data-stu-id="09b05-145">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="09b05-146">Per i test con esito negativo, anche gli output vengono stampati nella console per facilitare la diagnosi dell'errore.</span><span class="sxs-lookup"><span data-stu-id="09b05-146">For failing tests, the outputs are also printed to the console to help diagnose the failure.</span></span>

***

## <a name="facts-and-assertions"></a><span data-ttu-id="09b05-147">Fact e asserzioni</span><span class="sxs-lookup"><span data-stu-id="09b05-147">Facts and Assertions</span></span>

<span data-ttu-id="09b05-148">Poiché le funzioni in Q # non hanno effetti collaterali _logici_ , qualsiasi _altro tipo_ di effetto dell'esecuzione di una funzione il cui tipo di output è la tupla vuota `()` non può mai essere osservato dall'interno di un programma Q #.</span><span class="sxs-lookup"><span data-stu-id="09b05-148">Because functions in Q# have no _logical_ side effects, any _other kinds_ of effects of executing a function whose output type is the empty tuple `()` can never be observed from within a Q# program.</span></span>
<span data-ttu-id="09b05-149">In altre condizioni, un computer di destinazione può scegliere di non eseguire alcuna funzione che restituisce `()` con la garanzia che questa omissione non modificherà il comportamento di un codice Q # seguente.</span><span class="sxs-lookup"><span data-stu-id="09b05-149">That is, a target machine can choose not to execute any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="09b05-150">Questo rende le funzioni `()` che restituiscono (ad esempio `Unit` ) uno strumento utile per incorporare le asserzioni e la logica di debug nei programmi Q #.</span><span class="sxs-lookup"><span data-stu-id="09b05-150">This makes functions returning `()` (i.e. `Unit`) a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

<span data-ttu-id="09b05-151">Si prenda in considerazione un semplice esempio:</span><span class="sxs-lookup"><span data-stu-id="09b05-151">Let's consider a simple example:</span></span>

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="09b05-152">In questo caso, la parola chiave `fail` indica che il calcolo non deve continuare, generando un'eccezione nel computer di destinazione che esegue il programma Q #.</span><span class="sxs-lookup"><span data-stu-id="09b05-152">Here, the keyword `fail` indicates that the computation should not proceed, raising an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="09b05-153">Per definizione, non è possibile osservare un errore di questo tipo da Q #, in quanto non viene eseguito alcun ulteriore codice Q # dopo il `fail` raggiungimento di un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="09b05-153">By definition, a failure of this kind cannot be observed from within Q#, as no further Q# code is run after a `fail` statement is reached.</span></span>
<span data-ttu-id="09b05-154">Quindi, se si procede con una chiamata a `PositivityFact` , è possibile garantire che l'input sia positivo.</span><span class="sxs-lookup"><span data-stu-id="09b05-154">Thus, if we proceed past a call to `PositivityFact`, we can be assured by that its input was positive.</span></span>

<span data-ttu-id="09b05-155">Si noti che è possibile implementare lo stesso comportamento dell' `PositivityFact` utilizzo della [`Fact`](xref:microsoft.quantum.diagnostics.fact) funzione dallo <xref:microsoft.quantum.diagnostics> spazio dei nomi:</span><span class="sxs-lookup"><span data-stu-id="09b05-155">Note that we can implement the same behavior as `PositivityFact` using the [`Fact`](xref:microsoft.quantum.diagnostics.fact) function from the <xref:microsoft.quantum.diagnostics> namespace:</span></span>

```qsharp
    Fact(value <= 0, "Expected a positive number.");
```

<span data-ttu-id="09b05-156">Le *asserzioni*, d'altra parte, vengono usate in modo analogo ai fact, ma possono dipendere dallo stato del computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="09b05-156">*Assertions*, on the other hand, are used similarly to facts, but may be dependent on the state of the target machine.</span></span> <span data-ttu-id="09b05-157">In modo analogo, sono definite come operazioni, mentre i fact sono definiti come funzioni (come sopra).</span><span class="sxs-lookup"><span data-stu-id="09b05-157">Correspondingly, they are defined as operations, whereas facts are defined as functions (as above).</span></span>
<span data-ttu-id="09b05-158">Per comprendere la distinzione, prendere in considerazione il seguente utilizzo di un fact all'interno di un'asserzione:</span><span class="sxs-lookup"><span data-stu-id="09b05-158">To understand the distinction, consider the following use of a fact within an assertion:</span></span>

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

<span data-ttu-id="09b05-159">Qui viene utilizzata l'operazione <xref:microsoft.quantum.environment.getqubitsavailabletouse> per restituire il numero di qubits disponibili per l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="09b05-159">Here, we are using the operation <xref:microsoft.quantum.environment.getqubitsavailabletouse> to return the number of qubits available to use.</span></span>
<span data-ttu-id="09b05-160">Poiché questo dipende chiaramente dallo stato globale del programma e dall'ambiente di esecuzione, anche la definizione di `AssertQubitsAreAvailable` deve essere un'operazione.</span><span class="sxs-lookup"><span data-stu-id="09b05-160">As this clearly depends on the global state of the program and its execution environment, our definition of  `AssertQubitsAreAvailable` must be an operation as well.</span></span>
<span data-ttu-id="09b05-161">Tuttavia, è possibile usare tale stato globale per produrre un `Bool` valore semplice come input per la `Fact` funzione.</span><span class="sxs-lookup"><span data-stu-id="09b05-161">However, we can use that global state to yield a simple `Bool` value as input to the `Fact` function.</span></span>

<span data-ttu-id="09b05-162">Basandosi su queste idee, [il preludio](xref:microsoft.quantum.libraries.standard.prelude) offre due asserzioni particolarmente <xref:microsoft.quantum.intrinsic.assert> utili <xref:microsoft.quantum.intrinsic.assertprob> ed entrambe modellate come operazioni su `()` .</span><span class="sxs-lookup"><span data-stu-id="09b05-162">Building on these ideas, [the prelude](xref:microsoft.quantum.libraries.standard.prelude) offers two especially useful assertions, <xref:microsoft.quantum.intrinsic.assert> and <xref:microsoft.quantum.intrinsic.assertprob> both modeled as operations onto `()`.</span></span> <span data-ttu-id="09b05-163">Ognuna di queste asserzioni accetta un operatore Pauli che descrive una particolare misurazione di interesse, un registro Quantum su cui deve essere eseguita una misurazione e un risultato ipotetico.</span><span class="sxs-lookup"><span data-stu-id="09b05-163">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is to be performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="09b05-164">Nei computer di destinazione che operano per simulazione, [il teorema di non clonazione](https://en.wikipedia.org/wiki/No-cloning_theorem)non è vincolato e può eseguire tali misure senza compromettere il registro passato a tali asserzioni.</span><span class="sxs-lookup"><span data-stu-id="09b05-164">On target machines which work by simulation, we are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register passed to such assertions.</span></span>
<span data-ttu-id="09b05-165">Un simulatore può quindi, analogamente alla `PositivityFact` funzione precedente, interrompere il calcolo se il risultato ipotetico non viene osservato in pratica:</span><span class="sxs-lookup"><span data-stu-id="09b05-165">A simulator can then, similar to the `PositivityFact` function above, abort computation if the hypothetical outcome would not be observed in practice:</span></span>

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

<span data-ttu-id="09b05-166">Su hardware quantum fisico, in cui il teorema di non clonazione impedisce l'analisi dello stato del quantum, le `Assert` `AssertProb` operazioni e restituiscono semplicemente `()` senza alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="09b05-166">On physical quantum hardware, where the no-cloning theorem prevents examination of quantum state, the `Assert` and `AssertProb` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="09b05-167">Lo <xref:microsoft.quantum.diagnostics> spazio dei nomi fornisce diverse funzioni della `Assert` famiglia che consentono di controllare le condizioni più avanzate.</span><span class="sxs-lookup"><span data-stu-id="09b05-167">The <xref:microsoft.quantum.diagnostics> namespace provides several more functions of the `Assert` family which allow us to check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="09b05-168">Funzioni dump</span><span class="sxs-lookup"><span data-stu-id="09b05-168">Dump Functions</span></span>

<span data-ttu-id="09b05-169">Per semplificare la risoluzione dei problemi relativi ai programmi Quantum, lo <xref:microsoft.quantum.diagnostics> spazio dei nomi offre due funzioni che consentono di eseguire il dump in un file dello stato corrente del computer di destinazione: <xref:microsoft.quantum.diagnostics.dumpmachine> e <xref:microsoft.quantum.diagnostics.dumpregister> .</span><span class="sxs-lookup"><span data-stu-id="09b05-169">To help troubleshooting quantum programs, the <xref:microsoft.quantum.diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister>.</span></span> <span data-ttu-id="09b05-170">L'output generato di ogni dipende dal computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="09b05-170">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="09b05-171">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="09b05-171">DumpMachine</span></span>

<span data-ttu-id="09b05-172">Il simulatore Quantum a stato intero distribuito come parte del quantum Development Kit scrive nel file la [funzione Wave](https://en.wikipedia.org/wiki/Wave_function) dell'intero sistema Quantum, come matrice unidimensionale di numeri complessi, in cui ogni elemento rappresenta l'ampiezza della probabilità di misurazione dello stato di base computazionale $ \ket{n} $, dove $ \ket{n} = \ket{b_ {n-1}... b_1b_0} $ per BITS $ \{ b_i \} $.</span><span class="sxs-lookup"><span data-stu-id="09b05-172">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="09b05-173">Ad esempio, in un computer con solo due qubits allocati e nello stato quantico $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} , \end{align} $ $ Call <xref:microsoft.quantum.diagnostics.dumpmachine> genera questo output:</span><span class="sxs-lookup"><span data-stu-id="09b05-173">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="09b05-174">La prima riga fornisce un commento con gli ID dei qubits corrispondenti nell'ordine significativo.</span><span class="sxs-lookup"><span data-stu-id="09b05-174">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="09b05-175">Il resto delle righe descrive l'ampiezza di probabilità della misurazione del vettore di stato di base $ \ket{n} $ nei formati cartesiani e polari.</span><span class="sxs-lookup"><span data-stu-id="09b05-175">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="09b05-176">In dettaglio per la prima riga:</span><span class="sxs-lookup"><span data-stu-id="09b05-176">In detail for the first row:</span></span>

* <span data-ttu-id="09b05-177">**`∣0❭:`** Questa riga corrisponde allo `0` stato di base di calcolo</span><span class="sxs-lookup"><span data-stu-id="09b05-177">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="09b05-178">**`0.707107 +  0.000000 i`**: ampiezza della probabilità in formato cartesiano.</span><span class="sxs-lookup"><span data-stu-id="09b05-178">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="09b05-179">**` == `**: il `equal` segno separa entrambe le rappresentazioni equivalenti.</span><span class="sxs-lookup"><span data-stu-id="09b05-179">**` == `**: the `equal` sign separates both equivalent representations.</span></span>
* <span data-ttu-id="09b05-180">**`**********  `**: Rappresentazione grafica della grandezza, il numero di `*` è proporzionale alla probabilità di misurare questo vettore di stato.</span><span class="sxs-lookup"><span data-stu-id="09b05-180">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="09b05-181">**`[ 0.500000 ]`**: valore numerico della grandezza</span><span class="sxs-lookup"><span data-stu-id="09b05-181">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="09b05-182">**`    ---`**: Rappresentazione grafica della fase dell'ampiezza (vedere di seguito).</span><span class="sxs-lookup"><span data-stu-id="09b05-182">**`    ---`**: A graphical representation of the amplitude's phase (see below).</span></span>
* <span data-ttu-id="09b05-183">**`[ 0.0000 rad ]`**: valore numerico della fase (in radianti).</span><span class="sxs-lookup"><span data-stu-id="09b05-183">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="09b05-184">Sia la grandezza che la fase vengono visualizzate con una rappresentazione grafica.</span><span class="sxs-lookup"><span data-stu-id="09b05-184">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="09b05-185">La rappresentazione di magnitude è semplice: Mostra una barra di `*` , più grande è la probabilità maggiore sarà la barra.</span><span class="sxs-lookup"><span data-stu-id="09b05-185">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="09b05-186">Per la fase vengono mostrati i simboli seguenti per rappresentare l'angolo in base agli intervalli:</span><span class="sxs-lookup"><span data-stu-id="09b05-186">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

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

<span data-ttu-id="09b05-187">Gli esempi seguenti illustrano `DumpMachine` alcuni stati comuni:</span><span class="sxs-lookup"><span data-stu-id="09b05-187">The following examples show `DumpMachine` for some common states:</span></span>

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
  > <span data-ttu-id="09b05-188">L'ID di un qubit viene assegnato in fase di esecuzione e non è necessariamente allineato con l'ordine in cui è stato allocato qubit o la relativa posizione all'interno di un registro qubit.</span><span class="sxs-lookup"><span data-stu-id="09b05-188">The id of a qubit is assigned at runtime and it's not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019"></a>[<span data-ttu-id="09b05-189">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="09b05-189">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="09b05-190">È possibile individuare un ID qubit in Visual Studio inserendo un punto di interruzione nel codice e controllando il valore di una variabile qubit, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="09b05-190">You can figure out a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![Mostra ID qubit in Visual Studio](~/media/qubit_id.png)
  >
  > <span data-ttu-id="09b05-192">qubit con index `0` on `register2` ha ID = `3` , qubit con index con `1` ID = `2` .</span><span class="sxs-lookup"><span data-stu-id="09b05-192">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="09b05-193">Riga di comando/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="09b05-193">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="09b05-194">È possibile individuare un ID qubit usando la <xref:microsoft.quantum.intrinsic.message> funzione e passando la variabile qubit nel messaggio, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="09b05-194">You can figure out a qubit id by using the <xref:microsoft.quantum.intrinsic.message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="09b05-195">che può generare questo output:</span><span class="sxs-lookup"><span data-stu-id="09b05-195">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="09b05-196">il che significa che qubit con index `0` on `register2` ha ID = `3` , qubit con index con `1` ID = `2` .</span><span class="sxs-lookup"><span data-stu-id="09b05-196">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


***

<span data-ttu-id="09b05-197"><xref:microsoft.quantum.diagnostics.dumpmachine>fa parte dello <xref:microsoft.quantum.diagnostics> spazio dei nomi, quindi, per utilizzarlo, è necessario aggiungere un' `open` istruzione:</span><span class="sxs-lookup"><span data-stu-id="09b05-197"><xref:microsoft.quantum.diagnostics.dumpmachine> is part of the  <xref:microsoft.quantum.diagnostics> namespace, so in order to use it you must add an `open` statement:</span></span>

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


### <a name="dumpregister"></a><span data-ttu-id="09b05-198">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="09b05-198">DumpRegister</span></span>

<span data-ttu-id="09b05-199"><xref:microsoft.quantum.diagnostics.dumpregister>funziona come <xref:microsoft.quantum.diagnostics.dumpmachine> , ad eccezione del fatto che accetta anche una matrice di qubits per limitare la quantità di informazioni solo a quella pertinente per il qubits corrispondente.</span><span class="sxs-lookup"><span data-stu-id="09b05-199"><xref:microsoft.quantum.diagnostics.dumpregister> works like <xref:microsoft.quantum.diagnostics.dumpmachine>, except it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="09b05-200">Come per <xref:microsoft.quantum.diagnostics.dumpmachine> , le informazioni generate da <xref:microsoft.quantum.diagnostics.dumpregister> dipendono dal computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="09b05-200">As with <xref:microsoft.quantum.diagnostics.dumpmachine>, the information generated by <xref:microsoft.quantum.diagnostics.dumpregister> depends on the target machine.</span></span> <span data-ttu-id="09b05-201">Per il simulatore Quantum a stato completo scrive nel file la funzione Wave fino a una fase globale del sottosistema Quantum generato dal qubits specificato nello stesso formato di <xref:microsoft.quantum.diagnostics.dumpmachine> .</span><span class="sxs-lookup"><span data-stu-id="09b05-201">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:microsoft.quantum.diagnostics.dumpmachine>.</span></span>  <span data-ttu-id="09b05-202">Ad esempio, riportare un computer con solo due qubits allocati e nello stato quantico $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} =-e ^ {-i \ PI/4} ((\frac {1} {\sqrt {2} } \ket {0} -\frac{(1 + i)} {2} \ket {1} ) \otimes \frac{-(1 + i)} {\sqrt {2} } \ket {0} ), \end{align} $ $ Calling <xref:microsoft.quantum.diagnostics.dumpregister> per `qubit[0]` genera questo output:</span><span class="sxs-lookup"><span data-stu-id="09b05-202">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="09b05-203">e <xref:microsoft.quantum.diagnostics.dumpregister> la chiamata a per `qubit[1]` genera questo output:</span><span class="sxs-lookup"><span data-stu-id="09b05-203">and calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="09b05-204">In generale, lo stato di un registro con un altro registro è uno stato misto anziché uno stato puro.</span><span class="sxs-lookup"><span data-stu-id="09b05-204">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="09b05-205">In questo caso, <xref:microsoft.quantum.diagnostics.dumpregister> restituisce il messaggio seguente:</span><span class="sxs-lookup"><span data-stu-id="09b05-205">In this case, <xref:microsoft.quantum.diagnostics.dumpregister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="09b05-206">Nell'esempio seguente viene illustrato come è possibile utilizzare sia <xref:microsoft.quantum.diagnostics.dumpregister> che <xref:microsoft.quantum.diagnostics.dumpmachine> nel codice Q #:</span><span class="sxs-lookup"><span data-stu-id="09b05-206">The following example shows you how you can use both <xref:microsoft.quantum.diagnostics.dumpregister> and <xref:microsoft.quantum.diagnostics.dumpmachine> in your Q# code:</span></span>

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

## <a name="debugging"></a><span data-ttu-id="09b05-207">Debug</span><span class="sxs-lookup"><span data-stu-id="09b05-207">Debugging</span></span>

<span data-ttu-id="09b05-208">Oltre alle funzioni e alle `Assert` `Dump` operazioni, Q # supporta un sottoinsieme di funzionalità di debug standard di Visual Studio: l'impostazione dei punti di [interruzione di riga](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), l'esecuzione del [codice istruzione per istruzione con F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) e il [controllo dei valori delle variabili classiche](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) sono tutte possibili durante l'esecuzione del codice sul simulatore.</span><span class="sxs-lookup"><span data-stu-id="09b05-208">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible during code execution on the simulator.</span></span>

<span data-ttu-id="09b05-209">Il debug in Visual Studio Code sfrutta le funzionalità di debug fornite da C# per Visual Studio Code estensione con tecnologia OmniSharp e richiede l'installazione della [versione più recente](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span><span class="sxs-lookup"><span data-stu-id="09b05-209">Debugging in Visual Studio Code leverages the debugging capabilities provided by the C# for Visual Studio Code extension powered by OmniSharp and requires installing the [latest version](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span></span> 
