---
uid: Microsoft.Quantum.Canon.ApplyIfElseR
title: Operazione ApplyIfElseR
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseR
qsharp.summary: Applies one of two operations, depending on the value of a classical result.
ms.openlocfilehash: 874dae2ba5e842066e9c1582af431a73520e4ccd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209537"
---
# <a name="applyifelser-operation"></a><span data-ttu-id="4dc89-102">Operazione ApplyIfElseR</span><span class="sxs-lookup"><span data-stu-id="4dc89-102">ApplyIfElseR operation</span></span>

<span data-ttu-id="4dc89-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4dc89-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4dc89-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4dc89-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4dc89-105">Applica una delle due operazioni, a seconda del valore di un risultato classico.</span><span class="sxs-lookup"><span data-stu-id="4dc89-105">Applies one of two operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseR<'T, 'U> (result : Result, (zeroOp : ('T => Unit), zeroInput : 'T), (oneOp : ('U => Unit), oneInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="4dc89-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4dc89-106">Description</span></span>

<span data-ttu-id="4dc89-107">Dato un risultato `result` , applica l'operazione `zeroOp` con `zeroInput` come input quando `result` è uguale a `Zero` e si applica `oneOp(oneInput)` quando `result == One` .</span><span class="sxs-lookup"><span data-stu-id="4dc89-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="4dc89-108">Input</span><span class="sxs-lookup"><span data-stu-id="4dc89-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="4dc89-109">risultato: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="4dc89-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="4dc89-110">Risultato della misurazione usato per determinare se `zeroOp` `oneOp` viene applicato o.</span><span class="sxs-lookup"><span data-stu-id="4dc89-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit"></a><span data-ttu-id="4dc89-111">zeroOp:' t = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="4dc89-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="4dc89-112">Operazione da applicare quando `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="4dc89-112">The operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="4dc89-113">zeroInput: t</span><span class="sxs-lookup"><span data-stu-id="4dc89-113">zeroInput : 'T</span></span>

<span data-ttu-id="4dc89-114">Input da fornire a `zeroOp` quando `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="4dc89-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit"></a><span data-ttu-id="4dc89-115">oneOp:' U = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="4dc89-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="4dc89-116">Operazione da applicare quando `result == One` .</span><span class="sxs-lookup"><span data-stu-id="4dc89-116">The operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="4dc89-117">oneInput:' U</span><span class="sxs-lookup"><span data-stu-id="4dc89-117">oneInput : 'U</span></span>

<span data-ttu-id="4dc89-118">Input da fornire a `oneOp` quando `result == One` .</span><span class="sxs-lookup"><span data-stu-id="4dc89-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4dc89-119">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4dc89-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4dc89-120">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="4dc89-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4dc89-121">T</span><span class="sxs-lookup"><span data-stu-id="4dc89-121">'T</span></span>

<span data-ttu-id="4dc89-122">Tipo di input dell'operazione `zeroOp` da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="4dc89-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="4dc89-123">' U</span><span class="sxs-lookup"><span data-stu-id="4dc89-123">'U</span></span>

<span data-ttu-id="4dc89-124">Tipo di input dell'operazione `oneOp` da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="4dc89-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="4dc89-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4dc89-125">See Also</span></span>

- [<span data-ttu-id="4dc89-126">Microsoft. Quantum. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="4dc89-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="4dc89-127">Microsoft. Quantum. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="4dc89-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="4dc89-128">Microsoft. Quantum. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="4dc89-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="4dc89-129">Microsoft. Quantum. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="4dc89-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="4dc89-130">Microsoft. Quantum. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="4dc89-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)