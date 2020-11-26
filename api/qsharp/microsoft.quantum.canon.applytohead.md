---
uid: Microsoft.Quantum.Canon.ApplyToHead
title: Operazione ApplyToHead
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHead
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 35f19cbb1090e974e18f338239764c9c8b854116
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217340"
---
# <a name="applytohead-operation"></a><span data-ttu-id="a6dc7-102">Operazione ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="a6dc7-102">ApplyToHead operation</span></span>

<span data-ttu-id="a6dc7-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a6dc7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a6dc7-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a6dc7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a6dc7-105">Applica un'operazione al primo elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="a6dc7-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHead<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="a6dc7-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a6dc7-106">Description</span></span>

<span data-ttu-id="a6dc7-107">Data un'operazione `op` e una matrice di destinazioni `targets` , si applica `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="a6dc7-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="a6dc7-108">Input</span><span class="sxs-lookup"><span data-stu-id="a6dc7-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="a6dc7-109">op:' t = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="a6dc7-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="a6dc7-110">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="a6dc7-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="a6dc7-111">destinazioni:' t []</span><span class="sxs-lookup"><span data-stu-id="a6dc7-111">targets : 'T[]</span></span>

<span data-ttu-id="a6dc7-112">Matrice di destinazioni, di cui verrà applicato il primo oggetto `op` .</span><span class="sxs-lookup"><span data-stu-id="a6dc7-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a6dc7-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a6dc7-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a6dc7-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="a6dc7-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a6dc7-115">T</span><span class="sxs-lookup"><span data-stu-id="a6dc7-115">'T</span></span>

<span data-ttu-id="a6dc7-116">Tipo di input dell'operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="a6dc7-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="a6dc7-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6dc7-117">See Also</span></span>

- [<span data-ttu-id="a6dc7-118">Microsoft. Quantum. Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="a6dc7-118">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="a6dc7-119">Microsoft. Quantum. Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="a6dc7-119">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [<span data-ttu-id="a6dc7-120">Microsoft. Quantum. Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="a6dc7-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)