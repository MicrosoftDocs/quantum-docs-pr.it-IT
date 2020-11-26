---
uid: Microsoft.Quantum.Arrays.Zipped
title: Funzione compressa
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 56ed97d573bf29dddb7cdb1c3f360218bf97889a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219754"
---
# <a name="zipped-function"></a><span data-ttu-id="34ea8-102">Funzione compressa</span><span class="sxs-lookup"><span data-stu-id="34ea8-102">Zipped function</span></span>

<span data-ttu-id="34ea8-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="34ea8-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="34ea8-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="34ea8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="34ea8-105">Date due matrici, restituisce una nuova matrice di coppie in modo che ogni coppia contenga un elemento da ogni matrice originale.</span><span class="sxs-lookup"><span data-stu-id="34ea8-105">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zipped<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="34ea8-106">Input</span><span class="sxs-lookup"><span data-stu-id="34ea8-106">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="34ea8-107">Left:' t []</span><span class="sxs-lookup"><span data-stu-id="34ea8-107">left : 'T[]</span></span>

<span data-ttu-id="34ea8-108">Matrice contenente i valori per il primo elemento di ogni tupla.</span><span class="sxs-lookup"><span data-stu-id="34ea8-108">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="34ea8-109">Right:' U []</span><span class="sxs-lookup"><span data-stu-id="34ea8-109">right : 'U[]</span></span>

<span data-ttu-id="34ea8-110">Matrice contenente i valori per il secondo elemento di ogni tupla.</span><span class="sxs-lookup"><span data-stu-id="34ea8-110">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="34ea8-111">Output: (t,' U) []</span><span class="sxs-lookup"><span data-stu-id="34ea8-111">Output : ('T,'U)[]</span></span>

<span data-ttu-id="34ea8-112">Matrice contenente le coppie del form `(left[idx], right[idx])` per ciascuna `idx` .</span><span class="sxs-lookup"><span data-stu-id="34ea8-112">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="34ea8-113">Se le due matrici non sono di uguale lunghezza, l'output sarà purché il più breve degli input.</span><span class="sxs-lookup"><span data-stu-id="34ea8-113">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="34ea8-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="34ea8-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="34ea8-115">T</span><span class="sxs-lookup"><span data-stu-id="34ea8-115">'T</span></span>

<span data-ttu-id="34ea8-116">Tipo degli elementi della matrice di sinistra.</span><span class="sxs-lookup"><span data-stu-id="34ea8-116">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="34ea8-117">' U</span><span class="sxs-lookup"><span data-stu-id="34ea8-117">'U</span></span>

<span data-ttu-id="34ea8-118">Tipo degli elementi della matrice corretti.</span><span class="sxs-lookup"><span data-stu-id="34ea8-118">The type of the right array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="34ea8-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34ea8-119">See Also</span></span>

- [<span data-ttu-id="34ea8-120">Microsoft.Quantum.Arrays.ZipPED3</span><span class="sxs-lookup"><span data-stu-id="34ea8-120">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)
- [<span data-ttu-id="34ea8-121">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="34ea8-121">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)
- [<span data-ttu-id="34ea8-122">Microsoft. Quantum. Arrays. decompresso</span><span class="sxs-lookup"><span data-stu-id="34ea8-122">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)