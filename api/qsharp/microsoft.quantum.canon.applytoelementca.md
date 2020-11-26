---
uid: Microsoft.Quantum.Canon.ApplyToElementCA
title: Operazione ApplyToElementCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementCA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 8ae4ece0d3d56ea2be1ce494ab0c5ee7caacbbf8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208857"
---
# <a name="applytoelementca-operation"></a><span data-ttu-id="be139-102">Operazione ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="be139-102">ApplyToElementCA operation</span></span>

<span data-ttu-id="be139-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="be139-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="be139-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="be139-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="be139-105">Applica un'operazione a un determinato elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="be139-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementCA<'T> (op : ('T => Unit is Adj + Ctl), index : Int, targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="be139-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="be139-106">Description</span></span>

<span data-ttu-id="be139-107">`op`Viene applicata un'operazione, un indice `index` e una matrice di destinazioni `targets` `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="be139-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="be139-108">Input</span><span class="sxs-lookup"><span data-stu-id="be139-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="be139-109">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="be139-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="be139-110">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="be139-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="be139-111">Indice: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="be139-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="be139-112">Indice nella matrice di destinazioni.</span><span class="sxs-lookup"><span data-stu-id="be139-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="be139-113">destinazioni:' t []</span><span class="sxs-lookup"><span data-stu-id="be139-113">targets : 'T[]</span></span>

<span data-ttu-id="be139-114">Matrice di destinazioni possibili per `op` .</span><span class="sxs-lookup"><span data-stu-id="be139-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="be139-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="be139-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="be139-116">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="be139-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="be139-117">T</span><span class="sxs-lookup"><span data-stu-id="be139-117">'T</span></span>

<span data-ttu-id="be139-118">Tipo di input dell'operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="be139-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="be139-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be139-119">See Also</span></span>

- [<span data-ttu-id="be139-120">Microsoft. Quantum. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="be139-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="be139-121">Microsoft. Quantum. Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="be139-121">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="be139-122">Microsoft. Quantum. Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="be139-122">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)