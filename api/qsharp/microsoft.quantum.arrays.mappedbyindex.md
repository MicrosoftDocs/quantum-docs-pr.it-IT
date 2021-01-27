---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: MappedByIndex (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 584cabcb7b6059ae5d311f13f5f75bd1f87bdba5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845656"
---
# <a name="mappedbyindex-function"></a><span data-ttu-id="0c055-102">MappedByIndex (funzione)</span><span class="sxs-lookup"><span data-stu-id="0c055-102">MappedByIndex function</span></span>

<span data-ttu-id="0c055-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="0c055-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="0c055-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0c055-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0c055-105">Data una matrice e una funzione definita per gli elementi indicizzati della matrice, restituisce una nuova matrice costituita dalle immagini della matrice originale nella funzione.</span><span class="sxs-lookup"><span data-stu-id="0c055-105">Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function MappedByIndex<'T, 'U> (mapper : ((Int, 'T) -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="0c055-106">Input</span><span class="sxs-lookup"><span data-stu-id="0c055-106">Input</span></span>

### <a name="mapper--intt---u"></a><span data-ttu-id="0c055-107">Mapper: ([int](xref:microsoft.quantum.lang-ref.int),' t)->' U</span><span class="sxs-lookup"><span data-stu-id="0c055-107">mapper : ([Int](xref:microsoft.quantum.lang-ref.int),'T) -> 'U</span></span>

<span data-ttu-id="0c055-108">Funzione da `(Int, 'T)` a `'U` utilizzata per eseguire il mapping degli elementi e dei relativi indici.</span><span class="sxs-lookup"><span data-stu-id="0c055-108">A function from `(Int, 'T)` to `'U` that is used to map elements and their indices.</span></span>


### <a name="array--t"></a><span data-ttu-id="0c055-109">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="0c055-109">array : 'T[]</span></span>

<span data-ttu-id="0c055-110">Matrice di elementi su `'T` .</span><span class="sxs-lookup"><span data-stu-id="0c055-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="0c055-111">Output:' U []</span><span class="sxs-lookup"><span data-stu-id="0c055-111">Output : 'U[]</span></span>

<span data-ttu-id="0c055-112">Matrice `'U[]` di elementi mappati dalla `mapper` funzione.</span><span class="sxs-lookup"><span data-stu-id="0c055-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0c055-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="0c055-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0c055-114">T</span><span class="sxs-lookup"><span data-stu-id="0c055-114">'T</span></span>

<span data-ttu-id="0c055-115">Tipo di `array` elementi.</span><span class="sxs-lookup"><span data-stu-id="0c055-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="0c055-116">' U</span><span class="sxs-lookup"><span data-stu-id="0c055-116">'U</span></span>

<span data-ttu-id="0c055-117">Tipo di risultato della `mapper` funzione.</span><span class="sxs-lookup"><span data-stu-id="0c055-117">The result type of the `mapper` function.</span></span>

## <a name="example"></a><span data-ttu-id="0c055-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="0c055-118">Example</span></span>

<span data-ttu-id="0c055-119">Le due righe seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="0c055-119">The following two lines are equivalent:</span></span>

```qsharp
let arr = MapIndex(f, [x0, x1, x2]);
```

<span data-ttu-id="0c055-120">e</span><span class="sxs-lookup"><span data-stu-id="0c055-120">and</span></span>

```qsharp
let arr = [f(0, x0), f(1, x1), f(2, x2)];
```

## <a name="see-also"></a><span data-ttu-id="0c055-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c055-121">See Also</span></span>

- [<span data-ttu-id="0c055-122">Microsoft. Quantum. Arrays. mapping</span><span class="sxs-lookup"><span data-stu-id="0c055-122">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)