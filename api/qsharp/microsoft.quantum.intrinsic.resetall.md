---
uid: Microsoft.Quantum.Intrinsic.ResetAll
title: Operazione ResetAll
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ResetAll
qsharp.summary: Given an array of qubits, measure them and ensure they are in the |0⟩ state such that they can be safely released.
ms.openlocfilehash: 00b7c0f508d76fb0f5b46c7ec00c0718469365a3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711413"
---
# <a name="resetall-operation"></a>Operazione ResetAll

Spazio dei nomi: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)

Pacchetto [](https://nuget.org/packages/)


Dato un array di qubits, misurarli e assicurarsi che si trovino nello stato di ⟩ | 0 in modo che possano essere rilasciati in modo sicuro.

```qsharp
operation ResetAll (qubits : Qubit[]) : Unit
```


## <a name="input"></a>Input

### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Matrice di qubits i cui Stati devono essere reimpostati su $ \ket {0} $.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)

