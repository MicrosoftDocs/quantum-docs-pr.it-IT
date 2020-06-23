---
title: Simulatore di traccia di un computer quantistico
description: Informazioni su come usare il simulatore di traccia di un computer quantistico Microsoft per eseguire il debug del codice classico e per stimare i requisiti delle risorse di un programma quantistico.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
ms.openlocfilehash: 4cec688da35951271d87396d9b6a8fed744defc6
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85273500"
---
# <a name="quantum-trace-simulator"></a><span data-ttu-id="cb664-103">Simulatore di traccia quantistico</span><span class="sxs-lookup"><span data-stu-id="cb664-103">Quantum Trace Simulator</span></span>

<span data-ttu-id="cb664-104">Il simulatore di traccia del computer quantistico Microsoft esegue un programma quantistico senza simulare effettivamente lo stato di un computer quantistico.</span><span class="sxs-lookup"><span data-stu-id="cb664-104">The Microsoft quantum computer trace simulator executes a quantum program without actually simulating the state of a quantum computer.</span></span>  <span data-ttu-id="cb664-105">Per questo motivo, il simulatore di traccia può eseguire programmi quantistici che usano migliaia di qubit.</span><span class="sxs-lookup"><span data-stu-id="cb664-105">For this reason, the trace simulator can execute quantum programs that use thousands of qubits.</span></span>  <span data-ttu-id="cb664-106">È utile per due scopi principali:</span><span class="sxs-lookup"><span data-stu-id="cb664-106">It is useful for two main purposes:</span></span> 

* <span data-ttu-id="cb664-107">Eseguire il debug del codice classico che fa parte di un programma quantistico.</span><span class="sxs-lookup"><span data-stu-id="cb664-107">Debugging classical code that is part of a quantum program.</span></span> 
* <span data-ttu-id="cb664-108">Stimare le risorse necessarie per l'esecuzione di un'istanza specifica di un programma quantistico in un computer quantistico.</span><span class="sxs-lookup"><span data-stu-id="cb664-108">Estimating the resources required to run a given instance of a quantum program on a quantum computer.</span></span>

<span data-ttu-id="cb664-109">Il simulatore di traccia si basa sulle informazioni aggiuntive fornite dall'utente quando è necessario eseguire le misurazioni.</span><span class="sxs-lookup"><span data-stu-id="cb664-109">The trace simulator relies on additional information provided by the user when measurements must be performed.</span></span> <span data-ttu-id="cb664-110">Per informazioni dettagliate, vedere la sezione [Fornire la probabilità dei risultati di misurazione](#providing-the-probability-of-measurement-outcomes).</span><span class="sxs-lookup"><span data-stu-id="cb664-110">See Section [Providing the probability of measurement outcomes](#providing-the-probability-of-measurement-outcomes) for more details on this.</span></span> 

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="cb664-111">Fornire la probabilità dei risultati di misurazione</span><span class="sxs-lookup"><span data-stu-id="cb664-111">Providing the Probability of Measurement Outcomes</span></span>

<span data-ttu-id="cb664-112">Negli algoritmi quantistici vengono usate due tipologie di misurazioni.</span><span class="sxs-lookup"><span data-stu-id="cb664-112">There are two kinds of measurements that appear in quantum algorithms.</span></span> <span data-ttu-id="cb664-113">La prima svolge un ruolo ausiliario in cui l'utente generalmente conosce la probabilità dei risultati.</span><span class="sxs-lookup"><span data-stu-id="cb664-113">The first kind plays an auxiliary role where the user usually knows the probability of the outcomes.</span></span> <span data-ttu-id="cb664-114">In questo caso l'utente può scrivere <xref:microsoft.quantum.intrinsic.assertprob> dallo spazio dei nomi <xref:microsoft.quantum.intrinsic> per esprimere queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="cb664-114">In this case the user can write <xref:microsoft.quantum.intrinsic.assertprob> from the <xref:microsoft.quantum.intrinsic> namespace to express this knowledge.</span></span> <span data-ttu-id="cb664-115">L'esempio seguente illustra questi concetti.</span><span class="sxs-lookup"><span data-stu-id="cb664-115">The following example illustrates this:</span></span>

```qsharp
operation TeleportQubit(source : Qubit, target : Qubit) : Unit {
    using (qubit = Qubit()) {
        H(qubit);
        CNOT(qubit, target);
        CNOT(source, qubit);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [q], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(q) == One) { X(target); X(q); }
    }
}
```

<span data-ttu-id="cb664-116">Quando il simulatore di traccia esegue `AssertProb` registrerà che la misurazione `PauliZ` su `source` e `q` dovrà restituire un risultato di `Zero` con probabilità di 0,5.</span><span class="sxs-lookup"><span data-stu-id="cb664-116">When the trace simulator executes `AssertProb` it will record that measuring `PauliZ` on `source` and `q` should be given an outcome of `Zero` with probability 0.5.</span></span> <span data-ttu-id="cb664-117">Quando il simulatore esegue successivamente `M`, troverà i valori registrati delle probabilità del risultato e `M` restituirà `Zero` o `One` con probabilità di 0,5.</span><span class="sxs-lookup"><span data-stu-id="cb664-117">When the simulator executes `M` later, it will find the recorded values of the outcome probabilities and `M` will return `Zero` or `One` with probability 0.5.</span></span> <span data-ttu-id="cb664-118">Quando lo stesso codice viene eseguito in un simulatore che tiene traccia dello stato quantistico, tale simulatore verificherà che le probabilità fornite in `AssertProb` siano corrette.</span><span class="sxs-lookup"><span data-stu-id="cb664-118">When the same code is executed on a simulator that keeps track of the quantum state, such a simulator will check that the provided probabilities in `AssertProb` are correct.</span></span>

## <a name="running-your-program-with-the-quantum-computer-trace-simulator"></a><span data-ttu-id="cb664-119">Esecuzione del programma con il simulatore di traccia del computer quantistico</span><span class="sxs-lookup"><span data-stu-id="cb664-119">Running your Program with the Quantum Computer Trace Simulator</span></span> 

<span data-ttu-id="cb664-120">Il simulatore di traccia del computer quantistico può essere visualizzato semplicemente come un altro computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="cb664-120">The quantum computer trace simulator may be viewed as just another target machine.</span></span> <span data-ttu-id="cb664-121">Il programma del driver C# per usarlo è molto simile a quello per qualsiasi altro simulatore quantistico:</span><span class="sxs-lookup"><span data-stu-id="cb664-121">The C# driver program for using it is very similar to the one for any other quantum Simulator:</span></span> 

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

<span data-ttu-id="cb664-122">Si noti che se è presente almeno una misura non annotata con `AssertProb`, il simulatore genererà un'eccezione `UnconstrainedMeasurementException` dallo spazio dei nomi `Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators`.</span><span class="sxs-lookup"><span data-stu-id="cb664-122">Note that if there is at least one measurement not annotated using `AssertProb`, the simulator will throw `UnconstrainedMeasurementException` from the `Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators` namespace.</span></span> <span data-ttu-id="cb664-123">Per informazioni dettagliate, vedere la documentazione dell'API su [UnconstrainedMeasurementException](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.UnconstrainedMeasurementException).</span><span class="sxs-lookup"><span data-stu-id="cb664-123">See the API documentation on [UnconstrainedMeasurementException](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.UnconstrainedMeasurementException) for more details.</span></span>

<span data-ttu-id="cb664-124">Oltre all'esecuzione di programmi quantistici, il simulatore di traccia include cinque componenti per il rilevamento dei bug nei programmi e per l'esecuzione di stime delle risorse per il programma quantistico:</span><span class="sxs-lookup"><span data-stu-id="cb664-124">In addition to running quantum programs, the trace simulator comes with five components for detecting bugs in programs and performing quantum program resource estimates:</span></span> 

* [<span data-ttu-id="cb664-125">Controllo input distinti</span><span class="sxs-lookup"><span data-stu-id="cb664-125">Distinct Inputs Checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs)
* [<span data-ttu-id="cb664-126">Controllo utilizzo qubit invalidati</span><span class="sxs-lookup"><span data-stu-id="cb664-126">Invalidated Qubits Use Checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)
* [<span data-ttu-id="cb664-127">Contatore operazioni primitive</span><span class="sxs-lookup"><span data-stu-id="cb664-127">Primitive Operations Counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)
* [<span data-ttu-id="cb664-128">Contatore profondità circuito</span><span class="sxs-lookup"><span data-stu-id="cb664-128">Circuit Depth Counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)
* [<span data-ttu-id="cb664-129">Contatore larghezza circuito</span><span class="sxs-lookup"><span data-stu-id="cb664-129">Circuit Width Counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)

<span data-ttu-id="cb664-130">Ognuno di questi componenti può essere abilitato impostando i flag appropriati in `QCTraceSimulatorConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="cb664-130">Each of these components may be enabled by setting appropriate flags in `QCTraceSimulatorConfiguration`.</span></span> <span data-ttu-id="cb664-131">Per informazioni dettagliate su come usare ognuno di questi componenti, vedere i file di riferimento corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="cb664-131">More details about using each of these components are provided in the corresponding reference files.</span></span> <span data-ttu-id="cb664-132">Per informazioni specifiche, vedere la documentazione dell'API su [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration).</span><span class="sxs-lookup"><span data-stu-id="cb664-132">See the API documentation on [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) for specific details.</span></span>

## <a name="see-also"></a><span data-ttu-id="cb664-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb664-133">See also</span></span>
<span data-ttu-id="cb664-134">Informazioni di riferimento sul [simulatore di traccia del computer quantistico](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) per C#</span><span class="sxs-lookup"><span data-stu-id="cb664-134">The quantum computer [trace simulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) C# reference</span></span> 

