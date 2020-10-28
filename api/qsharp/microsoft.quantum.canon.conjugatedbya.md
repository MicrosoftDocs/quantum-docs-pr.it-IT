---
uid: Microsoft.Quantum.Canon.ConjugatedByA
title: ConjugatedByA (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByA
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: bcaab28e99d3d61f4a36da866321d28f3dc4bd53
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716467"
---
# <a name="conjugatedbya-function"></a><span data-ttu-id="fffbb-102">ConjugatedByA (funzione)</span><span class="sxs-lookup"><span data-stu-id="fffbb-102">ConjugatedByA function</span></span>

<span data-ttu-id="fffbb-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fffbb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fffbb-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fffbb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fffbb-105">Date le operazioni esterne e interne, restituisce una nuova operazione che coniuga l'operazione interna all'operazione esterna.</span><span class="sxs-lookup"><span data-stu-id="fffbb-105">Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.</span></span>

```qsharp
function ConjugatedByA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj)) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="fffbb-106">Input</span><span class="sxs-lookup"><span data-stu-id="fffbb-106">Input</span></span>

### <a name="outeroperation--t--unit-adj"></a><span data-ttu-id="fffbb-107">outerOperation:' t => ADJ [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fffbb-107">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="fffbb-108">L'operazione $U $ da usare per coniugare $V $.</span><span class="sxs-lookup"><span data-stu-id="fffbb-108">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="fffbb-109">Si noti che l'operazione esterna $U $ deve essere adjointable, ma non deve essere controllabile.</span><span class="sxs-lookup"><span data-stu-id="fffbb-109">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit-adj"></a><span data-ttu-id="fffbb-110">innerOperation:' t => ADJ [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fffbb-110">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="fffbb-111">Operazione $V $ coniugata.</span><span class="sxs-lookup"><span data-stu-id="fffbb-111">The operation $V$ being conjugated.</span></span>



## <a name="output--t--unit-adj"></a><span data-ttu-id="fffbb-112">Output:' t => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ</span><span class="sxs-lookup"><span data-stu-id="fffbb-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="fffbb-113">Nuova operazione la cui azione è rappresentata dall'unità $U ^ {\dagger} V U $.</span><span class="sxs-lookup"><span data-stu-id="fffbb-113">A new operation whose action is represented by the unitary $U^{\dagger} V U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="fffbb-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="fffbb-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fffbb-115">T</span><span class="sxs-lookup"><span data-stu-id="fffbb-115">'T</span></span>

<span data-ttu-id="fffbb-116">Tipo di destinazione in cui agiscono le operazioni interne ed esterne.</span><span class="sxs-lookup"><span data-stu-id="fffbb-116">The type of the target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="fffbb-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="fffbb-117">Remarks</span></span>

<span data-ttu-id="fffbb-118">L'operazione esterna viene sempre considerata adjointable, ma non deve essere controllabile affinché l'operazione combinata sia controllabile.</span><span class="sxs-lookup"><span data-stu-id="fffbb-118">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="fffbb-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fffbb-119">See Also</span></span>

- [<span data-ttu-id="fffbb-120">Microsoft. Quantum. Canon. ConjugatedByA</span><span class="sxs-lookup"><span data-stu-id="fffbb-120">Microsoft.Quantum.Canon.ConjugatedByA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [<span data-ttu-id="fffbb-121">Microsoft. Quantum. Canon. ConjugatedByC</span><span class="sxs-lookup"><span data-stu-id="fffbb-121">Microsoft.Quantum.Canon.ConjugatedByC</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByC)
- [<span data-ttu-id="fffbb-122">Microsoft. Quantum. Canon. ConjugatedByCA</span><span class="sxs-lookup"><span data-stu-id="fffbb-122">Microsoft.Quantum.Canon.ConjugatedByCA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [<span data-ttu-id="fffbb-123">Microsoft. Quantum. Canon. ApplyWith</span><span class="sxs-lookup"><span data-stu-id="fffbb-123">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)