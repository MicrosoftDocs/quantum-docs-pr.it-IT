---
title: Controllo input distinti
description: 'Informazioni su Microsoft QDK Distinct inputs Checker, che controlla il codice Q # per i potenziali conflitti con qubits condivisi.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: 11a0573242c8afb12f242aa3be5f9cff18290452
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274929"
---
# <a name="distinct-inputs-checker"></a><span data-ttu-id="4669c-103">Controllo input distinti</span><span class="sxs-lookup"><span data-stu-id="4669c-103">Distinct Inputs Checker</span></span>

<span data-ttu-id="4669c-104">`Distinct Inputs Checker`È una parte del [simulatore di traccia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Quantum computer.</span><span class="sxs-lookup"><span data-stu-id="4669c-104">The `Distinct Inputs Checker` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="4669c-105">È progettato per rilevare potenziali bug nel codice.</span><span class="sxs-lookup"><span data-stu-id="4669c-105">It is designed for detecting potential bugs in the code.</span></span> <span data-ttu-id="4669c-106">Si consideri la seguente parte del codice Q # per illustrare i problemi rilevati dal pacchetto:</span><span class="sxs-lookup"><span data-stu-id="4669c-106">Consider the following piece of Q# code to illustrate the issues detected by this package:</span></span>

```qsharp
operation ApplyBoth(
    q1 : Qubit,
    q2 : Qubit,
    op1 : (Qubit => Unit),
    op2 : (Qubit => Unit))
: Unit {
    op1(q1);
    op2(q2);
}
```

<span data-ttu-id="4669c-107">Quando l'utente esamina il programma, presuppone che l'ordine in cui `op1` `op2` vengono richiamati e non sia rilevante perché `q1` e `q2` sono qubits diversi e le operazioni agiscono su un qubits diverso.</span><span class="sxs-lookup"><span data-stu-id="4669c-107">When the user looks at this program, they assume that the order in which `op1` and `op2` are called does not matter because `q1` and `q2` are different qubits and operations acting on different qubits commute.</span></span> <span data-ttu-id="4669c-108">A questo punto, si consideri un esempio in cui viene usata questa operazione:</span><span class="sxs-lookup"><span data-stu-id="4669c-108">Let us now consider an example, where this operation is used:</span></span>

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

<span data-ttu-id="4669c-109">Ora `op1` e `op2` sono ottenuti usando un'applicazione parziale e condividono un qubit.</span><span class="sxs-lookup"><span data-stu-id="4669c-109">Now `op1` and `op2` are both obtained using partial application and share a qubit.</span></span> <span data-ttu-id="4669c-110">Quando l'utente chiama `ApplyBoth` nell'esempio precedente, il risultato dell'operazione dipende dall'ordine di `op1` e `op2` all'interno di `ApplyBoth` .</span><span class="sxs-lookup"><span data-stu-id="4669c-110">When the user calls `ApplyBoth` in the example above the result of the operation will depend on the order of `op1` and `op2` inside `ApplyBoth`.</span></span> <span data-ttu-id="4669c-111">Questo non è certamente ciò che l'utente aspetta.</span><span class="sxs-lookup"><span data-stu-id="4669c-111">This is definitely not what the user would expect to happen.</span></span> <span data-ttu-id="4669c-112">Il `Distinct Inputs Checker` rileverà tali situazioni quando abilitata e genererà un'operazione `DistinctInputsCheckerException` .</span><span class="sxs-lookup"><span data-stu-id="4669c-112">The `Distinct Inputs Checker` will detect such situations when enabled and will throw `DistinctInputsCheckerException`.</span></span> <span data-ttu-id="4669c-113">Per altri dettagli, vedere la documentazione dell'API in [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) .</span><span class="sxs-lookup"><span data-stu-id="4669c-113">See the API documentation on [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) for more details.</span></span>

## <a name="using-the-distinct-inputs-checker-in-your-c-program"></a><span data-ttu-id="4669c-114">Uso del controllo degli input distinti nel programma C#</span><span class="sxs-lookup"><span data-stu-id="4669c-114">Using the Distinct Inputs Checker in your C# Program</span></span>

<span data-ttu-id="4669c-115">Di seguito è riportato un esempio di codice del driver C# per l'uso di Quantum computer Trace Simulator con la `Distinct Inputs Checker` funzionalità abilitata:</span><span class="sxs-lookup"><span data-stu-id="4669c-115">The following is an example of C# driver code for using the quantum computer trace simulator with the `Distinct Inputs Checker` enabled:</span></span>

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
            var traceSimCfg = new QCTraceSimulatorConfiguration();
            traceSimCfg.useDistinctInputsChecker = true; //enables distinct inputs checker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

<span data-ttu-id="4669c-116">La classe `QCTraceSimulatorConfiguration` Archivia la configurazione del simulatore di traccia del computer Quantum e può essere fornita come argomento per il `QCTraceSimulator` costruttore.</span><span class="sxs-lookup"><span data-stu-id="4669c-116">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span></span> <span data-ttu-id="4669c-117">Quando `useDistinctInputsChecker` è impostato su true, l'oggetto `Distinct Inputs Checker` è abilitato.</span><span class="sxs-lookup"><span data-stu-id="4669c-117">When `useDistinctInputsChecker` is set to true the `Distinct Inputs Checker` is enabled.</span></span> <span data-ttu-id="4669c-118">Per altri dettagli, vedere la documentazione dell'API su [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) e [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) .</span><span class="sxs-lookup"><span data-stu-id="4669c-118">See the API documentation on [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) and [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="4669c-119">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="4669c-119">See also</span></span>

- <span data-ttu-id="4669c-120">Panoramica di Quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="4669c-120">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
