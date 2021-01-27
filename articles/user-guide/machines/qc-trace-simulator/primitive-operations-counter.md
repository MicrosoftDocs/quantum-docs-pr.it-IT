---
title: Contatore operazioni primitive-Quantum Development Kit
description: Informazioni sul contatore delle operazioni primitive Microsoft QDK, che usa il simulatore di traccia Quantum per tenere traccia dei processi primitivi usati dalle operazioni in un Q# programma.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: conceptual
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 19ea3c1f5a91c00de4d3e435318bf4cf8cdd83be
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858593"
---
# <a name="quantum-trace-simulator-primitive-operations-counter"></a><span data-ttu-id="d57fb-103">Simulatore di traccia Quantum: contatore operazioni primitive</span><span class="sxs-lookup"><span data-stu-id="d57fb-103">Quantum trace simulator: primitive operations counter</span></span>

<span data-ttu-id="d57fb-104">Il contatore delle operazioni primitive fa parte del [simulatore di traccia Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Development Kit Quantum.</span><span class="sxs-lookup"><span data-stu-id="d57fb-104">The primitive operation counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="d57fb-105">Conta il numero di processi primitivi usati da ogni operazione richiamata in un programma Quantum.</span><span class="sxs-lookup"><span data-stu-id="d57fb-105">It counts the number of primitive processes used by every operation invoked in a quantum program.</span></span> 

<span data-ttu-id="d57fb-106">Tutte <xref:Microsoft.Quantum.Intrinsic> le operazioni sono espresse in termini di rotazioni a singolo qubit, operazioni T, operazioni Clifford qubit singole, operazioni CNOT e misurazioni di osservabili di più qubit di Pauli.</span><span class="sxs-lookup"><span data-stu-id="d57fb-106">All <xref:Microsoft.Quantum.Intrinsic> operations are expressed in terms of single-qubit rotations, T operations, single-qubit Clifford operations, CNOT operations, and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="d57fb-107">Il contatore operazioni primitive aggrega e raccoglie statistiche su tutti i bordi del [grafico chiamate](https://en.wikipedia.org/wiki/Call_graph)dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="d57fb-107">The Primitive Operations Counter aggregates and collects statistics over all the edges of the operation's [call graph](https://en.wikipedia.org/wiki/Call_graph).</span></span>

## <a name="invoking-the-primitive-operation-counter"></a><span data-ttu-id="d57fb-108">Richiamo del contatore delle operazioni primitive</span><span class="sxs-lookup"><span data-stu-id="d57fb-108">Invoking the primitive operation counter</span></span>

<span data-ttu-id="d57fb-109">Per eseguire il simulatore di traccia Quantum con il contatore delle operazioni primitive, è necessario creare un' <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> istanza, impostare la `UsePrimitiveOperationsCounter` proprietà su **true**, quindi creare una nuova <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> istanza con `QCTraceSimulatorConfiguration` come parametro.</span><span class="sxs-lookup"><span data-stu-id="d57fb-109">To run the quantum trace simulator with the primitive operation counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UsePrimitiveOperationsCounter` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with the `QCTraceSimulatorConfiguration` as the parameter.</span></span>

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-primitive-operation-counter-in-a-c-host-program"></a><span data-ttu-id="d57fb-110">Uso del contatore delle operazioni primitive in un programma host C#</span><span class="sxs-lookup"><span data-stu-id="d57fb-110">Using the primitive operation counter in a C# host program</span></span>

<span data-ttu-id="d57fb-111">L'esempio C# seguente in questa sezione conta il numero <xref:Microsoft.Quantum.Intrinsic.T> di operazioni necessarie per implementare l' <xref:Microsoft.Quantum.Intrinsic.CCNOT> operazione, in base al codice di Q# esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="d57fb-111">The C# example that follows in this section counts how many <xref:Microsoft.Quantum.Intrinsic.T> operations are needed to implement the <xref:Microsoft.Quantum.Intrinsic.CCNOT> operation, based on the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

<span data-ttu-id="d57fb-112">Per verificare che siano `CCNOT` necessarie sette `T` operazioni e che `ApplySampleWithCCNOT` esegua otto `T` operazioni, usare il codice C# seguente:</span><span class="sxs-lookup"><span data-stu-id="d57fb-112">To check that `CCNOT` requires seven `T` operations and that `ApplySampleWithCCNOT` runs eight `T` operations, use the following C# code:</span></span>

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="d57fb-113">Viene eseguita la prima parte del programma `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="d57fb-113">The first part of the program runs `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="d57fb-114">La seconda parte usa il [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) metodo per recuperare il numero di `T` operazioni eseguite da `ApplySampleWithCCNOT` :</span><span class="sxs-lookup"><span data-stu-id="d57fb-114">The second part uses the [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the number of `T` operations run by `ApplySampleWithCCNOT`:</span></span> 

<span data-ttu-id="d57fb-115">Quando si chiama `GetMetric` con due parametri di tipo, viene restituito il valore della metrica associata a un bordo del grafico della chiamata specificato.</span><span class="sxs-lookup"><span data-stu-id="d57fb-115">When you call `GetMetric` with two type parameters, it returns the value of the metric associated with a given call graph edge.</span></span> <span data-ttu-id="d57fb-116">Nell'esempio precedente il programma chiama l' `Primitive.CCNOT` operazione all'interno `ApplySampleWithCCNOT` di e, pertanto, il grafico delle chiamate contiene il bordo `<Primitive.CCNOT, ApplySampleWithCCNOT>` .</span><span class="sxs-lookup"><span data-stu-id="d57fb-116">In the preceding example, the program calls the `Primitive.CCNOT` operation  within `ApplySampleWithCCNOT` and therefore the call graph contains the edge `<Primitive.CCNOT, ApplySampleWithCCNOT>`.</span></span> 

<span data-ttu-id="d57fb-117">Per recuperare il numero di `CNOT` operazioni utilizzate, aggiungere la riga seguente:</span><span class="sxs-lookup"><span data-stu-id="d57fb-117">To retrieve the number of `CNOT` operations used, add the following line:</span></span>
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

<span data-ttu-id="d57fb-118">Infine, è possibile restituire tutte le statistiche raccolte dal contatore delle operazioni primitive in formato CSV usando quanto segue:</span><span class="sxs-lookup"><span data-stu-id="d57fb-118">Finally, you can output all the statistics collected by the Primitive Operations Counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a><span data-ttu-id="d57fb-119">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="d57fb-119">See also</span></span>

- <span data-ttu-id="d57fb-120">Panoramica del [simulatore di traccia](xref:microsoft.quantum.machines.qc-trace-simulator.intro) Quantum Development Kit Quantum.</span><span class="sxs-lookup"><span data-stu-id="d57fb-120">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="d57fb-121"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>Riferimento all'API.</span><span class="sxs-lookup"><span data-stu-id="d57fb-121">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="d57fb-122"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>Riferimento all'API.</span><span class="sxs-lookup"><span data-stu-id="d57fb-122">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="d57fb-123"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.PrimitiveOperationsGroupsNames>Riferimento all'API.</span><span class="sxs-lookup"><span data-stu-id="d57fb-123">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.PrimitiveOperationsGroupsNames> API reference.</span></span>