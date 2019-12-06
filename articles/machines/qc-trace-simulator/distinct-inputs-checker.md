---
title: Controllo input distinti | Simulatore di traccia del computer Quantum | Microsoft Docs
description: Panoramica del simulatore di traccia del computer quantistico
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: ce3f156a84a4509781a74c9276b953c79670a756
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74864305"
---
# <a name="distinct-inputs-checker"></a><span data-ttu-id="c99c0-103">Controllo input distinti</span><span class="sxs-lookup"><span data-stu-id="c99c0-103">Distinct Inputs Checker</span></span>

<span data-ttu-id="c99c0-104">Il `Distinct Inputs Checker` fa parte del [simulatore di traccia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Quantum computer.</span><span class="sxs-lookup"><span data-stu-id="c99c0-104">The `Distinct Inputs Checker` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="c99c0-105">È progettato per rilevare potenziali bug nel codice.</span><span class="sxs-lookup"><span data-stu-id="c99c0-105">It is designed for detecting potential bugs in the code.</span></span> <span data-ttu-id="c99c0-106">Si consideri la seguente parte del codice Q # per illustrare i problemi rilevati dal pacchetto:</span><span class="sxs-lookup"><span data-stu-id="c99c0-106">Consider the following piece of Q# code to illustrate the issues detected by this package:</span></span>

```qsharp
operation DoBoth(q1 : Qubit, q2 : Qubit, op1 : (Qubit => Unit), op2 : (Qubit => Unit)) : Unit {

    op1(q1);
    op2(q2);
}
```

<span data-ttu-id="c99c0-107">Quando l'utente esamina il programma, presuppone che l'ordine in cui vengono chiamati `op1` e `op2` non sia rilevante perché `q1` e `q2` sono qubits e le operazioni eseguite su qubits diversi.</span><span class="sxs-lookup"><span data-stu-id="c99c0-107">When the user looks at this program, they assume that the order in which `op1` and `op2` are called does not matter because `q1` and `q2` are different qubits and operations acting on different qubits commute.</span></span> <span data-ttu-id="c99c0-108">A questo punto, si consideri un esempio in cui viene usata questa operazione:</span><span class="sxs-lookup"><span data-stu-id="c99c0-108">Let us now consider an example, where this operation is used:</span></span>

```qsharp
operation CapturedQubits () : Unit {

    using (q = Qubit[3]) {
        let op1 = CNOT(_, q[1]);
        let op2 = CNOT(q[1], _);
        DoBoth(q[0], q[2], op1, op2);
    }
}
```

<span data-ttu-id="c99c0-109">Ora `op1` e `op2` sono ottenuti usando un'applicazione parziale e condividono un qubit.</span><span class="sxs-lookup"><span data-stu-id="c99c0-109">Now `op1` and `op2` are both obtained using partial application and share a qubit.</span></span> <span data-ttu-id="c99c0-110">Quando l'utente chiama `DoBoth` nell'esempio precedente, il risultato dell'operazione dipenderà dall'ordine di `op1` e `op2` all'interno `DoBoth`.</span><span class="sxs-lookup"><span data-stu-id="c99c0-110">When the user calls `DoBoth` in the example above the result of the operation will depend on the order of `op1` and `op2` inside `DoBoth`.</span></span> <span data-ttu-id="c99c0-111">Questo non è certamente ciò che l'utente aspetta.</span><span class="sxs-lookup"><span data-stu-id="c99c0-111">This is definitely not what the user would expect to happen.</span></span> <span data-ttu-id="c99c0-112">Il `Distinct Inputs Checker` rileverà tali situazioni quando abilitata e genererà `DistinctInputsCheckerException`.</span><span class="sxs-lookup"><span data-stu-id="c99c0-112">The `Distinct Inputs Checker` will detect such situations when enabled and will throw `DistinctInputsCheckerException`.</span></span> <span data-ttu-id="c99c0-113">Per altri dettagli, vedere la documentazione dell'API in [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) .</span><span class="sxs-lookup"><span data-stu-id="c99c0-113">See the API documentation on [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) for more details.</span></span>

## <a name="using-the-distinct-inputs-checker-in-your-c-program"></a><span data-ttu-id="c99c0-114">Uso del controllo degli input distinti nel C# programma</span><span class="sxs-lookup"><span data-stu-id="c99c0-114">Using the Distinct Inputs Checker in your C# Program</span></span>

<span data-ttu-id="c99c0-115">Di seguito è riportato un esempio C# di codice del driver per l'uso di Quantum computer Trace Simulator con la `Distinct Inputs Checker` abilitata:</span><span class="sxs-lookup"><span data-stu-id="c99c0-115">The following is an example of C# driver code for using the quantum computer trace simulator with the `Distinct Inputs Checker` enabled:</span></span>

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

<span data-ttu-id="c99c0-116">La classe `QCTraceSimulatorConfiguration` archivia la configurazione del simulatore di traccia del computer Quantum e può essere fornita come argomento per il costruttore di `QCTraceSimulator`.</span><span class="sxs-lookup"><span data-stu-id="c99c0-116">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span></span> <span data-ttu-id="c99c0-117">Quando `useDistinctInputsChecker` è impostato su true, la `Distinct Inputs Checker` è abilitata.</span><span class="sxs-lookup"><span data-stu-id="c99c0-117">When `useDistinctInputsChecker` is set to true the `Distinct Inputs Checker` is enabled.</span></span> <span data-ttu-id="c99c0-118">Per altri dettagli, vedere la documentazione dell'API su [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) e [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) .</span><span class="sxs-lookup"><span data-stu-id="c99c0-118">See the API documentation on [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) and [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="c99c0-119">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="c99c0-119">See also</span></span>

- <span data-ttu-id="c99c0-120">Panoramica di Quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="c99c0-120">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
