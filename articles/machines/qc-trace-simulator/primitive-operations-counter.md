---
title: Contatore operazioni primitive | Simulatore di traccia del computer Quantum | Microsoft Docs
description: Panoramica del simulatore di traccia del computer quantistico
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: 1f554c0a1b92c8f6b59be3a9d9965e0e25bd074f
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820420"
---
# <a name="primitive-operations-counter"></a>Contatore operazioni primitive  

Il `Primitive Operations Counter` fa parte del [simulatore di traccia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Quantum computer. Viene conteggiato il numero di esecuzioni primitive utilizzate da ogni operazione richiamata in un programma Quantum. Tutte le operazioni da `Microsoft.Quantum.Intrinsic` sono espresse in termini di singole rotazioni qubit, T Gate, Single qubit Clifford Gates, CNOT Gates e misurazioni di più qubit Pauli osservabili. Le statistiche raccolte vengono aggregate sui bordi del grafico delle chiamate operazioni. È ora possibile contare il numero di `T` Gate necessari per implementare l'operazione di `CCNOT`. 

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a>Uso del contatore operazioni primitive in C# un programma

Per verificare che `CCNOT` effettivamente richieda 7 `T` Gates e che `ApplySampleWithCCNOT` esegua 8 `T` Gate, è possibile usare C# il codice seguente:

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.usePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

La prima parte del programma esegue `ApplySampleWithCCNOT`. Nella seconda parte viene usato il metodo `QCTraceSimulator.GetMetric` per ottenere il numero di controlli T eseguiti da `ApplySampleWithCCNOT`: 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

Quando `GetMetric` viene chiamato con due parametri di tipo, restituisce il valore della metrica associata a un bordo del grafico della chiamata specificato. Nell'esempio di operazione `Primitive.CCNOT` viene chiamato all'interno di `ApplySampleWithCCNOT` e quindi il grafico delle chiamate contiene la `<Primitive.CCNOT, ApplySampleWithCCNOT>`Edge. 

Per ottenere il numero di `CNOT` Gate usati, è possibile aggiungere la riga seguente:
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

Infine, per restituire tutte le statistiche raccolte dal contatore di controllo in formato CSV, è possibile usare quanto segue:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>Vedi anche ##

- Panoramica di Quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
