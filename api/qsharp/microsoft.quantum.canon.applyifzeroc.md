---
uid: Microsoft.Quantum.Canon.ApplyIfZeroC
title: Operazione ApplyIfZeroC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroC
qsharp.summary: Applies a controllable operation conditioned on a classical result value being zero.
ms.openlocfilehash: 3876e2baf1b3ad5bbfa0097d468b1e88adf05db4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841728"
---
# <a name="applyifzeroc-operation"></a><span data-ttu-id="559cc-102">Operazione ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="559cc-102">ApplyIfZeroC operation</span></span>

<span data-ttu-id="559cc-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="559cc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="559cc-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="559cc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="559cc-105">Applica un'operazione controllabile con un valore di risultato classico pari a zero.</span><span class="sxs-lookup"><span data-stu-id="559cc-105">Applies a controllable operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZeroC<'T> (result : Result, (op : ('T => Unit is Ctl), target : 'T)) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="559cc-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="559cc-106">Description</span></span>

<span data-ttu-id="559cc-107">Data un'operazione `op` e un valore `result` di risultato, si applica `op` a `target` se `result` è `Zero` .</span><span class="sxs-lookup"><span data-stu-id="559cc-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="559cc-108">Se `One` , non viene eseguita alcuna operazione in `target` .</span><span class="sxs-lookup"><span data-stu-id="559cc-108">If `One`, nothing happens to the `target`.</span></span>
<span data-ttu-id="559cc-109">Il suffisso `C` indica che l'operazione da applicare è controllabile.</span><span class="sxs-lookup"><span data-stu-id="559cc-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="559cc-110">Input</span><span class="sxs-lookup"><span data-stu-id="559cc-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="559cc-111">risultato: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="559cc-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="559cc-112">Risultato della misurazione che controlla se op viene applicato o meno.</span><span class="sxs-lookup"><span data-stu-id="559cc-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="559cc-113">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL</span><span class="sxs-lookup"><span data-stu-id="559cc-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="559cc-114">Operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="559cc-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="559cc-115">destinazione:' t</span><span class="sxs-lookup"><span data-stu-id="559cc-115">target : 'T</span></span>

<span data-ttu-id="559cc-116">Input a cui viene applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="559cc-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="559cc-117">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="559cc-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="559cc-118">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="559cc-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="559cc-119">T</span><span class="sxs-lookup"><span data-stu-id="559cc-119">'T</span></span>

<span data-ttu-id="559cc-120">Tipo di input dell'operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="559cc-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="559cc-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="559cc-121">See Also</span></span>

- [<span data-ttu-id="559cc-122">Microsoft. Quantum. Canon. ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="559cc-122">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="559cc-123">Microsoft. Quantum. Canon. ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="559cc-123">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="559cc-124">Microsoft. Quantum. Canon. ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="559cc-124">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)