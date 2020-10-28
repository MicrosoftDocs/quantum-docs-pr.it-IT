---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOps
title: Operazione ApplySeriesOfOps
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOps
qsharp.summary: Applies a list of ops and their targets sequentially on an array.
ms.openlocfilehash: aff0bcb831960153166e88aef1f05e000125d5d8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717671"
---
# <a name="applyseriesofops-operation"></a><span data-ttu-id="6e2ff-102">Operazione ApplySeriesOfOps</span><span class="sxs-lookup"><span data-stu-id="6e2ff-102">ApplySeriesOfOps operation</span></span>

<span data-ttu-id="6e2ff-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6e2ff-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6e2ff-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6e2ff-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6e2ff-105">Applica in sequenza un elenco di Ops e le relative destinazioni in una matrice.</span><span class="sxs-lookup"><span data-stu-id="6e2ff-105">Applies a list of ops and their targets sequentially on an array.</span></span>

```qsharp
operation ApplySeriesOfOps<'T> (listOfOps : ('T[] => Unit)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="6e2ff-106">Input</span><span class="sxs-lookup"><span data-stu-id="6e2ff-106">Input</span></span>

### <a name="listofops--t--unit-"></a><span data-ttu-id="6e2ff-107">listOfOps:' t [] => [unità](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="6e2ff-107">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="6e2ff-108">Elenco di operazioni, ciascuna delle quali accetta una matrice t, da applicare.</span><span class="sxs-lookup"><span data-stu-id="6e2ff-108">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="6e2ff-109">Vengono applicati in sequenza, l'indice più basso.</span><span class="sxs-lookup"><span data-stu-id="6e2ff-109">They are applied sequentially, lowest index first.</span></span>


### <a name="targets--int"></a><span data-ttu-id="6e2ff-110">destinazioni: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="6e2ff-110">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="6e2ff-111">Matrici annidate che descrivono le destinazioni dell'op.</span><span class="sxs-lookup"><span data-stu-id="6e2ff-111">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="6e2ff-112">Ogni matrice deve contenere un elenco di int che descrivono gli indici da usare.</span><span class="sxs-lookup"><span data-stu-id="6e2ff-112">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="6e2ff-113">registra:' t []</span><span class="sxs-lookup"><span data-stu-id="6e2ff-113">register : 'T[]</span></span>

<span data-ttu-id="6e2ff-114">Registro qubit su cui agire.</span><span class="sxs-lookup"><span data-stu-id="6e2ff-114">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6e2ff-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6e2ff-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6e2ff-116">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="6e2ff-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6e2ff-117">T</span><span class="sxs-lookup"><span data-stu-id="6e2ff-117">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="6e2ff-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e2ff-118">See Also</span></span>

- [<span data-ttu-id="6e2ff-119">Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="6e2ff-119">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)