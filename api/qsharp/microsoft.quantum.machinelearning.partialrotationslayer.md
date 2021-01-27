---
uid: Microsoft.Quantum.MachineLearning.PartialRotationsLayer
title: PartialRotationsLayer (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: PartialRotationsLayer
qsharp.summary: Returns an array of single-qubit rotations along a given axis, parameterized by distinct model parameters.
ms.openlocfilehash: e230df9b28c59e1d532d5b36adf90efa01f0f33e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852928"
---
# <a name="partialrotationslayer-function"></a>PartialRotationsLayer (funzione)

Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacchetto: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Restituisce una matrice di rotazioni a qubit singolo lungo un asse specificato, parametrizzato da parametri di modello distinti.

```qsharp
function PartialRotationsLayer (idxsQubits : Int[], axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>Input

### <a name="idxsqubits--int"></a>idxsQubits: [int](xref:microsoft.quantum.lang-ref.int)[]

Indici per il qubits da usare come destinazioni per ogni rotazione.


### <a name="axis--pauli"></a>asse: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Asse di rotazione per ogni rotazione nel livello specificato.



## <a name="output--controlledrotation"></a>Output: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Matrice di rotazioni controllate sull'asse specificato, una per ogni `nQubits` qubits.