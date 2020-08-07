---
title: Controllo input distinti-Quantum Development Kit
description: Informazioni su Microsoft QDK Distinct inputs Checker, che usa il simulatore di traccia Quantum per verificare il Q# codice per i potenziali conflitti con qubits condivisi.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 750c94e7f861678d37f051619ff5b29bf4fd3d3e
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868271"
---
# <a name="quantum-trace-simulator-distinct-inputs-checker"></a><span data-ttu-id="755b2-103">Simulatore di traccia Quantum: controllo input distinti</span><span class="sxs-lookup"><span data-stu-id="755b2-103">Quantum trace simulator: distinct inputs checker</span></span>

<span data-ttu-id="755b2-104">Il controllo degli input distinti fa parte del [simulatore di traccia Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Development Kit Quantum.</span><span class="sxs-lookup"><span data-stu-id="755b2-104">The distinct inputs checker is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="755b2-105">È possibile usarlo per rilevare potenziali bug nel codice causato da conflitti con qubits condivisi.</span><span class="sxs-lookup"><span data-stu-id="755b2-105">You can use it to detect potential bugs in the code caused by conflicts with shared qubits.</span></span> 

## <a name="conflicts-with-shared-qubits"></a><span data-ttu-id="755b2-106">Conflitti con qubits condiviso</span><span class="sxs-lookup"><span data-stu-id="755b2-106">Conflicts with shared qubits</span></span>

<span data-ttu-id="755b2-107">Si consideri il frammento di Q# codice seguente per illustrare i problemi rilevati dal controllo degli input distinti:</span><span class="sxs-lookup"><span data-stu-id="755b2-107">Consider the following piece of Q# code to illustrate the issues detected by the distinct inputs checker:</span></span>

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

<span data-ttu-id="755b2-108">Quando si esamina questo programma, è possibile presupporre che l'ordine in cui chiama e non è `op1` `op2` importante, perché `q1` e `q2` sono qubits diversi e le operazioni agiscono su un qubits diverso.</span><span class="sxs-lookup"><span data-stu-id="755b2-108">When you look at this program, you can assume that the order in which it calls `op1` and `op2` does not matter, because `q1` and `q2` are different qubits and operations acting on different qubits commute.</span></span> 

<span data-ttu-id="755b2-109">A questo punto, si consideri l'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="755b2-109">Now, consider this example:</span></span>

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

<span data-ttu-id="755b2-110">Si noti che `op1` e `op2` vengono ottenuti usando un'applicazione parziale e condividono un qubit.</span><span class="sxs-lookup"><span data-stu-id="755b2-110">Note that `op1` and `op2` are both obtained using partial application and share a qubit.</span></span> <span data-ttu-id="755b2-111">Quando si chiama `ApplyBoth` in questo esempio, il risultato dell'operazione dipende dall'ordine di `op1` e dall'interno, `op2` `ApplyBoth` non da quello previsto.</span><span class="sxs-lookup"><span data-stu-id="755b2-111">When you call `ApplyBoth` in this example, the result of the operation depends on the order of `op1` and `op2` inside `ApplyBoth` - not what you would expect to happen.</span></span> <span data-ttu-id="755b2-112">Quando si Abilita il controllo degli input distinti, rileva tali situazioni e genera un'eccezione `DistinctInputsCheckerException` .</span><span class="sxs-lookup"><span data-stu-id="755b2-112">When you enable the distinct inputs checker, it detects such situations and throws a `DistinctInputsCheckerException`.</span></span> <span data-ttu-id="755b2-113">Per ulteriori informazioni, vedere <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> nella Q# libreria API.</span><span class="sxs-lookup"><span data-stu-id="755b2-113">For more information, see <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> in the Q# API library.</span></span>

## <a name="invoking-the-distinct-inputs-checker"></a><span data-ttu-id="755b2-114">Richiamo del controllo degli input distinti</span><span class="sxs-lookup"><span data-stu-id="755b2-114">Invoking the distinct inputs checker</span></span>

<span data-ttu-id="755b2-115">Per eseguire il simulatore di traccia Quantum con il controllo degli input distinti è necessario creare un' <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> istanza, impostare la `UseDistinctInputsChecker` proprietà su **true**e quindi creare una nuova <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> istanza con `QCTraceSimulatorConfiguration` come parametro.</span><span class="sxs-lookup"><span data-stu-id="755b2-115">To run the quantum trace simulator with the distinct inputs checker you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseDistinctInputsChecker` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDistinctInputsChecker = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-distinct-inputs-checker-in-a-c-host-program"></a><span data-ttu-id="755b2-116">Uso del controllo degli input distinti in un programma host C#</span><span class="sxs-lookup"><span data-stu-id="755b2-116">Using the distinct inputs checker in a C# host program</span></span>

<span data-ttu-id="755b2-117">Di seguito è riportato un esempio di programma host C# che usa il simulatore di traccia Quantum con il controllo degli input distinti abilitato:</span><span class="sxs-lookup"><span data-stu-id="755b2-117">The following is an example of C# host program that uses the quantum trace simulator with the distinct inputs checker enabled:</span></span>

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
            traceSimCfg.UseDistinctInputsChecker = true; //enables distinct inputs checker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="755b2-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="755b2-118">See also</span></span>

- <span data-ttu-id="755b2-119">Panoramica del [simulatore di traccia](xref:microsoft.quantum.machines.qc-trace-simulator.intro) Quantum Development Kit Quantum.</span><span class="sxs-lookup"><span data-stu-id="755b2-119">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="755b2-120"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>Riferimento all'API.</span><span class="sxs-lookup"><span data-stu-id="755b2-120">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="755b2-121"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>Riferimento all'API.</span><span class="sxs-lookup"><span data-stu-id="755b2-121">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="755b2-122"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException>Riferimento all'API.</span><span class="sxs-lookup"><span data-stu-id="755b2-122">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> API reference.</span></span>
