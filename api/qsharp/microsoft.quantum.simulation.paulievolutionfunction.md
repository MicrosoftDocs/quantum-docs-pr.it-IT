---
uid: Microsoft.Quantum.Simulation.PauliEvolutionFunction
title: PauliEvolutionFunction (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: 060f4e4f23bb8b47518a3a22bbca8ab0be6e13b7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720198"
---
# <a name="paulievolutionfunction-function"></a><span data-ttu-id="a0621-102">PauliEvolutionFunction (funzione)</span><span class="sxs-lookup"><span data-stu-id="a0621-102">PauliEvolutionFunction function</span></span>

<span data-ttu-id="a0621-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="a0621-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="a0621-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a0621-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a0621-105">Rappresenta un generatore dinamico come un set di porte simulabili e un'espansione in base a Pauli.</span><span class="sxs-lookup"><span data-stu-id="a0621-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.</span></span>

```qsharp
function PauliEvolutionFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a><span data-ttu-id="a0621-106">Input</span><span class="sxs-lookup"><span data-stu-id="a0621-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="a0621-107">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="a0621-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="a0621-108">Un indice del generatore che deve essere rappresentato come evoluzione unitaria in base a Pauli.</span><span class="sxs-lookup"><span data-stu-id="a0621-108">A generator index to be represented as unitary evolution in the Pauli basis.</span></span>



## <a name="output--evolutionunitary"></a><span data-ttu-id="a0621-109">Output: [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span><span class="sxs-lookup"><span data-stu-id="a0621-109">Output : [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span></span>

<span data-ttu-id="a0621-110">Oggetto `EvolutionUnitary` che rappresenta l'evoluzione del tempo in base al termine a cui si fa riferimento in ' generatorIndex '.</span><span class="sxs-lookup"><span data-stu-id="a0621-110">An `EvolutionUnitary` representing time-evolution by the term referenced in \`generatorIndex.</span></span>