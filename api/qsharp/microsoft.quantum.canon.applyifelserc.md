---
uid: Microsoft.Quantum.Canon.ApplyIfElseRC
title: Operazione ApplyIfElseRC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRC
qsharp.summary: Applies one of two controllable operations, depending on the value of a classical result.
ms.openlocfilehash: 45bd0f46fb2e28c5c9aaa21cb7ec065baf279d2a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718119"
---
# <a name="applyifelserc-operation"></a><span data-ttu-id="51c7e-102">Operazione ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="51c7e-102">ApplyIfElseRC operation</span></span>

<span data-ttu-id="51c7e-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="51c7e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="51c7e-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="51c7e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="51c7e-105">Applica una delle due operazioni controllabili, a seconda del valore di un risultato classico.</span><span class="sxs-lookup"><span data-stu-id="51c7e-105">Applies one of two controllable operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseRC<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Ctl), zeroInput : 'T), (oneOp : ('U => Unit is Ctl), oneInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="51c7e-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51c7e-106">Description</span></span>

<span data-ttu-id="51c7e-107">Dato un risultato `result` , applica l'operazione `zeroOp` con `zeroInput` come input quando `result` è uguale a `Zero` e si applica `oneOp(oneInput)` quando `result == One` .</span><span class="sxs-lookup"><span data-stu-id="51c7e-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="51c7e-108">Input</span><span class="sxs-lookup"><span data-stu-id="51c7e-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="51c7e-109">risultato: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="51c7e-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="51c7e-110">Risultato della misurazione usato per determinare se `zeroOp` `oneOp` viene applicato o.</span><span class="sxs-lookup"><span data-stu-id="51c7e-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit-ctl"></a><span data-ttu-id="51c7e-111">zeroOp:' t => CTL [unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="51c7e-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="51c7e-112">Operazione controllabile da applicare quando `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="51c7e-112">The controllable operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="51c7e-113">zeroInput: t</span><span class="sxs-lookup"><span data-stu-id="51c7e-113">zeroInput : 'T</span></span>

<span data-ttu-id="51c7e-114">Input da fornire a `zeroOp` quando `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="51c7e-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit-ctl"></a><span data-ttu-id="51c7e-115">oneOp:' U => CTL [unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="51c7e-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="51c7e-116">Operazione controllabile da applicare quando `result == One` .</span><span class="sxs-lookup"><span data-stu-id="51c7e-116">The controllable operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="51c7e-117">oneInput:' U</span><span class="sxs-lookup"><span data-stu-id="51c7e-117">oneInput : 'U</span></span>

<span data-ttu-id="51c7e-118">Input da fornire a `oneOp` quando `result == One` .</span><span class="sxs-lookup"><span data-stu-id="51c7e-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="51c7e-119">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="51c7e-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="51c7e-120">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="51c7e-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="51c7e-121">T</span><span class="sxs-lookup"><span data-stu-id="51c7e-121">'T</span></span>

<span data-ttu-id="51c7e-122">Tipo di input dell'operazione `zeroOp` da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="51c7e-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="51c7e-123">' U</span><span class="sxs-lookup"><span data-stu-id="51c7e-123">'U</span></span>

<span data-ttu-id="51c7e-124">Tipo di input dell'operazione `oneOp` da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="51c7e-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="51c7e-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51c7e-125">See Also</span></span>

- [<span data-ttu-id="51c7e-126">Microsoft. Quantum. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="51c7e-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="51c7e-127">Microsoft. Quantum. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="51c7e-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="51c7e-128">Microsoft. Quantum. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="51c7e-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="51c7e-129">Microsoft. Quantum. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="51c7e-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="51c7e-130">Microsoft. Quantum. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="51c7e-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)