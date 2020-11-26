---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: DecomposedOn (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: 79f952e7bc7ba9f5337cf5e7a625e0d270a2e17a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203230"
---
# <a name="decomposedon-function"></a><span data-ttu-id="7ff75-102">DecomposedOn (funzione)</span><span class="sxs-lookup"><span data-stu-id="7ff75-102">DecomposedOn function</span></span>

<span data-ttu-id="7ff75-103">Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="7ff75-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="7ff75-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7ff75-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7ff75-105">Scompone una permutazione su una variabile</span><span class="sxs-lookup"><span data-stu-id="7ff75-105">Decomposes a permutation on a variable</span></span>

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a><span data-ttu-id="7ff75-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7ff75-106">Description</span></span>

<span data-ttu-id="7ff75-107">Data una permutazione $ \Pi $ ( `perm` ) e un indice $i $ ( `index` ), questo metodo restituisce tre permutazioni $ ((\ pi_l, \ pi_r), \Pi ') $ in modo tale che le immagini di $ \ pi_l $ e $ \ pi_r $ non modifichino i bit nei rispettivi elementi a indici diversi da $i $ e immagini di $ \Pi ' $ non cambiano bit $i $ nei relativi elementi.</span><span class="sxs-lookup"><span data-stu-id="7ff75-107">Given a permutation $\pi$ (`perm`) and an index $i$ (`index`), this method returns three permutations $((\pi_l, \pi_r), \pi')$ such that the images of $\pi_l$ and $\pi_r$ do not change bits in their elements at indexes other than $i$ and images of $\pi'$ do not change bit $i$ in their elements.</span></span>

## <a name="input"></a><span data-ttu-id="7ff75-108">Input</span><span class="sxs-lookup"><span data-stu-id="7ff75-108">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="7ff75-109">Perm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="7ff75-109">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="index--int"></a><span data-ttu-id="7ff75-110">Indice: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7ff75-110">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--intintint"></a><span data-ttu-id="7ff75-111">Output: (([int](xref:microsoft.quantum.lang-ref.int)[],[int](xref:microsoft.quantum.lang-ref.int)[]),[int](xref:microsoft.quantum.lang-ref.int)[])</span><span class="sxs-lookup"><span data-stu-id="7ff75-111">Output : (([Int](xref:microsoft.quantum.lang-ref.int)[],[Int](xref:microsoft.quantum.lang-ref.int)[]),[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>

