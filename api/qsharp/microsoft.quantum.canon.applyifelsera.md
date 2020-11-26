---
uid: Microsoft.Quantum.Canon.ApplyIfElseRA
title: Operazione ApplyIfElseRA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRA
qsharp.summary: Applies one of two adjointable operations, depending on the value of a classical result.
ms.openlocfilehash: 3ebd09b1e5876ff397f3524ba828ba26a271e91e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218598"
---
# <a name="applyifelsera-operation"></a><span data-ttu-id="c31d9-102">Operazione ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="c31d9-102">ApplyIfElseRA operation</span></span>

<span data-ttu-id="c31d9-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c31d9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c31d9-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c31d9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c31d9-105">Applica una delle due operazioni adjointable, a seconda del valore di un risultato classico.</span><span class="sxs-lookup"><span data-stu-id="c31d9-105">Applies one of two adjointable operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseRA<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Adj), zeroInput : 'T), (oneOp : ('U => Unit is Adj), oneInput : 'U)) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="c31d9-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c31d9-106">Description</span></span>

<span data-ttu-id="c31d9-107">Dato un risultato `result` , applica l'operazione `zeroOp` con `zeroInput` come input quando `result` è uguale a `Zero` e si applica `oneOp(oneInput)` quando `result == One` .</span><span class="sxs-lookup"><span data-stu-id="c31d9-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="c31d9-108">Input</span><span class="sxs-lookup"><span data-stu-id="c31d9-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="c31d9-109">risultato: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="c31d9-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="c31d9-110">Risultato della misurazione usato per determinare se `zeroOp` `oneOp` viene applicato o.</span><span class="sxs-lookup"><span data-stu-id="c31d9-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit--is-adj"></a><span data-ttu-id="c31d9-111">zeroOp:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ</span><span class="sxs-lookup"><span data-stu-id="c31d9-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="c31d9-112">Operazione adjointable da applicare quando `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="c31d9-112">The adjointable operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="c31d9-113">zeroInput: t</span><span class="sxs-lookup"><span data-stu-id="c31d9-113">zeroInput : 'T</span></span>

<span data-ttu-id="c31d9-114">Input da fornire a `zeroOp` quando `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="c31d9-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit--is-adj"></a><span data-ttu-id="c31d9-115">oneOp:' U => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ</span><span class="sxs-lookup"><span data-stu-id="c31d9-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="c31d9-116">Operazione adjointable da applicare quando `result == One` .</span><span class="sxs-lookup"><span data-stu-id="c31d9-116">The adjointable operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="c31d9-117">oneInput:' U</span><span class="sxs-lookup"><span data-stu-id="c31d9-117">oneInput : 'U</span></span>

<span data-ttu-id="c31d9-118">Input da fornire a `oneOp` quando `result == One` .</span><span class="sxs-lookup"><span data-stu-id="c31d9-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c31d9-119">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c31d9-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c31d9-120">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="c31d9-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c31d9-121">T</span><span class="sxs-lookup"><span data-stu-id="c31d9-121">'T</span></span>

<span data-ttu-id="c31d9-122">Tipo di input dell'operazione `zeroOp` da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="c31d9-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="c31d9-123">' U</span><span class="sxs-lookup"><span data-stu-id="c31d9-123">'U</span></span>

<span data-ttu-id="c31d9-124">Tipo di input dell'operazione `oneOp` da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="c31d9-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="c31d9-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c31d9-125">See Also</span></span>

- [<span data-ttu-id="c31d9-126">Microsoft. Quantum. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="c31d9-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="c31d9-127">Microsoft. Quantum. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="c31d9-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="c31d9-128">Microsoft. Quantum. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="c31d9-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="c31d9-129">Microsoft. Quantum. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="c31d9-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="c31d9-130">Microsoft. Quantum. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="c31d9-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)