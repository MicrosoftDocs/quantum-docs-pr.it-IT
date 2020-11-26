---
uid: Microsoft.Quantum.Canon.ApplyIf
title: Operazione ApplyIf
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIf
qsharp.summary: Applies an operation conditioned on a classical bit.
ms.openlocfilehash: c5a1012328fa012ee02707aa59c94ac9c44b8e87
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218836"
---
# <a name="applyif-operation"></a><span data-ttu-id="46174-102">Operazione ApplyIf</span><span class="sxs-lookup"><span data-stu-id="46174-102">ApplyIf operation</span></span>

<span data-ttu-id="46174-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="46174-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="46174-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="46174-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="46174-105">Applica un'operazione condizionata su un bit classico.</span><span class="sxs-lookup"><span data-stu-id="46174-105">Applies an operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIf<'T> (op : ('T => Unit), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="46174-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="46174-106">Description</span></span>

<span data-ttu-id="46174-107">Data un'operazione `op` e un valore `bit` di bit, si applica `op` a `target` se `bit` è `true` .</span><span class="sxs-lookup"><span data-stu-id="46174-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="46174-108">Se `false` , non viene eseguita alcuna operazione in `target` .</span><span class="sxs-lookup"><span data-stu-id="46174-108">If `false`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="46174-109">Input</span><span class="sxs-lookup"><span data-stu-id="46174-109">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="46174-110">op:' t = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="46174-110">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="46174-111">Operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="46174-111">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="46174-112">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="46174-112">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="46174-113">valore booleano che controlla se op viene applicato o meno.</span><span class="sxs-lookup"><span data-stu-id="46174-113">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="46174-114">destinazione:' t</span><span class="sxs-lookup"><span data-stu-id="46174-114">target : 'T</span></span>

<span data-ttu-id="46174-115">Input a cui viene applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="46174-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="46174-116">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="46174-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="46174-117">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="46174-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="46174-118">T</span><span class="sxs-lookup"><span data-stu-id="46174-118">'T</span></span>

<span data-ttu-id="46174-119">Tipo di input dell'operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="46174-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="46174-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46174-120">See Also</span></span>

- [<span data-ttu-id="46174-121">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="46174-121">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="46174-122">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="46174-122">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="46174-123">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="46174-123">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)