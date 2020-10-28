---
uid: Microsoft.Quantum.Math.PNorm
title: PNorm (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNorm
qsharp.summary: >-
  Returns the `L(p)` norm of a vector of `Double`s.

  That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.
ms.openlocfilehash: cea85715e448305486f6d8a6c10e11da56edf3ee
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722298"
---
# <a name="pnorm-function"></a>PNorm (funzione)

Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pacchetto [](https://nuget.org/packages/)


Restituisce la `L(p)` norma di un vettore di `Double` s.

Ovvero, data una matrice $x $ di tipo `Double[]` , restituisce l'$p $-norm $ \| x \| \_ p = (\ Sum_ {j} | x_j | ^ {p}) ^ {1/p} $.

```qsharp
function PNorm (p : Double, array : Double[]) : Double
```


## <a name="input"></a>Input

### <a name="p--double"></a>p: [Double](xref:microsoft.quantum.lang-ref.double)

L'esponente $p $ nella $p $-Norm.


### <a name="array--double"></a>array: [Double](xref:microsoft.quantum.lang-ref.double)[]





## <a name="output--double"></a>Output: [Double](xref:microsoft.quantum.lang-ref.double)

Il $p $-norm $ \| x \| _P $.