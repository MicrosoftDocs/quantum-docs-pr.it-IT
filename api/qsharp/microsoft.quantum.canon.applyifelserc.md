---
uid: Microsoft.Quantum.Canon.ApplyIfElseRC
title: Operazione ApplyIfElseRC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRC
qsharp.summary: Applies one of two controllable operations, depending on the value of a classical result.
ms.openlocfilehash: bac763168dbc7379691f850a79cbb6e61639ba89
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841796"
---
# <a name="applyifelserc-operation"></a><span data-ttu-id="dc8fc-102">Operazione ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="dc8fc-102">ApplyIfElseRC operation</span></span>

<span data-ttu-id="dc8fc-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dc8fc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dc8fc-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dc8fc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dc8fc-105">Applica una delle due operazioni controllabili, a seconda del valore di un risultato classico.</span><span class="sxs-lookup"><span data-stu-id="dc8fc-105">Applies one of two controllable operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseRC<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Ctl), zeroInput : 'T), (oneOp : ('U => Unit is Ctl), oneInput : 'U)) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="dc8fc-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dc8fc-106">Description</span></span>

<span data-ttu-id="dc8fc-107">Dato un risultato `result` , applica l'operazione `zeroOp` con `zeroInput` come input quando `result` è uguale a `Zero` e si applica `oneOp(oneInput)` quando `result == One` .</span><span class="sxs-lookup"><span data-stu-id="dc8fc-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="dc8fc-108">Input</span><span class="sxs-lookup"><span data-stu-id="dc8fc-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="dc8fc-109">risultato: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="dc8fc-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="dc8fc-110">Risultato della misurazione usato per determinare se `zeroOp` `oneOp` viene applicato o.</span><span class="sxs-lookup"><span data-stu-id="dc8fc-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit--is-ctl"></a><span data-ttu-id="dc8fc-111">zeroOp:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL</span><span class="sxs-lookup"><span data-stu-id="dc8fc-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="dc8fc-112">Operazione controllabile da applicare quando `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="dc8fc-112">The controllable operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="dc8fc-113">zeroInput: t</span><span class="sxs-lookup"><span data-stu-id="dc8fc-113">zeroInput : 'T</span></span>

<span data-ttu-id="dc8fc-114">Input da fornire a `zeroOp` quando `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="dc8fc-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit--is-ctl"></a><span data-ttu-id="dc8fc-115">oneOp:' U => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL</span><span class="sxs-lookup"><span data-stu-id="dc8fc-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="dc8fc-116">Operazione controllabile da applicare quando `result == One` .</span><span class="sxs-lookup"><span data-stu-id="dc8fc-116">The controllable operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="dc8fc-117">oneInput:' U</span><span class="sxs-lookup"><span data-stu-id="dc8fc-117">oneInput : 'U</span></span>

<span data-ttu-id="dc8fc-118">Input da fornire a `oneOp` quando `result == One` .</span><span class="sxs-lookup"><span data-stu-id="dc8fc-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dc8fc-119">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dc8fc-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="dc8fc-120">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="dc8fc-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dc8fc-121">T</span><span class="sxs-lookup"><span data-stu-id="dc8fc-121">'T</span></span>

<span data-ttu-id="dc8fc-122">Tipo di input dell'operazione `zeroOp` da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="dc8fc-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="dc8fc-123">' U</span><span class="sxs-lookup"><span data-stu-id="dc8fc-123">'U</span></span>

<span data-ttu-id="dc8fc-124">Tipo di input dell'operazione `oneOp` da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="dc8fc-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc8fc-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc8fc-125">See Also</span></span>

- [<span data-ttu-id="dc8fc-126">Microsoft. Quantum. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="dc8fc-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="dc8fc-127">Microsoft. Quantum. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="dc8fc-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="dc8fc-128">Microsoft. Quantum. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="dc8fc-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="dc8fc-129">Microsoft. Quantum. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="dc8fc-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="dc8fc-130">Microsoft. Quantum. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="dc8fc-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)