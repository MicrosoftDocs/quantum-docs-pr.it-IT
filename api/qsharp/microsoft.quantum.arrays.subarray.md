---
uid: Microsoft.Quantum.Arrays.Subarray
title: Funzione subarray
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Subarray
qsharp.summary: Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.
ms.openlocfilehash: be7b6ee1a396d67ebc311d8d97f4bd751a32d171
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718842"
---
# <a name="subarray-function"></a><span data-ttu-id="e8a06-102">Funzione subarray</span><span class="sxs-lookup"><span data-stu-id="e8a06-102">Subarray function</span></span>

<span data-ttu-id="e8a06-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e8a06-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e8a06-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e8a06-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e8a06-105">Accetta una matrice e un elenco di percorsi e produce una nuova matrice formata dagli elementi della matrice originale che corrispondono alle posizioni specificate.</span><span class="sxs-lookup"><span data-stu-id="e8a06-105">Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.</span></span>

```qsharp
function Subarray<'T> (indices : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="e8a06-106">Input</span><span class="sxs-lookup"><span data-stu-id="e8a06-106">Input</span></span>

### <a name="indices--int"></a><span data-ttu-id="e8a06-107">indici: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="e8a06-107">indices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="e8a06-108">Elenco di numeri interi utilizzati per definire la sottomatrice.</span><span class="sxs-lookup"><span data-stu-id="e8a06-108">A list of integers that is used to define the subarray.</span></span>


### <a name="array--t"></a><span data-ttu-id="e8a06-109">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="e8a06-109">array : 'T[]</span></span>

<span data-ttu-id="e8a06-110">Matrice di elementi su `'T` .</span><span class="sxs-lookup"><span data-stu-id="e8a06-110">An array of elements over `'T`.</span></span>



## <a name="output--t"></a><span data-ttu-id="e8a06-111">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="e8a06-111">Output : 'T[]</span></span>

<span data-ttu-id="e8a06-112">Matrice `out` di elementi i cui indici corrispondono alla sottomatrice, in modo tale che `out[idx] == array[indices[idx]]` .</span><span class="sxs-lookup"><span data-stu-id="e8a06-112">An array `out` of elements whose indices correspond to the subarray, such that `out[idx] == array[indices[idx]]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e8a06-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="e8a06-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e8a06-114">T</span><span class="sxs-lookup"><span data-stu-id="e8a06-114">'T</span></span>

<span data-ttu-id="e8a06-115">Tipo di `array` elementi.</span><span class="sxs-lookup"><span data-stu-id="e8a06-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="e8a06-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="e8a06-116">Remarks</span></span>

<span data-ttu-id="e8a06-117">La funzione viene definita per i tipi generici, ad esempio ogni volta che è presente una matrice `'T[]` e un elenco di percorsi che `Int[]` definiscono la sottomatrice.</span><span class="sxs-lookup"><span data-stu-id="e8a06-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a list of locations `Int[]` defining the subarray.</span></span>
<span data-ttu-id="e8a06-118">La costruzione della sottomatrice è basata sulla generazione di una nuova copia completa della matrice specificata anziché sulla gestione dei riferimenti.</span><span class="sxs-lookup"><span data-stu-id="e8a06-118">The construction of the subarray is a based on generating a new, deep copy of the given array as opposed to maintaining references.</span></span>

<span data-ttu-id="e8a06-119">Se `Length(indices) < Length(array)` , questa funzione restituirà un subset di `array` .</span><span class="sxs-lookup"><span data-stu-id="e8a06-119">If `Length(indices) < Length(array)`, this function will return a subset of `array`.</span></span> <span data-ttu-id="e8a06-120">D'altra parte, se `indices` contiene elementi ripetuti, verranno ripetuti anche gli elementi corrispondenti di `array` .</span><span class="sxs-lookup"><span data-stu-id="e8a06-120">On the other hand, if `indices` contains repeated elements, the corresponding elements of `array` will likewise be repeated.</span></span>
<span data-ttu-id="e8a06-121">Se `indices` e `array` sono della stessa lunghezza, questa funzione fornisce permutazioni di `array` .</span><span class="sxs-lookup"><span data-stu-id="e8a06-121">If `indices` and `array` are the same length, this function provides permutations of `array`.</span></span>