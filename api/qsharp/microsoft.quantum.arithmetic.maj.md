---
uid: Microsoft.Quantum.Arithmetic.MAJ
title: Operazione MAJ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MAJ
qsharp.summary: This applies the in-place majority operation to 3 qubits.
ms.openlocfilehash: c1801d1d7ed04ead11b672f24d44a94989cf8f1d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721014"
---
# <a name="maj-operation"></a>Operazione MAJ

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto [](https://nuget.org/packages/)


Questa operazione applica la maggioranza sul posto a 3 qubits.

```qsharp
operation MAJ (input0 : Qubit, input1 : Qubit, target : Qubit) : Unit
```


## <a name="description"></a>Descrizione

Se si denota lo stato della qubit di destinazione come $ \ket{z} $ e gli Stati di input del qubits di input come $ \ket{x} $ e $ \ket{y} $, questa operazione esegue la trasformazione seguente: $ \ket{XYZ} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)} $.

## <a name="input"></a>Input

### <a name="input0--qubit"></a>input0: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Primo qubit di input.


### <a name="input1--qubit"></a>INPUT1: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Secondo qubit di input.


### <a name="target--qubit"></a>destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit su cui verrà applicata la funzione di maggioranza.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)

