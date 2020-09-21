---
title: Contatore larghezza-Quantum Development Kit
description: Informazioni sul contatore Microsoft QDK Width, che usa il simulatore di traccia Quantum per contare il numero di qubits allocati e presi in prestito dalle operazioni in un Q# programma.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 701c36dd8c8b087a2728cd935aee0c2ffc4f59f9
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835945"
---
# <a name="quantum-trace-simulator-width-counter"></a>Simulatore di traccia Quantum: contatore larghezza

Il contatore della larghezza fa parte del [simulatore di traccia Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Development Kit Quantum. È possibile usarlo per conteggiare il numero di qubits allocati e presi in prestito da ogni operazione in un Q# programma. Alcune operazioni primitive possono allocare qubits aggiuntive, ad esempio, moltiplicare `X` le operazioni controllate o controllate `T` .

## <a name="invoking-the-width-counter"></a>Richiamo del contatore della larghezza

Per eseguire il simulatore di traccia Quantum con il contatore larghezza, è necessario creare un' <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> istanza, impostare la `UseWidthCounter` proprietà su **true**, quindi creare una nuova <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> istanza con `QCTraceSimulatorConfiguration` come parametro. 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-width-counter-in-a-c-host-program"></a>Uso del contatore Width in un programma host C#

Nell'esempio di C# seguente in questa sezione viene calcolato il numero di qubits aggiuntivi allocati dall'implementazione di un'operazione di moltiplicazione controllata <xref:microsoft.quantum.intrinsic.x> , in base al Q# codice di esempio seguente:

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

L'operazione di moltiplicazione controllata <xref:microsoft.quantum.intrinsic.x> agisce su un totale di cinque qubits, alloca due [qubits ausiliari](xref:microsoft.quantum.glossary#ancilla)e ha una larghezza di input pari a **5**. Usare il programma C# seguente per verificare i conteggi:

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
int totalNumberOfQubits = 5;
var res = ApplyMultiControlledX.Run(sim, totalNumberOfQubits).Result;

double allocatedQubits = 
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.ExtraWidth,
        functor: OperationFunctor.Controlled); 

double inputWidth =
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.InputWidth,
        functor: OperationFunctor.Controlled);
```

La prima parte del programma esegue l' `ApplyMultiControlledX` operazione. La seconda parte usa il [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) metodo per recuperare il numero di qubits allocati, nonché il numero di qubits che l' `Controlled X` operazione ha ricevuto come input. 

Infine, è possibile restituire tutte le statistiche raccolte dal contatore della larghezza in formato CSV usando quanto segue:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a>Vedere anche

- Panoramica del [simulatore di traccia](xref:microsoft.quantum.machines.qc-trace-simulator.intro) Quantum Development Kit Quantum.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>Riferimento all'API.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>Riferimento all'API.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter>Riferimento all'API.
