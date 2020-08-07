---
title: Contatore larghezza-Quantum Development Kit
description: Informazioni sul contatore Microsoft QDK Width, che usa il simulatore di traccia Quantum per contare il numero di qubits allocati e presi in prestito dalle operazioni in un Q# programma.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 02f4937aaccf7bf49d6450355c6b42b273071b2e
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868203"
---
# <a name="quantum-trace-simulator-width-counter"></a><span data-ttu-id="f37b9-103">Simulatore di traccia Quantum: contatore larghezza</span><span class="sxs-lookup"><span data-stu-id="f37b9-103">Quantum trace simulator: width counter</span></span>

<span data-ttu-id="f37b9-104">Il contatore della larghezza fa parte del [simulatore di traccia Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Development Kit Quantum.</span><span class="sxs-lookup"><span data-stu-id="f37b9-104">The width counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="f37b9-105">È possibile usarlo per conteggiare il numero di qubits allocati e presi in prestito da ogni operazione in un Q# programma.</span><span class="sxs-lookup"><span data-stu-id="f37b9-105">You can use it to count the number of qubits allocated and borrowed by each operation in a Q# program.</span></span> <span data-ttu-id="f37b9-106">Alcune operazioni primitive possono allocare qubits aggiuntive, ad esempio, moltiplicare `X` le operazioni controllate o controllate `T` .</span><span class="sxs-lookup"><span data-stu-id="f37b9-106">Some primitive operations can allocate extra qubits, for example, multiply controlled `X` operations or controlled `T` operations.</span></span>

## <a name="invoking-the-width-counter"></a><span data-ttu-id="f37b9-107">Richiamo del contatore della larghezza</span><span class="sxs-lookup"><span data-stu-id="f37b9-107">Invoking the width counter</span></span>

<span data-ttu-id="f37b9-108">Per eseguire il simulatore di traccia Quantum con il contatore larghezza, è necessario creare un' <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> istanza, impostare la `UseWidthCounter` proprietà su **true**, quindi creare una nuova <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> istanza con `QCTraceSimulatorConfiguration` come parametro.</span><span class="sxs-lookup"><span data-stu-id="f37b9-108">To run the quantum trace simulator with the width counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseWidthCounter` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with the `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-width-counter-in-a-c-host-program"></a><span data-ttu-id="f37b9-109">Uso del contatore Width in un programma host C#</span><span class="sxs-lookup"><span data-stu-id="f37b9-109">Using the width counter in a C# host program</span></span>

<span data-ttu-id="f37b9-110">Nell'esempio di C# seguente in questa sezione viene calcolato il numero di qubits aggiuntivi allocati dall'implementazione di un'operazione di moltiplicazione controllata <xref:microsoft.quantum.intrinsic.x> , in base al Q# codice di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="f37b9-110">The C# example that follows in this section computes the number of extra qubits allocated by the implementation of a multiply controlled <xref:microsoft.quantum.intrinsic.x> operation, based on the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

<span data-ttu-id="f37b9-111">L'operazione di moltiplicazione controllata <xref:microsoft.quantum.intrinsic.x> agisce su un totale di cinque qubits, alloca due [qubits ausiliari](xref:microsoft.quantum.glossary#ancilla)e ha una larghezza di input pari a **5**.</span><span class="sxs-lookup"><span data-stu-id="f37b9-111">The multiply controlled <xref:microsoft.quantum.intrinsic.x> operation acts on a total of five qubits, allocates two [ancillary qubits](xref:microsoft.quantum.glossary#ancilla), and has an input width of **5**.</span></span> <span data-ttu-id="f37b9-112">Usare il programma C# seguente per verificare i conteggi:</span><span class="sxs-lookup"><span data-stu-id="f37b9-112">Use the following C# program to verify the counts:</span></span>

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
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

<span data-ttu-id="f37b9-113">La prima parte del programma esegue l' `ApplyMultiControlledX` operazione.</span><span class="sxs-lookup"><span data-stu-id="f37b9-113">The first part of the program runs the `ApplyMultiControlledX` operation.</span></span> <span data-ttu-id="f37b9-114">La seconda parte usa il [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) metodo per recuperare il numero di qubits allocati, nonché il numero di qubits che l' `Controlled X` operazione ha ricevuto come input.</span><span class="sxs-lookup"><span data-stu-id="f37b9-114">The second part uses the [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the number of allocated qubits as well as the number of qubits that the `Controlled X` operation received as input.</span></span> 

<span data-ttu-id="f37b9-115">Infine, è possibile restituire tutte le statistiche raccolte dal contatore della larghezza in formato CSV usando quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f37b9-115">Finally, you can output all the statistics collected by the width counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a><span data-ttu-id="f37b9-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f37b9-116">See also</span></span>

- <span data-ttu-id="f37b9-117">Panoramica del [simulatore di traccia](xref:microsoft.quantum.machines.qc-trace-simulator.intro) Quantum Development Kit Quantum.</span><span class="sxs-lookup"><span data-stu-id="f37b9-117">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="f37b9-118"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>Riferimento all'API.</span><span class="sxs-lookup"><span data-stu-id="f37b9-118">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="f37b9-119"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>Riferimento all'API.</span><span class="sxs-lookup"><span data-stu-id="f37b9-119">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="f37b9-120"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter>Riferimento all'API.</span><span class="sxs-lookup"><span data-stu-id="f37b9-120">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter> API reference.</span></span>
