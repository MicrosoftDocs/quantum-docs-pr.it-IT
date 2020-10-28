---
uid: Microsoft.Quantum.Math.PNormalized
title: PNormalized (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: 6f9dfebe83f52cbf486cd8e6874d3699f5e6b8ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722284"
---
# <a name="pnormalized-function"></a>PNormalized (funzione)

Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pacchetto [](https://nuget.org/packages/)


Normalizza un vettore di `Double` nell'oggetto `L(p)` Norm.

Ovvero, data una matrice $x $ di tipo `Double[]` , restituisce una matrice in cui tutti gli elementi sono divisi per la $p $-norm $ \| x \| _P $.

```qsharp
function PNormalized (p : Double, array : Double[]) : Double[]
```


## <a name="input"></a>Input

### <a name="p--double"></a>p: [Double](xref:microsoft.quantum.lang-ref.double)

L'esponente $p $ nella $p $-Norm.


### <a name="array--double"></a>array: [Double](xref:microsoft.quantum.lang-ref.double)[]





## <a name="output--double"></a>Output: [Double](xref:microsoft.quantum.lang-ref.double)[]

La matrice $x $ normalizzata dalla $p $-norm $ \| x \| _P $.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Math. PNorm](xref:Microsoft.Quantum.Math.PNorm)