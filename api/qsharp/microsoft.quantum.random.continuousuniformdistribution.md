---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: a3911fe9962ce18daa239de0272c53d83344134a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193081"
---
# <a name="continuousuniformdistribution-function"></a><span data-ttu-id="b7103-102">ContinuousUniformDistribution (funzione)</span><span class="sxs-lookup"><span data-stu-id="b7103-102">ContinuousUniformDistribution function</span></span>

<span data-ttu-id="b7103-103">Spazio dei nomi: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="b7103-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="b7103-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="b7103-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="b7103-105">Restituisce una distribuzione uniforme in un intervallo inclusivo specificato.</span><span class="sxs-lookup"><span data-stu-id="b7103-105">Returns a uniform distribution over a given inclusive interval.</span></span>

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="b7103-106">Input</span><span class="sxs-lookup"><span data-stu-id="b7103-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="b7103-107">min: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b7103-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b7103-108">Numero reale più piccolo da disegnare.</span><span class="sxs-lookup"><span data-stu-id="b7103-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="b7103-109">numero massimo: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b7103-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b7103-110">Numero reale più grande da disegnare.</span><span class="sxs-lookup"><span data-stu-id="b7103-110">The largest real number to be drawn.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="b7103-111">Output: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="b7103-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="b7103-112">Una distribuzione le cui variabili casuali sono numeri reali nell'intervallo inclusivo da `min` a `max` con probabilità uniforme.</span><span class="sxs-lookup"><span data-stu-id="b7103-112">A distribution whose random variates are real numbers in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="b7103-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b7103-113">Remarks</span></span>

<span data-ttu-id="b7103-114">Ha esito negativo se `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="b7103-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="b7103-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7103-115">See Also</span></span>

- [<span data-ttu-id="b7103-116">Microsoft. Quantum. DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="b7103-116">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)