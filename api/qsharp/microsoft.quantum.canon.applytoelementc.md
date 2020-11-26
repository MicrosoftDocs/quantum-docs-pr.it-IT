---
uid: Microsoft.Quantum.Canon.ApplyToElementC
title: Operazione ApplyToElementC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementC
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: c8d7841e3846ab435671f7959c724f987d8ad5a0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217578"
---
# <a name="applytoelementc-operation"></a><span data-ttu-id="dd48f-102">Operazione ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="dd48f-102">ApplyToElementC operation</span></span>

<span data-ttu-id="dd48f-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dd48f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dd48f-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dd48f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dd48f-105">Applica un'operazione a un determinato elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="dd48f-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementC<'T> (op : ('T => Unit is Ctl), index : Int, targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="dd48f-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dd48f-106">Description</span></span>

<span data-ttu-id="dd48f-107">`op`Viene applicata un'operazione, un indice `index` e una matrice di destinazioni `targets` `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="dd48f-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="dd48f-108">Input</span><span class="sxs-lookup"><span data-stu-id="dd48f-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="dd48f-109">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL</span><span class="sxs-lookup"><span data-stu-id="dd48f-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="dd48f-110">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="dd48f-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="dd48f-111">Indice: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dd48f-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dd48f-112">Indice nella matrice di destinazioni.</span><span class="sxs-lookup"><span data-stu-id="dd48f-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="dd48f-113">destinazioni:' t []</span><span class="sxs-lookup"><span data-stu-id="dd48f-113">targets : 'T[]</span></span>

<span data-ttu-id="dd48f-114">Matrice di destinazioni possibili per `op` .</span><span class="sxs-lookup"><span data-stu-id="dd48f-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dd48f-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dd48f-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="dd48f-116">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="dd48f-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dd48f-117">T</span><span class="sxs-lookup"><span data-stu-id="dd48f-117">'T</span></span>

<span data-ttu-id="dd48f-118">Tipo di input dell'operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="dd48f-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="dd48f-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd48f-119">See Also</span></span>

- [<span data-ttu-id="dd48f-120">Microsoft. Quantum. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="dd48f-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="dd48f-121">Microsoft. Quantum. Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="dd48f-121">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [<span data-ttu-id="dd48f-122">Microsoft. Quantum. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="dd48f-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)