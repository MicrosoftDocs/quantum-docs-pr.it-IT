---
uid: Microsoft.Quantum.Canon.ApplyIfOneC
title: Operazione ApplyIfOneC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneC
qsharp.summary: Applies a controllable operation conditioned on a classical result value being one.
ms.openlocfilehash: ebeec5b46567892ad30f194ababb42876ba08bcb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841764"
---
# <a name="applyifonec-operation"></a><span data-ttu-id="bf3de-102">Operazione ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="bf3de-102">ApplyIfOneC operation</span></span>

<span data-ttu-id="bf3de-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bf3de-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bf3de-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bf3de-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bf3de-105">Applica un'operazione controllabile con un valore di risultato classico che è uno.</span><span class="sxs-lookup"><span data-stu-id="bf3de-105">Applies a controllable operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneC<'T> (result : Result, (op : ('T => Unit is Ctl), target : 'T)) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="bf3de-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bf3de-106">Description</span></span>

<span data-ttu-id="bf3de-107">Data un'operazione `op` e un valore `result` di risultato, si applica `op` a `target` se `result` è `One` .</span><span class="sxs-lookup"><span data-stu-id="bf3de-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="bf3de-108">Se `Zero` , non viene eseguita alcuna operazione in `target` .</span><span class="sxs-lookup"><span data-stu-id="bf3de-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="bf3de-109">Il suffisso `C` indica che l'operazione da applicare è controllabile.</span><span class="sxs-lookup"><span data-stu-id="bf3de-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="bf3de-110">Input</span><span class="sxs-lookup"><span data-stu-id="bf3de-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="bf3de-111">risultato: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="bf3de-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="bf3de-112">Risultato della misurazione che controlla se op viene applicato o meno.</span><span class="sxs-lookup"><span data-stu-id="bf3de-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="bf3de-113">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL</span><span class="sxs-lookup"><span data-stu-id="bf3de-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="bf3de-114">Operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="bf3de-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="bf3de-115">destinazione:' t</span><span class="sxs-lookup"><span data-stu-id="bf3de-115">target : 'T</span></span>

<span data-ttu-id="bf3de-116">Input a cui viene applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="bf3de-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bf3de-117">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bf3de-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bf3de-118">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="bf3de-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bf3de-119">T</span><span class="sxs-lookup"><span data-stu-id="bf3de-119">'T</span></span>

<span data-ttu-id="bf3de-120">Tipo di input dell'operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="bf3de-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="bf3de-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf3de-121">See Also</span></span>

- [<span data-ttu-id="bf3de-122">Microsoft. Quantum. Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="bf3de-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="bf3de-123">Microsoft. Quantum. Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="bf3de-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="bf3de-124">Microsoft. Quantum. Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="bf3de-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)