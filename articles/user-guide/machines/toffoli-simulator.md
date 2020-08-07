---
title: Quantum Toffoli Simulator-Quantum Development Kit
description: Informazioni sul simulatore Microsoft QDK Toffoli, un simulatore Quantum con scopo speciale che può essere usato con milioni di qubits.
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 6/25/2020
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8a981645703423856e667be7c3dccf5270a5885f
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868101"
---
# <a name="quantum-development-kit-qdk-toffoli-simulator"></a><span data-ttu-id="c1e31-103">Simulatore di Toffoli per Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="c1e31-103">Quantum Development Kit (QDK) Toffoli simulator</span></span>

<span data-ttu-id="c1e31-104">Il simulatore di Toffoli QDK è un simulatore per scopi specifici con un ambito limitato e supporta solo `X` `CNOT` le operazioni Quantum, e multicontrollate `X` .</span><span class="sxs-lookup"><span data-stu-id="c1e31-104">The QDK Toffoli simulator is a special-purpose simulator with a limited scope and only supports `X`, `CNOT`, and multi-controlled `X` quantum operations.</span></span> <span data-ttu-id="c1e31-105">Sono disponibili tutte le logiche e i calcoli classici.</span><span class="sxs-lookup"><span data-stu-id="c1e31-105">All classical logic and computations are available.</span></span>

<span data-ttu-id="c1e31-106">Sebbene il simulatore Toffoli sia più limitato alle funzionalità rispetto al [simulatore di stato completo](xref:microsoft.quantum.machines.full-state-simulator), ha il vantaggio di poter simulare molto più qubits.</span><span class="sxs-lookup"><span data-stu-id="c1e31-106">While the Toffoli simulator is more restricted in functionality than the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), it has the advantage of being able to simulate far more qubits.</span></span> <span data-ttu-id="c1e31-107">Il simulatore Toffoli può essere usato con milioni di qubits, mentre il simulatore di stato completo è limitato a circa 30 qubits.</span><span class="sxs-lookup"><span data-stu-id="c1e31-107">The Toffoli simulator can be used with millions of qubits, while the full state simulator is limited to about 30 qubits.</span></span> <span data-ttu-id="c1e31-108">Questa operazione è utile, ad esempio, con i Oracle che valutano le funzioni booleane, che possono essere implementati usando un set limitato di algoritmi supportati e testati su un numero elevato di qubits.</span><span class="sxs-lookup"><span data-stu-id="c1e31-108">This is useful, for example, with oracles that evaluate Boolean functions - they can be implemented using the limited set of supported algorithms and tested on a large number of qubits.</span></span>

## <a name="invoking-the-toffoli-simulator"></a><span data-ttu-id="c1e31-109">Richiamo del simulatore Toffoli</span><span class="sxs-lookup"><span data-stu-id="c1e31-109">Invoking the Toffoli simulator</span></span>

<span data-ttu-id="c1e31-110">Il simulatore Toffoli viene esposto tramite la `ToffoliSimulator` classe.</span><span class="sxs-lookup"><span data-stu-id="c1e31-110">You expose the Toffoli simulator via the `ToffoliSimulator` class.</span></span> <span data-ttu-id="c1e31-111">Per ulteriori informazioni, vedere [modalità di esecuzione di un Q# programma](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="c1e31-111">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-toffoli-simulator-from-c"></a><span data-ttu-id="c1e31-112">Richiamo del simulatore Toffoli da C #</span><span class="sxs-lookup"><span data-stu-id="c1e31-112">Invoking the Toffoli simulator from C#</span></span>

<span data-ttu-id="c1e31-113">Come per altri computer di destinazione, creare prima un'istanza della classe `ToffoliSimulator` e quindi passarla come primo parametro del metodo `Run` di un'operazione.</span><span class="sxs-lookup"><span data-stu-id="c1e31-113">As with other target machines, you first create an instance of the `ToffoliSimulator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="c1e31-114">Si noti che, a differenza della classe `QuantumSimulator`, la classe `ToffoliSimulator` non implementa l'interfaccia <xref:System.IDisposable>, per cui non è necessario racchiuderla in un'istruzione `using`.</span><span class="sxs-lookup"><span data-stu-id="c1e31-114">Note that, unlike the `QuantumSimulator` class, the `ToffoliSimulator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

### <a name="invoking-the-toffoli-simulator-from-python"></a><span data-ttu-id="c1e31-115">Richiamo del simulatore Toffoli da Python</span><span class="sxs-lookup"><span data-stu-id="c1e31-115">Invoking the Toffoli simulator from Python</span></span>

<span data-ttu-id="c1e31-116">Usare il metodo [toffoli_simulate ()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) dalla libreria Python con l'operazione importata Q# :</span><span class="sxs-lookup"><span data-stu-id="c1e31-116">Use the [toffoli_simulate()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) method from the Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.toffoli_simulate()
```

### <a name="invoking-the-toffoli-simulator-from-the-command-line"></a><span data-ttu-id="c1e31-117">Richiamo del simulatore Toffoli dalla riga di comando</span><span class="sxs-lookup"><span data-stu-id="c1e31-117">Invoking the Toffoli simulator from the command line</span></span>

<span data-ttu-id="c1e31-118">Quando si esegue un Q# programma dalla riga di comando, usare il parametro **--Simulator** (o **-s** Shortcut) per specificare il computer di destinazione del simulatore Toffoli.</span><span class="sxs-lookup"><span data-stu-id="c1e31-118">When running a Q# program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the Toffoli simulator target machine.</span></span> <span data-ttu-id="c1e31-119">Il comando che segue esegue un programma usando lo strumento di stima delle risorse:</span><span class="sxs-lookup"><span data-stu-id="c1e31-119">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ToffoliSimulator
```

### <a name="invoking-the-toffoli-simulator-from-juptyer-notebooks"></a><span data-ttu-id="c1e31-120">Richiamo del simulatore Toffoli da Juptyer Notebooks</span><span class="sxs-lookup"><span data-stu-id="c1e31-120">Invoking the Toffoli simulator from Juptyer Notebooks</span></span>

<span data-ttu-id="c1e31-121">Usare il Q# comando i Magic [% Toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) per eseguire l' Q# operazione.</span><span class="sxs-lookup"><span data-stu-id="c1e31-121">Use the IQ# magic command [%toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) to run the Q# operation.</span></span>

```
%toffoli myOperation
```

## <a name="supported-operations"></a><span data-ttu-id="c1e31-122">Operazioni supportate</span><span class="sxs-lookup"><span data-stu-id="c1e31-122">Supported operations</span></span>

<span data-ttu-id="c1e31-123">Il simulatore Toffoli supporta:</span><span class="sxs-lookup"><span data-stu-id="c1e31-123">The Toffoli simulator supports:</span></span>

* <span data-ttu-id="c1e31-124">Rotazioni e exponentiated Paulis, ad esempio `R` e `Exp` , quando l'operazione risultante è uguale a `X` o alla matrice di identità.</span><span class="sxs-lookup"><span data-stu-id="c1e31-124">Rotations and exponentiated Paulis, such as `R` and `Exp`, when the resulting operation equals `X` or the identity matrix.</span></span>
* <span data-ttu-id="c1e31-125">Operazioni di misurazione e [asserzione](xref:microsoft.quantum.diagnostics.assertmeasurement) , ma solo in `Z` base a Pauli.</span><span class="sxs-lookup"><span data-stu-id="c1e31-125">Measurement and [assert](xref:microsoft.quantum.diagnostics.assertmeasurement) operations, but only in the Pauli `Z` basis.</span></span> <span data-ttu-id="c1e31-126">Si noti che la probabilità di un'operazione di misurazione è sempre **0** o **1**. non esiste alcuna casualità nel simulatore Toffoli.</span><span class="sxs-lookup"><span data-stu-id="c1e31-126">Note that a measurement operation's probability is always either **0** or **1**; there is no randomness in the Toffoli simulator.</span></span>
* <span data-ttu-id="c1e31-127">`DumpMachine``DumpRegister`funzioni e.</span><span class="sxs-lookup"><span data-stu-id="c1e31-127">`DumpMachine` and `DumpRegister` functions.</span></span>
<span data-ttu-id="c1e31-128">Entrambe le funzioni restituiscono lo `Z` stato di base corrente di ogni qubit, un qubit per riga.</span><span class="sxs-lookup"><span data-stu-id="c1e31-128">Both functions output the current `Z`-basis state of each qubit, one qubit per line.</span></span>

## <a name="specifying-the-number-of-qubits"></a><span data-ttu-id="c1e31-129">Specifica del numero di qubits</span><span class="sxs-lookup"><span data-stu-id="c1e31-129">Specifying the number of qubits</span></span>

<span data-ttu-id="c1e31-130">Per impostazione predefinita, un' `ToffoliSimulator` istanza di alloca spazio per 65.536 qubits.</span><span class="sxs-lookup"><span data-stu-id="c1e31-130">By default, a `ToffoliSimulator` instance allocates space for 65,536 qubits.</span></span>
<span data-ttu-id="c1e31-131">Se l'algoritmo richiede più qubits di questo, è possibile specificare il numero di qubit fornendo un valore per il `qubitCount` parametro al costruttore.</span><span class="sxs-lookup"><span data-stu-id="c1e31-131">If your algorithm requires more qubits than this, you can specify the qubit count by providing a value for the `qubitCount` parameter to the constructor.</span></span>
<span data-ttu-id="c1e31-132">Ogni qubit aggiuntivo richiede un solo byte di memoria, quindi non vi è alcun costo significativo per sovrastimare il numero di qubits necessarie.</span><span class="sxs-lookup"><span data-stu-id="c1e31-132">Each additional qubit requires only one byte of memory, so there is no significant cost to overestimating the number of qubits you'll need.</span></span>

<span data-ttu-id="c1e31-133">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c1e31-133">For example:</span></span>

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```

## <a name="see-also"></a><span data-ttu-id="c1e31-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1e31-134">See also</span></span>

- [<span data-ttu-id="c1e31-135">Strumento di stima risorse Quantum</span><span class="sxs-lookup"><span data-stu-id="c1e31-135">Quantum Resources Estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="c1e31-136">Simulatore di traccia Quantum</span><span class="sxs-lookup"><span data-stu-id="c1e31-136">Quantum Trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="c1e31-137">Simulatore di stato completo Quantum</span><span class="sxs-lookup"><span data-stu-id="c1e31-137">Quantum Full State simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 