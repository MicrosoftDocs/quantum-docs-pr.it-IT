---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformation
title: Operazione ApplyWithInputTransformation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformation
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: 2b7863337ef724d9c3ba10201a9a01d0b2226ea8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716862"
---
# <a name="applywithinputtransformation-operation"></a><span data-ttu-id="d3d8f-102">Operazione ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="d3d8f-102">ApplyWithInputTransformation operation</span></span>

<span data-ttu-id="d3d8f-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d3d8f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d3d8f-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d3d8f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d3d8f-105">Data un'operazione che accetta un input, una funzione che restituisce un output compatibile con tale operazione e un input per tale funzione, applica l'operazione usando la funzione per trasformare l'input in un form previsto dall'operazione.</span><span class="sxs-lookup"><span data-stu-id="d3d8f-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit), input : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="d3d8f-106">Input</span><span class="sxs-lookup"><span data-stu-id="d3d8f-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="d3d8f-107">FN:' U->' t</span><span class="sxs-lookup"><span data-stu-id="d3d8f-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="d3d8f-108">Funzione che trasforma l'input specificato in un form previsto dall'operazione.</span><span class="sxs-lookup"><span data-stu-id="d3d8f-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="d3d8f-109">op:' t = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="d3d8f-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="d3d8f-110">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="d3d8f-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="d3d8f-111">input:' U</span><span class="sxs-lookup"><span data-stu-id="d3d8f-111">input : 'U</span></span>

<span data-ttu-id="d3d8f-112">Input della funzione.</span><span class="sxs-lookup"><span data-stu-id="d3d8f-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d3d8f-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d3d8f-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d3d8f-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="d3d8f-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d3d8f-115">T</span><span class="sxs-lookup"><span data-stu-id="d3d8f-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="d3d8f-116">' U</span><span class="sxs-lookup"><span data-stu-id="d3d8f-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="d3d8f-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3d8f-117">See Also</span></span>

- [<span data-ttu-id="d3d8f-118">Microsoft. Quantum. Canon. ApplyWithInputTransformationA</span><span class="sxs-lookup"><span data-stu-id="d3d8f-118">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="d3d8f-119">Microsoft. Quantum. Canon. ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="d3d8f-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="d3d8f-120">Microsoft. Quantum. Canon. ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="d3d8f-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="d3d8f-121">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="d3d8f-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)