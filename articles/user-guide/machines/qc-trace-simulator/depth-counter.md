---
title: Contatore profondità
description: Informazioni sul contatore Microsoft QDK Depth, che raccoglie i conteggi della profondità di ogni operazione richiamata in un programma Quantum.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: d532a9f512b8c87d83d62ed26e3bb67e1b6f668b
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274938"
---
# <a name="depth-counter"></a>Contatore profondità

`Depth Counter`È una parte del [simulatore di traccia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Quantum computer.
Viene usato per raccogliere i conteggi della profondità di ogni operazione richiamata in un programma Quantum. Tutte le operazioni da <xref:microsoft.quantum.intrinsic> sono espresse in termini di singole rotazioni qubit, T Gate, Single qubit Clifford Gates, CNOT Gates e misurazioni di qubit Pauli osservabili. Gli utenti possono impostare la profondità per ognuna delle operazioni primitive tramite il `gateTimes` campo di <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> .

Per impostazione predefinita, tutte le operazioni hanno la profondità 0 ad eccezione di T Gate con profondità 1. Ciò significa che, per impostazione predefinita, viene calcolata solo la profondità T delle operazioni (che è spesso auspicabile). Le statistiche raccolte vengono aggregate su tutti i bordi del grafico delle chiamate di operazioni. 

È ora possibile calcolare la <xref:microsoft.quantum.intrinsic.t> profondità dell' <xref:microsoft.quantum.intrinsic.ccnot> operazione. Si userà il codice di esempio Q # seguente:

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a>Uso del contatore depth in un programma C#

Per verificare che `CCNOT` abbia `T` una profondità di 5 e `ApplySampleWithCCNOT` `T` una profondità di 6, è possibile usare il codice C# seguente:

```csharp
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.useDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

Viene eseguita la prima parte del programma `ApplySampleWithCCNOT` . Nella seconda parte viene usato il metodo `QCTraceSimulator.GetMetric` per ottenere la `T` profondità di `CCNOT` e `ApplySampleWithCCNOT` : 

```csharp
double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

Infine, per restituire tutte le statistiche raccolte `Depth Counter` in formato CSV, è possibile usare quanto segue:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a>Vedi anche ##

- Panoramica di Quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
