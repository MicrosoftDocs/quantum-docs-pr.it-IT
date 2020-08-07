---
title: Controllo di utilizzo qubits invalidato-Quantum Development Kit
description: Informazioni su Microsoft QDK Invalidated qubits use Checker, che usa il simulatore di traccia Quantum per verificare il Q# codice per la qubits potenzialmente non valida.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
no-loc:
- Q#
- $$v
ms.openlocfilehash: c451747badba03801bd4ecd419420f131ac502d6
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868288"
---
# <a name="quantum-trace-simulator-invalidated-qubits-use-checker"></a>Simulatore di traccia Quantum: controllo di utilizzo qubits invalidato

Il controllo di utilizzo di qubits invalidato fa parte del [simulatore di traccia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Quantum Development Kit Quantum. È possibile usarlo per rilevare potenziali bug nel codice causato da qubits non validi. 

## <a name="invalid-qubits"></a>Qubits non valido

Si consideri il frammento di Q# codice seguente per illustrare i problemi rilevati dal controllo di utilizzo qubits invalidato:

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

Quando si applica l' `H` operazione a `q[0]` , punta a un qubit già rilasciato, che può causare un comportamento non definito. Quando il controllo di utilizzo di qubits invalidato è abilitato, genera l'eccezione `InvalidatedQubitsUseCheckerException` se il programma applica un'operazione a un qubit già rilasciato. Per altre informazioni, vedere <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException>.

## <a name="invoking-the-invalidated-qubits-use-checker"></a>Richiamo del controllo Use qubits invalidato

Per eseguire il simulatore di traccia Quantum con il controllo di utilizzo qubits invalidato, è necessario creare un' <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> istanza, impostare la `UseInvalidatedQubitsUseChecker` proprietà su **true**, quindi creare una nuova <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> istanza con `QCTraceSimulatorConfiguration` come parametro. 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseInvalidatedQubitsUseChecker = true;
var sim = new QCTraceSimulator(config);
```


## <a name="using-the-invalidated-qubits-use-checker-in-a-c-host-program"></a>Uso del controllo di utilizzo qubits invalidato in un programma host C#

Di seguito è riportato un esempio di programmi host C# che usa il simulatore di traccia Quantum con il controllo di utilizzo qubits invalidato abilitato: 

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

## <a name="see-also"></a>Vedere anche

- Panoramica del [simulatore di traccia](xref:microsoft.quantum.machines.qc-trace-simulator.intro) Quantum Development Kit Quantum.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>Riferimento all'API.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>Riferimento all'API.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException>Riferimento all'API.