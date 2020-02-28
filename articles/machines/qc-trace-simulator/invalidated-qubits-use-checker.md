---
title: Controllo utilizzo qubit invalidati
description: 'Informazioni su Microsoft QDK Invalidated qubits use Checker, che controlla il codice Q # per qubits potenzialmente non validi.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: e2bbb12448e27f28db030a0084302fb24f46f26b
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907070"
---
# <a name="invalidated-qubits-use-checker"></a>Controllo utilizzo qubits invalidato

Il `Invalidated Qubits Use Checker` fa parte del Quantum computer [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) progettato per rilevare potenziali bug nel codice. Si consideri il seguente codice Q # per illustrare i problemi rilevati dal `Invalidated Qubits Use Checker`.

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

Quando `H` viene applicato al `q[0]` fa riferimento a una qubit già rilasciata. Questo può causare un comportamento indefinito. Quando la `Invalidated Qubits Use Checker` è abilitata, verrà generata l'eccezione `InvalidatedQubitsUseCheckerException` se un'operazione viene applicata a una qubit già rilasciata. Per altri dettagli, vedere la documentazione dell'API in [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) .

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a>Uso del controllo di utilizzo qubits invalidato nel C# programma

Di seguito è riportato un esempio C# di codice driver per l'utilizzo del computer Quantum `Trace
Simulator` con la `Invalidated Qubits Use Checker` abilitata: 

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

La classe `QCTraceSimulatorConfiguration` archivia la configurazione del simulatore di traccia del computer Quantum e può essere fornita come argomento per il costruttore di `QCTraceSimulator`. Quando `useInvalidatedQubitsUseChecker` è impostato su true, la `Invalidated Qubits Use Checker` è abilitata. Per altri dettagli, vedere la documentazione dell'API su [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) e [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) .

## <a name="see-also"></a>Vedere anche ##

- Panoramica di Quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
