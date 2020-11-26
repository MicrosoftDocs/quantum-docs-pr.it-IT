---
uid: Microsoft.Quantum.Canon.ApplyIfA
title: Operazione ApplyIfA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfA
qsharp.summary: Applies a adjointable operation conditioned on a classical bit.
ms.openlocfilehash: d2880bbb95ebaf621ef9e5885051b94f32a3f1cc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218768"
---
# <a name="applyifa-operation"></a><span data-ttu-id="ca6b7-102">Operazione ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="ca6b7-102">ApplyIfA operation</span></span>

<span data-ttu-id="ca6b7-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ca6b7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ca6b7-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ca6b7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ca6b7-105">Applica un'operazione adjointable condizionata su un bit classico.</span><span class="sxs-lookup"><span data-stu-id="ca6b7-105">Applies a adjointable operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfA<'T> (op : ('T => Unit is Adj), bit : Bool, target : 'T) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="ca6b7-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ca6b7-106">Description</span></span>

<span data-ttu-id="ca6b7-107">Data un'operazione `op` e un valore `bit` di bit, si applica `op` a `target` se `bit` è `true` .</span><span class="sxs-lookup"><span data-stu-id="ca6b7-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="ca6b7-108">Se `false` , non viene eseguita alcuna operazione in `target` .</span><span class="sxs-lookup"><span data-stu-id="ca6b7-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="ca6b7-109">Il suffisso `A` indica che l'operazione da applicare è adjointable.</span><span class="sxs-lookup"><span data-stu-id="ca6b7-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="ca6b7-110">Input</span><span class="sxs-lookup"><span data-stu-id="ca6b7-110">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="ca6b7-111">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ</span><span class="sxs-lookup"><span data-stu-id="ca6b7-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="ca6b7-112">Operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="ca6b7-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="ca6b7-113">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ca6b7-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ca6b7-114">valore booleano che controlla se op viene applicato o meno.</span><span class="sxs-lookup"><span data-stu-id="ca6b7-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="ca6b7-115">destinazione:' t</span><span class="sxs-lookup"><span data-stu-id="ca6b7-115">target : 'T</span></span>

<span data-ttu-id="ca6b7-116">Input a cui viene applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="ca6b7-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ca6b7-117">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ca6b7-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ca6b7-118">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="ca6b7-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ca6b7-119">T</span><span class="sxs-lookup"><span data-stu-id="ca6b7-119">'T</span></span>

<span data-ttu-id="ca6b7-120">Tipo di input dell'operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="ca6b7-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="ca6b7-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca6b7-121">See Also</span></span>

- [<span data-ttu-id="ca6b7-122">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="ca6b7-122">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="ca6b7-123">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="ca6b7-123">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="ca6b7-124">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="ca6b7-124">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)