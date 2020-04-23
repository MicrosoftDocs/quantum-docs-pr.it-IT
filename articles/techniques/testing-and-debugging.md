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
# <a name="testing-and-debugging"></a><span data-ttu-id="4eadb-103">Test e debug</span><span class="sxs-lookup"><span data-stu-id="4eadb-103">Testing and Debugging</span></span>

<span data-ttu-id="4eadb-104">Come per la programmazione classica, è essenziale essere in grado di verificare che i programmi quantistici agiscano come previsto, e di essere in grado di diagnosticare un programma quantistico che non è corretto.</span><span class="sxs-lookup"><span data-stu-id="4eadb-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose a quantum program that is incorrect.</span></span>
<span data-ttu-id="4eadb-105">In questa sezione vengono illustrati gli strumenti offerti da Q per il test e il debug di programmi quantistici.</span><span class="sxs-lookup"><span data-stu-id="4eadb-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="4eadb-106">Unit test</span><span class="sxs-lookup"><span data-stu-id="4eadb-106">Unit Tests</span></span>

<span data-ttu-id="4eadb-107">Un approccio comune per testare i programmi classici consiste nello scrivere programmi di piccole dimensioni denominati *unit test* che eseguono codice in una libreria e ne confrontano l'output con un output previsto.</span><span class="sxs-lookup"><span data-stu-id="4eadb-107">One common approach to testing classical programs is to write small programs called *unit tests* which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="4eadb-108">Ad esempio, potremmo voler `Square(2)` garantire `4`che restituisca , dato che sappiamo *a priori* che .</span><span class="sxs-lookup"><span data-stu-id="4eadb-108">For instance, we may want to ensure that `Square(2)` returns `4`, since we know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="4eadb-109">Il sistema Q è supporta la creazione di unit test per programmi quantistici e che possono essere eseguiti come test all'interno del framework di unit test [xUnit.](https://xunit.github.io/)</span><span class="sxs-lookup"><span data-stu-id="4eadb-109">Q# supports creating unit tests for quantum programs, and which can be executed as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="4eadb-110">Creazione di un progetto di testCreating a Test Project</span><span class="sxs-lookup"><span data-stu-id="4eadb-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="4eadb-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="4eadb-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="4eadb-112">Aprire Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="4eadb-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="4eadb-113">Vai al `File` menu `New`  >  `Project...`e seleziona .</span><span class="sxs-lookup"><span data-stu-id="4eadb-113">Go to the `File` menu and select `New` > `Project...`.</span></span>
<span data-ttu-id="4eadb-114">Nell'angolo superiore destro `Q#`cercare e `Q# Test Project` selezionare il modello.</span><span class="sxs-lookup"><span data-stu-id="4eadb-114">In the upper right corner, search for `Q#`, and select the `Q# Test Project` template.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="4eadb-115">Riga di comando/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="4eadb-115">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="4eadb-116">Dalla riga di comando preferita, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="4eadb-116">From your favorite command line, run the following command:</span></span>
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="4eadb-117">Il nuovo progetto disporrà di un singolo file, `Tests.qs`che offre una comoda posizione per definire i nuovi unit test di Q.</span><span class="sxs-lookup"><span data-stu-id="4eadb-117">Your new project will have a single file `Tests.qs`, which provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="4eadb-118">Inizialmente questo file contiene `AllocateQubit` uno unit test di esempio che controlla che{0}un qubit appena allocato si trova nello stato di errore e stampa un messaggio:</span><span class="sxs-lookup"><span data-stu-id="4eadb-118">Initially this file contains one sample unit test `AllocateQubit` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            Assert([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

:new: <span data-ttu-id="4eadb-119">qualsiasi operazione o funzione di Q `Unit` che `Unit` accetta un argomento di `@Test("...")` tipo e restituisce può essere contrassegnata come unit test tramite l'attributo .</span><span class="sxs-lookup"><span data-stu-id="4eadb-119">Any Q# operation or function that takes an argument of type `Unit` and returns `Unit` can be marked as a unit test via the `@Test("...")` attribute.</span></span> <span data-ttu-id="4eadb-120">L'argomento di `"QuantumSimulator"` tale attributo, precedente, specifica la destinazione su cui viene eseguito il test.</span><span class="sxs-lookup"><span data-stu-id="4eadb-120">The argument to that attribute, `"QuantumSimulator"` above, specifies the target on which the test is executed.</span></span> <span data-ttu-id="4eadb-121">Un singolo test può essere eseguito su più destinazioni.</span><span class="sxs-lookup"><span data-stu-id="4eadb-121">A single test can be executed on multiple targets.</span></span> <span data-ttu-id="4eadb-122">Ad esempio, aggiungere `@Test("ResourcesEstimator")` `AllocateQubit`un attributo sopra .</span><span class="sxs-lookup"><span data-stu-id="4eadb-122">For example, add an attribute `@Test("ResourcesEstimator")` above `AllocateQubit`.</span></span> 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
<span data-ttu-id="4eadb-123">Salvare il file ed eseguire tutti i test.</span><span class="sxs-lookup"><span data-stu-id="4eadb-123">Save the file and execute all tests.</span></span> <span data-ttu-id="4eadb-124">Dovrebbero essere presenti due unit test, uno in cui AllocateQubit viene eseguito su QuantumSimulator e uno in cui viene eseguito nel ResourceEstimator.</span><span class="sxs-lookup"><span data-stu-id="4eadb-124">There should now be two unit tests, one where AllocateQubit is executed on the QuantumSimulator, and one where it is executed in the ResourceEstimator.</span></span> 

<span data-ttu-id="4eadb-125">Il compilatore Q, riconosce le destinazioni predefinite "QuantumSimulator", "ToffoliSimulator" e "ResourcesEstimator" come destinazioni di esecuzione valide per gli unit test.</span><span class="sxs-lookup"><span data-stu-id="4eadb-125">The Q# compiler recognizes the built-in targets "QuantumSimulator", "ToffoliSimulator", and "ResourcesEstimator" as valid execution targets for unit tests.</span></span> <span data-ttu-id="4eadb-126">È inoltre possibile specificare qualsiasi nome completo per definire una destinazione di esecuzione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="4eadb-126">It is also possible to specify any fully qualified name to define a custom execution target.</span></span> 

### <a name="running-q-unit-tests"></a><span data-ttu-id="4eadb-127">Esecuzione di unit test Q</span><span class="sxs-lookup"><span data-stu-id="4eadb-127">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="4eadb-128">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="4eadb-128">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="4eadb-129">Come configurazione una tantera per `Test` soluzione, `Test Settings`  >  `Default Processor Architecture`  > passare al menu e selezionare `X64`.</span><span class="sxs-lookup"><span data-stu-id="4eadb-129">As a one-time per-solution setup, go to `Test` menu and select `Test Settings` > `Default Processor Architecture` > `X64`.</span></span>

> [!TIP]
> <span data-ttu-id="4eadb-130">L'impostazione dell'architettura del processore predefinita`.suo`per Visual Studio viene archiviata nel file delle opzioni della soluzione ( ) per ogni soluzione.</span><span class="sxs-lookup"><span data-stu-id="4eadb-130">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="4eadb-131">Se si elimina questo file, sarà `X64` necessario selezionare nuovamente come architettura del processore.</span><span class="sxs-lookup"><span data-stu-id="4eadb-131">If you delete this file, then you will need to select `X64` as your processor architecture again.</span></span>

<span data-ttu-id="4eadb-132">Compilare il progetto, `Test` accedere `Windows`  >  `Test Explorer`al menu e selezionare .</span><span class="sxs-lookup"><span data-stu-id="4eadb-132">Build the project, go to the `Test` menu and select `Windows` > `Test Explorer`.</span></span> <span data-ttu-id="4eadb-133">`AllocateQubit`apparirà nell'elenco dei test `Not Run Tests` nel gruppo.</span><span class="sxs-lookup"><span data-stu-id="4eadb-133">`AllocateQubit` will show up in the list of tests in the `Not Run Tests` group.</span></span> <span data-ttu-id="4eadb-134">Selezionare `Run All` o eseguire questo test individuale, e dovrebbe passare!</span><span class="sxs-lookup"><span data-stu-id="4eadb-134">Select `Run All` or run this individual test, and it should pass!</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="4eadb-135">Riga di comando/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="4eadb-135">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="4eadb-136">Per eseguire i test, passare alla cartella `Tests.csproj`del progetto (la cartella che contiene ) ed eseguire il comando:</span><span class="sxs-lookup"><span data-stu-id="4eadb-136">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and execute the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="4eadb-137">L'output dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="4eadb-137">You should get output similar to the following:</span></span>

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

<span data-ttu-id="4eadb-138">Gli unit test possono essere filtrati in base al nome e/o all'obiettivo di esecuzione:</span><span class="sxs-lookup"><span data-stu-id="4eadb-138">Unit tests can be filtered according to their name and/or the execution target:</span></span>

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

<span data-ttu-id="4eadb-139">La funzione <xref:microsoft.quantum.intrinsic.message> intrinseca ha tipo `(String -> Unit)` e consente la creazione di messaggi di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="4eadb-139">The intrinsic function <xref:microsoft.quantum.intrinsic.message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="4eadb-140">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="4eadb-140">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="4eadb-141">Dopo aver eseguito un test in Esplora test e aver fatto clic sul test, verrà visualizzato un pannello con le informazioni sull'esecuzione del test: stato Superato/Non superato, tempo trascorso e collegamento "Output".</span><span class="sxs-lookup"><span data-stu-id="4eadb-141">After you execute a test in Test Explorer and click on the test, a panel will appear with information about test execution: Passed/Failed status, elapsed time and an "Output" link.</span></span> <span data-ttu-id="4eadb-142">Se si fa clic sul collegamento "Output", l'output di test si aprirà in una nuova finestra.</span><span class="sxs-lookup"><span data-stu-id="4eadb-142">If you click the "Output" link, test output will open in a new window.</span></span>

![uscita di prova](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="4eadb-144">Riga di comando/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="4eadb-144">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="4eadb-145">Lo stato superato/non superato per ogni `dotnet test`test viene stampato nella console da .</span><span class="sxs-lookup"><span data-stu-id="4eadb-145">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="4eadb-146">Per i test non superati, gli output vengono stampati anche nella console per diagnosticare l'errore.</span><span class="sxs-lookup"><span data-stu-id="4eadb-146">For failing tests, the outputs are also printed to the console to help diagnose the failure.</span></span>

***

## <a name="facts-and-assertions"></a><span data-ttu-id="4eadb-147">Fatti e asserzioni</span><span class="sxs-lookup"><span data-stu-id="4eadb-147">Facts and Assertions</span></span>

<span data-ttu-id="4eadb-148">Poiché le funzioni in Q , non hanno effetti collaterali _logici,_ qualsiasi altro `()` _tipo_ di effetti di esecuzione di una funzione il cui tipo di output è la tupla vuota non può mai essere osservato dall'interno di un programma Di O.</span><span class="sxs-lookup"><span data-stu-id="4eadb-148">Because functions in Q# have no _logical_ side effects, any _other kinds_ of effects of executing a function whose output type is the empty tuple `()` can never be observed from within a Q# program.</span></span>
<span data-ttu-id="4eadb-149">In altre parte, un computer di destinazione `()` può scegliere di non eseguire alcuna funzione che restituisce con la garanzia che questa omissione non modificherà il comportamento di qualsiasi codice Q .</span><span class="sxs-lookup"><span data-stu-id="4eadb-149">That is, a target machine can choose not to execute any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="4eadb-150">In questo modo `()` le funzioni `Unit`che restituiscono (ad esempio) uno strumento utile per l'incorporamento di asserzioni e la logica di debug nei programmi Q.</span><span class="sxs-lookup"><span data-stu-id="4eadb-150">This makes functions returning `()` (i.e. `Unit`) a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

<span data-ttu-id="4eadb-151">Consideriamo un semplice esempio:</span><span class="sxs-lookup"><span data-stu-id="4eadb-151">Let's consider a simple example:</span></span>

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="4eadb-152">In questo `fail` caso, la parola chiave indica che il calcolo non deve procedere, generando un'eccezione nel computer di destinazione che esegue il programma Q.</span><span class="sxs-lookup"><span data-stu-id="4eadb-152">Here, the keyword `fail` indicates that the computation should not proceed, raising an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="4eadb-153">Per definizione, un errore di questo tipo non può essere osservato dall'interno `fail` di Q , poiché non viene eseguito alcun ulteriore codice Q , dopo il raggiungimento di un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="4eadb-153">By definition, a failure of this kind cannot be observed from within Q#, as no further Q# code is run after a `fail` statement is reached.</span></span>
<span data-ttu-id="4eadb-154">Così, se procediamo `PositivityFact`passato una chiamata a , possiamo essere certi dal fatto che il suo input è stato positivo.</span><span class="sxs-lookup"><span data-stu-id="4eadb-154">Thus, if we proceed past a call to `PositivityFact`, we can be assured by that its input was positive.</span></span>

<span data-ttu-id="4eadb-155">Si noti che è `PositivityFact` possibile [`Fact`](xref:microsoft.quantum.diagnostics.fact) implementare <xref:microsoft.quantum.diagnostics> lo stesso comportamento dell'utilizzo della funzione dallo spazio dei nomi:Note that we can implement the same behavior as using the function from the namespace:</span><span class="sxs-lookup"><span data-stu-id="4eadb-155">Note that we can implement the same behavior as `PositivityFact` using the [`Fact`](xref:microsoft.quantum.diagnostics.fact) function from the <xref:microsoft.quantum.diagnostics> namespace:</span></span>

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

<span data-ttu-id="4eadb-156">*Le asserzioni*, d'altra parte, vengono utilizzate in modo simile ai fatti, ma possono dipendere dallo stato del computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4eadb-156">*Assertions*, on the other hand, are used similarly to facts, but may be dependent on the state of the target machine.</span></span> <span data-ttu-id="4eadb-157">Di conseguenza, sono definiti come operazioni, mentre i fatti sono definiti come funzioni (come sopra).</span><span class="sxs-lookup"><span data-stu-id="4eadb-157">Correspondingly, they are defined as operations, whereas facts are defined as functions (as above).</span></span>
<span data-ttu-id="4eadb-158">Per comprendere la distinzione, considerare il seguente utilizzo di un fatto all'interno di un'asserzione:</span><span class="sxs-lookup"><span data-stu-id="4eadb-158">To understand the distinction, consider the following use of a fact within an assertion:</span></span>

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

<span data-ttu-id="4eadb-159">Qui, stiamo usando <xref:microsoft.quantum.environment.getqubitsavailabletouse> l'operazione per restituire il numero di qubit disponibili per l'uso.</span><span class="sxs-lookup"><span data-stu-id="4eadb-159">Here, we are using the operation <xref:microsoft.quantum.environment.getqubitsavailabletouse> to return the number of qubits available to use.</span></span>
<span data-ttu-id="4eadb-160">Poiché questo dipende chiaramente dallo stato globale del programma `AssertQubitsAreAvailable` e dal suo ambiente di esecuzione, anche la nostra definizione di deve essere un'operazione.</span><span class="sxs-lookup"><span data-stu-id="4eadb-160">As this clearly depends on the global state of the program and its execution environment, our definition of  `AssertQubitsAreAvailable` must be an operation as well.</span></span>
<span data-ttu-id="4eadb-161">Tuttavia, è possibile utilizzare tale `Bool` stato globale per `Fact` restituire un valore semplice come input per la funzione.</span><span class="sxs-lookup"><span data-stu-id="4eadb-161">However, we can use that global state to yield a simple `Bool` value as input to the `Fact` function.</span></span>

<span data-ttu-id="4eadb-162">Sulla base di queste idee, [il preludio](xref:microsoft.quantum.libraries.standard.prelude) offre due asserzioni particolarmente utili ed <xref:microsoft.quantum.intrinsic.assert> <xref:microsoft.quantum.intrinsic.assertprob> entrambe modellate come operazioni su . `()`</span><span class="sxs-lookup"><span data-stu-id="4eadb-162">Building on these ideas, [the prelude](xref:microsoft.quantum.libraries.standard.prelude) offers two especially useful assertions, <xref:microsoft.quantum.intrinsic.assert> and <xref:microsoft.quantum.intrinsic.assertprob> both modeled as operations onto `()`.</span></span> <span data-ttu-id="4eadb-163">Queste asserzioni prendono ciascuna un operatore Pauli che descrive una particolare misurazione dell'interesse, un registro quantistico su cui deve essere eseguita una misurazione e un risultato ipotetico.</span><span class="sxs-lookup"><span data-stu-id="4eadb-163">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is to be performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="4eadb-164">Sulle macchine bersaglio che funzionano tramite simulazione, non siamo vincolati dal [teorema](https://en.wikipedia.org/wiki/No-cloning_theorem)di non clonazione e possiamo eseguire tali misurazioni senza disturbare il registro passato a tali asserzioni.</span><span class="sxs-lookup"><span data-stu-id="4eadb-164">On target machines which work by simulation, we are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register passed to such assertions.</span></span>
<span data-ttu-id="4eadb-165">Un simulatore può quindi, analogamente alla funzione precedente, interrompere il `PositivityFact` calcolo se l'esito ipotetico non viene osservato nella pratica:</span><span class="sxs-lookup"><span data-stu-id="4eadb-165">A simulator can then, similar to the `PositivityFact` function above, abort computation if the hypothetical outcome would not be observed in practice:</span></span>

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

<span data-ttu-id="4eadb-166">Sull'hardware quantistico fisico, dove il teorema no-cloning `AssertProb` impedisce `()` l'esame dello stato quantistico, le `Assert` operazioni e ritornano semplicemente senza altri effetti.</span><span class="sxs-lookup"><span data-stu-id="4eadb-166">On physical quantum hardware, where the no-cloning theorem prevents examination of quantum state, the `Assert` and `AssertProb` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="4eadb-167">Lo <xref:microsoft.quantum.diagnostics> spazio dei nomi `Assert` fornisce diverse altre funzioni della famiglia che ci permettono di controllare le condizioni più avanzate.</span><span class="sxs-lookup"><span data-stu-id="4eadb-167">The <xref:microsoft.quantum.diagnostics> namespace provides several more functions of the `Assert` family which allow us to check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="4eadb-168">Funzioni di dump</span><span class="sxs-lookup"><span data-stu-id="4eadb-168">Dump Functions</span></span>

<span data-ttu-id="4eadb-169">Per facilitare la <xref:microsoft.quantum.diagnostics> risoluzione dei problemi relativi ai programmi quantistici, <xref:microsoft.quantum.diagnostics.dumpmachine> lo <xref:microsoft.quantum.diagnostics.dumpregister>spazio dei nomi offre due funzioni che possono eseguire il dump in un file dello stato corrente del computer di destinazione: e .</span><span class="sxs-lookup"><span data-stu-id="4eadb-169">To help troubleshooting quantum programs, the <xref:microsoft.quantum.diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister>.</span></span> <span data-ttu-id="4eadb-170">L'output generato di ciascuno dipende dal computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4eadb-170">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="4eadb-171">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="4eadb-171">DumpMachine</span></span>

<span data-ttu-id="4eadb-172">Il simulatore quantistico full-state distribuito come parte del Quantum Development Kit scrive nel file la [funzione d'onda](https://en.wikipedia.org/wiki/Wave_function) dell'intero sistema quantistico, come una matrice unidimensionale di numeri complessi, in cui ogni elemento rappresenta l'ampiezza della probabilità di misurare b_ lo stato di base computazionale . b_1b_0 per bit,\{b_i\}di z.</span><span class="sxs-lookup"><span data-stu-id="4eadb-172">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="4eadb-173">Ad esempio, in un computer in cui sono stati allocati solo due qubit e nello stato quantistico , "inizio",{00} "inizio" , "se",{2} "sepsi" o "frac"{1}, "sqrt" e "sqt"{2}- "frac" (1 , "i", "fine",{10}"fine" e "chiamata" <xref:microsoft.quantum.diagnostics.dumpmachine> genera questo output:</span><span class="sxs-lookup"><span data-stu-id="4eadb-173">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="4eadb-174">La prima riga fornisce un commento con gli ID dei qubit corrispondenti nell'ordine significativo.</span><span class="sxs-lookup"><span data-stu-id="4eadb-174">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="4eadb-175">Il resto delle righe descrive l'ampiezza di probabilità di misurare il vettore di stato di base , in entrambi i formati cartesiano e polare.</span><span class="sxs-lookup"><span data-stu-id="4eadb-175">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="4eadb-176">In dettaglio per la prima riga:</span><span class="sxs-lookup"><span data-stu-id="4eadb-176">In detail for the first row:</span></span>

* <span data-ttu-id="4eadb-177">**`∣0❭:`** questa riga corrisponde `0` allo stato di base computazionale</span><span class="sxs-lookup"><span data-stu-id="4eadb-177">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="4eadb-178">**`0.707107 +  0.000000 i`**: l'ampiezza di probabilità in formato cartesiano.</span><span class="sxs-lookup"><span data-stu-id="4eadb-178">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="4eadb-179">**` == `**: `equal` il segno si separa entrambe le rappresentazioni equivalenti.</span><span class="sxs-lookup"><span data-stu-id="4eadb-179">**` == `**: the `equal` sign seperates both equivalent representations.</span></span>
* <span data-ttu-id="4eadb-180">**`**********  `**: Rappresentazione grafica della grandezza, il `*` numero di è proporzionato alla probabilità di misurare questo vettore di stato.</span><span class="sxs-lookup"><span data-stu-id="4eadb-180">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="4eadb-181">**`[ 0.500000 ]`**: il valore numerico della grandezza</span><span class="sxs-lookup"><span data-stu-id="4eadb-181">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="4eadb-182">**`    ---`**: rappresentazione grafica della fase dell'ampiezza (vedi sotto).</span><span class="sxs-lookup"><span data-stu-id="4eadb-182">**`    ---`**: A graphical representation of the amplitude's phase (see below).</span></span>
* <span data-ttu-id="4eadb-183">**`[ 0.0000 rad ]`**: il valore numerico della fase (in radianti).</span><span class="sxs-lookup"><span data-stu-id="4eadb-183">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="4eadb-184">Sia la grandezza che la fase vengono visualizzate con una rappresentazione grafica.</span><span class="sxs-lookup"><span data-stu-id="4eadb-184">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="4eadb-185">La rappresentazione di magnitudo è dritta: mostra una barra di `*`, maggiore è la probabilità che più grande sarà la barra.</span><span class="sxs-lookup"><span data-stu-id="4eadb-185">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="4eadb-186">Per la fase, mostriamo i seguenti simboli per rappresentare l'angolo in base agli intervalli:</span><span class="sxs-lookup"><span data-stu-id="4eadb-186">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

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

<span data-ttu-id="4eadb-187">Gli esempi `DumpMachine` seguenti illustrano alcuni stati comuni:The following examples show for some common states:</span><span class="sxs-lookup"><span data-stu-id="4eadb-187">The following examples show `DumpMachine` for some common states:</span></span>

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
  > <span data-ttu-id="4eadb-188">L'ID di un qubit viene assegnato in fase di esecuzione e non è necessariamente allineato con l'ordine in cui è stato allocato il qubit o la sua posizione all'interno di un registro qubit.</span><span class="sxs-lookup"><span data-stu-id="4eadb-188">The id of a qubit is assigned at runtime and it's not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019"></a>[<span data-ttu-id="4eadb-189">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="4eadb-189">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="4eadb-190">È possibile calcolare un id qubit in Visual Studio inserendo un punto di interruzione nel codice e controllando il valore di una variabile qubit, ad esempio:You can figure out a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span><span class="sxs-lookup"><span data-stu-id="4eadb-190">You can figure out a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![show qubit id in Visual Studio](~/media/qubit_id.png)
  >
  > <span data-ttu-id="4eadb-192">il qubit `0` con `register2` index`3`on has id `1` , il`2`qubit con index has id .</span><span class="sxs-lookup"><span data-stu-id="4eadb-192">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="4eadb-193">Riga di comando/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="4eadb-193">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="4eadb-194">È possibile calcolare un id <xref:microsoft.quantum.intrinsic.message> qubit utilizzando la funzione e passando la variabile qubit nel messaggio, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4eadb-194">You can figure out a qubit id by using the <xref:microsoft.quantum.intrinsic.message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="4eadb-195">che potrebbe generare questo output:</span><span class="sxs-lookup"><span data-stu-id="4eadb-195">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="4eadb-196">il che significa che `0` il `register2` qubit`3`con index on `1` has`2`id , il qubit con index has id .</span><span class="sxs-lookup"><span data-stu-id="4eadb-196">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


***

<span data-ttu-id="4eadb-197"><xref:microsoft.quantum.diagnostics.dumpmachine>fa parte <xref:microsoft.quantum.diagnostics> dello spazio dei nomi, pertanto `open` per poterlo utilizzare è necessario aggiungere un'istruzione:</span><span class="sxs-lookup"><span data-stu-id="4eadb-197"><xref:microsoft.quantum.diagnostics.dumpmachine> is part of the  <xref:microsoft.quantum.diagnostics> namespace, so in order to use it you must add an `open` statement:</span></span>

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


### <a name="dumpregister"></a><span data-ttu-id="4eadb-198">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="4eadb-198">DumpRegister</span></span>

<span data-ttu-id="4eadb-199"><xref:microsoft.quantum.diagnostics.dumpregister>funziona <xref:microsoft.quantum.diagnostics.dumpmachine>come , tranne per il fatto che ci vuole anche una serie di qubit per limitare la quantità di informazioni solo a quella rilevante per i qubit corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="4eadb-199"><xref:microsoft.quantum.diagnostics.dumpregister> works like <xref:microsoft.quantum.diagnostics.dumpmachine>, except it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="4eadb-200">Come <xref:microsoft.quantum.diagnostics.dumpmachine>per , le <xref:microsoft.quantum.diagnostics.dumpregister> informazioni generate da dipendono dal computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4eadb-200">As with <xref:microsoft.quantum.diagnostics.dumpmachine>, the information generated by <xref:microsoft.quantum.diagnostics.dumpregister> depends on the target machine.</span></span> <span data-ttu-id="4eadb-201">Per il simulatore quantistico full-state scrive nel file la funzione d'onda fino a una fase globale <xref:microsoft.quantum.diagnostics.dumpmachine>del sottosistema quantistico generato dai qubit forniti nello stesso formato di .</span><span class="sxs-lookup"><span data-stu-id="4eadb-201">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:microsoft.quantum.diagnostics.dumpmachine>.</span></span>  <span data-ttu-id="4eadb-202">{1}Ad esempio, riprendere un computer con solo due qubit allocati e nello stato quantistico .{2}{00} {2} {10} ( ( ( . . . . . . . . . . . . . . . . . . .{1}. .{2}. .{0} . .{2} . .{1} {2}{0} <xref:microsoft.quantum.diagnostics.dumpregister> `qubit[0]` . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .</span><span class="sxs-lookup"><span data-stu-id="4eadb-202">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="4eadb-203">e <xref:microsoft.quantum.diagnostics.dumpregister> la `qubit[1]` chiamata genera questo output:</span><span class="sxs-lookup"><span data-stu-id="4eadb-203">and calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="4eadb-204">In generale, lo stato di un registro che è impigliato con un altro registro è uno stato misto piuttosto che uno stato puro.</span><span class="sxs-lookup"><span data-stu-id="4eadb-204">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="4eadb-205">In questo <xref:microsoft.quantum.diagnostics.dumpregister> caso, restituisce il seguente messaggio:</span><span class="sxs-lookup"><span data-stu-id="4eadb-205">In this case, <xref:microsoft.quantum.diagnostics.dumpregister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="4eadb-206">L'esempio seguente mostra come <xref:microsoft.quantum.diagnostics.dumpregister> è <xref:microsoft.quantum.diagnostics.dumpmachine> possibile usare entrambi e nel codice Q:</span><span class="sxs-lookup"><span data-stu-id="4eadb-206">The following example shows you how you can use both <xref:microsoft.quantum.diagnostics.dumpregister> and <xref:microsoft.quantum.diagnostics.dumpmachine> in your Q# code:</span></span>

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

## <a name="debugging"></a><span data-ttu-id="4eadb-207">Debug</span><span class="sxs-lookup"><span data-stu-id="4eadb-207">Debugging</span></span>

<span data-ttu-id="4eadb-208">Oltre alle `Assert` `Dump` funzioni e alle operazioni, Qè supporta un sottoinsieme di funzionalità di debug standard di Visual Studio: [l'impostazione](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints)di punti di interruzione di riga, [l'esecuzione del codice tramite F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) e l'ispezione [dei valori delle variabili classiche](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) sono tutte possibili durante l'esecuzione del codice nel simulatore.</span><span class="sxs-lookup"><span data-stu-id="4eadb-208">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible during code execution on the simulator.</span></span>

<span data-ttu-id="4eadb-209">Il debug nel codice di Visual Studio sfrutta le funzionalità di debug fornite dall'estensione di codice di Visual Studio per Visual Studio basata su OmniSharp e richiede l'installazione della [versione più recente.](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)</span><span class="sxs-lookup"><span data-stu-id="4eadb-209">Debugging in Visual Studio Code leverages the debugging capabilities provided by the C# for Visual Studio Code extension powered by OmniSharp and requires installing the [latest version](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span></span> 
