---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 756e9e95cac5554ab8f885dab7c47ac1b174c0f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722816"
---
# <a name="categoricaldistribution-function"></a><span data-ttu-id="b2c49-102">CategoricalDistribution (funzione)</span><span class="sxs-lookup"><span data-stu-id="b2c49-102">CategoricalDistribution function</span></span>

<span data-ttu-id="b2c49-103">Spazio dei nomi: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="b2c49-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="b2c49-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b2c49-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b2c49-105">Restituisce una distribuzione categorica discreta, in cui viene specificata in modo esplicito la probabilità per ogni elenco finito di risultati specificati.</span><span class="sxs-lookup"><span data-stu-id="b2c49-105">Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.</span></span>

```qsharp
function CategoricalDistribution (probs : Double[]) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="b2c49-106">Input</span><span class="sxs-lookup"><span data-stu-id="b2c49-106">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="b2c49-107">Probe: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="b2c49-107">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="b2c49-108">Probabilità per ogni risultato della distribuzione categorica.</span><span class="sxs-lookup"><span data-stu-id="b2c49-108">The probabilities for each outcome from the categorical distribution.</span></span>
<span data-ttu-id="b2c49-109">Queste probabilità potrebbero non essere normalizzate, ma devono essere tutte non negative.</span><span class="sxs-lookup"><span data-stu-id="b2c49-109">These probabilities may not be normalized, but must all be non-negative.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="b2c49-110">Output: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="b2c49-110">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="b2c49-111">Indice `i` con probabilità `probs[i] / sum` , dove `sum` è la somma di `probs` specificata da `Fold(PlusD, 0.0, probs)` .</span><span class="sxs-lookup"><span data-stu-id="b2c49-111">The index `i` with probability `probs[i] / sum`, where `sum` is the sum of `probs` given by `Fold(PlusD, 0.0, probs)`.</span></span>