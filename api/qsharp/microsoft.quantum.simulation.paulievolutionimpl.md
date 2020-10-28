---
uid: Microsoft.Quantum.Simulation.PauliEvolutionImpl
title: Operazione PauliEvolutionImpl
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionImpl
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.

  See [Dynamical Generator Modeling](/quantum/libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 2fc9fda2dd6eec71d8b17ba8a00d8545e517eec8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720207"
---
# <a name="paulievolutionimpl-operation"></a>Operazione PauliEvolutionImpl

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto [](https://nuget.org/packages/)


Rappresenta un generatore dinamico come un set di porte simulabili e un'espansione in base a Pauli.

Per ulteriori informazioni, vedere [modellazione dinamica del generatore](/quantum/libraries/data-structures#dynamical-generator-modeling) .

```qsharp
operation PauliEvolutionImpl (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, delta : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a>Input

### <a name="generatorindex--generatorindex"></a>generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Un indice del generatore che deve essere rappresentato come evoluzione unitaria in base a Pauli.


### <a name="delta--double"></a>Delta: [Double](xref:microsoft.quantum.lang-ref.double)

Moltiplicatore per la durata dell'evoluzione del tempo in base al termine a cui si fa riferimento in `generatorIndex` .


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Eseguire la registrazione a seguito dell'operatore Time-Evolution.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)

