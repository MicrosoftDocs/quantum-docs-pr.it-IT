---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: Operazione DrawRandomInt
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: f7b6cb75f761e4c45295245ed4bd4fb82c592809
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192911"
---
# <a name="drawrandomint-operation"></a><span data-ttu-id="a58f9-102">Operazione DrawRandomInt</span><span class="sxs-lookup"><span data-stu-id="a58f9-102">DrawRandomInt operation</span></span>

<span data-ttu-id="a58f9-103">Spazio dei nomi: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="a58f9-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="a58f9-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a58f9-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="a58f9-105">Disegna un intero casuale in un intervallo inclusivo specificato.</span><span class="sxs-lookup"><span data-stu-id="a58f9-105">Draws a random integer in a given inclusive range.</span></span>

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a><span data-ttu-id="a58f9-106">Input</span><span class="sxs-lookup"><span data-stu-id="a58f9-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="a58f9-107">min: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a58f9-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a58f9-108">Integer più piccolo da disegnare.</span><span class="sxs-lookup"><span data-stu-id="a58f9-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="a58f9-109">Max: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a58f9-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a58f9-110">Integer più grande da disegnare.</span><span class="sxs-lookup"><span data-stu-id="a58f9-110">The largest integer to be drawn.</span></span>



## <a name="output--int"></a><span data-ttu-id="a58f9-111">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a58f9-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a58f9-112">Intero nell'intervallo inclusivo compreso tra `min` e `max` con probabilità uniforme.</span><span class="sxs-lookup"><span data-stu-id="a58f9-112">An integer in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="a58f9-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a58f9-113">Remarks</span></span>

<span data-ttu-id="a58f9-114">Ha esito negativo se `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="a58f9-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="a58f9-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a58f9-115">See Also</span></span>

- [<span data-ttu-id="a58f9-116">Microsoft. Quantum. DiscreteUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="a58f9-116">Microsoft.Quantum.DiscreteUniformDistribution</span></span>](xref:Microsoft.Quantum.DiscreteUniformDistribution)