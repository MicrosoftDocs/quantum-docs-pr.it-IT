---
uid: Microsoft.Quantum.Simulation.InterpolatedEvolution
title: InterpolatedEvolution (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolatedEvolution
qsharp.summary: Interpolates between two generators with a uniform schedule, returning an operation that applies simulated evolution under the resulting time-dependent generator to a qubit register.
ms.openlocfilehash: 2ad907c02a2412dd4bf95630f401b5f1db5c8a08
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225109"
---
# <a name="interpolatedevolution-function"></a><span data-ttu-id="72add-102">InterpolatedEvolution (funzione)</span><span class="sxs-lookup"><span data-stu-id="72add-102">InterpolatedEvolution function</span></span>

<span data-ttu-id="72add-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="72add-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="72add-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="72add-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="72add-105">Esegue l'interpolazione tra due generatori con una pianificazione uniforme, restituendo un'operazione che applica l'evoluzione simulata sotto il generatore dipendente dal tempo risultante a un registro qubit.</span><span class="sxs-lookup"><span data-stu-id="72add-105">Interpolates between two generators with a uniform schedule, returning an operation that applies simulated evolution under the resulting time-dependent generator to a qubit register.</span></span>

```qsharp
function InterpolatedEvolution (interpolationTime : Double, evolutionGeneratorStart : Microsoft.Quantum.Simulation.EvolutionGenerator, evolutionGeneratorEnd : Microsoft.Quantum.Simulation.EvolutionGenerator, timeDependentSimulationAlgorithm : Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="72add-106">Input</span><span class="sxs-lookup"><span data-stu-id="72add-106">Input</span></span>

### <a name="interpolationtime--double"></a><span data-ttu-id="72add-107">interpolationTime: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="72add-107">interpolationTime : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="72add-108">Tempo di esecuzione dell'interpolazione.</span><span class="sxs-lookup"><span data-stu-id="72add-108">Time to perform the interpolation over.</span></span>


### <a name="evolutiongeneratorstart--evolutiongenerator"></a><span data-ttu-id="72add-109">evolutionGeneratorStart: [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="72add-109">evolutionGeneratorStart : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="72add-110">Generatore iniziale per simulare l'evoluzione in.</span><span class="sxs-lookup"><span data-stu-id="72add-110">Initial generator to simulate evolution under.</span></span>


### <a name="evolutiongeneratorend--evolutiongenerator"></a><span data-ttu-id="72add-111">evolutionGeneratorEnd: [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="72add-111">evolutionGeneratorEnd : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="72add-112">Generatore finale per simulare l'evoluzione in.</span><span class="sxs-lookup"><span data-stu-id="72add-112">Final generator to simulate evolution under.</span></span>


### <a name="timedependentsimulationalgorithm--timedependentsimulationalgorithm"></a><span data-ttu-id="72add-113">timeDependentSimulationAlgorithm: [timeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="72add-113">timeDependentSimulationAlgorithm : [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span></span>

<span data-ttu-id="72add-114">Algoritmo di simulazione dipendente dal tempo che verrà usato per simulare l'evoluzione durante la pianificazione dell'interpolazione uniforme.</span><span class="sxs-lookup"><span data-stu-id="72add-114">A time-dependent simulation algorithm that will be used to simulate evolution during the uniform interpolation schedule.</span></span>



## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="72add-115">Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="72add-115">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>



## <a name="remarks"></a><span data-ttu-id="72add-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="72add-116">Remarks</span></span>

<span data-ttu-id="72add-117">Se viene scelto il tempo di interpolazione per soddisfare le condizioni di adiabatica, questa funzione restituisce un'operazione che esegue la preparazione dello stato adiabatica per il generatore dinamico finale.</span><span class="sxs-lookup"><span data-stu-id="72add-117">If the interpolation time is chosen to meet the adiabatic conditions, then this function returns an operation which performs adiabatic state preparation for the final dynamical generator.</span></span>