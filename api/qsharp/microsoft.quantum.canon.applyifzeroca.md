---
uid: Microsoft.Quantum.Canon.ApplyIfZeroCA
title: Operazione ApplyIfZeroCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroCA
qsharp.summary: Applies a unitary operation conditioned on a classical result value being zero.
ms.openlocfilehash: 85612bd3dd7af45b7901fef775a7d556eb229608
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718007"
---
# <a name="applyifzeroca-operation"></a><span data-ttu-id="77686-102">Operazione ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="77686-102">ApplyIfZeroCA operation</span></span>

<span data-ttu-id="77686-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="77686-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="77686-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="77686-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="77686-105">Applica un'operazione unitaria condizionata a un valore di risultato classico che è zero.</span><span class="sxs-lookup"><span data-stu-id="77686-105">Applies a unitary operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZeroCA<'T> (result : Result, (op : ('T => Unit is Adj + Ctl), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="77686-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="77686-106">Description</span></span>

<span data-ttu-id="77686-107">Data un'operazione `op` e un valore `result` di risultato, si applica `op` a `target` se `result` è `Zero` .</span><span class="sxs-lookup"><span data-stu-id="77686-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="77686-108">Se `One` , non viene eseguita alcuna operazione in `target` .</span><span class="sxs-lookup"><span data-stu-id="77686-108">If `One`, nothing happens to the `target`.</span></span>
<span data-ttu-id="77686-109">Il suffisso `CA` indica che l'operazione da applicare è unitaria (controllabile e adjointable).</span><span class="sxs-lookup"><span data-stu-id="77686-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="77686-110">Input</span><span class="sxs-lookup"><span data-stu-id="77686-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="77686-111">risultato: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="77686-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="77686-112">Risultato della misurazione che controlla se op viene applicato o meno.</span><span class="sxs-lookup"><span data-stu-id="77686-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="77686-113">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="77686-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="77686-114">Operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="77686-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="77686-115">destinazione:' t</span><span class="sxs-lookup"><span data-stu-id="77686-115">target : 'T</span></span>

<span data-ttu-id="77686-116">Input a cui viene applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="77686-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="77686-117">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="77686-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="77686-118">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="77686-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="77686-119">T</span><span class="sxs-lookup"><span data-stu-id="77686-119">'T</span></span>

<span data-ttu-id="77686-120">Tipo di input dell'operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="77686-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="77686-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77686-121">See Also</span></span>

- [<span data-ttu-id="77686-122">Microsoft. Quantum. Canon. ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="77686-122">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="77686-123">Microsoft. Quantum. Canon. ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="77686-123">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="77686-124">Microsoft. Quantum. Canon. ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="77686-124">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)