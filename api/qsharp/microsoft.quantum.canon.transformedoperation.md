---
uid: Microsoft.Quantum.Canon.TransformedOperation
title: TransformedOperation (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperation
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: 9f564fee38fb22283da4807f829ddc5ec156bf3d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852064"
---
# <a name="transformedoperation-function"></a><span data-ttu-id="5c3fd-102">TransformedOperation (funzione)</span><span class="sxs-lookup"><span data-stu-id="5c3fd-102">TransformedOperation function</span></span>

<span data-ttu-id="5c3fd-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5c3fd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5c3fd-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5c3fd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5c3fd-105">Data una funzione e un'operazione, restituisce una nuova operazione il cui input viene trasformato dalla funzione specificata.</span><span class="sxs-lookup"><span data-stu-id="5c3fd-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit)) : ('U => Unit)
```


## <a name="input"></a><span data-ttu-id="5c3fd-106">Input</span><span class="sxs-lookup"><span data-stu-id="5c3fd-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="5c3fd-107">FN:' U->' t</span><span class="sxs-lookup"><span data-stu-id="5c3fd-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="5c3fd-108">Funzione che trasforma l'input specificato in un form previsto dall'operazione.</span><span class="sxs-lookup"><span data-stu-id="5c3fd-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="5c3fd-109">op:' t = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="5c3fd-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="5c3fd-110">Operazione da trasformare.</span><span class="sxs-lookup"><span data-stu-id="5c3fd-110">The operation to be transformed.</span></span>



## <a name="output--u--unit"></a><span data-ttu-id="5c3fd-111">Output:' U => [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5c3fd-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="5c3fd-112">Una nuova operazione TBAT chiama `fn` con l'input, quindi passa l'output risultante a `op` .</span><span class="sxs-lookup"><span data-stu-id="5c3fd-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5c3fd-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="5c3fd-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5c3fd-114">T</span><span class="sxs-lookup"><span data-stu-id="5c3fd-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="5c3fd-115">' U</span><span class="sxs-lookup"><span data-stu-id="5c3fd-115">'U</span></span>



## <a name="example"></a><span data-ttu-id="5c3fd-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="5c3fd-116">Example</span></span>

<span data-ttu-id="5c3fd-117">La chiamata seguente usa @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" per trasformare un'operazione progettata per gli @"Microsoft.Quantum.Arithmetic.BigEndian" input in un'operazione che accetta input di tipo @"Microsoft.Quantum.Arithmetic.LittleEndian" :</span><span class="sxs-lookup"><span data-stu-id="5c3fd-117">The following call uses @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" to transform an operation designed for @"Microsoft.Quantum.Arithmetic.BigEndian" inputs into an operation that accepts inputs of type @"Microsoft.Quantum.Arithmetic.LittleEndian":</span></span>

```qsharp
let leOp = TransformedOperation(LittleEndianAsBigEndian, ApplyXorInPlaceBE);
```

## <a name="see-also"></a><span data-ttu-id="5c3fd-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c3fd-118">See Also</span></span>

- [<span data-ttu-id="5c3fd-119">Microsoft. Quantum. Canon. TransformedOperationA</span><span class="sxs-lookup"><span data-stu-id="5c3fd-119">Microsoft.Quantum.Canon.TransformedOperationA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [<span data-ttu-id="5c3fd-120">Microsoft. Quantum. Canon. TransformedOperationC</span><span class="sxs-lookup"><span data-stu-id="5c3fd-120">Microsoft.Quantum.Canon.TransformedOperationC</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [<span data-ttu-id="5c3fd-121">Microsoft. Quantum. Canon. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="5c3fd-121">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="5c3fd-122">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="5c3fd-122">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="5c3fd-123">Microsoft. Quantum. Canon. compose</span><span class="sxs-lookup"><span data-stu-id="5c3fd-123">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)