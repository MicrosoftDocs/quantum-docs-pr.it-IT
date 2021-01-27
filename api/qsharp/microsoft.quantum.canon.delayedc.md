---
uid: Microsoft.Quantum.Canon.DelayedC
title: DelayedC (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedC
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: a1f2582668131816b774bf4a8b7476d9f1ee8cad
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840570"
---
# <a name="delayedc-function"></a><span data-ttu-id="c256c-102">DelayedC (funzione)</span><span class="sxs-lookup"><span data-stu-id="c256c-102">DelayedC function</span></span>

<span data-ttu-id="c256c-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c256c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c256c-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c256c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c256c-105">Restituisce un'operazione che applica l'operazione specificata con l'argomento specificato.</span><span class="sxs-lookup"><span data-stu-id="c256c-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedC<'T> (op : ('T => Unit is Ctl), arg : 'T) : (Unit => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="c256c-106">Input</span><span class="sxs-lookup"><span data-stu-id="c256c-106">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="c256c-107">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL</span><span class="sxs-lookup"><span data-stu-id="c256c-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="c256c-108">Operazione da applicare in seguito all'applicazione del valore restituito</span><span class="sxs-lookup"><span data-stu-id="c256c-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="c256c-109">ARG:' t</span><span class="sxs-lookup"><span data-stu-id="c256c-109">arg : 'T</span></span>

<span data-ttu-id="c256c-110">Input a cui `op` viene applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="c256c-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit--is-ctl"></a><span data-ttu-id="c256c-111">Output: [unità unità](xref:microsoft.quantum.lang-ref.unit) => [](xref:microsoft.quantum.lang-ref.unit) è CTL</span><span class="sxs-lookup"><span data-stu-id="c256c-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="c256c-112">Nuova operazione applicata con l' `op` input `arg`</span><span class="sxs-lookup"><span data-stu-id="c256c-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c256c-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="c256c-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c256c-114">T</span><span class="sxs-lookup"><span data-stu-id="c256c-114">'T</span></span>

<span data-ttu-id="c256c-115">Tipo di input dell'operazione da ritardare.</span><span class="sxs-lookup"><span data-stu-id="c256c-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="c256c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c256c-116">See Also</span></span>

- [<span data-ttu-id="c256c-117">Microsoft. Quantum. Canon. Delayed</span><span class="sxs-lookup"><span data-stu-id="c256c-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="c256c-118">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="c256c-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)