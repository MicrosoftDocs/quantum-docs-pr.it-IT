---
uid: Microsoft.Quantum.Arithmetic.ApplyMajorityInPlace
title: Operazione ApplyMajorityInPlace
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyMajorityInPlace
qsharp.summary: Applies the three-qubit majority operation in-place on a register of qubits.
ms.openlocfilehash: 3664ffe96cd1db8cf5e8898387fe7f2d45b4ea98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721599"
---
# <a name="applymajorityinplace-operation"></a>Operazione ApplyMajorityInPlace

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto [](https://nuget.org/packages/)


Applica l'operazione di maggioranza dei tre qubit sul posto in un registro di qubits.

```qsharp
operation ApplyMajorityInPlace (output : Qubit, input : Qubit[]) : Unit
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

