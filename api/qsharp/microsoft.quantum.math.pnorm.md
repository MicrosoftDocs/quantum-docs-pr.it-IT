---
uid: Microsoft.Quantum.Math.PNorm
title: PNorm (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNorm
qsharp.summary: >-
  Returns the `L(p)` norm of a vector of `Double`s.

  That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.
ms.openlocfilehash: 3fe029bd893fc4d11aaf351f7ea566256cac5a9e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194730"
---
# <a name="pnorm-function"></a><span data-ttu-id="aeb71-102">PNorm (funzione)</span><span class="sxs-lookup"><span data-stu-id="aeb71-102">PNorm function</span></span>

<span data-ttu-id="aeb71-103">Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="aeb71-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="aeb71-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="aeb71-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="aeb71-105">Restituisce la `L(p)` norma di un vettore di `Double` s.</span><span class="sxs-lookup"><span data-stu-id="aeb71-105">Returns the `L(p)` norm of a vector of `Double`s.</span></span>

<span data-ttu-id="aeb71-106">Ovvero, data una matrice $x $ di tipo `Double[]` , restituisce l'$p $-norm $ \| x \| \_ p = (\ Sum_ {j} | x_j | ^ {p}) ^ {1/p} $.</span><span class="sxs-lookup"><span data-stu-id="aeb71-106">That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.</span></span>

```qsharp
function PNorm (p : Double, array : Double[]) : Double
```


## <a name="input"></a><span data-ttu-id="aeb71-107">Input</span><span class="sxs-lookup"><span data-stu-id="aeb71-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="aeb71-108">p: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="aeb71-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="aeb71-109">L'esponente $p $ nella $p $-Norm.</span><span class="sxs-lookup"><span data-stu-id="aeb71-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="aeb71-110">array: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="aeb71-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="aeb71-111">Output: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="aeb71-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="aeb71-112">Il $p $-norm $ \| x \| _P $.</span><span class="sxs-lookup"><span data-stu-id="aeb71-112">The $p$-norm $\|x\|_p$.</span></span>