---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsCA
title: Operazione ApplySeriesOfOpsCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsCA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint + Controlled)
ms.openlocfilehash: 9dd1343b3ebcc75592441f150eee822cfe83f9a1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217884"
---
# <a name="applyseriesofopsca-operation"></a><span data-ttu-id="a7e59-102">Operazione ApplySeriesOfOpsCA</span><span class="sxs-lookup"><span data-stu-id="a7e59-102">ApplySeriesOfOpsCA operation</span></span>

<span data-ttu-id="a7e59-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a7e59-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a7e59-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a7e59-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a7e59-105">Applica in sequenza un elenco di Ops e le relative destinazioni in una matrice.</span><span class="sxs-lookup"><span data-stu-id="a7e59-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="a7e59-106">(Contiguo + controllato)</span><span class="sxs-lookup"><span data-stu-id="a7e59-106">(Adjoint + Controlled)</span></span>

```qsharp
operation ApplySeriesOfOpsCA<'T> (listOfOps : ('T[] => Unit is Adj + Ctl)[], targets : Int[][], register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a7e59-107">Input</span><span class="sxs-lookup"><span data-stu-id="a7e59-107">Input</span></span>

### <a name="listofops--t--unit--is-adj--ctl"></a><span data-ttu-id="a7e59-108">listOfOps:' t [] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL []</span><span class="sxs-lookup"><span data-stu-id="a7e59-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>

<span data-ttu-id="a7e59-109">Elenco di operazioni, ciascuna delle quali accetta una matrice t, da applicare.</span><span class="sxs-lookup"><span data-stu-id="a7e59-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="a7e59-110">Vengono applicati in sequenza, l'indice più basso.</span><span class="sxs-lookup"><span data-stu-id="a7e59-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="a7e59-111">Ogni deve avere un Funct e un functor controllato.</span><span class="sxs-lookup"><span data-stu-id="a7e59-111">Each must have both an Adjoint and Controlled functor.</span></span>


### <a name="targets--int"></a><span data-ttu-id="a7e59-112">destinazioni: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="a7e59-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="a7e59-113">Matrici annidate che descrivono le destinazioni dell'op.</span><span class="sxs-lookup"><span data-stu-id="a7e59-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="a7e59-114">Ogni matrice deve contenere un elenco di int che descrivono gli indici da usare.</span><span class="sxs-lookup"><span data-stu-id="a7e59-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="a7e59-115">registra:' t []</span><span class="sxs-lookup"><span data-stu-id="a7e59-115">register : 'T[]</span></span>

<span data-ttu-id="a7e59-116">Registro qubit su cui agire.</span><span class="sxs-lookup"><span data-stu-id="a7e59-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a7e59-117">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a7e59-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a7e59-118">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="a7e59-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a7e59-119">T</span><span class="sxs-lookup"><span data-stu-id="a7e59-119">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="a7e59-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7e59-120">See Also</span></span>

- [<span data-ttu-id="a7e59-121">Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="a7e59-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)