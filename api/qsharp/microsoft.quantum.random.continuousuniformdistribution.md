---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: 74300efb10ba7b5aa006f0b1b6aafde0da840f00
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709428"
---
# <a name="continuousuniformdistribution-function"></a><span data-ttu-id="f0174-102">ContinuousUniformDistribution (funzione)</span><span class="sxs-lookup"><span data-stu-id="f0174-102">ContinuousUniformDistribution function</span></span>

<span data-ttu-id="f0174-103">Spazio dei nomi: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="f0174-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="f0174-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f0174-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f0174-105">Restituisce una distribuzione uniforme in un intervallo inclusivo specificato.</span><span class="sxs-lookup"><span data-stu-id="f0174-105">Returns a uniform distribution over a given inclusive interval.</span></span>

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="f0174-106">Input</span><span class="sxs-lookup"><span data-stu-id="f0174-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="f0174-107">min: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f0174-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f0174-108">Numero reale più piccolo da disegnare.</span><span class="sxs-lookup"><span data-stu-id="f0174-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="f0174-109">numero massimo: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f0174-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f0174-110">Numero reale più grande da disegnare.</span><span class="sxs-lookup"><span data-stu-id="f0174-110">The largest real number to be drawn.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="f0174-111">Output: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="f0174-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="f0174-112">Una distribuzione le cui variabili casuali sono numeri reali nell'intervallo inclusivo da `min` a `max` con probabilità uniforme.</span><span class="sxs-lookup"><span data-stu-id="f0174-112">A distribution whose random variates are real numbers in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="f0174-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="f0174-113">Remarks</span></span>

<span data-ttu-id="f0174-114">Ha esito negativo se `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="f0174-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="f0174-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0174-115">See Also</span></span>

- [<span data-ttu-id="f0174-116">Microsoft. Quantum. DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="f0174-116">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)