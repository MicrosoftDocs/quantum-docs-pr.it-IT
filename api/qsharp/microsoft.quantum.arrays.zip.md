---
uid: Microsoft.Quantum.Arrays.Zip
title: Funzione zip
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip
qsharp.summary: >-
  > [!WARNING]

  > Zip has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.


  Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 44db8d38d96babd16ead5ae6dde91da23bdee2c9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219856"
---
# <a name="zip-function"></a><span data-ttu-id="4284c-102">Funzione zip</span><span class="sxs-lookup"><span data-stu-id="4284c-102">Zip function</span></span>

<span data-ttu-id="4284c-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="4284c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="4284c-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4284c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="4284c-105">Il file zip è stato deprecato.</span><span class="sxs-lookup"><span data-stu-id="4284c-105">Zip has been deprecated.</span></span> <span data-ttu-id="4284c-106">Usare invece <xref:Microsoft.Quantum.Arrays.Zipped>.</span><span class="sxs-lookup"><span data-stu-id="4284c-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.</span></span>

<span data-ttu-id="4284c-107">Date due matrici, restituisce una nuova matrice di coppie in modo che ogni coppia contenga un elemento da ogni matrice originale.</span><span class="sxs-lookup"><span data-stu-id="4284c-107">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zip<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="4284c-108">Input</span><span class="sxs-lookup"><span data-stu-id="4284c-108">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="4284c-109">Left:' t []</span><span class="sxs-lookup"><span data-stu-id="4284c-109">left : 'T[]</span></span>

<span data-ttu-id="4284c-110">Matrice contenente i valori per il primo elemento di ogni tupla.</span><span class="sxs-lookup"><span data-stu-id="4284c-110">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="4284c-111">Right:' U []</span><span class="sxs-lookup"><span data-stu-id="4284c-111">right : 'U[]</span></span>

<span data-ttu-id="4284c-112">Matrice contenente i valori per il secondo elemento di ogni tupla.</span><span class="sxs-lookup"><span data-stu-id="4284c-112">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="4284c-113">Output: (t,' U) []</span><span class="sxs-lookup"><span data-stu-id="4284c-113">Output : ('T,'U)[]</span></span>

<span data-ttu-id="4284c-114">Matrice contenente le coppie del form `(left[idx], right[idx])` per ciascuna `idx` .</span><span class="sxs-lookup"><span data-stu-id="4284c-114">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="4284c-115">Se le due matrici non sono di uguale lunghezza, l'output sarà purché il più breve degli input.</span><span class="sxs-lookup"><span data-stu-id="4284c-115">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4284c-116">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="4284c-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4284c-117">T</span><span class="sxs-lookup"><span data-stu-id="4284c-117">'T</span></span>

<span data-ttu-id="4284c-118">Tipo degli elementi della matrice di sinistra.</span><span class="sxs-lookup"><span data-stu-id="4284c-118">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="4284c-119">' U</span><span class="sxs-lookup"><span data-stu-id="4284c-119">'U</span></span>

<span data-ttu-id="4284c-120">Tipo degli elementi della matrice corretti.</span><span class="sxs-lookup"><span data-stu-id="4284c-120">The type of the right array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="4284c-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4284c-121">See Also</span></span>

- [<span data-ttu-id="4284c-122">Microsoft.Quantum.Arrays.Zip3</span><span class="sxs-lookup"><span data-stu-id="4284c-122">Microsoft.Quantum.Arrays.Zip3</span></span>](xref:Microsoft.Quantum.Arrays.Zip3)
- [<span data-ttu-id="4284c-123">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="4284c-123">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)
- [<span data-ttu-id="4284c-124">Microsoft. Quantum. Arrays. decompresso</span><span class="sxs-lookup"><span data-stu-id="4284c-124">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)