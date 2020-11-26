---
uid: Microsoft.Quantum.Canon.ApplyIfZero
title: Operazione ApplyIfZero
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZero
qsharp.summary: Applies an operation conditioned on a classical result value being zero.
ms.openlocfilehash: 3b14ef8a1aa736fe096a21fe51be5a7c5bb1d09d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209435"
---
# <a name="applyifzero-operation"></a><span data-ttu-id="fbb2f-102">Operazione ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="fbb2f-102">ApplyIfZero operation</span></span>

<span data-ttu-id="fbb2f-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fbb2f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fbb2f-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fbb2f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fbb2f-105">Applica un'operazione condizionata su un valore di risultato classico che è zero.</span><span class="sxs-lookup"><span data-stu-id="fbb2f-105">Applies an operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZero<'T> (result : Result, (op : ('T => Unit), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="fbb2f-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fbb2f-106">Description</span></span>

<span data-ttu-id="fbb2f-107">Data un'operazione `op` e un valore `result` di risultato, si applica `op` a `target` se `result` è `Zero` .</span><span class="sxs-lookup"><span data-stu-id="fbb2f-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="fbb2f-108">Se `One` , non viene eseguita alcuna operazione in `target` .</span><span class="sxs-lookup"><span data-stu-id="fbb2f-108">If `One`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="fbb2f-109">Input</span><span class="sxs-lookup"><span data-stu-id="fbb2f-109">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="fbb2f-110">risultato: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="fbb2f-110">result : __invalid<Result>__</span></span>

<span data-ttu-id="fbb2f-111">Risultato della misurazione che controlla se op viene applicato o meno.</span><span class="sxs-lookup"><span data-stu-id="fbb2f-111">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="fbb2f-112">op:' t = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="fbb2f-112">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="fbb2f-113">Operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="fbb2f-113">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="fbb2f-114">destinazione:' t</span><span class="sxs-lookup"><span data-stu-id="fbb2f-114">target : 'T</span></span>

<span data-ttu-id="fbb2f-115">Input a cui viene applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="fbb2f-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fbb2f-116">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fbb2f-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="fbb2f-117">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="fbb2f-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fbb2f-118">T</span><span class="sxs-lookup"><span data-stu-id="fbb2f-118">'T</span></span>

<span data-ttu-id="fbb2f-119">Tipo di input dell'operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="fbb2f-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="fbb2f-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fbb2f-120">See Also</span></span>

- [<span data-ttu-id="fbb2f-121">Microsoft. Quantum. Canon. ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="fbb2f-121">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="fbb2f-122">Microsoft. Quantum. Canon. ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="fbb2f-122">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="fbb2f-123">Microsoft. Quantum. Canon. ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="fbb2f-123">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)