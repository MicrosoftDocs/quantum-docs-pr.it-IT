---
title: Controllo utilizzo qubit invalidati
description: 'Informazioni su Microsoft QDK Invalidated qubits use Checker, che controlla il codice Q # per qubits potenzialmente non validi.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: e2bbb12448e27f28db030a0084302fb24f46f26b
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274899"
---
# <a name="invalidated-qubits-use-checker"></a><span data-ttu-id="13ce7-103">Controllo utilizzo qubits invalidato</span><span class="sxs-lookup"><span data-stu-id="13ce7-103">Invalidated Qubits Use Checker</span></span>

<span data-ttu-id="13ce7-104">Il `Invalidated Qubits Use Checker` fa parte del Quantum computer [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) progettato per rilevare potenziali bug nel codice.</span><span class="sxs-lookup"><span data-stu-id="13ce7-104">The `Invalidated Qubits Use Checker` is a part of the quantum computer [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) designed for detecting potential bugs in the code.</span></span> <span data-ttu-id="13ce7-105">Si consideri la seguente parte del codice Q # per illustrare i problemi rilevati da `Invalidated Qubits Use Checker` .</span><span class="sxs-lookup"><span data-stu-id="13ce7-105">Consider the following piece of Q# code to illustrate the issues detected by the `Invalidated Qubits Use Checker`.</span></span>

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

<span data-ttu-id="13ce7-106">Quando `H` viene applicato `q[0]` , punta a un qubit già rilasciato.</span><span class="sxs-lookup"><span data-stu-id="13ce7-106">When `H` is applied to `q[0]` it points to an already released qubit.</span></span> <span data-ttu-id="13ce7-107">Questo può causare un comportamento indefinito.</span><span class="sxs-lookup"><span data-stu-id="13ce7-107">This can cause undefined behavior.</span></span> <span data-ttu-id="13ce7-108">Quando `Invalidated Qubits Use Checker` è abilitato, l'eccezione viene `InvalidatedQubitsUseCheckerException` generata se un'operazione viene applicata a un qubit già rilasciato.</span><span class="sxs-lookup"><span data-stu-id="13ce7-108">When the `Invalidated Qubits Use Checker` is enabled, the exception `InvalidatedQubitsUseCheckerException` will be thrown if an operation is applied to an already released qubit.</span></span> <span data-ttu-id="13ce7-109">Per altri dettagli, vedere la documentazione dell'API in [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) .</span><span class="sxs-lookup"><span data-stu-id="13ce7-109">See the API documentation on [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) for more details.</span></span>

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a><span data-ttu-id="13ce7-110">Uso del controllo di utilizzo qubits invalidato nel programma C#</span><span class="sxs-lookup"><span data-stu-id="13ce7-110">Using the Invalidated Qubits Use Checker in your C# Program</span></span>

<span data-ttu-id="13ce7-111">Di seguito è riportato un esempio di codice del driver C# per l'uso del computer Quantum `Trace
Simulator` con la `Invalidated Qubits Use Checker` funzionalità abilitata:</span><span class="sxs-lookup"><span data-stu-id="13ce7-111">The following is an example of C# driver code for using the quantum computer `Trace
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

<span data-ttu-id="13ce7-112">La classe `QCTraceSimulatorConfiguration` Archivia la configurazione del simulatore di traccia del computer Quantum e può essere fornita come argomento per il `QCTraceSimulator` costruttore.</span><span class="sxs-lookup"><span data-stu-id="13ce7-112">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span></span> <span data-ttu-id="13ce7-113">Quando `useInvalidatedQubitsUseChecker` è impostato su true, l'oggetto `Invalidated Qubits Use Checker` è abilitato.</span><span class="sxs-lookup"><span data-stu-id="13ce7-113">When `useInvalidatedQubitsUseChecker` is set to true the `Invalidated Qubits Use Checker` is enabled.</span></span> <span data-ttu-id="13ce7-114">Per altri dettagli, vedere la documentazione dell'API su [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) e [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="13ce7-114">See the API documentation on [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) and [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="13ce7-115">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="13ce7-115">See also</span></span> ##

- <span data-ttu-id="13ce7-116">Panoramica di Quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="13ce7-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
