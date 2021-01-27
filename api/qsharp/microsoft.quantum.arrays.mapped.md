---
uid: Microsoft.Quantum.Arrays.Mapped
title: Funzione mappata
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Mapped
qsharp.summary: Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 00ea0803faf6e8edfa748af63dd6c7e217b1de41
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845680"
---
# <a name="mapped-function"></a><span data-ttu-id="d348d-102">Funzione mappata</span><span class="sxs-lookup"><span data-stu-id="d348d-102">Mapped function</span></span>

<span data-ttu-id="d348d-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d348d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d348d-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d348d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d348d-105">Data una matrice e una funzione definita per gli elementi della matrice, restituisce una nuova matrice costituita dalle immagini della matrice originale nella funzione.</span><span class="sxs-lookup"><span data-stu-id="d348d-105">Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function Mapped<'T, 'U> (mapper : ('T -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="d348d-106">Input</span><span class="sxs-lookup"><span data-stu-id="d348d-106">Input</span></span>

### <a name="mapper--t---u"></a><span data-ttu-id="d348d-107">Mapper:' t->' U</span><span class="sxs-lookup"><span data-stu-id="d348d-107">mapper : 'T -> 'U</span></span>

<span data-ttu-id="d348d-108">Funzione da `'T` a `'U` utilizzata per eseguire il mapping degli elementi.</span><span class="sxs-lookup"><span data-stu-id="d348d-108">A function from `'T` to `'U` that is used to map elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="d348d-109">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="d348d-109">array : 'T[]</span></span>

<span data-ttu-id="d348d-110">Matrice di elementi su `'T` .</span><span class="sxs-lookup"><span data-stu-id="d348d-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="d348d-111">Output:' U []</span><span class="sxs-lookup"><span data-stu-id="d348d-111">Output : 'U[]</span></span>

<span data-ttu-id="d348d-112">Matrice `'U[]` di elementi mappati dalla `mapper` funzione.</span><span class="sxs-lookup"><span data-stu-id="d348d-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d348d-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="d348d-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d348d-114">T</span><span class="sxs-lookup"><span data-stu-id="d348d-114">'T</span></span>

<span data-ttu-id="d348d-115">Tipo di `array` elementi.</span><span class="sxs-lookup"><span data-stu-id="d348d-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="d348d-116">' U</span><span class="sxs-lookup"><span data-stu-id="d348d-116">'U</span></span>

<span data-ttu-id="d348d-117">Tipo di risultato della `mapper` funzione.</span><span class="sxs-lookup"><span data-stu-id="d348d-117">The result type of the `mapper` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="d348d-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="d348d-118">Remarks</span></span>

<span data-ttu-id="d348d-119">La funzione viene definita per i tipi generici, ad esempio, ogni volta che si dispone di una matrice `'T[]` e di una funzione, è `mapper: 'T -> 'U` possibile eseguire il mapping degli elementi della matrice e produrre una nuova matrice di tipo `'U[]` .</span><span class="sxs-lookup"><span data-stu-id="d348d-119">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `mapper: 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>