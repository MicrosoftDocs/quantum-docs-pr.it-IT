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
# <a name="quantum-development-kit-full-state-simulator"></a><span data-ttu-id="ad996-103">Simulatore di stato completo del kit di sviluppo Quantum</span><span class="sxs-lookup"><span data-stu-id="ad996-103">Quantum Development Kit Full State Simulator</span></span>

<span data-ttu-id="ad996-104">Quantum Development Kit fornisce un simulatore Quantum di stato completo simile a [liq $ UI | \rangle $](http://stationq.github.io/Liquid/) da Microsoft Research.</span><span class="sxs-lookup"><span data-stu-id="ad996-104">The Quantum Development Kit provides a full state quantum simulator similar to [LIQ$Ui|\rangle$](http://stationq.github.io/Liquid/) from Microsoft Research.</span></span>
<span data-ttu-id="ad996-105">Questo simulatore può essere usato per eseguire ed eseguire il debug degli algoritmi Quantum scritti in Q # nel computer.</span><span class="sxs-lookup"><span data-stu-id="ad996-105">This simulator can be used to execute and debug quantum algorithms written in Q# on your computer.</span></span>

<span data-ttu-id="ad996-106">Questo simulatore quantum viene esposto tramite la `QuantumSimulator` classe.</span><span class="sxs-lookup"><span data-stu-id="ad996-106">This quantum simulator is exposed via the `QuantumSimulator` class.</span></span> <span data-ttu-id="ad996-107">Per usare il simulatore, è sufficiente creare un'istanza di questa classe e passarla al `Run` metodo dell'operazione Quantum che si vuole eseguire insieme ai restanti parametri:</span><span class="sxs-lookup"><span data-stu-id="ad996-107">To use the simulator, simply create an instance of this class and pass it to the `Run` method of the quantum operation you want to execute along with the rest of the parameters:</span></span>

```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

## <a name="idisposable"></a><span data-ttu-id="ad996-108">IDisposable</span><span class="sxs-lookup"><span data-stu-id="ad996-108">IDisposable</span></span>

<span data-ttu-id="ad996-109">La `QuantumSimulator` classe implementa <xref:System.IDisposable> , quindi il `Dispose` metodo deve essere chiamato quando l'istanza del simulatore non viene più usata.</span><span class="sxs-lookup"><span data-stu-id="ad996-109">The `QuantumSimulator` class implements <xref:System.IDisposable>, thus the `Dispose` method should be called once the instance of the simulator is not used anymore.</span></span> <span data-ttu-id="ad996-110">Il modo migliore per eseguire questa operazione consiste nell'eseguire il wrapping del simulatore all'interno di un' `using` istruzione, come nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="ad996-110">The best way to do this is to wrap the simulator within a `using` statement, as in the example above.</span></span>

## <a name="seed"></a><span data-ttu-id="ad996-111">Seed</span><span class="sxs-lookup"><span data-stu-id="ad996-111">Seed</span></span>

<span data-ttu-id="ad996-112">`QuantumSimulator`Usa un generatore di numeri casuali per simulare la casualità quantistica.</span><span class="sxs-lookup"><span data-stu-id="ad996-112">The `QuantumSimulator` uses a random number generator to simulate quantum randomness.</span></span> <span data-ttu-id="ad996-113">A scopo di test, è talvolta utile avere risultati deterministici.</span><span class="sxs-lookup"><span data-stu-id="ad996-113">For testing purposes, it is sometimes useful to have deterministic results.</span></span> <span data-ttu-id="ad996-114">Questa operazione può essere eseguita specificando un valore di inizializzazione per il generatore di numeri casuali nel `QuantumSimulator` costruttore di tramite il `randomNumberGeneratorSeed` parametro:</span><span class="sxs-lookup"><span data-stu-id="ad996-114">This can be accomplished by providing a seed for the random number generator in the `QuantumSimulator`'s constructor via the `randomNumberGeneratorSeed` parameter:</span></span>

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="threads"></a><span data-ttu-id="ad996-115">Threads</span><span class="sxs-lookup"><span data-stu-id="ad996-115">Threads</span></span>

<span data-ttu-id="ad996-116">`QuantumSimulator`Usa [OpenMP](http://www.openmp.org/) per parallelizzare l'algebra lineare necessaria.</span><span class="sxs-lookup"><span data-stu-id="ad996-116">The `QuantumSimulator` uses [OpenMP](http://www.openmp.org/) to parallelize the linear algebra required.</span></span> <span data-ttu-id="ad996-117">Per impostazione predefinita, OpenMP usa tutti i thread hardware disponibili, il che significa che i programmi con un numero basso di qubit vengono spesso eseguiti lentamente perché il coordinamento necessario ostacolerà il lavoro effettivo.</span><span class="sxs-lookup"><span data-stu-id="ad996-117">By default OpenMP uses all available hardware threads, which means that programs with small numbers of qubits will often run slowly because the coordination required will dwarf the actual work.</span></span> <span data-ttu-id="ad996-118">Questo problema può essere risolto impostando la variabile `OMP_NUM_THREADS` di ambiente su un numero ridotto.</span><span class="sxs-lookup"><span data-stu-id="ad996-118">This can be fixed by setting the environment variable `OMP_NUM_THREADS` to a small number.</span></span> <span data-ttu-id="ad996-119">Come regola empirica molto approssimativa, 1 thread è adatto per un totale di circa 4 qubit, quindi è consigliabile aggiungere un altro thread per ogni qubit, anche se dipende pesantemente dall'algoritmo.</span><span class="sxs-lookup"><span data-stu-id="ad996-119">As a very rough rule of thumb, 1 thread is good for up to about 4 qubits, and then an additional thread per qubit is good, although this is highly dependent on your algorithm.</span></span>

