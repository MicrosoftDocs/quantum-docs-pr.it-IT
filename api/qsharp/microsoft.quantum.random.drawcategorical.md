---
uid: Microsoft.Quantum.Random.DrawCategorical
title: Operazione DrawCategorical
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawCategorical
qsharp.summary: Draws a random sample from a categorical distribution specified by a list of probablities.
ms.openlocfilehash: a5826aa5f658fea766db0ca5ccbb9c0d7d056d4c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192996"
---
# <a name="drawcategorical-operation"></a><span data-ttu-id="b59f0-102">Operazione DrawCategorical</span><span class="sxs-lookup"><span data-stu-id="b59f0-102">DrawCategorical operation</span></span>

<span data-ttu-id="b59f0-103">Spazio dei nomi: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="b59f0-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="b59f0-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="b59f0-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="b59f0-105">Disegna un campione casuale da una distribuzione categorica specificata da un elenco di probablities.</span><span class="sxs-lookup"><span data-stu-id="b59f0-105">Draws a random sample from a categorical distribution specified by a list of probablities.</span></span>

```qsharp
operation DrawCategorical (probs : Double[]) : Int
```


## <a name="description"></a><span data-ttu-id="b59f0-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b59f0-106">Description</span></span>

<span data-ttu-id="b59f0-107">La probabilità di selezione di un indice specifico è proporzionale al valore dell'elemento di matrice in corrispondenza di tale indice.</span><span class="sxs-lookup"><span data-stu-id="b59f0-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span>
<span data-ttu-id="b59f0-108">Gli elementi della matrice uguali a zero vengono ignorati e i relativi indici non vengono mai restituiti.</span><span class="sxs-lookup"><span data-stu-id="b59f0-108">Array elements that are equal to zero are ignored and their indices are never returned.</span></span> <span data-ttu-id="b59f0-109">Se un elemento della matrice è minore di zero o se nessun elemento della matrice è maggiore di zero, l'operazione ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="b59f0-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>

## <a name="input"></a><span data-ttu-id="b59f0-110">Input</span><span class="sxs-lookup"><span data-stu-id="b59f0-110">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="b59f0-111">Probe: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="b59f0-111">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="b59f0-112">Matrice di numeri a virgola mobile proporzionale alla probabilità di selezione di ogni indice.</span><span class="sxs-lookup"><span data-stu-id="b59f0-112">An array of floating-point numbers proportional to the probability of selecting each index.</span></span>



## <a name="output--int"></a><span data-ttu-id="b59f0-113">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b59f0-113">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b59f0-114">Numero intero $i $ con probabilità $ \Pr (i) = p_i/\ sum_i p_i $, dove $p _i $ è l'elemento $i $ th di `probs` .</span><span class="sxs-lookup"><span data-stu-id="b59f0-114">An integer $i$ with probability $\Pr(i) = p_i / \sum_i p_i$, where $p_i$ is the $i$th element of `probs`.</span></span>

## <a name="see-also"></a><span data-ttu-id="b59f0-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b59f0-115">See Also</span></span>

- [<span data-ttu-id="b59f0-116">Microsoft. Quantum. Random. CategoricalDistribution</span><span class="sxs-lookup"><span data-stu-id="b59f0-116">Microsoft.Quantum.Random.CategoricalDistribution</span></span>](xref:Microsoft.Quantum.Random.CategoricalDistribution)