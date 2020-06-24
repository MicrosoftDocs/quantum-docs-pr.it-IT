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
# <a name="invalidated-qubits-use-checker"></a>Controllo utilizzo qubits invalidato

Il `Invalidated Qubits Use Checker` fa parte del Quantum computer [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) progettato per rilevare potenziali bug nel codice. Si consideri la seguente parte del codice Q # per illustrare i problemi rilevati da `Invalidated Qubits Use Checker` .

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

Quando `H` viene applicato `q[0]` , punta a un qubit già rilasciato. Questo può causare un comportamento indefinito. Quando `Invalidated Qubits Use Checker` è abilitato, l'eccezione viene `InvalidatedQubitsUseCheckerException` generata se un'operazione viene applicata a un qubit già rilasciato. Per altri dettagli, vedere la documentazione dell'API in [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) .

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a>Uso del controllo di utilizzo qubits invalidato nel programma C#

Di seguito è riportato un esempio di codice del driver C# per l'uso del computer Quantum `Trace
Simulator` con la `Invalidated Qubits Use Checker` funzionalità abilitata: 

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

La classe `QCTraceSimulatorConfiguration` Archivia la configurazione del simulatore di traccia del computer Quantum e può essere fornita come argomento per il `QCTraceSimulator` costruttore. Quando `useInvalidatedQubitsUseChecker` è impostato su true, l'oggetto `Invalidated Qubits Use Checker` è abilitato. Per altri dettagli, vedere la documentazione dell'API su [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) e [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) .

## <a name="see-also"></a>Vedi anche ##

- Panoramica di Quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
