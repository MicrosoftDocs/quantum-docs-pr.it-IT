---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformation
title: Operazione ApplyWithInputTransformation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformation
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: d4589acbe9f9dc6c6ab665582ed663dbc193edbb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850366"
---
# <a name="applywithinputtransformation-operation"></a><span data-ttu-id="2426f-102">Operazione ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="2426f-102">ApplyWithInputTransformation operation</span></span>

<span data-ttu-id="2426f-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2426f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2426f-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2426f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2426f-105">Data un'operazione che accetta un input, una funzione che restituisce un output compatibile con tale operazione e un input per tale funzione, applica l'operazione usando la funzione per trasformare l'input in un form previsto dall'operazione.</span><span class="sxs-lookup"><span data-stu-id="2426f-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit), input : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="2426f-106">Input</span><span class="sxs-lookup"><span data-stu-id="2426f-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="2426f-107">FN:' U->' t</span><span class="sxs-lookup"><span data-stu-id="2426f-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="2426f-108">Funzione che trasforma l'input specificato in un form previsto dall'operazione.</span><span class="sxs-lookup"><span data-stu-id="2426f-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="2426f-109">op:' t = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="2426f-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="2426f-110">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="2426f-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="2426f-111">input:' U</span><span class="sxs-lookup"><span data-stu-id="2426f-111">input : 'U</span></span>

<span data-ttu-id="2426f-112">Input della funzione.</span><span class="sxs-lookup"><span data-stu-id="2426f-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2426f-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2426f-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2426f-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="2426f-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2426f-115">T</span><span class="sxs-lookup"><span data-stu-id="2426f-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="2426f-116">' U</span><span class="sxs-lookup"><span data-stu-id="2426f-116">'U</span></span>



## <a name="example"></a><span data-ttu-id="2426f-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="2426f-117">Example</span></span>

<span data-ttu-id="2426f-118">La chiamata seguente usa @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" per applicare un'operazione progettata per gli @"Microsoft.Quantum.Arithmetic.BigEndian" input a un input di tipo @"Microsoft.Quantum.Arithmetic.LittleEndian" :</span><span class="sxs-lookup"><span data-stu-id="2426f-118">The following call uses @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" to apply an operation designed for @"Microsoft.Quantum.Arithmetic.BigEndian" inputs to an input of type @"Microsoft.Quantum.Arithmetic.LittleEndian":</span></span>

```qsharp
ApplyWithInputTransformation(LittleEndianAsBigEndian, ApplyXorInPlaceBE, LittleEndian(qubits));
```

## <a name="see-also"></a><span data-ttu-id="2426f-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2426f-119">See Also</span></span>

- [<span data-ttu-id="2426f-120">Microsoft. Quantum. Canon. ApplyWithInputTransformationA</span><span class="sxs-lookup"><span data-stu-id="2426f-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="2426f-121">Microsoft. Quantum. Canon. ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="2426f-121">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="2426f-122">Microsoft. Quantum. Canon. ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="2426f-122">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="2426f-123">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="2426f-123">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)