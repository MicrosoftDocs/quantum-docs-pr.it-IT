---
uid: Microsoft.Quantum.Arrays.Any
title: Qualsiasi funzione
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Any
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.
ms.openlocfilehash: dd5639f1b0a76cb356c89aca0c0e02d375f30d12
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719475"
---
# <a name="any-function"></a><span data-ttu-id="0a2d0-102">Qualsiasi funzione</span><span class="sxs-lookup"><span data-stu-id="0a2d0-102">Any function</span></span>

<span data-ttu-id="0a2d0-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="0a2d0-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="0a2d0-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0a2d0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0a2d0-105">Data una matrice e un predicato definito per gli elementi della matrice, verifica se almeno un elemento della matrice soddisfa il predicato.</span><span class="sxs-lookup"><span data-stu-id="0a2d0-105">Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.</span></span>

```qsharp
function Any<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="0a2d0-106">Input</span><span class="sxs-lookup"><span data-stu-id="0a2d0-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="0a2d0-107">predicato:' t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="0a2d0-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0a2d0-108">Funzione da `'T` a `Bool` utilizzata per controllare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="0a2d0-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="0a2d0-109">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="0a2d0-109">array : 'T[]</span></span>

<span data-ttu-id="0a2d0-110">Matrice di elementi su `'T` .</span><span class="sxs-lookup"><span data-stu-id="0a2d0-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="0a2d0-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="0a2d0-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0a2d0-112">`Bool`Valore della funzione o del predicato applicato a tutti gli elementi.</span><span class="sxs-lookup"><span data-stu-id="0a2d0-112">A `Bool` value of the OR function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0a2d0-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="0a2d0-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0a2d0-114">T</span><span class="sxs-lookup"><span data-stu-id="0a2d0-114">'T</span></span>

<span data-ttu-id="0a2d0-115">Tipo di `array` elementi.</span><span class="sxs-lookup"><span data-stu-id="0a2d0-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="0a2d0-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="0a2d0-116">Remarks</span></span>

<span data-ttu-id="0a2d0-117">La funzione è definita per i tipi generici, ad esempio, ogni volta che si dispone di una matrice `'T[]` e di una funzione, è `predicate: 'T -> Bool` possibile produrre un `Bool` valore che indica se alcuni elementi soddisfano `predicate` .</span><span class="sxs-lookup"><span data-stu-id="0a2d0-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if some element satisfies `predicate`.</span></span>