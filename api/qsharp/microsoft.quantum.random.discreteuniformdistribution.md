---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: f909e7def5439ec0feef4ca4dc0cf8ed12374dfe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853728"
---
# <a name="discreteuniformdistribution-function"></a><span data-ttu-id="74af6-102">DiscreteUniformDistribution (funzione)</span><span class="sxs-lookup"><span data-stu-id="74af6-102">DiscreteUniformDistribution function</span></span>

<span data-ttu-id="74af6-103">Spazio dei nomi: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="74af6-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="74af6-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="74af6-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="74af6-105">Restituisce una distribuzione uniforme in un intervallo inclusivo specificato.</span><span class="sxs-lookup"><span data-stu-id="74af6-105">Returns a uniform distribution over a given inclusive range.</span></span>

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="74af6-106">Input</span><span class="sxs-lookup"><span data-stu-id="74af6-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="74af6-107">min: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="74af6-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="74af6-108">Integer più piccolo da disegnare.</span><span class="sxs-lookup"><span data-stu-id="74af6-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="74af6-109">Max: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="74af6-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="74af6-110">Integer più grande da disegnare.</span><span class="sxs-lookup"><span data-stu-id="74af6-110">The largest integer to be drawn.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="74af6-111">Output: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="74af6-111">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="74af6-112">Una distribuzione le cui variabili casuali sono numeri interi nell'intervallo inclusivo da `min` a `max` con probabilità uniforme.</span><span class="sxs-lookup"><span data-stu-id="74af6-112">A distribution whose random variates are integers in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="74af6-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="74af6-113">Example</span></span>

<span data-ttu-id="74af6-114">Il seguente frammento Q # esegue in modo casuale un dado a sei lati:</span><span class="sxs-lookup"><span data-stu-id="74af6-114">The following Q# snippet randomly rolls a six-sided die:</span></span>

```qsharp
let dieDistribution = DiscreteUniformDistribution(1, 6);
let dieRoll = dieDistribution::Sample();
```

## <a name="remarks"></a><span data-ttu-id="74af6-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="74af6-115">Remarks</span></span>

<span data-ttu-id="74af6-116">Ha esito negativo se `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="74af6-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="74af6-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74af6-117">See Also</span></span>

- [<span data-ttu-id="74af6-118">Microsoft. Quantum. DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="74af6-118">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)