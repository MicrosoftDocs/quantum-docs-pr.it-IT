---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationA
title: Operazione ApplyWithInputTransformationA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: 3ab07f301f310e3ec380981bdb53201fc74bd289
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841131"
---
# <a name="applywithinputtransformationa-operation"></a><span data-ttu-id="365e5-102">Operazione ApplyWithInputTransformationA</span><span class="sxs-lookup"><span data-stu-id="365e5-102">ApplyWithInputTransformationA operation</span></span>

<span data-ttu-id="365e5-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="365e5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="365e5-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="365e5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="365e5-105">Data un'operazione che accetta un input, una funzione che restituisce un output compatibile con tale operazione e un input per tale funzione, applica l'operazione usando la funzione per trasformare l'input in un form previsto dall'operazione.</span><span class="sxs-lookup"><span data-stu-id="365e5-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj), input : 'U) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="365e5-106">Input</span><span class="sxs-lookup"><span data-stu-id="365e5-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="365e5-107">FN:' U->' t</span><span class="sxs-lookup"><span data-stu-id="365e5-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="365e5-108">Funzione che trasforma l'input specificato in un form previsto dall'operazione.</span><span class="sxs-lookup"><span data-stu-id="365e5-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-adj"></a><span data-ttu-id="365e5-109">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ</span><span class="sxs-lookup"><span data-stu-id="365e5-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="365e5-110">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="365e5-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="365e5-111">input:' U</span><span class="sxs-lookup"><span data-stu-id="365e5-111">input : 'U</span></span>

<span data-ttu-id="365e5-112">Input della funzione.</span><span class="sxs-lookup"><span data-stu-id="365e5-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="365e5-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="365e5-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="365e5-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="365e5-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="365e5-115">T</span><span class="sxs-lookup"><span data-stu-id="365e5-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="365e5-116">' U</span><span class="sxs-lookup"><span data-stu-id="365e5-116">'U</span></span>



## <a name="example"></a><span data-ttu-id="365e5-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="365e5-117">Example</span></span>

<span data-ttu-id="365e5-118">La chiamata seguente usa @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" per applicare un'operazione progettata per gli @"Microsoft.Quantum.Arithmetic.BigEndian" input a un input di tipo @"Microsoft.Quantum.Arithmetic.LittleEndian" :</span><span class="sxs-lookup"><span data-stu-id="365e5-118">The following call uses @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" to apply an operation designed for @"Microsoft.Quantum.Arithmetic.BigEndian" inputs to an input of type @"Microsoft.Quantum.Arithmetic.LittleEndian":</span></span>

```qsharp
ApplyWithInputTransformation(LittleEndianAsBigEndian, ApplyXorInPlaceBE, LittleEndian(qubits));
```

## <a name="see-also"></a><span data-ttu-id="365e5-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="365e5-119">See Also</span></span>

- [<span data-ttu-id="365e5-120">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="365e5-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="365e5-121">Microsoft. Quantum. Canon. ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="365e5-121">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="365e5-122">Microsoft. Quantum. Canon. ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="365e5-122">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="365e5-123">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="365e5-123">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)