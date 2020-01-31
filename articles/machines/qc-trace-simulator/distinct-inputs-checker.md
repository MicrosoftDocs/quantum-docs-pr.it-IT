---
title: Controllo input distinti | Simulatore di traccia del computer Quantum | Microsoft Docs
description: Panoramica del simulatore di traccia del computer quantistico
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: 3c21a54f5da83bf1ea0792e79cc773be5fba71e8
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820964"
---
# <a name="distinct-inputs-checker"></a>Controllo input distinti

Il `Distinct Inputs Checker` fa parte del [simulatore di traccia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Quantum computer. È progettato per rilevare potenziali bug nel codice. Si consideri la seguente parte del codice Q # per illustrare i problemi rilevati dal pacchetto:

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

Quando l'utente esamina il programma, presuppone che l'ordine in cui vengono chiamati `op1` e `op2` non sia rilevante perché `q1` e `q2` sono qubits e le operazioni eseguite su qubits diversi. A questo punto, si consideri un esempio in cui viene usata questa operazione:

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

Ora `op1` e `op2` sono ottenuti usando un'applicazione parziale e condividono un qubit. Quando l'utente chiama `ApplyBoth` nell'esempio precedente, il risultato dell'operazione dipenderà dall'ordine di `op1` e `op2` all'interno `ApplyBoth`. Questo non è certamente ciò che l'utente aspetta. Il `Distinct Inputs Checker` rileverà tali situazioni quando abilitata e genererà `DistinctInputsCheckerException`. Per altri dettagli, vedere la documentazione dell'API in [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) .

## <a name="using-the-distinct-inputs-checker-in-your-c-program"></a>Uso del controllo degli input distinti nel C# programma

Di seguito è riportato un esempio C# di codice del driver per l'uso di Quantum computer Trace Simulator con la `Distinct Inputs Checker` abilitata:

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

La classe `QCTraceSimulatorConfiguration` archivia la configurazione del simulatore di traccia del computer Quantum e può essere fornita come argomento per il costruttore di `QCTraceSimulator`. Quando `useDistinctInputsChecker` è impostato su true, la `Distinct Inputs Checker` è abilitata. Per altri dettagli, vedere la documentazione dell'API su [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) e [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) .

## <a name="see-also"></a>Vedi anche

- Panoramica di Quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
