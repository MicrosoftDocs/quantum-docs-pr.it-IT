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
# <a name="distinct-inputs-checker"></a>Controllo input distinti

`Distinct Inputs Checker`È una parte del [simulatore di traccia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Quantum computer. È progettato per rilevare potenziali bug nel codice. Si consideri la seguente parte del codice Q # per illustrare i problemi rilevati dal pacchetto:

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

Quando l'utente esamina il programma, presuppone che l'ordine in cui `op1` `op2` vengono richiamati e non sia rilevante perché `q1` e `q2` sono qubits diversi e le operazioni agiscono su un qubits diverso. A questo punto, si consideri un esempio in cui viene usata questa operazione:

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

Ora `op1` e `op2` sono ottenuti usando un'applicazione parziale e condividono un qubit. Quando l'utente chiama `ApplyBoth` nell'esempio precedente, il risultato dell'operazione dipende dall'ordine di `op1` e `op2` all'interno di `ApplyBoth` . Questo non è certamente ciò che l'utente aspetta. Il `Distinct Inputs Checker` rileverà tali situazioni quando abilitata e genererà un'operazione `DistinctInputsCheckerException` . Per altri dettagli, vedere la documentazione dell'API in [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) .

## <a name="using-the-distinct-inputs-checker-in-your-c-program"></a>Uso del controllo degli input distinti nel programma C#

Di seguito è riportato un esempio di codice del driver C# per l'uso di Quantum computer Trace Simulator con la `Distinct Inputs Checker` funzionalità abilitata:

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

La classe `QCTraceSimulatorConfiguration` Archivia la configurazione del simulatore di traccia del computer Quantum e può essere fornita come argomento per il `QCTraceSimulator` costruttore. Quando `useDistinctInputsChecker` è impostato su true, l'oggetto `Distinct Inputs Checker` è abilitato. Per altri dettagli, vedere la documentazione dell'API su [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) e [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) .

## <a name="see-also"></a>Vedi anche

- Panoramica di Quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
