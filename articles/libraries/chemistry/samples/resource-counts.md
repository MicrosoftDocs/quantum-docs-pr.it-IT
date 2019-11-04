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
## <a name="obtaining-resource-counts"></a>Recupero dei conteggi delle risorse

Il costo della simulazione di $n $ qubits in un computer classico si ridimensiona in modo esponenziale con $n $. Questo limita significativamente le dimensioni di una simulazione chimica quantistica che è possibile eseguire con il simulatore di stato completo. Per le istanze di chimica di grandi dimensioni, è possibile che si ottengano comunque informazioni utili. In questo articolo viene esaminato il modo in cui i costi delle risorse, ad esempio il numero di controlli T-Gates o CNOT, per simulare la chimica possono essere ottenuti in modo automatico tramite il [simulatore di traccia](xref:microsoft.quantum.machines.qc-trace-simulator.intro). Tali informazioni segnalano quando i computer quantum potrebbero essere sufficientemente grandi per eseguire questi algoritmi di chimica quantistica. Per informazioni di riferimento, vedere l'esempio `GetGateCount` fornito.

Si supponga di avere già un'istanza di `FermionHamiltonian`, ad esempio, caricata dallo schema Broombridge, come illustrato nell'esempio relativo al [caricamento del file](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) . 

```csharp
    // Filename of Hamiltonian to be loaded.
    var filename = "...";

    // This deserializes Broombridge.
    var problem = Broombridge.Deserializers.DeserializeBroombridge(filename).ProblemDescriptions.First();

    // This is a data structure representing the Jordan-Wigner encoding 
    // of the Hamiltonian that we may pass to a Q# algorithm.
    var qSharpData = problem.ToQSharpFormat();
```

La sintassi per ottenere le stime delle risorse è quasi identica all'esecuzione dell'algoritmo sul simulatore a stato completo. È sufficiente scegliere un computer di destinazione diverso. Ai fini delle stime delle risorse, è sufficiente valutare il costo di un singolo passaggio Trotter o un percorso quantistico creato dalla tecnica Qubitization. Il testo standard per richiamare questi algoritmi è il seguente.

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

È ora possibile configurare il simulatore di traccia per tenere traccia delle risorse a cui si è interessati. In questo caso, vengono conteggiate le operazioni Quantum primitive impostando il flag di `usePrimitiveOperationsCounter` su `true`. Un `throwOnUnconstraintMeasurement` di dettaglio tecnico è impostato su `false` per evitare eccezioni nei casi in cui il codice Q # non asserisce correttamente probabiltiy di risultati di misurazione, se vengono eseguiti.

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

A questo punto è possibile eseguire l'algoritmo Quantum dal programma driver come indicato di seguito.

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