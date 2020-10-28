---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationCA
title: Operazione ApplyWithInputTransformationCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationCA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: c80ce0887a202a60de81c2d12fa95ce1eab59058
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716834"
---
# <a name="applywithinputtransformationca-operation"></a><span data-ttu-id="84965-102">Operazione ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="84965-102">ApplyWithInputTransformationCA operation</span></span>

<span data-ttu-id="84965-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="84965-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="84965-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="84965-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="84965-105">Data un'operazione che accetta un input, una funzione che restituisce un output compatibile con tale operazione e un input per tale funzione, applica l'operazione usando la funzione per trasformare l'input in un form previsto dall'operazione.</span><span class="sxs-lookup"><span data-stu-id="84965-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationCA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj + Ctl), input : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="84965-106">Input</span><span class="sxs-lookup"><span data-stu-id="84965-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="84965-107">FN:' U->' t</span><span class="sxs-lookup"><span data-stu-id="84965-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="84965-108">Funzione che trasforma l'input specificato in un form previsto dall'operazione.</span><span class="sxs-lookup"><span data-stu-id="84965-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="84965-109">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="84965-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="84965-110">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="84965-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="84965-111">input:' U</span><span class="sxs-lookup"><span data-stu-id="84965-111">input : 'U</span></span>

<span data-ttu-id="84965-112">Input della funzione.</span><span class="sxs-lookup"><span data-stu-id="84965-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="84965-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="84965-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="84965-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="84965-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="84965-115">T</span><span class="sxs-lookup"><span data-stu-id="84965-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="84965-116">' U</span><span class="sxs-lookup"><span data-stu-id="84965-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="84965-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84965-117">See Also</span></span>

- [<span data-ttu-id="84965-118">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="84965-118">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="84965-119">Microsoft. Quantum. Canon. ApplyWithInputTransformationA</span><span class="sxs-lookup"><span data-stu-id="84965-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="84965-120">Microsoft. Quantum. Canon. ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="84965-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="84965-121">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="84965-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)