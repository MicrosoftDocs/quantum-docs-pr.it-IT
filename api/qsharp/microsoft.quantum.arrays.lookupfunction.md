---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: LookupFunction (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: 22b56bb7e9f03ebc5b2225efb2e6450d56022664
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845690"
---
# <a name="lookupfunction-function"></a><span data-ttu-id="d1a21-102">LookupFunction (funzione)</span><span class="sxs-lookup"><span data-stu-id="d1a21-102">LookupFunction function</span></span>

<span data-ttu-id="d1a21-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d1a21-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d1a21-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d1a21-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d1a21-105">Data una matrice, restituisce una funzione che restituisce elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="d1a21-105">Given an array, returns a function which returns elements of that array.</span></span>

```qsharp
function LookupFunction<'T> (array : 'T[]) : (Int -> 'T)
```


## <a name="input"></a><span data-ttu-id="d1a21-106">Input</span><span class="sxs-lookup"><span data-stu-id="d1a21-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="d1a21-107">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="d1a21-107">array : 'T[]</span></span>

<span data-ttu-id="d1a21-108">Matrice da rappresentare come funzione di ricerca.</span><span class="sxs-lookup"><span data-stu-id="d1a21-108">The array to be represented as a lookup function.</span></span>



## <a name="output--int---t"></a><span data-ttu-id="d1a21-109">Output: [int](xref:microsoft.quantum.lang-ref.int) -> t</span><span class="sxs-lookup"><span data-stu-id="d1a21-109">Output : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="d1a21-110">Funzione di questo `f` tipo `f(idx) == f[idx]` .</span><span class="sxs-lookup"><span data-stu-id="d1a21-110">A function `f` such that `f(idx) == f[idx]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d1a21-111">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="d1a21-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d1a21-112">T</span><span class="sxs-lookup"><span data-stu-id="d1a21-112">'T</span></span>

<span data-ttu-id="d1a21-113">Tipo degli elementi della matrice rappresentata come funzione di ricerca.</span><span class="sxs-lookup"><span data-stu-id="d1a21-113">The type of the elements of the array being represented as a lookup function.</span></span>

## <a name="remarks"></a><span data-ttu-id="d1a21-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="d1a21-114">Remarks</span></span>

<span data-ttu-id="d1a21-115">Questa funzione è particolarmente utile per l'interoperabilità con funzioni e operazioni che accettano `Int -> 'T` funzioni come argomenti.</span><span class="sxs-lookup"><span data-stu-id="d1a21-115">This function is mainly useful for interoperating with functions and operations that take `Int -> 'T` functions as their arguments.</span></span> <span data-ttu-id="d1a21-116">Si tratta di un'operazione comune, ad esempio, nella libreria di rappresentazione del generatore, in cui le funzioni vengono usate per evitare la necessità di registrare un'intera matrice in memoria.</span><span class="sxs-lookup"><span data-stu-id="d1a21-116">This is common, for instance, in the generator representation library, where functions are used to avoid the need to record an entire array in memory.</span></span>