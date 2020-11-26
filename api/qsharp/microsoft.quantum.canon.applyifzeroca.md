---
uid: Microsoft.Quantum.Canon.ApplyIfZeroCA
title: Operazione ApplyIfZeroCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroCA
qsharp.summary: Applies a unitary operation conditioned on a classical result value being zero.
ms.openlocfilehash: 4baae1fe7d615cbbf01935b4eca05fe947ff296e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218462"
---
# <a name="applyifzeroca-operation"></a><span data-ttu-id="75d82-102">Operazione ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="75d82-102">ApplyIfZeroCA operation</span></span>

<span data-ttu-id="75d82-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="75d82-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="75d82-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="75d82-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="75d82-105">Applica un'operazione unitaria condizionata a un valore di risultato classico che è zero.</span><span class="sxs-lookup"><span data-stu-id="75d82-105">Applies a unitary operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZeroCA<'T> (result : Result, (op : ('T => Unit is Adj + Ctl), target : 'T)) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="75d82-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="75d82-106">Description</span></span>

<span data-ttu-id="75d82-107">Data un'operazione `op` e un valore `result` di risultato, si applica `op` a `target` se `result` è `Zero` .</span><span class="sxs-lookup"><span data-stu-id="75d82-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="75d82-108">Se `One` , non viene eseguita alcuna operazione in `target` .</span><span class="sxs-lookup"><span data-stu-id="75d82-108">If `One`, nothing happens to the `target`.</span></span>
<span data-ttu-id="75d82-109">Il suffisso `CA` indica che l'operazione da applicare è unitaria (controllabile e adjointable).</span><span class="sxs-lookup"><span data-stu-id="75d82-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="75d82-110">Input</span><span class="sxs-lookup"><span data-stu-id="75d82-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="75d82-111">risultato: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="75d82-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="75d82-112">Risultato della misurazione che controlla se op viene applicato o meno.</span><span class="sxs-lookup"><span data-stu-id="75d82-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="75d82-113">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="75d82-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="75d82-114">Operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="75d82-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="75d82-115">destinazione:' t</span><span class="sxs-lookup"><span data-stu-id="75d82-115">target : 'T</span></span>

<span data-ttu-id="75d82-116">Input a cui viene applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="75d82-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="75d82-117">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="75d82-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="75d82-118">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="75d82-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="75d82-119">T</span><span class="sxs-lookup"><span data-stu-id="75d82-119">'T</span></span>

<span data-ttu-id="75d82-120">Tipo di input dell'operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="75d82-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="75d82-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75d82-121">See Also</span></span>

- [<span data-ttu-id="75d82-122">Microsoft. Quantum. Canon. ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="75d82-122">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="75d82-123">Microsoft. Quantum. Canon. ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="75d82-123">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="75d82-124">Microsoft. Quantum. Canon. ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="75d82-124">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)