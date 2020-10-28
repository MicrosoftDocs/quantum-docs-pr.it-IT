---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: Funzione _SwapOrderToPermuteArray
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: 965f2f3d4f8b366abb27287ce0d27a3b7d7b8fb8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719490"
---
# <a name="_swapordertopermutearray-function"></a><span data-ttu-id="7002c-102">Funzione _SwapOrderToPermuteArray</span><span class="sxs-lookup"><span data-stu-id="7002c-102">_SwapOrderToPermuteArray function</span></span>

<span data-ttu-id="7002c-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="7002c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="7002c-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7002c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7002c-105">Restituisce gli elementi Order in una matrice devono essere scambiati per produrre una matrice ordinata.</span><span class="sxs-lookup"><span data-stu-id="7002c-105">Returns the order elements in an array need to be swapped to produce an ordered array.</span></span>
<span data-ttu-id="7002c-106">Presuppone che si verifichino scambi sul posto.</span><span class="sxs-lookup"><span data-stu-id="7002c-106">Assumes swaps occur in place.</span></span>

```qsharp
function _SwapOrderToPermuteArray (newOrder : Int[]) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="7002c-107">Input</span><span class="sxs-lookup"><span data-stu-id="7002c-107">Input</span></span>

### <a name="neworder--int"></a><span data-ttu-id="7002c-108">newOrder: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="7002c-108">newOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="7002c-109">Matrice con la permutazione degli indici della nuova matrice.</span><span class="sxs-lookup"><span data-stu-id="7002c-109">Array with the permutation of the indices of the new array.</span></span> <span data-ttu-id="7002c-110">Deve essere presente $n $ Elements, ognuno dei quali è un intero univoco compreso tra $0 $ e $n-$1.</span><span class="sxs-lookup"><span data-stu-id="7002c-110">There should be $n$ elements, each being a unique integer from $0$ to $n-1$.</span></span>



## <a name="output--intint"></a><span data-ttu-id="7002c-111">Output: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="7002c-111">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="7002c-112">La tupla rappresenta i due indici da scambiare.</span><span class="sxs-lookup"><span data-stu-id="7002c-112">The tuple represents the two indices to be swapped.</span></span> <span data-ttu-id="7002c-113">Gli scambi iniziano in corrispondenza dell'indice più basso.</span><span class="sxs-lookup"><span data-stu-id="7002c-113">The swaps begin at the lowest index.</span></span>

## <a name="remarks"></a><span data-ttu-id="7002c-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="7002c-114">Remarks</span></span>

## <a name="psuedocode"></a><span data-ttu-id="7002c-115">Psuedocode</span><span class="sxs-lookup"><span data-stu-id="7002c-115">Psuedocode</span></span>

<span data-ttu-id="7002c-116">per (index in 0.. length (newOrder)-1) {while newOrder [index]! = index {switch newOrder [index] with newOrder [newOrder [index]]}}</span><span class="sxs-lookup"><span data-stu-id="7002c-116">for (index in 0..Length(newOrder) - 1) { while newOrder[index] != index { Switch newOrder[index] with newOrder[newOrder[index]] } }</span></span>