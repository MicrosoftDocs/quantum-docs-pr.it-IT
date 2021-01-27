---
uid: Microsoft.Quantum.Arrays.Zip4
title: Zip4 (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip4
qsharp.summary: >-
  > [!WARNING]

  > Zip4 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped4> instead.


  Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.
ms.openlocfilehash: 534721e6544a31f6f5d27db0c077e9d8c574aecd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850890"
---
# <a name="zip4-function"></a><span data-ttu-id="f4a7e-102">Zip4 (funzione)</span><span class="sxs-lookup"><span data-stu-id="f4a7e-102">Zip4 function</span></span>

<span data-ttu-id="f4a7e-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f4a7e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f4a7e-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f4a7e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="f4a7e-105">Zip4 è stato deprecato.</span><span class="sxs-lookup"><span data-stu-id="f4a7e-105">Zip4 has been deprecated.</span></span> <span data-ttu-id="f4a7e-106">Usare invece <xref:Microsoft.Quantum.Arrays.Zipped4>.</span><span class="sxs-lookup"><span data-stu-id="f4a7e-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped4> instead.</span></span>

<span data-ttu-id="f4a7e-107">Date quattro matrici, restituisce una nuova matrice di 4 tuple in modo che ogni tupla a 4 elementi contenga un elemento da ogni matrice originale.</span><span class="sxs-lookup"><span data-stu-id="f4a7e-107">Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.</span></span>

```qsharp
function Zip4<'T1, 'T2, 'T3, 'T4> (first : 'T1[], second : 'T2[], third : 'T3[], fourth : 'T4[]) : ('T1, 'T2, 'T3, 'T4)[]
```


## <a name="input"></a><span data-ttu-id="f4a7e-108">Input</span><span class="sxs-lookup"><span data-stu-id="f4a7e-108">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="f4a7e-109">primo:' t 1 []</span><span class="sxs-lookup"><span data-stu-id="f4a7e-109">first : 'T1[]</span></span>

<span data-ttu-id="f4a7e-110">Matrice contenente i valori per il primo elemento di ogni tupla.</span><span class="sxs-lookup"><span data-stu-id="f4a7e-110">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="f4a7e-111">secondo:' t 2 []</span><span class="sxs-lookup"><span data-stu-id="f4a7e-111">second : 'T2[]</span></span>

<span data-ttu-id="f4a7e-112">Matrice contenente i valori per il secondo elemento di ogni tupla.</span><span class="sxs-lookup"><span data-stu-id="f4a7e-112">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="f4a7e-113">terzo:' t 3 []</span><span class="sxs-lookup"><span data-stu-id="f4a7e-113">third : 'T3[]</span></span>

<span data-ttu-id="f4a7e-114">Matrice contenente i valori per il terzo elemento di ogni tupla.</span><span class="sxs-lookup"><span data-stu-id="f4a7e-114">An array containing values for the third element of each tuple.</span></span>


### <a name="fourth--t4"></a><span data-ttu-id="f4a7e-115">quarto:' t 4 []</span><span class="sxs-lookup"><span data-stu-id="f4a7e-115">fourth : 'T4[]</span></span>

<span data-ttu-id="f4a7e-116">Matrice contenente i valori per il quarto elemento di ogni tupla.</span><span class="sxs-lookup"><span data-stu-id="f4a7e-116">An array containing values for the fourth element of each tuple.</span></span>



## <a name="output--t1t2t3t4"></a><span data-ttu-id="f4a7e-117">Output: (' t 1,' t 2,' t 3,' t 4) []</span><span class="sxs-lookup"><span data-stu-id="f4a7e-117">Output : ('T1,'T2,'T3,'T4)[]</span></span>

<span data-ttu-id="f4a7e-118">Matrice contenente 4 tuple del form `(first[idx], second[idx], third[idx], fourth[idx])` per ciascuna `idx` .</span><span class="sxs-lookup"><span data-stu-id="f4a7e-118">An array containing 4-tuples of the form `(first[idx], second[idx], third[idx], fourth[idx])` for each `idx`.</span></span> <span data-ttu-id="f4a7e-119">Se le quattro matrici non sono di uguale lunghezza, l'output sarà purché il più breve degli input.</span><span class="sxs-lookup"><span data-stu-id="f4a7e-119">If the four arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f4a7e-120">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="f4a7e-120">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="f4a7e-121">' T 1</span><span class="sxs-lookup"><span data-stu-id="f4a7e-121">'T1</span></span>

<span data-ttu-id="f4a7e-122">Tipo dei primi elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="f4a7e-122">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="f4a7e-123">T 2</span><span class="sxs-lookup"><span data-stu-id="f4a7e-123">'T2</span></span>

<span data-ttu-id="f4a7e-124">Tipo di secondi elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="f4a7e-124">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="f4a7e-125">' T 3</span><span class="sxs-lookup"><span data-stu-id="f4a7e-125">'T3</span></span>

<span data-ttu-id="f4a7e-126">Tipo dei tre elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="f4a7e-126">The type of the third array elements.</span></span>
### <a name="t4"></a><span data-ttu-id="f4a7e-127">' T 4</span><span class="sxs-lookup"><span data-stu-id="f4a7e-127">'T4</span></span>

<span data-ttu-id="f4a7e-128">Tipo dei quarti elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="f4a7e-128">The type of the fourth array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="f4a7e-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4a7e-129">See Also</span></span>

- [<span data-ttu-id="f4a7e-130">Microsoft.Quantum.Arrays.Zip</span><span class="sxs-lookup"><span data-stu-id="f4a7e-130">Microsoft.Quantum.Arrays.Zip</span></span>](xref:Microsoft.Quantum.Arrays.Zip)
- [<span data-ttu-id="f4a7e-131">Microsoft.Quantum.Arrays.Zip3</span><span class="sxs-lookup"><span data-stu-id="f4a7e-131">Microsoft.Quantum.Arrays.Zip3</span></span>](xref:Microsoft.Quantum.Arrays.Zip3)