---
title: Contatore larghezza | Simulatore di traccia del computer Quantum | Microsoft Docs
description: Panoramica del simulatore di traccia del computer quantistico
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: 9c3601e74eec17bd6b463e90f8f3085c959d6f95
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820369"
---
# <a name="width-counter"></a><span data-ttu-id="3040b-103">Contatore larghezza</span><span class="sxs-lookup"><span data-stu-id="3040b-103">Width Counter</span></span>

<span data-ttu-id="3040b-104">Il `Width Counter` conta il numero di qubits allocati e presi in prestito da ogni operazione.</span><span class="sxs-lookup"><span data-stu-id="3040b-104">The `Width Counter` counts the number of qubits allocated and borrowed by each operation.</span></span>
<span data-ttu-id="3040b-105">Tutte le operazioni dello spazio dei nomi `Microsoft.Quantum.Intrinsic` sono espresse in termini di singole rotazioni qubit, T Gate, Single qubit Clifford Gates, CNOT Gates e misurazioni di qubit Pauli osservabili.</span><span class="sxs-lookup"><span data-stu-id="3040b-105">All operations from the `Microsoft.Quantum.Intrinsic` namespace are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="3040b-106">Alcune delle operazioni primitive possono allocare qubits aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="3040b-106">Some of the primitive operations can allocate extra qubits.</span></span> <span data-ttu-id="3040b-107">Ad esempio, moltiplicare controlli `X` controllati o controlli `T` controllati.</span><span class="sxs-lookup"><span data-stu-id="3040b-107">For example, multiply controlled `X` gates or controlled `T` gates.</span></span> <span data-ttu-id="3040b-108">Consente di calcolare il numero di qubits aggiuntivi allocati dall'implementazione di un controllo `X` di moltiplicazione controllato:</span><span class="sxs-lookup"><span data-stu-id="3040b-108">Let us compute the number of extra qubits allocated by the implementation of a multiply controlled `X` gate:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a><span data-ttu-id="3040b-109">Uso del contatore della larghezza C# in un programma</span><span class="sxs-lookup"><span data-stu-id="3040b-109">Using Width Counter within a C# Program</span></span>

<span data-ttu-id="3040b-110">Il `X` di moltiplicazione controllato che agisce su un totale di 5 qubits alloca 2 qubits ausiliari e la larghezza di input sarà 5.</span><span class="sxs-lookup"><span data-stu-id="3040b-110">Multiply controlled `X` acting on a total of 5 qubits will allocate 2 ancillary qubits and its input width will be 5.</span></span> <span data-ttu-id="3040b-111">Per verificarne il caso, è possibile usare il programma seguente C# :</span><span class="sxs-lookup"><span data-stu-id="3040b-111">To check that this is the case, we can use the following C# program:</span></span>

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.useWidthCounter = true;
var sim = new QCTraceSimulator(config);
int totalNumberOfQubits = 5;
var res = ApplyMultiControlledX.Run(sim, totalNumberOfQubits).Result;

double allocatedQubits = 
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.ExtraWidth,
        functor: OperationFunctor.Controlled); 

double inputWidth =
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.InputWidth,
        functor: OperationFunctor.Controlled);
```

<span data-ttu-id="3040b-112">La prima parte del programma esegue `ApplyMultiControlledX`.</span><span class="sxs-lookup"><span data-stu-id="3040b-112">The first part of the program executes `ApplyMultiControlledX`.</span></span> <span data-ttu-id="3040b-113">Nella seconda parte viene usato il metodo `QCTraceSimulator.GetMetric` per ottenere il numero di qubits allocati, nonché il numero di qubits che ha controllato `X` ricevuto come input.</span><span class="sxs-lookup"><span data-stu-id="3040b-113">In the second part we use the method `QCTraceSimulator.GetMetric` to get the number of allocated qubits as well as the number of qubits that Controlled `X` received as input.</span></span> 

<span data-ttu-id="3040b-114">Infine, per restituire tutte le statistiche raccolte dal contatore di larghezza in formato CSV, è possibile usare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="3040b-114">Finally, to output all the statistics collected by width counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a><span data-ttu-id="3040b-115">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="3040b-115">See also</span></span> ##

- <span data-ttu-id="3040b-116">Panoramica di Quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="3040b-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
