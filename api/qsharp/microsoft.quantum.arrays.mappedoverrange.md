---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: MappedOverRange (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: b1d73c2503e63ed09a3d6a56421760ca29eb0c3f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220689"
---
# <a name="mappedoverrange-function"></a><span data-ttu-id="60e65-102">MappedOverRange (funzione)</span><span class="sxs-lookup"><span data-stu-id="60e65-102">MappedOverRange function</span></span>

<span data-ttu-id="60e65-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="60e65-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="60e65-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="60e65-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="60e65-105">Dato un intervallo e una funzione che accetta un Integer come input, restituisce una nuova matrice costituita dalle immagini dei valori di intervallo nella funzione.</span><span class="sxs-lookup"><span data-stu-id="60e65-105">Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.</span></span>

```qsharp
function MappedOverRange<'T> (mapper : (Int -> 'T), range : Range) : 'T[]
```


## <a name="input"></a><span data-ttu-id="60e65-106">Input</span><span class="sxs-lookup"><span data-stu-id="60e65-106">Input</span></span>

### <a name="mapper--int---t"></a><span data-ttu-id="60e65-107">Mapper: [int](xref:microsoft.quantum.lang-ref.int) ->' t</span><span class="sxs-lookup"><span data-stu-id="60e65-107">mapper : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="60e65-108">Funzione da `Int` a `'T` utilizzata per eseguire il mapping dei valori di intervallo.</span><span class="sxs-lookup"><span data-stu-id="60e65-108">A function from `Int` to `'T` that is used to map range values.</span></span>


### <a name="range--range"></a><span data-ttu-id="60e65-109">intervallo: [intervallo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="60e65-109">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="60e65-110">Un intervallo di numeri interi.</span><span class="sxs-lookup"><span data-stu-id="60e65-110">A range of integers.</span></span>



## <a name="output--t"></a><span data-ttu-id="60e65-111">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="60e65-111">Output : 'T[]</span></span>

<span data-ttu-id="60e65-112">Matrice `'T[]` di elementi mappati dalla `mapper` funzione.</span><span class="sxs-lookup"><span data-stu-id="60e65-112">An array `'T[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="60e65-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="60e65-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="60e65-114">T</span><span class="sxs-lookup"><span data-stu-id="60e65-114">'T</span></span>

<span data-ttu-id="60e65-115">Tipo di risultato della `mapper` funzione.</span><span class="sxs-lookup"><span data-stu-id="60e65-115">The result type of the `mapper` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="60e65-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="60e65-116">Remarks</span></span>

<span data-ttu-id="60e65-117">La funzione è definita per i tipi generici, ad esempio ogni volta che è presente una funzione, è `mapper: Int -> 'T` possibile eseguire il mapping dei valori dell'intervallo e produrre una matrice di tipo `'T[]` .</span><span class="sxs-lookup"><span data-stu-id="60e65-117">The function is defined for generic types, i.e., whenever we have a function `mapper: Int -> 'T` we can map the values of the range and produce an array of type `'T[]`.</span></span>

## <a name="see-also"></a><span data-ttu-id="60e65-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60e65-118">See Also</span></span>

- [<span data-ttu-id="60e65-119">Microsoft. Quantum. Arrays. mapping</span><span class="sxs-lookup"><span data-stu-id="60e65-119">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)