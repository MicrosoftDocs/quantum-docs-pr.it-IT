---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsA
title: Operazione ApplySeriesOfOpsA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint)
ms.openlocfilehash: e2b928fa4c9446e16d2bf5e7b68a32d4bba3a528
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717657"
---
# <a name="applyseriesofopsa-operation"></a><span data-ttu-id="9a0d4-102">Operazione ApplySeriesOfOpsA</span><span class="sxs-lookup"><span data-stu-id="9a0d4-102">ApplySeriesOfOpsA operation</span></span>

<span data-ttu-id="9a0d4-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9a0d4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9a0d4-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9a0d4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9a0d4-105">Applica in sequenza un elenco di Ops e le relative destinazioni in una matrice.</span><span class="sxs-lookup"><span data-stu-id="9a0d4-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="9a0d4-106">Adjoint</span><span class="sxs-lookup"><span data-stu-id="9a0d4-106">(Adjoint)</span></span>

```qsharp
operation ApplySeriesOfOpsA<'T> (listOfOps : ('T[] => Unit is Adj)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="9a0d4-107">Input</span><span class="sxs-lookup"><span data-stu-id="9a0d4-107">Input</span></span>

### <a name="listofops--t--unit-adj"></a><span data-ttu-id="9a0d4-108">listOfOps:' t [] => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ []</span><span class="sxs-lookup"><span data-stu-id="9a0d4-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj[]</span></span>

<span data-ttu-id="9a0d4-109">Elenco di operazioni, ciascuna delle quali accetta una matrice t, da applicare.</span><span class="sxs-lookup"><span data-stu-id="9a0d4-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="9a0d4-110">Vengono applicati in sequenza, l'indice più basso.</span><span class="sxs-lookup"><span data-stu-id="9a0d4-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="9a0d4-111">Ogni deve avere un functor adiacente</span><span class="sxs-lookup"><span data-stu-id="9a0d4-111">Each must have an adjoint functor</span></span>


### <a name="targets--int"></a><span data-ttu-id="9a0d4-112">destinazioni: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="9a0d4-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="9a0d4-113">Matrici annidate che descrivono le destinazioni dell'op.</span><span class="sxs-lookup"><span data-stu-id="9a0d4-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="9a0d4-114">Ogni matrice deve contenere un elenco di int che descrivono gli indici da usare.</span><span class="sxs-lookup"><span data-stu-id="9a0d4-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="9a0d4-115">registra:' t []</span><span class="sxs-lookup"><span data-stu-id="9a0d4-115">register : 'T[]</span></span>

<span data-ttu-id="9a0d4-116">Registro qubit su cui agire.</span><span class="sxs-lookup"><span data-stu-id="9a0d4-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9a0d4-117">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9a0d4-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9a0d4-118">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="9a0d4-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9a0d4-119">T</span><span class="sxs-lookup"><span data-stu-id="9a0d4-119">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="9a0d4-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a0d4-120">See Also</span></span>

- [<span data-ttu-id="9a0d4-121">Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="9a0d4-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)