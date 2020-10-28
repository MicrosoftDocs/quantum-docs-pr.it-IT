---
uid: Microsoft.Quantum.Intrinsic.SWAP
title: Operazione di scambio
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: SWAP
qsharp.summary: >-
  Applies the SWAP gate to a pair of qubits.

  \begin{align} \operatorname{SWAP} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix}, \end{align}

  where rows and columns are ordered as in the quantum concepts guide.
ms.openlocfilehash: 18b910741e9d0883fc5fcd025eb647407c823269
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719994"
---
# <a name="swap-operation"></a>Operazione di scambio

Spazio dei nomi: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)

Pacchetto [](https://nuget.org/packages/)


Applica lo SWAP Gate a una coppia di qubits.

\begin{align} \operatorname{SWAP} \mathrel{: =} \begin{Bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \end{Bmatrix}, \end{align}

dove righe e colonne vengono ordinate come nella Guida ai concetti di Quantum.

```qsharp
operation SWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit
```


## <a name="input"></a>Input

### <a name="qubit1--qubit"></a>qubit1: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Primo qubit da scambiare.


### <a name="qubit2--qubit"></a>qubit2: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Secondo qubit da scambiare.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

Equivalente a:

```qsharp
CNOT(qubit1, qubit2);
CNOT(qubit2, qubit1);
CNOT(qubit1, qubit2);
```