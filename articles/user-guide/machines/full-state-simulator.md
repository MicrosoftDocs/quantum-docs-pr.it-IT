---
title: Full state Quantum Simulator-Quantum Development Kit
description: Informazioni su come eseguire i Q# programmi nel Microsoft Quantum Development Kit simulatore di stato completo.
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
no-loc:
- Q#
- $$v
ms.openlocfilehash: a27cece9858d62814b9d80c47e61c5d7d3b8c885
ms.sourcegitcommit: 11bd357baeb6ab53a402882979e75964d0869b57
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2020
ms.locfileid: "88992224"
---
# <a name="quantum-development-kit-qdk-full-state-simulator"></a><span data-ttu-id="1b3e4-103">Simulatore di stato completo di Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="1b3e4-103">Quantum Development Kit (QDK) full state simulator</span></span>

<span data-ttu-id="1b3e4-104">QDK fornisce un simulatore di stato completo che simula una macchina quantistica nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="1b3e4-104">The QDK provides a full state simulator that simulates a quantum machine on your local computer.</span></span> <span data-ttu-id="1b3e4-105">È possibile usare il simulatore di stato completo per eseguire ed eseguire il debug degli algoritmi Quantum scritti in Q# , usando fino a 30 qubits.</span><span class="sxs-lookup"><span data-stu-id="1b3e4-105">You can use the full state simulator to run and debug quantum algorithms written in Q#, utilizing up to 30 qubits.</span></span> <span data-ttu-id="1b3e4-106">Il simulatore di stato completo è simile al simulatore Quantum usato nella piattaforma  [liq $ UI | \rangle $](http://stationq.github.io/Liquid/) di Microsoft Research.</span><span class="sxs-lookup"><span data-stu-id="1b3e4-106">The full state simulator is similar to the quantum simulator used in the  [LIQ$Ui|\rangle$](http://stationq.github.io/Liquid/) platform from Microsoft Research.</span></span>

## <a name="invoking-and-running-the-full-state-simulator"></a><span data-ttu-id="1b3e4-107">Richiamo ed esecuzione del simulatore di stato completo</span><span class="sxs-lookup"><span data-stu-id="1b3e4-107">Invoking and running the full state simulator</span></span>

<span data-ttu-id="1b3e4-108">Il simulatore di stato completo viene esposto tramite la `QuantumSimulator` classe.</span><span class="sxs-lookup"><span data-stu-id="1b3e4-108">You expose the full state simulator via the `QuantumSimulator` class.</span></span> <span data-ttu-id="1b3e4-109">Per ulteriori informazioni, vedere [modalità di esecuzione di un Q# programma](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="1b3e4-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-simulator-from-c"></a><span data-ttu-id="1b3e4-110">Richiamo del simulatore da C #</span><span class="sxs-lookup"><span data-stu-id="1b3e4-110">Invoking the simulator from C#</span></span>

<span data-ttu-id="1b3e4-111">Creare un'istanza della `QuantumSimulator` classe e passarla al `Run` metodo di un'operazione Quantum, insieme ad altri parametri.</span><span class="sxs-lookup"><span data-stu-id="1b3e4-111">Create an instance of the `QuantumSimulator` class and then pass it to the `Run` method of a quantum operation, along with any additional parameters.</span></span>
```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

<span data-ttu-id="1b3e4-112">Poiché la `QuantumSimulator` classe implementa l' <xref:System.IDisposable> interfaccia, è necessario chiamare il `Dispose` Metodo una volta che l'istanza del simulatore non è più necessaria.</span><span class="sxs-lookup"><span data-stu-id="1b3e4-112">Because the `QuantumSimulator` class implements the <xref:System.IDisposable> interface, you must call the `Dispose` method once you do not need the instance of the simulator anymore.</span></span> <span data-ttu-id="1b3e4-113">Il modo migliore per eseguire questa operazione consiste nell'eseguire il wrapping della dichiarazione del simulatore e delle operazioni all'interno di un'istruzione [using](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) , che chiama automaticamente il `Dispose` metodo.</span><span class="sxs-lookup"><span data-stu-id="1b3e4-113">The best way to do this is to wrap the simulator declaration and operations within a [using](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) statement, which automatically calls the `Dispose` method.</span></span>

### <a name="invoking-the-simulator-from-python"></a><span data-ttu-id="1b3e4-114">Richiamo del simulatore da Python</span><span class="sxs-lookup"><span data-stu-id="1b3e4-114">Invoking the simulator from Python</span></span>

<span data-ttu-id="1b3e4-115">Usare il metodo [simulate ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) dalla Q# libreria Python con l'operazione importata Q# :</span><span class="sxs-lookup"><span data-stu-id="1b3e4-115">Use the [simulate()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) method from the Q# Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.simulate()
```

### <a name="invoking-the-simulator-from-the-command-line"></a><span data-ttu-id="1b3e4-116">Richiamo del simulatore dalla riga di comando</span><span class="sxs-lookup"><span data-stu-id="1b3e4-116">Invoking the simulator from the command line</span></span>

<span data-ttu-id="1b3e4-117">Quando si esegue un Q# programma dalla riga di comando, il simulatore di stato completo è il computer di destinazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="1b3e4-117">When running a Q# program from the command line, the full state simulator is the default target machine.</span></span> <span data-ttu-id="1b3e4-118">Facoltativamente, è possibile usare il parametro **--Simulator** (o **-s** Shortcut) per specificare il computer di destinazione desiderato.</span><span class="sxs-lookup"><span data-stu-id="1b3e4-118">Optionally, you can use the **--simulator** (or **-s** shortcut) parameter to specify the desired target machine.</span></span> <span data-ttu-id="1b3e4-119">Entrambi i comandi seguenti eseguono un programma usando il simulatore di stato completo.</span><span class="sxs-lookup"><span data-stu-id="1b3e4-119">Both of the following commands run a program using the full state simulator.</span></span> 

```dotnetcli
dotnet run
dotnet run -s QuantumSimulator
```

### <a name="invoking-the-simulator-from-juptyer-notebooks"></a><span data-ttu-id="1b3e4-120">Richiamo del simulatore da notebook Juptyer</span><span class="sxs-lookup"><span data-stu-id="1b3e4-120">Invoking the simulator from Juptyer Notebooks</span></span>

<span data-ttu-id="1b3e4-121">Usare il Q# comando i Magic [% simulate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) per eseguire l' Q# operazione.</span><span class="sxs-lookup"><span data-stu-id="1b3e4-121">Use the IQ# magic command [%simulate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%simulate myOperation
```
## <a name="seeding-the-simulator"></a><span data-ttu-id="1b3e4-122">Seeding del simulatore</span><span class="sxs-lookup"><span data-stu-id="1b3e4-122">Seeding the simulator</span></span>

<span data-ttu-id="1b3e4-123">Per impostazione predefinita, il simulatore di stato completo usa un generatore di numeri casuali per simulare la casualità quantistica.</span><span class="sxs-lookup"><span data-stu-id="1b3e4-123">By default, the full state simulator uses a random number generator to simulate quantum randomness.</span></span> <span data-ttu-id="1b3e4-124">A scopo di test, è talvolta utile avere risultati deterministici.</span><span class="sxs-lookup"><span data-stu-id="1b3e4-124">For testing purposes, it is sometimes useful to have deterministic results.</span></span> <span data-ttu-id="1b3e4-125">Per eseguire questa operazione in un programma C#, è possibile fornire un valore di inizializzazione per il generatore di numeri casuali nel `QuantumSimulator` costruttore tramite il `randomNumberGeneratorSeed` parametro.</span><span class="sxs-lookup"><span data-stu-id="1b3e4-125">In a C# program, you can accomplish this by providing a seed for the random number generator in the `QuantumSimulator` constructor via the `randomNumberGeneratorSeed` parameter.</span></span>

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="configuring-threads"></a><span data-ttu-id="1b3e4-126">Configurazione di thread</span><span class="sxs-lookup"><span data-stu-id="1b3e4-126">Configuring threads</span></span>

<span data-ttu-id="1b3e4-127">Il simulatore di stato completo usa [OpenMP](http://www.openmp.org/) per parallelizzare l'algebra lineare necessaria.</span><span class="sxs-lookup"><span data-stu-id="1b3e4-127">The full state simulator uses [OpenMP](http://www.openmp.org/) to parallelize the linear algebra required.</span></span> <span data-ttu-id="1b3e4-128">Per impostazione predefinita, OpenMP utilizza tutti i thread di hardware disponibili, il che significa che i programmi con un numero ridotto di qubits spesso vengono eseguiti lentamente, perché il coordinamento che è necessario sminuisce il lavoro effettivo.</span><span class="sxs-lookup"><span data-stu-id="1b3e4-128">By default, OpenMP uses all available hardware threads, which means that programs with small numbers of qubits often runs slowly because the coordination that is required dwarfs the actual work.</span></span> <span data-ttu-id="1b3e4-129">È possibile risolvere il problema impostando la variabile `OMP_NUM_THREADS` di ambiente su un numero ridotto.</span><span class="sxs-lookup"><span data-stu-id="1b3e4-129">You can fix this by setting the environment variable `OMP_NUM_THREADS` to a small number.</span></span> <span data-ttu-id="1b3e4-130">Come regola generale, configurare un thread per un massimo di quattro qubits, quindi un thread aggiuntivo per ogni qubit.</span><span class="sxs-lookup"><span data-stu-id="1b3e4-130">As a rule of thumb, configure one thread for up to four qubits, and then one additional thread per qubit.</span></span> <span data-ttu-id="1b3e4-131">Potrebbe essere necessario modificare la variabile a seconda dell'algoritmo.</span><span class="sxs-lookup"><span data-stu-id="1b3e4-131">You might need to adjust the variable depending on your algorithm.</span></span>

## <a name="see-also"></a><span data-ttu-id="1b3e4-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b3e4-132">See also</span></span>

- [<span data-ttu-id="1b3e4-133">Strumento di stima risorse</span><span class="sxs-lookup"><span data-stu-id="1b3e4-133">Quantum resources estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="1b3e4-134">Simulatore di Toffoli</span><span class="sxs-lookup"><span data-stu-id="1b3e4-134">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="1b3e4-135">Simulatore di traccia Quantum</span><span class="sxs-lookup"><span data-stu-id="1b3e4-135">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)