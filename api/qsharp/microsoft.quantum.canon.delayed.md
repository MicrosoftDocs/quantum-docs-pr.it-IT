---
uid: Microsoft.Quantum.Canon.Delayed
title: Funzione ritardata
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delayed
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 40fcc7d0a178fdb18437b4d6c96542db593347b4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840575"
---
# <a name="delayed-function"></a><span data-ttu-id="021ea-102">Funzione ritardata</span><span class="sxs-lookup"><span data-stu-id="021ea-102">Delayed function</span></span>

<span data-ttu-id="021ea-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="021ea-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="021ea-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="021ea-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="021ea-105">Restituisce un'operazione che applica l'operazione specificata con l'argomento specificato.</span><span class="sxs-lookup"><span data-stu-id="021ea-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function Delayed<'T, 'U> (op : ('T => 'U), arg : 'T) : (Unit => 'U)
```


## <a name="input"></a><span data-ttu-id="021ea-106">Input</span><span class="sxs-lookup"><span data-stu-id="021ea-106">Input</span></span>

### <a name="op--t--u"></a><span data-ttu-id="021ea-107">op:' t =>' U</span><span class="sxs-lookup"><span data-stu-id="021ea-107">op : 'T => 'U</span></span> 

<span data-ttu-id="021ea-108">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="021ea-108">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="021ea-109">ARG:' t</span><span class="sxs-lookup"><span data-stu-id="021ea-109">arg : 'T</span></span>

<span data-ttu-id="021ea-110">Input a cui viene applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="021ea-110">The input to which the operation is applied.</span></span>



## <a name="output--unit--u"></a><span data-ttu-id="021ea-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit) =>' U</span><span class="sxs-lookup"><span data-stu-id="021ea-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => 'U</span></span> 

<span data-ttu-id="021ea-112">Nuova operazione applicata con l' `op` input `arg`</span><span class="sxs-lookup"><span data-stu-id="021ea-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="021ea-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="021ea-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="021ea-114">T</span><span class="sxs-lookup"><span data-stu-id="021ea-114">'T</span></span>

<span data-ttu-id="021ea-115">Tipo di input dell'operazione da ritardare.</span><span class="sxs-lookup"><span data-stu-id="021ea-115">The input type of the operation to be delayed.</span></span>
### <a name="u"></a><span data-ttu-id="021ea-116">' U</span><span class="sxs-lookup"><span data-stu-id="021ea-116">'U</span></span>

<span data-ttu-id="021ea-117">Tipo restituito dell'operazione da ritardare.</span><span class="sxs-lookup"><span data-stu-id="021ea-117">The return type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="021ea-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="021ea-118">See Also</span></span>

- [<span data-ttu-id="021ea-119">Microsoft. Quantum. Canon. DelayedC</span><span class="sxs-lookup"><span data-stu-id="021ea-119">Microsoft.Quantum.Canon.DelayedC</span></span>](xref:Microsoft.Quantum.Canon.DelayedC)
- [<span data-ttu-id="021ea-120">Microsoft. Quantum. Canon. Delaya</span><span class="sxs-lookup"><span data-stu-id="021ea-120">Microsoft.Quantum.Canon.DelayedA</span></span>](xref:Microsoft.Quantum.Canon.DelayedA)
- [<span data-ttu-id="021ea-121">Microsoft. Quantum. Canon. DelayedCA</span><span class="sxs-lookup"><span data-stu-id="021ea-121">Microsoft.Quantum.Canon.DelayedCA</span></span>](xref:Microsoft.Quantum.Canon.DelayedCA)
- [<span data-ttu-id="021ea-122">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="021ea-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)