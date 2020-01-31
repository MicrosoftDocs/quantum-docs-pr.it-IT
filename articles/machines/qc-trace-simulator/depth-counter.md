---
title: Contatore profondità | Simulatore di traccia del computer Quantum | Microsoft Docs
description: Panoramica del simulatore di traccia del computer quantistico
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: 07f927c794e2c62e53e4e053b5bc683d24bbed8d
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820471"
---
# <a name="depth-counter"></a><span data-ttu-id="f7cff-103">Contatore profondità</span><span class="sxs-lookup"><span data-stu-id="f7cff-103">Depth Counter</span></span>

<span data-ttu-id="f7cff-104">Il `Depth Counter` fa parte del [simulatore di traccia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Quantum computer.</span><span class="sxs-lookup"><span data-stu-id="f7cff-104">The `Depth Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>
<span data-ttu-id="f7cff-105">Viene usato per raccogliere i conteggi della profondità di ogni operazione richiamata in un programma Quantum.</span><span class="sxs-lookup"><span data-stu-id="f7cff-105">It is used to gather counts of the depth of every operation invoked in a quantum program.</span></span> <span data-ttu-id="f7cff-106">Tutte le operazioni da <xref:microsoft.quantum.intrinsic> sono espresse in termini di singole rotazioni qubit, T Gate, Single qubit Clifford Gates, CNOT Gates e misurazioni di più qubit Pauli osservabili.</span><span class="sxs-lookup"><span data-stu-id="f7cff-106">All operations from <xref:microsoft.quantum.intrinsic> are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="f7cff-107">Gli utenti possono impostare la profondità per ognuna delle operazioni primitive tramite il campo `gateTimes` di <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span><span class="sxs-lookup"><span data-stu-id="f7cff-107">Users can set the depth for each of the primitive operations via the `gateTimes` field of <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span></span>

<span data-ttu-id="f7cff-108">Per impostazione predefinita, tutte le operazioni hanno la profondità 0 ad eccezione di T Gate con profondità 1.</span><span class="sxs-lookup"><span data-stu-id="f7cff-108">By default, all operations have depth 0 except the T gate which has depth 1.</span></span> <span data-ttu-id="f7cff-109">Ciò significa che, per impostazione predefinita, viene calcolata solo la profondità T delle operazioni (che è spesso auspicabile).</span><span class="sxs-lookup"><span data-stu-id="f7cff-109">This means that by default, only the T depth of operations is computed (which is often desirable).</span></span> <span data-ttu-id="f7cff-110">Le statistiche raccolte vengono aggregate su tutti i bordi del grafico delle chiamate di operazioni.</span><span class="sxs-lookup"><span data-stu-id="f7cff-110">Collected statistics are aggregated over all the edges of the operations call graph.</span></span> 

<span data-ttu-id="f7cff-111">È ora possibile calcolare la profondità <xref:microsoft.quantum.intrinsic.t> dell'operazione di <xref:microsoft.quantum.intrinsic.ccnot>.</span><span class="sxs-lookup"><span data-stu-id="f7cff-111">Let us now compute the <xref:microsoft.quantum.intrinsic.t> depth of the <xref:microsoft.quantum.intrinsic.ccnot> operation.</span></span> <span data-ttu-id="f7cff-112">Si userà il codice di esempio Q # seguente:</span><span class="sxs-lookup"><span data-stu-id="f7cff-112">We will use the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a><span data-ttu-id="f7cff-113">Uso del contatore depth in C# un programma</span><span class="sxs-lookup"><span data-stu-id="f7cff-113">Using Depth Counter within a C# Program</span></span>

<span data-ttu-id="f7cff-114">Per verificare che `CCNOT` abbia `T` Depth 5 e `ApplySampleWithCCNOT` abbia `T` profondità 6 è possibile usare il codice C# seguente:</span><span class="sxs-lookup"><span data-stu-id="f7cff-114">To check that `CCNOT` has `T` depth 5 and `ApplySampleWithCCNOT` has `T` depth 6 we can use the following C# code:</span></span>

```csharp 
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.useDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="f7cff-115">La prima parte del programma esegue `ApplySampleWithCCNOT`.</span><span class="sxs-lookup"><span data-stu-id="f7cff-115">The first part of the program executes `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="f7cff-116">Nella seconda parte viene usato il metodo `QCTraceSimulator.GetMetric` per ottenere la profondità `T` di `CCNOT` e `ApplySampleWithCCNOT`:</span><span class="sxs-lookup"><span data-stu-id="f7cff-116">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the `T` depth of `CCNOT` and `ApplySampleWithCCNOT`:</span></span> 

```csharp
double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="f7cff-117">Infine, per restituire tutte le statistiche raccolte da `Depth Counter` in formato CSV, è possibile usare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f7cff-117">Finally, to output all the statistics collected by `Depth Counter` in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a><span data-ttu-id="f7cff-118">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="f7cff-118">See also</span></span> ##

- <span data-ttu-id="f7cff-119">Panoramica di Quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="f7cff-119">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
