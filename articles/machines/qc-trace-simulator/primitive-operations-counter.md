---
title: Contatore operazioni primitive
description: Informazioni sul contatore delle operazioni primitive Microsoft QDK, che tiene traccia del numero di esecuzioni primitive usate dalle operazioni in un programma Quantum.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: 8bdb0aed370e72b58b23025f1685ad7ce1a77a43
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77905948"
---
# <a name="primitive-operations-counter"></a><span data-ttu-id="15954-103">Contatore operazioni primitive</span><span class="sxs-lookup"><span data-stu-id="15954-103">Primitive Operations Counter</span></span>  

<span data-ttu-id="15954-104">Il `Primitive Operations Counter` fa parte del [simulatore di traccia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Quantum computer.</span><span class="sxs-lookup"><span data-stu-id="15954-104">The `Primitive Operations Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="15954-105">Viene conteggiato il numero di esecuzioni primitive utilizzate da ogni operazione richiamata in un programma Quantum.</span><span class="sxs-lookup"><span data-stu-id="15954-105">It counts the number of primitive executions used by every operation invoked in a quantum program.</span></span> <span data-ttu-id="15954-106">Tutte le operazioni da `Microsoft.Quantum.Intrinsic` sono espresse in termini di singole rotazioni qubit, T Gate, Single qubit Clifford Gates, CNOT Gates e misurazioni di più qubit Pauli osservabili.</span><span class="sxs-lookup"><span data-stu-id="15954-106">All operations from `Microsoft.Quantum.Intrinsic` are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="15954-107">Le statistiche raccolte vengono aggregate sui bordi del grafico delle chiamate operazioni.</span><span class="sxs-lookup"><span data-stu-id="15954-107">Collected statistics are aggregated over the edges of the operations call graph.</span></span> <span data-ttu-id="15954-108">È ora possibile contare il numero di `T` Gate necessari per implementare l'operazione di `CCNOT`.</span><span class="sxs-lookup"><span data-stu-id="15954-108">Let us now count how many `T` gates are needed to implement the `CCNOT` operation.</span></span> 

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a><span data-ttu-id="15954-109">Uso del contatore operazioni primitive in C# un programma</span><span class="sxs-lookup"><span data-stu-id="15954-109">Using the Primitive Operations Counter within a C# Program</span></span>

<span data-ttu-id="15954-110">Per verificare che `CCNOT` effettivamente richieda 7 `T` Gates e che `ApplySampleWithCCNOT` esegua 8 `T` Gate, è possibile usare C# il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="15954-110">To check that `CCNOT` indeed requires 7 `T` gates and that `ApplySampleWithCCNOT` executes 8 `T` gates we can use the following C# code:</span></span>

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.usePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="15954-111">La prima parte del programma esegue `ApplySampleWithCCNOT`.</span><span class="sxs-lookup"><span data-stu-id="15954-111">The first part of the program executes `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="15954-112">Nella seconda parte viene usato il metodo `QCTraceSimulator.GetMetric` per ottenere il numero di controlli T eseguiti da `ApplySampleWithCCNOT`:</span><span class="sxs-lookup"><span data-stu-id="15954-112">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the number of T gates executed by `ApplySampleWithCCNOT`:</span></span> 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="15954-113">Quando `GetMetric` viene chiamato con due parametri di tipo, restituisce il valore della metrica associata a un bordo del grafico della chiamata specificato.</span><span class="sxs-lookup"><span data-stu-id="15954-113">When `GetMetric` is called with two type parameters it returns the value of the metric associated with a given call graph edge.</span></span> <span data-ttu-id="15954-114">Nell'esempio di operazione `Primitive.CCNOT` viene chiamato all'interno di `ApplySampleWithCCNOT` e quindi il grafico delle chiamate contiene la `<Primitive.CCNOT, ApplySampleWithCCNOT>`Edge.</span><span class="sxs-lookup"><span data-stu-id="15954-114">In our example operation `Primitive.CCNOT` is called within `ApplySampleWithCCNOT` and therefore the call graph contains the edge `<Primitive.CCNOT, ApplySampleWithCCNOT>`.</span></span> 

<span data-ttu-id="15954-115">Per ottenere il numero di `CNOT` Gate usati, è possibile aggiungere la riga seguente:</span><span class="sxs-lookup"><span data-stu-id="15954-115">To get the number of `CNOT` gates used, we can add the following line:</span></span>
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

<span data-ttu-id="15954-116">Infine, per restituire tutte le statistiche raccolte dal contatore di controllo in formato CSV, è possibile usare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="15954-116">Finally, to output all the statistics collected by the gate counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a><span data-ttu-id="15954-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15954-117">See also</span></span> ##

- <span data-ttu-id="15954-118">Panoramica di Quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="15954-118">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
