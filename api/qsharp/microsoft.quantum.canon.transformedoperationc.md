---
uid: Microsoft.Quantum.Canon.TransformedOperationC
title: TransformedOperationC (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationC
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: 9475c5a1cc3b7e14c56c301749311a72e15f71e0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852035"
---
# <a name="transformedoperationc-function"></a><span data-ttu-id="27b9f-102">TransformedOperationC (funzione)</span><span class="sxs-lookup"><span data-stu-id="27b9f-102">TransformedOperationC function</span></span>

<span data-ttu-id="27b9f-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="27b9f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="27b9f-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="27b9f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="27b9f-105">Data una funzione e un'operazione, restituisce una nuova operazione il cui input viene trasformato dalla funzione specificata.</span><span class="sxs-lookup"><span data-stu-id="27b9f-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperationC<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Ctl)) : ('U => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="27b9f-106">Input</span><span class="sxs-lookup"><span data-stu-id="27b9f-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="27b9f-107">FN:' U->' t</span><span class="sxs-lookup"><span data-stu-id="27b9f-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="27b9f-108">Funzione che trasforma l'input specificato in un form previsto dall'operazione.</span><span class="sxs-lookup"><span data-stu-id="27b9f-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="27b9f-109">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL</span><span class="sxs-lookup"><span data-stu-id="27b9f-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="27b9f-110">Operazione da trasformare.</span><span class="sxs-lookup"><span data-stu-id="27b9f-110">The operation to be transformed.</span></span>



## <a name="output--u--unit--is-ctl"></a><span data-ttu-id="27b9f-111">Output:' U => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL</span><span class="sxs-lookup"><span data-stu-id="27b9f-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="27b9f-112">Una nuova operazione TBAT chiama `fn` con l'input, quindi passa l'output risultante a `op` .</span><span class="sxs-lookup"><span data-stu-id="27b9f-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="27b9f-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="27b9f-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="27b9f-114">T</span><span class="sxs-lookup"><span data-stu-id="27b9f-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="27b9f-115">' U</span><span class="sxs-lookup"><span data-stu-id="27b9f-115">'U</span></span>



## <a name="example"></a><span data-ttu-id="27b9f-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="27b9f-116">Example</span></span>

<span data-ttu-id="27b9f-117">La chiamata seguente usa @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" per trasformare un'operazione progettata per gli @"Microsoft.Quantum.Arithmetic.BigEndian" input in un'operazione che accetta input di tipo @"Microsoft.Quantum.Arithmetic.LittleEndian" :</span><span class="sxs-lookup"><span data-stu-id="27b9f-117">The following call uses @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" to transform an operation designed for @"Microsoft.Quantum.Arithmetic.BigEndian" inputs into an operation that accepts inputs of type @"Microsoft.Quantum.Arithmetic.LittleEndian":</span></span>

```qsharp
let leOp = TransformedOperation(LittleEndianAsBigEndian, ApplyXorInPlaceBE);
```

## <a name="see-also"></a><span data-ttu-id="27b9f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27b9f-118">See Also</span></span>

- [<span data-ttu-id="27b9f-119">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="27b9f-119">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [<span data-ttu-id="27b9f-120">Microsoft. Quantum. Canon. TransformedOperationA</span><span class="sxs-lookup"><span data-stu-id="27b9f-120">Microsoft.Quantum.Canon.TransformedOperationA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [<span data-ttu-id="27b9f-121">Microsoft. Quantum. Canon. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="27b9f-121">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="27b9f-122">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="27b9f-122">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="27b9f-123">Microsoft. Quantum. Canon. compose</span><span class="sxs-lookup"><span data-stu-id="27b9f-123">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)