---
uid: Microsoft.Quantum.Arithmetic.ApplyMajorityInPlace
title: Operazione ApplyMajorityInPlace
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyMajorityInPlace
qsharp.summary: Applies the three-qubit majority operation in-place on a register of qubits.
ms.openlocfilehash: c32d7546fb753f78a72479cec11a6ed09c5e6179
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190735"
---
# <a name="applymajorityinplace-operation"></a>Operazione ApplyMajorityInPlace

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applica l'operazione di maggioranza dei tre qubit sul posto in un registro di qubits.

```qsharp
operation ApplyMajorityInPlace (output : Qubit, input : Qubit[]) : Unit is Adj + Ctl
```


## <a name="description"></a>Descrizione

Questa operazione calcola la funzione di maggioranza sul posto su 3 qubits.

Se si denota output qubit come $z $ e input qubits come $x $ e $y $, l'operazione esegue la trasformazione seguente: $ \ket{XYZ} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)} $.

## <a name="input"></a>Input

### <a name="output--qubit"></a>output: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Primo input qubit. Si noti che l'output viene calcolato sul posto e archiviato in questo qubit.


### <a name="input--qubit"></a>input: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Secondo e terzo qubits di input.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)

