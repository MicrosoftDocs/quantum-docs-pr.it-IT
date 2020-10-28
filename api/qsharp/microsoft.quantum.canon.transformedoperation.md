---
uid: Microsoft.Quantum.Canon.TransformedOperation
title: TransformedOperation (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperation
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: d8c2f52290ce89d0a8ff138ba25f6b2e5e0516d5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715336"
---
# <a name="transformedoperation-function"></a><span data-ttu-id="e99af-102">TransformedOperation (funzione)</span><span class="sxs-lookup"><span data-stu-id="e99af-102">TransformedOperation function</span></span>

<span data-ttu-id="e99af-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e99af-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e99af-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e99af-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e99af-105">Data una funzione e un'operazione, restituisce una nuova operazione il cui input viene trasformato dalla funzione specificata.</span><span class="sxs-lookup"><span data-stu-id="e99af-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit)) : ('U => Unit)
```


## <a name="input"></a><span data-ttu-id="e99af-106">Input</span><span class="sxs-lookup"><span data-stu-id="e99af-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="e99af-107">FN:' U->' t</span><span class="sxs-lookup"><span data-stu-id="e99af-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="e99af-108">Funzione che trasforma l'input specificato in un form previsto dall'operazione.</span><span class="sxs-lookup"><span data-stu-id="e99af-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="e99af-109">op:' t = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="e99af-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="e99af-110">Operazione da trasformare.</span><span class="sxs-lookup"><span data-stu-id="e99af-110">The operation to be transformed.</span></span>



## <a name="output--u--unit"></a><span data-ttu-id="e99af-111">Output:' U => [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e99af-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="e99af-112">Una nuova operazione TBAT chiama `fn` con l'input, quindi passa l'output risultante a `op` .</span><span class="sxs-lookup"><span data-stu-id="e99af-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e99af-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="e99af-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e99af-114">T</span><span class="sxs-lookup"><span data-stu-id="e99af-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="e99af-115">' U</span><span class="sxs-lookup"><span data-stu-id="e99af-115">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="e99af-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e99af-116">See Also</span></span>

- [<span data-ttu-id="e99af-117">Microsoft. Quantum. Canon. TransformedOperationA</span><span class="sxs-lookup"><span data-stu-id="e99af-117">Microsoft.Quantum.Canon.TransformedOperationA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [<span data-ttu-id="e99af-118">Microsoft. Quantum. Canon. TransformedOperationC</span><span class="sxs-lookup"><span data-stu-id="e99af-118">Microsoft.Quantum.Canon.TransformedOperationC</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [<span data-ttu-id="e99af-119">Microsoft. Quantum. Canon. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="e99af-119">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="e99af-120">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="e99af-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="e99af-121">Microsoft. Quantum. Canon. compose</span><span class="sxs-lookup"><span data-stu-id="e99af-121">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)