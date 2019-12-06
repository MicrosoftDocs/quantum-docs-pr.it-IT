---
title: Controllo utilizzo qubits invalidato | Simulatore di traccia del computer Quantum | Microsoft Docs
description: Panoramica del simulatore di traccia del computer quantistico
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: 283cc7d7d88f731f40fa396c38ae5ea8dd90537f
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74863181"
---
# <a name="invalidated-qubits-use-checker"></a><span data-ttu-id="c4df9-103">Controllo utilizzo qubits invalidato</span><span class="sxs-lookup"><span data-stu-id="c4df9-103">Invalidated Qubits Use Checker</span></span>

<span data-ttu-id="c4df9-104">Il `Invalidated Qubits Use Checker` fa parte del Quantum computer [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) progettato per rilevare potenziali bug nel codice.</span><span class="sxs-lookup"><span data-stu-id="c4df9-104">The `Invalidated Qubits Use Checker` is a part of the quantum computer [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) designed for detecting potential bugs in the code.</span></span> <span data-ttu-id="c4df9-105">Si consideri il seguente codice Q # per illustrare i problemi rilevati dal `Invalidated Qubits Use Checker`.</span><span class="sxs-lookup"><span data-stu-id="c4df9-105">Consider the following piece of Q# code to illustrate the issues detected by the `Invalidated Qubits Use Checker`.</span></span>

```qsharp
operation UseReleasedQubit () : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

<span data-ttu-id="c4df9-106">Quando `H` viene applicato al `q[0]` fa riferimento a una qubit già rilasciata.</span><span class="sxs-lookup"><span data-stu-id="c4df9-106">When `H` is applied to `q[0]` it points to an already released qubit.</span></span> <span data-ttu-id="c4df9-107">Questo può causare un comportamento indefinito.</span><span class="sxs-lookup"><span data-stu-id="c4df9-107">This can cause undefined behavior.</span></span> <span data-ttu-id="c4df9-108">Quando la `Invalidated Qubits Use Checker` è abilitata, verrà generata l'eccezione `InvalidatedQubitsUseCheckerException` se un'operazione viene applicata a una qubit già rilasciata.</span><span class="sxs-lookup"><span data-stu-id="c4df9-108">When the `Invalidated Qubits Use Checker` is enabled, the exception `InvalidatedQubitsUseCheckerException` will be thrown if an operation is applied to an already released qubit.</span></span> <span data-ttu-id="c4df9-109">Per altri dettagli, vedere la documentazione dell'API in [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) .</span><span class="sxs-lookup"><span data-stu-id="c4df9-109">See the API documentation on [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) for more details.</span></span>

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a><span data-ttu-id="c4df9-110">Uso del controllo di utilizzo qubits invalidato nel C# programma</span><span class="sxs-lookup"><span data-stu-id="c4df9-110">Using the Invalidated Qubits Use Checker in your C# Program</span></span>

<span data-ttu-id="c4df9-111">Di seguito è riportato un esempio C# di codice driver per l'utilizzo del computer Quantum `Trace
Simulator` con la `Invalidated Qubits Use Checker` abilitata:</span><span class="sxs-lookup"><span data-stu-id="c4df9-111">The following is an example of C# driver code for using the quantum computer `Trace
Simulator` with the `Invalidated Qubits Use Checker` enabled:</span></span> 

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
            traceSimCfg.useInvalidatedQubitsUseChecker = true; // enables useInvalidatedQubitsUseChecker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

<span data-ttu-id="c4df9-112">La classe `QCTraceSimulatorConfiguration` archivia la configurazione del simulatore di traccia del computer Quantum e può essere fornita come argomento per il costruttore di `QCTraceSimulator`.</span><span class="sxs-lookup"><span data-stu-id="c4df9-112">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span></span> <span data-ttu-id="c4df9-113">Quando `useInvalidatedQubitsUseChecker` è impostato su true, la `Invalidated Qubits Use Checker` è abilitata.</span><span class="sxs-lookup"><span data-stu-id="c4df9-113">When `useInvalidatedQubitsUseChecker` is set to true the `Invalidated Qubits Use Checker` is enabled.</span></span> <span data-ttu-id="c4df9-114">Per altri dettagli, vedere la documentazione dell'API su [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) e [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="c4df9-114">See the API documentation on [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) and [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="c4df9-115">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="c4df9-115">See also</span></span> ##

- <span data-ttu-id="c4df9-116">Panoramica di Quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="c4df9-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
