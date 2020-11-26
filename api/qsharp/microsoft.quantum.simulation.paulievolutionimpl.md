---
uid: Microsoft.Quantum.Simulation.PauliEvolutionImpl
title: Operazione PauliEvolutionImpl
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionImpl
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.

  See [Dynamical Generator Modeling](/quantum/libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 868f3eef187e8e993127cfcab21e1574583ac845
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229138"
---
# <a name="paulievolutionimpl-operation"></a><span data-ttu-id="1f69d-102">Operazione PauliEvolutionImpl</span><span class="sxs-lookup"><span data-stu-id="1f69d-102">PauliEvolutionImpl operation</span></span>

<span data-ttu-id="1f69d-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="1f69d-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="1f69d-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1f69d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1f69d-105">Rappresenta un generatore dinamico come un set di porte simulabili e un'espansione in base a Pauli.</span><span class="sxs-lookup"><span data-stu-id="1f69d-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.</span></span>

<span data-ttu-id="1f69d-106">Per ulteriori informazioni, vedere [modellazione dinamica del generatore](/quantum/libraries/data-structures#dynamical-generator-modeling) .</span><span class="sxs-lookup"><span data-stu-id="1f69d-106">See [Dynamical Generator Modeling](/quantum/libraries/data-structures#dynamical-generator-modeling) for more details.</span></span>

```qsharp
operation PauliEvolutionImpl (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, delta : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="1f69d-107">Input</span><span class="sxs-lookup"><span data-stu-id="1f69d-107">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="1f69d-108">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="1f69d-108">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="1f69d-109">Un indice del generatore che deve essere rappresentato come evoluzione unitaria in base a Pauli.</span><span class="sxs-lookup"><span data-stu-id="1f69d-109">A generator index to be represented as unitary evolution in the Pauli basis.</span></span>


### <a name="delta--double"></a><span data-ttu-id="1f69d-110">Delta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1f69d-110">delta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1f69d-111">Moltiplicatore per la durata dell'evoluzione del tempo in base al termine a cui si fa riferimento in `generatorIndex` .</span><span class="sxs-lookup"><span data-stu-id="1f69d-111">A multiplier on the duration of time-evolution by the term referenced in `generatorIndex`.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="1f69d-112">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1f69d-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1f69d-113">Eseguire la registrazione a seguito dell'operatore Time-Evolution.</span><span class="sxs-lookup"><span data-stu-id="1f69d-113">Register acted upon by time-evolution operator.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1f69d-114">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1f69d-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

