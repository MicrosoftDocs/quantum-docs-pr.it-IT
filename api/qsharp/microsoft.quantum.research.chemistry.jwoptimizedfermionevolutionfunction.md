---
uid: Microsoft.Quantum.Research.Chemistry.JWOptimizedFermionEvolutionFunction
title: JWOptimizedFermionEvolutionFunction (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JWOptimizedFermionEvolutionFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.
ms.openlocfilehash: 40a4bccc6cf74a63c354bfd628baa45768916fe2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229920"
---
# <a name="jwoptimizedfermionevolutionfunction-function"></a>JWOptimizedFermionEvolutionFunction (funzione)

Spazio dei nomi: [Microsoft. Quantum. Research. Chemistry](xref:Microsoft.Quantum.Research.Chemistry)

Pacchetto: [Microsoft. Quantum. Research. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)


Rappresenta un generatore dinamico come un set di controlli simulabili e un'espansione in base a JWOptimized.

```qsharp
function JWOptimizedFermionEvolutionFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, parityQubit : Qubit) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a>Input

### <a name="generatorindex--generatorindex"></a>generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Indice del generatore da rappresentare come evoluzione unitaria in base a JWOptimized.


### <a name="parityqubit--qubit"></a>parityQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit che determina il segno di evoluzione del tempo.



## <a name="output--evolutionunitary"></a>Output: [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)

Oggetto `EvolutionUnitary` che rappresenta l'evoluzione del tempo in base al termine a cui si fa riferimento in ' generatorIndex '.