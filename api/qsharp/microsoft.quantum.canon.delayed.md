---
uid: Microsoft.Quantum.Canon.Delayed
title: Funzione ritardata
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delayed
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 863c63d0c1a50339e9d5b9fbe4729932b2706f32
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216456"
---
# <a name="delayed-function"></a><span data-ttu-id="428d6-102">Funzione ritardata</span><span class="sxs-lookup"><span data-stu-id="428d6-102">Delayed function</span></span>

<span data-ttu-id="428d6-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="428d6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="428d6-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="428d6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="428d6-105">Restituisce un'operazione che applica l'operazione specificata con l'argomento specificato.</span><span class="sxs-lookup"><span data-stu-id="428d6-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function Delayed<'T, 'U> (op : ('T => 'U), arg : 'T) : (Unit => 'U)
```


## <a name="input"></a><span data-ttu-id="428d6-106">Input</span><span class="sxs-lookup"><span data-stu-id="428d6-106">Input</span></span>

### <a name="op--t--u"></a><span data-ttu-id="428d6-107">op:' t =>' U</span><span class="sxs-lookup"><span data-stu-id="428d6-107">op : 'T => 'U</span></span> 

<span data-ttu-id="428d6-108">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="428d6-108">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="428d6-109">ARG:' t</span><span class="sxs-lookup"><span data-stu-id="428d6-109">arg : 'T</span></span>

<span data-ttu-id="428d6-110">Input a cui viene applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="428d6-110">The input to which the operation is applied.</span></span>



## <a name="output--unit--u"></a><span data-ttu-id="428d6-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit) =>' U</span><span class="sxs-lookup"><span data-stu-id="428d6-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => 'U</span></span> 

<span data-ttu-id="428d6-112">Nuova operazione applicata con l' `op` input `arg`</span><span class="sxs-lookup"><span data-stu-id="428d6-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="428d6-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="428d6-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="428d6-114">T</span><span class="sxs-lookup"><span data-stu-id="428d6-114">'T</span></span>

<span data-ttu-id="428d6-115">Tipo di input dell'operazione da ritardare.</span><span class="sxs-lookup"><span data-stu-id="428d6-115">The input type of the operation to be delayed.</span></span>
### <a name="u"></a><span data-ttu-id="428d6-116">' U</span><span class="sxs-lookup"><span data-stu-id="428d6-116">'U</span></span>

<span data-ttu-id="428d6-117">Tipo restituito dell'operazione da ritardare.</span><span class="sxs-lookup"><span data-stu-id="428d6-117">The return type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="428d6-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="428d6-118">See Also</span></span>

- [<span data-ttu-id="428d6-119">Microsoft. Quantum. Canon. DelayedC</span><span class="sxs-lookup"><span data-stu-id="428d6-119">Microsoft.Quantum.Canon.DelayedC</span></span>](xref:Microsoft.Quantum.Canon.DelayedC)
- [<span data-ttu-id="428d6-120">Microsoft. Quantum. Canon. Delaya</span><span class="sxs-lookup"><span data-stu-id="428d6-120">Microsoft.Quantum.Canon.DelayedA</span></span>](xref:Microsoft.Quantum.Canon.DelayedA)
- [<span data-ttu-id="428d6-121">Microsoft. Quantum. Canon. DelayedCA</span><span class="sxs-lookup"><span data-stu-id="428d6-121">Microsoft.Quantum.Canon.DelayedCA</span></span>](xref:Microsoft.Quantum.Canon.DelayedCA)
- [<span data-ttu-id="428d6-122">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="428d6-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)