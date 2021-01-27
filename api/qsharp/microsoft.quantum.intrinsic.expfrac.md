---
uid: Microsoft.Quantum.Intrinsic.ExpFrac
title: Operazione ExpFrac
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ExpFrac
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator with an argument given by a dyadic fraction.

  \begin{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: 6634caff164c841876fb53e79c3f93254a7d624c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849426"
---
# <a name="expfrac-operation"></a>Operazione ExpFrac

Spazio dei nomi: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Applica il valore esponenziale di un operatore qubit di Pauli con un argomento fornito da una frazione diadico.

\begin{align} e ^ {i \Pi k [P_0 \otimes P_1 \cdots P_ {N-1}]/2 ^ N}, \end{align} dove $P _i $ è l'elemento $i $ th di `paulis` e dove $N = $ `Length(paulis)` .

```qsharp
operation ExpFrac (paulis : Pauli[], numerator : Int, power : Int, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Input

### <a name="paulis--pauli"></a>Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Matrice di valori Pauli Single-qubit che indicano i fattori del prodotto tensore in ogni qubit.


### <a name="numerator--int"></a>numeratore: [int](xref:microsoft.quantum.lang-ref.int)

Numeratore ($k $) nella rappresentazione della frazione diadico dell'angolo in base al quale deve essere ruotato il registro qubit.


### <a name="power--int"></a>Potenza: [int](xref:microsoft.quantum.lang-ref.int)

Potenza di due ($n $) che specifica il denominatore dell'angolo in base al quale deve essere ruotato il registro qubit.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Eseguire la registrazione per applicare la rotazione specificata a.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)

