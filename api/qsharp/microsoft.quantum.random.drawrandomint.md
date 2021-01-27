---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: Operazione DrawRandomInt
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: ebed7f52b7c4a8c538ed9d718c486b5aa94a0327
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851130"
---
# <a name="drawrandomint-operation"></a><span data-ttu-id="ce53d-102">Operazione DrawRandomInt</span><span class="sxs-lookup"><span data-stu-id="ce53d-102">DrawRandomInt operation</span></span>

<span data-ttu-id="ce53d-103">Spazio dei nomi: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="ce53d-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="ce53d-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="ce53d-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="ce53d-105">Disegna un intero casuale in un intervallo inclusivo specificato.</span><span class="sxs-lookup"><span data-stu-id="ce53d-105">Draws a random integer in a given inclusive range.</span></span>

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a><span data-ttu-id="ce53d-106">Input</span><span class="sxs-lookup"><span data-stu-id="ce53d-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="ce53d-107">min: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ce53d-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ce53d-108">Integer più piccolo da disegnare.</span><span class="sxs-lookup"><span data-stu-id="ce53d-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="ce53d-109">Max: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ce53d-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ce53d-110">Integer più grande da disegnare.</span><span class="sxs-lookup"><span data-stu-id="ce53d-110">The largest integer to be drawn.</span></span>



## <a name="output--int"></a><span data-ttu-id="ce53d-111">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ce53d-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ce53d-112">Intero nell'intervallo inclusivo compreso tra `min` e `max` con probabilità uniforme.</span><span class="sxs-lookup"><span data-stu-id="ce53d-112">An integer in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="ce53d-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="ce53d-113">Example</span></span>

<span data-ttu-id="ce53d-114">Il seguente frammento Q # esegue in modo casuale un dado a sei lati:</span><span class="sxs-lookup"><span data-stu-id="ce53d-114">The following Q# snippet randomly rolls a six-sided die:</span></span>

```qsharp
let roll = DrawRandomInt(1, 6);
```

## <a name="remarks"></a><span data-ttu-id="ce53d-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="ce53d-115">Remarks</span></span>

<span data-ttu-id="ce53d-116">Ha esito negativo se `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="ce53d-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="ce53d-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce53d-117">See Also</span></span>

- [<span data-ttu-id="ce53d-118">Microsoft. Quantum. DiscreteUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="ce53d-118">Microsoft.Quantum.DiscreteUniformDistribution</span></span>](xref:Microsoft.Quantum.DiscreteUniformDistribution)