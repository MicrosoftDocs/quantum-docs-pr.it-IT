---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: Operazione DrawRandomDouble
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: 792e9c714b761b48618aec2091e167a359c2b522
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847616"
---
# <a name="drawrandomdouble-operation"></a><span data-ttu-id="8fd19-102">Operazione DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="8fd19-102">DrawRandomDouble operation</span></span>

<span data-ttu-id="8fd19-103">Spazio dei nomi: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="8fd19-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="8fd19-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="8fd19-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="8fd19-105">Disegna un numero reale casuale in un intervallo inclusivo specificato.</span><span class="sxs-lookup"><span data-stu-id="8fd19-105">Draws a random real number in a given inclusive interval.</span></span>

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a><span data-ttu-id="8fd19-106">Input</span><span class="sxs-lookup"><span data-stu-id="8fd19-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="8fd19-107">min: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8fd19-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8fd19-108">Numero reale più piccolo da disegnare.</span><span class="sxs-lookup"><span data-stu-id="8fd19-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="8fd19-109">numero massimo: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8fd19-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8fd19-110">Numero reale più grande da disegnare.</span><span class="sxs-lookup"><span data-stu-id="8fd19-110">The largest real number to be drawn.</span></span>



## <a name="output--double"></a><span data-ttu-id="8fd19-111">Output: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8fd19-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8fd19-112">Numero reale casuale nell'intervallo inclusivo compreso tra `min` e `max` con probabilità uniforme.</span><span class="sxs-lookup"><span data-stu-id="8fd19-112">A random real number in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="8fd19-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="8fd19-113">Example</span></span>

<span data-ttu-id="8fd19-114">Il seguente frammento Q # disegna in modo casuale un angolo compreso tra $0 $ e $2 \Pi $:</span><span class="sxs-lookup"><span data-stu-id="8fd19-114">The following Q# snippet randomly draws an angle between $0$ and $2 \pi$:</span></span>

```qsharp
let angle = DrawRandomDouble(0.0, 2.0 * PI());
```

## <a name="remarks"></a><span data-ttu-id="8fd19-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="8fd19-115">Remarks</span></span>

<span data-ttu-id="8fd19-116">Ha esito negativo se `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="8fd19-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="8fd19-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8fd19-117">See Also</span></span>

- [<span data-ttu-id="8fd19-118">Microsoft. Quantum. ContinuousUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="8fd19-118">Microsoft.Quantum.ContinuousUniformDistribution</span></span>](xref:Microsoft.Quantum.ContinuousUniformDistribution)