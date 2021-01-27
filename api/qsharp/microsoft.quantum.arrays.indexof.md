---
uid: Microsoft.Quantum.Arrays.IndexOf
title: Funzione IndexOf
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 64db55e831078a7130a3ced6a30bfbd2299c392d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848515"
---
# <a name="indexof-function"></a><span data-ttu-id="bd7f6-102">Funzione IndexOf</span><span class="sxs-lookup"><span data-stu-id="bd7f6-102">IndexOf function</span></span>

<span data-ttu-id="bd7f6-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="bd7f6-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="bd7f6-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bd7f6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bd7f6-105">Restituisce il primo indice del primo elemento di una matrice che soddisfa un predicato specificato.</span><span class="sxs-lookup"><span data-stu-id="bd7f6-105">Returns the first index of the first element in an array that satisfies a given predicate.</span></span> <span data-ttu-id="bd7f6-106">Se tale elemento non esiste, restituisce-1.</span><span class="sxs-lookup"><span data-stu-id="bd7f6-106">If no such element exists, returns -1.</span></span>

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="bd7f6-107">Input</span><span class="sxs-lookup"><span data-stu-id="bd7f6-107">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="bd7f6-108">predicato:' t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="bd7f6-108">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="bd7f6-109">Funzione di predicato che agisce sugli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="bd7f6-109">A predicate function acting on elements of the array.</span></span>


### <a name="arr--t"></a><span data-ttu-id="bd7f6-110">arr:' t []</span><span class="sxs-lookup"><span data-stu-id="bd7f6-110">arr : 'T[]</span></span>

<span data-ttu-id="bd7f6-111">Matrice da cercare utilizzando il predicato specificato.</span><span class="sxs-lookup"><span data-stu-id="bd7f6-111">An array to be searched using the given predicate.</span></span>



## <a name="output--int"></a><span data-ttu-id="bd7f6-112">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bd7f6-112">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bd7f6-113">Indice più piccolo in `idx` modo che `predicate(arr[idx])` sia true oppure-1 se tale elemento non esiste.</span><span class="sxs-lookup"><span data-stu-id="bd7f6-113">Either the smallest index `idx` such that `predicate(arr[idx])` is true, or -1 if no such element exists.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bd7f6-114">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="bd7f6-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bd7f6-115">T</span><span class="sxs-lookup"><span data-stu-id="bd7f6-115">'T</span></span>



## <a name="example"></a><span data-ttu-id="bd7f6-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="bd7f6-116">Example</span></span>

<span data-ttu-id="bd7f6-117">Si supponga che `IsEven : Int -> Bool` sia una funzione che restituisce `true` se e solo se l'input è pari.</span><span class="sxs-lookup"><span data-stu-id="bd7f6-117">Suppose that `IsEven : Int -> Bool` is a function that returns `true` if and only if its input is even.</span></span> <span data-ttu-id="bd7f6-118">Quindi, può essere usato con `IndexOf` per trovare il primo elemento even in una matrice:</span><span class="sxs-lookup"><span data-stu-id="bd7f6-118">Then, this can be used with `IndexOf` to find the first even element in an array:</span></span>

```qsharp
let items = [1, 3, 17, 2, 21];
let idx = IndexOf(IsEven, items); // returns 3
```