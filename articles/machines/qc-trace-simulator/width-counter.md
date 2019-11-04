---
title: Contatore larghezza | Simulatore di traccia del computer Quantum | Microsoft Docs
description: Panoramica del simulatore di traccia del computer quantistico
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: ae0c0ec2e677be03dc8dc1497dc62ad9034295a4
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442403"
---
# <a name="width-counter"></a>Contatore larghezza

Il `Width Counter` conta il numero di qubits allocati e presi in prestito da ogni operazione.
Tutte le operazioni dello spazio dei nomi `Microsoft.Quantum.Primitive` sono espresse in termini di singole rotazioni qubit, T Gate, Single qubit Clifford Gates, CNOT Gates e misurazioni di qubit Pauli osservabili. Alcune delle operazioni primitive possono allocare qubits aggiuntive. Ad esempio, moltiplicare controlli `X` controllati o controlli `T` controllati. Consente di calcolare il numero di qubits aggiuntivi allocati dall'implementazione di un controllo `X` di moltiplicazione controllato:

```qsharp
open Microsoft.Quantum.Primitive;
open Microsoft.Quantum.Arrays;
operation MultiControlledXDriver( numberOfQubits : Int ) : Unit {

    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a>Uso del contatore della larghezza C# in un programma

Il `X` di moltiplicazione controllato che agisce su un totale di 5 qubits alloca 2 qubits ausiliari e la larghezza di input sarà 5. Per verificarne il caso, è possibile usare il programma seguente C# :

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.useWidthCounter = true;
var sim = new QCTraceSimulator(config);
int totalNumberOfQubits = 5;
var res = MultiControlledXDriver.Run(sim, totalNumberOfQubits).Result;

double allocatedQubits = 
    sim.GetMetric<Primitive.X, MultiControlledXDriver>(
        WidthCounter.Metrics.ExtraWidth,
        functor: OperationFunctor.Controlled); 

double inputWidth =
    sim.GetMetric<Primitive.X, MultiControlledXDriver>(
        WidthCounter.Metrics.InputWidth,
        functor: OperationFunctor.Controlled);
```

La prima parte del programma esegue `MultiControlledXDriver`. Nella seconda parte viene usato il metodo `QCTraceSimulator.GetMetric` per ottenere il numero di qubits allocati, nonché il numero di qubits che ha controllato `X` ricevuto come input. 

Infine, per restituire tutte le statistiche raccolte dal contatore di larghezza in formato CSV, è possibile usare quanto segue:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a>Vedi anche ##

- Panoramica di Quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
