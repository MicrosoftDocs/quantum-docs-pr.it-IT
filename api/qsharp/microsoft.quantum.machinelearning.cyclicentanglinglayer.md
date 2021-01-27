---
uid: Microsoft.Quantum.MachineLearning.CyclicEntanglingLayer
title: CyclicEntanglingLayer (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CyclicEntanglingLayer
qsharp.summary: Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.
ms.openlocfilehash: 5d0af0a60217b69dc7eb8ece8952f2a7f0c09280
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847374"
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

## <a name="example"></a>Esempio

Gli elementi seguenti sono equivalenti:

```qsharp
let layer = CyclicEntanglingLayer(3, PauliX, 2);
let layer = [
    ControlledRotation((0, [2]), PauliX, 0),
    ControlledRotation((1, [0]), PauliX, 1),
    ControlledRotation((2, [1]), PauliX, 2)
];
```