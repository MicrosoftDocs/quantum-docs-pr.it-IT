---
uid: Microsoft.Quantum.Arrays.IsSorted
title: Funzione sorted
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsSorted
qsharp.summary: Given an array, returns whether that array is sorted as defined by a given comparison function.
ms.openlocfilehash: a5916b5cbf36e1b6c421a81e04016a333e2b5be7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845728"
---
# <a name="issorted-function"></a><span data-ttu-id="32c94-102">Funzione sorted</span><span class="sxs-lookup"><span data-stu-id="32c94-102">IsSorted function</span></span>

<span data-ttu-id="32c94-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="32c94-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="32c94-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="32c94-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="32c94-105">Data una matrice, restituisce un valore che indica se la matrice è ordinata in base a quanto definito da una funzione di confronto specificata.</span><span class="sxs-lookup"><span data-stu-id="32c94-105">Given an array, returns whether that array is sorted as defined by a given comparison function.</span></span>

```qsharp
function IsSorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="32c94-106">Input</span><span class="sxs-lookup"><span data-stu-id="32c94-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="32c94-107">confronto: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="32c94-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="32c94-108">Funzione che confronta due elementi, che `a` sono considerati minori o uguali a `b` se `comparison(a, b)` è `true` .</span><span class="sxs-lookup"><span data-stu-id="32c94-108">A function that compares two elements such that `a` is considered to be less than or equal to `b` if `comparison(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="32c94-109">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="32c94-109">array : 'T[]</span></span>

<span data-ttu-id="32c94-110">Matrice da verificare.</span><span class="sxs-lookup"><span data-stu-id="32c94-110">The array to be checked.</span></span>



## <a name="output--bool"></a><span data-ttu-id="32c94-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="32c94-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="32c94-112">`true` Se e solo se per ogni coppia di elementi `a` e `b` di `array` si verifica in questo ordine, `comparison(a, b)` è `true` .</span><span class="sxs-lookup"><span data-stu-id="32c94-112">`true` if and only if for each pair of elements `a` and `b` of `array` occuring in that order, `comparison(a, b)` is `true`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="32c94-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="32c94-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="32c94-114">T</span><span class="sxs-lookup"><span data-stu-id="32c94-114">'T</span></span>

<span data-ttu-id="32c94-115">Tipo di ogni elemento di `array` .</span><span class="sxs-lookup"><span data-stu-id="32c94-115">The type of each element of `array`.</span></span>

## <a name="remarks"></a><span data-ttu-id="32c94-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="32c94-116">Remarks</span></span>

<span data-ttu-id="32c94-117">`comparison`Si presuppone che la funzione sia transitiva, in modo che `comparison(a, b)` , se e `comparison(b, c)` , `comparison(a, c)` si presuppone.</span><span class="sxs-lookup"><span data-stu-id="32c94-117">The function `comparison` is assumed to be transitive, such that if `comparison(a, b)` and `comparison(b, c)`, then `comparison(a, c)` is assumed.</span></span> <span data-ttu-id="32c94-118">Se questa proprietà non viene mantenuta, l'output di questa funzione potrebbe non essere corretto.</span><span class="sxs-lookup"><span data-stu-id="32c94-118">If this property does not hold, then the output of this function may be incorrect.</span></span>