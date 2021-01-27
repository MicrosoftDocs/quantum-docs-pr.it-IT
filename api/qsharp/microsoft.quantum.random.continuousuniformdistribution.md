---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: c81eb433f50277c677756ee70d916f4856260c6d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842323"
---
# <a name="continuousuniformdistribution-function"></a><span data-ttu-id="52338-102">ContinuousUniformDistribution (funzione)</span><span class="sxs-lookup"><span data-stu-id="52338-102">ContinuousUniformDistribution function</span></span>

<span data-ttu-id="52338-103">Spazio dei nomi: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="52338-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="52338-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="52338-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="52338-105">Restituisce una distribuzione uniforme in un intervallo inclusivo specificato.</span><span class="sxs-lookup"><span data-stu-id="52338-105">Returns a uniform distribution over a given inclusive interval.</span></span>

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="52338-106">Input</span><span class="sxs-lookup"><span data-stu-id="52338-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="52338-107">min: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="52338-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="52338-108">Numero reale più piccolo da disegnare.</span><span class="sxs-lookup"><span data-stu-id="52338-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="52338-109">numero massimo: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="52338-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="52338-110">Numero reale più grande da disegnare.</span><span class="sxs-lookup"><span data-stu-id="52338-110">The largest real number to be drawn.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="52338-111">Output: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="52338-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="52338-112">Una distribuzione le cui variabili casuali sono numeri reali nell'intervallo inclusivo da `min` a `max` con probabilità uniforme.</span><span class="sxs-lookup"><span data-stu-id="52338-112">A distribution whose random variates are real numbers in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="52338-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="52338-113">Example</span></span>

<span data-ttu-id="52338-114">Il seguente frammento Q # disegna in modo casuale un angolo compreso tra $0 $ e $2 \Pi $:</span><span class="sxs-lookup"><span data-stu-id="52338-114">The following Q# snippet randomly draws an angle between $0$ and $2 \pi$:</span></span>

```qsharp
let angleDistribution = ContinuousUniformDistribution(0.0, 2.0 * PI());
let angle = angleDistribution::Sample();
```

## <a name="remarks"></a><span data-ttu-id="52338-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="52338-115">Remarks</span></span>

<span data-ttu-id="52338-116">Ha esito negativo se `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="52338-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="52338-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52338-117">See Also</span></span>

- [<span data-ttu-id="52338-118">Microsoft. Quantum. DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="52338-118">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)