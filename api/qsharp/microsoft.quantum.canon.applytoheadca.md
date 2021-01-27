---
uid: Microsoft.Quantum.Canon.ApplyToHeadCA
title: Operazione ApplyToHeadCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadCA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 1bb24006a2d52167dfc7a7871cfbf5a4378d1cb7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850606"
---
# <a name="applytoheadca-operation"></a><span data-ttu-id="028fd-102">Operazione ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="028fd-102">ApplyToHeadCA operation</span></span>

<span data-ttu-id="028fd-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="028fd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="028fd-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="028fd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="028fd-105">Applica un'operazione al primo elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="028fd-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="028fd-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="028fd-106">Description</span></span>

<span data-ttu-id="028fd-107">Data un'operazione `op` e una matrice di destinazioni `targets` , si applica `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="028fd-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="028fd-108">Input</span><span class="sxs-lookup"><span data-stu-id="028fd-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="028fd-109">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="028fd-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="028fd-110">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="028fd-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="028fd-111">destinazioni:' t []</span><span class="sxs-lookup"><span data-stu-id="028fd-111">targets : 'T[]</span></span>

<span data-ttu-id="028fd-112">Matrice di destinazioni, di cui verrà applicato il primo oggetto `op` .</span><span class="sxs-lookup"><span data-stu-id="028fd-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="028fd-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="028fd-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="028fd-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="028fd-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="028fd-115">T</span><span class="sxs-lookup"><span data-stu-id="028fd-115">'T</span></span>

<span data-ttu-id="028fd-116">Tipo di input dell'operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="028fd-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="028fd-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="028fd-117">See Also</span></span>

- [<span data-ttu-id="028fd-118">Microsoft. Quantum. Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="028fd-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="028fd-119">Microsoft. Quantum. Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="028fd-119">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="028fd-120">Microsoft. Quantum. Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="028fd-120">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)