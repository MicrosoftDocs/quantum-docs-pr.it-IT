---
title: Contatore di profondità-Quantum Development Kit
description: 'Informazioni sul contatore Microsoft QDK Depth, che usa il simulatore di traccia Quantum per raccogliere i conteggi della profondità di ogni operazione richiamata in un programma Q #.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: 811e387fedf547d2681518ae0bb525c13dc84ff4
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871128"
---
# <a name="quantum-trace-simulator-depth-counter"></a>Simulatore di traccia Quantum: contatore Depth

Il contatore Depth è parte del [simulatore di traccia Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Development Kit Quantum.
È possibile usarlo per raccogliere i conteggi che rappresentano il limite inferiore della profondità di ogni operazione richiamata in un programma Quantum. 

## <a name="depth-values"></a>Valori di profondità

Per impostazione predefinita, tutte le operazioni hanno una profondità di **0** tranne l' `T` operazione, che ha una profondità di **1**. Ciò significa che, per impostazione predefinita, `T` viene calcolata solo la profondità delle operazioni (che è spesso auspicabile). Il contatore Depth aggrega e raccoglie le statistiche su tutti i bordi del [grafico delle chiamate](https://en.wikipedia.org/wiki/Call_graph)dell'operazione.

Tutte <xref:microsoft.quantum.intrinsic> le operazioni sono espresse in termini di rotazioni, operazioni, operazioni di qubit Clifford a singolo qubit, operazioni <xref:microsoft.quantum.intrinsic.t> <xref:microsoft.quantum.intrinsic.cnot> e misurazioni di più qubit di Pauli osservabili. Gli utenti possono impostare la profondità per ognuna delle operazioni primitive tramite il `gateTimes` campo di <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> .

## <a name="invoking-the-depth-counter"></a>Richiamo del contatore di profondità

Per eseguire il simulatore di traccia Quantum con il contatore Depth, è necessario creare un' <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> istanza, impostarne la `UseDepthCounter` proprietà su **true**e quindi creare una nuova <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> istanza con `QCTraceSimulatorConfiguration` come parametro. 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-depth-counter-in-a-c-host-program"></a>Uso del contatore depth in un programma host C#

Nell'esempio di C# seguente in questa sezione viene calcolata la `T` profondità dell' `CCNOT` operazione, in base al codice di esempio Q # seguente:

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

Per verificare che `CCNOT` abbia `T` la profondità **5** e `ApplySampleWithCCNOT` `T` la profondità **6**, usare il codice C# seguente:

```csharp
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

Viene eseguita la prima parte del programma `ApplySampleWithCCNOT` . La seconda parte usa il [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) metodo per recuperare la `T` profondità di `CCNOT` e `ApplySampleWithCCNOT` . 

Infine, è possibile restituire tutte le statistiche raccolte dal contatore di profondità nel formato CSV usando quanto segue:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a>Vedere anche

- Panoramica del [simulatore di traccia](xref:microsoft.quantum.machines.qc-trace-simulator.intro) Quantum Development Kit Quantum.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>Riferimento all'API.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>Riferimento all'API.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter>Riferimento all'API.
