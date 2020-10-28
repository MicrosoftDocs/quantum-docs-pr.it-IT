---
uid: Microsoft.Quantum.Simulation.TrotterStepImpl
title: Operazione TrotterStepImpl
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStepImpl
qsharp.summary: Implements time-evolution by a term contained in a `GeneratorSystem`.
ms.openlocfilehash: 1ddd7ab33df243d729b5b48cba393d976bfd3640
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725322"
---
# <a name="trotterstepimpl-operation"></a>Operazione TrotterStepImpl

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto [](https://nuget.org/packages/)


Implementa l'evoluzione del tempo in base a un termine contenuto in un oggetto `GeneratorSystem` .

```qsharp
operation TrotterStepImpl (evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, idx : Int, stepsize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a>Input

### <a name="evolutiongenerator--evolutiongenerator"></a>evolutionGenerator: [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)

Descrizione completa del sistema da simulare.


### <a name="idx--int"></a>idx: [int](xref:microsoft.quantum.lang-ref.int)

Indice Integer a un termine nel sistema descritto.


### <a name="stepsize--double"></a>STEPSIZE: [Double](xref:microsoft.quantum.lang-ref.double)

Moltiplicatore per la durata dell'evoluzione del tempo per termine indicizzato da `idx` .


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubits agito da simulazione.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)

