---
uid: Microsoft.Quantum.Arrays.ForEach
title: Operazione ForEach
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ForEach
qsharp.summary: Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.
ms.openlocfilehash: 90dd6f94408d37d2b32d82e772a482b0e69c523f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848593"
---
# <a name="foreach-operation"></a><span data-ttu-id="d2ea7-102">Operazione ForEach</span><span class="sxs-lookup"><span data-stu-id="d2ea7-102">ForEach operation</span></span>

<span data-ttu-id="d2ea7-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d2ea7-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d2ea7-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d2ea7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d2ea7-105">Data una matrice e un'operazione definita per gli elementi della matrice, restituisce una nuova matrice costituita dalle immagini della matrice originale sotto l'operazione.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-105">Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.</span></span>

```qsharp
operation ForEach<'T, 'U> (action : ('T => 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="d2ea7-106">Input</span><span class="sxs-lookup"><span data-stu-id="d2ea7-106">Input</span></span>

### <a name="action--t--u"></a><span data-ttu-id="d2ea7-107">azione:' t =>' U</span><span class="sxs-lookup"><span data-stu-id="d2ea7-107">action : 'T => 'U</span></span> 

<span data-ttu-id="d2ea7-108">Operazione da `'T` a `'U` applicata a ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-108">An operation from `'T` to `'U` that is applied to each element.</span></span>


### <a name="array--t"></a><span data-ttu-id="d2ea7-109">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="d2ea7-109">array : 'T[]</span></span>

<span data-ttu-id="d2ea7-110">Matrice di elementi su `'T` .</span><span class="sxs-lookup"><span data-stu-id="d2ea7-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="d2ea7-111">Output:' U []</span><span class="sxs-lookup"><span data-stu-id="d2ea7-111">Output : 'U[]</span></span>

<span data-ttu-id="d2ea7-112">Matrice `'U[]` di elementi mappati dall' `action` operazione.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-112">An array `'U[]` of elements that are mapped by the `action` operation.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d2ea7-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="d2ea7-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d2ea7-114">T</span><span class="sxs-lookup"><span data-stu-id="d2ea7-114">'T</span></span>

<span data-ttu-id="d2ea7-115">Tipo di `array` elementi.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="d2ea7-116">' U</span><span class="sxs-lookup"><span data-stu-id="d2ea7-116">'U</span></span>

<span data-ttu-id="d2ea7-117">Tipo di risultato dell' `action` operazione.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-117">The result type of the `action` operation.</span></span>

## <a name="remarks"></a><span data-ttu-id="d2ea7-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="d2ea7-118">Remarks</span></span>

<span data-ttu-id="d2ea7-119">L'operazione è definita per i tipi generici, ad esempio ogni volta che è presente una matrice `'T[]` e un'operazione è `action : 'T -> 'U` possibile eseguire il mapping degli elementi della matrice e produrre una nuova matrice di tipo `'U[]` .</span><span class="sxs-lookup"><span data-stu-id="d2ea7-119">The operation is defined for generic types, i.e., whenever we have an array `'T[]` and an operation `action : 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>