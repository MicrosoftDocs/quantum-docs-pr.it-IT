---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: LookupFunction (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: db20795719d11138cbdc5a38c0a19d0f247af059
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220774"
---
# <a name="lookupfunction-function"></a><span data-ttu-id="13f4c-102">LookupFunction (funzione)</span><span class="sxs-lookup"><span data-stu-id="13f4c-102">LookupFunction function</span></span>

<span data-ttu-id="13f4c-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="13f4c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="13f4c-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="13f4c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="13f4c-105">Data una matrice, restituisce una funzione che restituisce elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="13f4c-105">Given an array, returns a function which returns elements of that array.</span></span>

```qsharp
function LookupFunction<'T> (array : 'T[]) : (Int -> 'T)
```


## <a name="input"></a><span data-ttu-id="13f4c-106">Input</span><span class="sxs-lookup"><span data-stu-id="13f4c-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="13f4c-107">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="13f4c-107">array : 'T[]</span></span>

<span data-ttu-id="13f4c-108">Matrice da rappresentare come funzione di ricerca.</span><span class="sxs-lookup"><span data-stu-id="13f4c-108">The array to be represented as a lookup function.</span></span>



## <a name="output--int---t"></a><span data-ttu-id="13f4c-109">Output: [int](xref:microsoft.quantum.lang-ref.int) -> t</span><span class="sxs-lookup"><span data-stu-id="13f4c-109">Output : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="13f4c-110">Funzione di questo `f` tipo `f(idx) == f[idx]` .</span><span class="sxs-lookup"><span data-stu-id="13f4c-110">A function `f` such that `f(idx) == f[idx]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="13f4c-111">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="13f4c-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="13f4c-112">T</span><span class="sxs-lookup"><span data-stu-id="13f4c-112">'T</span></span>

<span data-ttu-id="13f4c-113">Tipo degli elementi della matrice rappresentata come funzione di ricerca.</span><span class="sxs-lookup"><span data-stu-id="13f4c-113">The type of the elements of the array being represented as a lookup function.</span></span>

## <a name="remarks"></a><span data-ttu-id="13f4c-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="13f4c-114">Remarks</span></span>

<span data-ttu-id="13f4c-115">Questa funzione è particolarmente utile per l'interoperabilità con funzioni e operazioni che accettano `Int -> 'T` funzioni come argomenti.</span><span class="sxs-lookup"><span data-stu-id="13f4c-115">This function is mainly useful for interoperating with functions and operations that take `Int -> 'T` functions as their arguments.</span></span> <span data-ttu-id="13f4c-116">Si tratta di un'operazione comune, ad esempio, nella libreria di rappresentazione del generatore, in cui le funzioni vengono usate per evitare la necessità di registrare un'intera matrice in memoria.</span><span class="sxs-lookup"><span data-stu-id="13f4c-116">This is common, for instance, in the generator representation library, where functions are used to avoid the need to record an entire array in memory.</span></span>