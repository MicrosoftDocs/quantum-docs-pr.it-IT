---
uid: Microsoft.Quantum.Math.PNormalized
title: PNormalized (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: 196bdab67528aa8672a010ac3830459e27276ce9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227523"
---
# <a name="pnormalized-function"></a><span data-ttu-id="d910f-102">PNormalized (funzione)</span><span class="sxs-lookup"><span data-stu-id="d910f-102">PNormalized function</span></span>

<span data-ttu-id="d910f-103">Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="d910f-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="d910f-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d910f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d910f-105">Normalizza un vettore di `Double` nell'oggetto `L(p)` Norm.</span><span class="sxs-lookup"><span data-stu-id="d910f-105">Normalizes a vector of `Double`s in the `L(p)` norm.</span></span>

<span data-ttu-id="d910f-106">Ovvero, data una matrice $x $ di tipo `Double[]` , restituisce una matrice in cui tutti gli elementi sono divisi per la $p $-norm $ \| x \| _P $.</span><span class="sxs-lookup"><span data-stu-id="d910f-106">That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.</span></span>

```qsharp
function PNormalized (p : Double, array : Double[]) : Double[]
```


## <a name="input"></a><span data-ttu-id="d910f-107">Input</span><span class="sxs-lookup"><span data-stu-id="d910f-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="d910f-108">p: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d910f-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d910f-109">L'esponente $p $ nella $p $-Norm.</span><span class="sxs-lookup"><span data-stu-id="d910f-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="d910f-110">array: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="d910f-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="d910f-111">Output: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="d910f-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="d910f-112">La matrice $x $ normalizzata dalla $p $-norm $ \| x \| _P $.</span><span class="sxs-lookup"><span data-stu-id="d910f-112">The array $x$ normalized by the $p$-norm $\|x\|_p$.</span></span>

## <a name="see-also"></a><span data-ttu-id="d910f-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d910f-113">See Also</span></span>

- [<span data-ttu-id="d910f-114">Microsoft. Quantum. Math. PNorm</span><span class="sxs-lookup"><span data-stu-id="d910f-114">Microsoft.Quantum.Math.PNorm</span></span>](xref:Microsoft.Quantum.Math.PNorm)