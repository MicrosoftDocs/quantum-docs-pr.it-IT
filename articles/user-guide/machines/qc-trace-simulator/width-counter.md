---
title: Contatore larghezza
description: Informazioni sul contatore Microsoft QDK Width, che conta il numero di qubits allocati e presi in prestito da ogni operazione in un programma Quantum.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: a76292222950310acc90dded02980e4a5b792e76
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274898"
---
# <a name="width-counter"></a>Contatore larghezza

Viene `Width Counter` conteggiato il numero di qubits allocati e presi in prestito da ogni operazione.
Tutte le operazioni dello `Microsoft.Quantum.Intrinsic` spazio dei nomi sono espresse in termini di singole rotazioni qubit, T Gate, Single qubit Clifford Gates, CNOT Gates e misurazioni di più qubit Pauli osservabili. Alcune delle operazioni primitive possono allocare qubits aggiuntive. Ad esempio, moltiplicare le `X` porte controllate o controllate `T` . Consente di calcolare il numero di qubits aggiuntivi allocati dall'implementazione di un controllo Multiply controllato `X` :

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a>Uso del contatore della larghezza in un programma C#

La funzione di moltiplicazione controllata `X` che agisce su un totale di 5 qubits alloca 2 qubits ausiliari e la larghezza di input sarà 5. Per verificarne il caso, è possibile usare il programma C# seguente:

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.useWidthCounter = true;
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

Viene eseguita la prima parte del programma `ApplyMultiControlledX` . Nella seconda parte viene usato il metodo `QCTraceSimulator.GetMetric` per ottenere il numero di qubits allocati, nonché il numero di qubits che ha controllato `X` come input. 

Infine, per restituire tutte le statistiche raccolte dal contatore di larghezza in formato CSV, è possibile usare quanto segue:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a>Vedi anche ##

- Panoramica di Quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
