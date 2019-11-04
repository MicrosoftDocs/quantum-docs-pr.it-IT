---
title: Contatore profondità | Simulatore di traccia del computer Quantum | Microsoft Docs
description: Panoramica del simulatore di traccia del computer Quantum
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: f5fcaa64e91290d377eeba597df2e307e187277c
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184900"
---
# <a name="depth-counter"></a>Contatore profondità

Il `Depth Counter` fa parte del [simulatore di traccia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Quantum computer.
Viene usato per raccogliere i conteggi della profondità di ogni operazione richiamata in un programma Quantum. Tutte le operazioni da <xref:microsoft.quantum.intrinsic> sono espresse in termini di singole rotazioni qubit, T Gate, Single qubit Clifford Gates, CNOT Gates e misurazioni di più qubit Pauli osservabili. Gli utenti possono impostare la profondità per ognuna delle operazioni primitive tramite il campo `gateTimes` di <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.

Per impostazione predefinita, tutte le operazioni hanno la profondità 0 ad eccezione di T Gate con profondità 1. Ciò significa che, per impostazione predefinita, viene calcolata solo la profondità T delle operazioni (che è spesso auspicabile). Le statistiche raccolte vengono aggregate su tutti i bordi del grafico delle chiamate di operazioni. 

È ora possibile calcolare la profondità <xref:microsoft.quantum.intrinsic.t> dell'operazione di <xref:microsoft.quantum.intrinsic.ccnot>. Si userà il seguente codice del driver Q #: 

```qsharp
open Microsoft.Quantum.Primitive;
operation CCNOTDriver() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a>Uso del contatore depth in C# un programma

Per verificare che `CCNOT` abbia `T` Depth 5 e `CCNOTDriver` abbia `T` profondità 6 è possibile usare il codice C# seguente:

```csharp 
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.useDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = CCNOTDriver.Run(sim).Result;

double tDepth = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<CCNOTDriver>(DepthCounter.Metrics.Depth);
```

La prima parte del programma esegue `CCNOTDriver`. Nella seconda parte viene usato il metodo `QCTraceSimulator.GetMetric` per ottenere la profondità `T` di `CCNOT` e `CCNOTDriver`: 

```csharp
double tDepth = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<CCNOTDriver>(DepthCounter.Metrics.Depth);
```

Infine, per restituire tutte le statistiche raccolte da `Depth Counter` in formato CSV, è possibile usare quanto segue:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a>Vedi anche ##

- Panoramica di Quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
