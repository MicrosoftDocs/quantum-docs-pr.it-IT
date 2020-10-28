---
uid: Microsoft.Quantum.Intrinsic.Exp
title: Operazione exp
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Exp
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator.

  \begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: b923374a954f90aba2deaead79dd419fbf67fea3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711525"
---
# <a name="exp-operation"></a>Operazione exp

Spazio dei nomi: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)

Pacchetto [](https://nuget.org/packages/)


Applica il valore esponenziale di un operatore qubit di Pauli.

\begin{align} e ^ {i \theta [P_0 \otimes P_1 \cdots P_ {N-1}]}, \end{align} dove $P _i $ è l'elemento $i $ th di `paulis` e dove $N = $ `Length(paulis)` .

```qsharp
operation Exp (paulis : Pauli[], theta : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a>Input

### <a name="paulis--pauli"></a>Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Matrice di valori Pauli Single-qubit che indicano i fattori del prodotto tensore in ogni qubit.


### <a name="theta--double"></a>Theta: [Double](xref:microsoft.quantum.lang-ref.double)

Angolo relativo all'operatore Pauli qubit specificato in base al quale deve essere ruotato il registro di destinazione.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Eseguire la registrazione per applicare la rotazione specificata a.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)

