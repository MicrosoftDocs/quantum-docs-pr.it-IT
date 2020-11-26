---
uid: Microsoft.Quantum.Intrinsic.Exp
title: Operazione exp
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Exp
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator.

  \begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: 2eea29ec08260ea9cee1bafde80a0942e06f5abc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96212410"
---
# <a name="exp-operation"></a>Operazione exp

Spazio dei nomi: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Applica il valore esponenziale di un operatore qubit di Pauli.

\begin{align} e ^ {i \theta [P_0 \otimes P_1 \cdots P_ {N-1}]}, \end{align} dove $P _i $ è l'elemento $i $ th di `paulis` e dove $N = $ `Length(paulis)` .

```qsharp
operation Exp (paulis : Pauli[], theta : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Input

### <a name="paulis--pauli"></a>Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Matrice di valori Pauli Single-qubit che indicano i fattori del prodotto tensore in ogni qubit.


### <a name="theta--double"></a>Theta: [Double](xref:microsoft.quantum.lang-ref.double)

Angolo relativo all'operatore Pauli qubit specificato in base al quale deve essere ruotato il registro di destinazione.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Eseguire la registrazione per applicare la rotazione specificata a.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)

