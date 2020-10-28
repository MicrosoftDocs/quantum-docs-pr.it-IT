---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: Operazione DrawRandomInt
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: d9d8d9fbb25587ac5ccbd4edf0e555649380375f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724661"
---
# <a name="drawrandomint-operation"></a><span data-ttu-id="3445c-102">Operazione DrawRandomInt</span><span class="sxs-lookup"><span data-stu-id="3445c-102">DrawRandomInt operation</span></span>

<span data-ttu-id="3445c-103">Spazio dei nomi: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="3445c-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="3445c-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3445c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3445c-105">Disegna un intero casuale in un intervallo inclusivo specificato.</span><span class="sxs-lookup"><span data-stu-id="3445c-105">Draws a random integer in a given inclusive range.</span></span>

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a><span data-ttu-id="3445c-106">Input</span><span class="sxs-lookup"><span data-stu-id="3445c-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="3445c-107">min: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3445c-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3445c-108">Integer più piccolo da disegnare.</span><span class="sxs-lookup"><span data-stu-id="3445c-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="3445c-109">Max: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3445c-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3445c-110">Integer più grande da disegnare.</span><span class="sxs-lookup"><span data-stu-id="3445c-110">The largest integer to be drawn.</span></span>



## <a name="output--int"></a><span data-ttu-id="3445c-111">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3445c-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3445c-112">Intero nell'intervallo inclusivo compreso tra `min` e `max` con probabilità uniforme.</span><span class="sxs-lookup"><span data-stu-id="3445c-112">An integer in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="3445c-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="3445c-113">Remarks</span></span>

<span data-ttu-id="3445c-114">Ha esito negativo se `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="3445c-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="3445c-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3445c-115">See Also</span></span>

- [<span data-ttu-id="3445c-116">Microsoft. Quantum. DiscreteUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="3445c-116">Microsoft.Quantum.DiscreteUniformDistribution</span></span>](xref:Microsoft.Quantum.DiscreteUniformDistribution)