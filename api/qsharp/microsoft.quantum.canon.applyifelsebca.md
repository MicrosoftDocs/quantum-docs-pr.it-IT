---
uid: Microsoft.Quantum.Canon.ApplyIfElseBCA
title: Operazione ApplyIfElseBCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBCA
qsharp.summary: Applies one of two unitary operations, depending on the value of a classical bit.
ms.openlocfilehash: 3ed9d7cbf277f4c3acd0e6c3b5f920c3e140855d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844964"
---
# <a name="applyifelsebca-operation"></a><span data-ttu-id="45bc8-102">Operazione ApplyIfElseBCA</span><span class="sxs-lookup"><span data-stu-id="45bc8-102">ApplyIfElseBCA operation</span></span>

<span data-ttu-id="45bc8-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="45bc8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="45bc8-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="45bc8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="45bc8-105">Applica una delle due operazioni unitarie, a seconda del valore di un bit classico.</span><span class="sxs-lookup"><span data-stu-id="45bc8-105">Applies one of two unitary operations, depending on the value of a classical bit.</span></span>

```qsharp
operation ApplyIfElseBCA<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Adj + Ctl), trueInput : 'T), (falseOp : ('U => Unit is Adj + Ctl), falseInput : 'U)) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="45bc8-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="45bc8-106">Description</span></span>

<span data-ttu-id="45bc8-107">Dato un bit `bit` , applica l'operazione `trueOp` con `trueInput` come input quando `bit` è `true` e si applica `falseOp(falseInput)` quando `bit` è `false` .</span><span class="sxs-lookup"><span data-stu-id="45bc8-107">Given a bit `bit`, applies the operation `trueOp` with `trueInput` as its input when `bit` is `true`, and applies `falseOp(falseInput)` when `bit` is `false`.</span></span>

## <a name="input"></a><span data-ttu-id="45bc8-108">Input</span><span class="sxs-lookup"><span data-stu-id="45bc8-108">Input</span></span>

### <a name="bit--bool"></a><span data-ttu-id="45bc8-109">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="45bc8-109">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="45bc8-110">Valore booleano utilizzato per determinare se `trueOp` `falseOp` viene applicato o.</span><span class="sxs-lookup"><span data-stu-id="45bc8-110">The boolean value used to determine whether `trueOp` or `falseOp` is applied.</span></span>


### <a name="trueop--t--unit--is-adj--ctl"></a><span data-ttu-id="45bc8-111">trueOp:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="45bc8-111">trueOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="45bc8-112">Operazione unitaria da applicare quando `bit` è `true` .</span><span class="sxs-lookup"><span data-stu-id="45bc8-112">The unitary operation to be applied when `bit` is `true`.</span></span>


### <a name="trueinput--t"></a><span data-ttu-id="45bc8-113">trueInput: t</span><span class="sxs-lookup"><span data-stu-id="45bc8-113">trueInput : 'T</span></span>

<span data-ttu-id="45bc8-114">Input da fornire a `trueOp` quando `bit` è `true` .</span><span class="sxs-lookup"><span data-stu-id="45bc8-114">The input to be provided to `trueOp` when `bit` is `true`.</span></span>


### <a name="falseop--u--unit--is-adj--ctl"></a><span data-ttu-id="45bc8-115">falseOp:' U => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="45bc8-115">falseOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="45bc8-116">Operazione unitaria da applicare quando `bit` è `false` .</span><span class="sxs-lookup"><span data-stu-id="45bc8-116">The unitary operation to be applied when `bit` is `false`.</span></span>


### <a name="falseinput--u"></a><span data-ttu-id="45bc8-117">falseInput:' U</span><span class="sxs-lookup"><span data-stu-id="45bc8-117">falseInput : 'U</span></span>

<span data-ttu-id="45bc8-118">Input da fornire a `falseOp` quando `bit` è `false` .</span><span class="sxs-lookup"><span data-stu-id="45bc8-118">The input to be provided to `falseOp` when `bit` is `false`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="45bc8-119">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="45bc8-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="45bc8-120">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="45bc8-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="45bc8-121">T</span><span class="sxs-lookup"><span data-stu-id="45bc8-121">'T</span></span>

<span data-ttu-id="45bc8-122">Tipo di input dell'operazione `trueOp` da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="45bc8-122">The input type of the operation `trueOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="45bc8-123">' U</span><span class="sxs-lookup"><span data-stu-id="45bc8-123">'U</span></span>

<span data-ttu-id="45bc8-124">Tipo di input dell'operazione `falseOp` da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="45bc8-124">The input type of the operation `falseOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="45bc8-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45bc8-125">See Also</span></span>

- [<span data-ttu-id="45bc8-126">Microsoft. Quantum. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="45bc8-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="45bc8-127">Microsoft. Quantum. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="45bc8-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="45bc8-128">Microsoft. Quantum. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="45bc8-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="45bc8-129">Microsoft. Quantum. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="45bc8-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="45bc8-130">Microsoft. Quantum. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="45bc8-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)