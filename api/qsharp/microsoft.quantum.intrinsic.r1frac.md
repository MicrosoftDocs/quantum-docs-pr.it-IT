---
uid: Microsoft.Quantum.Intrinsic.R1Frac
title: Operazione R1Frac
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R1Frac
qsharp.summary: >-
  Applies a rotation about the $\ket{1}$ state by an angle specified as a dyadic fraction.

  \begin{align} R_1(n, k) \mathrel{:=} \operatorname{diag}(1, e^{i \pi k / 2^n}). \end{align}

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r", and does not include the > factor of $1/ 2$ included by @"microsoft.quantum.intrinsic.r1".
ms.openlocfilehash: bfa6cd60eebd05feec8cfa2bf71e09dc0d02843a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720903"
---
# <a name="r1frac-operation"></a>Operazione R1Frac

Spazio dei nomi: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)

Pacchetto [](https://nuget.org/packages/)


Applica una rotazione sullo {1} stato di $ \ket $ da un angolo specificato come frazione diadico.

\begin{align} R_1 (n, k) \mathrel{: =} \operatorname{diag} (1, e ^ {i \Pi k/2 ^ n}).
\end{align}

> [!WARNING]
> Questa operazione usa la convenzione di segno **opposto** da @"microsoft.quantum.intrinsic.r" e non include il fattore di $1/2 $ incluso in @"microsoft.quantum.intrinsic.r1" .

```qsharp
operation R1Frac (numerator : Int, power : Int, qubit : Qubit) : Unit
```


## <a name="input"></a>Input

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
RFrac(PauliZ, -numerator, denominator + 1, qubit);
RFrac(PauliI, numerator, denominator + 1, qubit);
```