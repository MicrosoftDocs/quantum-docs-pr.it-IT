---
uid: Microsoft.Quantum.Canon.ApplyToHeadCA
title: Operazione ApplyToHeadCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadCA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 5bb016373040b1b66984405ea2bda0b8cb0c5102
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717237"
---
# <a name="applytoheadca-operation"></a><span data-ttu-id="2c4ca-102">Operazione ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="2c4ca-102">ApplyToHeadCA operation</span></span>

<span data-ttu-id="2c4ca-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2c4ca-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2c4ca-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2c4ca-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2c4ca-105">Applica un'operazione al primo elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="2c4ca-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="2c4ca-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2c4ca-106">Description</span></span>

<span data-ttu-id="2c4ca-107">Data un'operazione `op` e una matrice di destinazioni `targets` , si applica `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="2c4ca-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="2c4ca-108">Input</span><span class="sxs-lookup"><span data-stu-id="2c4ca-108">Input</span></span>

### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="2c4ca-109">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="2c4ca-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="2c4ca-110">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="2c4ca-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="2c4ca-111">destinazioni:' t []</span><span class="sxs-lookup"><span data-stu-id="2c4ca-111">targets : 'T[]</span></span>

<span data-ttu-id="2c4ca-112">Matrice di destinazioni, di cui verrà applicato il primo oggetto `op` .</span><span class="sxs-lookup"><span data-stu-id="2c4ca-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2c4ca-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2c4ca-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2c4ca-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="2c4ca-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2c4ca-115">T</span><span class="sxs-lookup"><span data-stu-id="2c4ca-115">'T</span></span>

<span data-ttu-id="2c4ca-116">Tipo di input dell'operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="2c4ca-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="2c4ca-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c4ca-117">See Also</span></span>

- [<span data-ttu-id="2c4ca-118">Microsoft. Quantum. Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="2c4ca-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="2c4ca-119">Microsoft. Quantum. Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="2c4ca-119">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="2c4ca-120">Microsoft. Quantum. Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="2c4ca-120">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)