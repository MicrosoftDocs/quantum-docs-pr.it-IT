---
uid: Microsoft.Quantum.Arrays.Zipped
title: Funzione compressa
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 5177ab0ade5a9ad7788e60c1028befb84b0191d4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845343"
---
# <a name="zipped-function"></a><span data-ttu-id="aa509-102">Funzione compressa</span><span class="sxs-lookup"><span data-stu-id="aa509-102">Zipped function</span></span>

<span data-ttu-id="aa509-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="aa509-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="aa509-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="aa509-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="aa509-105">Date due matrici, restituisce una nuova matrice di coppie in modo che ogni coppia contenga un elemento da ogni matrice originale.</span><span class="sxs-lookup"><span data-stu-id="aa509-105">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zipped<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="aa509-106">Input</span><span class="sxs-lookup"><span data-stu-id="aa509-106">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="aa509-107">Left:' t []</span><span class="sxs-lookup"><span data-stu-id="aa509-107">left : 'T[]</span></span>

<span data-ttu-id="aa509-108">Matrice contenente i valori per il primo elemento di ogni tupla.</span><span class="sxs-lookup"><span data-stu-id="aa509-108">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="aa509-109">Right:' U []</span><span class="sxs-lookup"><span data-stu-id="aa509-109">right : 'U[]</span></span>

<span data-ttu-id="aa509-110">Matrice contenente i valori per il secondo elemento di ogni tupla.</span><span class="sxs-lookup"><span data-stu-id="aa509-110">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="aa509-111">Output: (t,' U) []</span><span class="sxs-lookup"><span data-stu-id="aa509-111">Output : ('T,'U)[]</span></span>

<span data-ttu-id="aa509-112">Matrice contenente le coppie del form `(left[idx], right[idx])` per ciascuna `idx` .</span><span class="sxs-lookup"><span data-stu-id="aa509-112">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="aa509-113">Se le due matrici non sono di uguale lunghezza, l'output sarà purché il più breve degli input.</span><span class="sxs-lookup"><span data-stu-id="aa509-113">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="aa509-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="aa509-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="aa509-115">T</span><span class="sxs-lookup"><span data-stu-id="aa509-115">'T</span></span>

<span data-ttu-id="aa509-116">Tipo degli elementi della matrice di sinistra.</span><span class="sxs-lookup"><span data-stu-id="aa509-116">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="aa509-117">' U</span><span class="sxs-lookup"><span data-stu-id="aa509-117">'U</span></span>

<span data-ttu-id="aa509-118">Tipo degli elementi della matrice corretti.</span><span class="sxs-lookup"><span data-stu-id="aa509-118">The type of the right array elements.</span></span>

## <a name="example"></a><span data-ttu-id="aa509-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="aa509-119">Example</span></span>

```qsharp
let left = [1, 3, 71];
let right = [false, true];
let pairs = Zipped(left, right); // [(1, false), (3, true)]
```

## <a name="see-also"></a><span data-ttu-id="aa509-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa509-120">See Also</span></span>

- [<span data-ttu-id="aa509-121">Microsoft.Quantum.Arrays.ZipPED3</span><span class="sxs-lookup"><span data-stu-id="aa509-121">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)
- [<span data-ttu-id="aa509-122">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="aa509-122">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)
- [<span data-ttu-id="aa509-123">Microsoft. Quantum. Arrays. decompresso</span><span class="sxs-lookup"><span data-stu-id="aa509-123">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)