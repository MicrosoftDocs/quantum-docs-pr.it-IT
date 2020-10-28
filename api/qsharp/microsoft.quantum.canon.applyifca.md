---
uid: Microsoft.Quantum.Canon.ApplyIfCA
title: Operazione ApplyIfCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfCA
qsharp.summary: Applies a unitary operation conditioned on a classical bit.
ms.openlocfilehash: 9057c79622f15a082963d94fc261664e00322feb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718230"
---
# <a name="applyifca-operation"></a><span data-ttu-id="d82e8-102">Operazione ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="d82e8-102">ApplyIfCA operation</span></span>

<span data-ttu-id="d82e8-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d82e8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d82e8-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d82e8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d82e8-105">Applica un'operazione unitaria condizionata su un bit classico.</span><span class="sxs-lookup"><span data-stu-id="d82e8-105">Applies a unitary operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfCA<'T> (op : ('T => Unit is Ctl + Adj), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="d82e8-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d82e8-106">Description</span></span>

<span data-ttu-id="d82e8-107">Data un'operazione `op` e un valore `bit` di bit, si applica `op` a `target` se `bit` è `true` .</span><span class="sxs-lookup"><span data-stu-id="d82e8-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="d82e8-108">Se `false` , non viene eseguita alcuna operazione in `target` .</span><span class="sxs-lookup"><span data-stu-id="d82e8-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="d82e8-109">Il suffisso `CA` indica che l'operazione da applicare è unitaria (controllabile e adjointable).</span><span class="sxs-lookup"><span data-stu-id="d82e8-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="d82e8-110">Input</span><span class="sxs-lookup"><span data-stu-id="d82e8-110">Input</span></span>

### <a name="op--t--unit-ctl--adj"></a><span data-ttu-id="d82e8-111">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit) CTL + ADJ</span><span class="sxs-lookup"><span data-stu-id="d82e8-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="d82e8-112">Operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="d82e8-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="d82e8-113">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d82e8-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d82e8-114">valore booleano che controlla se op viene applicato o meno.</span><span class="sxs-lookup"><span data-stu-id="d82e8-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="d82e8-115">destinazione:' t</span><span class="sxs-lookup"><span data-stu-id="d82e8-115">target : 'T</span></span>

<span data-ttu-id="d82e8-116">Input a cui viene applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="d82e8-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d82e8-117">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d82e8-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d82e8-118">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="d82e8-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d82e8-119">T</span><span class="sxs-lookup"><span data-stu-id="d82e8-119">'T</span></span>

<span data-ttu-id="d82e8-120">Tipo di input dell'operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="d82e8-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="d82e8-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d82e8-121">See Also</span></span>

- [<span data-ttu-id="d82e8-122">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="d82e8-122">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="d82e8-123">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="d82e8-123">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="d82e8-124">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="d82e8-124">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)