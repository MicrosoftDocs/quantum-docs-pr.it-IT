---
title: Simulatore di stato completo del kit di sviluppo Quantum | Microsoft Docs
description: Panoramica del simulatore di stato completo di Microsoft Quantum Development Kit
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 12/7/2017
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: ab0e65765d27e301a59948d7c02105a523022e68
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184679"
---
# <a name="quantum-development-kit-full-state-simulator"></a>Simulatore di stato completo del kit di sviluppo Quantum

Quantum Development Kit fornisce un simulatore Quantum di stato completo simile a [liq $ UI | \rangle $](http://stationq.github.io/Liquid/) da Microsoft Research.
Questo simulatore può essere usato per eseguire ed eseguire il debug degli algoritmi Quantum scritti in Q # nel computer.

Questo simulatore quantum viene esposto tramite la classe `QuantumSimulator`. Per usare il simulatore, è sufficiente creare un'istanza di questa classe e passarla al metodo `Run` dell'operazione Quantum che si vuole eseguire insieme ai restanti parametri:

```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

## <a name="idisposable"></a>IDisposable

La classe `QuantumSimulator` implementa <xref:System.IDisposable>, pertanto è necessario chiamare il metodo `Dispose` una volta che l'istanza del simulatore non viene più utilizzata. Il modo migliore per eseguire questa operazione consiste nell'eseguire il wrapping del simulatore in un'istruzione `using`, come nell'esempio precedente.

## <a name="seed"></a>Inizializzazione

Il `QuantumSimulator` usa un generatore di numeri casuali per simulare la casualità quantistica. A scopo di test, è talvolta utile avere risultati deterministici. Questa operazione può essere eseguita fornendo un valore di inizializzazione per il generatore di numeri casuali nel costruttore del `QuantumSimulator`tramite il parametro `randomNumberGeneratorSeed`:

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="threads"></a>Threads

Il `QuantumSimulator` USA [OpenMP](http://www.openmp.org/) per parallelizzare l'algebra lineare necessaria. Per impostazione predefinita, OpenMP utilizza tutti i thread di hardware disponibili, il che significa che i programmi con un numero ridotto di qubits vengono spesso eseguiti lentamente perché il coordinamento necessario può sminuire il lavoro effettivo. Questo problema può essere risolto impostando la variabile di ambiente `OMP_NUM_THREADS` su un numero ridotto. Come regola empirica molto approssimativa, 1 thread è adatto per un massimo di 4 qubits, quindi un thread aggiuntivo per ogni qubit è valido, sebbene questo sia molto dipendente dall'algoritmo.

