---
uid: Microsoft.Quantum.Canon.Delayed
title: Funzione ritardata
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delayed
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 820a38c2b4de2e0151d55bd88fb4f69567182f6b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716257"
---
# <a name="delayed-function"></a><span data-ttu-id="12ee2-102">Funzione ritardata</span><span class="sxs-lookup"><span data-stu-id="12ee2-102">Delayed function</span></span>

<span data-ttu-id="12ee2-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="12ee2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="12ee2-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="12ee2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="12ee2-105">Restituisce un'operazione che applica l'operazione specificata con l'argomento specificato.</span><span class="sxs-lookup"><span data-stu-id="12ee2-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function Delayed<'T, 'U> (op : ('T => 'U), arg : 'T) : (Unit => 'U)
```


## <a name="input"></a><span data-ttu-id="12ee2-106">Input</span><span class="sxs-lookup"><span data-stu-id="12ee2-106">Input</span></span>

### <a name="op--t--u"></a><span data-ttu-id="12ee2-107">op:' t =>' U</span><span class="sxs-lookup"><span data-stu-id="12ee2-107">op : 'T => 'U</span></span> 

<span data-ttu-id="12ee2-108">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="12ee2-108">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="12ee2-109">ARG:' t</span><span class="sxs-lookup"><span data-stu-id="12ee2-109">arg : 'T</span></span>

<span data-ttu-id="12ee2-110">Input a cui viene applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="12ee2-110">The input to which the operation is applied.</span></span>



## <a name="output--unit--u"></a><span data-ttu-id="12ee2-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit) =>' U</span><span class="sxs-lookup"><span data-stu-id="12ee2-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => 'U</span></span> 

<span data-ttu-id="12ee2-112">Nuova operazione applicata con l' `op` input `arg`</span><span class="sxs-lookup"><span data-stu-id="12ee2-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="12ee2-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="12ee2-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="12ee2-114">T</span><span class="sxs-lookup"><span data-stu-id="12ee2-114">'T</span></span>

<span data-ttu-id="12ee2-115">Tipo di input dell'operazione da ritardare.</span><span class="sxs-lookup"><span data-stu-id="12ee2-115">The input type of the operation to be delayed.</span></span>
### <a name="u"></a><span data-ttu-id="12ee2-116">' U</span><span class="sxs-lookup"><span data-stu-id="12ee2-116">'U</span></span>

<span data-ttu-id="12ee2-117">Tipo restituito dell'operazione da ritardare.</span><span class="sxs-lookup"><span data-stu-id="12ee2-117">The return type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="12ee2-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12ee2-118">See Also</span></span>

- [<span data-ttu-id="12ee2-119">Microsoft. Quantum. Canon. DelayedC</span><span class="sxs-lookup"><span data-stu-id="12ee2-119">Microsoft.Quantum.Canon.DelayedC</span></span>](xref:Microsoft.Quantum.Canon.DelayedC)
- [<span data-ttu-id="12ee2-120">Microsoft. Quantum. Canon. Delaya</span><span class="sxs-lookup"><span data-stu-id="12ee2-120">Microsoft.Quantum.Canon.DelayedA</span></span>](xref:Microsoft.Quantum.Canon.DelayedA)
- [<span data-ttu-id="12ee2-121">Microsoft. Quantum. Canon. DelayedCA</span><span class="sxs-lookup"><span data-stu-id="12ee2-121">Microsoft.Quantum.Canon.DelayedCA</span></span>](xref:Microsoft.Quantum.Canon.DelayedCA)
- [<span data-ttu-id="12ee2-122">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="12ee2-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)