---
uid: Microsoft.Quantum.Arrays.Count
title: Count - funzione
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Count
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 48b75cc6d6584f899223a0803f31fd174836f303
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221556"
---
# <a name="count-function"></a><span data-ttu-id="839dc-102">Count - funzione</span><span class="sxs-lookup"><span data-stu-id="839dc-102">Count function</span></span>

<span data-ttu-id="839dc-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="839dc-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="839dc-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="839dc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="839dc-105">Data una matrice e un predicato definito per gli elementi della matrice, restituisce il numero di elementi una matrice costituita dagli elementi che soddisfano il predicato.</span><span class="sxs-lookup"><span data-stu-id="839dc-105">Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Count<'T> (predicate : ('T -> Bool), array : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="839dc-106">Input</span><span class="sxs-lookup"><span data-stu-id="839dc-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="839dc-107">predicato:' t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="839dc-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="839dc-108">Funzione da `'T` a booleana utilizzata per filtrare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="839dc-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="839dc-109">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="839dc-109">array : 'T[]</span></span>

<span data-ttu-id="839dc-110">Matrice di elementi su `'T` .</span><span class="sxs-lookup"><span data-stu-id="839dc-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="839dc-111">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="839dc-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="839dc-112">Numero di elementi in `array` che soddisfano il predicato.</span><span class="sxs-lookup"><span data-stu-id="839dc-112">The number of elements in `array` that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="839dc-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="839dc-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="839dc-114">T</span><span class="sxs-lookup"><span data-stu-id="839dc-114">'T</span></span>

<span data-ttu-id="839dc-115">Tipo di `array` elementi.</span><span class="sxs-lookup"><span data-stu-id="839dc-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="839dc-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="839dc-116">Remarks</span></span>

<span data-ttu-id="839dc-117">La funzione è definita per i tipi generici, ad esempio ogni volta che sono presenti una matrice `'T[]` e un predicato, è `'T -> Bool` possibile filtrare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="839dc-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>