---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorI
title: ExtendedGreatestCommonDivisorI (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorI
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 8cb21ae5052ae6c5a8aed8be71d6bd3d32034272
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723723"
---
# <a name="extendedgreatestcommondivisori-function"></a>ExtendedGreatestCommonDivisorI (funzione)

Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pacchetto [](https://nuget.org/packages/)


Calcola una tupla $ (u, v) $ in modo che $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $, dove $ \operatorname{GCD} $ è $a $ massimo comune divisore di $a $ e $b $. Il MCD è sempre positivo.

```qsharp
function ExtendedGreatestCommonDivisorI (a : Int, b : Int) : (Int, Int)
```


## <a name="input"></a>Input

### <a name="a--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)

il primo numero di cui è in corso il calcolo del divisore più comune esteso


### <a name="b--int"></a>b: [int](xref:microsoft.quantum.lang-ref.int)

secondo numero di cui è in corso il calcolo del divisore maggiore comune esteso



## <a name="output--intint"></a>Output: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))

Tuple $ (u, v) $ con la proprietà $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $.

## <a name="references"></a>Riferimenti

- Questa implementazione è in base a https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm