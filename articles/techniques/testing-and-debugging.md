---
title: 'Tecniche Q #-test e debug | Microsoft Docs'
description: 'Tecniche Q #-test e debug'
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 25679331f1bed9f98b86c6eb20f511c891bac1af
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183489"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="d1a34-103">Test e debug</span><span class="sxs-lookup"><span data-stu-id="d1a34-103">Testing and Debugging</span></span>

<span data-ttu-id="d1a34-104">Come per la programmazione classica, è essenziale poter controllare che i programmi Quantum funzionino come previsto e per essere in grado di diagnosticare un programma quantum non corretto.</span><span class="sxs-lookup"><span data-stu-id="d1a34-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose a quantum program that is incorrect.</span></span>
<span data-ttu-id="d1a34-105">Questa sezione include gli strumenti offerti da Q # per il test e il debug di programmi Quantum.</span><span class="sxs-lookup"><span data-stu-id="d1a34-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="d1a34-106">Unit test</span><span class="sxs-lookup"><span data-stu-id="d1a34-106">Unit Tests</span></span>

<span data-ttu-id="d1a34-107">Un approccio comune al test dei programmi classici è quello di scrivere piccoli programmi denominati *unit test* che eseguono codice in una libreria e confrontano l'output con un output previsto.</span><span class="sxs-lookup"><span data-stu-id="d1a34-107">One common approach to testing classical programs is to write small programs called *unit tests* which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="d1a34-108">Ad esempio, potrebbe essere necessario assicurarsi che `Square(2)` restituisca `4`, dal momento che è noto *un valore precedente* a $2 ^ 2 = $4.</span><span class="sxs-lookup"><span data-stu-id="d1a34-108">For instance, we may want to ensure that `Square(2)` returns `4`, since we know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="d1a34-109">Q # supporta la creazione di unit test per i programmi Quantum e che può essere eseguito come test nel Framework di unit test di [xUnit](https://xunit.github.io/) .</span><span class="sxs-lookup"><span data-stu-id="d1a34-109">Q# supports creating unit tests for quantum programs, and which can be executed as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="d1a34-110">Creazione di un progetto di test</span><span class="sxs-lookup"><span data-stu-id="d1a34-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="d1a34-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="d1a34-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="d1a34-112">Aprire Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="d1a34-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="d1a34-113">Passare al menu `File` e selezionare `New` > `Project...`.</span><span class="sxs-lookup"><span data-stu-id="d1a34-113">Go to the `File` menu and select `New` > `Project...`.</span></span>
<span data-ttu-id="d1a34-114">In Esplora modelli di progetto, in `Installed` > `Visual C#`selezionare il modello `Q# Test Project`.</span><span class="sxs-lookup"><span data-stu-id="d1a34-114">In the project template explorer, under `Installed` > `Visual C#`, select the `Q# Test Project` template.</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="d1a34-115">Riga di comando/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="d1a34-115">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="d1a34-116">Dalla riga di comando preferita, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="d1a34-116">From your favorite command line, run the following command:</span></span>
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="d1a34-117">In entrambi i casi, il nuovo progetto disporrà di due file aperti.</span><span class="sxs-lookup"><span data-stu-id="d1a34-117">In either case, your new project will have two files open.</span></span>
<span data-ttu-id="d1a34-118">Il primo file, `Tests.qs`, rappresenta una comoda posizione per definire nuovi unit test Q #.</span><span class="sxs-lookup"><span data-stu-id="d1a34-118">The first file, `Tests.qs`, provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="d1a34-119">Inizialmente questo file contiene un campione unit test `AllocateQubitTest` che verifica che un qubit appena allocato si trovi nello stato $ \ket{0}$ e stampa un messaggio:</span><span class="sxs-lookup"><span data-stu-id="d1a34-119">Initially this file contains one sample unit test `AllocateQubitTest` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    operation AllocateQubitTest () : Unit {
        using (q = Qubit()) {
            Assert([PauliZ], [q], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

<span data-ttu-id="d1a34-120">Qualsiasi operazione Q # compatibile con il tipo `(Unit => Unit)` o funzione compatibile con `(Unit -> Unit)` può essere eseguita come unit test.</span><span class="sxs-lookup"><span data-stu-id="d1a34-120">Any Q# operation compatible with the type `(Unit => Unit)` or function compatible with `(Unit -> Unit)` can be executed as a unit test.</span></span> 

<span data-ttu-id="d1a34-121">Il secondo file, `TestSuiteRunner.cs` contiene un metodo che consente di individuare ed eseguire unit test Q #.</span><span class="sxs-lookup"><span data-stu-id="d1a34-121">The second file, `TestSuiteRunner.cs` contains a method that discovers and runs Q# unit tests.</span></span> <span data-ttu-id="d1a34-122">Si tratta del metodo `TestTarget` annotato con `OperationDriver` attributo.</span><span class="sxs-lookup"><span data-stu-id="d1a34-122">This is the method `TestTarget` annotated with `OperationDriver` attribute.</span></span>
<span data-ttu-id="d1a34-123">L'attributo `OperationDriver` fa parte della libreria di estensioni xUnit Microsoft. Quantum. Simulation. xUnit.</span><span class="sxs-lookup"><span data-stu-id="d1a34-123">The `OperationDriver` attribute is a part of the Xunit extension library Microsoft.Quantum.Simulation.Xunit.</span></span>
<span data-ttu-id="d1a34-124">Il Framework di testing unità chiama `TestTarget` metodo per ogni Q # unit test rilevato.</span><span class="sxs-lookup"><span data-stu-id="d1a34-124">The unit testing framework calls `TestTarget` method for every Q# unit test it has discovered.</span></span>
<span data-ttu-id="d1a34-125">Il Framework passa la descrizione unit test al metodo tramite `op` argomento.</span><span class="sxs-lookup"><span data-stu-id="d1a34-125">The framework passes the unit test description to the method through `op` argument.</span></span> <span data-ttu-id="d1a34-126">La riga di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="d1a34-126">The following line of code:</span></span>
```csharp
op.TestOperationRunner(sim);
```
<span data-ttu-id="d1a34-127">esegue il unit test `QuantumSimulator`.</span><span class="sxs-lookup"><span data-stu-id="d1a34-127">executes the unit test on `QuantumSimulator`.</span></span>

<span data-ttu-id="d1a34-128">Per impostazione predefinita, il meccanismo di individuazione unit test Cerca tutte le funzioni Q # o le operazioni di tipo compatibile che soddisfano le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="d1a34-128">By default, the unit test discovery mechanism looks for all Q# functions or operations of compatible type that satisfy the following properties:</span></span>
* <span data-ttu-id="d1a34-129">Si trova nello stesso assembly del metodo annotato con l'attributo `OperationDriver`.</span><span class="sxs-lookup"><span data-stu-id="d1a34-129">Located in the same assembly as the method annotated with the `OperationDriver` attribute.</span></span>
* <span data-ttu-id="d1a34-130">Si trova nello stesso spazio dei nomi del metodo annotato con l'attributo `OperationDriver`.</span><span class="sxs-lookup"><span data-stu-id="d1a34-130">Located in the same namespace as the method annotated with the `OperationDriver` attribute.</span></span>
* <span data-ttu-id="d1a34-131">Ha un nome che termina con `Test`.</span><span class="sxs-lookup"><span data-stu-id="d1a34-131">Has a name ending with `Test`.</span></span>

<span data-ttu-id="d1a34-132">È possibile impostare un assembly, uno spazio dei nomi e un suffisso per unit test funzioni e operazioni utilizzando parametri facoltativi dell'attributo `OperationDriver`:</span><span class="sxs-lookup"><span data-stu-id="d1a34-132">An assembly, a namespace, and a suffix for unit test functions and operations can be set using optional parameters of the `OperationDriver` attribute:</span></span>
* <span data-ttu-id="d1a34-133">`AssemblyName` parametro imposta il nome dell'assembly in cui viene eseguita la ricerca dei test.</span><span class="sxs-lookup"><span data-stu-id="d1a34-133">`AssemblyName` parameter sets the name of the assembly which is being searched for tests.</span></span>
* <span data-ttu-id="d1a34-134">`TestNamespace` parametro imposta il nome dello spazio dei nomi in cui vengono cercati i test.</span><span class="sxs-lookup"><span data-stu-id="d1a34-134">`TestNamespace` parameter sets the name of the namespace which is being searched for tests.</span></span>
* <span data-ttu-id="d1a34-135">`Suffix` imposta il suffisso di nomi di operazione o di funzione considerati unit test.</span><span class="sxs-lookup"><span data-stu-id="d1a34-135">`Suffix` sets the suffix of operation or function names that are considered to be unit tests.</span></span>

<span data-ttu-id="d1a34-136">Inoltre, il `TestCasePrefix` parametro facoltativo consente di impostare un prefisso per il nome del test case.</span><span class="sxs-lookup"><span data-stu-id="d1a34-136">In addition, the `TestCasePrefix` optional parameter lets you set a prefix for the name of the test case.</span></span> <span data-ttu-id="d1a34-137">Il prefisso davanti al nome dell'operazione verrà visualizzato nell'elenco dei test case.</span><span class="sxs-lookup"><span data-stu-id="d1a34-137">The prefix in front of the operation name will appear in the list of test cases.</span></span> <span data-ttu-id="d1a34-138">Ad esempio, `TestCasePrefix = "QSim:"` provocherà la visualizzazione `AllocateQubitTest` `QSim:AllocateQubitTest` nell'elenco dei test trovati.</span><span class="sxs-lookup"><span data-stu-id="d1a34-138">For example, `TestCasePrefix = "QSim:"` will cause `AllocateQubitTest` to appear as `QSim:AllocateQubitTest` in the list of found tests.</span></span> <span data-ttu-id="d1a34-139">Questo può essere utile per indicare, ad esempio, quale simulatore viene usato per eseguire un test.</span><span class="sxs-lookup"><span data-stu-id="d1a34-139">This can be useful to indicate, for instance, which simulator is used to run a test.</span></span>

### <a name="running-q-unit-tests"></a><span data-ttu-id="d1a34-140">Esecuzione di unit test Q #</span><span class="sxs-lookup"><span data-stu-id="d1a34-140">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="d1a34-141">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="d1a34-141">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="d1a34-142">Per configurare una sola volta per soluzione, passare al menu `Test` e selezionare `Test Settings` > `Default Processor Architecture` > `X64`.</span><span class="sxs-lookup"><span data-stu-id="d1a34-142">As a one-time per-solution setup, go to `Test` menu and select `Test Settings` > `Default Processor Architecture` > `X64`.</span></span>

> [!TIP]
> <span data-ttu-id="d1a34-143">L'impostazione predefinita dell'architettura del processore per Visual Studio è archiviata nel file di opzioni soluzione (`.suo`) per ogni soluzione.</span><span class="sxs-lookup"><span data-stu-id="d1a34-143">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="d1a34-144">Se si elimina questo file, sarà necessario selezionare di nuovo `X64` come architettura del processore.</span><span class="sxs-lookup"><span data-stu-id="d1a34-144">If you delete this file, then you will need to select `X64` as your processor architecture again.</span></span>

<span data-ttu-id="d1a34-145">Compilare il progetto, andare al menu `Test` e selezionare `Windows` > `Test Explorer`.</span><span class="sxs-lookup"><span data-stu-id="d1a34-145">Build the project, go to the `Test` menu and select `Windows` > `Test Explorer`.</span></span> <span data-ttu-id="d1a34-146">`AllocateQubitTest` sarà visualizzato nell'elenco dei test del gruppo `Not Run Tests`.</span><span class="sxs-lookup"><span data-stu-id="d1a34-146">`AllocateQubitTest` will show up in the list of tests in the `Not Run Tests` group.</span></span> <span data-ttu-id="d1a34-147">Selezionare `Run All` o eseguire questo test singolo e dovrebbe essere superato.</span><span class="sxs-lookup"><span data-stu-id="d1a34-147">Select `Run All` or run this individual test, and it should pass!</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="d1a34-148">Riga di comando/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="d1a34-148">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="d1a34-149">Per eseguire i test, passare alla cartella del progetto (la cartella che contiene `Tests.csproj`) ed eseguire il comando:</span><span class="sxs-lookup"><span data-stu-id="d1a34-149">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and execute the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="d1a34-150">L'output dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="d1a34-150">You should get output similar to the following:</span></span>

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

***

## <a name="logging-and-assertions"></a><span data-ttu-id="d1a34-151">Registrazione e asserzioni</span><span class="sxs-lookup"><span data-stu-id="d1a34-151">Logging and Assertions</span></span>

<span data-ttu-id="d1a34-152">Una conseguenza importante del fatto che le funzioni in Q # non hanno effetti collaterali è che gli effetti dell'esecuzione di una funzione il cui tipo di output è la tupla vuota `()` non possono mai essere osservati dall'interno di un programma Q #.</span><span class="sxs-lookup"><span data-stu-id="d1a34-152">One important consequence of the fact that functions in Q# have no side effects is that any effects of executing a function whose output type is the empty tuple `()` can never be observed from within a Q# program.</span></span>
<span data-ttu-id="d1a34-153">In altre condizioni, un computer di destinazione può scegliere di non eseguire alcuna funzione che restituisce `()` con la garanzia che questa omissione non modificherà il comportamento di un codice Q # seguente.</span><span class="sxs-lookup"><span data-stu-id="d1a34-153">That is, a target machine can choose not to execute any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="d1a34-154">Questo rende le funzioni che restituiscono `()` uno strumento utile per incorporare le asserzioni e la logica di debug nei programmi Q #.</span><span class="sxs-lookup"><span data-stu-id="d1a34-154">This makes functions returning `()` a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

### <a name="logging"></a><span data-ttu-id="d1a34-155">Registrazione</span><span class="sxs-lookup"><span data-stu-id="d1a34-155">Logging</span></span>

<span data-ttu-id="d1a34-156">La funzione intrinseca <xref:microsoft.quantum.intrinsic.message> dispone del tipo `(String -> Unit)` e consente la creazione di messaggi di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="d1a34-156">The intrinsic function <xref:microsoft.quantum.intrinsic.message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

<span data-ttu-id="d1a34-157">L'azione `onLog` di `QuantumSimulator` può essere usata per definire le azioni eseguite quando il codice Q # chiama `Message`.</span><span class="sxs-lookup"><span data-stu-id="d1a34-157">The `onLog` action of `QuantumSimulator` can be used to define actions performed when Q# code calls `Message`.</span></span> <span data-ttu-id="d1a34-158">Per impostazione predefinita, i messaggi registrati vengono stampati nell'output standard.</span><span class="sxs-lookup"><span data-stu-id="d1a34-158">By default logged messages are printed to standard output.</span></span>

<span data-ttu-id="d1a34-159">Quando si definisce un gruppo di unit test, i messaggi registrati possono essere indirizzati all'output del test.</span><span class="sxs-lookup"><span data-stu-id="d1a34-159">When defining a unit test suite, the logged messages can be directed to the test output.</span></span> <span data-ttu-id="d1a34-160">Quando si crea un progetto da un modello di progetto di test Q #, questo reindirizzamento è preconfigurato per il gruppo e viene creato per impostazione predefinita come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="d1a34-160">When a project is created from Q# Test Project template, this redirection is pre-configured for the suite and created by default as follows:</span></span>

```qsharp
using (var sim = new QuantumSimulator())
{
    // OnLog defines action(s) performed when Q# test calls operation Message
    sim.OnLog += (msg) => { output.WriteLine(msg); };
    op.TestOperationRunner(sim);
}
```

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="d1a34-161">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="d1a34-161">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="d1a34-162">Dopo aver eseguito un test in Esplora test e aver fatto clic sul test, verrà visualizzato un pannello con le informazioni sull'esecuzione dei test: stato superato/non riuscito, tempo trascorso e collegamento "output".</span><span class="sxs-lookup"><span data-stu-id="d1a34-162">After you execute a test in Test Explorer and click on the test, a panel will appear with information about test execution: Passed/Failed status, elapsed time and an "Output" link.</span></span> <span data-ttu-id="d1a34-163">Se si fa clic sul collegamento "output", l'output del test viene aperto in una nuova finestra.</span><span class="sxs-lookup"><span data-stu-id="d1a34-163">If you click the "Output" link, test output will open in a new window.</span></span>

![output del test](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="d1a34-165">Riga di comando/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="d1a34-165">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="d1a34-166">Lo stato di superamento/errore per ogni test viene stampato nella console di `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="d1a34-166">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="d1a34-167">Per i test con esito negativo, vengono stampati nella console anche gli output registrati come risultato della chiamata `output.WriteLine(msg)` precedente, per facilitare la diagnosi dell'errore.</span><span class="sxs-lookup"><span data-stu-id="d1a34-167">For failing tests, the outputs logged as a result of the `output.WriteLine(msg)` call above are also printed to the console to help diagnose the failure.</span></span>

***

### <a name="assertions"></a><span data-ttu-id="d1a34-168">Asserzioni</span><span class="sxs-lookup"><span data-stu-id="d1a34-168">Assertions</span></span>

<span data-ttu-id="d1a34-169">È possibile applicare la stessa logica alle asserzioni di implementazione.</span><span class="sxs-lookup"><span data-stu-id="d1a34-169">The same logic can be applied to implementing assertions.</span></span> <span data-ttu-id="d1a34-170">Si prenda in considerazione un semplice esempio:</span><span class="sxs-lookup"><span data-stu-id="d1a34-170">Let's consider a simple example:</span></span>

```qsharp
function AssertPositive(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="d1a34-171">In questo caso, la parola chiave `fail` indica che il calcolo non deve proseguire, generando un'eccezione nel computer di destinazione che esegue il programma Q #.</span><span class="sxs-lookup"><span data-stu-id="d1a34-171">Here, the keyword `fail` indicates that the computation should not proceed, raising an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="d1a34-172">Per definizione, non è possibile osservare un errore di questo tipo dall'interno di Q #, perché non viene eseguito un ulteriore codice Q # dopo il raggiungimento di un'istruzione `fail`.</span><span class="sxs-lookup"><span data-stu-id="d1a34-172">By definition, a failure of this kind cannot be observed from within Q#, as no further Q# code is run after a `fail` statement is reached.</span></span>
<span data-ttu-id="d1a34-173">Di conseguenza, se si procede dopo una chiamata a `AssertPositive`, è possibile garantire che l'input sia positivo.</span><span class="sxs-lookup"><span data-stu-id="d1a34-173">Thus, if we proceed past a call to `AssertPositive`, we can be assured by that its input was positive.</span></span>

<span data-ttu-id="d1a34-174">Basandosi su queste idee, [il preludio](xref:microsoft.quantum.libraries.standard.prelude) offre due asserzioni particolarmente utili, <xref:microsoft.quantum.intrinsic.assert> e <xref:microsoft.quantum.intrinsic.assertprob> entrambe modellate come operazioni su `()`.</span><span class="sxs-lookup"><span data-stu-id="d1a34-174">Building on these ideas, [the prelude](xref:microsoft.quantum.libraries.standard.prelude) offers two especially useful assertions, <xref:microsoft.quantum.intrinsic.assert> and <xref:microsoft.quantum.intrinsic.assertprob> both modeled as operations onto `()`.</span></span> <span data-ttu-id="d1a34-175">Ognuna di queste asserzioni accetta un operatore Pauli che descrive una particolare misurazione di interesse, un registro Quantum su cui deve essere eseguita una misurazione e un risultato ipotetico.</span><span class="sxs-lookup"><span data-stu-id="d1a34-175">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is to be performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="d1a34-176">Nei computer di destinazione che operano per simulazione, [il teorema di non clonazione](https://en.wikipedia.org/wiki/No-cloning_theorem)non è vincolato e può eseguire tali misure senza compromettere il registro passato a tali asserzioni.</span><span class="sxs-lookup"><span data-stu-id="d1a34-176">On target machines which work by simulation, we are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register passed to such assertions.</span></span>
<span data-ttu-id="d1a34-177">Un simulatore può quindi, analogamente alla `AssertPositive` funzione precedente, Interrompi il calcolo se il risultato ipotetico non viene osservato in pratica:</span><span class="sxs-lookup"><span data-stu-id="d1a34-177">A simulator can then, similar to the `AssertPositive` function above, abort computation if the hypothetical outcome would not be observed in practice:</span></span>

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

<span data-ttu-id="d1a34-178">Su hardware quantum fisico, in cui il teorema di non clonazione impedisce l'analisi dello stato del quantum, le operazioni di `Assert` e `AssertProb` restituiscono semplicemente `()` senza alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="d1a34-178">On physical quantum hardware, where the no-cloning theorem prevents examination of quantum state, the `Assert` and `AssertProb` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="d1a34-179">Lo spazio dei nomi <xref:microsoft.quantum.diagnostics> fornisce diverse funzioni della famiglia di `Assert` che consentono di controllare le condizioni più avanzate.</span><span class="sxs-lookup"><span data-stu-id="d1a34-179">The <xref:microsoft.quantum.diagnostics> namespace provides several more functions of the `Assert` family which allow us to check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="d1a34-180">Funzioni dump</span><span class="sxs-lookup"><span data-stu-id="d1a34-180">Dump Functions</span></span>

<span data-ttu-id="d1a34-181">Per semplificare la risoluzione dei problemi relativi ai programmi Quantum, lo spazio dei nomi <xref:microsoft.quantum.diagnostics> offre due funzioni che consentono di eseguire il dump in un file dello stato corrente del computer di destinazione: <xref:microsoft.quantum.diagnostics.dumpmachine> e <xref:microsoft.quantum.diagnostics.dumpregister>.</span><span class="sxs-lookup"><span data-stu-id="d1a34-181">To help troubleshooting quantum programs, the <xref:microsoft.quantum.diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister>.</span></span> <span data-ttu-id="d1a34-182">L'output generato di ogni dipende dal computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d1a34-182">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="d1a34-183">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="d1a34-183">DumpMachine</span></span>

<span data-ttu-id="d1a34-184">Il simulatore Quantum a stato intero distribuito come parte del quantum Development Kit scrive nel file la [funzione Wave](https://en.wikipedia.org/wiki/Wave_function) dell'intero sistema Quantum, come matrice unidimensionale di numeri complessi, in cui ogni elemento rappresenta l'ampiezza del probabilità di misurare lo stato di base di calcolo $ \ket{n} $, dove $ \ket{n} = \ket{b_{n-1}... b_1b_0} $ per BITS $\{b_i\}$.</span><span class="sxs-lookup"><span data-stu-id="d1a34-184">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="d1a34-185">Ad esempio, in un computer con solo due qubits allocati e nello stato quantico $ $ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{(1 + i)}{2} \ket{10}, \end{align} $ $ chiamata <xref:microsoft.quantum.diagnostics.dumpmachine> genera questo output :</span><span class="sxs-lookup"><span data-stu-id="d1a34-185">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="d1a34-186">La prima riga fornisce un commento con gli ID dei qubits corrispondenti nell'ordine significativo.</span><span class="sxs-lookup"><span data-stu-id="d1a34-186">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="d1a34-187">Il resto delle righe descrive l'ampiezza di probabilità della misurazione del vettore di stato di base $ \ket{n} $ nei formati cartesiani e polari.</span><span class="sxs-lookup"><span data-stu-id="d1a34-187">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="d1a34-188">In dettaglio per la prima riga:</span><span class="sxs-lookup"><span data-stu-id="d1a34-188">In detail for the first row:</span></span>

* <span data-ttu-id="d1a34-189">**`∣0❭:`** questa riga corrisponde allo stato di base del calcolo `0`</span><span class="sxs-lookup"><span data-stu-id="d1a34-189">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="d1a34-190">**`0.707107 +  0.000000 i`** : l'ampiezza della probabilità in formato cartesiano.</span><span class="sxs-lookup"><span data-stu-id="d1a34-190">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="d1a34-191">**` == `** : il segno di `equal` separa entrambe le rappresentazioni equivalenti.</span><span class="sxs-lookup"><span data-stu-id="d1a34-191">**` == `**: the `equal` sign seperates both equivalent representations.</span></span>
* <span data-ttu-id="d1a34-192">**`**********  `** : rappresentazione grafica della grandezza, il numero di `*` è proporzionale alla probabilità di misurare questo vettore di stato.</span><span class="sxs-lookup"><span data-stu-id="d1a34-192">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="d1a34-193">**`[ 0.500000 ]`** : valore numerico della grandezza</span><span class="sxs-lookup"><span data-stu-id="d1a34-193">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="d1a34-194">**`    ---`** : rappresentazione grafica della fase dell'ampiezza (vedere di seguito).</span><span class="sxs-lookup"><span data-stu-id="d1a34-194">**`    ---`**: A graphical representation of the amplitude's phase (see below).</span></span>
* <span data-ttu-id="d1a34-195">**`[ 0.0000 rad ]`** : valore numerico della fase (in radianti).</span><span class="sxs-lookup"><span data-stu-id="d1a34-195">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="d1a34-196">Sia la grandezza che la fase vengono visualizzate con una rappresentazione grafica.</span><span class="sxs-lookup"><span data-stu-id="d1a34-196">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="d1a34-197">La rappresentazione di magnitude è semplice: Mostra una barra di `*`, più grande è la probabilità maggiore sarà la barra.</span><span class="sxs-lookup"><span data-stu-id="d1a34-197">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="d1a34-198">Per la fase vengono mostrati i simboli seguenti per rappresentare l'angolo in base agli intervalli:</span><span class="sxs-lookup"><span data-stu-id="d1a34-198">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

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

<span data-ttu-id="d1a34-199">Gli esempi seguenti illustrano `DumpMachine` per alcuni stati comuni:</span><span class="sxs-lookup"><span data-stu-id="d1a34-199">The following examples show `DumpMachine` for some common states:</span></span>

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
  > <span data-ttu-id="d1a34-200">L'ID di un qubit viene assegnato in fase di esecuzione e non è necessariamente allineato con l'ordine in cui è stato allocato qubit o la relativa posizione all'interno di un registro qubit.</span><span class="sxs-lookup"><span data-stu-id="d1a34-200">The id of a qubit is assigned at runtime and it's not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="d1a34-201">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="d1a34-201">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="d1a34-202">È possibile individuare un ID qubit in Visual Studio inserendo un punto di interruzione nel codice e controllando il valore di una variabile qubit, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d1a34-202">You can figure out a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![Mostra ID qubit in Visual Studio](~/media/qubit_id.png)
  >
  > <span data-ttu-id="d1a34-204">qubit con index `0` in `register2` dispone di ID =`3`, qubit con index `1` con ID =`2`.</span><span class="sxs-lookup"><span data-stu-id="d1a34-204">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="d1a34-205">Riga di comando/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="d1a34-205">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="d1a34-206">È possibile individuare un ID qubit usando la funzione <xref:microsoft.quantum.intrinsic.message> e passando la variabile qubit nel messaggio, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d1a34-206">You can figure out a qubit id by using the <xref:microsoft.quantum.intrinsic.message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="d1a34-207">che può generare questo output:</span><span class="sxs-lookup"><span data-stu-id="d1a34-207">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="d1a34-208">il che significa che qubit con index `0` in `register2` dispone di ID =`3`, qubit con index `1` con ID =`2`.</span><span class="sxs-lookup"><span data-stu-id="d1a34-208">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


***

<span data-ttu-id="d1a34-209"><xref:microsoft.quantum.diagnostics.dumpmachine> fa parte dello spazio dei nomi <xref:microsoft.quantum.diagnostics>, quindi, per utilizzarlo, è necessario aggiungere un'istruzione `open`:</span><span class="sxs-lookup"><span data-stu-id="d1a34-209"><xref:microsoft.quantum.diagnostics.dumpmachine> is part of the  <xref:microsoft.quantum.diagnostics> namespace, so in order to use it you must add an `open` statement:</span></span>

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


### <a name="dumpregister"></a><span data-ttu-id="d1a34-210">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="d1a34-210">DumpRegister</span></span>

<span data-ttu-id="d1a34-211"><xref:microsoft.quantum.diagnostics.dumpregister> funziona come <xref:microsoft.quantum.diagnostics.dumpmachine>, ad eccezione del fatto che accetta anche una matrice di qubits per limitare la quantità di informazioni solo a quella pertinente per il qubits corrispondente.</span><span class="sxs-lookup"><span data-stu-id="d1a34-211"><xref:microsoft.quantum.diagnostics.dumpregister> works like <xref:microsoft.quantum.diagnostics.dumpmachine>, except it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="d1a34-212">Come con <xref:microsoft.quantum.diagnostics.dumpmachine>, le informazioni generate da <xref:microsoft.quantum.diagnostics.dumpregister> dipendono dal computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d1a34-212">As with <xref:microsoft.quantum.diagnostics.dumpmachine>, the information generated by <xref:microsoft.quantum.diagnostics.dumpregister> depends on the target machine.</span></span> <span data-ttu-id="d1a34-213">Per il simulatore Quantum a stato completo scrive nel file la funzione Wave fino a una fase globale del sottosistema Quantum generato dal qubits specificato nello stesso formato <xref:microsoft.quantum.diagnostics.dumpmachine>.</span><span class="sxs-lookup"><span data-stu-id="d1a34-213">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:microsoft.quantum.diagnostics.dumpmachine>.</span></span>  <span data-ttu-id="d1a34-214">Ad esempio, riportare un computer con solo due qubits allocati e nello stato quantico $ $ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{(1 + i)}{2} \ket{10} =-e ^ {-i \ PI/4} ((\frac{1}{\sqrt{2}} \ KET{0}-\frac{(1 + i)}{2} \ket{1}) \otimes \frac{-(1 + i)} {\sqrt{2}} \ket{0}), \end{align} $ $ Calling <xref:microsoft.quantum.diagnostics.dumpregister> per `qubit[0]` genera questo output:</span><span class="sxs-lookup"><span data-stu-id="d1a34-214">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="d1a34-215">e chiamando <xref:microsoft.quantum.diagnostics.dumpregister> per `qubit[1]` genera questo output:</span><span class="sxs-lookup"><span data-stu-id="d1a34-215">and calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="d1a34-216">In generale, lo stato di un registro con un altro registro è uno stato misto anziché uno stato puro.</span><span class="sxs-lookup"><span data-stu-id="d1a34-216">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="d1a34-217">In questo caso, <xref:microsoft.quantum.diagnostics.dumpregister> restituisce il messaggio seguente:</span><span class="sxs-lookup"><span data-stu-id="d1a34-217">In this case, <xref:microsoft.quantum.diagnostics.dumpregister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="d1a34-218">Nell'esempio seguente viene illustrato come è possibile utilizzare sia <xref:microsoft.quantum.diagnostics.dumpregister> che <xref:microsoft.quantum.diagnostics.dumpmachine> nel codice Q #:</span><span class="sxs-lookup"><span data-stu-id="d1a34-218">The following example shows you how you can use both <xref:microsoft.quantum.diagnostics.dumpregister> and <xref:microsoft.quantum.diagnostics.dumpmachine> in your Q# code:</span></span>

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

## <a name="debugging"></a><span data-ttu-id="d1a34-219">Debug</span><span class="sxs-lookup"><span data-stu-id="d1a34-219">Debugging</span></span>

<span data-ttu-id="d1a34-220">Oltre alle funzioni e alle operazioni `Assert` e `Dump`, Q # supporta un sottoinsieme di funzionalità di debug standard di Visual Studio: impostazione dei punti di [interruzione riga](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [esecuzione del codice istruzione per istruzione con F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) e [controllo dei valori delle variabili classiche ](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows)sono tutte possibili durante l'esecuzione del codice sul simulatore.</span><span class="sxs-lookup"><span data-stu-id="d1a34-220">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible during code execution on the simulator.</span></span>

<span data-ttu-id="d1a34-221">Il debug in Visual Studio Code non è ancora supportato.</span><span class="sxs-lookup"><span data-stu-id="d1a34-221">Debugging in Visual Studio Code is not yet supported.</span></span>

