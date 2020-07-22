---
title: Contatore operazioni primitive-Quantum Development Kit
description: 'Informazioni sul contatore delle operazioni primitive Microsoft QDK, che usa il simulatore di traccia Quantum per tenere traccia delle esecuzioni primitive usate dalle operazioni in un programma Q #.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: ea022d499354f7cefd60da690466496e0ce7c336
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871026"
---
# <a name="quantum-trace-simulator-primitive-operations-counter"></a>Simulatore di traccia Quantum: contatore operazioni primitive

Il contatore delle operazioni primitive fa parte del [simulatore di traccia Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Development Kit Quantum. Viene conteggiato il numero di esecuzioni primitive utilizzate da ogni operazione richiamata in un programma Quantum. 

Tutte <xref:microsoft.quantum.intrinsic> le operazioni sono espresse in termini di rotazioni a singolo qubit, operazioni T, operazioni Clifford qubit singole, operazioni CNOT e misurazioni di osservabili di più qubit di Pauli. Il contatore operazioni primitive aggrega e raccoglie statistiche su tutti i bordi del [grafico chiamate](https://en.wikipedia.org/wiki/Call_graph)dell'operazione.

## <a name="invoking-the-primitive-operation-counter"></a>Richiamo del contatore delle operazioni primitive

Per eseguire il simulatore di traccia Quantum con il contatore delle operazioni primitive, è necessario creare un' <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> istanza, impostare la `UsePrimitiveOperationsCounter` proprietà su **true**, quindi creare una nuova <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> istanza con `QCTraceSimulatorConfiguration` come parametro.

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-primitive-operation-counter-in-a-c-host-program"></a>Uso del contatore delle operazioni primitive in un programma host C#

L'esempio C# seguente in questa sezione conta il numero <xref:microsoft.quantum.intrinsic.t> di operazioni necessarie per implementare l' <xref:microsoft.quantum.intrinsic.ccnot> operazione, in base al codice di esempio Q # seguente:

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

Per verificare che siano `CCNOT` necessarie sette `T` operazioni e che `ApplySampleWithCCNOT` esegua otto `T` operazioni, usare il codice C# seguente:

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

Viene eseguita la prima parte del programma `ApplySampleWithCCNOT` . La seconda parte usa il [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) metodo per recuperare il numero di `T` operazioni eseguite da `ApplySampleWithCCNOT` : 

Quando si chiama `GetMetric` con due parametri di tipo, viene restituito il valore della metrica associata a un bordo del grafico della chiamata specificato. Nell'esempio precedente il programma chiama l' `Primitive.CCNOT` operazione all'interno `ApplySampleWithCCNOT` di e, pertanto, il grafico delle chiamate contiene il bordo `<Primitive.CCNOT, ApplySampleWithCCNOT>` . 

Per recuperare il numero di `CNOT` operazioni utilizzate, aggiungere la riga seguente:
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

Infine, è possibile restituire tutte le statistiche raccolte dal contatore delle operazioni primitive in formato CSV usando quanto segue:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>Vedere anche

- Panoramica del [simulatore di traccia](xref:microsoft.quantum.machines.qc-trace-simulator.intro) Quantum Development Kit Quantum.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>Riferimento all'API.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>Riferimento all'API.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.PrimitiveOperationsGroupsNames>Riferimento all'API.