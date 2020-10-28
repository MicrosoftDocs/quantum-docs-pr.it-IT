---
uid: Microsoft.Quantum.Arrays.Zip3
title: Zip3 (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip3
qsharp.summary: >-
  > [!WARNING]

  > Zip3 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.


  Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: f4b1a769614ee9434b2141b8fcb91f34cd071bdb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718722"
---
# <a name="zip3-function"></a><span data-ttu-id="e394d-102">Zip3 (funzione)</span><span class="sxs-lookup"><span data-stu-id="e394d-102">Zip3 function</span></span>

<span data-ttu-id="e394d-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e394d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e394d-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e394d-104">Package: [](https://nuget.org/packages/)</span></span>


> [!WARNING]
> <span data-ttu-id="e394d-105">Zip3 è stato deprecato.</span><span class="sxs-lookup"><span data-stu-id="e394d-105">Zip3 has been deprecated.</span></span> <span data-ttu-id="e394d-106">Usare invece <xref:Microsoft.Quantum.Arrays.Zipped3>.</span><span class="sxs-lookup"><span data-stu-id="e394d-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.</span></span>

<span data-ttu-id="e394d-107">Date tre matrici, restituisce una nuova matrice di 3 tuple in modo che ogni tupla con 3 Tuple contenga un elemento da ogni matrice originale.</span><span class="sxs-lookup"><span data-stu-id="e394d-107">Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.</span></span>

```qsharp
function Zip3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a><span data-ttu-id="e394d-108">Input</span><span class="sxs-lookup"><span data-stu-id="e394d-108">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="e394d-109">primo:' t 1 []</span><span class="sxs-lookup"><span data-stu-id="e394d-109">first : 'T1[]</span></span>

<span data-ttu-id="e394d-110">Matrice contenente i valori per il primo elemento di ogni tupla.</span><span class="sxs-lookup"><span data-stu-id="e394d-110">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="e394d-111">secondo:' t 2 []</span><span class="sxs-lookup"><span data-stu-id="e394d-111">second : 'T2[]</span></span>

<span data-ttu-id="e394d-112">Matrice contenente i valori per il secondo elemento di ogni tupla.</span><span class="sxs-lookup"><span data-stu-id="e394d-112">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="e394d-113">terzo:' t 3 []</span><span class="sxs-lookup"><span data-stu-id="e394d-113">third : 'T3[]</span></span>

<span data-ttu-id="e394d-114">Matrice contenente i valori per il terzo elemento di ogni tupla.</span><span class="sxs-lookup"><span data-stu-id="e394d-114">An array containing values for the third element of each tuple.</span></span>



## <a name="output--t1t2t3"></a><span data-ttu-id="e394d-115">Output: (' t 1,' t 2,' t 3) []</span><span class="sxs-lookup"><span data-stu-id="e394d-115">Output : ('T1,'T2,'T3)[]</span></span>

<span data-ttu-id="e394d-116">Matrice contenente 3 tuple del form `(first[idx], second[idx], third[idx])` per ciascuna `idx` .</span><span class="sxs-lookup"><span data-stu-id="e394d-116">An array containing 3-tuples of the form `(first[idx], second[idx], third[idx])` for each `idx`.</span></span> <span data-ttu-id="e394d-117">Se le tre matrici non sono di uguale lunghezza, l'output sarà purché il più breve degli input.</span><span class="sxs-lookup"><span data-stu-id="e394d-117">If the three arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e394d-118">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="e394d-118">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="e394d-119">' T 1</span><span class="sxs-lookup"><span data-stu-id="e394d-119">'T1</span></span>

<span data-ttu-id="e394d-120">Tipo dei primi elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="e394d-120">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="e394d-121">T 2</span><span class="sxs-lookup"><span data-stu-id="e394d-121">'T2</span></span>

<span data-ttu-id="e394d-122">Tipo di secondi elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="e394d-122">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="e394d-123">' T 3</span><span class="sxs-lookup"><span data-stu-id="e394d-123">'T3</span></span>

<span data-ttu-id="e394d-124">Tipo dei tre elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="e394d-124">The type of the third array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="e394d-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e394d-125">See Also</span></span>

- [<span data-ttu-id="e394d-126">Microsoft.Quantum.Arrays.Zip</span><span class="sxs-lookup"><span data-stu-id="e394d-126">Microsoft.Quantum.Arrays.Zip</span></span>](xref:Microsoft.Quantum.Arrays.Zip)
- [<span data-ttu-id="e394d-127">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="e394d-127">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)