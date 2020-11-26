---
uid: Microsoft.Quantum.Canon.ConjugatedByCA
title: ConjugatedByCA (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByCA
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: acd5a9f796f751b9c9c374d841e80de9286fcd24
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207310"
---
# <a name="conjugatedbyca-function"></a><span data-ttu-id="c018a-102">ConjugatedByCA (funzione)</span><span class="sxs-lookup"><span data-stu-id="c018a-102">ConjugatedByCA function</span></span>

<span data-ttu-id="c018a-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c018a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c018a-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c018a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c018a-105">Date le operazioni esterne e interne, restituisce una nuova operazione che coniuga l'operazione interna all'operazione esterna.</span><span class="sxs-lookup"><span data-stu-id="c018a-105">Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.</span></span>

```qsharp
function ConjugatedByCA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj + Ctl)) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="c018a-106">Input</span><span class="sxs-lookup"><span data-stu-id="c018a-106">Input</span></span>

### <a name="outeroperation--t--unit--is-adj"></a><span data-ttu-id="c018a-107">outerOperation:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ</span><span class="sxs-lookup"><span data-stu-id="c018a-107">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="c018a-108">L'operazione $U $ da usare per coniugare $V $.</span><span class="sxs-lookup"><span data-stu-id="c018a-108">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="c018a-109">Si noti che l'operazione esterna $U $ deve essere adjointable, ma non deve essere controllabile.</span><span class="sxs-lookup"><span data-stu-id="c018a-109">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit--is-adj--ctl"></a><span data-ttu-id="c018a-110">innerOperation:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="c018a-110">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="c018a-111">Operazione $V $ coniugata.</span><span class="sxs-lookup"><span data-stu-id="c018a-111">The operation $V$ being conjugated.</span></span>



## <a name="output--t--unit--is-adj--ctl"></a><span data-ttu-id="c018a-112">Output:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="c018a-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="c018a-113">Nuova operazione la cui azione è rappresentata dall'unità $U ^ {\dagger} V U $.</span><span class="sxs-lookup"><span data-stu-id="c018a-113">A new operation whose action is represented by the unitary $U^{\dagger} V U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c018a-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="c018a-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c018a-115">T</span><span class="sxs-lookup"><span data-stu-id="c018a-115">'T</span></span>

<span data-ttu-id="c018a-116">Tipo di destinazione in cui agiscono le operazioni interne ed esterne.</span><span class="sxs-lookup"><span data-stu-id="c018a-116">The type of the target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="c018a-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="c018a-117">Remarks</span></span>

<span data-ttu-id="c018a-118">L'operazione esterna viene sempre considerata adjointable, ma non deve essere controllabile affinché l'operazione combinata sia controllabile.</span><span class="sxs-lookup"><span data-stu-id="c018a-118">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="c018a-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c018a-119">See Also</span></span>

- [<span data-ttu-id="c018a-120">Microsoft. Quantum. Canon. ConjugatedByA</span><span class="sxs-lookup"><span data-stu-id="c018a-120">Microsoft.Quantum.Canon.ConjugatedByA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [<span data-ttu-id="c018a-121">Microsoft. Quantum. Canon. ConjugatedByC</span><span class="sxs-lookup"><span data-stu-id="c018a-121">Microsoft.Quantum.Canon.ConjugatedByC</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByC)
- [<span data-ttu-id="c018a-122">Microsoft. Quantum. Canon. ConjugatedByCA</span><span class="sxs-lookup"><span data-stu-id="c018a-122">Microsoft.Quantum.Canon.ConjugatedByCA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [<span data-ttu-id="c018a-123">Microsoft. Quantum. Canon. ApplyWith</span><span class="sxs-lookup"><span data-stu-id="c018a-123">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)