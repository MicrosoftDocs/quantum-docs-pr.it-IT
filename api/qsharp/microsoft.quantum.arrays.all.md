---
uid: Microsoft.Quantum.Arrays.All
title: All (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: All
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.
ms.openlocfilehash: 345c3fb92babd4ae2e54803b6c3b79b3313ef417
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719478"
---
# <a name="all-function"></a><span data-ttu-id="c3506-102">All (funzione)</span><span class="sxs-lookup"><span data-stu-id="c3506-102">All function</span></span>

<span data-ttu-id="c3506-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c3506-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c3506-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c3506-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c3506-105">Data una matrice e un predicato definito per gli elementi della matrice e controlla se tutti gli elementi della matrice soddisfano il predicato.</span><span class="sxs-lookup"><span data-stu-id="c3506-105">Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.</span></span>

```qsharp
function All<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="c3506-106">Input</span><span class="sxs-lookup"><span data-stu-id="c3506-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="c3506-107">predicato:' t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c3506-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c3506-108">Funzione da `'T` a `Bool` utilizzata per controllare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="c3506-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="c3506-109">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="c3506-109">array : 'T[]</span></span>

<span data-ttu-id="c3506-110">Matrice di elementi su `'T` .</span><span class="sxs-lookup"><span data-stu-id="c3506-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c3506-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c3506-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c3506-112">`Bool`Valore della funzione e del predicato applicato a tutti gli elementi.</span><span class="sxs-lookup"><span data-stu-id="c3506-112">A `Bool` value of the AND function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c3506-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="c3506-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c3506-114">T</span><span class="sxs-lookup"><span data-stu-id="c3506-114">'T</span></span>

<span data-ttu-id="c3506-115">Tipo di `array` elementi.</span><span class="sxs-lookup"><span data-stu-id="c3506-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="c3506-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="c3506-116">Remarks</span></span>

<span data-ttu-id="c3506-117">La funzione è definita per i tipi generici, ad esempio, ogni volta che si dispone di una matrice `'T[]` e di una funzione, è `predicate: 'T -> Bool` possibile produrre un `Bool` valore che indica se tutti gli elementi soddisfano `predicate` .</span><span class="sxs-lookup"><span data-stu-id="c3506-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if all elements satisfy `predicate`.</span></span>