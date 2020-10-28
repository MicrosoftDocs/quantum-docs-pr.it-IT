---
uid: Microsoft.Quantum.Chemistry.JordanWigner.PrepareUnitaryCoupledClusterState
title: Operazione PrepareUnitaryCoupledClusterState
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: PrepareUnitaryCoupledClusterState
qsharp.summary: Unitary coupled-cluster state preparation of trial state
ms.openlocfilehash: 4db31e3e79d27f12178dbf121cd04727c2332c62
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713824"
---
# <a name="prepareunitarycoupledclusterstate-operation"></a>Operazione PrepareUnitaryCoupledClusterState

Spazio dei nomi: [Microsoft. Quantum. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Pacchetto [](https://nuget.org/packages/)


Accoppiato unitario-preparazione stato del cluster dello stato di valutazione

```qsharp
operation PrepareUnitaryCoupledClusterState (initialStatePreparation : (Qubit[] => Unit), clusterOperator : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[], trotterStepSize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a>Input

### <a name="initialstatepreparation--qubit--unit"></a>initialStatePreparation: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unità](xref:microsoft.quantum.lang-ref.unit)> 

Unità per preparare lo stato di valutazione iniziale.


### <a name="clusteroperator--jordanwignerinputstate"></a>clusterOperator: [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]




### <a name="trotterstepsize--double"></a>trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)




### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubits di hamiltoniana.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)

