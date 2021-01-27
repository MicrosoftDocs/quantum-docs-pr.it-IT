---
uid: Microsoft.Quantum.Math.PNormalized
title: PNormalized (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: ea6a88d07d3b246f666b793f0b10ab6598ea4ff6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854840"
---
# <a name="pnormalized-function"></a><span data-ttu-id="d2ed3-102">PNormalized (funzione)</span><span class="sxs-lookup"><span data-stu-id="d2ed3-102">PNormalized function</span></span>

<span data-ttu-id="d2ed3-103">Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="d2ed3-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="d2ed3-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d2ed3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d2ed3-105">Normalizza un vettore di `Double` nell'oggetto `L(p)` Norm.</span><span class="sxs-lookup"><span data-stu-id="d2ed3-105">Normalizes a vector of `Double`s in the `L(p)` norm.</span></span>

<span data-ttu-id="d2ed3-106">Ovvero, data una matrice $x $ di tipo `Double[]` , restituisce una matrice in cui tutti gli elementi sono divisi per la $p $-norm $ \| x \| _P $.</span><span class="sxs-lookup"><span data-stu-id="d2ed3-106">That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.</span></span>

```qsharp
function PNormalized (p : Double, array : Double[]) : Double[]
```


## <a name="input"></a><span data-ttu-id="d2ed3-107">Input</span><span class="sxs-lookup"><span data-stu-id="d2ed3-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="d2ed3-108">p: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d2ed3-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d2ed3-109">L'esponente $p $ nella $p $-Norm.</span><span class="sxs-lookup"><span data-stu-id="d2ed3-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="d2ed3-110">array: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="d2ed3-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="d2ed3-111">Output: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="d2ed3-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="d2ed3-112">La matrice $x $ normalizzata dalla $p $-norm $ \| x \| _P $.</span><span class="sxs-lookup"><span data-stu-id="d2ed3-112">The array $x$ normalized by the $p$-norm $\|x\|_p$.</span></span>

## <a name="see-also"></a><span data-ttu-id="d2ed3-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2ed3-113">See Also</span></span>

- [<span data-ttu-id="d2ed3-114">Microsoft. Quantum. Math. PNorm</span><span class="sxs-lookup"><span data-stu-id="d2ed3-114">Microsoft.Quantum.Math.PNorm</span></span>](xref:Microsoft.Quantum.Math.PNorm)