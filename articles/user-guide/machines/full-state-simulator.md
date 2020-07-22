---
title: Full state Quantum Simulator-Quantum Development Kit
description: 'Informazioni su come eseguire i programmi Q # nel Microsoft Quantum Development Kit simulatore di stato completo.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: 563fdbd2a45461d112e4c46651eddd75c6fc3db2
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871179"
---
# <a name="quantum-development-kit-qdk-full-state-simulator"></a>Simulatore di stato completo di Quantum Development Kit (QDK)

QDK fornisce un simulatore di stato completo che simula una macchina quantistica nel computer locale. È possibile usare il simulatore di stato completo per eseguire ed eseguire il debug degli algoritmi Quantum scritti in Q #, usando fino a 30 qubits. Il simulatore di stato completo è simile al simulatore Quantum usato nella piattaforma [liq $ UI | \rangle $](http://stationq.github.io/Liquid/) di Microsoft Research.

## <a name="invoking-and-running-the-full-state-simulator"></a>Richiamo ed esecuzione del simulatore di stato completo

Il simulatore di stato completo viene esposto tramite la `QuantumSimulator` classe. Per ulteriori informazioni, vedere [modalità di esecuzione di un programma Q #](xref:microsoft.quantum.guide.host-programs).

### <a name="invoking-the-simulator-from-c"></a>Richiamo del simulatore da C #

Creare un'istanza della `QuantumSimulator` classe e passarla al `Run` metodo di un'operazione Quantum, insieme ad altri parametri.
```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

Poiché la `QuantumSimulator` classe implementa l' <xref:System.IDisposable> interfaccia, è necessario chiamare il `Dispose` Metodo una volta che l'istanza del simulatore non è più necessaria. Il modo migliore per eseguire questa operazione consiste nell'eseguire il wrapping della dichiarazione del simulatore e delle operazioni all'interno di un'istruzione [using](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) , che chiama automaticamente il `Dispose` metodo.

### <a name="invoking-the-simulator-from-python"></a>Richiamo del simulatore da Python

Usare il metodo [simulate ()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) dalla libreria Python q # con l'operazione q # importata:

```python
qubit_result = myOperation.simulate()
```

### <a name="invoking-the-simulator-from-the-command-line"></a>Richiamo del simulatore dalla riga di comando

Quando si esegue un programma Q # dalla riga di comando, il simulatore di stato completo è il computer di destinazione predefinito. Facoltativamente, è possibile usare il parametro **--Simulator** (o **-s** Shortcut) per specificare il computer di destinazione desiderato. Entrambi i comandi seguenti eseguono un programma usando il simulatore di stato completo. 

```dotnetcli
dotnet run
dotnet run -s QuantumSimulator
```

### <a name="invoking-the-simulator-from-juptyer-notebooks"></a>Richiamo del simulatore da notebook Juptyer

Usare il comando IQ # Magic [% simulate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) per eseguire l'operazione Q #.

```
%simulate myOperation
```
## <a name="seeding-the-simulator"></a>Seeding del simulatore

Per impostazione predefinita, il simulatore di stato completo usa un generatore di numeri casuali per simulare la casualità quantistica. A scopo di test, è talvolta utile avere risultati deterministici. Per eseguire questa operazione in un programma C#, è possibile fornire un valore di inizializzazione per il generatore di numeri casuali nel `QuantumSimulator` costruttore tramite il `randomNumberGeneratorSeed` parametro.

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="configuring-threads"></a>Configurazione di thread

Il simulatore di stato completo usa [OpenMP](http://www.openmp.org/) per parallelizzare l'algebra lineare necessaria. Per impostazione predefinita, OpenMP utilizza tutti i thread di hardware disponibili, il che significa che i programmi con un numero ridotto di qubits spesso vengono eseguiti lentamente, perché il coordinamento che è necessario sminuisce il lavoro effettivo. È possibile risolvere il problema impostando la variabile `OMP_NUM_THREADS` di ambiente su un numero ridotto. Come regola generale, configurare un thread per un massimo di quattro qubits, quindi un thread aggiuntivo per ogni qubit. Potrebbe essere necessario modificare la variabile a seconda dell'algoritmo.

## <a name="see-also"></a>Vedere anche

- [Strumento di stima risorse Quantum](xref:microsoft.quantum.machines.resources-estimator)
- [Quantum Toffoli Simulator](xref:microsoft.quantum.machines.toffoli-simulator)
- [Simulatore di traccia Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)