---
uid: Microsoft.Quantum.Canon.ApplyToHeadC
title: Operazione ApplyToHeadC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadC
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 3ff6c25837f1219dd456bf1739a2953ff72e2df9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717251"
---
# <a name="applytoheadc-operation"></a><span data-ttu-id="c208e-102">Operazione ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="c208e-102">ApplyToHeadC operation</span></span>

<span data-ttu-id="c208e-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c208e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c208e-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c208e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c208e-105">Applica un'operazione al primo elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="c208e-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="c208e-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c208e-106">Description</span></span>

<span data-ttu-id="c208e-107">Data un'operazione `op` e una matrice di destinazioni `targets` , si applica `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="c208e-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="c208e-108">Input</span><span class="sxs-lookup"><span data-stu-id="c208e-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="c208e-109">op:' t => CTL [unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c208e-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="c208e-110">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="c208e-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="c208e-111">destinazioni:' t []</span><span class="sxs-lookup"><span data-stu-id="c208e-111">targets : 'T[]</span></span>

<span data-ttu-id="c208e-112">Matrice di destinazioni, di cui verrà applicato il primo oggetto `op` .</span><span class="sxs-lookup"><span data-stu-id="c208e-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c208e-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c208e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c208e-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="c208e-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c208e-115">T</span><span class="sxs-lookup"><span data-stu-id="c208e-115">'T</span></span>

<span data-ttu-id="c208e-116">Tipo di input dell'operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="c208e-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="c208e-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c208e-117">See Also</span></span>

- [<span data-ttu-id="c208e-118">Microsoft. Quantum. Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="c208e-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="c208e-119">Microsoft. Quantum. Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="c208e-119">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="c208e-120">Microsoft. Quantum. Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="c208e-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)