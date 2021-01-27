---
uid: Microsoft.Quantum.Canon.ApplyToElementC
title: Operazione ApplyToElementC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementC
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: bc63b6b591781a6283b872ef0c2509094a656b4c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850750"
---
# <a name="applytoelementc-operation"></a><span data-ttu-id="369a2-102">Operazione ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="369a2-102">ApplyToElementC operation</span></span>

<span data-ttu-id="369a2-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="369a2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="369a2-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="369a2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="369a2-105">Applica un'operazione a un determinato elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="369a2-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementC<'T> (op : ('T => Unit is Ctl), index : Int, targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="369a2-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="369a2-106">Description</span></span>

<span data-ttu-id="369a2-107">`op`Viene applicata un'operazione, un indice `index` e una matrice di destinazioni `targets` `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="369a2-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="369a2-108">Input</span><span class="sxs-lookup"><span data-stu-id="369a2-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="369a2-109">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL</span><span class="sxs-lookup"><span data-stu-id="369a2-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="369a2-110">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="369a2-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="369a2-111">Indice: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="369a2-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="369a2-112">Indice nella matrice di destinazioni.</span><span class="sxs-lookup"><span data-stu-id="369a2-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="369a2-113">destinazioni:' t []</span><span class="sxs-lookup"><span data-stu-id="369a2-113">targets : 'T[]</span></span>

<span data-ttu-id="369a2-114">Matrice di destinazioni possibili per `op` .</span><span class="sxs-lookup"><span data-stu-id="369a2-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="369a2-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="369a2-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="369a2-116">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="369a2-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="369a2-117">T</span><span class="sxs-lookup"><span data-stu-id="369a2-117">'T</span></span>

<span data-ttu-id="369a2-118">Tipo di input dell'operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="369a2-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="369a2-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="369a2-119">See Also</span></span>

- [<span data-ttu-id="369a2-120">Microsoft. Quantum. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="369a2-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="369a2-121">Microsoft. Quantum. Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="369a2-121">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [<span data-ttu-id="369a2-122">Microsoft. Quantum. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="369a2-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)