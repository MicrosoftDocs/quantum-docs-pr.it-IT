---
uid: Microsoft.Quantum.Random.DrawCategorical
title: Operazione DrawCategorical
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawCategorical
qsharp.summary: Draws a random sample from a categorical distribution specified by a list of probablities.
ms.openlocfilehash: fdc5ae3a9341cb11e8fda129bdd030289b6c99c2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720282"
---
# <a name="drawcategorical-operation"></a><span data-ttu-id="e2ad6-102">Operazione DrawCategorical</span><span class="sxs-lookup"><span data-stu-id="e2ad6-102">DrawCategorical operation</span></span>

<span data-ttu-id="e2ad6-103">Spazio dei nomi: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="e2ad6-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="e2ad6-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e2ad6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e2ad6-105">Disegna un campione casuale da una distribuzione categorica specificata da un elenco di probablities.</span><span class="sxs-lookup"><span data-stu-id="e2ad6-105">Draws a random sample from a categorical distribution specified by a list of probablities.</span></span>

```qsharp
operation DrawCategorical (probs : Double[]) : Int
```


## <a name="description"></a><span data-ttu-id="e2ad6-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e2ad6-106">Description</span></span>

<span data-ttu-id="e2ad6-107">La probabilità di selezione di un indice specifico è proporzionale al valore dell'elemento di matrice in corrispondenza di tale indice.</span><span class="sxs-lookup"><span data-stu-id="e2ad6-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span>
<span data-ttu-id="e2ad6-108">Gli elementi della matrice uguali a zero vengono ignorati e i relativi indici non vengono mai restituiti.</span><span class="sxs-lookup"><span data-stu-id="e2ad6-108">Array elements that are equal to zero are ignored and their indices are never returned.</span></span> <span data-ttu-id="e2ad6-109">Se un elemento della matrice è minore di zero o se nessun elemento della matrice è maggiore di zero, l'operazione ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="e2ad6-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>

## <a name="input"></a><span data-ttu-id="e2ad6-110">Input</span><span class="sxs-lookup"><span data-stu-id="e2ad6-110">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="e2ad6-111">Probe: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="e2ad6-111">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="e2ad6-112">Matrice di numeri a virgola mobile proporzionale alla probabilità di selezione di ogni indice.</span><span class="sxs-lookup"><span data-stu-id="e2ad6-112">An array of floating-point numbers proportional to the probability of selecting each index.</span></span>



## <a name="output--int"></a><span data-ttu-id="e2ad6-113">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e2ad6-113">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e2ad6-114">Numero intero $i $ con probabilità $ \Pr (i) = p_i/\ sum_i p_i $, dove $p _i $ è l'elemento $i $ th di `probs` .</span><span class="sxs-lookup"><span data-stu-id="e2ad6-114">An integer $i$ with probability $\Pr(i) = p_i / \sum_i p_i$, where $p_i$ is the $i$th element of `probs`.</span></span>

## <a name="see-also"></a><span data-ttu-id="e2ad6-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2ad6-115">See Also</span></span>

- [<span data-ttu-id="e2ad6-116">Microsoft. Quantum. Random. CategoricalDistribution</span><span class="sxs-lookup"><span data-stu-id="e2ad6-116">Microsoft.Quantum.Random.CategoricalDistribution</span></span>](xref:Microsoft.Quantum.Random.CategoricalDistribution)