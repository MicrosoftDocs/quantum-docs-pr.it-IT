---
title: Contatore operazioni primitive
description: Informazioni sul contatore delle operazioni primitive Microsoft QDK, che tiene traccia del numero di esecuzioni primitive usate dalle operazioni in un programma Quantum.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: 8bdb0aed370e72b58b23025f1685ad7ce1a77a43
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274889"
---
# <a name="primitive-operations-counter"></a>Contatore operazioni primitive  

`Primitive Operations Counter`È una parte del [simulatore di traccia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Quantum computer. Viene conteggiato il numero di esecuzioni primitive utilizzate da ogni operazione richiamata in un programma Quantum. Tutte le operazioni da `Microsoft.Quantum.Intrinsic` sono espresse in termini di singole rotazioni qubit, T Gate, Single qubit Clifford Gates, CNOT Gates e misurazioni di qubit Pauli osservabili. Le statistiche raccolte vengono aggregate sui bordi del grafico delle chiamate operazioni. È ora possibile contare il numero `T` di controlli necessari per implementare l' `CCNOT` operazione. 

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a>Uso del contatore operazioni primitive in un programma C#

Per verificare che siano `CCNOT` effettivamente necessari 7 `T` cancelli e che `ApplySampleWithCCNOT` esegua 8 `T` porte, è possibile usare il codice C# seguente:

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

Viene eseguita la prima parte del programma `ApplySampleWithCCNOT` . Nella seconda parte viene usato il metodo `QCTraceSimulator.GetMetric` per ottenere il numero di controlli T eseguiti da `ApplySampleWithCCNOT` : 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

Quando `GetMetric` viene chiamato con due parametri di tipo, restituisce il valore della metrica associata a un bordo del grafico della chiamata specificato. Nell'operazione di esempio `Primitive.CCNOT` viene chiamato all'interno `ApplySampleWithCCNOT` di e, pertanto, il grafico delle chiamate contiene il bordo `<Primitive.CCNOT, ApplySampleWithCCNOT>` . 

Per ottenere il numero di `CNOT` porte utilizzate, è possibile aggiungere la riga seguente:
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

Infine, per restituire tutte le statistiche raccolte dal contatore di controllo in formato CSV, è possibile usare quanto segue:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>Vedi anche ##

- Panoramica di Quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
