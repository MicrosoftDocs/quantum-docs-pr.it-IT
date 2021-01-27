---
uid: Microsoft.Quantum.Canon.ApplyWithA
title: Operazione ApplyWithA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithA
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: f717347a81e4efa5ad1736485ad9e1c518d736a7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841164"
---
# <a name="applywitha-operation"></a><span data-ttu-id="6bea8-102">Operazione ApplyWithA</span><span class="sxs-lookup"><span data-stu-id="6bea8-102">ApplyWithA operation</span></span>

<span data-ttu-id="6bea8-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6bea8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6bea8-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6bea8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6bea8-105">Date due operazioni, applica una come coniugata con l'altra.</span><span class="sxs-lookup"><span data-stu-id="6bea8-105">Given two operations, applies one as conjugated with the other.</span></span>

```qsharp
operation ApplyWithA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj), target : 'T) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="6bea8-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6bea8-106">Description</span></span>

<span data-ttu-id="6bea8-107">Date due operazioni, rispettivamente descritte da operatori unitari $U $ e $V $, le applicano nella sequenza $U ^ {\dagger} V U $.</span><span class="sxs-lookup"><span data-stu-id="6bea8-107">Given two operations, respectively described by unitary operators $U$ and $V$, applies them in the sequence $U^{\dagger} V U$.</span></span> <span data-ttu-id="6bea8-108">Questa operazione implementa quindi l'operatore unitario fornito da $V $ coniugato con $U $.</span><span class="sxs-lookup"><span data-stu-id="6bea8-108">That is, this operation implements the unitary operator given by $V$ conjugated with $U$.</span></span>

## <a name="input"></a><span data-ttu-id="6bea8-109">Input</span><span class="sxs-lookup"><span data-stu-id="6bea8-109">Input</span></span>

### <a name="outeroperation--t--unit--is-adj"></a><span data-ttu-id="6bea8-110">outerOperation:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ</span><span class="sxs-lookup"><span data-stu-id="6bea8-110">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="6bea8-111">L'operazione $U $ da usare per coniugare $V $.</span><span class="sxs-lookup"><span data-stu-id="6bea8-111">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="6bea8-112">Si noti che l'operazione esterna $U $ deve essere adjointable, ma non deve essere controllabile.</span><span class="sxs-lookup"><span data-stu-id="6bea8-112">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit--is-adj"></a><span data-ttu-id="6bea8-113">innerOperation:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ</span><span class="sxs-lookup"><span data-stu-id="6bea8-113">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="6bea8-114">Operazione $V $ coniugata.</span><span class="sxs-lookup"><span data-stu-id="6bea8-114">The operation $V$ being conjugated.</span></span>


### <a name="target--t"></a><span data-ttu-id="6bea8-115">destinazione:' t</span><span class="sxs-lookup"><span data-stu-id="6bea8-115">target : 'T</span></span>

<span data-ttu-id="6bea8-116">Input da fornire alle operazioni esterne e interne.</span><span class="sxs-lookup"><span data-stu-id="6bea8-116">The input to be provided to the outer and inner operations.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6bea8-117">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6bea8-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6bea8-118">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="6bea8-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6bea8-119">T</span><span class="sxs-lookup"><span data-stu-id="6bea8-119">'T</span></span>

<span data-ttu-id="6bea8-120">Destinazione in cui agiscono le operazioni interne ed esterne.</span><span class="sxs-lookup"><span data-stu-id="6bea8-120">The target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="6bea8-121">Commenti</span><span class="sxs-lookup"><span data-stu-id="6bea8-121">Remarks</span></span>

<span data-ttu-id="6bea8-122">L'operazione esterna viene sempre considerata adjointable, ma non deve essere controllabile affinché l'operazione combinata sia controllabile.</span><span class="sxs-lookup"><span data-stu-id="6bea8-122">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="6bea8-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6bea8-123">See Also</span></span>

- [<span data-ttu-id="6bea8-124">Microsoft. Quantum. Canon. ApplyWith</span><span class="sxs-lookup"><span data-stu-id="6bea8-124">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)
- [<span data-ttu-id="6bea8-125">Microsoft. Quantum. Canon. ApplyWithC</span><span class="sxs-lookup"><span data-stu-id="6bea8-125">Microsoft.Quantum.Canon.ApplyWithC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithC)
- [<span data-ttu-id="6bea8-126">Microsoft. Quantum. Canon. ApplyWithCA</span><span class="sxs-lookup"><span data-stu-id="6bea8-126">Microsoft.Quantum.Canon.ApplyWithCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithCA)