---
title: Simulatore di traccia di un computer quantistico
description: Informazioni su come usare il simulatore di traccia di un computer quantistico Microsoft per eseguire il debug del codice classico e per stimare i requisiti delle risorse di un programma quantistico.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
ms.openlocfilehash: 72c259933d2df8f79319e6c0c65ae181a9f9cff3
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "77906084"
---
# <a name="quantum-trace-simulator"></a>Simulatore di traccia quantistico

Il simulatore di traccia del computer quantistico Microsoft esegue un programma quantistico senza simulare effettivamente lo stato di un computer quantistico.  Per questo motivo, il simulatore di traccia può eseguire programmi quantistici che usano migliaia di qubit.  È utile per due scopi principali: 

* Eseguire il debug del codice classico che fa parte di un programma quantistico. 
* Stimare le risorse necessarie per l'esecuzione di un'istanza specifica di un programma quantistico in un computer quantistico.

Il simulatore di traccia si basa sulle informazioni aggiuntive fornite dall'utente quando è necessario eseguire le misurazioni. Per informazioni dettagliate, vedere la sezione [Fornire la probabilità dei risultati di misurazione](#providing-the-probability-of-measurement-outcomes). 

## <a name="providing-the-probability-of-measurement-outcomes"></a>Fornire la probabilità dei risultati di misurazione

Negli algoritmi quantistici vengono usate due tipologie di misurazioni. La prima svolge un ruolo ausiliario in cui l'utente generalmente conosce la probabilità dei risultati. In questo caso l'utente può scrivere <xref:microsoft.quantum.intrinsic.assertprob> dallo spazio dei nomi <xref:microsoft.quantum.intrinsic> per esprimere queste informazioni. L'esempio seguente illustra questi concetti.

```qsharp
operation TeleportQubit(source : Qubit, target : Qubit) : Unit {
    using (qubit = Qubit()) {
        H(qubit);
        CNOT(qubit, target);
        CNOT(source, qubit);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [q], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(q) == One) { X(target); X(q); }
    }
}
```

Quando il simulatore di traccia esegue `AssertProb` registrerà che la misurazione `PauliZ` su `source` e `q` dovrà restituire un risultato di `Zero` con probabilità di 0,5. Quando il simulatore esegue successivamente `M`, troverà i valori registrati delle probabilità del risultato e `M` restituirà `Zero` o `One` con probabilità di 0,5. Quando lo stesso codice viene eseguito in un simulatore che tiene traccia dello stato quantistico, tale simulatore verificherà che le probabilità fornite in `AssertProb` siano corrette.

## <a name="running-your-program-with-the-quantum-computer-trace-simulator"></a>Esecuzione del programma con il simulatore di traccia del computer quantistico 

Il simulatore di traccia del computer quantistico può essere visualizzato semplicemente come un altro computer di destinazione. Il programma del driver C# per usarlo è molto simile a quello per qualsiasi altro simulatore quantistico: 

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
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

Si noti che se è presente almeno una misura non annotata con `AssertProb`, il simulatore genererà un'eccezione `UnconstrainedMeasurementException` dallo spazio dei nomi `Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators`. Per informazioni dettagliate, vedere la documentazione dell'API su [UnconstrainedMeasurementException](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.UnconstrainedMeasurementException).

Oltre all'esecuzione di programmi quantistici, il simulatore di traccia include cinque componenti per il rilevamento dei bug nei programmi e per l'esecuzione di stime delle risorse per il programma quantistico: 

* [Controllo input distinti](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs)
* [Controllo utilizzo qubit invalidati](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)
* [Contatore operazioni primitive](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)
* [Contatore profondità circuito](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)
* [Contatore larghezza circuito](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)

Ognuno di questi componenti può essere abilitato impostando i flag appropriati in `QCTraceSimulatorConfiguration`. Per informazioni dettagliate su come usare ognuno di questi componenti, vedere i file di riferimento corrispondenti. Per informazioni specifiche, vedere la documentazione dell'API su [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration).

## <a name="see-also"></a>Vedere anche
Informazioni di riferimento sul [simulatore di traccia del computer quantistico](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) per C# 

