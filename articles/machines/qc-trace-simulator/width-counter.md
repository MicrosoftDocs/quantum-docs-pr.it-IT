---
title: Contatore larghezza
description: Informazioni sul contatore Microsoft QDK Width, che conta il numero di qubits allocati e presi in prestito da ogni operazione in un programma Quantum.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: a76292222950310acc90dded02980e4a5b792e76
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907087"
---
# <a name="width-counter"></a><span data-ttu-id="73e52-103">Contatore larghezza</span><span class="sxs-lookup"><span data-stu-id="73e52-103">Width Counter</span></span>

<span data-ttu-id="73e52-104">Il `Width Counter` conta il numero di qubits allocati e presi in prestito da ogni operazione.</span><span class="sxs-lookup"><span data-stu-id="73e52-104">The `Width Counter` counts the number of qubits allocated and borrowed by each operation.</span></span>
<span data-ttu-id="73e52-105">Tutte le operazioni dello spazio dei nomi `Microsoft.Quantum.Intrinsic` sono espresse in termini di singole rotazioni qubit, T Gate, Single qubit Clifford Gates, CNOT Gates e misurazioni di qubit Pauli osservabili.</span><span class="sxs-lookup"><span data-stu-id="73e52-105">All operations from the `Microsoft.Quantum.Intrinsic` namespace are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="73e52-106">Alcune delle operazioni primitive possono allocare qubits aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="73e52-106">Some of the primitive operations can allocate extra qubits.</span></span> <span data-ttu-id="73e52-107">Ad esempio, moltiplicare controlli `X` controllati o controlli `T` controllati.</span><span class="sxs-lookup"><span data-stu-id="73e52-107">For example, multiply controlled `X` gates or controlled `T` gates.</span></span> <span data-ttu-id="73e52-108">Consente di calcolare il numero di qubits aggiuntivi allocati dall'implementazione di un controllo `X` di moltiplicazione controllato:</span><span class="sxs-lookup"><span data-stu-id="73e52-108">Let us compute the number of extra qubits allocated by the implementation of a multiply controlled `X` gate:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a><span data-ttu-id="73e52-109">Uso del contatore della larghezza C# in un programma</span><span class="sxs-lookup"><span data-stu-id="73e52-109">Using Width Counter within a C# Program</span></span>

<span data-ttu-id="73e52-110">Il `X` di moltiplicazione controllato che agisce su un totale di 5 qubits alloca 2 qubits ausiliari e la larghezza di input sarà 5.</span><span class="sxs-lookup"><span data-stu-id="73e52-110">Multiply controlled `X` acting on a total of 5 qubits will allocate 2 ancillary qubits and its input width will be 5.</span></span> <span data-ttu-id="73e52-111">Per verificarne il caso, è possibile usare il programma seguente C# :</span><span class="sxs-lookup"><span data-stu-id="73e52-111">To check that this is the case, we can use the following C# program:</span></span>

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

<span data-ttu-id="73e52-112">La prima parte del programma esegue `ApplyMultiControlledX`.</span><span class="sxs-lookup"><span data-stu-id="73e52-112">The first part of the program executes `ApplyMultiControlledX`.</span></span> <span data-ttu-id="73e52-113">Nella seconda parte viene usato il metodo `QCTraceSimulator.GetMetric` per ottenere il numero di qubits allocati, nonché il numero di qubits che ha controllato `X` ricevuto come input.</span><span class="sxs-lookup"><span data-stu-id="73e52-113">In the second part we use the method `QCTraceSimulator.GetMetric` to get the number of allocated qubits as well as the number of qubits that Controlled `X` received as input.</span></span> 

<span data-ttu-id="73e52-114">Infine, per restituire tutte le statistiche raccolte dal contatore di larghezza in formato CSV, è possibile usare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="73e52-114">Finally, to output all the statistics collected by width counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a><span data-ttu-id="73e52-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73e52-115">See also</span></span> ##

- <span data-ttu-id="73e52-116">Panoramica di Quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="73e52-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
