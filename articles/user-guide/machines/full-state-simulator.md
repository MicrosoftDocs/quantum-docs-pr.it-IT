---
title: Simulatore di stato completo
description: 'Informazioni su come eseguire i programmi Q # nel Microsoft Quantum Development Kit simulatore di stato completo.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 12/7/2017
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: f73abbc4366b003e4b22366ed83ca9c897737307
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274948"
---
# <a name="quantum-development-kit-full-state-simulator"></a>Simulatore di stato completo del kit di sviluppo Quantum

Quantum Development Kit fornisce un simulatore Quantum di stato completo simile a [liq $ UI | \rangle $](http://stationq.github.io/Liquid/) da Microsoft Research.
Questo simulatore può essere usato per eseguire ed eseguire il debug degli algoritmi Quantum scritti in Q # nel computer.

Questo simulatore quantum viene esposto tramite la `QuantumSimulator` classe. Per usare il simulatore, è sufficiente creare un'istanza di questa classe e passarla al `Run` metodo dell'operazione Quantum che si vuole eseguire insieme ai restanti parametri:

```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

## <a name="idisposable"></a>IDisposable

La `QuantumSimulator` classe implementa <xref:System.IDisposable> , quindi il `Dispose` metodo deve essere chiamato quando l'istanza del simulatore non viene più usata. Il modo migliore per eseguire questa operazione consiste nell'eseguire il wrapping del simulatore all'interno di un' `using` istruzione, come nell'esempio precedente.

## <a name="seed"></a>Seed

`QuantumSimulator`Usa un generatore di numeri casuali per simulare la casualità quantistica. A scopo di test, è talvolta utile avere risultati deterministici. Questa operazione può essere eseguita specificando un valore di inizializzazione per il generatore di numeri casuali nel `QuantumSimulator` costruttore di tramite il `randomNumberGeneratorSeed` parametro:

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="threads"></a>Threads

`QuantumSimulator`Usa [OpenMP](http://www.openmp.org/) per parallelizzare l'algebra lineare necessaria. Per impostazione predefinita, OpenMP usa tutti i thread hardware disponibili, il che significa che i programmi con un numero basso di qubit vengono spesso eseguiti lentamente perché il coordinamento necessario ostacolerà il lavoro effettivo. Questo problema può essere risolto impostando la variabile `OMP_NUM_THREADS` di ambiente su un numero ridotto. Come regola empirica molto approssimativa, 1 thread è adatto per un totale di circa 4 qubit, quindi è consigliabile aggiungere un altro thread per ogni qubit, anche se dipende pesantemente dall'algoritmo.

