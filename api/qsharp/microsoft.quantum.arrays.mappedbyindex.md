---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: MappedByIndex (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 430495517974b641c249fa146aa9effec542e825
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209928"
---
# <a name="mappedbyindex-function"></a><span data-ttu-id="64a16-102">MappedByIndex (funzione)</span><span class="sxs-lookup"><span data-stu-id="64a16-102">MappedByIndex function</span></span>

<span data-ttu-id="64a16-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="64a16-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="64a16-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="64a16-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="64a16-105">Data una matrice e una funzione definita per gli elementi indicizzati della matrice, restituisce una nuova matrice costituita dalle immagini della matrice originale nella funzione.</span><span class="sxs-lookup"><span data-stu-id="64a16-105">Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function MappedByIndex<'T, 'U> (mapper : ((Int, 'T) -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="64a16-106">Input</span><span class="sxs-lookup"><span data-stu-id="64a16-106">Input</span></span>

### <a name="mapper--intt---u"></a><span data-ttu-id="64a16-107">Mapper: ([int](xref:microsoft.quantum.lang-ref.int),' t)->' U</span><span class="sxs-lookup"><span data-stu-id="64a16-107">mapper : ([Int](xref:microsoft.quantum.lang-ref.int),'T) -> 'U</span></span>

<span data-ttu-id="64a16-108">Funzione da `(Int, 'T)` a `'U` utilizzata per eseguire il mapping degli elementi e dei relativi indici.</span><span class="sxs-lookup"><span data-stu-id="64a16-108">A function from `(Int, 'T)` to `'U` that is used to map elements and their indices.</span></span>


### <a name="array--t"></a><span data-ttu-id="64a16-109">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="64a16-109">array : 'T[]</span></span>

<span data-ttu-id="64a16-110">Matrice di elementi su `'T` .</span><span class="sxs-lookup"><span data-stu-id="64a16-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="64a16-111">Output:' U []</span><span class="sxs-lookup"><span data-stu-id="64a16-111">Output : 'U[]</span></span>

<span data-ttu-id="64a16-112">Matrice `'U[]` di elementi mappati dalla `mapper` funzione.</span><span class="sxs-lookup"><span data-stu-id="64a16-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="64a16-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="64a16-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="64a16-114">T</span><span class="sxs-lookup"><span data-stu-id="64a16-114">'T</span></span>

<span data-ttu-id="64a16-115">Tipo di `array` elementi.</span><span class="sxs-lookup"><span data-stu-id="64a16-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="64a16-116">' U</span><span class="sxs-lookup"><span data-stu-id="64a16-116">'U</span></span>

<span data-ttu-id="64a16-117">Tipo di risultato della `mapper` funzione.</span><span class="sxs-lookup"><span data-stu-id="64a16-117">The result type of the `mapper` function.</span></span>

## <a name="see-also"></a><span data-ttu-id="64a16-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64a16-118">See Also</span></span>

- [<span data-ttu-id="64a16-119">Microsoft. Quantum. Arrays. mapping</span><span class="sxs-lookup"><span data-stu-id="64a16-119">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)