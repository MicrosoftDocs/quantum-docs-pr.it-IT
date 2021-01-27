---
uid: Microsoft.Quantum.Arrays.Any
title: Qualsiasi funzione
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Any
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.
ms.openlocfilehash: a05f9531168bf2b32977665d38cc00f3c8e64879
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846272"
---
# <a name="any-function"></a><span data-ttu-id="71246-102">Qualsiasi funzione</span><span class="sxs-lookup"><span data-stu-id="71246-102">Any function</span></span>

<span data-ttu-id="71246-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="71246-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="71246-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="71246-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="71246-105">Data una matrice e un predicato definito per gli elementi della matrice, verifica se almeno un elemento della matrice soddisfa il predicato.</span><span class="sxs-lookup"><span data-stu-id="71246-105">Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.</span></span>

```qsharp
function Any<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="71246-106">Input</span><span class="sxs-lookup"><span data-stu-id="71246-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="71246-107">predicato:' t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="71246-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="71246-108">Funzione da `'T` a `Bool` utilizzata per controllare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="71246-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="71246-109">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="71246-109">array : 'T[]</span></span>

<span data-ttu-id="71246-110">Matrice di elementi su `'T` .</span><span class="sxs-lookup"><span data-stu-id="71246-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="71246-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="71246-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="71246-112">`Bool`Valore della funzione o del predicato applicato a tutti gli elementi.</span><span class="sxs-lookup"><span data-stu-id="71246-112">A `Bool` value of the OR function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="71246-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="71246-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="71246-114">T</span><span class="sxs-lookup"><span data-stu-id="71246-114">'T</span></span>

<span data-ttu-id="71246-115">Tipo di `array` elementi.</span><span class="sxs-lookup"><span data-stu-id="71246-115">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="71246-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="71246-116">Example</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function IsThreePresent() : Bool {
    let arrayOfInts = [1, 2, 3, 4, 5];
    let is3Present = IsNumberPresentInArray(3, arrayOfInts);
    return is3Present;
}

function IsNumberPresentInArray(n : Int, array : Int[]) : Bool {
    return Any(EqualI(_, n), array);
}
```

## <a name="remarks"></a><span data-ttu-id="71246-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="71246-117">Remarks</span></span>

<span data-ttu-id="71246-118">La funzione è definita per i tipi generici, ad esempio, ogni volta che si dispone di una matrice `'T[]` e di una funzione, è `predicate: 'T -> Bool` possibile produrre un `Bool` valore che indica se alcuni elementi soddisfano `predicate` .</span><span class="sxs-lookup"><span data-stu-id="71246-118">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if some element satisfies `predicate`.</span></span>