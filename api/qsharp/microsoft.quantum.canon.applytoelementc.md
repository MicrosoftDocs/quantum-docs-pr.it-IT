---
uid: Microsoft.Quantum.Canon.ApplyToElementC
title: Operazione ApplyToElementC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementC
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: bd466ff59e6e962be9a7e58b6d298c60b0d1d90d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717450"
---
# <a name="applytoelementc-operation"></a><span data-ttu-id="b39cb-102">Operazione ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="b39cb-102">ApplyToElementC operation</span></span>

<span data-ttu-id="b39cb-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b39cb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b39cb-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b39cb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b39cb-105">Applica un'operazione a un determinato elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="b39cb-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementC<'T> (op : ('T => Unit is Ctl), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="b39cb-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b39cb-106">Description</span></span>

<span data-ttu-id="b39cb-107">`op`Viene applicata un'operazione, un indice `index` e una matrice di destinazioni `targets` `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="b39cb-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="b39cb-108">Input</span><span class="sxs-lookup"><span data-stu-id="b39cb-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="b39cb-109">op:' t => CTL [unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b39cb-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="b39cb-110">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="b39cb-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="b39cb-111">Indice: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b39cb-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b39cb-112">Indice nella matrice di destinazioni.</span><span class="sxs-lookup"><span data-stu-id="b39cb-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="b39cb-113">destinazioni:' t []</span><span class="sxs-lookup"><span data-stu-id="b39cb-113">targets : 'T[]</span></span>

<span data-ttu-id="b39cb-114">Matrice di destinazioni possibili per `op` .</span><span class="sxs-lookup"><span data-stu-id="b39cb-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b39cb-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b39cb-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b39cb-116">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="b39cb-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b39cb-117">T</span><span class="sxs-lookup"><span data-stu-id="b39cb-117">'T</span></span>

<span data-ttu-id="b39cb-118">Tipo di input dell'operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="b39cb-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="b39cb-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b39cb-119">See Also</span></span>

- [<span data-ttu-id="b39cb-120">Microsoft. Quantum. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="b39cb-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="b39cb-121">Microsoft. Quantum. Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="b39cb-121">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [<span data-ttu-id="b39cb-122">Microsoft. Quantum. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="b39cb-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)