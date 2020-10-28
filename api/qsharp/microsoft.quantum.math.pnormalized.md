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
# <a name="pnormalized-function"></a><span data-ttu-id="33f1a-102">PNormalized (funzione)</span><span class="sxs-lookup"><span data-stu-id="33f1a-102">PNormalized function</span></span>

<span data-ttu-id="33f1a-103">Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="33f1a-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="33f1a-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="33f1a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="33f1a-105">Normalizza un vettore di `Double` nell'oggetto `L(p)` Norm.</span><span class="sxs-lookup"><span data-stu-id="33f1a-105">Normalizes a vector of `Double`s in the `L(p)` norm.</span></span>

<span data-ttu-id="33f1a-106">Ovvero, data una matrice $x $ di tipo `Double[]` , restituisce una matrice in cui tutti gli elementi sono divisi per la $p $-norm $ \| x \| _P $.</span><span class="sxs-lookup"><span data-stu-id="33f1a-106">That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.</span></span>

```qsharp
function PNormalized (p : Double, array : Double[]) : Double[]
```


## <a name="input"></a><span data-ttu-id="33f1a-107">Input</span><span class="sxs-lookup"><span data-stu-id="33f1a-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="33f1a-108">p: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="33f1a-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="33f1a-109">L'esponente $p $ nella $p $-Norm.</span><span class="sxs-lookup"><span data-stu-id="33f1a-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="33f1a-110">array: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="33f1a-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="33f1a-111">Output: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="33f1a-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="33f1a-112">La matrice $x $ normalizzata dalla $p $-norm $ \| x \| _P $.</span><span class="sxs-lookup"><span data-stu-id="33f1a-112">The array $x$ normalized by the $p$-norm $\|x\|_p$.</span></span>

## <a name="see-also"></a><span data-ttu-id="33f1a-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33f1a-113">See Also</span></span>

- [<span data-ttu-id="33f1a-114">Microsoft. Quantum. Math. PNorm</span><span class="sxs-lookup"><span data-stu-id="33f1a-114">Microsoft.Quantum.Math.PNorm</span></span>](xref:Microsoft.Quantum.Math.PNorm)