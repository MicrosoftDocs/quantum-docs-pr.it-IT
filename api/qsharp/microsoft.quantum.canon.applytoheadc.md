---
uid: Microsoft.Quantum.Canon.ApplyToHeadC
title: Operazione ApplyToHeadC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadC
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 3a65ad52e0b2f8b3a921fc549c35311f24d0e189
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850635"
---
# <a name="applytoheadc-operation"></a><span data-ttu-id="372e0-102">Operazione ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="372e0-102">ApplyToHeadC operation</span></span>

<span data-ttu-id="372e0-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="372e0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="372e0-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="372e0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="372e0-105">Applica un'operazione al primo elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="372e0-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="372e0-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="372e0-106">Description</span></span>

<span data-ttu-id="372e0-107">Data un'operazione `op` e una matrice di destinazioni `targets` , si applica `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="372e0-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="372e0-108">Input</span><span class="sxs-lookup"><span data-stu-id="372e0-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="372e0-109">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL</span><span class="sxs-lookup"><span data-stu-id="372e0-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="372e0-110">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="372e0-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="372e0-111">destinazioni:' t []</span><span class="sxs-lookup"><span data-stu-id="372e0-111">targets : 'T[]</span></span>

<span data-ttu-id="372e0-112">Matrice di destinazioni, di cui verrà applicato il primo oggetto `op` .</span><span class="sxs-lookup"><span data-stu-id="372e0-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="372e0-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="372e0-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="372e0-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="372e0-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="372e0-115">T</span><span class="sxs-lookup"><span data-stu-id="372e0-115">'T</span></span>

<span data-ttu-id="372e0-116">Tipo di input dell'operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="372e0-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="372e0-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="372e0-117">See Also</span></span>

- [<span data-ttu-id="372e0-118">Microsoft. Quantum. Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="372e0-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="372e0-119">Microsoft. Quantum. Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="372e0-119">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="372e0-120">Microsoft. Quantum. Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="372e0-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)