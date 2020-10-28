---
uid: Microsoft.Quantum.Arrays.Zipped4
title: Zipped4 (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped4
qsharp.summary: Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.
ms.openlocfilehash: 413b415288170b4a6bffbb773e3277cdb47bdbbe
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718683"
---
# <a name="zipped4-function"></a><span data-ttu-id="8b3b9-102">Zipped4 (funzione)</span><span class="sxs-lookup"><span data-stu-id="8b3b9-102">Zipped4 function</span></span>

<span data-ttu-id="8b3b9-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="8b3b9-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="8b3b9-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8b3b9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8b3b9-105">Date quattro matrici, restituisce una nuova matrice di 4 tuple in modo che ogni tupla a 4 elementi contenga un elemento da ogni matrice originale.</span><span class="sxs-lookup"><span data-stu-id="8b3b9-105">Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.</span></span>

```qsharp
function Zipped4<'T1, 'T2, 'T3, 'T4> (first : 'T1[], second : 'T2[], third : 'T3[], fourth : 'T4[]) : ('T1, 'T2, 'T3, 'T4)[]
```


## <a name="input"></a><span data-ttu-id="8b3b9-106">Input</span><span class="sxs-lookup"><span data-stu-id="8b3b9-106">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="8b3b9-107">primo:' t 1 []</span><span class="sxs-lookup"><span data-stu-id="8b3b9-107">first : 'T1[]</span></span>

<span data-ttu-id="8b3b9-108">Matrice contenente i valori per il primo elemento di ogni tupla.</span><span class="sxs-lookup"><span data-stu-id="8b3b9-108">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="8b3b9-109">secondo:' t 2 []</span><span class="sxs-lookup"><span data-stu-id="8b3b9-109">second : 'T2[]</span></span>

<span data-ttu-id="8b3b9-110">Matrice contenente i valori per il secondo elemento di ogni tupla.</span><span class="sxs-lookup"><span data-stu-id="8b3b9-110">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="8b3b9-111">terzo:' t 3 []</span><span class="sxs-lookup"><span data-stu-id="8b3b9-111">third : 'T3[]</span></span>

<span data-ttu-id="8b3b9-112">Matrice contenente i valori per il terzo elemento di ogni tupla.</span><span class="sxs-lookup"><span data-stu-id="8b3b9-112">An array containing values for the third element of each tuple.</span></span>


### <a name="fourth--t4"></a><span data-ttu-id="8b3b9-113">quarto:' t 4 []</span><span class="sxs-lookup"><span data-stu-id="8b3b9-113">fourth : 'T4[]</span></span>

<span data-ttu-id="8b3b9-114">Matrice contenente i valori per il quarto elemento di ogni tupla.</span><span class="sxs-lookup"><span data-stu-id="8b3b9-114">An array containing values for the fourth element of each tuple.</span></span>



## <a name="output--t1t2t3t4"></a><span data-ttu-id="8b3b9-115">Output: (' t 1,' t 2,' t 3,' t 4) []</span><span class="sxs-lookup"><span data-stu-id="8b3b9-115">Output : ('T1,'T2,'T3,'T4)[]</span></span>

<span data-ttu-id="8b3b9-116">Matrice contenente 4 tuple del form `(first[idx], second[idx], third[idx], fourth[idx])` per ciascuna `idx` .</span><span class="sxs-lookup"><span data-stu-id="8b3b9-116">An array containing 4-tuples of the form `(first[idx], second[idx], third[idx], fourth[idx])` for each `idx`.</span></span> <span data-ttu-id="8b3b9-117">Se le quattro matrici non sono di uguale lunghezza, l'output sarà purché il più breve degli input.</span><span class="sxs-lookup"><span data-stu-id="8b3b9-117">If the four arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8b3b9-118">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="8b3b9-118">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="8b3b9-119">' T 1</span><span class="sxs-lookup"><span data-stu-id="8b3b9-119">'T1</span></span>

<span data-ttu-id="8b3b9-120">Tipo dei primi elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="8b3b9-120">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="8b3b9-121">T 2</span><span class="sxs-lookup"><span data-stu-id="8b3b9-121">'T2</span></span>

<span data-ttu-id="8b3b9-122">Tipo di secondi elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="8b3b9-122">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="8b3b9-123">' T 3</span><span class="sxs-lookup"><span data-stu-id="8b3b9-123">'T3</span></span>

<span data-ttu-id="8b3b9-124">Tipo dei tre elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="8b3b9-124">The type of the third array elements.</span></span>
### <a name="t4"></a><span data-ttu-id="8b3b9-125">' T 4</span><span class="sxs-lookup"><span data-stu-id="8b3b9-125">'T4</span></span>

<span data-ttu-id="8b3b9-126">Tipo dei quarti elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="8b3b9-126">The type of the fourth array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="8b3b9-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8b3b9-127">See Also</span></span>

- [<span data-ttu-id="8b3b9-128">Microsoft.Quantum.Arrays.ZipPED</span><span class="sxs-lookup"><span data-stu-id="8b3b9-128">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)
- [<span data-ttu-id="8b3b9-129">Microsoft.Quantum.Arrays.ZipPED3</span><span class="sxs-lookup"><span data-stu-id="8b3b9-129">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)