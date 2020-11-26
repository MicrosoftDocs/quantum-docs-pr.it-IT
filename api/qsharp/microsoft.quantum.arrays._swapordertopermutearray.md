---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: Funzione _SwapOrderToPermuteArray
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: 9df2ec00d91c1124fae960efd15d576b15b0223c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221709"
---
# <a name="_swapordertopermutearray-function"></a><span data-ttu-id="8d83e-102">Funzione _SwapOrderToPermuteArray</span><span class="sxs-lookup"><span data-stu-id="8d83e-102">_SwapOrderToPermuteArray function</span></span>

<span data-ttu-id="8d83e-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="8d83e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="8d83e-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8d83e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8d83e-105">Restituisce gli elementi Order in una matrice devono essere scambiati per produrre una matrice ordinata.</span><span class="sxs-lookup"><span data-stu-id="8d83e-105">Returns the order elements in an array need to be swapped to produce an ordered array.</span></span>
<span data-ttu-id="8d83e-106">Presuppone che si verifichino scambi sul posto.</span><span class="sxs-lookup"><span data-stu-id="8d83e-106">Assumes swaps occur in place.</span></span>

```qsharp
function _SwapOrderToPermuteArray (newOrder : Int[]) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="8d83e-107">Input</span><span class="sxs-lookup"><span data-stu-id="8d83e-107">Input</span></span>

### <a name="neworder--int"></a><span data-ttu-id="8d83e-108">newOrder: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="8d83e-108">newOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="8d83e-109">Matrice con la permutazione degli indici della nuova matrice.</span><span class="sxs-lookup"><span data-stu-id="8d83e-109">Array with the permutation of the indices of the new array.</span></span> <span data-ttu-id="8d83e-110">Deve essere presente $n $ Elements, ognuno dei quali è un intero univoco compreso tra $0 $ e $n-$1.</span><span class="sxs-lookup"><span data-stu-id="8d83e-110">There should be $n$ elements, each being a unique integer from $0$ to $n-1$.</span></span>



## <a name="output--intint"></a><span data-ttu-id="8d83e-111">Output: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="8d83e-111">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="8d83e-112">La tupla rappresenta i due indici da scambiare.</span><span class="sxs-lookup"><span data-stu-id="8d83e-112">The tuple represents the two indices to be swapped.</span></span> <span data-ttu-id="8d83e-113">Gli scambi iniziano in corrispondenza dell'indice più basso.</span><span class="sxs-lookup"><span data-stu-id="8d83e-113">The swaps begin at the lowest index.</span></span>

## <a name="remarks"></a><span data-ttu-id="8d83e-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="8d83e-114">Remarks</span></span>

## <a name="psuedocode"></a><span data-ttu-id="8d83e-115">Psuedocode</span><span class="sxs-lookup"><span data-stu-id="8d83e-115">Psuedocode</span></span>

<span data-ttu-id="8d83e-116">per (index in 0.. length (newOrder)-1) {while newOrder [index]! = index {switch newOrder [index] with newOrder [newOrder [index]]}}</span><span class="sxs-lookup"><span data-stu-id="8d83e-116">for (index in 0..Length(newOrder) - 1) { while newOrder[index] != index { Switch newOrder[index] with newOrder[newOrder[index]] } }</span></span>