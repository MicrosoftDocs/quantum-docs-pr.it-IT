---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationC
title: Operazione ApplyWithInputTransformationC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationC
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: 030c41d3ce0a5d613a95c6511f7278497ec5cda1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217170"
---
# <a name="applywithinputtransformationc-operation"></a><span data-ttu-id="7c428-102">Operazione ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="7c428-102">ApplyWithInputTransformationC operation</span></span>

<span data-ttu-id="7c428-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7c428-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7c428-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7c428-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7c428-105">Data un'operazione che accetta un input, una funzione che restituisce un output compatibile con tale operazione e un input per tale funzione, applica l'operazione usando la funzione per trasformare l'input in un form previsto dall'operazione.</span><span class="sxs-lookup"><span data-stu-id="7c428-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationC<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Ctl), input : 'U) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="7c428-106">Input</span><span class="sxs-lookup"><span data-stu-id="7c428-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="7c428-107">FN:' U->' t</span><span class="sxs-lookup"><span data-stu-id="7c428-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="7c428-108">Funzione che trasforma l'input specificato in un form previsto dall'operazione.</span><span class="sxs-lookup"><span data-stu-id="7c428-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="7c428-109">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL</span><span class="sxs-lookup"><span data-stu-id="7c428-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="7c428-110">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="7c428-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="7c428-111">input:' U</span><span class="sxs-lookup"><span data-stu-id="7c428-111">input : 'U</span></span>

<span data-ttu-id="7c428-112">Input della funzione.</span><span class="sxs-lookup"><span data-stu-id="7c428-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7c428-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7c428-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7c428-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="7c428-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7c428-115">T</span><span class="sxs-lookup"><span data-stu-id="7c428-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="7c428-116">' U</span><span class="sxs-lookup"><span data-stu-id="7c428-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="7c428-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c428-117">See Also</span></span>

- [<span data-ttu-id="7c428-118">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="7c428-118">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="7c428-119">Microsoft. Quantum. Canon. ApplyWithInputTransformationA</span><span class="sxs-lookup"><span data-stu-id="7c428-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="7c428-120">Microsoft. Quantum. Canon. ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="7c428-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="7c428-121">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="7c428-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)