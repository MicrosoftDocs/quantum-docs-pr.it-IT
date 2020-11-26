---
uid: Microsoft.Quantum.Canon.ApplyIfOne
title: Operazione ApplyIfOne
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOne
qsharp.summary: Applies an operation conditioned on a classical result value being one.
ms.openlocfilehash: b7c07e01ebcaf2d475283bea0695aa68dd10776e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209401"
---
# <a name="applyifone-operation"></a><span data-ttu-id="379c2-102">Operazione ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="379c2-102">ApplyIfOne operation</span></span>

<span data-ttu-id="379c2-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="379c2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="379c2-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="379c2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="379c2-105">Applica un'operazione condizionata su un valore di risultato classico.</span><span class="sxs-lookup"><span data-stu-id="379c2-105">Applies an operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOne<'T> (result : Result, (op : ('T => Unit), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="379c2-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="379c2-106">Description</span></span>

<span data-ttu-id="379c2-107">Data un'operazione `op` e un valore `result` di risultato, si applica `op` a `target` se `result` è `One` .</span><span class="sxs-lookup"><span data-stu-id="379c2-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="379c2-108">Se `Zero` , non viene eseguita alcuna operazione in `target` .</span><span class="sxs-lookup"><span data-stu-id="379c2-108">If `Zero`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="379c2-109">Input</span><span class="sxs-lookup"><span data-stu-id="379c2-109">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="379c2-110">risultato: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="379c2-110">result : __invalid<Result>__</span></span>

<span data-ttu-id="379c2-111">Risultato della misurazione che controlla se op viene applicato o meno.</span><span class="sxs-lookup"><span data-stu-id="379c2-111">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="379c2-112">op:' t = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="379c2-112">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="379c2-113">Operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="379c2-113">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="379c2-114">destinazione:' t</span><span class="sxs-lookup"><span data-stu-id="379c2-114">target : 'T</span></span>

<span data-ttu-id="379c2-115">Input a cui viene applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="379c2-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="379c2-116">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="379c2-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="379c2-117">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="379c2-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="379c2-118">T</span><span class="sxs-lookup"><span data-stu-id="379c2-118">'T</span></span>

<span data-ttu-id="379c2-119">Tipo di input dell'operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="379c2-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="379c2-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="379c2-120">See Also</span></span>

- [<span data-ttu-id="379c2-121">Microsoft. Quantum. Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="379c2-121">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="379c2-122">Microsoft. Quantum. Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="379c2-122">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="379c2-123">Microsoft. Quantum. Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="379c2-123">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)