---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorL
title: ExtendedGreatestCommonDivisorL (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorL
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 1445f1c3d2a5852459a492fa5e6bfd2a685786d9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857522"
---
# <a name="extendedgreatestcommondivisorl-function"></a>ExtendedGreatestCommonDivisorL (funzione)

Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Calcola una tupla $ (u, v) $ in modo che $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $, dove $ \operatorname{GCD} $ è $a $ massimo comune divisore di $a $ e $b $. Il MCD è sempre positivo.

```qsharp
function ExtendedGreatestCommonDivisorL (a : BigInt, b : BigInt) : (BigInt, BigInt)
```


## <a name="input"></a>Input

### <a name="a--bigint"></a>r: [bigint](xref:microsoft.quantum.lang-ref.bigint)

il primo numero di cui è in corso il calcolo del divisore più comune esteso


### <a name="b--bigint"></a>b: [bigint](xref:microsoft.quantum.lang-ref.bigint)

secondo numero di cui è in corso il calcolo del divisore maggiore comune esteso



## <a name="output--bigintbigint"></a>Output: ([bigint](xref:microsoft.quantum.lang-ref.bigint),[bigint](xref:microsoft.quantum.lang-ref.bigint))

Tuple $ (u, v) $ con la proprietà $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $.

## <a name="references"></a>Riferimenti

- Questa implementazione è in base a https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm