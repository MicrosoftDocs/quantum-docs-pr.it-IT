---
uid: Microsoft.Quantum.Canon.ApplyToElement
title: Operazione ApplyToElement
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElement
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 5c321d95c9b79bc50827c2b50c406b164e143dc6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717506"
---
# <a name="applytoelement-operation"></a><span data-ttu-id="6df1f-102">Operazione ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="6df1f-102">ApplyToElement operation</span></span>

<span data-ttu-id="6df1f-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6df1f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6df1f-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6df1f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6df1f-105">Applica un'operazione a un determinato elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="6df1f-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElement<'T> (op : ('T => Unit), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="6df1f-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6df1f-106">Description</span></span>

<span data-ttu-id="6df1f-107">`op`Viene applicata un'operazione, un indice `index` e una matrice di destinazioni `targets` `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="6df1f-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="6df1f-108">Input</span><span class="sxs-lookup"><span data-stu-id="6df1f-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="6df1f-109">op:' t = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="6df1f-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="6df1f-110">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="6df1f-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="6df1f-111">Indice: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6df1f-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6df1f-112">Indice nella matrice di destinazioni.</span><span class="sxs-lookup"><span data-stu-id="6df1f-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="6df1f-113">destinazioni:' t []</span><span class="sxs-lookup"><span data-stu-id="6df1f-113">targets : 'T[]</span></span>

<span data-ttu-id="6df1f-114">Matrice di destinazioni possibili per `op` .</span><span class="sxs-lookup"><span data-stu-id="6df1f-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6df1f-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6df1f-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6df1f-116">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="6df1f-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6df1f-117">T</span><span class="sxs-lookup"><span data-stu-id="6df1f-117">'T</span></span>

<span data-ttu-id="6df1f-118">Tipo di input dell'operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="6df1f-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="6df1f-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6df1f-119">See Also</span></span>

- [<span data-ttu-id="6df1f-120">Microsoft. Quantum. Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="6df1f-120">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="6df1f-121">Microsoft. Quantum. Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="6df1f-121">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [<span data-ttu-id="6df1f-122">Microsoft. Quantum. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="6df1f-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)