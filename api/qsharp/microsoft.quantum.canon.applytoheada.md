---
uid: Microsoft.Quantum.Canon.ApplyToHeadA
title: Operazione ApplyToHeadA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 3397c059706c48ff8ca47dd2312cfa9565aacaba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208636"
---
# <a name="applytoheada-operation"></a><span data-ttu-id="db3e2-102">Operazione ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="db3e2-102">ApplyToHeadA operation</span></span>

<span data-ttu-id="db3e2-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="db3e2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="db3e2-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="db3e2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="db3e2-105">Applica un'operazione al primo elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="db3e2-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="db3e2-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="db3e2-106">Description</span></span>

<span data-ttu-id="db3e2-107">Data un'operazione `op` e una matrice di destinazioni `targets` , si applica `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="db3e2-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="db3e2-108">Input</span><span class="sxs-lookup"><span data-stu-id="db3e2-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="db3e2-109">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ</span><span class="sxs-lookup"><span data-stu-id="db3e2-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="db3e2-110">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="db3e2-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="db3e2-111">destinazioni:' t []</span><span class="sxs-lookup"><span data-stu-id="db3e2-111">targets : 'T[]</span></span>

<span data-ttu-id="db3e2-112">Matrice di destinazioni, di cui verrà applicato il primo oggetto `op` .</span><span class="sxs-lookup"><span data-stu-id="db3e2-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="db3e2-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="db3e2-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="db3e2-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="db3e2-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="db3e2-115">T</span><span class="sxs-lookup"><span data-stu-id="db3e2-115">'T</span></span>

<span data-ttu-id="db3e2-116">Tipo di input dell'operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="db3e2-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="db3e2-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db3e2-117">See Also</span></span>

- [<span data-ttu-id="db3e2-118">Microsoft. Quantum. Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="db3e2-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="db3e2-119">Microsoft. Quantum. Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="db3e2-119">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [<span data-ttu-id="db3e2-120">Microsoft. Quantum. Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="db3e2-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)