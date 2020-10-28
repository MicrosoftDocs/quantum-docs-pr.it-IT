---
uid: Microsoft.Quantum.Canon.ApplyIfOneA
title: Operazione ApplyIfOneA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneA
qsharp.summary: Applies an adjointable operation conditioned on a classical result value being one.
ms.openlocfilehash: 76c15aba6042c2801ecfe8470e82099c54ba3846
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718094"
---
# <a name="applyifonea-operation"></a><span data-ttu-id="24e30-102">Operazione ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="24e30-102">ApplyIfOneA operation</span></span>

<span data-ttu-id="24e30-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="24e30-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="24e30-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="24e30-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="24e30-105">Applica un'operazione adjointable condizionata a un valore di risultato classico che è uno.</span><span class="sxs-lookup"><span data-stu-id="24e30-105">Applies an adjointable operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneA<'T> (result : Result, (op : ('T => Unit is Adj), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="24e30-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="24e30-106">Description</span></span>

<span data-ttu-id="24e30-107">Data un'operazione `op` e un valore `result` di risultato, si applica `op` a `target` se `result` è `One` .</span><span class="sxs-lookup"><span data-stu-id="24e30-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="24e30-108">Se `Zero` , non viene eseguita alcuna operazione in `target` .</span><span class="sxs-lookup"><span data-stu-id="24e30-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="24e30-109">Il suffisso `A` indica che l'operazione da applicare è adjointable.</span><span class="sxs-lookup"><span data-stu-id="24e30-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="24e30-110">Input</span><span class="sxs-lookup"><span data-stu-id="24e30-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="24e30-111">risultato: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="24e30-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="24e30-112">Risultato della misurazione che controlla se op viene applicato o meno.</span><span class="sxs-lookup"><span data-stu-id="24e30-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit-adj"></a><span data-ttu-id="24e30-113">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ</span><span class="sxs-lookup"><span data-stu-id="24e30-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="24e30-114">Operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="24e30-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="24e30-115">destinazione:' t</span><span class="sxs-lookup"><span data-stu-id="24e30-115">target : 'T</span></span>

<span data-ttu-id="24e30-116">Input a cui viene applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="24e30-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="24e30-117">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="24e30-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="24e30-118">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="24e30-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="24e30-119">T</span><span class="sxs-lookup"><span data-stu-id="24e30-119">'T</span></span>

<span data-ttu-id="24e30-120">Tipo di input dell'operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="24e30-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="24e30-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24e30-121">See Also</span></span>

- [<span data-ttu-id="24e30-122">Microsoft. Quantum. Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="24e30-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="24e30-123">Microsoft. Quantum. Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="24e30-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="24e30-124">Microsoft. Quantum. Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="24e30-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)