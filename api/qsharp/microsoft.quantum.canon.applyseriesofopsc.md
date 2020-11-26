---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsC
title: Operazione ApplySeriesOfOpsC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsC
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Controlled)
ms.openlocfilehash: eaa0ea3e33cce708af5879cfbe875397fbb82a8a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217935"
---
# <a name="applyseriesofopsc-operation"></a><span data-ttu-id="69909-102">Operazione ApplySeriesOfOpsC</span><span class="sxs-lookup"><span data-stu-id="69909-102">ApplySeriesOfOpsC operation</span></span>

<span data-ttu-id="69909-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="69909-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="69909-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="69909-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="69909-105">Applica in sequenza un elenco di Ops e le relative destinazioni in una matrice.</span><span class="sxs-lookup"><span data-stu-id="69909-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="69909-106">Controllato</span><span class="sxs-lookup"><span data-stu-id="69909-106">(Controlled)</span></span>

```qsharp
operation ApplySeriesOfOpsC<'T> (listOfOps : ('T[] => Unit is Ctl)[], targets : Int[][], register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="69909-107">Input</span><span class="sxs-lookup"><span data-stu-id="69909-107">Input</span></span>

### <a name="listofops--t--unit--is-ctl"></a><span data-ttu-id="69909-108">listOfOps:' t [] => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL []</span><span class="sxs-lookup"><span data-stu-id="69909-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl[]</span></span>

<span data-ttu-id="69909-109">Elenco di operazioni, ciascuna delle quali accetta una matrice t, da applicare.</span><span class="sxs-lookup"><span data-stu-id="69909-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="69909-110">Vengono applicati in sequenza, l'indice più basso.</span><span class="sxs-lookup"><span data-stu-id="69909-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="69909-111">Ogni deve avere un functor controllato</span><span class="sxs-lookup"><span data-stu-id="69909-111">Each must have a Controlled functor</span></span>


### <a name="targets--int"></a><span data-ttu-id="69909-112">destinazioni: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="69909-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="69909-113">Matrici annidate che descrivono le destinazioni dell'op.</span><span class="sxs-lookup"><span data-stu-id="69909-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="69909-114">Ogni matrice deve contenere un elenco di int che descrivono gli indici da usare.</span><span class="sxs-lookup"><span data-stu-id="69909-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="69909-115">registra:' t []</span><span class="sxs-lookup"><span data-stu-id="69909-115">register : 'T[]</span></span>

<span data-ttu-id="69909-116">Registro qubit su cui agire.</span><span class="sxs-lookup"><span data-stu-id="69909-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="69909-117">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="69909-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="69909-118">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="69909-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="69909-119">T</span><span class="sxs-lookup"><span data-stu-id="69909-119">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="69909-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69909-120">See Also</span></span>

- [<span data-ttu-id="69909-121">Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="69909-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)