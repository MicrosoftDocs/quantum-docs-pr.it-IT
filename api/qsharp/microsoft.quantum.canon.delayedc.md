---
uid: Microsoft.Quantum.Canon.DelayedC
title: DelayedC (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedC
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: d8036397559b1587b806f701d89e892eea2da8f9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207013"
---
# <a name="delayedc-function"></a><span data-ttu-id="e1a72-102">DelayedC (funzione)</span><span class="sxs-lookup"><span data-stu-id="e1a72-102">DelayedC function</span></span>

<span data-ttu-id="e1a72-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e1a72-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e1a72-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e1a72-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e1a72-105">Restituisce un'operazione che applica l'operazione specificata con l'argomento specificato.</span><span class="sxs-lookup"><span data-stu-id="e1a72-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedC<'T> (op : ('T => Unit is Ctl), arg : 'T) : (Unit => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="e1a72-106">Input</span><span class="sxs-lookup"><span data-stu-id="e1a72-106">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="e1a72-107">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL</span><span class="sxs-lookup"><span data-stu-id="e1a72-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="e1a72-108">Operazione da applicare in seguito all'applicazione del valore restituito</span><span class="sxs-lookup"><span data-stu-id="e1a72-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="e1a72-109">ARG:' t</span><span class="sxs-lookup"><span data-stu-id="e1a72-109">arg : 'T</span></span>

<span data-ttu-id="e1a72-110">Input a cui `op` viene applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="e1a72-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit--is-ctl"></a><span data-ttu-id="e1a72-111">Output: [unità unità](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) è CTL</span><span class="sxs-lookup"><span data-stu-id="e1a72-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="e1a72-112">Nuova operazione applicata con l' `op` input `arg`</span><span class="sxs-lookup"><span data-stu-id="e1a72-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e1a72-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="e1a72-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e1a72-114">T</span><span class="sxs-lookup"><span data-stu-id="e1a72-114">'T</span></span>

<span data-ttu-id="e1a72-115">Tipo di input dell'operazione da ritardare.</span><span class="sxs-lookup"><span data-stu-id="e1a72-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="e1a72-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1a72-116">See Also</span></span>

- [<span data-ttu-id="e1a72-117">Microsoft. Quantum. Canon. Delayed</span><span class="sxs-lookup"><span data-stu-id="e1a72-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="e1a72-118">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="e1a72-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)