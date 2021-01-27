---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationC
title: Operazione ApplyWithInputTransformationC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationC
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: d877fedbc0caa1a9ebc87d80cbce9ab54ca20d88
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850364"
---
# <a name="applywithinputtransformationc-operation"></a><span data-ttu-id="39b25-102">Operazione ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="39b25-102">ApplyWithInputTransformationC operation</span></span>

<span data-ttu-id="39b25-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="39b25-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="39b25-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="39b25-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="39b25-105">Data un'operazione che accetta un input, una funzione che restituisce un output compatibile con tale operazione e un input per tale funzione, applica l'operazione usando la funzione per trasformare l'input in un form previsto dall'operazione.</span><span class="sxs-lookup"><span data-stu-id="39b25-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationC<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Ctl), input : 'U) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="39b25-106">Input</span><span class="sxs-lookup"><span data-stu-id="39b25-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="39b25-107">FN:' U->' t</span><span class="sxs-lookup"><span data-stu-id="39b25-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="39b25-108">Funzione che trasforma l'input specificato in un form previsto dall'operazione.</span><span class="sxs-lookup"><span data-stu-id="39b25-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="39b25-109">op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è CTL</span><span class="sxs-lookup"><span data-stu-id="39b25-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="39b25-110">Operazione da applicare.</span><span class="sxs-lookup"><span data-stu-id="39b25-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="39b25-111">input:' U</span><span class="sxs-lookup"><span data-stu-id="39b25-111">input : 'U</span></span>

<span data-ttu-id="39b25-112">Input della funzione.</span><span class="sxs-lookup"><span data-stu-id="39b25-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="39b25-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="39b25-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="39b25-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="39b25-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="39b25-115">T</span><span class="sxs-lookup"><span data-stu-id="39b25-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="39b25-116">' U</span><span class="sxs-lookup"><span data-stu-id="39b25-116">'U</span></span>



## <a name="example"></a><span data-ttu-id="39b25-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="39b25-117">Example</span></span>

<span data-ttu-id="39b25-118">La chiamata seguente usa @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" per applicare un'operazione progettata per gli @"Microsoft.Quantum.Arithmetic.BigEndian" input a un input di tipo @"Microsoft.Quantum.Arithmetic.LittleEndian" :</span><span class="sxs-lookup"><span data-stu-id="39b25-118">The following call uses @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" to apply an operation designed for @"Microsoft.Quantum.Arithmetic.BigEndian" inputs to an input of type @"Microsoft.Quantum.Arithmetic.LittleEndian":</span></span>

```qsharp
ApplyWithInputTransformation(LittleEndianAsBigEndian, ApplyXorInPlaceBE, LittleEndian(qubits));
```

## <a name="see-also"></a><span data-ttu-id="39b25-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39b25-119">See Also</span></span>

- [<span data-ttu-id="39b25-120">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="39b25-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="39b25-121">Microsoft. Quantum. Canon. ApplyWithInputTransformationA</span><span class="sxs-lookup"><span data-stu-id="39b25-121">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="39b25-122">Microsoft. Quantum. Canon. ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="39b25-122">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="39b25-123">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="39b25-123">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)