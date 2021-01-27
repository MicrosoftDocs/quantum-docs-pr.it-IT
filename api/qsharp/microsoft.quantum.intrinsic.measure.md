---
uid: Microsoft.Quantum.Intrinsic.Measure
title: Operazione di misurazione
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Measure
qsharp.summary: >-
  Performs a joint measurement of one or more qubits in the specified Pauli bases.

  The output result is given by the distribution: \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \frac12 \braket{ \psi \mid| \left( \boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_{N-1} \right) \mid| \psi }, \end{align} where $P_i$ is the $i$th element of `bases`, and where $N = \texttt{Length}(\texttt{bases})$. That is, measurement returns a `Result` $d$ such that the eigenvalue of the observed measurement effect is $(-1)^d$.
ms.openlocfilehash: bf0a606b1bfc8c4762245422450ec26907ec1946
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818780"
---
# <a name="measure-operation"></a>Operazione di misurazione

Spazio dei nomi: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Esegue una misurazione congiunta di uno o più qubits nelle basi di Pauli specificate.

Il risultato di output viene fornito dalla distribuzione: \begin{align} \Pr (\texttt{Zero} | \ket{\psi}) = \frac12 \braket{\psi \MID | \left (\boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_ {N-1} \right) \MID | \psi}, \end{align} dove $P _i $ è l'elemento $i $ th di `bases` e dove $N = \texttt{Length} (\texttt{Bases}) $.
Ovvero, la misurazione restituisce un `Result` $d $, in modo che il valore di autovalore dell'effetto di misurazione osservato sia $ (-1) ^ d $.

```qsharp
operation Measure (bases : Pauli[], qubits : Qubit[]) : Result
```


## <a name="input"></a>Input

### <a name="bases--pauli"></a>basi: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Matrice di valori Pauli Single-qubit che indicano i fattori del prodotto tensore in ogni qubit.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro di qubits da misurare.



## <a name="output--__invalidresult__"></a>Output: __non <Result> valido__

`Zero` Se viene osservato il autovalore $ + $1 e `One` se viene osservato il autovalore $-$1.

## <a name="remarks"></a>Commenti

Se la matrice di base e la matrice qubit hanno lunghezze diverse, l'operazione avrà esito negativo.