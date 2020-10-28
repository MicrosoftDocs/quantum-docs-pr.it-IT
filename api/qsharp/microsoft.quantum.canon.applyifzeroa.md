---
uid: Microsoft.Quantum.Canon.ApplyIfZeroA
title: Operazione ApplyIfZeroA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroA
qsharp.summary: Applies an adjointable operation conditioned on a classical result value being zero.
ms.openlocfilehash: d324cd970e8df49ceb51b6bf5c9f3c9c3ff142f9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718052"
---
# <a name="applyifzeroa-operation"></a><span data-ttu-id="1800d-102">Operazione ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="1800d-102">ApplyIfZeroA operation</span></span>

<span data-ttu-id="1800d-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1800d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1800d-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1800d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1800d-105">Applica un'operazione adjointable condizionata su un valore di risultato classico che è zero.</span><span class="sxs-lookup"><span data-stu-id="1800d-105">Applies an adjointable operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZeroA<'T> (result : Result, (op : ('T => Unit is Adj), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="1800d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1800d-106">Description</span></span>

<span data-ttu-id="1800d-107">Data un'operazione `op` e un valore `result` di risultato, si applica `op` a `target` se `result` è `Zero` .</span><span class="sxs-lookup"><span data-stu-id="1800d-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="1800d-108">Se `One` , non viene eseguita alcuna operazione in `target` .</span><span class="sxs-lookup"><span data-stu-id="1800d-108">If `One`, nothing happens to the `target`.</span></span>
<span data-ttu-id="1800d-109">Il suffisso `A` indica che l'operazione da applicare è adjointable.</span><span class="sxs-lookup"><span data-stu-id="1800d-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="1800d-110">Input</span><span class="sxs-lookup"><span data-stu-id="1800d-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="1800d-111">risultato: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="1800d-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="1800d-112">Risultato della misurazione che controlla se op viene applicato o meno.</span><span class="sxs-lookup"><span data-stu-id="1800d-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit-adj"></a><span data-ttu-id="1800d-113">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ</span><span class="sxs-lookup"><span data-stu-id="1800d-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="1800d-114">Operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="1800d-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="1800d-115">destinazione:' t</span><span class="sxs-lookup"><span data-stu-id="1800d-115">target : 'T</span></span>

<span data-ttu-id="1800d-116">Input a cui viene applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="1800d-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1800d-117">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1800d-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1800d-118">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="1800d-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1800d-119">T</span><span class="sxs-lookup"><span data-stu-id="1800d-119">'T</span></span>

<span data-ttu-id="1800d-120">Tipo di input dell'operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="1800d-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="1800d-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1800d-121">See Also</span></span>

- [<span data-ttu-id="1800d-122">Microsoft. Quantum. Canon. ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="1800d-122">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="1800d-123">Microsoft. Quantum. Canon. ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="1800d-123">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="1800d-124">Microsoft. Quantum. Canon. ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="1800d-124">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)