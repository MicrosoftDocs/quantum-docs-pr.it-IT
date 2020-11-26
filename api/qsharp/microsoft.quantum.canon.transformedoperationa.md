---
uid: Microsoft.Quantum.Canon.TransformedOperationA
title: TransformedOperationA (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationA
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: eceba260e601b73bdfa2de6ea6ab146820b5c59a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204879"
---
# <a name="transformedoperationa-function"></a><span data-ttu-id="e2d2e-102">TransformedOperationA (funzione)</span><span class="sxs-lookup"><span data-stu-id="e2d2e-102">TransformedOperationA function</span></span>

<span data-ttu-id="e2d2e-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e2d2e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e2d2e-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e2d2e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e2d2e-105">Data una funzione e un'operazione, restituisce una nuova operazione il cui input viene trasformato dalla funzione specificata.</span><span class="sxs-lookup"><span data-stu-id="e2d2e-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperationA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj)) : ('U => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="e2d2e-106">Input</span><span class="sxs-lookup"><span data-stu-id="e2d2e-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="e2d2e-107">FN:' U->' t</span><span class="sxs-lookup"><span data-stu-id="e2d2e-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="e2d2e-108">Funzione che trasforma l'input specificato in un form previsto dall'operazione.</span><span class="sxs-lookup"><span data-stu-id="e2d2e-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-adj"></a><span data-ttu-id="e2d2e-109">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ</span><span class="sxs-lookup"><span data-stu-id="e2d2e-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="e2d2e-110">Operazione da trasformare.</span><span class="sxs-lookup"><span data-stu-id="e2d2e-110">The operation to be transformed.</span></span>



## <a name="output--u--unit--is-adj"></a><span data-ttu-id="e2d2e-111">Output:' U => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ</span><span class="sxs-lookup"><span data-stu-id="e2d2e-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="e2d2e-112">Una nuova operazione TBAT chiama `fn` con l'input, quindi passa l'output risultante a `op` .</span><span class="sxs-lookup"><span data-stu-id="e2d2e-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e2d2e-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="e2d2e-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e2d2e-114">T</span><span class="sxs-lookup"><span data-stu-id="e2d2e-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="e2d2e-115">' U</span><span class="sxs-lookup"><span data-stu-id="e2d2e-115">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="e2d2e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2d2e-116">See Also</span></span>

- [<span data-ttu-id="e2d2e-117">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="e2d2e-117">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [<span data-ttu-id="e2d2e-118">Microsoft. Quantum. Canon. TransformedOperationC</span><span class="sxs-lookup"><span data-stu-id="e2d2e-118">Microsoft.Quantum.Canon.TransformedOperationC</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [<span data-ttu-id="e2d2e-119">Microsoft. Quantum. Canon. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="e2d2e-119">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="e2d2e-120">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="e2d2e-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="e2d2e-121">Microsoft. Quantum. Canon. compose</span><span class="sxs-lookup"><span data-stu-id="e2d2e-121">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)