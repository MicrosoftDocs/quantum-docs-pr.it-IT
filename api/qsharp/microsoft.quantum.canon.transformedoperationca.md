---
uid: Microsoft.Quantum.Canon.TransformedOperationCA
title: TransformedOperationCA (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationCA
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: fa204433dc8195dd27fa40980fb2262f8a3848bb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204845"
---
# <a name="transformedoperationca-function"></a><span data-ttu-id="49e3b-102">TransformedOperationCA (funzione)</span><span class="sxs-lookup"><span data-stu-id="49e3b-102">TransformedOperationCA function</span></span>

<span data-ttu-id="49e3b-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="49e3b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="49e3b-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="49e3b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="49e3b-105">Data una funzione e un'operazione, restituisce una nuova operazione il cui input viene trasformato dalla funzione specificata.</span><span class="sxs-lookup"><span data-stu-id="49e3b-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperationCA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj + Ctl)) : ('U => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="49e3b-106">Input</span><span class="sxs-lookup"><span data-stu-id="49e3b-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="49e3b-107">FN:' U->' t</span><span class="sxs-lookup"><span data-stu-id="49e3b-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="49e3b-108">Funzione che trasforma l'input specificato in un form previsto dall'operazione.</span><span class="sxs-lookup"><span data-stu-id="49e3b-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="49e3b-109">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="49e3b-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="49e3b-110">Operazione da trasformare.</span><span class="sxs-lookup"><span data-stu-id="49e3b-110">The operation to be transformed.</span></span>



## <a name="output--u--unit--is-adj--ctl"></a><span data-ttu-id="49e3b-111">Output:' U => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="49e3b-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="49e3b-112">Una nuova operazione TBAT chiama `fn` con l'input, quindi passa l'output risultante a `op` .</span><span class="sxs-lookup"><span data-stu-id="49e3b-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="49e3b-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="49e3b-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="49e3b-114">T</span><span class="sxs-lookup"><span data-stu-id="49e3b-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="49e3b-115">' U</span><span class="sxs-lookup"><span data-stu-id="49e3b-115">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="49e3b-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49e3b-116">See Also</span></span>

- [<span data-ttu-id="49e3b-117">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="49e3b-117">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [<span data-ttu-id="49e3b-118">Microsoft. Quantum. Canon. TransformedOperationA</span><span class="sxs-lookup"><span data-stu-id="49e3b-118">Microsoft.Quantum.Canon.TransformedOperationA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [<span data-ttu-id="49e3b-119">Microsoft. Quantum. Canon. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="49e3b-119">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="49e3b-120">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="49e3b-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="49e3b-121">Microsoft. Quantum. Canon. compose</span><span class="sxs-lookup"><span data-stu-id="49e3b-121">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)