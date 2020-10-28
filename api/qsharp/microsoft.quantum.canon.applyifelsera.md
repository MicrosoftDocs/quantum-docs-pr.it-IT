---
uid: Microsoft.Quantum.Canon.ApplyIfElseRA
title: Operazione ApplyIfElseRA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRA
qsharp.summary: Applies one of two adjointable operations, depending on the value of a classical result.
ms.openlocfilehash: d0181d98a9867f71d8a8f8dea4331e5a13f9e59c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718147"
---
# <a name="applyifelsera-operation"></a><span data-ttu-id="bfe2d-102">Operazione ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="bfe2d-102">ApplyIfElseRA operation</span></span>

<span data-ttu-id="bfe2d-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bfe2d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bfe2d-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bfe2d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bfe2d-105">Applica una delle due operazioni adjointable, a seconda del valore di un risultato classico.</span><span class="sxs-lookup"><span data-stu-id="bfe2d-105">Applies one of two adjointable operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseRA<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Adj), zeroInput : 'T), (oneOp : ('U => Unit is Adj), oneInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="bfe2d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bfe2d-106">Description</span></span>

<span data-ttu-id="bfe2d-107">Dato un risultato `result` , applica l'operazione `zeroOp` con `zeroInput` come input quando `result` è uguale a `Zero` e si applica `oneOp(oneInput)` quando `result == One` .</span><span class="sxs-lookup"><span data-stu-id="bfe2d-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="bfe2d-108">Input</span><span class="sxs-lookup"><span data-stu-id="bfe2d-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="bfe2d-109">risultato: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="bfe2d-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="bfe2d-110">Risultato della misurazione usato per determinare se `zeroOp` `oneOp` viene applicato o.</span><span class="sxs-lookup"><span data-stu-id="bfe2d-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit-adj"></a><span data-ttu-id="bfe2d-111">zeroOp:' t => ADJ [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bfe2d-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="bfe2d-112">Operazione adjointable da applicare quando `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="bfe2d-112">The adjointable operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="bfe2d-113">zeroInput: t</span><span class="sxs-lookup"><span data-stu-id="bfe2d-113">zeroInput : 'T</span></span>

<span data-ttu-id="bfe2d-114">Input da fornire a `zeroOp` quando `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="bfe2d-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit-adj"></a><span data-ttu-id="bfe2d-115">oneOp:' U => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ</span><span class="sxs-lookup"><span data-stu-id="bfe2d-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="bfe2d-116">Operazione adjointable da applicare quando `result == One` .</span><span class="sxs-lookup"><span data-stu-id="bfe2d-116">The adjointable operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="bfe2d-117">oneInput:' U</span><span class="sxs-lookup"><span data-stu-id="bfe2d-117">oneInput : 'U</span></span>

<span data-ttu-id="bfe2d-118">Input da fornire a `oneOp` quando `result == One` .</span><span class="sxs-lookup"><span data-stu-id="bfe2d-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bfe2d-119">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bfe2d-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bfe2d-120">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="bfe2d-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bfe2d-121">T</span><span class="sxs-lookup"><span data-stu-id="bfe2d-121">'T</span></span>

<span data-ttu-id="bfe2d-122">Tipo di input dell'operazione `zeroOp` da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="bfe2d-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="bfe2d-123">' U</span><span class="sxs-lookup"><span data-stu-id="bfe2d-123">'U</span></span>

<span data-ttu-id="bfe2d-124">Tipo di input dell'operazione `oneOp` da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="bfe2d-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="bfe2d-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bfe2d-125">See Also</span></span>

- [<span data-ttu-id="bfe2d-126">Microsoft. Quantum. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="bfe2d-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="bfe2d-127">Microsoft. Quantum. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="bfe2d-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="bfe2d-128">Microsoft. Quantum. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="bfe2d-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="bfe2d-129">Microsoft. Quantum. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="bfe2d-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="bfe2d-130">Microsoft. Quantum. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="bfe2d-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)