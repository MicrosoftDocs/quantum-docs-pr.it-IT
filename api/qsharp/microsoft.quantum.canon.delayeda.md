---
uid: Microsoft.Quantum.Canon.DelayedA
title: Funzione delaya
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 11c11cdd75d80d6324666ef56930f7a522121826
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716246"
---
# <a name="delayeda-function"></a><span data-ttu-id="e13d8-102">Funzione delaya</span><span class="sxs-lookup"><span data-stu-id="e13d8-102">DelayedA function</span></span>

<span data-ttu-id="e13d8-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e13d8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e13d8-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e13d8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e13d8-105">Restituisce un'operazione che applica l'operazione specificata con l'argomento specificato.</span><span class="sxs-lookup"><span data-stu-id="e13d8-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedA<'T> (op : ('T => Unit is Adj), arg : 'T) : (Unit => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="e13d8-106">Input</span><span class="sxs-lookup"><span data-stu-id="e13d8-106">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="e13d8-107">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ</span><span class="sxs-lookup"><span data-stu-id="e13d8-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="e13d8-108">Operazione da applicare in seguito all'applicazione del valore restituito</span><span class="sxs-lookup"><span data-stu-id="e13d8-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="e13d8-109">ARG:' t</span><span class="sxs-lookup"><span data-stu-id="e13d8-109">arg : 'T</span></span>

<span data-ttu-id="e13d8-110">Input a cui `op` viene applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="e13d8-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit-adj"></a><span data-ttu-id="e13d8-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) ADJ unità</span><span class="sxs-lookup"><span data-stu-id="e13d8-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="e13d8-112">Nuova operazione applicata con l' `op` input `arg`</span><span class="sxs-lookup"><span data-stu-id="e13d8-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e13d8-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="e13d8-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e13d8-114">T</span><span class="sxs-lookup"><span data-stu-id="e13d8-114">'T</span></span>

<span data-ttu-id="e13d8-115">Tipo di input dell'operazione da ritardare.</span><span class="sxs-lookup"><span data-stu-id="e13d8-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="e13d8-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e13d8-116">See Also</span></span>

- [<span data-ttu-id="e13d8-117">Microsoft. Quantum. Canon. Delayed</span><span class="sxs-lookup"><span data-stu-id="e13d8-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="e13d8-118">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="e13d8-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)