---
uid: Microsoft.Quantum.Arrays.Sorted
title: Funzione ordinata
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Sorted
qsharp.summary: Given an array, returns the elements of that array sorted by a given comparison function.
ms.openlocfilehash: cb8a1ef438d798c8201ed9f52677e253770df1d3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845437"
---
# <a name="sorted-function"></a><span data-ttu-id="55fa6-102">Funzione ordinata</span><span class="sxs-lookup"><span data-stu-id="55fa6-102">Sorted function</span></span>

<span data-ttu-id="55fa6-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="55fa6-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="55fa6-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="55fa6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="55fa6-105">Data una matrice, restituisce gli elementi di tale matrice ordinati in base a una funzione di confronto specificata.</span><span class="sxs-lookup"><span data-stu-id="55fa6-105">Given an array, returns the elements of that array sorted by a given comparison function.</span></span>

```qsharp
function Sorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="55fa6-106">Input</span><span class="sxs-lookup"><span data-stu-id="55fa6-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="55fa6-107">confronto: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="55fa6-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="55fa6-108">Funzione che confronta due elementi, che `a` sono considerati minori o uguali a `b` se `comparison(a, b)` è `true` .</span><span class="sxs-lookup"><span data-stu-id="55fa6-108">A function that compares two elements such that `a` is considered to be less than or equal to `b` if `comparison(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="55fa6-109">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="55fa6-109">array : 'T[]</span></span>

<span data-ttu-id="55fa6-110">Matrice da ordinare.</span><span class="sxs-lookup"><span data-stu-id="55fa6-110">The array to be sorted.</span></span>



## <a name="output--t"></a><span data-ttu-id="55fa6-111">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="55fa6-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="55fa6-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="55fa6-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="55fa6-113">T</span><span class="sxs-lookup"><span data-stu-id="55fa6-113">'T</span></span>

<span data-ttu-id="55fa6-114">Tipo di ogni elemento di `array` .</span><span class="sxs-lookup"><span data-stu-id="55fa6-114">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="55fa6-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="55fa6-115">Example</span></span>

<span data-ttu-id="55fa6-116">Il frammento di codice seguente ordina una matrice di numeri interi che si verificano in ordine crescente:</span><span class="sxs-lookup"><span data-stu-id="55fa6-116">The following snippet sorts an array of integers to occur in ascending order:</span></span>

```qsharp
let sortedArray = Sorted(LessThanOrEqualI, [3, 17, 11, -201, -11]);
```

## <a name="remarks"></a><span data-ttu-id="55fa6-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="55fa6-117">Remarks</span></span>

<span data-ttu-id="55fa6-118">`comparison`Si presuppone che la funzione sia transitiva, in modo che `comparison(a, b)` , se e `comparison(b, c)` , `comparison(a, c)` si presuppone.</span><span class="sxs-lookup"><span data-stu-id="55fa6-118">The function `comparison` is assumed to be transitive, such that if `comparison(a, b)` and `comparison(b, c)`, then `comparison(a, c)` is assumed.</span></span> <span data-ttu-id="55fa6-119">Se questa proprietà non viene mantenuta, l'output di questa funzione potrebbe non essere corretto.</span><span class="sxs-lookup"><span data-stu-id="55fa6-119">If this property does not hold, then the output of this function may be incorrect.</span></span>

<span data-ttu-id="55fa6-120">Poiché si tratta di una funzione, i risultati sono completamente determinstic, anche quando due elementi sono considerati uguali in, `comparison` ovvero quando `comparison(a, b)` e `comparison(b, a)` sono entrambi `true` .</span><span class="sxs-lookup"><span data-stu-id="55fa6-120">As this is a function, the results are completely determinstic, even when two elements are considered equal under `comparison`; that is, when `comparison(a, b)` and `comparison(b, a)` are both `true`.</span></span>
<span data-ttu-id="55fa6-121">In particolare, l'ordinamento eseguito da questa funzione è sicuramente stabile, in modo che se due elementi `a` e `b` si verificano in tale ordine all'interno di `array` e sono considerati uguali in `comparison` , viene `a` visualizzato anche prima `b` nell'output.</span><span class="sxs-lookup"><span data-stu-id="55fa6-121">In particular, the sort performed by this function is guaranteed to be stable, so that if two elements `a` and `b` occur in that order within `array` and are considered equal under `comparison`, then `a` will also appear before `b` in the output.</span></span>

<span data-ttu-id="55fa6-122">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="55fa6-122">For example:</span></span>

```qsharp
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