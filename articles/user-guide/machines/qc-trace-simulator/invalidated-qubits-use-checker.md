---
title: Controllo di utilizzo qubits invalidato-Quantum Development Kit
description: Informazioni su Microsoft QDK Invalidated qubits use Checker, che usa il simulatore di traccia Quantum per verificare il Q# codice per la qubits potenzialmente non valida.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
no-loc:
- Q#
- $$v
ms.openlocfilehash: 18371b3798d0eaa12d4e7107f58f44379594619f
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835996"
---
# <a name="quantum-trace-simulator-invalidated-qubits-use-checker"></a><span data-ttu-id="e4d34-103">Simulatore di traccia Quantum: controllo di utilizzo qubits invalidato</span><span class="sxs-lookup"><span data-stu-id="e4d34-103">Quantum trace simulator: invalidated qubits use checker</span></span>

<span data-ttu-id="e4d34-104">Il controllo di utilizzo di qubits invalidato fa parte del [simulatore di traccia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Quantum Development Kit Quantum.</span><span class="sxs-lookup"><span data-stu-id="e4d34-104">The invalidated qubits use checker is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="e4d34-105">È possibile usarlo per rilevare potenziali bug nel codice causato da qubits non validi.</span><span class="sxs-lookup"><span data-stu-id="e4d34-105">You can use it to detect potential bugs in the code caused by invalid qubits.</span></span> 

## <a name="invalid-qubits"></a><span data-ttu-id="e4d34-106">Qubits non valido</span><span class="sxs-lookup"><span data-stu-id="e4d34-106">Invalid qubits</span></span>

<span data-ttu-id="e4d34-107">Si consideri il frammento di Q# codice seguente per illustrare i problemi rilevati dal controllo di utilizzo qubits invalidato:</span><span class="sxs-lookup"><span data-stu-id="e4d34-107">Consider the following piece of Q# code to illustrate the issues detected by the invalidated qubits use checker:</span></span>

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

<span data-ttu-id="e4d34-108">Quando si applica l' `H` operazione a `q[0]` , punta a un qubit già rilasciato, che può causare un comportamento non definito.</span><span class="sxs-lookup"><span data-stu-id="e4d34-108">When you apply the `H` operation to `q[0]`, it points to an already released qubit, which can cause undefined behavior.</span></span> <span data-ttu-id="e4d34-109">Quando il controllo di utilizzo di qubits invalidato è abilitato, genera l'eccezione `InvalidatedQubitsUseCheckerException` se il programma applica un'operazione a un qubit già rilasciato.</span><span class="sxs-lookup"><span data-stu-id="e4d34-109">When the Invalidated Qubits Use Checker is enabled, it throws the exception `InvalidatedQubitsUseCheckerException` if the program applies an operation to an already released qubit.</span></span> <span data-ttu-id="e4d34-110">Per altre informazioni, vedere <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException>.</span><span class="sxs-lookup"><span data-stu-id="e4d34-110">For more information, see <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException>.</span></span>

## <a name="invoking-the-invalidated-qubits-use-checker"></a><span data-ttu-id="e4d34-111">Richiamo del controllo Use qubits invalidato</span><span class="sxs-lookup"><span data-stu-id="e4d34-111">Invoking the invalidated qubits use checker</span></span>

<span data-ttu-id="e4d34-112">Per eseguire il simulatore di traccia Quantum con il controllo di utilizzo qubits invalidato, è necessario creare un' <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> istanza, impostare la `UseInvalidatedQubitsUseChecker` proprietà su **true**, quindi creare una nuova <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> istanza con `QCTraceSimulatorConfiguration` come parametro.</span><span class="sxs-lookup"><span data-stu-id="e4d34-112">To run the quantum trace simulator with the invalidated qubits use checker you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseInvalidatedQubitsUseChecker` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseInvalidatedQubitsUseChecker = true;
var sim = new QCTraceSimulator(config);
```


## <a name="using-the-invalidated-qubits-use-checker-in-a-c-host-program"></a><span data-ttu-id="e4d34-113">Uso del controllo di utilizzo qubits invalidato in un programma host C#</span><span class="sxs-lookup"><span data-stu-id="e4d34-113">Using the invalidated qubits use checker in a C# host program</span></span>

<span data-ttu-id="e4d34-114">Di seguito è riportato un esempio di programmi host C# che usa il simulatore di traccia Quantum con il controllo di utilizzo qubits invalidato abilitato:</span><span class="sxs-lookup"><span data-stu-id="e4d34-114">The following is an example of C# host programs that uses the quantum trace simulator with the invalidated qubits use checker enabled:</span></span> 

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
            traceSimCfg.UseInvalidatedQubitsUseChecker = true; // enables UseInvalidatedQubitsUseChecker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="e4d34-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4d34-115">See also</span></span>

- <span data-ttu-id="e4d34-116">Panoramica del [simulatore di traccia](xref:microsoft.quantum.machines.qc-trace-simulator.intro) Quantum Development Kit Quantum.</span><span class="sxs-lookup"><span data-stu-id="e4d34-116">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="e4d34-117"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>Riferimento all'API.</span><span class="sxs-lookup"><span data-stu-id="e4d34-117">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="e4d34-118"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>Riferimento all'API.</span><span class="sxs-lookup"><span data-stu-id="e4d34-118">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="e4d34-119"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException>Riferimento all'API.</span><span class="sxs-lookup"><span data-stu-id="e4d34-119">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException> API reference.</span></span>