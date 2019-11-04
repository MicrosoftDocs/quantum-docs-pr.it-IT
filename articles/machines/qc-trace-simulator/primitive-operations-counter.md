---
title: Contatore operazioni primitive | Simulatore di traccia del computer Quantum | Microsoft Docs
description: Panoramica del simulatore di traccia del computer Quantum
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: b7ec8b0d7a713051e36cb778c087050f0257710f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184883"
---
# <a name="primitive-operations-counter"></a>Contatore operazioni primitive  

Il `Primitive Operations Counter` fa parte del [simulatore di traccia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Quantum computer. Viene conteggiato il numero di esecuzioni primitive utilizzate da ogni operazione richiamata in un programma Quantum. Tutte le operazioni da `Microsoft.Quantum.Primitive` sono espresse in termini di singole rotazioni qubit, T Gate, Single qubit Clifford Gates, CNOT Gates e misurazioni di più qubit Pauli osservabili. Le statistiche raccolte vengono aggregate sui bordi del grafico delle chiamate operazioni. È ora possibile contare il numero di `T` Gate necessari per implementare l'operazione di `CCNOT`. 

```qsharp
open Microsoft.Quantum.Primitive;
operation CCNOTDriver() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a>Uso del contatore operazioni primitive in C# un programma

Per verificare che `CCNOT` effettivamente richieda 7 `T` Gates e che `CCNOTDriver` esegua 8 `T` Gate, è possibile usare C# il codice seguente:

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.usePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = CCNOTDriver.Run(sim).Result;

double tCountAll = sim.GetMetric<CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
```

La prima parte del programma esegue `CCNOTDriver`. Nella seconda parte viene usato il metodo `QCTraceSimulator.GetMetric` per ottenere il numero di controlli T eseguiti da `CCNOTDriver`: 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
```

Quando `GetMetric` viene chiamato con due parametri di tipo, restituisce il valore della metrica associata a un bordo del grafico della chiamata specificato. Nell'esempio di operazione `Primitive.CCNOT` viene chiamato all'interno di `CCNOTDriver` e quindi il grafico delle chiamate contiene la `<Primitive.CCNOT,CCNOTDriver>`Edge. 

Per ottenere il numero di `CNOT` Gate usati, è possibile aggiungere la riga seguente:
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.CX);
```

Infine, per restituire tutte le statistiche raccolte dal contatore di controllo in formato CSV, è possibile usare quanto segue:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>Vedi anche ##

- Panoramica di Quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
