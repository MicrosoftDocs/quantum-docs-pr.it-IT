---
uid: Microsoft.Quantum.Simulation.TrotterSimulationAlgorithmImpl
title: Operazione TrotterSimulationAlgorithmImpl
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterSimulationAlgorithmImpl
qsharp.summary: Makes repeated calls to `TrotterStep` to approximate the time-evolution operator exp(_-iHt_).
ms.openlocfilehash: 2af68532d700a1fb5b037707ce4650696cbe1a64
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725361"
---
# <a name="trottersimulationalgorithmimpl-operation"></a>Operazione TrotterSimulationAlgorithmImpl

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto [](https://nuget.org/packages/)


Effettua chiamate ripetute a `TrotterStep` per approssimare l'operatore Time-Evolution exp ( _-iHt_ ).

```qsharp
operation TrotterSimulationAlgorithmImpl (trotterStepSize : Double, trotterOrder : Int, maxTime : Double, evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, qubits : Qubit[]) : Unit
```


## <a name="input"></a>Input

### <a name="trotterstepsize--double"></a>trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)

Durata dell'evoluzione del tempo simulato in un singolo passaggio Trotter.


### <a name="trotterorder--int"></a>trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)

Ordine di Trotter Integrator. Deve essere 1 o un numero pari.


### <a name="maxtime--double"></a>maxTime: [Double](xref:microsoft.quantum.lang-ref.double)

Durata totale della simulazione $t $.


### <a name="evolutiongenerator--evolutiongenerator"></a>evolutionGenerator: [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)

Descrizione completa del sistema da simulare.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubits agito da simulazione.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)

