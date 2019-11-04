---
title: Recupero dei conteggi delle risorse | Microsoft Docs
description: Recupero dei conteggi delle risorse docs
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.resourcecounts
ms.openlocfilehash: b28a27c4c1f1e64644fcfb074a731ff7b65cacb6
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184084"
---
## <a name="obtaining-resource-counts"></a><span data-ttu-id="a0074-103">Recupero dei conteggi delle risorse</span><span class="sxs-lookup"><span data-stu-id="a0074-103">Obtaining resource counts</span></span>

<span data-ttu-id="a0074-104">Il costo della simulazione di $n $ qubits in un computer classico si ridimensiona in modo esponenziale con $n $.</span><span class="sxs-lookup"><span data-stu-id="a0074-104">The cost of simulating $n$ qubits on a classical computers scales exponentially with $n$.</span></span> <span data-ttu-id="a0074-105">Questo limita significativamente le dimensioni di una simulazione chimica quantistica che è possibile eseguire con il simulatore di stato completo.</span><span class="sxs-lookup"><span data-stu-id="a0074-105">This greatly limits the size of an quantum chemistry simulation we may perform with the full-state simulator.</span></span> <span data-ttu-id="a0074-106">Per le istanze di chimica di grandi dimensioni, è possibile che si ottengano comunque informazioni utili.</span><span class="sxs-lookup"><span data-stu-id="a0074-106">For large instances of chemistry, we may nevertheless obtain useful information.</span></span> <span data-ttu-id="a0074-107">In questo articolo viene esaminato il modo in cui i costi delle risorse, ad esempio il numero di controlli T-Gates o CNOT, per simulare la chimica possono essere ottenuti in modo automatico tramite il [simulatore di traccia](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span><span class="sxs-lookup"><span data-stu-id="a0074-107">Here, we examine how resource costs, such as the number of T-gates or CNOT gates, for simulating chemistry may be obtained in an automated fashion using the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="a0074-108">Tali informazioni segnalano quando i computer quantum potrebbero essere sufficientemente grandi per eseguire questi algoritmi di chimica quantistica.</span><span class="sxs-lookup"><span data-stu-id="a0074-108">Such information informs us of when quantum computers might be large enough to run these quantum chemistry algorithms.</span></span> <span data-ttu-id="a0074-109">Per informazioni di riferimento, vedere l'esempio `GetGateCount` fornito.</span><span class="sxs-lookup"><span data-stu-id="a0074-109">For reference, see the provided `GetGateCount` sample.</span></span>

<span data-ttu-id="a0074-110">Si supponga di avere già un'istanza di `FermionHamiltonian`, ad esempio, caricata dallo schema Broombridge, come illustrato nell'esempio relativo al [caricamento del file](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) .</span><span class="sxs-lookup"><span data-stu-id="a0074-110">Let us assume that we already have a `FermionHamiltonian` instance, say, loaded from the Broombridge schema as discussed in the [loading-from-file](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) example.</span></span> 

```csharp
    // Filename of Hamiltonian to be loaded.
    var filename = "...";

    // This deserializes Broombridge.
    var problem = Broombridge.Deserializers.DeserializeBroombridge(filename).ProblemDescriptions.First();

    // This is a data structure representing the Jordan-Wigner encoding 
    // of the Hamiltonian that we may pass to a Q# algorithm.
    var qSharpData = problem.ToQSharpFormat();
```

<span data-ttu-id="a0074-111">La sintassi per ottenere le stime delle risorse è quasi identica all'esecuzione dell'algoritmo sul simulatore a stato completo.</span><span class="sxs-lookup"><span data-stu-id="a0074-111">The syntax for obtaining resource estimates is almost identical to running the algorithm on the full-state simulator.</span></span> <span data-ttu-id="a0074-112">È sufficiente scegliere un computer di destinazione diverso.</span><span class="sxs-lookup"><span data-stu-id="a0074-112">We simply choose a different target machine.</span></span> <span data-ttu-id="a0074-113">Ai fini delle stime delle risorse, è sufficiente valutare il costo di un singolo passaggio Trotter o un percorso quantistico creato dalla tecnica Qubitization.</span><span class="sxs-lookup"><span data-stu-id="a0074-113">For the purposes of resource estimates, it suffices to evaluate the cost of a single Trotter step, or a quantum walk created by the Qubitization technique.</span></span> <span data-ttu-id="a0074-114">Il testo standard per richiamare questi algoritmi è il seguente.</span><span class="sxs-lookup"><span data-stu-id="a0074-114">The boilerplate for invoking these algorithms are as follows.</span></span>

```qsharp
//////////////////////////////////////////////////////////////////////////
// Using Trotterization //////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////

/// # Summary
/// This allocates qubits and applies a single Trotter step.
operation RunTrotterStep (qSharpData: JordanWignerEncodingData) : Unit {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    // We use a Product formula, also known as `Trotterization` to
    // simulate the Hamiltonian.
    // The integrator step size does not affect the gate cost of a single step.
    let trotterStepSize = 1.0;
    
    // Order of integrator
    let trotterOrder = 1;
    let (nQubits, (rescaleFactor, oracle)) = TrotterStepOracle(qSharpData, trotterStepSize, trotterOrder);
    
    // We not allocate qubits an run a single step.
    using (qubits = Qubit[nQubits]) {
        oracle(qubits);
        ResetAll(qubits);
    }
}


//////////////////////////////////////////////////////////////////////////
// Using Qubitization ////////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////

/// # Summary
/// This allocates qubits and applies a single qubitization step.
operation RunQubitizationStep (qSharpData: JordanWignerEncodingData) : Double {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    let (nQubits, (l1Norm, oracle)) = QubitizationOracle(qSharpData);
    
    // We now allocate qubits and run a single step.
    using (qubits = Qubit[nQubits]) {
        oracle(qubits);
        ResetAll(qubits);
    }
    
    return l1Norm;
}
```

<span data-ttu-id="a0074-115">È ora possibile configurare il simulatore di traccia per tenere traccia delle risorse a cui si è interessati.</span><span class="sxs-lookup"><span data-stu-id="a0074-115">We now configure the trace simulator to track the resources we are interested in.</span></span> <span data-ttu-id="a0074-116">In questo caso, vengono conteggiate le operazioni Quantum primitive impostando il flag di `usePrimitiveOperationsCounter` su `true`.</span><span class="sxs-lookup"><span data-stu-id="a0074-116">In this case, we count primitive quantum operations by setting the `usePrimitiveOperationsCounter` flag to `true`.</span></span> <span data-ttu-id="a0074-117">Un `throwOnUnconstraintMeasurement` di dettaglio tecnico è impostato su `false` per evitare eccezioni nei casi in cui il codice Q # non asserisce correttamente probabiltiy di risultati di misurazione, se vengono eseguiti.</span><span class="sxs-lookup"><span data-stu-id="a0074-117">A technical detail `throwOnUnconstraintMeasurement` is set to `false` to avoid exceptions in cases where the Q# code does not correctly assert of probabiltiy of measurement outcomes, if any are performed.</span></span>

```csharp
private static QCTraceSimulator CreateAndConfigureTraceSim()
{
    // Create and configure Trace Simulator
    var config = new QCTraceSimulatorConfiguration()
    {
        usePrimitiveOperationsCounter = true,
        throwOnUnconstraintMeasurement = false
    };

    return new QCTraceSimulator(config);
}
```

<span data-ttu-id="a0074-118">A questo punto è possibile eseguire l'algoritmo Quantum dal programma driver come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="a0074-118">We now run the quantum algorithm from the driver program as follows.</span></span>

```csharp
// Instantiate a trace simulator instance
QCTraceSimulator sim = CreateAndConfigureTraceSim();

// Run the quantum algorithm on the trace simulator.
RunQubitizationStep.Run(sim, qSharpData);

// Print all resource counts to file.
var gateStats = sim.ToCSV();
foreach (var x in gateStats)
{
    System.IO.File.WriteAllLines($"QubitizationGateCountEstimates.{x.Key}.csv", new string[] { x.Value });
}
```