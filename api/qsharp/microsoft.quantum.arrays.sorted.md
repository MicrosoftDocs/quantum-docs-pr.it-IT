---
uid: Microsoft.Quantum.Arrays.Sorted
title: Funzione ordinata
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Sorted
qsharp.summary: Given an array, returns the elements of that array sorted by a given comparison function.
ms.openlocfilehash: bd8b869e03c7f4687c456a944e07a811ae0d2ce2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220230"
---
# <a name="sorted-function"></a><span data-ttu-id="d0cc7-102">Funzione ordinata</span><span class="sxs-lookup"><span data-stu-id="d0cc7-102">Sorted function</span></span>

<span data-ttu-id="d0cc7-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d0cc7-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d0cc7-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d0cc7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d0cc7-105">Data una matrice, restituisce gli elementi di tale matrice ordinati in base a una funzione di confronto specificata.</span><span class="sxs-lookup"><span data-stu-id="d0cc7-105">Given an array, returns the elements of that array sorted by a given comparison function.</span></span>

```qsharp
function Sorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="d0cc7-106">Input</span><span class="sxs-lookup"><span data-stu-id="d0cc7-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="d0cc7-107">confronto: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d0cc7-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d0cc7-108">Funzione che confronta due elementi, che `a` sono considerati minori o uguali a `b` se `comparison(a, b)` è `true` .</span><span class="sxs-lookup"><span data-stu-id="d0cc7-108">A function that compares two elements such that `a` is considered to be less than or equal to `b` if `comparison(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="d0cc7-109">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="d0cc7-109">array : 'T[]</span></span>

<span data-ttu-id="d0cc7-110">Matrice da ordinare.</span><span class="sxs-lookup"><span data-stu-id="d0cc7-110">The array to be sorted.</span></span>



## <a name="output--t"></a><span data-ttu-id="d0cc7-111">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="d0cc7-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d0cc7-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="d0cc7-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d0cc7-113">T</span><span class="sxs-lookup"><span data-stu-id="d0cc7-113">'T</span></span>

<span data-ttu-id="d0cc7-114">Tipo di ogni elemento di `array` .</span><span class="sxs-lookup"><span data-stu-id="d0cc7-114">The type of each element of `array`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d0cc7-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="d0cc7-115">Remarks</span></span>

<span data-ttu-id="d0cc7-116">`comparison`Si presuppone che la funzione sia transitiva, in modo che `comparison(a, b)` , se e `comparison(b, c)` , `comparison(a, c)` si presuppone.</span><span class="sxs-lookup"><span data-stu-id="d0cc7-116">The function `comparison` is assumed to be transitive, such that if `comparison(a, b)` and `comparison(b, c)`, then `comparison(a, c)` is assumed.</span></span> <span data-ttu-id="d0cc7-117">Se questa proprietà non viene mantenuta, l'output di questa funzione potrebbe non essere corretto.</span><span class="sxs-lookup"><span data-stu-id="d0cc7-117">If this property does not hold, then the output of this function may be incorrect.</span></span>

<span data-ttu-id="d0cc7-118">Poiché si tratta di una funzione, i risultati sono completamente determinstic, anche quando due elementi sono considerati uguali in, `comparison` ovvero quando `comparison(a, b)` e `comparison(b, a)` sono entrambi `true` .</span><span class="sxs-lookup"><span data-stu-id="d0cc7-118">As this is a function, the results are completely determinstic, even when two elements are considered equal under `comparison`; that is, when `comparison(a, b)` and `comparison(b, a)` are both `true`.</span></span>
<span data-ttu-id="d0cc7-119">In particolare, l'ordinamento eseguito da questa funzione è sicuramente stabile, in modo che se due elementi `a` e `b` si verificano in tale ordine all'interno di `array` e sono considerati uguali in `comparison` , viene `a` visualizzato anche prima `b` nell'output.</span><span class="sxs-lookup"><span data-stu-id="d0cc7-119">In particular, the sort performed by this function is guaranteed to be stable, so that if two elements `a` and `b` occur in that order within `array` and are considered equal under `comparison`, then `a` will also appear before `b` in the output.</span></span>

<span data-ttu-id="d0cc7-120">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d0cc7-120">For example:</span></span>

```Q#
function LastDigitLessThanOrEqual(left : Int, right : Int) : Bool {
    return LessThanOrEqualI(
        left % 10, right % 10
    );
}

function SortedByLastDigit() : Int[] {
    return Sorted(LastDigitLessThanOrEqual, [3, 37, 11, 17]);
}
// returns [11, 3, 37, 17].
```