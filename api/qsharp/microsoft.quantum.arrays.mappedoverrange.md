---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: MappedOverRange (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: 7093043e2a290e6132774b8fe154d3627a254f27
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845643"
---
# <a name="mappedoverrange-function"></a><span data-ttu-id="b092d-102">MappedOverRange (funzione)</span><span class="sxs-lookup"><span data-stu-id="b092d-102">MappedOverRange function</span></span>

<span data-ttu-id="b092d-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b092d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b092d-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b092d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b092d-105">Dato un intervallo e una funzione che accetta un Integer come input, restituisce una nuova matrice costituita dalle immagini dei valori di intervallo nella funzione.</span><span class="sxs-lookup"><span data-stu-id="b092d-105">Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.</span></span>

```qsharp
function MappedOverRange<'T> (mapper : (Int -> 'T), range : Range) : 'T[]
```


## <a name="input"></a><span data-ttu-id="b092d-106">Input</span><span class="sxs-lookup"><span data-stu-id="b092d-106">Input</span></span>

### <a name="mapper--int---t"></a><span data-ttu-id="b092d-107">Mapper: [int](xref:microsoft.quantum.lang-ref.int) ->' t</span><span class="sxs-lookup"><span data-stu-id="b092d-107">mapper : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="b092d-108">Funzione da `Int` a `'T` utilizzata per eseguire il mapping dei valori di intervallo.</span><span class="sxs-lookup"><span data-stu-id="b092d-108">A function from `Int` to `'T` that is used to map range values.</span></span>


### <a name="range--range"></a><span data-ttu-id="b092d-109">intervallo: [intervallo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="b092d-109">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="b092d-110">Un intervallo di numeri interi.</span><span class="sxs-lookup"><span data-stu-id="b092d-110">A range of integers.</span></span>



## <a name="output--t"></a><span data-ttu-id="b092d-111">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="b092d-111">Output : 'T[]</span></span>

<span data-ttu-id="b092d-112">Matrice `'T[]` di elementi mappati dalla `mapper` funzione.</span><span class="sxs-lookup"><span data-stu-id="b092d-112">An array `'T[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b092d-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="b092d-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b092d-114">T</span><span class="sxs-lookup"><span data-stu-id="b092d-114">'T</span></span>

<span data-ttu-id="b092d-115">Tipo di risultato della `mapper` funzione.</span><span class="sxs-lookup"><span data-stu-id="b092d-115">The result type of the `mapper` function.</span></span>

## <a name="example"></a><span data-ttu-id="b092d-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="b092d-116">Example</span></span>

<span data-ttu-id="b092d-117">Questo esempio aggiunge 1 a un intervallo di numeri pari:</span><span class="sxs-lookup"><span data-stu-id="b092d-117">This example adds 1 to a range of even numbers:</span></span>

```qsharp
let numbers = MappedOverRange(PlusI(1, _), 0..2..10);
// numbers = [1, 3, 5, 7, 9, 11]
```

## <a name="remarks"></a><span data-ttu-id="b092d-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="b092d-118">Remarks</span></span>

<span data-ttu-id="b092d-119">La funzione è definita per i tipi generici, ad esempio ogni volta che è presente una funzione, è `mapper: Int -> 'T` possibile eseguire il mapping dei valori dell'intervallo e produrre una matrice di tipo `'T[]` .</span><span class="sxs-lookup"><span data-stu-id="b092d-119">The function is defined for generic types, i.e., whenever we have a function `mapper: Int -> 'T` we can map the values of the range and produce an array of type `'T[]`.</span></span>

## <a name="see-also"></a><span data-ttu-id="b092d-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b092d-120">See Also</span></span>

- [<span data-ttu-id="b092d-121">Microsoft. Quantum. Arrays. mapping</span><span class="sxs-lookup"><span data-stu-id="b092d-121">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)