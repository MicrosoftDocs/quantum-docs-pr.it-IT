---
uid: Microsoft.Quantum.Canon.ConjugatedByC
title: ConjugatedByC (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByC
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: c4c381e40c5a941487bcf78ebe5339574aedb45d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716456"
---
# <a name="conjugatedbyc-function"></a><span data-ttu-id="785f1-102">ConjugatedByC (funzione)</span><span class="sxs-lookup"><span data-stu-id="785f1-102">ConjugatedByC function</span></span>

<span data-ttu-id="785f1-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="785f1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="785f1-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="785f1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="785f1-105">Date le operazioni esterne e interne, restituisce una nuova operazione che coniuga l'operazione interna all'operazione esterna.</span><span class="sxs-lookup"><span data-stu-id="785f1-105">Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.</span></span>

```qsharp
function ConjugatedByC<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Ctl)) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="785f1-106">Input</span><span class="sxs-lookup"><span data-stu-id="785f1-106">Input</span></span>

### <a name="outeroperation--t--unit-adj"></a><span data-ttu-id="785f1-107">outerOperation:' t => ADJ [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="785f1-107">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="785f1-108">L'operazione $U $ da usare per coniugare $V $.</span><span class="sxs-lookup"><span data-stu-id="785f1-108">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="785f1-109">Si noti che l'operazione esterna $U $ deve essere adjointable, ma non deve essere controllabile.</span><span class="sxs-lookup"><span data-stu-id="785f1-109">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit-ctl"></a><span data-ttu-id="785f1-110">innerOperation:' t => CTL [unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="785f1-110">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="785f1-111">Operazione $V $ coniugata.</span><span class="sxs-lookup"><span data-stu-id="785f1-111">The operation $V$ being conjugated.</span></span>



## <a name="output--t--unit-ctl"></a><span data-ttu-id="785f1-112">Output:' t => CTL [unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="785f1-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="785f1-113">Nuova operazione la cui azione è rappresentata dall'unità $U ^ {\dagger} V U $.</span><span class="sxs-lookup"><span data-stu-id="785f1-113">A new operation whose action is represented by the unitary $U^{\dagger} V U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="785f1-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="785f1-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="785f1-115">T</span><span class="sxs-lookup"><span data-stu-id="785f1-115">'T</span></span>

<span data-ttu-id="785f1-116">Tipo di destinazione in cui agiscono le operazioni interne ed esterne.</span><span class="sxs-lookup"><span data-stu-id="785f1-116">The type of the target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="785f1-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="785f1-117">Remarks</span></span>

<span data-ttu-id="785f1-118">L'operazione esterna viene sempre considerata adjointable, ma non deve essere controllabile affinché l'operazione combinata sia controllabile.</span><span class="sxs-lookup"><span data-stu-id="785f1-118">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="785f1-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="785f1-119">See Also</span></span>

- [<span data-ttu-id="785f1-120">Microsoft. Quantum. Canon. ConjugatedBy</span><span class="sxs-lookup"><span data-stu-id="785f1-120">Microsoft.Quantum.Canon.ConjugatedBy</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedBy)
- [<span data-ttu-id="785f1-121">Microsoft. Quantum. Canon. ConjugatedByA</span><span class="sxs-lookup"><span data-stu-id="785f1-121">Microsoft.Quantum.Canon.ConjugatedByA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [<span data-ttu-id="785f1-122">Microsoft. Quantum. Canon. ConjugatedByCA</span><span class="sxs-lookup"><span data-stu-id="785f1-122">Microsoft.Quantum.Canon.ConjugatedByCA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [<span data-ttu-id="785f1-123">Microsoft. Quantum. Canon. ApplyWith</span><span class="sxs-lookup"><span data-stu-id="785f1-123">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)