---
title: Contatore di profondità-Quantum Development Kit
description: 'Informazioni sul contatore Microsoft QDK Depth, che usa il simulatore di traccia Quantum per raccogliere i conteggi della profondità di ogni operazione richiamata in un programma Q #.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: 811e387fedf547d2681518ae0bb525c13dc84ff4
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871128"
---
# <a name="quantum-trace-simulator-depth-counter"></a><span data-ttu-id="07147-103">Simulatore di traccia Quantum: contatore Depth</span><span class="sxs-lookup"><span data-stu-id="07147-103">Quantum trace simulator: depth counter</span></span>

<span data-ttu-id="07147-104">Il contatore Depth è parte del [simulatore di traccia Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Development Kit Quantum.</span><span class="sxs-lookup"><span data-stu-id="07147-104">The depth counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>
<span data-ttu-id="07147-105">È possibile usarlo per raccogliere i conteggi che rappresentano il limite inferiore della profondità di ogni operazione richiamata in un programma Quantum.</span><span class="sxs-lookup"><span data-stu-id="07147-105">You can use it to gather counts that represent the lower bound of the depth of every operation invoked in a quantum program.</span></span> 

## <a name="depth-values"></a><span data-ttu-id="07147-106">Valori di profondità</span><span class="sxs-lookup"><span data-stu-id="07147-106">Depth values</span></span>

<span data-ttu-id="07147-107">Per impostazione predefinita, tutte le operazioni hanno una profondità di **0** tranne l' `T` operazione, che ha una profondità di **1**.</span><span class="sxs-lookup"><span data-stu-id="07147-107">By default, all operations have a depth of **0** except the `T` operation, which has a depth of **1**.</span></span> <span data-ttu-id="07147-108">Ciò significa che, per impostazione predefinita, `T` viene calcolata solo la profondità delle operazioni (che è spesso auspicabile).</span><span class="sxs-lookup"><span data-stu-id="07147-108">This means that by default, only the `T` depth of operations is computed (which is often desirable).</span></span> <span data-ttu-id="07147-109">Il contatore Depth aggrega e raccoglie le statistiche su tutti i bordi del [grafico delle chiamate](https://en.wikipedia.org/wiki/Call_graph)dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="07147-109">The depth counter aggregates and collects statistics over all the edges of the operation's [call graph](https://en.wikipedia.org/wiki/Call_graph).</span></span>

<span data-ttu-id="07147-110">Tutte <xref:microsoft.quantum.intrinsic> le operazioni sono espresse in termini di rotazioni, operazioni, operazioni di qubit Clifford a singolo qubit, operazioni <xref:microsoft.quantum.intrinsic.t> <xref:microsoft.quantum.intrinsic.cnot> e misurazioni di più qubit di Pauli osservabili.</span><span class="sxs-lookup"><span data-stu-id="07147-110">All <xref:microsoft.quantum.intrinsic> operations are expressed in terms of single-qubit rotations, <xref:microsoft.quantum.intrinsic.t> operations, single-qubit Clifford operations, <xref:microsoft.quantum.intrinsic.cnot> operations, and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="07147-111">Gli utenti possono impostare la profondità per ognuna delle operazioni primitive tramite il `gateTimes` campo di <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> .</span><span class="sxs-lookup"><span data-stu-id="07147-111">Users can set the depth for each of the primitive operations via the `gateTimes` field of <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span></span>

## <a name="invoking-the-depth-counter"></a><span data-ttu-id="07147-112">Richiamo del contatore di profondità</span><span class="sxs-lookup"><span data-stu-id="07147-112">Invoking the depth counter</span></span>

<span data-ttu-id="07147-113">Per eseguire il simulatore di traccia Quantum con il contatore Depth, è necessario creare un' <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> istanza, impostarne la `UseDepthCounter` proprietà su **true**e quindi creare una nuova <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> istanza con `QCTraceSimulatorConfiguration` come parametro.</span><span class="sxs-lookup"><span data-stu-id="07147-113">To run the quantum trace simulator with the depth counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set its `UseDepthCounter` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-depth-counter-in-a-c-host-program"></a><span data-ttu-id="07147-114">Uso del contatore depth in un programma host C#</span><span class="sxs-lookup"><span data-stu-id="07147-114">Using the depth counter in a C# host program</span></span>

<span data-ttu-id="07147-115">Nell'esempio di C# seguente in questa sezione viene calcolata la `T` profondità dell' `CCNOT` operazione, in base al codice di esempio Q # seguente:</span><span class="sxs-lookup"><span data-stu-id="07147-115">The C# example that follows in this section computes the `T` depth of the `CCNOT` operation, based on the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

<span data-ttu-id="07147-116">Per verificare che `CCNOT` abbia `T` la profondità **5** e `ApplySampleWithCCNOT` `T` la profondità **6**, usare il codice C# seguente:</span><span class="sxs-lookup"><span data-stu-id="07147-116">To check that `CCNOT` has `T` depth **5** and `ApplySampleWithCCNOT` has `T` depth **6**, use the following C# code:</span></span>

```csharp
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="07147-117">Viene eseguita la prima parte del programma `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="07147-117">The first part of the program runs `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="07147-118">La seconda parte usa il [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) metodo per recuperare la `T` profondità di `CCNOT` e `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="07147-118">The second part uses the [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the `T` depth of `CCNOT` and `ApplySampleWithCCNOT`.</span></span> 

<span data-ttu-id="07147-119">Infine, è possibile restituire tutte le statistiche raccolte dal contatore di profondità nel formato CSV usando quanto segue:</span><span class="sxs-lookup"><span data-stu-id="07147-119">Finally, you can output all the statistics collected by the depth counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a><span data-ttu-id="07147-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="07147-120">See also</span></span>

- <span data-ttu-id="07147-121">Panoramica del [simulatore di traccia](xref:microsoft.quantum.machines.qc-trace-simulator.intro) Quantum Development Kit Quantum.</span><span class="sxs-lookup"><span data-stu-id="07147-121">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="07147-122"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>Riferimento all'API.</span><span class="sxs-lookup"><span data-stu-id="07147-122">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="07147-123"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>Riferimento all'API.</span><span class="sxs-lookup"><span data-stu-id="07147-123">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="07147-124"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter>Riferimento all'API.</span><span class="sxs-lookup"><span data-stu-id="07147-124">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter> API reference.</span></span>
