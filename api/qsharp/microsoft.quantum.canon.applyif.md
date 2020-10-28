---
uid: Microsoft.Quantum.Canon.ApplyIf
title: Operazione ApplyIf
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIf
qsharp.summary: Applies an operation conditioned on a classical bit.
ms.openlocfilehash: c8f6860a7a3b8af86b0edb048baccbf057dd245a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718242"
---
# <a name="applyif-operation"></a><span data-ttu-id="53b77-102">Operazione ApplyIf</span><span class="sxs-lookup"><span data-stu-id="53b77-102">ApplyIf operation</span></span>

<span data-ttu-id="53b77-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="53b77-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="53b77-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="53b77-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="53b77-105">Applica un'operazione condizionata su un bit classico.</span><span class="sxs-lookup"><span data-stu-id="53b77-105">Applies an operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIf<'T> (op : ('T => Unit), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="53b77-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53b77-106">Description</span></span>

<span data-ttu-id="53b77-107">Data un'operazione `op` e un valore `bit` di bit, si applica `op` a `target` se `bit` è `true` .</span><span class="sxs-lookup"><span data-stu-id="53b77-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="53b77-108">Se `false` , non viene eseguita alcuna operazione in `target` .</span><span class="sxs-lookup"><span data-stu-id="53b77-108">If `false`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="53b77-109">Input</span><span class="sxs-lookup"><span data-stu-id="53b77-109">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="53b77-110">op:' t = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="53b77-110">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="53b77-111">Operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="53b77-111">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="53b77-112">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="53b77-112">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="53b77-113">valore booleano che controlla se op viene applicato o meno.</span><span class="sxs-lookup"><span data-stu-id="53b77-113">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="53b77-114">destinazione:' t</span><span class="sxs-lookup"><span data-stu-id="53b77-114">target : 'T</span></span>

<span data-ttu-id="53b77-115">Input a cui viene applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="53b77-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="53b77-116">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="53b77-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="53b77-117">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="53b77-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="53b77-118">T</span><span class="sxs-lookup"><span data-stu-id="53b77-118">'T</span></span>

<span data-ttu-id="53b77-119">Tipo di input dell'operazione da applicare in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="53b77-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="53b77-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53b77-120">See Also</span></span>

- [<span data-ttu-id="53b77-121">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="53b77-121">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="53b77-122">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="53b77-122">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="53b77-123">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="53b77-123">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)