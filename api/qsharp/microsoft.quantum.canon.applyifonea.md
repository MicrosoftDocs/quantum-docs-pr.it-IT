---
uid: Microsoft.Quantum.Canon.ApplyIfOneA
title: Operazione ApplyIfOneA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneA
qsharp.summary: Applies an adjointable operation conditioned on a classical result value being one.
ms.openlocfilehash: 1593f565e950a9410df0ae9de59e6d0e6a7b99b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844938"
---
# <a name="applyifonea-operation"></a><span data-ttu-id="79d54-102">Operazione ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="79d54-102">ApplyIfOneA operation</span></span>

<span data-ttu-id="79d54-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="79d54-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="79d54-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="79d54-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="79d54-105">Applica un'operazione adjointable condizionata a un valore di risultato classico che è uno.</span><span class="sxs-lookup"><span data-stu-id="79d54-105">Applies an adjointable operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneA<'T> (result : Result, (op : ('T => Unit is Adj), target : 'T)) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="79d54-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="79d54-106">Description</span></span>

<span data-ttu-id="79d54-107">Data un'operazione `op` e un valore `result` di risultato, si applica `op` a `target` se `result` è `One` .</span><span class="sxs-lookup"><span data-stu-id="79d54-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="79d54-108">Se `Zero` , non viene eseguita alcuna operazione in `target` .</span><span class="sxs-lookup"><span data-stu-id="79d54-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="79d54-109">Il suffisso `A` indica che l'operazione da applicare è adjointable.</span><span class="sxs-lookup"><span data-stu-id="79d54-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="79d54-110">Input</span><span class="sxs-lookup"><span data-stu-id="79d54-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="79d54-111">risultato: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="79d54-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="79d54-112">Risultato della misurazione che controlla se op viene applicato o meno.</span><span class="sxs-lookup"><span data-stu-id="79d54-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-adj"></a><span data-ttu-id="79d54-113">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ</span><span class="sxs-lookup"><span data-stu-id="79d54-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="79d54-114">Operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="79d54-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="79d54-115">destinazione:' t</span><span class="sxs-lookup"><span data-stu-id="79d54-115">target : 'T</span></span>

<span data-ttu-id="79d54-116">Input a cui viene applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="79d54-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="79d54-117">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="79d54-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="79d54-118">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="79d54-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="79d54-119">T</span><span class="sxs-lookup"><span data-stu-id="79d54-119">'T</span></span>

<span data-ttu-id="79d54-120">Tipo di input dell'operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="79d54-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="79d54-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79d54-121">See Also</span></span>

- [<span data-ttu-id="79d54-122">Microsoft. Quantum. Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="79d54-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="79d54-123">Microsoft. Quantum. Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="79d54-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="79d54-124">Microsoft. Quantum. Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="79d54-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)