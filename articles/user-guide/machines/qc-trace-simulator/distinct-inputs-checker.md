---
title: Controllo input distinti-Quantum Development Kit
description: Informazioni su Microsoft QDK Distinct inputs Checker, che usa il simulatore di traccia Quantum per verificare il Q# codice per i potenziali conflitti con qubits condivisi.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: conceptual
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8076a705b1960ae8e23be4cea87e613329a24f77
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858653"
---
# <a name="quantum-trace-simulator-distinct-inputs-checker"></a>Simulatore di traccia Quantum: controllo input distinti

Il controllo degli input distinti fa parte del [simulatore di traccia Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Development Kit Quantum. È possibile usarlo per rilevare potenziali bug nel codice causato da conflitti con qubits condivisi. 

## <a name="conflicts-with-shared-qubits"></a>Conflitti con qubits condiviso

Si consideri il frammento di Q# codice seguente per illustrare i problemi rilevati dal controllo degli input distinti:

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

Quando si esamina questo programma, è possibile presupporre che l'ordine in cui chiama e non è `op1` `op2` importante, perché `q1` e `q2` sono qubits diversi e le operazioni agiscono su un qubits diverso. 

A questo punto, si consideri l'esempio seguente:

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

Si noti che `op1` e `op2` vengono ottenuti usando un'applicazione parziale e condividono un qubit. Quando si chiama `ApplyBoth` in questo esempio, il risultato dell'operazione dipende dall'ordine di `op1` e dall'interno, `op2` `ApplyBoth` non da quello previsto. Quando si Abilita il controllo degli input distinti, rileva tali situazioni e genera un'eccezione `DistinctInputsCheckerException` . Per ulteriori informazioni, vedere <xref:Microsoft.Quantum.Simulation.QCTraceSimulatorRuntime.DistinctInputsCheckerException> nella Q# libreria API.

## <a name="invoking-the-distinct-inputs-checker"></a>Richiamo del controllo degli input distinti

Per eseguire il simulatore di traccia Quantum con il controllo degli input distinti è necessario creare un' <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> istanza, impostare la `UseDistinctInputsChecker` proprietà su **true** e quindi creare una nuova <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> istanza con `QCTraceSimulatorConfiguration` come parametro. 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDistinctInputsChecker = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-distinct-inputs-checker-in-a-c-host-program"></a>Uso del controllo degli input distinti in un programma host C#

Di seguito è riportato un esempio di programma host C# che usa il simulatore di traccia Quantum con il controllo degli input distinti abilitato:

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

## <a name="see-also"></a>Vedi anche

- Panoramica del [simulatore di traccia](xref:microsoft.quantum.machines.qc-trace-simulator.intro) Quantum Development Kit Quantum.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>Riferimento all'API.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>Riferimento all'API.
- <xref:Microsoft.Quantum.Simulation.QCTraceSimulatorRuntime.DistinctInputsCheckerException>Riferimento all'API.
