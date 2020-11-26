---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: Tipo definito dall'utente ControlledRotation
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: 1e664b470caeba656ea4a73f70bbc0ef5fe76f7e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196566"
---
# <a name="controlledrotation-user-defined-type"></a>Tipo definito dall'utente ControlledRotation

Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacchetto: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Descrive una rotazione controllata in termini di indici di destinazione e di controllo, asse di rotazione e indice in un vettore di parametri del modello.

```qsharp

newtype ControlledRotation = ((TargetIndex : Int, ControlIndices : Int[]), Axis : Pauli, ParameterIndex : Int);
```



## <a name="named-items"></a>Elementi denominati

### <a name="targetindex--int"></a>TargetIndex: [int](xref:microsoft.quantum.lang-ref.int)

Indice della qubit di destinazione per la rotazione controllata.
### <a name="controlindices--int"></a>ControlIndices: [int](xref:microsoft.quantum.lang-ref.int)[]

Matrice di indici qubit del controllo per la rotazione.
### <a name="axis--pauli"></a>Asse: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Asse della rotazione.
### <a name="parameterindex--int"></a>ParameterIndex: [int](xref:microsoft.quantum.lang-ref.int)

Indice in un vettore di parametri del modello che descrive l'angolo per la rotazione.

## <a name="remarks"></a>Osservazioni

Una rotazione non controllata può essere rappresentata impostando `ControlIndices` su una matrice vuota di indici, `new Int[0]` .