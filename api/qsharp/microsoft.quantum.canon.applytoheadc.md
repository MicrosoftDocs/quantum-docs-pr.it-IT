---
uid: Microsoft.Quantum.Canon.ApplyToHeadC
title: Operazione ApplyToHeadC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadC
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 2b7321a6c385e2d98a0e91a8f58091ea8dc43ff4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208602"
---
# <a name="applytoheadc-operation"></a><span data-ttu-id="98655-102">Operazione ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="98655-102">ApplyToHeadC operation</span></span>

<span data-ttu-id="98655-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="98655-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="98655-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="98655-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="98655-105">Applica un'operazione al primo elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="98655-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="98655-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="98655-106">Description</span></span>

<span data-ttu-id="98655-107">Data un'operazione `op` e una matrice di destinazioni `targets` , si applica `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="98655-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="98655-108">Input</span><span class="sxs-lookup"><span data-stu-id="98655-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="98655-109">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL</span><span class="sxs-lookup"><span data-stu-id="98655-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="98655-110">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="98655-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="98655-111">destinazioni:' t []</span><span class="sxs-lookup"><span data-stu-id="98655-111">targets : 'T[]</span></span>

<span data-ttu-id="98655-112">Matrice di destinazioni, di cui verrà applicato il primo oggetto `op` .</span><span class="sxs-lookup"><span data-stu-id="98655-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="98655-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="98655-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="98655-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="98655-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="98655-115">T</span><span class="sxs-lookup"><span data-stu-id="98655-115">'T</span></span>

<span data-ttu-id="98655-116">Tipo di input dell'operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="98655-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="98655-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98655-117">See Also</span></span>

- [<span data-ttu-id="98655-118">Microsoft. Quantum. Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="98655-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="98655-119">Microsoft. Quantum. Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="98655-119">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="98655-120">Microsoft. Quantum. Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="98655-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)