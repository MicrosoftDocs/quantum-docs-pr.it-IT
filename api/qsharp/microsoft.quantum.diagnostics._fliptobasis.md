---
uid: Microsoft.Quantum.Diagnostics._flipToBasis
title: operazione _flipToBasis
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _flipToBasis
qsharp.summary: >-
  Applies unitaries that map $\ket{0}\otimes\cdots\ket{0}$ to $\ket{\psi_0} \otimes \ket{\psi_{n - 1}}$, where $\ket{\psi_k}$ depends on `basis[k]`.

  The correspondence between value of `basis[k]` and $\ket{\psi_k}$ is the following:

  - `basis[k]=0` $\rightarrow \ket{0}$. - `basis[k]=1` $\rightarrow \ket{1}$. - `basis[k]=2` $\rightarrow \ket{+}$. - `basis[k]=3` $\rightarrow \ket{i}$ ( +1 eigenstate of Pauli Y ).
ms.openlocfilehash: e074ed2ae259f6aef49a8d327ce518a9e2caebfa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713149"
---
# <a name="_fliptobasis-operation"></a>operazione _flipToBasis

Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacchetto [](https://nuget.org/packages/)


Applica unitaries che mappano $ \ket {0} \otimes\cdots\ket {0} $ a $ \ket{\ psi_0} \otimes \ket{\ psi_ {n-1}} $, dove $ \ket{\ psi_k} $ dipende da `basis[k]` .

La corrispondenza tra il valore di `basis[k]` e $ \ket{\ psi_k} $ è la seguente:

- `basis[k]=0` $ \rightarrow \ket {0} $.
- `basis[k]=1` $ \rightarrow \ket {1} $.
- `basis[k]=2` $ \rightarrow \ket{+} $.
- `basis[k]=3` $ \rightarrow \ket{i} $ (+ 1 autostato di Pauli Y).

```qsharp
operation _flipToBasis (basis : Int[], qubits : Qubit[]) : Unit
```


## <a name="input"></a>Input

### <a name="basis--int"></a>base: [int](xref:microsoft.quantum.lang-ref.int)[]

Matrice di ID di stato di base a qubit singolo (0 <= ID <= 3), uno per ogni elemento di qubits.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit da operare.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)

