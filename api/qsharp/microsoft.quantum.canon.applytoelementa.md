---
uid: Microsoft.Quantum.Canon.ApplyToElementA
title: Operazione ApplyToElementA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: e8318a7873476ee49d8e1e235e6c917a38ee6200
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208874"
---
# <a name="applytoelementa-operation"></a><span data-ttu-id="d6c5f-102">Operazione ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="d6c5f-102">ApplyToElementA operation</span></span>

<span data-ttu-id="d6c5f-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d6c5f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d6c5f-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d6c5f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d6c5f-105">Applica un'operazione a un determinato elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="d6c5f-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementA<'T> (op : ('T => Unit is Adj), index : Int, targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="d6c5f-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d6c5f-106">Description</span></span>

<span data-ttu-id="d6c5f-107">`op`Viene applicata un'operazione, un indice `index` e una matrice di destinazioni `targets` `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="d6c5f-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="d6c5f-108">Input</span><span class="sxs-lookup"><span data-stu-id="d6c5f-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="d6c5f-109">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ</span><span class="sxs-lookup"><span data-stu-id="d6c5f-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="d6c5f-110">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="d6c5f-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="d6c5f-111">Indice: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d6c5f-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d6c5f-112">Indice nella matrice di destinazioni.</span><span class="sxs-lookup"><span data-stu-id="d6c5f-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="d6c5f-113">destinazioni:' t []</span><span class="sxs-lookup"><span data-stu-id="d6c5f-113">targets : 'T[]</span></span>

<span data-ttu-id="d6c5f-114">Matrice di destinazioni possibili per `op` .</span><span class="sxs-lookup"><span data-stu-id="d6c5f-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d6c5f-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d6c5f-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d6c5f-116">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="d6c5f-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d6c5f-117">T</span><span class="sxs-lookup"><span data-stu-id="d6c5f-117">'T</span></span>

<span data-ttu-id="d6c5f-118">Tipo di input dell'operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="d6c5f-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="d6c5f-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6c5f-119">See Also</span></span>

- [<span data-ttu-id="d6c5f-120">Microsoft. Quantum. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="d6c5f-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="d6c5f-121">Microsoft. Quantum. Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="d6c5f-121">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="d6c5f-122">Microsoft. Quantum. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="d6c5f-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)