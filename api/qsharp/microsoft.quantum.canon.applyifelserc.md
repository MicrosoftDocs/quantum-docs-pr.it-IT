---
uid: Microsoft.Quantum.Canon.ApplyIfElseRC
title: Operazione ApplyIfElseRC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRC
qsharp.summary: Applies one of two controllable operations, depending on the value of a classical result.
ms.openlocfilehash: b2e4ade84b25b0100fe4b69814c760a672833f06
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209486"
---
# <a name="applyifelserc-operation"></a><span data-ttu-id="7750a-102">Operazione ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="7750a-102">ApplyIfElseRC operation</span></span>

<span data-ttu-id="7750a-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7750a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7750a-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7750a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7750a-105">Applica una delle due operazioni controllabili, a seconda del valore di un risultato classico.</span><span class="sxs-lookup"><span data-stu-id="7750a-105">Applies one of two controllable operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseRC<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Ctl), zeroInput : 'T), (oneOp : ('U => Unit is Ctl), oneInput : 'U)) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="7750a-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7750a-106">Description</span></span>

<span data-ttu-id="7750a-107">Dato un risultato `result` , applica l'operazione `zeroOp` con `zeroInput` come input quando `result` è uguale a `Zero` e si applica `oneOp(oneInput)` quando `result == One` .</span><span class="sxs-lookup"><span data-stu-id="7750a-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="7750a-108">Input</span><span class="sxs-lookup"><span data-stu-id="7750a-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="7750a-109">risultato: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="7750a-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="7750a-110">Risultato della misurazione usato per determinare se `zeroOp` `oneOp` viene applicato o.</span><span class="sxs-lookup"><span data-stu-id="7750a-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit--is-ctl"></a><span data-ttu-id="7750a-111">zeroOp:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL</span><span class="sxs-lookup"><span data-stu-id="7750a-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="7750a-112">Operazione controllabile da applicare quando `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="7750a-112">The controllable operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="7750a-113">zeroInput: t</span><span class="sxs-lookup"><span data-stu-id="7750a-113">zeroInput : 'T</span></span>

<span data-ttu-id="7750a-114">Input da fornire a `zeroOp` quando `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="7750a-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit--is-ctl"></a><span data-ttu-id="7750a-115">oneOp:' U => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL</span><span class="sxs-lookup"><span data-stu-id="7750a-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="7750a-116">Operazione controllabile da applicare quando `result == One` .</span><span class="sxs-lookup"><span data-stu-id="7750a-116">The controllable operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="7750a-117">oneInput:' U</span><span class="sxs-lookup"><span data-stu-id="7750a-117">oneInput : 'U</span></span>

<span data-ttu-id="7750a-118">Input da fornire a `oneOp` quando `result == One` .</span><span class="sxs-lookup"><span data-stu-id="7750a-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7750a-119">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7750a-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7750a-120">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="7750a-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7750a-121">T</span><span class="sxs-lookup"><span data-stu-id="7750a-121">'T</span></span>

<span data-ttu-id="7750a-122">Tipo di input dell'operazione `zeroOp` da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="7750a-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="7750a-123">' U</span><span class="sxs-lookup"><span data-stu-id="7750a-123">'U</span></span>

<span data-ttu-id="7750a-124">Tipo di input dell'operazione `oneOp` da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="7750a-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="7750a-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7750a-125">See Also</span></span>

- [<span data-ttu-id="7750a-126">Microsoft. Quantum. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="7750a-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="7750a-127">Microsoft. Quantum. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="7750a-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="7750a-128">Microsoft. Quantum. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="7750a-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="7750a-129">Microsoft. Quantum. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="7750a-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="7750a-130">Microsoft. Quantum. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="7750a-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)