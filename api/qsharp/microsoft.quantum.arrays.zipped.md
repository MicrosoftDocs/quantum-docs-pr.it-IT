---
uid: Microsoft.Quantum.Arrays.Zipped
title: Funzione compressa
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 67170fa005675f0e5d788c9c3b350fb9a961a597
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718710"
---
# <a name="zipped-function"></a><span data-ttu-id="41097-102">Funzione compressa</span><span class="sxs-lookup"><span data-stu-id="41097-102">Zipped function</span></span>

<span data-ttu-id="41097-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="41097-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="41097-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="41097-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="41097-105">Date due matrici, restituisce una nuova matrice di coppie in modo che ogni coppia contenga un elemento da ogni matrice originale.</span><span class="sxs-lookup"><span data-stu-id="41097-105">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zipped<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="41097-106">Input</span><span class="sxs-lookup"><span data-stu-id="41097-106">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="41097-107">Left:' t []</span><span class="sxs-lookup"><span data-stu-id="41097-107">left : 'T[]</span></span>

<span data-ttu-id="41097-108">Matrice contenente i valori per il primo elemento di ogni tupla.</span><span class="sxs-lookup"><span data-stu-id="41097-108">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="41097-109">Right:' U []</span><span class="sxs-lookup"><span data-stu-id="41097-109">right : 'U[]</span></span>

<span data-ttu-id="41097-110">Matrice contenente i valori per il secondo elemento di ogni tupla.</span><span class="sxs-lookup"><span data-stu-id="41097-110">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="41097-111">Output: (t,' U) []</span><span class="sxs-lookup"><span data-stu-id="41097-111">Output : ('T,'U)[]</span></span>

<span data-ttu-id="41097-112">Matrice contenente le coppie del form `(left[idx], right[idx])` per ciascuna `idx` .</span><span class="sxs-lookup"><span data-stu-id="41097-112">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="41097-113">Se le due matrici non sono di uguale lunghezza, l'output sarà purché il più breve degli input.</span><span class="sxs-lookup"><span data-stu-id="41097-113">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="41097-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="41097-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="41097-115">T</span><span class="sxs-lookup"><span data-stu-id="41097-115">'T</span></span>

<span data-ttu-id="41097-116">Tipo degli elementi della matrice di sinistra.</span><span class="sxs-lookup"><span data-stu-id="41097-116">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="41097-117">' U</span><span class="sxs-lookup"><span data-stu-id="41097-117">'U</span></span>

<span data-ttu-id="41097-118">Tipo degli elementi della matrice corretti.</span><span class="sxs-lookup"><span data-stu-id="41097-118">The type of the right array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="41097-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41097-119">See Also</span></span>

- [<span data-ttu-id="41097-120">Microsoft.Quantum.Arrays.ZipPED3</span><span class="sxs-lookup"><span data-stu-id="41097-120">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)
- [<span data-ttu-id="41097-121">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="41097-121">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)
- [<span data-ttu-id="41097-122">Microsoft. Quantum. Arrays. decompresso</span><span class="sxs-lookup"><span data-stu-id="41097-122">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)