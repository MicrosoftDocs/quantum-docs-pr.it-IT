---
uid: Microsoft.Quantum.Canon.ApplyIfOne
title: Operazione ApplyIfOne
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOne
qsharp.summary: Applies an operation conditioned on a classical result value being one.
ms.openlocfilehash: 8c668423d126f02736bcb541e73e210a761c5719
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718105"
---
# <a name="applyifone-operation"></a><span data-ttu-id="a8a07-102">Operazione ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="a8a07-102">ApplyIfOne operation</span></span>

<span data-ttu-id="a8a07-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a8a07-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a8a07-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a8a07-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a8a07-105">Applica un'operazione condizionata su un valore di risultato classico.</span><span class="sxs-lookup"><span data-stu-id="a8a07-105">Applies an operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOne<'T> (result : Result, (op : ('T => Unit), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="a8a07-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a8a07-106">Description</span></span>

<span data-ttu-id="a8a07-107">Data un'operazione `op` e un valore `result` di risultato, si applica `op` a `target` se `result` è `One` .</span><span class="sxs-lookup"><span data-stu-id="a8a07-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="a8a07-108">Se `Zero` , non viene eseguita alcuna operazione in `target` .</span><span class="sxs-lookup"><span data-stu-id="a8a07-108">If `Zero`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="a8a07-109">Input</span><span class="sxs-lookup"><span data-stu-id="a8a07-109">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="a8a07-110">risultato: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="a8a07-110">result : __invalid<Result>__</span></span>

<span data-ttu-id="a8a07-111">Risultato della misurazione che controlla se op viene applicato o meno.</span><span class="sxs-lookup"><span data-stu-id="a8a07-111">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="a8a07-112">op:' t = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="a8a07-112">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="a8a07-113">Operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="a8a07-113">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="a8a07-114">destinazione:' t</span><span class="sxs-lookup"><span data-stu-id="a8a07-114">target : 'T</span></span>

<span data-ttu-id="a8a07-115">Input a cui viene applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="a8a07-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a8a07-116">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a8a07-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a8a07-117">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="a8a07-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a8a07-118">T</span><span class="sxs-lookup"><span data-stu-id="a8a07-118">'T</span></span>

<span data-ttu-id="a8a07-119">Tipo di input dell'operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="a8a07-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="a8a07-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8a07-120">See Also</span></span>

- [<span data-ttu-id="a8a07-121">Microsoft. Quantum. Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="a8a07-121">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="a8a07-122">Microsoft. Quantum. Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="a8a07-122">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="a8a07-123">Microsoft. Quantum. Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="a8a07-123">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)