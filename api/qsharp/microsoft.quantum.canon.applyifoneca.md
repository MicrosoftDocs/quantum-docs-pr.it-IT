---
uid: Microsoft.Quantum.Canon.ApplyIfOneCA
title: Operazione ApplyIfOneCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneCA
qsharp.summary: Applies a unitary operation conditioned on a classical result value being one.
ms.openlocfilehash: 29801ed0bec08d0ab818f237feb17c2a2a7af1e4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218581"
---
# <a name="applyifoneca-operation"></a><span data-ttu-id="f4984-102">Operazione ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="f4984-102">ApplyIfOneCA operation</span></span>

<span data-ttu-id="f4984-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f4984-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f4984-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f4984-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f4984-105">Applica un'operazione unitaria condizionata a un valore di risultato classico che è uno.</span><span class="sxs-lookup"><span data-stu-id="f4984-105">Applies a unitary operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneCA<'T> (result : Result, (op : ('T => Unit is Adj + Ctl), target : 'T)) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="f4984-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f4984-106">Description</span></span>

<span data-ttu-id="f4984-107">Data un'operazione `op` e un valore `result` di risultato, si applica `op` a `target` se `result` è `One` .</span><span class="sxs-lookup"><span data-stu-id="f4984-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="f4984-108">Se `Zero` , non viene eseguita alcuna operazione in `target` .</span><span class="sxs-lookup"><span data-stu-id="f4984-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="f4984-109">Il suffisso `CA` indica che l'operazione da applicare è unitaria (controllabile e adjointable).</span><span class="sxs-lookup"><span data-stu-id="f4984-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="f4984-110">Input</span><span class="sxs-lookup"><span data-stu-id="f4984-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="f4984-111">risultato: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="f4984-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="f4984-112">Risultato della misurazione che controlla se op viene applicato o meno.</span><span class="sxs-lookup"><span data-stu-id="f4984-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="f4984-113">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="f4984-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="f4984-114">Operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="f4984-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="f4984-115">destinazione:' t</span><span class="sxs-lookup"><span data-stu-id="f4984-115">target : 'T</span></span>

<span data-ttu-id="f4984-116">Input a cui viene applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="f4984-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f4984-117">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f4984-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f4984-118">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="f4984-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f4984-119">T</span><span class="sxs-lookup"><span data-stu-id="f4984-119">'T</span></span>

<span data-ttu-id="f4984-120">Tipo di input dell'operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="f4984-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="f4984-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4984-121">See Also</span></span>

- [<span data-ttu-id="f4984-122">Microsoft. Quantum. Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="f4984-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="f4984-123">Microsoft. Quantum. Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="f4984-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="f4984-124">Microsoft. Quantum. Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="f4984-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)