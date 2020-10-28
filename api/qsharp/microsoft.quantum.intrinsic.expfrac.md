---
uid: Microsoft.Quantum.Intrinsic.ExpFrac
title: Operazione ExpFrac
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ExpFrac
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator with an argument given by a dyadic fraction.

  \begin{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: d11912a272387b087098f59e7ac071534b01c054
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711486"
---
# <a name="expfrac-operation"></a>Operazione ExpFrac

Spazio dei nomi: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)

Pacchetto [](https://nuget.org/packages/)


Applica il valore esponenziale di un operatore qubit di Pauli con un argomento fornito da una frazione diadico.

\begin{align} e ^ {i \Pi k [P_0 \otimes P_1 \cdots P_ {N-1}]/2 ^ N}, \end{align} dove $P _i $ è l'elemento $i $ th di `paulis` e dove $N = $ `Length(paulis)` .

```qsharp
operation ExpFrac (paulis : Pauli[], numerator : Int, power : Int, qubits : Qubit[]) : Unit
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

