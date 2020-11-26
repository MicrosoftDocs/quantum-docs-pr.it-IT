---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitA
title: Operazione ApplyToFirstQubitA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitA
qsharp.summary: Applies an operation to the first qubit in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 4f0b209988c01076bdd0429d36d98c8060141618
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208840"
---
# <a name="applytofirstqubita-operation"></a>Operazione ApplyToFirstQubitA

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applica un'operazione al primo qubit nel registro.
Il modificatore `A` indica che l'operazione è adjointable.

```qsharp
operation ApplyToFirstQubitA (op : (Qubit => Unit is Adj), register : Qubit[]) : Unit is Adj
```


## <a name="input"></a>Input

### <a name="op--qubit--unit--is-adj"></a>op: [Qubit](xref:microsoft.quantum.lang-ref.qubit) l' => [unità](xref:microsoft.quantum.lang-ref.unit) qubit è ADJ

Operazione da applicare al primo qubit


### <a name="register--qubit"></a>Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Matrice qubit per la prima qubit di cui viene applicata l'operazione



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. ApplyToFirstQubit](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)