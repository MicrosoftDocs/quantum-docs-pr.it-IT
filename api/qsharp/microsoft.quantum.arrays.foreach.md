---
uid: Microsoft.Quantum.Arrays.ForEach
title: Operazione ForEach
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ForEach
qsharp.summary: Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.
ms.openlocfilehash: ab6ac6eb913095f31ba166ac27f034f2e2875acf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719202"
---
# <a name="foreach-operation"></a><span data-ttu-id="70934-102">Operazione ForEach</span><span class="sxs-lookup"><span data-stu-id="70934-102">ForEach operation</span></span>

<span data-ttu-id="70934-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="70934-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="70934-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="70934-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="70934-105">Data una matrice e un'operazione definita per gli elementi della matrice, restituisce una nuova matrice costituita dalle immagini della matrice originale sotto l'operazione.</span><span class="sxs-lookup"><span data-stu-id="70934-105">Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.</span></span>

```qsharp
operation ForEach<'T, 'U> (action : ('T => 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="70934-106">Input</span><span class="sxs-lookup"><span data-stu-id="70934-106">Input</span></span>

### <a name="action--t--u"></a><span data-ttu-id="70934-107">azione:' t =>' U</span><span class="sxs-lookup"><span data-stu-id="70934-107">action : 'T => 'U</span></span> 

<span data-ttu-id="70934-108">Operazione da `'T` a `'U` applicata a ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="70934-108">An operation from `'T` to `'U` that is applied to each element.</span></span>


### <a name="array--t"></a><span data-ttu-id="70934-109">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="70934-109">array : 'T[]</span></span>

<span data-ttu-id="70934-110">Matrice di elementi su `'T` .</span><span class="sxs-lookup"><span data-stu-id="70934-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="70934-111">Output:' U []</span><span class="sxs-lookup"><span data-stu-id="70934-111">Output : 'U[]</span></span>

<span data-ttu-id="70934-112">Matrice `'U[]` di elementi mappati dall' `action` operazione.</span><span class="sxs-lookup"><span data-stu-id="70934-112">An array `'U[]` of elements that are mapped by the `action` operation.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="70934-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="70934-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="70934-114">T</span><span class="sxs-lookup"><span data-stu-id="70934-114">'T</span></span>

<span data-ttu-id="70934-115">Tipo di `array` elementi.</span><span class="sxs-lookup"><span data-stu-id="70934-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="70934-116">' U</span><span class="sxs-lookup"><span data-stu-id="70934-116">'U</span></span>

<span data-ttu-id="70934-117">Tipo di risultato dell' `action` operazione.</span><span class="sxs-lookup"><span data-stu-id="70934-117">The result type of the `action` operation.</span></span>

## <a name="remarks"></a><span data-ttu-id="70934-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="70934-118">Remarks</span></span>

<span data-ttu-id="70934-119">L'operazione è definita per i tipi generici, ad esempio ogni volta che è presente una matrice `'T[]` e un'operazione è `action : 'T -> 'U` possibile eseguire il mapping degli elementi della matrice e produrre una nuova matrice di tipo `'U[]` .</span><span class="sxs-lookup"><span data-stu-id="70934-119">The operation is defined for generic types, i.e., whenever we have an array `'T[]` and an operation `action : 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>