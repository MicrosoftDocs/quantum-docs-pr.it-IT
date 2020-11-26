---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianProduct
title: Operazione IterateThroughCartesianProduct
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianProduct
qsharp.summary: Applies an operation for each index in the Cartesian product of several ranges.
ms.openlocfilehash: 6340c7a972253e6f583a3856df93a7066ced3139
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206443"
---
# <a name="iteratethroughcartesianproduct-operation"></a><span data-ttu-id="ff689-102">Operazione IterateThroughCartesianProduct</span><span class="sxs-lookup"><span data-stu-id="ff689-102">IterateThroughCartesianProduct operation</span></span>

<span data-ttu-id="ff689-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ff689-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ff689-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ff689-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ff689-105">Applica un'operazione per ogni indice nel prodotto cartesiano di diversi intervalli.</span><span class="sxs-lookup"><span data-stu-id="ff689-105">Applies an operation for each index in the Cartesian product of several ranges.</span></span>

```qsharp
operation IterateThroughCartesianProduct (bounds : Int[], op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="ff689-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ff689-106">Description</span></span>

<span data-ttu-id="ff689-107">Applica in modo iterativo un'operazione per ogni elemento del prodotto cartesiano di `0..(bounds[0] - 1)` , `0..(bounds[1] - 1)` ,..., `0..(bounds[Length(bounds) - 1] - 1)`</span><span class="sxs-lookup"><span data-stu-id="ff689-107">Iteratively applies an operation for each element of the Cartesian product of `0..(bounds[0] - 1)`, `0..(bounds[1] - 1)`, ..., `0..(bounds[Length(bounds) - 1] - 1)`</span></span>

## <a name="input"></a><span data-ttu-id="ff689-108">Input</span><span class="sxs-lookup"><span data-stu-id="ff689-108">Input</span></span>

### <a name="bounds--int"></a><span data-ttu-id="ff689-109">limiti: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ff689-109">bounds : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="ff689-110">Matrice che specifica gli intervalli di cui eseguire l'iterazione, con ogni intervallo specificato come lunghezza intera.</span><span class="sxs-lookup"><span data-stu-id="ff689-110">An array specifying the ranges to be iterated over, with each range being specified as an integer length.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="ff689-111">op: [int](xref:microsoft.quantum.lang-ref.int)[] = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="ff689-111">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="ff689-112">Operazione da chiamare per ogni elemento del prodotto cartesiano specificato.</span><span class="sxs-lookup"><span data-stu-id="ff689-112">An operation to be called for each element of the given Cartesian product.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ff689-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ff689-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="ff689-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff689-114">See Also</span></span>

- [<span data-ttu-id="ff689-115">Microsoft. Quantum. Canon. IterateThroughCartesianPower</span><span class="sxs-lookup"><span data-stu-id="ff689-115">Microsoft.Quantum.Canon.IterateThroughCartesianPower</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower)