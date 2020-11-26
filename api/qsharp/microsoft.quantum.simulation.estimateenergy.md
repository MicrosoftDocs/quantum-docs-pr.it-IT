---
uid: Microsoft.Quantum.Simulation.EstimateEnergy
title: Operazione EstimateEnergy
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EstimateEnergy
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: 0a02a8aad891c45b184b9b18d4e9383236485940
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229495"
---
# <a name="estimateenergy-operation"></a>Operazione EstimateEnergy

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Esegue la preparazione dello stato applicando un oggetto `statePrepUnitary` in una stima della fase dello stato di input allocata automaticamente rispetto a nello `qpeUnitary` stato risultante utilizzando un oggetto `phaseEstAlgorithm` .

```qsharp
operation EstimateEnergy (nQubits : Int, statePrepUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double)) : Double
```


## <a name="input"></a>Input

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Numero di qubits usati per eseguire la simulazione.


### <a name="stateprepunitary--qubit--unit"></a>statePrepUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unità](xref:microsoft.quantum.lang-ref.unit)> 

Oggetto Oracle che rappresenta la preparazione dello stato per il generatore dinamico iniziale.


### <a name="qpeunitary--qubit--unit--is-adj--ctl"></a>qpeUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL

Oracle che rappresenta un operatore unitario $U $ che rappresenta l'evoluzione per il tempo $ \delta t $ in un generatore dinamico con stato di base $ \ket{\Phi} $ e l'energia dello stato di base $E = \Phi \\ , \delta t $.


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a>phaseEstAlgorithm: ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double) 

Operazione che esegue la stima della fase su una determinata operazione unitaria.
Per ulteriori informazioni, vedere la [stima della fase iterativa](/quantum/libraries/characterization#iterative-phase-estimation) .



## <a name="output--double"></a>Output: [Double](xref:microsoft.quantum.lang-ref.double)

Una stima $ \hat{\Phi} $ dell'energia dello stato di base $ \Phi $ dell'energia di stato di base del generatore rappresentato da $U $.