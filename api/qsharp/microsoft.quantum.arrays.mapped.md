---
uid: Microsoft.Quantum.Arrays.Mapped
title: Funzione mappata
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Mapped
qsharp.summary: Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 9632b9f53ffad8ece958ab1dc9ad446c7dcb9e13
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220740"
---
# <a name="mapped-function"></a><span data-ttu-id="2394e-102">Funzione mappata</span><span class="sxs-lookup"><span data-stu-id="2394e-102">Mapped function</span></span>

<span data-ttu-id="2394e-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2394e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2394e-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2394e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2394e-105">Data una matrice e una funzione definita per gli elementi della matrice, restituisce una nuova matrice costituita dalle immagini della matrice originale nella funzione.</span><span class="sxs-lookup"><span data-stu-id="2394e-105">Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function Mapped<'T, 'U> (mapper : ('T -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="2394e-106">Input</span><span class="sxs-lookup"><span data-stu-id="2394e-106">Input</span></span>

### <a name="mapper--t---u"></a><span data-ttu-id="2394e-107">Mapper:' t->' U</span><span class="sxs-lookup"><span data-stu-id="2394e-107">mapper : 'T -> 'U</span></span>

<span data-ttu-id="2394e-108">Funzione da `'T` a `'U` utilizzata per eseguire il mapping degli elementi.</span><span class="sxs-lookup"><span data-stu-id="2394e-108">A function from `'T` to `'U` that is used to map elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="2394e-109">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="2394e-109">array : 'T[]</span></span>

<span data-ttu-id="2394e-110">Matrice di elementi su `'T` .</span><span class="sxs-lookup"><span data-stu-id="2394e-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="2394e-111">Output:' U []</span><span class="sxs-lookup"><span data-stu-id="2394e-111">Output : 'U[]</span></span>

<span data-ttu-id="2394e-112">Matrice `'U[]` di elementi mappati dalla `mapper` funzione.</span><span class="sxs-lookup"><span data-stu-id="2394e-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2394e-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="2394e-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2394e-114">T</span><span class="sxs-lookup"><span data-stu-id="2394e-114">'T</span></span>

<span data-ttu-id="2394e-115">Tipo di `array` elementi.</span><span class="sxs-lookup"><span data-stu-id="2394e-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="2394e-116">' U</span><span class="sxs-lookup"><span data-stu-id="2394e-116">'U</span></span>

<span data-ttu-id="2394e-117">Tipo di risultato della `mapper` funzione.</span><span class="sxs-lookup"><span data-stu-id="2394e-117">The result type of the `mapper` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="2394e-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="2394e-118">Remarks</span></span>

<span data-ttu-id="2394e-119">La funzione viene definita per i tipi generici, ad esempio, ogni volta che si dispone di una matrice `'T[]` e di una funzione, è `mapper: 'T -> 'U` possibile eseguire il mapping degli elementi della matrice e produrre una nuova matrice di tipo `'U[]` .</span><span class="sxs-lookup"><span data-stu-id="2394e-119">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `mapper: 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>