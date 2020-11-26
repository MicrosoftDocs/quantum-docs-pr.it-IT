---
uid: Microsoft.Quantum.Arrays.ForEach
title: Operazione ForEach
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ForEach
qsharp.summary: Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.
ms.openlocfilehash: b362d28e77c8dea2b3daeed4a4d605e1dd42e487
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221148"
---
# <a name="foreach-operation"></a><span data-ttu-id="cac95-102">Operazione ForEach</span><span class="sxs-lookup"><span data-stu-id="cac95-102">ForEach operation</span></span>

<span data-ttu-id="cac95-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="cac95-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="cac95-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cac95-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cac95-105">Data una matrice e un'operazione definita per gli elementi della matrice, restituisce una nuova matrice costituita dalle immagini della matrice originale sotto l'operazione.</span><span class="sxs-lookup"><span data-stu-id="cac95-105">Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.</span></span>

```qsharp
operation ForEach<'T, 'U> (action : ('T => 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="cac95-106">Input</span><span class="sxs-lookup"><span data-stu-id="cac95-106">Input</span></span>

### <a name="action--t--u"></a><span data-ttu-id="cac95-107">azione:' t =>' U</span><span class="sxs-lookup"><span data-stu-id="cac95-107">action : 'T => 'U</span></span> 

<span data-ttu-id="cac95-108">Operazione da `'T` a `'U` applicata a ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="cac95-108">An operation from `'T` to `'U` that is applied to each element.</span></span>


### <a name="array--t"></a><span data-ttu-id="cac95-109">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="cac95-109">array : 'T[]</span></span>

<span data-ttu-id="cac95-110">Matrice di elementi su `'T` .</span><span class="sxs-lookup"><span data-stu-id="cac95-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="cac95-111">Output:' U []</span><span class="sxs-lookup"><span data-stu-id="cac95-111">Output : 'U[]</span></span>

<span data-ttu-id="cac95-112">Matrice `'U[]` di elementi mappati dall' `action` operazione.</span><span class="sxs-lookup"><span data-stu-id="cac95-112">An array `'U[]` of elements that are mapped by the `action` operation.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="cac95-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="cac95-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cac95-114">T</span><span class="sxs-lookup"><span data-stu-id="cac95-114">'T</span></span>

<span data-ttu-id="cac95-115">Tipo di `array` elementi.</span><span class="sxs-lookup"><span data-stu-id="cac95-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="cac95-116">' U</span><span class="sxs-lookup"><span data-stu-id="cac95-116">'U</span></span>

<span data-ttu-id="cac95-117">Tipo di risultato dell' `action` operazione.</span><span class="sxs-lookup"><span data-stu-id="cac95-117">The result type of the `action` operation.</span></span>

## <a name="remarks"></a><span data-ttu-id="cac95-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="cac95-118">Remarks</span></span>

<span data-ttu-id="cac95-119">L'operazione è definita per i tipi generici, ad esempio ogni volta che è presente una matrice `'T[]` e un'operazione è `action : 'T -> 'U` possibile eseguire il mapping degli elementi della matrice e produrre una nuova matrice di tipo `'U[]` .</span><span class="sxs-lookup"><span data-stu-id="cac95-119">The operation is defined for generic types, i.e., whenever we have an array `'T[]` and an operation `action : 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>