---
uid: Microsoft.Quantum.Canon.ApplyToElementA
title: Operazione ApplyToElementA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: f34089c2a45de281507cb79bde8a8cb9d2fefe47
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717489"
---
# <a name="applytoelementa-operation"></a><span data-ttu-id="21694-102">Operazione ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="21694-102">ApplyToElementA operation</span></span>

<span data-ttu-id="21694-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="21694-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="21694-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="21694-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="21694-105">Applica un'operazione a un determinato elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="21694-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementA<'T> (op : ('T => Unit is Adj), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="21694-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="21694-106">Description</span></span>

<span data-ttu-id="21694-107">`op`Viene applicata un'operazione, un indice `index` e una matrice di destinazioni `targets` `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="21694-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="21694-108">Input</span><span class="sxs-lookup"><span data-stu-id="21694-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="21694-109">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ</span><span class="sxs-lookup"><span data-stu-id="21694-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="21694-110">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="21694-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="21694-111">Indice: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="21694-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="21694-112">Indice nella matrice di destinazioni.</span><span class="sxs-lookup"><span data-stu-id="21694-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="21694-113">destinazioni:' t []</span><span class="sxs-lookup"><span data-stu-id="21694-113">targets : 'T[]</span></span>

<span data-ttu-id="21694-114">Matrice di destinazioni possibili per `op` .</span><span class="sxs-lookup"><span data-stu-id="21694-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="21694-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="21694-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="21694-116">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="21694-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="21694-117">T</span><span class="sxs-lookup"><span data-stu-id="21694-117">'T</span></span>

<span data-ttu-id="21694-118">Tipo di input dell'operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="21694-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="21694-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21694-119">See Also</span></span>

- [<span data-ttu-id="21694-120">Microsoft. Quantum. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="21694-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="21694-121">Microsoft. Quantum. Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="21694-121">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="21694-122">Microsoft. Quantum. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="21694-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)