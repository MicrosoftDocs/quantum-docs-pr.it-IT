---
uid: Microsoft.Quantum.MachineLearning.CyclicEntanglingLayer
title: CyclicEntanglingLayer (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CyclicEntanglingLayer
qsharp.summary: Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.
ms.openlocfilehash: 5421765e36ef3e8e744e118206dafcb2bb582cc2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211934"
---
# <a name="cyclicentanglinglayer-function"></a>CyclicEntanglingLayer (funzione)

Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacchetto: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Restituisce una matrice di rotazioni controllate singolarmente lungo un asse specificato, disposte ciclicamente in un registro di qubits e parametrizzato da parametri di modello distinti.

```qsharp
function CyclicEntanglingLayer (nQubits : Int, axis : Pauli, stride : Int) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>Input

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Numero di qubits di cui ha agito il livello specificato.


### <a name="axis--pauli"></a>asse: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Asse di rotazione per ogni rotazione nel livello specificato.


### <a name="stride--int"></a>stride: [int](xref:microsoft.quantum.lang-ref.int)

Separazione tra gli indici di destinazione e di controllo per ogni rotazione.



## <a name="output--controlledrotation"></a>Output: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Una matrice di rotazioni controllate da due qubit, disposti ciclicamente in un registro di `nQubits` qubits.