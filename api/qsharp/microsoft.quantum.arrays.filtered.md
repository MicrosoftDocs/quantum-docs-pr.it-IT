---
uid: Microsoft.Quantum.Arrays.Filtered
title: Funzione filtrata
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Filtered
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: fa8600f4d773daf6eabf8b9961ab46961155d1fd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221267"
---
# <a name="filtered-function"></a><span data-ttu-id="9befb-102">Funzione filtrata</span><span class="sxs-lookup"><span data-stu-id="9befb-102">Filtered function</span></span>

<span data-ttu-id="9befb-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9befb-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9befb-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9befb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9befb-105">Data una matrice e un predicato definito per gli elementi della matrice, restituisce una matrice costituita dagli elementi che soddisfano il predicato.</span><span class="sxs-lookup"><span data-stu-id="9befb-105">Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Filtered<'T> (predicate : ('T -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="9befb-106">Input</span><span class="sxs-lookup"><span data-stu-id="9befb-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="9befb-107">predicato:' t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="9befb-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="9befb-108">Funzione da `'T` a booleana utilizzata per filtrare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="9befb-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="9befb-109">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="9befb-109">array : 'T[]</span></span>

<span data-ttu-id="9befb-110">Matrice di elementi su `'T` .</span><span class="sxs-lookup"><span data-stu-id="9befb-110">An array of elements over `'T`.</span></span>



## <a name="output--t"></a><span data-ttu-id="9befb-111">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="9befb-111">Output : 'T[]</span></span>

<span data-ttu-id="9befb-112">Matrice `'T[]` di elementi che soddisfano il predicato.</span><span class="sxs-lookup"><span data-stu-id="9befb-112">An array `'T[]` of elements that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9befb-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="9befb-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9befb-114">T</span><span class="sxs-lookup"><span data-stu-id="9befb-114">'T</span></span>

<span data-ttu-id="9befb-115">Tipo di `array` elementi.</span><span class="sxs-lookup"><span data-stu-id="9befb-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="9befb-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="9befb-116">Remarks</span></span>

<span data-ttu-id="9befb-117">La funzione è definita per i tipi generici, ad esempio ogni volta che sono presenti una matrice `'T[]` e un predicato, è `'T -> Bool` possibile filtrare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="9befb-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>