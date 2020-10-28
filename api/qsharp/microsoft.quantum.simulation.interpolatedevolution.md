---
uid: Microsoft.Quantum.Simulation.InterpolatedEvolution
title: InterpolatedEvolution (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolatedEvolution
qsharp.summary: Interpolates between two generators with a uniform schedule, returning an operation that applies simulated evolution under the resulting time-dependent generator to a qubit register.
ms.openlocfilehash: 18026b9872f6a3344a1e5c2122f55927975ccb59
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710587"
---
# <a name="interpolatedevolution-function"></a>InterpolatedEvolution (funzione)

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto [](https://nuget.org/packages/)


Esegue l'interpolazione tra due generatori con una pianificazione uniforme, restituendo un'operazione che applica l'evoluzione simulata sotto il generatore dipendente dal tempo risultante a un registro qubit.

```qsharp
function InterpolatedEvolution (interpolationTime : Double, evolutionGeneratorStart : Microsoft.Quantum.Simulation.EvolutionGenerator, evolutionGeneratorEnd : Microsoft.Quantum.Simulation.EvolutionGenerator, timeDependentSimulationAlgorithm : Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>Input

### <a name="interpolationtime--double"></a>interpolationTime: [Double](xref:microsoft.quantum.lang-ref.double)

Tempo di esecuzione dell'interpolazione.


### <a name="evolutiongeneratorstart--evolutiongenerator"></a>evolutionGeneratorStart: [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)

Generatore iniziale per simulare l'evoluzione in.


### <a name="evolutiongeneratorend--evolutiongenerator"></a>evolutionGeneratorEnd: [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)

Generatore finale per simulare l'evoluzione in.


### <a name="timedependentsimulationalgorithm--timedependentsimulationalgorithm"></a>timeDependentSimulationAlgorithm: [timeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)

Algoritmo di simulazione dipendente dal tempo che verrà usato per simulare l'evoluzione durante la pianificazione dell'interpolazione uniforme.



## <a name="output--qubit--unit-adj--ctl"></a>Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL



## <a name="remarks"></a>Commenti

Se viene scelto il tempo di interpolazione per soddisfare le condizioni di adiabatica, questa funzione restituisce un'operazione che esegue la preparazione dello stato adiabatica per il generatore dinamico finale.