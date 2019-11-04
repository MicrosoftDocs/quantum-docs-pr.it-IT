---
title: Simulatori quantistici e applicazioni host | Microsoft Docs
description: Descrive come eseguire i simulatori quantistici con un linguaggio .NET per il calcolo classico, in genere C# o Q#.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines
ms.openlocfilehash: 14aed75ed0ed192f88699b1c7dbacfae23f74642
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442226"
---
# <a name="quantum-simulators-and-host-applications"></a><span data-ttu-id="75f97-103">Simulatori quantistici e applicazioni host</span><span class="sxs-lookup"><span data-stu-id="75f97-103">Quantum simulators and host applications</span></span>

## <a name="what-youll-learn"></a><span data-ttu-id="75f97-104">Contenuto dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="75f97-104">What You'll Learn</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="75f97-105">Come vengono eseguiti gli algoritmi quantistici</span><span class="sxs-lookup"><span data-stu-id="75f97-105">How quantum algorithms are executed</span></span>
> * <span data-ttu-id="75f97-106">Quali simulatori quantistici sono inclusi in questa versione</span><span class="sxs-lookup"><span data-stu-id="75f97-106">What quantum simulators are included in this release</span></span>
> * <span data-ttu-id="75f97-107">Come scrivere un driver C# per l'algoritmo quantistico</span><span class="sxs-lookup"><span data-stu-id="75f97-107">How to write a C# driver for your quantum algorithm</span></span>

## <a name="the-quantum-development-kit-execution-model"></a><span data-ttu-id="75f97-108">Modello di esecuzione di Quantum Development Kit</span><span class="sxs-lookup"><span data-stu-id="75f97-108">The Quantum Development Kit Execution Model</span></span>

<span data-ttu-id="75f97-109">In [Scrittura di un programma quantistico](xref:microsoft.quantum.write-program), l'algoritmo quantistico è stato eseguito passando un oggetto `QuantumSimulator` al metodo `Run` della classe dell'algoritmo.</span><span class="sxs-lookup"><span data-stu-id="75f97-109">In [Writing a quantum program](xref:microsoft.quantum.write-program), we executed our quantum algorithm by passing a `QuantumSimulator` object to the algorithm class's `Run` method.</span></span>
<span data-ttu-id="75f97-110">La classe `QuantumSimulator` esegue l'algoritmo quantistico simulando completamente il vettore di stato quantistico, perfetto per l'esecuzione e il test di `Teleport`.</span><span class="sxs-lookup"><span data-stu-id="75f97-110">The `QuantumSimulator` class executes the quantum algorithm by fully simulating the quantum state vector, which is perfect for running and testing `Teleport`.</span></span>
<span data-ttu-id="75f97-111">Per altre informazioni sui vettori di stato quantistici, vedere la [Guida ai concetti](xref:microsoft.quantum.concepts.intro).</span><span class="sxs-lookup"><span data-stu-id="75f97-111">See the [Concepts guide](xref:microsoft.quantum.concepts.intro) for more on quantum state vectors.</span></span>

<span data-ttu-id="75f97-112">Per eseguire un algoritmo quantistico, è possibile usare altri computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="75f97-112">Other target machines may be used to run a quantum algorithm.</span></span>
<span data-ttu-id="75f97-113">Il computer è responsabile della fornitura di implementazioni di primitive quantistiche per l'algoritmo.</span><span class="sxs-lookup"><span data-stu-id="75f97-113">The machine is responsible for providing implementations of quantum primitives for the algorithm.</span></span>
<span data-ttu-id="75f97-114">Sono incluse operazioni primitive come H, CNOT e misura, oltre alla gestione e al monitoraggio di qubit.</span><span class="sxs-lookup"><span data-stu-id="75f97-114">This includes primitive operations such as H, CNOT, and Measure, as well as qubit management and tracking.</span></span>
<span data-ttu-id="75f97-115">Classi diverse di computer quantistici rappresentano modelli di esecuzione diversi per lo stesso algoritmo quantistico.</span><span class="sxs-lookup"><span data-stu-id="75f97-115">Different classes of quantum machines represent different execution models for the same quantum algorithm.</span></span>

<span data-ttu-id="75f97-116">Ogni tipo di computer quantistico può fornire implementazioni diverse di tali primitive.</span><span class="sxs-lookup"><span data-stu-id="75f97-116">Each type of quantum machine may provide different implementations of these primitives.</span></span>
<span data-ttu-id="75f97-117">Ad esempio, il simulatore di traccia del computer quantistico incluso nel kit di sviluppo non esegue alcuna simulazione.</span><span class="sxs-lookup"><span data-stu-id="75f97-117">For instance, the quantum computer trace simulator included in the development kit doesn't do any simulation at all.</span></span>
<span data-ttu-id="75f97-118">Piuttosto, tiene traccia dell'utilizzo di gate, qubit e altre risorse per l'algoritmo.</span><span class="sxs-lookup"><span data-stu-id="75f97-118">Rather, it tracks gate, qubit, and other resource usage for the algorithm.</span></span>

### <a name="quantum-machines"></a><span data-ttu-id="75f97-119">Computer quantistici</span><span class="sxs-lookup"><span data-stu-id="75f97-119">Quantum Machines</span></span>

<span data-ttu-id="75f97-120">In futuro, verranno definite ulteriori classi di computer quantistici per supportare altri tipi di simulazione e per supportare l'esecuzione in computer quantistici topologici.</span><span class="sxs-lookup"><span data-stu-id="75f97-120">In the future, we will define additional quantum machine classes to support other types of simulation and to support execution on topological quantum computers.</span></span>
<span data-ttu-id="75f97-121">Consentire all'algoritmo di rimanere costante e variando al contempo l'implementazione del computer sottostante semplifica il test e il debug di un algoritmo in simulazione, per poterlo eseguire nell'hardware reale con la certezza che l'algoritmo non è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="75f97-121">Allowing the algorithm to stay constant while varying the underlying machine implementation makes it easy to test and debug an algorithm in simulation and then run it on real hardware with confidence that the algorithm hasn't changed.</span></span>

### <a name="whats-included-in-this-release"></a><span data-ttu-id="75f97-122">Contenuti di questa versione</span><span class="sxs-lookup"><span data-stu-id="75f97-122">What's Included in this Release</span></span>

<span data-ttu-id="75f97-123">Questa versione di Quantum Developer Kit include numerose classi di computer quantistico.</span><span class="sxs-lookup"><span data-stu-id="75f97-123">This release of the quantum developer kit includes several quantum machine classes.</span></span>
<span data-ttu-id="75f97-124">Tutte le classi sono definite nello spazio dei nomi `Microsoft.Quantum.Simulation.Simulators`.</span><span class="sxs-lookup"><span data-stu-id="75f97-124">All of them are defined in the `Microsoft.Quantum.Simulation.Simulators` namespace.</span></span>

* <span data-ttu-id="75f97-125">Un [simulatore di vettori di stato completo](xref:microsoft.quantum.machines.full-state-simulator), la classe `QuantumSimulator`.</span><span class="sxs-lookup"><span data-stu-id="75f97-125">A [full state vector simulator](xref:microsoft.quantum.machines.full-state-simulator), the `QuantumSimulator` class.</span></span>
* <span data-ttu-id="75f97-126">Uno [strumento di stima risorse semplice](xref:microsoft.quantum.machines.resources-estimator), la classe `ResourcesEstimator`, consente un'analisi generale delle risorse necessarie per eseguire un algoritmo quantistico.</span><span class="sxs-lookup"><span data-stu-id="75f97-126">A [simple resources estimator](xref:microsoft.quantum.machines.resources-estimator), the `ResourcesEstimator` class, it allows a top level analysis of the resources needed to run a quantum algorithm.</span></span>
* <span data-ttu-id="75f97-127">Un [strumento di stima delle risorse basato su traccia](xref:microsoft.quantum.machines.qc-trace-simulator.intro), la classe `QCTraceSimulator`, consente l'analisi avanzata dei consumi di risorse per l'intero grafico di chiamata dell'algoritmo.</span><span class="sxs-lookup"><span data-stu-id="75f97-127">A [trace-based resource estimator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), the `QCTraceSimulator` class, it allows advanced analysis of resources consumptions for the algorithm's entire call-graph.</span></span>
* <span data-ttu-id="75f97-128">Un [simulatore di Toffoli](xref:microsoft.quantum.machines.toffoli-simulator), la classe `ToffoliSimulator`.</span><span class="sxs-lookup"><span data-stu-id="75f97-128">A [Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator), the `ToffoliSimulator` class.</span></span>

## <a name="writing-a-host-application"></a><span data-ttu-id="75f97-129">Scrittura di un'applicazione host</span><span class="sxs-lookup"><span data-stu-id="75f97-129">Writing a host application</span></span>

<span data-ttu-id="75f97-130">In [Scrittura di un programma quantistico](xref:microsoft.quantum.write-program), è stato creato un semplice driver C# per l'algoritmo di teletrasporto.</span><span class="sxs-lookup"><span data-stu-id="75f97-130">In [Writing a quantum program](xref:microsoft.quantum.write-program), we wrote a simple C# driver for our teleport algorithm.</span></span> <span data-ttu-id="75f97-131">Gli scopi principali di un driver C# sono quattro:</span><span class="sxs-lookup"><span data-stu-id="75f97-131">A C# driver has 4 main purposes:</span></span>

* <span data-ttu-id="75f97-132">Creazione del computer di destinazione</span><span class="sxs-lookup"><span data-stu-id="75f97-132">Constructing the target machine</span></span>
* <span data-ttu-id="75f97-133">Calcolo degli argomenti necessari per l'algoritmo quantistico</span><span class="sxs-lookup"><span data-stu-id="75f97-133">Computing any arguments required for the quantum algorithm</span></span>
* <span data-ttu-id="75f97-134">Esecuzione dell'algoritmo quantistico tramite il simulatore</span><span class="sxs-lookup"><span data-stu-id="75f97-134">Running the quantum algorithm using the simulator</span></span>
* <span data-ttu-id="75f97-135">Elaborazione del risultato dell'operazione</span><span class="sxs-lookup"><span data-stu-id="75f97-135">Processing the result of the operation</span></span>

<span data-ttu-id="75f97-136">Ora verrà illustrato ogni passaggio in dettaglio.</span><span class="sxs-lookup"><span data-stu-id="75f97-136">Here we'll discuss each step in more detail.</span></span>

### <a name="constructing-the-target-machine"></a><span data-ttu-id="75f97-137">Creazione del computer di destinazione</span><span class="sxs-lookup"><span data-stu-id="75f97-137">Constructing the Target Machine</span></span>

<span data-ttu-id="75f97-138">I computer quantistici sono istanze di classi .NET normali, che vengono quindi create richiamandone il costruttore, come per qualsiasi altra classe .NET.</span><span class="sxs-lookup"><span data-stu-id="75f97-138">Quantum machines are instances of normal .NET classes, so they are created by invoking their constructor, just like any .NET class.</span></span>
<span data-ttu-id="75f97-139">Alcuni simulatori, incluso `QuantumSimulator`, implementano l'interfaccia .NET <xref:System.IDisposable?displayProperty=nameWithType> e devono quindi essere racchiusi in un'istruzione `using` C#.</span><span class="sxs-lookup"><span data-stu-id="75f97-139">Some simulators, including the `QuantumSimulator`, implement the .NET <xref:System.IDisposable?displayProperty=nameWithType> interface, and so should be wrapped in a C# `using` statement.</span></span>

### <a name="computing-arguments-for-the-algorithm"></a><span data-ttu-id="75f97-140">Calcolo degli argomenti per l'algoritmo</span><span class="sxs-lookup"><span data-stu-id="75f97-140">Computing Arguments for the Algorithm</span></span>

<span data-ttu-id="75f97-141">Nell'esempio `Teleport` sono stati calcolati alcuni argomenti relativamente artificiali da passare all'algoritmo quantistico.</span><span class="sxs-lookup"><span data-stu-id="75f97-141">In our `Teleport` example, we computed some relatively artificial arguments to pass to our quantum algorithm.</span></span>
<span data-ttu-id="75f97-142">In genere, tuttavia, l'algoritmo richiede grandi quantità di dati ed è più facile fornirli dal driver classico.</span><span class="sxs-lookup"><span data-stu-id="75f97-142">More typically, however, there is significant data required by the quantum algorithm, and it is easiest to provide it from the classical driver.</span></span>

<span data-ttu-id="75f97-143">Ad esempio, quando si esegue una simulazione chimica, l'algoritmo quantistico richiede una tabella di grandi dimensioni di integrali di interazione tra orbitali molecolari.</span><span class="sxs-lookup"><span data-stu-id="75f97-143">For instance, when doing chemical simulations, the quantum algorithm requires a large table of molecular orbital interaction integrals.</span></span>
<span data-ttu-id="75f97-144">Questi vengono normalmente letti da un file che viene fornito quando si esegue l'algoritmo.</span><span class="sxs-lookup"><span data-stu-id="75f97-144">Generally these are read in from a file that is provided when running the algorithm.</span></span>
<span data-ttu-id="75f97-145">Poiché Q# non dispone di un meccanismo per accedere al file system, questo tipo di dati viene raccolto in modo più efficace dal driver classico e quindi i dati vengono passati al metodo `Run` dell'algoritmo quantistico.</span><span class="sxs-lookup"><span data-stu-id="75f97-145">Since Q# does not have a mechanism for accessing the file system, this sort of data is best collected by the classical driver and then passed to the quantum algorithm's `Run` method.</span></span>

<span data-ttu-id="75f97-146">Il driver classico gioca un ruolo fondamentale anche nel caso dei metodi variazionali.</span><span class="sxs-lookup"><span data-stu-id="75f97-146">Another case where the classical driver plays a key role is in variational methods.</span></span>
<span data-ttu-id="75f97-147">In questa classe di algoritmi uno stato quantistico viene preparato in base ad alcuni parametri classici e tale stato viene usato per calcolare un valore di interesse.</span><span class="sxs-lookup"><span data-stu-id="75f97-147">In this class of algorithms, a quantum state is prepared based on some classical parameters, and that state is used to compute some value of interest.</span></span>
<span data-ttu-id="75f97-148">I parametri vengono rettificati in base a un tipo di algoritmo hill climbing o di apprendimento automatico e l'algoritmo quantistico viene eseguito nuovamente.</span><span class="sxs-lookup"><span data-stu-id="75f97-148">The parameters are adjusted based on some type of hill climbing or machine learning algorithm and the quantum algorithm run again.</span></span>
<span data-ttu-id="75f97-149">Per questi algoritmi, l'algoritmo hill climbing stesso viene implementato in modo ottimale come funzione puramente classica chiamata dal driver classico. I risultati dell'algoritmo hill climbing vengono quindi passati alla successiva esecuzione dell'algoritmo quantistico.</span><span class="sxs-lookup"><span data-stu-id="75f97-149">For such algorithms, the hill climbing algorithm itself is best implemented as a purely classical function that is called by the classical driver; the results of the hill climbing are then passed to the next execution of the quantum algorithm.</span></span>

### <a name="running-the-quantum-algorithm"></a><span data-ttu-id="75f97-150">Esecuzione dell'algoritmo quantistico</span><span class="sxs-lookup"><span data-stu-id="75f97-150">Running the Quantum Algorithm</span></span>

<span data-ttu-id="75f97-151">Questa parte è in genere molto semplice.</span><span class="sxs-lookup"><span data-stu-id="75f97-151">This part is generally very straightforward.</span></span>
<span data-ttu-id="75f97-152">Ogni operazione Q# viene compilata in una classe che fornisce un metodo `Run` statico.</span><span class="sxs-lookup"><span data-stu-id="75f97-152">Each Q# operation is compiled into a class that provides a static `Run` method.</span></span>
<span data-ttu-id="75f97-153">Gli argomenti di questo metodo vengono forniti dalla tupla di argomenti bidimensionali dell'operazione stessa, oltre a un primo argomento aggiuntivo che è il simulatore da usare per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="75f97-153">The arguments to this method are given by the flattened argument tuple of the operation itself, plus an additional first argument which is the simulator to execute with.</span></span> <span data-ttu-id="75f97-154">Per un'operazione che prevede la tupla denominata di tipo `(a: String, (b: Double, c: Double))` la controparte bidimensionale è di tipo `(String a, Double b, Double c)`.</span><span class="sxs-lookup"><span data-stu-id="75f97-154">For an operation that expects the named tuple of type `(a: String, (b: Double, c: Double))` its flattened counterpart is of type `(String a, Double b, Double c)`.</span></span>


<span data-ttu-id="75f97-155">Il passaggio di argomenti a un metodo `Run` prevede alcune particolarità:</span><span class="sxs-lookup"><span data-stu-id="75f97-155">There are some subtleties when passing arguments to a `Run` method:</span></span>

* <span data-ttu-id="75f97-156">Le matrici devono essere racchiuse in un oggetto `Microsoft.Quantum.Simulation.Core.QArray<T>`.</span><span class="sxs-lookup"><span data-stu-id="75f97-156">Arrays must be wrapped in a `Microsoft.Quantum.Simulation.Core.QArray<T>` object.</span></span>
    <span data-ttu-id="75f97-157">Una classe `QArray` dispone di un costruttore che può eseguire qualsiasi raccolta ordinata (`IEnumerable<T>`) di oggetti appropriati.</span><span class="sxs-lookup"><span data-stu-id="75f97-157">A `QArray` class has a constructor that can take any ordered collection (`IEnumerable<T>`) of appropriate objects.</span></span>
* <span data-ttu-id="75f97-158">La tupla vuota, `()` in Q#, è rappresentata da `QVoid.Instance` in C#.</span><span class="sxs-lookup"><span data-stu-id="75f97-158">The empty tuple, `()` in Q#, is represented by `QVoid.Instance` in C#.</span></span>
* <span data-ttu-id="75f97-159">Le tuple non vuote sono rappresentate come istanze di `ValueTuple` .NET.</span><span class="sxs-lookup"><span data-stu-id="75f97-159">Non-empty tuples are represented as .NET `ValueTuple` instances.</span></span>
* <span data-ttu-id="75f97-160">I tipi definiti dall'utente Q# vengono passati come tipo di base.</span><span class="sxs-lookup"><span data-stu-id="75f97-160">Q# user-defined types are passed as their base type.</span></span>
* <span data-ttu-id="75f97-161">Per passare un'operazione o una funzione a un metodo `Run`, è necessario ottenere un'istanza della classe dell'operazione o della funzione, usando il metodo `Get<>` del simulatore.</span><span class="sxs-lookup"><span data-stu-id="75f97-161">To pass an operation or a function to a `Run` method, you have to obtain an   instance of the operation's or function's class, using the simulator's `Get<>` method.</span></span>

### <a name="processing-the-results"></a><span data-ttu-id="75f97-162">Elaborazione dei risultati</span><span class="sxs-lookup"><span data-stu-id="75f97-162">Processing the Results</span></span>

<span data-ttu-id="75f97-163">I risultati dell'algoritmo quantistico vengono restituiti dal metodo `Run`.</span><span class="sxs-lookup"><span data-stu-id="75f97-163">The results of the quantum algorithm are returned from the `Run` method.</span></span>
<span data-ttu-id="75f97-164">Il metodo `Run` viene eseguito in modo asincrono in modo che restituisca un'istanza di <xref:System.Threading.Tasks.Task`1>.</span><span class="sxs-lookup"><span data-stu-id="75f97-164">The `Run` method executes asynchronously thus it returns an instance of <xref:System.Threading.Tasks.Task`1>.</span></span>
<span data-ttu-id="75f97-165">Sono disponibili diversi modi per ottenere i risultati dell'operazione effettiva.</span><span class="sxs-lookup"><span data-stu-id="75f97-165">There are multiple ways to get the actual operation's results.</span></span> <span data-ttu-id="75f97-166">Il più semplice consiste nell'usare la [proprietà `Result`](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task-1.result) di `Task`:</span><span class="sxs-lookup"><span data-stu-id="75f97-166">The simplest is by using the `Task`'s [`Result` property](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task-1.result):</span></span>

```csharp
    var res = BellTest.Run(sim, 1000, initial).Result;
```
<span data-ttu-id="75f97-167">ma anche altre tecniche, ad esempio l'uso del [metodo `Wait`](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task.wait) o della [parola chiave `await`](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await) C#, funzioneranno.</span><span class="sxs-lookup"><span data-stu-id="75f97-167">but other techniques, like using the [`Wait` method](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task.wait) or C# [`await` keyword](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await) will also work.</span></span>

<span data-ttu-id="75f97-168">Come per gli argomenti, le tuple Q# sono rappresentate come istanze di `ValueTuple` e le matrici Q# sono rappresentate come istanze di `QArray`.</span><span class="sxs-lookup"><span data-stu-id="75f97-168">As with arguments, Q# tuples are represented as `ValueTuple` instances and Q# arrays are represented as `QArray` instances.</span></span>
<span data-ttu-id="75f97-169">I tipi definiti dall'utente vengono restituiti come tipi di base.</span><span class="sxs-lookup"><span data-stu-id="75f97-169">User-defined types are returned as their base types.</span></span>
<span data-ttu-id="75f97-170">La tupla vuota, `()`, viene restituita come istanza della classe `QVoid`.</span><span class="sxs-lookup"><span data-stu-id="75f97-170">The empty tuple, `()`, is returned as an instance of the `QVoid` class.</span></span>

<span data-ttu-id="75f97-171">Molti algoritmi quantistici richiedono una sostanziale post-elaborazione per la derivazione di risposte utili.</span><span class="sxs-lookup"><span data-stu-id="75f97-171">Many quantum algorithms require substantial post-processing to derive useful answers.</span></span>
<span data-ttu-id="75f97-172">Ad esempio, la parte quantistica dell'algoritmo di Shor è solo l'inizio di un calcolo che trova i fattori di un numero.</span><span class="sxs-lookup"><span data-stu-id="75f97-172">For instance, the quantum part of Shor's algorithm is just the beginning of a computation that finds the factors of a number.</span></span>

<span data-ttu-id="75f97-173">Nella maggior parte dei casi, è più semplice eseguire questo tipo di post-elaborazione nel driver classico.</span><span class="sxs-lookup"><span data-stu-id="75f97-173">In most cases, it is simplest and easiest to do this sort of post-processing in the classical driver.</span></span>
<span data-ttu-id="75f97-174">Solo il driver classico può segnalare i risultati all'utente o scriverli su disco.</span><span class="sxs-lookup"><span data-stu-id="75f97-174">Only the classical driver can report results to the user or write them to disk.</span></span>
<span data-ttu-id="75f97-175">Il driver classico avrà accesso alle librerie di analisi e ad altre funzioni matematiche non esposte in Q#.</span><span class="sxs-lookup"><span data-stu-id="75f97-175">The classical driver will have access to analytical libraries and other mathematical functions that are not exposed in Q#.</span></span>


## <a name="failures"></a><span data-ttu-id="75f97-176">Errori</span><span class="sxs-lookup"><span data-stu-id="75f97-176">Failures</span></span>

<span data-ttu-id="75f97-177">Quando viene raggiunta l'istruzione `fail` Q# durante l'esecuzione di un'operazione, viene generata un'eccezione `ExecutionFailException`.</span><span class="sxs-lookup"><span data-stu-id="75f97-177">When the Q# `fail` statement is reached during the execution of an operation, an `ExecutionFailException` is thrown.</span></span>

<span data-ttu-id="75f97-178">A causa dell'utilizzo di `System.Task` nel metodo `Run`, l'eccezione generata come risultato di un'istruzione `fail` verrà racchiusa in un'eccezione `System.AggregateException`.</span><span class="sxs-lookup"><span data-stu-id="75f97-178">Due to the use of `System.Task` in the `Run` method, the exception thrown as a result of a `fail` statement will be wrapped into a `System.AggregateException`.</span></span>
<span data-ttu-id="75f97-179">Per individuare il motivo effettivo dell'errore, è necessario eseguire un'iterazione nella `AggregateException` 
`InnerExceptions`, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="75f97-179">To find the actual reason for the failure, you need to iterate into the `AggregateException` 
`InnerExceptions`, for example:</span></span>

```csharp

            try
            {
                using(var sim = new QuantumSimulator())
                {
                    /// call your operations here...
                }
            }
            catch (AggregateException e)
            {
                // Unwrap AggregateException to get the message from Q# fail statement.
                // Go through all inner exceptions.
                foreach (Exception inner in e.InnerExceptions)
                {
                    // If the exception of type ExecutionFailException
                    if (inner is ExecutionFailException failException)
                    {
                        // Print the message it contains
                        Console.WriteLine($" {failException.Message}");
                    }
                }
            }
```

## <a name="other-classical-languages"></a><span data-ttu-id="75f97-180">Altri linguaggi classici</span><span class="sxs-lookup"><span data-stu-id="75f97-180">Other Classical Languages</span></span>

<span data-ttu-id="75f97-181">Sebbene gli esempi forniti siano scritti in C#, F# e Python, Quantum Development Kit supporta anche la scrittura di programmi host classici in altri linguaggi.</span><span class="sxs-lookup"><span data-stu-id="75f97-181">While the samples we have provided are in C#, F#, and Python, the Quantum Development Kit also supports writing classical host programs in other languages.</span></span>
<span data-ttu-id="75f97-182">Se, ad esempio, si vuole scrivere un programma host in Visual Basic, [non dovrebbero verificarsi problemi](https://github.com/tcNickolas/MiscQSharp/blob/master/Quantum_VBNet/README.md#using-q-with-visual-basic-net).</span><span class="sxs-lookup"><span data-stu-id="75f97-182">For example, if you want to write a host program in Visual Basic, [it should work just fine](https://github.com/tcNickolas/MiscQSharp/blob/master/Quantum_VBNet/README.md#using-q-with-visual-basic-net).</span></span>
