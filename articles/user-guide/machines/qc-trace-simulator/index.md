---
title: Simulatore di traccia quantistico - Quantum Development Kit
description: Informazioni su come usare il simulatore di traccia di un computer quantistico Microsoft per eseguire il debug di codice classico e per stimare i requisiti delle risorse di un programma Q#.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 7f5e25aa7b58277642783e03d03854cd75ff4ca3
ms.sourcegitcommit: d98190988ff03146d9ca2b0d325870cd717d729a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/06/2020
ms.locfileid: "91771290"
---
# <a name="microsoft-quantum-development-kit-qdk-quantum-trace-simulator"></a><span data-ttu-id="b4d32-103">Simulatore di traccia quantistico del Quantum Development Kit (QDK) Microsoft</span><span class="sxs-lookup"><span data-stu-id="b4d32-103">Microsoft Quantum Development Kit (QDK) quantum trace simulator</span></span>

<span data-ttu-id="b4d32-104">La classe <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> del QDK esegue un programma quantistico senza effettivamente simulare lo stato di un computer quantistico.</span><span class="sxs-lookup"><span data-stu-id="b4d32-104">The QDK <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> class runs a quantum program without actually simulating the state of a quantum computer.</span></span> <span data-ttu-id="b4d32-105">Per questo motivo, il simulatore di traccia quantistico può eseguire programmi quantistici che usano migliaia di qubit.</span><span class="sxs-lookup"><span data-stu-id="b4d32-105">For this reason, the quantum trace simulator is able to run quantum programs that use thousands of qubits.</span></span>  <span data-ttu-id="b4d32-106">È utile per due scopi principali:</span><span class="sxs-lookup"><span data-stu-id="b4d32-106">It is useful for two main purposes:</span></span> 

* <span data-ttu-id="b4d32-107">Eseguire il debug del codice classico che fa parte di un programma quantistico.</span><span class="sxs-lookup"><span data-stu-id="b4d32-107">Debugging classical code that is part of a quantum program.</span></span> 
* <span data-ttu-id="b4d32-108">Stimare le risorse necessarie per l'esecuzione di un'istanza specifica di un programma quantistico in un computer quantistico.</span><span class="sxs-lookup"><span data-stu-id="b4d32-108">Estimating the resources required to run a given instance of a quantum program on a quantum computer.</span></span> <span data-ttu-id="b4d32-109">Di fatto, lo [strumento di stima risorse](xref:microsoft.quantum.machines.resources-estimator), che prevede un set più limitato di metriche, è basato sul simulatore di traccia.</span><span class="sxs-lookup"><span data-stu-id="b4d32-109">In fact, the [Resources estimator](xref:microsoft.quantum.machines.resources-estimator), which provides a more limited set of metrics, is built upon the trace simulator.</span></span>

## <a name="invoking-the-quantum-trace-simulator"></a><span data-ttu-id="b4d32-110">Come richiamare il simulatore di traccia quantistico</span><span class="sxs-lookup"><span data-stu-id="b4d32-110">Invoking the quantum trace simulator</span></span>

<span data-ttu-id="b4d32-111">È possibile usare il simulatore di traccia quantistico per eseguire qualsiasi operazione Q#.</span><span class="sxs-lookup"><span data-stu-id="b4d32-111">You can use the quantum trace simulator to run any Q# operation.</span></span>

<span data-ttu-id="b4d32-112">Come per altri computer di destinazione, creare prima un'istanza della classe `QCTraceSimulator` e quindi passarla come primo parametro del metodo `Run` di un'operazione.</span><span class="sxs-lookup"><span data-stu-id="b4d32-112">As with other target machines, you first create an instance of the `QCTraceSimulator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="b4d32-113">Si noti che, a differenza della classe `QuantumSimulator`, la classe `QCTraceSimulator` non implementa l'interfaccia <xref:System.IDisposable>, per cui non è necessario racchiuderla in un'istruzione `using`.</span><span class="sxs-lookup"><span data-stu-id="b4d32-113">Note that, unlike the `QuantumSimulator` class, the `QCTraceSimulator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            QCTraceSimulator sim = new QCTraceSimulator();
            var res = MyQuantumProgram.Run(sim).Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="b4d32-114">Come fornire la probabilità dei risultati di misurazione</span><span class="sxs-lookup"><span data-stu-id="b4d32-114">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="b4d32-115">Poiché il simulatore di traccia quantistico non simula lo stato quantico effettivo, non è in grado di calcolare la probabilità dei risultati di misurazione all'interno di un'operazione.</span><span class="sxs-lookup"><span data-stu-id="b4d32-115">Because the quantum trace simulator does not simulate the actual quantum state, it cannot calculate the probability of measurement outcomes within an operation.</span></span> 

<span data-ttu-id="b4d32-116">Pertanto, se un'operazione include misurazioni, è necessario fornire queste probabilità in modo esplicito usando l'operazione <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> dello spazio dei nomi <xref:microsoft.quantum.diagnostics>.</span><span class="sxs-lookup"><span data-stu-id="b4d32-116">Therefore, if an operation includes measurements, you must explicitly provide these probabilities using the <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> operation from the <xref:microsoft.quantum.diagnostics> namespace.</span></span> <span data-ttu-id="b4d32-117">L'esempio seguente illustra questi concetti.</span><span class="sxs-lookup"><span data-stu-id="b4d32-117">The following example illustrates this:</span></span>

```qsharp
operation TeleportQubit(source : Qubit, target : Qubit) : Unit {
    using (qubit = Qubit()) {
        H(qubit);
        CNOT(qubit, target);
        CNOT(source, qubit);
        H(source);

        AssertMeasurementProbability([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertMeasurementProbability([PauliZ], [q], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(q) == One) { X(target); X(q); }
    }
}
```

<span data-ttu-id="b4d32-118">Quando il simulatore di traccia quantistico esegue `AssertMeasurementProbability`, registra che la misurazione `PauliZ` su `source` e `q` dovrà restituire un risultato `Zero` con probabilità **0,5**.</span><span class="sxs-lookup"><span data-stu-id="b4d32-118">When the quantum trace simulator encounters `AssertMeasurementProbability` it records that measuring `PauliZ` on `source` and `q` should give an outcome of `Zero`, with probability **0.5**.</span></span> <span data-ttu-id="b4d32-119">Quando in seguito esegue l'operazione `M`, trova i valori registrati delle probabilità dei risultati `M` restituisce `Zero` o `One` con probabilità **0,5**.</span><span class="sxs-lookup"><span data-stu-id="b4d32-119">When it runs the `M` operation later, it finds the recorded values of the outcome probabilities, and `M` returns `Zero` or `One`, with probability **0.5**.</span></span> <span data-ttu-id="b4d32-120">Quando lo stesso codice viene eseguito in un simulatore che tiene traccia dello stato quantico, tale simulatore verifica che le probabilità fornite in `AssertMeasurementProbability` siano corrette.</span><span class="sxs-lookup"><span data-stu-id="b4d32-120">When the same code runs on a simulator that keeps track of the quantum state, that simulator checks that the provided probabilities in `AssertMeasurementProbability` are correct.</span></span>

<span data-ttu-id="b4d32-121">Si noti che se è presente almeno un'operazione di misurazione non annotata con `AssertMeasurementProbability`, il simulatore genera [`UnconstrainedMeasurementException`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.unconstrainedmeasurementexception).</span><span class="sxs-lookup"><span data-stu-id="b4d32-121">Note that if there is at least one measurement operation that is not annotated using `AssertMeasurementProbability`, the simulator throws an [`UnconstrainedMeasurementException`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.unconstrainedmeasurementexception).</span></span>

## <a name="quantum-trace-simulator-tools"></a><span data-ttu-id="b4d32-122">Strumenti del simulatore di traccia quantistico</span><span class="sxs-lookup"><span data-stu-id="b4d32-122">Quantum trace simulator tools</span></span>

<span data-ttu-id="b4d32-123">Il QDK include cinque strumenti che è possibile usare con il simulatore di traccia quantistico per rilevare bug nei programmi ed eseguire stime delle risorse dei programmi quantistici:</span><span class="sxs-lookup"><span data-stu-id="b4d32-123">The QDK includes five tools that you can use with the quantum trace simulator to detect bugs in your programs and perform quantum program resource estimates:</span></span> 

|<span data-ttu-id="b4d32-124">Strumento</span><span class="sxs-lookup"><span data-stu-id="b4d32-124">Tool</span></span> | <span data-ttu-id="b4d32-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b4d32-125">Description</span></span> |
|-----| -----|
|[<span data-ttu-id="b4d32-126">Controllo input distinti</span><span class="sxs-lookup"><span data-stu-id="b4d32-126">Distinct inputs checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) |<span data-ttu-id="b4d32-127">Verifica i potenziali conflitti con qubit condivisi</span><span class="sxs-lookup"><span data-stu-id="b4d32-127">Checks for potential conflicts with shared qubits</span></span> |
|[<span data-ttu-id="b4d32-128">Controllo utilizzo qubit invalidati</span><span class="sxs-lookup"><span data-stu-id="b4d32-128">Invalidated qubits use checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)  |<span data-ttu-id="b4d32-129">Controlla se il programma applica un'operazione a un qubit già rilasciato</span><span class="sxs-lookup"><span data-stu-id="b4d32-129">Checks if the program applies an operation to a qubit that is already released</span></span> |
|[<span data-ttu-id="b4d32-130">Contatore operazioni primitive</span><span class="sxs-lookup"><span data-stu-id="b4d32-130">Primitive operations counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)  | <span data-ttu-id="b4d32-131">Conta il numero di primitive usate da ogni operazione richiamata in un programma quantistico</span><span class="sxs-lookup"><span data-stu-id="b4d32-131">Counts the number of primitives used by every operation invoked in a quantum program</span></span>  |
|[<span data-ttu-id="b4d32-132">Contatore profondità</span><span class="sxs-lookup"><span data-stu-id="b4d32-132">Depth counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)  |<span data-ttu-id="b4d32-133">Raccoglie i conteggi che rappresentano il limite inferiore della profondità di ogni operazione richiamata in un programma quantistico</span><span class="sxs-lookup"><span data-stu-id="b4d32-133">Gathers counts that represent the lower bound of the depth of every operation invoked in a quantum program</span></span>   |
|[<span data-ttu-id="b4d32-134">Contatore larghezza</span><span class="sxs-lookup"><span data-stu-id="b4d32-134">Width counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)  |<span data-ttu-id="b4d32-135">Conta il numero di qubit allocati e presi in prestito da ogni operazione in un programma quantistico</span><span class="sxs-lookup"><span data-stu-id="b4d32-135">Counts the number of qubits allocated and borrowed by each operation in a quantum program</span></span> |

<span data-ttu-id="b4d32-136">Ognuno di questi strumenti viene abilitato impostando flag appropriati in `QCTraceSimulatorConfiguration` e passando quindi la configurazione alla dichiarazione `QCTraceSimulator`.</span><span class="sxs-lookup"><span data-stu-id="b4d32-136">Each of these tools is enabled by setting appropriate flags in `QCTraceSimulatorConfiguration` and then passing the configuration to the `QCTraceSimulator` declaration.</span></span> <span data-ttu-id="b4d32-137">Per informazioni sull'uso di ognuno di questi strumenti, vedere i collegamenti nell'elenco precedente.</span><span class="sxs-lookup"><span data-stu-id="b4d32-137">For information on using each of these tools, see the links in the preceding list.</span></span> <span data-ttu-id="b4d32-138">Per altre informazioni sulla configurazione di `QCTraceSimulator`, vedere [QCTraceSimulatorConfiguration](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration).</span><span class="sxs-lookup"><span data-stu-id="b4d32-138">For more information about configuring `QCTraceSimulator`, see [QCTraceSimulatorConfiguration](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration).</span></span>

## <a name="qctracesimulator-methods"></a><span data-ttu-id="b4d32-139">Metodi QCTraceSimulator</span><span class="sxs-lookup"><span data-stu-id="b4d32-139">QCTraceSimulator methods</span></span>

<span data-ttu-id="b4d32-140">`QCTraceSimulator` include diversi metodi predefiniti per recuperare i valori delle metriche registrate durante un'operazione quantistica.</span><span class="sxs-lookup"><span data-stu-id="b4d32-140">`QCTraceSimulator` has several built-in methods to retrieve the values of the metrics tracked during a quantum operation.</span></span> <span data-ttu-id="b4d32-141">Esempi dei metodi [QCTraceSimulator.GetMetric](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) e [QCTraceSimulator.ToCSV](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.tocsv) sono disponibili negli articoli [Contatore operazioni primitive](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter), [Contatore profondità](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) e [Contatore larghezza](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter).</span><span class="sxs-lookup"><span data-stu-id="b4d32-141">Examples of the [QCTraceSimulator.GetMetric](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) and the [QCTraceSimulator.ToCSV](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.tocsv) methods can be found in the [Primitive operations counter](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter), [Depth counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter), and [Width counter](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter) articles.</span></span> <span data-ttu-id="b4d32-142">Per altre informazioni su tutti i metodi disponibili, vedere [QCTraceSimulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) nelle informazioni di riferimento sull'API Q#.</span><span class="sxs-lookup"><span data-stu-id="b4d32-142">For more information on all available methods, see [QCTraceSimulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) in the Q# API reference.</span></span>  

## <a name="see-also"></a><span data-ttu-id="b4d32-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4d32-143">See also</span></span>

- [<span data-ttu-id="b4d32-144">Strumento di stima risorse</span><span class="sxs-lookup"><span data-stu-id="b4d32-144">Quantum resources estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="b4d32-145">Simulatore di Toffoli</span><span class="sxs-lookup"><span data-stu-id="b4d32-145">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="b4d32-146">Simulatore di stato completo</span><span class="sxs-lookup"><span data-stu-id="b4d32-146">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 