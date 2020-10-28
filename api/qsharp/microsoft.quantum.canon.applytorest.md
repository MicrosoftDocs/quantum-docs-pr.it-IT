---
uid: Microsoft.Quantum.Canon.ApplyToRest
title: Operazione ApplyToRest
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRest
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 29bf080d693c668421181f10faef50f5681683be
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717111"
---
# <a name="applytorest-operation"></a><span data-ttu-id="9279b-102">Operazione ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="9279b-102">ApplyToRest operation</span></span>

<span data-ttu-id="9279b-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9279b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9279b-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9279b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9279b-105">Applica un'operazione a tutti gli elementi tranne il primo elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="9279b-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRest<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="9279b-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9279b-106">Description</span></span>

<span data-ttu-id="9279b-107">Data un'operazione `op` e una matrice di destinazioni `targets` , si applica `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="9279b-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="9279b-108">Input</span><span class="sxs-lookup"><span data-stu-id="9279b-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="9279b-109">op:' t [] = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="9279b-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="9279b-110">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="9279b-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="9279b-111">destinazioni:' t []</span><span class="sxs-lookup"><span data-stu-id="9279b-111">targets : 'T[]</span></span>

<span data-ttu-id="9279b-112">Matrice di destinazioni a cui verranno applicati tutti gli altri, tranne il primo `op` .</span><span class="sxs-lookup"><span data-stu-id="9279b-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9279b-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9279b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9279b-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="9279b-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9279b-115">T</span><span class="sxs-lookup"><span data-stu-id="9279b-115">'T</span></span>

<span data-ttu-id="9279b-116">Tipo di input dell'operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="9279b-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="9279b-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9279b-117">See Also</span></span>

- [<span data-ttu-id="9279b-118">Microsoft. Quantum. Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="9279b-118">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="9279b-119">Microsoft. Quantum. Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="9279b-119">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [<span data-ttu-id="9279b-120">Microsoft. Quantum. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="9279b-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)