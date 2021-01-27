---
uid: Microsoft.Quantum.Arrays.Filtered
title: Funzione filtrata
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Filtered
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 83336b7001ce1d8ab1f5340b194abdcf93588c31
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847153"
---
# <a name="filtered-function"></a><span data-ttu-id="ac011-102">Funzione filtrata</span><span class="sxs-lookup"><span data-stu-id="ac011-102">Filtered function</span></span>

<span data-ttu-id="ac011-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ac011-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ac011-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ac011-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ac011-105">Data una matrice e un predicato definito per gli elementi della matrice, restituisce una matrice costituita dagli elementi che soddisfano il predicato.</span><span class="sxs-lookup"><span data-stu-id="ac011-105">Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Filtered<'T> (predicate : ('T -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="ac011-106">Input</span><span class="sxs-lookup"><span data-stu-id="ac011-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="ac011-107">predicato:' t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ac011-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ac011-108">Funzione da `'T` a booleana utilizzata per filtrare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="ac011-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="ac011-109">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="ac011-109">array : 'T[]</span></span>

<span data-ttu-id="ac011-110">Matrice di elementi su `'T` .</span><span class="sxs-lookup"><span data-stu-id="ac011-110">An array of elements over `'T`.</span></span>



## <a name="output--t"></a><span data-ttu-id="ac011-111">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="ac011-111">Output : 'T[]</span></span>

<span data-ttu-id="ac011-112">Matrice `'T[]` di elementi che soddisfano il predicato.</span><span class="sxs-lookup"><span data-stu-id="ac011-112">An array `'T[]` of elements that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ac011-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="ac011-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ac011-114">T</span><span class="sxs-lookup"><span data-stu-id="ac011-114">'T</span></span>

<span data-ttu-id="ac011-115">Tipo di `array` elementi.</span><span class="sxs-lookup"><span data-stu-id="ac011-115">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="ac011-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="ac011-116">Example</span></span>

<span data-ttu-id="ac011-117">Nel codice seguente viene illustrata la funzione "filtrata".</span><span class="sxs-lookup"><span data-stu-id="ac011-117">The following code demonstrates the "Filtered" function.</span></span>
<span data-ttu-id="ac011-118">Un predicato viene definito utilizzando la @"microsoft.quantum.logical.greaterthani" funzione:</span><span class="sxs-lookup"><span data-stu-id="ac011-118">A predicate is defined using the @"microsoft.quantum.logical.greaterthani" function:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function FilteredDemo() : Unit {
   let predicate = GreaterThanI(_, 5);
   let filteredArray = Filtered(predicate, [2, 5, 9, 1, 8]);
   Message($"{filteredArray}");
}
```

<span data-ttu-id="ac011-119">Il risultato previsto da questo esempio sarà una matrice di numeri maggiori di 5.</span><span class="sxs-lookup"><span data-stu-id="ac011-119">The outcome one should expect from this example will be an array of numbers greater than 5.</span></span>

## <a name="remarks"></a><span data-ttu-id="ac011-120">Commenti</span><span class="sxs-lookup"><span data-stu-id="ac011-120">Remarks</span></span>

<span data-ttu-id="ac011-121">La funzione è definita per i tipi generici, ad esempio ogni volta che sono presenti una matrice `'T[]` e un predicato, è `'T -> Bool` possibile filtrare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="ac011-121">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>