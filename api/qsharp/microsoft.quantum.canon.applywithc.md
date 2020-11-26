---
uid: Microsoft.Quantum.Canon.ApplyWithC
title: Operazione ApplyWithC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithC
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: 172f9098a53c97e71f160b4a48479c3184be4385
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217238"
---
# <a name="applywithc-operation"></a><span data-ttu-id="147fb-102">Operazione ApplyWithC</span><span class="sxs-lookup"><span data-stu-id="147fb-102">ApplyWithC operation</span></span>

<span data-ttu-id="147fb-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="147fb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="147fb-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="147fb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="147fb-105">Date due operazioni, applica una come coniugata con l'altra.</span><span class="sxs-lookup"><span data-stu-id="147fb-105">Given two operations, applies one as conjugated with the other.</span></span>

```qsharp
operation ApplyWithC<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Ctl), target : 'T) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="147fb-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="147fb-106">Description</span></span>

<span data-ttu-id="147fb-107">Date due operazioni, rispettivamente descritte da operatori unitari $U $ e $V $, le applicano nella sequenza $U ^ {\dagger} V U $.</span><span class="sxs-lookup"><span data-stu-id="147fb-107">Given two operations, respectively described by unitary operators $U$ and $V$, applies them in the sequence $U^{\dagger} V U$.</span></span> <span data-ttu-id="147fb-108">Questa operazione implementa quindi l'operatore unitario fornito da $V $ coniugato con $U $.</span><span class="sxs-lookup"><span data-stu-id="147fb-108">That is, this operation implements the unitary operator given by $V$ conjugated with $U$.</span></span>

## <a name="input"></a><span data-ttu-id="147fb-109">Input</span><span class="sxs-lookup"><span data-stu-id="147fb-109">Input</span></span>

### <a name="outeroperation--t--unit--is-adj"></a><span data-ttu-id="147fb-110">outerOperation:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ</span><span class="sxs-lookup"><span data-stu-id="147fb-110">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="147fb-111">L'operazione $U $ da usare per coniugare $V $.</span><span class="sxs-lookup"><span data-stu-id="147fb-111">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="147fb-112">Si noti che l'operazione esterna $U $ deve essere adjointable, ma non deve essere controllabile.</span><span class="sxs-lookup"><span data-stu-id="147fb-112">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit--is-ctl"></a><span data-ttu-id="147fb-113">innerOperation:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL</span><span class="sxs-lookup"><span data-stu-id="147fb-113">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="147fb-114">Operazione $V $ coniugata.</span><span class="sxs-lookup"><span data-stu-id="147fb-114">The operation $V$ being conjugated.</span></span>


### <a name="target--t"></a><span data-ttu-id="147fb-115">destinazione:' t</span><span class="sxs-lookup"><span data-stu-id="147fb-115">target : 'T</span></span>

<span data-ttu-id="147fb-116">Input da fornire alle operazioni esterne e interne.</span><span class="sxs-lookup"><span data-stu-id="147fb-116">The input to be provided to the outer and inner operations.</span></span>



## <a name="output--unit"></a><span data-ttu-id="147fb-117">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="147fb-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="147fb-118">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="147fb-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="147fb-119">T</span><span class="sxs-lookup"><span data-stu-id="147fb-119">'T</span></span>

<span data-ttu-id="147fb-120">Destinazione in cui agiscono le operazioni interne ed esterne.</span><span class="sxs-lookup"><span data-stu-id="147fb-120">The target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="147fb-121">Commenti</span><span class="sxs-lookup"><span data-stu-id="147fb-121">Remarks</span></span>

<span data-ttu-id="147fb-122">L'operazione esterna viene sempre considerata adjointable, ma non deve essere controllabile affinché l'operazione combinata sia controllabile.</span><span class="sxs-lookup"><span data-stu-id="147fb-122">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="147fb-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="147fb-123">See Also</span></span>

- [<span data-ttu-id="147fb-124">Microsoft. Quantum. Canon. ApplyWith</span><span class="sxs-lookup"><span data-stu-id="147fb-124">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)
- [<span data-ttu-id="147fb-125">Microsoft. Quantum. Canon. ApplyWithA</span><span class="sxs-lookup"><span data-stu-id="147fb-125">Microsoft.Quantum.Canon.ApplyWithA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithA)
- [<span data-ttu-id="147fb-126">Microsoft. Quantum. Canon. ApplyWithCA</span><span class="sxs-lookup"><span data-stu-id="147fb-126">Microsoft.Quantum.Canon.ApplyWithCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithCA)