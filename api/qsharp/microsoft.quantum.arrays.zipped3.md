---
uid: Microsoft.Quantum.Arrays.Zipped3
title: Zipped3 (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped3
qsharp.summary: Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: 37fda4082a46870270414649f807659fa561962b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219686"
---
# <a name="zipped3-function"></a><span data-ttu-id="f313f-102">Zipped3 (funzione)</span><span class="sxs-lookup"><span data-stu-id="f313f-102">Zipped3 function</span></span>

<span data-ttu-id="f313f-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f313f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f313f-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f313f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f313f-105">Date tre matrici, restituisce una nuova matrice di 3 tuple in modo che ogni tupla con 3 Tuple contenga un elemento da ogni matrice originale.</span><span class="sxs-lookup"><span data-stu-id="f313f-105">Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.</span></span>

```qsharp
function Zipped3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a><span data-ttu-id="f313f-106">Input</span><span class="sxs-lookup"><span data-stu-id="f313f-106">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="f313f-107">primo:' t 1 []</span><span class="sxs-lookup"><span data-stu-id="f313f-107">first : 'T1[]</span></span>

<span data-ttu-id="f313f-108">Matrice contenente i valori per il primo elemento di ogni tupla.</span><span class="sxs-lookup"><span data-stu-id="f313f-108">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="f313f-109">secondo:' t 2 []</span><span class="sxs-lookup"><span data-stu-id="f313f-109">second : 'T2[]</span></span>

<span data-ttu-id="f313f-110">Matrice contenente i valori per il secondo elemento di ogni tupla.</span><span class="sxs-lookup"><span data-stu-id="f313f-110">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="f313f-111">terzo:' t 3 []</span><span class="sxs-lookup"><span data-stu-id="f313f-111">third : 'T3[]</span></span>

<span data-ttu-id="f313f-112">Matrice contenente i valori per il terzo elemento di ogni tupla.</span><span class="sxs-lookup"><span data-stu-id="f313f-112">An array containing values for the third element of each tuple.</span></span>



## <a name="output--t1t2t3"></a><span data-ttu-id="f313f-113">Output: (' t 1,' t 2,' t 3) []</span><span class="sxs-lookup"><span data-stu-id="f313f-113">Output : ('T1,'T2,'T3)[]</span></span>

<span data-ttu-id="f313f-114">Matrice contenente 3 tuple del form `(first[idx], second[idx], third[idx])` per ciascuna `idx` .</span><span class="sxs-lookup"><span data-stu-id="f313f-114">An array containing 3-tuples of the form `(first[idx], second[idx], third[idx])` for each `idx`.</span></span> <span data-ttu-id="f313f-115">Se le tre matrici non sono di uguale lunghezza, l'output sarà purché il più breve degli input.</span><span class="sxs-lookup"><span data-stu-id="f313f-115">If the three arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f313f-116">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="f313f-116">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="f313f-117">' T 1</span><span class="sxs-lookup"><span data-stu-id="f313f-117">'T1</span></span>

<span data-ttu-id="f313f-118">Tipo dei primi elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="f313f-118">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="f313f-119">T 2</span><span class="sxs-lookup"><span data-stu-id="f313f-119">'T2</span></span>

<span data-ttu-id="f313f-120">Tipo di secondi elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="f313f-120">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="f313f-121">' T 3</span><span class="sxs-lookup"><span data-stu-id="f313f-121">'T3</span></span>

<span data-ttu-id="f313f-122">Tipo dei tre elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="f313f-122">The type of the third array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="f313f-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f313f-123">See Also</span></span>

- [<span data-ttu-id="f313f-124">Microsoft.Quantum.Arrays.ZipPED</span><span class="sxs-lookup"><span data-stu-id="f313f-124">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)
- [<span data-ttu-id="f313f-125">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="f313f-125">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)