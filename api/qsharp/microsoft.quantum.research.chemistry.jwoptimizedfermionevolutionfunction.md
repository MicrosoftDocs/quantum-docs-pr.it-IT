---
uid: Microsoft.Quantum.Research.Chemistry.JWOptimizedFermionEvolutionFunction
title: JWOptimizedFermionEvolutionFunction (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JWOptimizedFermionEvolutionFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.
ms.openlocfilehash: 952f3dc4ab0595ace0ee34c040cb21969afa111f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710800"
---
# <a name="jwoptimizedfermionevolutionfunction-function"></a><span data-ttu-id="cb8da-102">JWOptimizedFermionEvolutionFunction (funzione)</span><span class="sxs-lookup"><span data-stu-id="cb8da-102">JWOptimizedFermionEvolutionFunction function</span></span>

<span data-ttu-id="cb8da-103">Spazio dei nomi: [Microsoft. Quantum. Research. Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="cb8da-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="cb8da-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cb8da-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cb8da-105">Rappresenta un generatore dinamico come un set di controlli simulabili e un'espansione in base a JWOptimized.</span><span class="sxs-lookup"><span data-stu-id="cb8da-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.</span></span>

```qsharp
function JWOptimizedFermionEvolutionFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, parityQubit : Qubit) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a><span data-ttu-id="cb8da-106">Input</span><span class="sxs-lookup"><span data-stu-id="cb8da-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="cb8da-107">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="cb8da-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="cb8da-108">Indice del generatore da rappresentare come evoluzione unitaria in base a JWOptimized.</span><span class="sxs-lookup"><span data-stu-id="cb8da-108">A generator index to be represented as unitary evolution in the JWOptimized basis.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="cb8da-109">parityQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="cb8da-109">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="cb8da-110">Qubit che determina il segno di evoluzione del tempo.</span><span class="sxs-lookup"><span data-stu-id="cb8da-110">Qubit that determines the sign of time-evolution.</span></span>



## <a name="output--evolutionunitary"></a><span data-ttu-id="cb8da-111">Output: [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span><span class="sxs-lookup"><span data-stu-id="cb8da-111">Output : [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span></span>

<span data-ttu-id="cb8da-112">Oggetto `EvolutionUnitary` che rappresenta l'evoluzione del tempo in base al termine a cui si fa riferimento in ' generatorIndex '.</span><span class="sxs-lookup"><span data-stu-id="cb8da-112">An `EvolutionUnitary` representing time-evolution by the term referenced in \`generatorIndex.</span></span>