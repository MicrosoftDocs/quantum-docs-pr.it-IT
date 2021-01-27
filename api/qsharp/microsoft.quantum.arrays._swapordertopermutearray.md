---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: Funzione _SwapOrderToPermuteArray
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: ff8e4e23dde7d69f93054a275548ded49d5b0bfb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846300"
---
# <a name="_swapordertopermutearray-function"></a><span data-ttu-id="39898-102">Funzione _SwapOrderToPermuteArray</span><span class="sxs-lookup"><span data-stu-id="39898-102">_SwapOrderToPermuteArray function</span></span>

<span data-ttu-id="39898-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="39898-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="39898-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="39898-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="39898-105">Restituisce gli elementi Order in una matrice devono essere scambiati per produrre una matrice ordinata.</span><span class="sxs-lookup"><span data-stu-id="39898-105">Returns the order elements in an array need to be swapped to produce an ordered array.</span></span>
<span data-ttu-id="39898-106">Presuppone che si verifichino scambi sul posto.</span><span class="sxs-lookup"><span data-stu-id="39898-106">Assumes swaps occur in place.</span></span>

```qsharp
function _SwapOrderToPermuteArray (newOrder : Int[]) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="39898-107">Input</span><span class="sxs-lookup"><span data-stu-id="39898-107">Input</span></span>

### <a name="neworder--int"></a><span data-ttu-id="39898-108">newOrder: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="39898-108">newOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="39898-109">Matrice con la permutazione degli indici della nuova matrice.</span><span class="sxs-lookup"><span data-stu-id="39898-109">Array with the permutation of the indices of the new array.</span></span> <span data-ttu-id="39898-110">Deve essere presente $n $ Elements, ognuno dei quali è un intero univoco compreso tra $0 $ e $n-$1.</span><span class="sxs-lookup"><span data-stu-id="39898-110">There should be $n$ elements, each being a unique integer from $0$ to $n-1$.</span></span>



## <a name="output--intint"></a><span data-ttu-id="39898-111">Output: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="39898-111">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="39898-112">La tupla rappresenta i due indici da scambiare.</span><span class="sxs-lookup"><span data-stu-id="39898-112">The tuple represents the two indices to be swapped.</span></span> <span data-ttu-id="39898-113">Gli scambi iniziano in corrispondenza dell'indice più basso.</span><span class="sxs-lookup"><span data-stu-id="39898-113">The swaps begin at the lowest index.</span></span>

## <a name="example"></a><span data-ttu-id="39898-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="39898-114">Example</span></span>

```qsharp
// The following returns [(0, 5),(0, 4),(0, 1),(0, 3)];
let swapOrder = _SwapOrderToPermuteArray([5, 3, 2, 0, 1, 4]);
```

## <a name="remarks"></a><span data-ttu-id="39898-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="39898-115">Remarks</span></span>

## <a name="psuedocode"></a><span data-ttu-id="39898-116">Psuedocode</span><span class="sxs-lookup"><span data-stu-id="39898-116">Psuedocode</span></span>

<span data-ttu-id="39898-117">per (index in 0.. length (newOrder)-1) {while newOrder [index]! = index {switch newOrder [index] with newOrder [newOrder [index]]}}</span><span class="sxs-lookup"><span data-stu-id="39898-117">for (index in 0..Length(newOrder) - 1) { while newOrder[index] != index { Switch newOrder[index] with newOrder[newOrder[index]] } }</span></span>