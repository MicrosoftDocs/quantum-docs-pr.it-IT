---
uid: Microsoft.Quantum.Canon.ApplyWith
title: Operazione ApplyWith
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWith
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: 61047ea2ea249e5a4d39b5747c542462c9632138
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716946"
---
# <a name="applywith-operation"></a><span data-ttu-id="02116-102">Operazione ApplyWith</span><span class="sxs-lookup"><span data-stu-id="02116-102">ApplyWith operation</span></span>

<span data-ttu-id="02116-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="02116-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="02116-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="02116-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="02116-105">Date due operazioni, applica una come coniugata con l'altra.</span><span class="sxs-lookup"><span data-stu-id="02116-105">Given two operations, applies one as conjugated with the other.</span></span>

```qsharp
operation ApplyWith<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit), target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="02116-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02116-106">Description</span></span>

<span data-ttu-id="02116-107">Date due operazioni, rispettivamente descritte da operatori unitari $U $ e $V $, le applicano nella sequenza $U ^ {\dagger} V U $.</span><span class="sxs-lookup"><span data-stu-id="02116-107">Given two operations, respectively described by unitary operators $U$ and $V$, applies them in the sequence $U^{\dagger} V U$.</span></span> <span data-ttu-id="02116-108">Questa operazione implementa quindi l'operatore unitario fornito da $V $ coniugato con $U $.</span><span class="sxs-lookup"><span data-stu-id="02116-108">That is, this operation implements the unitary operator given by $V$ conjugated with $U$.</span></span>

## <a name="input"></a><span data-ttu-id="02116-109">Input</span><span class="sxs-lookup"><span data-stu-id="02116-109">Input</span></span>

### <a name="outeroperation--t--unit-adj"></a><span data-ttu-id="02116-110">outerOperation:' t => ADJ [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="02116-110">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="02116-111">L'operazione $U $ da usare per coniugare $V $.</span><span class="sxs-lookup"><span data-stu-id="02116-111">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="02116-112">Si noti che l'operazione esterna $U $ deve essere adjointable, ma non deve essere controllabile.</span><span class="sxs-lookup"><span data-stu-id="02116-112">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit"></a><span data-ttu-id="02116-113">innerOperation:' t = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="02116-113">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="02116-114">Operazione $V $ coniugata.</span><span class="sxs-lookup"><span data-stu-id="02116-114">The operation $V$ being conjugated.</span></span>


### <a name="target--t"></a><span data-ttu-id="02116-115">destinazione:' t</span><span class="sxs-lookup"><span data-stu-id="02116-115">target : 'T</span></span>

<span data-ttu-id="02116-116">Input da fornire alle operazioni esterne e interne.</span><span class="sxs-lookup"><span data-stu-id="02116-116">The input to be provided to the outer and inner operations.</span></span>



## <a name="output--unit"></a><span data-ttu-id="02116-117">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="02116-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="02116-118">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="02116-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="02116-119">T</span><span class="sxs-lookup"><span data-stu-id="02116-119">'T</span></span>

<span data-ttu-id="02116-120">Destinazione in cui agiscono le operazioni interne ed esterne.</span><span class="sxs-lookup"><span data-stu-id="02116-120">The target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="02116-121">Commenti</span><span class="sxs-lookup"><span data-stu-id="02116-121">Remarks</span></span>

<span data-ttu-id="02116-122">L'operazione esterna viene sempre considerata adjointable, ma non deve essere controllabile affinché l'operazione combinata sia controllabile.</span><span class="sxs-lookup"><span data-stu-id="02116-122">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="02116-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02116-123">See Also</span></span>

- [<span data-ttu-id="02116-124">Microsoft. Quantum. Canon. ApplyWithA</span><span class="sxs-lookup"><span data-stu-id="02116-124">Microsoft.Quantum.Canon.ApplyWithA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithA)
- [<span data-ttu-id="02116-125">Microsoft. Quantum. Canon. ApplyWithC</span><span class="sxs-lookup"><span data-stu-id="02116-125">Microsoft.Quantum.Canon.ApplyWithC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithC)
- [<span data-ttu-id="02116-126">Microsoft. Quantum. Canon. ApplyWithCA</span><span class="sxs-lookup"><span data-stu-id="02116-126">Microsoft.Quantum.Canon.ApplyWithCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithCA)