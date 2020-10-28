---
uid: Microsoft.Quantum.Canon.ApplyIfZeroC
title: Operazione ApplyIfZeroC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroC
qsharp.summary: Applies a controllable operation conditioned on a classical result value being zero.
ms.openlocfilehash: cfc2a659f4da011baadff1a0d6a20a2a36d0a285
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718010"
---
# <a name="applyifzeroc-operation"></a><span data-ttu-id="79eda-102">Operazione ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="79eda-102">ApplyIfZeroC operation</span></span>

<span data-ttu-id="79eda-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="79eda-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="79eda-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="79eda-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="79eda-105">Applica un'operazione controllabile con un valore di risultato classico pari a zero.</span><span class="sxs-lookup"><span data-stu-id="79eda-105">Applies a controllable operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZeroC<'T> (result : Result, (op : ('T => Unit is Ctl), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="79eda-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="79eda-106">Description</span></span>

<span data-ttu-id="79eda-107">Data un'operazione `op` e un valore `result` di risultato, si applica `op` a `target` se `result` è `Zero` .</span><span class="sxs-lookup"><span data-stu-id="79eda-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="79eda-108">Se `One` , non viene eseguita alcuna operazione in `target` .</span><span class="sxs-lookup"><span data-stu-id="79eda-108">If `One`, nothing happens to the `target`.</span></span>
<span data-ttu-id="79eda-109">Il suffisso `C` indica che l'operazione da applicare è controllabile.</span><span class="sxs-lookup"><span data-stu-id="79eda-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="79eda-110">Input</span><span class="sxs-lookup"><span data-stu-id="79eda-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="79eda-111">risultato: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="79eda-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="79eda-112">Risultato della misurazione che controlla se op viene applicato o meno.</span><span class="sxs-lookup"><span data-stu-id="79eda-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit-ctl"></a><span data-ttu-id="79eda-113">op:' t => CTL [unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="79eda-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="79eda-114">Operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="79eda-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="79eda-115">destinazione:' t</span><span class="sxs-lookup"><span data-stu-id="79eda-115">target : 'T</span></span>

<span data-ttu-id="79eda-116">Input a cui viene applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="79eda-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="79eda-117">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="79eda-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="79eda-118">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="79eda-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="79eda-119">T</span><span class="sxs-lookup"><span data-stu-id="79eda-119">'T</span></span>

<span data-ttu-id="79eda-120">Tipo di input dell'operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="79eda-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="79eda-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79eda-121">See Also</span></span>

- [<span data-ttu-id="79eda-122">Microsoft. Quantum. Canon. ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="79eda-122">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="79eda-123">Microsoft. Quantum. Canon. ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="79eda-123">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="79eda-124">Microsoft. Quantum. Canon. ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="79eda-124">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)