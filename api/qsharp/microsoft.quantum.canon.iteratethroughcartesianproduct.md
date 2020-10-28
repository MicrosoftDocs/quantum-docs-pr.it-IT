---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianProduct
title: Operazione IterateThroughCartesianProduct
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianProduct
qsharp.summary: Applies an operation for each index in the Cartesian product of several ranges.
ms.openlocfilehash: e4fc71f6f707639f6f89eece8546ec2fb434a15a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716036"
---
# <a name="iteratethroughcartesianproduct-operation"></a><span data-ttu-id="35715-102">Operazione IterateThroughCartesianProduct</span><span class="sxs-lookup"><span data-stu-id="35715-102">IterateThroughCartesianProduct operation</span></span>

<span data-ttu-id="35715-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="35715-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="35715-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="35715-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="35715-105">Applica un'operazione per ogni indice nel prodotto cartesiano di diversi intervalli.</span><span class="sxs-lookup"><span data-stu-id="35715-105">Applies an operation for each index in the Cartesian product of several ranges.</span></span>

```qsharp
operation IterateThroughCartesianProduct (bounds : Int[], op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="35715-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="35715-106">Description</span></span>

<span data-ttu-id="35715-107">Applica in modo iterativo un'operazione per ogni elemento del prodotto cartesiano di `0..(bounds[0] - 1)` , `0..(bounds[1] - 1)` ,..., `0..(bounds[Length(bounds) - 1] - 1)`</span><span class="sxs-lookup"><span data-stu-id="35715-107">Iteratively applies an operation for each element of the Cartesian product of `0..(bounds[0] - 1)`, `0..(bounds[1] - 1)`, ..., `0..(bounds[Length(bounds) - 1] - 1)`</span></span>

## <a name="input"></a><span data-ttu-id="35715-108">Input</span><span class="sxs-lookup"><span data-stu-id="35715-108">Input</span></span>

### <a name="bounds--int"></a><span data-ttu-id="35715-109">limiti: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="35715-109">bounds : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="35715-110">Matrice che specifica gli intervalli di cui eseguire l'iterazione, con ogni intervallo specificato come lunghezza intera.</span><span class="sxs-lookup"><span data-stu-id="35715-110">An array specifying the ranges to be iterated over, with each range being specified as an integer length.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="35715-111">op: [int](xref:microsoft.quantum.lang-ref.int)[] = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="35715-111">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="35715-112">Operazione da chiamare per ogni elemento del prodotto cartesiano specificato.</span><span class="sxs-lookup"><span data-stu-id="35715-112">An operation to be called for each element of the given Cartesian product.</span></span>



## <a name="output--unit"></a><span data-ttu-id="35715-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="35715-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="35715-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35715-114">See Also</span></span>

- [<span data-ttu-id="35715-115">Microsoft. Quantum. Canon. IterateThroughCartesianPower</span><span class="sxs-lookup"><span data-stu-id="35715-115">Microsoft.Quantum.Canon.IterateThroughCartesianPower</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower)