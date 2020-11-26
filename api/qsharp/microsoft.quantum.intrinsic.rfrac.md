---
uid: Microsoft.Quantum.Intrinsic.RFrac
title: Operazione RFrac
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: RFrac
qsharp.summary: >-
  Applies a rotation about the given Pauli axis by an angle specified as a dyadic fraction.

  \begin{align} R_{\mu}(n, k) \mathrel{:=} e^{i \pi n \sigma_{\mu} / 2^k}, \end{align} where $\mu \in \{I, X, Y, Z\}$.

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r".
ms.openlocfilehash: bd182ea50d747e07bb0f8051c5dbc128b7ff7674
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198640"
---
# <a name="rfrac-operation"></a>Operazione RFrac

Spazio dei nomi: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Applica una rotazione sull'asse di Pauli specificato da un angolo specificato come frazione diadico.

\begin{align} R_ {\mu} (n, k) \mathrel{: =} e ^ {i \Pi n \ sigma_ {\mu}/2 ^ k}, \end{align} dove $ \mu \In \{ i, X, Y, Z \} $.

> [!WARNING]
> Questa operazione usa la convenzione di segno **opposto** da @"microsoft.quantum.intrinsic.r" .

```qsharp
operation RFrac (pauli : Pauli, numerator : Int, power : Int, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Input

### <a name="pauli--pauli"></a>Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Operatore Pauli da exponentiated per formare la rotazione.


### <a name="numerator--int"></a>numeratore: [int](xref:microsoft.quantum.lang-ref.int)

Numeratore nella rappresentazione della frazione diadico dell'angolo in base al quale deve essere ruotato qubit.


### <a name="power--int"></a>Potenza: [int](xref:microsoft.quantum.lang-ref.int)

Potenza di due che specifica il denominatore dell'angolo in base al quale deve essere ruotato il qubit.


### <a name="qubit--qubit"></a>Qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit a cui deve essere applicato il controllo.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

Equivalente a:

```qsharp
// PI() is a Q# function that returns an approximation of π.
R(pauli, -PI() * IntAsDouble(numerator) / IntAsDouble(2 ^ (power - 1)), qubit);
```