---
uid: Microsoft.Quantum.Math.BitSizeL
title: BitSizeL (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeL
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: c94d873d7117fd2ee66226fab6d4bfc5b33bc46d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848919"
---
# <a name="bitsizel-function"></a>BitSizeL (funzione)

Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Per un valore integer non negativo `a` , restituisce il numero di bit necessari per rappresentare `a` .

Ovvero restituisce il più piccolo $n $ in modo che $a < 2 ^ n $.

```qsharp
function BitSizeL (a : BigInt) : Int
```


## <a name="input"></a>Input

### <a name="a--bigint"></a>r: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Integer le cui dimensioni di bit devono essere calcolate.



## <a name="output--int"></a>Output: [int](xref:microsoft.quantum.lang-ref.int)

Dimensioni di bit di `a` .