---
uid: Microsoft.Quantum.Canon.ApplyIfElseBA
title: Operazione ApplyIfElseBA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBA
qsharp.summary: Applies one of two adjointable operations, depending on the value of a classical bit.
ms.openlocfilehash: 74d43344481c5a808e84ce9c9e36fa3e83cd0d89
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218666"
---
# <a name="applyifelseba-operation"></a><span data-ttu-id="e86a5-102">Operazione ApplyIfElseBA</span><span class="sxs-lookup"><span data-stu-id="e86a5-102">ApplyIfElseBA operation</span></span>

<span data-ttu-id="e86a5-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e86a5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e86a5-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e86a5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e86a5-105">Applica una delle due operazioni adjointable, a seconda del valore di un bit classico.</span><span class="sxs-lookup"><span data-stu-id="e86a5-105">Applies one of two adjointable operations, depending on the value of a classical bit.</span></span>

```qsharp
operation ApplyIfElseBA<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Adj), trueInput : 'T), (falseOp : ('U => Unit is Adj), falseInput : 'U)) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="e86a5-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e86a5-106">Description</span></span>

<span data-ttu-id="e86a5-107">Dato un bit `bit` , applica l'operazione `trueOp` con `trueInput` come input quando `bit` è `true` e si applica `falseOp(falseInput)` quando `bit` è `false` .</span><span class="sxs-lookup"><span data-stu-id="e86a5-107">Given a bit `bit`, applies the operation `trueOp` with `trueInput` as its input when `bit` is `true`, and applies `falseOp(falseInput)` when `bit` is `false`.</span></span>

## <a name="input"></a><span data-ttu-id="e86a5-108">Input</span><span class="sxs-lookup"><span data-stu-id="e86a5-108">Input</span></span>

### <a name="bit--bool"></a><span data-ttu-id="e86a5-109">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e86a5-109">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e86a5-110">Valore booleano utilizzato per determinare se `trueOp` `falseOp` viene applicato o.</span><span class="sxs-lookup"><span data-stu-id="e86a5-110">The boolean value used to determine whether `trueOp` or `falseOp` is applied.</span></span>


### <a name="trueop--t--unit--is-adj"></a><span data-ttu-id="e86a5-111">trueOp:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ</span><span class="sxs-lookup"><span data-stu-id="e86a5-111">trueOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="e86a5-112">Operazione adjointable da applicare quando `bit` è `true` .</span><span class="sxs-lookup"><span data-stu-id="e86a5-112">The adjointable operation to be applied when `bit` is `true`.</span></span>


### <a name="trueinput--t"></a><span data-ttu-id="e86a5-113">trueInput: t</span><span class="sxs-lookup"><span data-stu-id="e86a5-113">trueInput : 'T</span></span>

<span data-ttu-id="e86a5-114">Input da fornire a `trueOp` quando `bit` è `true` .</span><span class="sxs-lookup"><span data-stu-id="e86a5-114">The input to be provided to `trueOp` when `bit` is `true`.</span></span>


### <a name="falseop--u--unit--is-adj"></a><span data-ttu-id="e86a5-115">falseOp:' U => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ</span><span class="sxs-lookup"><span data-stu-id="e86a5-115">falseOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="e86a5-116">Operazione adjointable da applicare quando `bit` è `false` .</span><span class="sxs-lookup"><span data-stu-id="e86a5-116">The adjointable operation to be applied when `bit` is `false`.</span></span>


### <a name="falseinput--u"></a><span data-ttu-id="e86a5-117">falseInput:' U</span><span class="sxs-lookup"><span data-stu-id="e86a5-117">falseInput : 'U</span></span>

<span data-ttu-id="e86a5-118">Input da fornire a `falseOp` quando `bit` è `false` .</span><span class="sxs-lookup"><span data-stu-id="e86a5-118">The input to be provided to `falseOp` when `bit` is `false`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e86a5-119">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e86a5-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e86a5-120">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="e86a5-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e86a5-121">T</span><span class="sxs-lookup"><span data-stu-id="e86a5-121">'T</span></span>

<span data-ttu-id="e86a5-122">Tipo di input dell'operazione `trueOp` da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="e86a5-122">The input type of the operation `trueOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="e86a5-123">' U</span><span class="sxs-lookup"><span data-stu-id="e86a5-123">'U</span></span>

<span data-ttu-id="e86a5-124">Tipo di input dell'operazione `falseOp` da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="e86a5-124">The input type of the operation `falseOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="e86a5-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e86a5-125">See Also</span></span>

- [<span data-ttu-id="e86a5-126">Microsoft. Quantum. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="e86a5-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="e86a5-127">Microsoft. Quantum. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="e86a5-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="e86a5-128">Microsoft. Quantum. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="e86a5-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="e86a5-129">Microsoft. Quantum. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="e86a5-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="e86a5-130">Microsoft. Quantum. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="e86a5-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)