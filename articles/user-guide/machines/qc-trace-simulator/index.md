---
title: Simulatore di traccia quantistico - Quantum Development Kit
description: Informazioni su come usare il simulatore di traccia di un computer quantistico Microsoft per eseguire il debug di codice classico e per stimare i requisiti delle risorse di un programma Q#.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
ms.openlocfilehash: c01f01973ea08153cbfa35d87a588a4eae46f1b7
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871111"
---
# <a name="microsoft-quantum-development-kit-qdk-quantum-trace-simulator"></a>Simulatore di traccia quantistico del Quantum Development Kit (QDK) Microsoft

La classe <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> del QDK esegue un programma quantistico senza effettivamente simulare lo stato di un computer quantistico. Per questo motivo, il simulatore di traccia quantistico può eseguire programmi quantistici che usano migliaia di qubit.  È utile per due scopi principali: 

* Eseguire il debug del codice classico che fa parte di un programma quantistico. 
* Stimare le risorse necessarie per l'esecuzione di un'istanza specifica di un programma quantistico in un computer quantistico. Di fatto, lo [strumento di stima risorse](xref:microsoft.quantum.machines.resources-estimator), che prevede un set più limitato di metriche, è basato sul simulatore di traccia.

## <a name="invoking-the-quantum-trace-simulator"></a>Come richiamare il simulatore di traccia quantistico

È possibile usare il simulatore di traccia quantistico per eseguire qualsiasi operazione Q#.

Come per altri computer di destinazione, creare prima un'istanza della classe `QCTraceSimulator` e quindi passarla come primo parametro del metodo `Run` di un'operazione.

Si noti che, a differenza della classe `QuantumSimulator`, la classe `QCTraceSimulator` non implementa l'interfaccia <xref:System.IDisposable>, per cui non è necessario racchiuderla in un'istruzione `using`.

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            QCTraceSimulator sim = new QCTraceSimulator();
            var res = MyQuantumProgram.Run(sim).Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="providing-the-probability-of-measurement-outcomes"></a>Come fornire la probabilità dei risultati di misurazione

Poiché il simulatore di traccia quantistico non simula lo stato quantico effettivo, non è in grado di calcolare la probabilità dei risultati di misurazione all'interno di un'operazione. 

Pertanto, se un'operazione include misurazioni, è necessario fornire queste probabilità in modo esplicito usando l'operazione <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> dello spazio dei nomi <xref:microsoft.quantum.diagnostics>. L'esempio seguente illustra questi concetti.

```qsharp
operation TeleportQubit(source : Qubit, target : Qubit) : Unit {
    using (qubit = Qubit()) {
        H(qubit);
        CNOT(qubit, target);
        CNOT(source, qubit);
        H(source);

        AssertMeasurementProbability([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertMeasurementProbability([PauliZ], [q], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(q) == One) { X(target); X(q); }
    }
}
```

Quando il simulatore di traccia quantistico esegue `AssertMeasurementProbability`, registra che la misurazione `PauliZ` su `source` e `q` dovrà restituire un risultato `Zero` con probabilità **0,5**. Quando in seguito esegue l'operazione `M`, trova i valori registrati delle probabilità dei risultati `M` restituisce `Zero` o `One` con probabilità **0,5**. Quando lo stesso codice viene eseguito in un simulatore che tiene traccia dello stato quantico, tale simulatore verifica che le probabilità fornite in `AssertMeasurementProbability` siano corrette.

Si noti che se è presente almeno un'operazione di misurazione non annotata con `AssertMeasurementProbability`, il simulatore genera [`UnconstrainedMeasurementException`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.unconstrainedmeasurementexception).

## <a name="quantum-trace-simulator-tools"></a>Strumenti del simulatore di traccia quantistico

Il QDK include cinque strumenti che è possibile usare con il simulatore di traccia quantistico per rilevare bug nei programmi ed eseguire stime delle risorse dei programmi quantistici: 

|Strumento | Descrizione |
|-----| -----|
|[Controllo input distinti](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) |Verifica i potenziali conflitti con qubit condivisi |
|[Controllo utilizzo qubit invalidati](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)  |Controlla se il programma applica un'operazione a un qubit già rilasciato |
|[Contatore operazioni primitive](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)  | Conta il numero di esecuzioni di primitive usate da ogni operazione richiamata in un programma quantistico  |
|[Contatore profondità](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)  |Raccoglie i conteggi che rappresentano il limite inferiore della profondità di ogni operazione richiamata in un programma quantistico   |
|[Contatore larghezza](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)  |Conta il numero di qubit allocati e presi in prestito da ogni operazione in un programma quantistico |

Ognuno di questi strumenti viene abilitato impostando flag appropriati in `QCTraceSimulatorConfiguration` e passando quindi la configurazione alla dichiarazione `QCTraceSimulator`. Per informazioni sull'uso di ognuno di questi strumenti, vedere i collegamenti nell'elenco precedente. Per altre informazioni sulla configurazione di `QCTraceSimulator`, vedere [QCTraceSimulatorConfiguration](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration).

## <a name="qctracesimulator-methods"></a>Metodi QCTraceSimulator

`QCTraceSimulator` include diversi metodi predefiniti per recuperare i valori delle metriche registrate durante un'operazione quantistica. Esempi dei metodi [QCTraceSimulator.GetMetric](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) e [QCTraceSimulator.ToCSV](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.tocsv) sono disponibili negli articoli [Contatore operazioni primitive](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter), [Contatore profondità](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) e [Contatore larghezza](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter). Per altre informazioni su tutti i metodi disponibili, vedere [QCTraceSimulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) nelle informazioni di riferimento sull'API Q#.  

## <a name="see-also"></a>Vedere anche

- [Strumento di stima risorse](xref:microsoft.quantum.machines.resources-estimator)
- [Simulatore di Toffoli](xref:microsoft.quantum.machines.toffoli-simulator)
- [Simulatore di stato completo](xref:microsoft.quantum.machines.full-state-simulator) 