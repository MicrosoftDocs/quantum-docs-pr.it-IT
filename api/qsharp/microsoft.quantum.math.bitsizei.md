---
uid: Microsoft.Quantum.Math.BitSizeI
title: BitSizeI (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeI
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: e7cfe03908a8a394fc8ceb1c9facbf02f3db2d48
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723194"
---
# <a name="bitsizei-function"></a>BitSizeI (funzione)

Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pacchetto [](https://nuget.org/packages/)


Per un valore integer non negativo `a` , restituisce il numero di bit necessari per rappresentare `a` .

Ovvero restituisce il più piccolo $n $ in modo che $a < 2 ^ n $.

```qsharp
function BitSizeI (a : Int) : Int
```


## <a name="input"></a>Input

### <a name="a--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)

Integer le cui dimensioni di bit devono essere calcolate.



## <a name="output--int"></a>Output: [int](xref:microsoft.quantum.lang-ref.int)

Dimensioni di bit di `a` .