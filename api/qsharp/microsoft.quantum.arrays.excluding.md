---
uid: Microsoft.Quantum.Arrays.Excluding
title: Esclusione di funzioni
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Excluding
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: c117431e3d98bba4ed3d29cb0b171247bf77be0b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848663"
---
# <a name="excluding-function"></a><span data-ttu-id="22635-102">Esclusione di funzioni</span><span class="sxs-lookup"><span data-stu-id="22635-102">Excluding function</span></span>

<span data-ttu-id="22635-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="22635-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="22635-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="22635-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="22635-105">Restituisce una matrice contenente gli elementi di un'altra matrice, esclusi gli elementi in un determinato elenco di indici.</span><span class="sxs-lookup"><span data-stu-id="22635-105">Returns an array containing the elements of another array, excluding elements at a given list of indices.</span></span>

```qsharp
function Excluding<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="22635-106">Input</span><span class="sxs-lookup"><span data-stu-id="22635-106">Input</span></span>

### <a name="remove--int"></a><span data-ttu-id="22635-107">Remove: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="22635-107">remove : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="22635-108">Matrice di indici che indica gli elementi che devono essere esclusi dall'output.</span><span class="sxs-lookup"><span data-stu-id="22635-108">An array of indices denoting which elements should be excluded from the output.</span></span>


### <a name="array--t"></a><span data-ttu-id="22635-109">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="22635-109">array : 'T[]</span></span>

<span data-ttu-id="22635-110">Matrice di cui vengono presi i valori nella matrice di output.</span><span class="sxs-lookup"><span data-stu-id="22635-110">Array of which the values in the output array are taken.</span></span>



## <a name="output--t"></a><span data-ttu-id="22635-111">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="22635-111">Output : 'T[]</span></span>

<span data-ttu-id="22635-112">Matrice `output` che `output[0]` rappresenta il primo elemento di `array` il cui indice non è presente in `remove` , ovvero `output[1]` il secondo elemento e così via.</span><span class="sxs-lookup"><span data-stu-id="22635-112">An array `output` such that `output[0]` is the first element of `array` whose index does not appear in `remove`, such that `output[1]` is the second such element, and so forth.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="22635-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="22635-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="22635-114">T</span><span class="sxs-lookup"><span data-stu-id="22635-114">'T</span></span>

<span data-ttu-id="22635-115">Tipo degli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="22635-115">The type of the array elements.</span></span>

## <a name="example"></a><span data-ttu-id="22635-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="22635-116">Example</span></span>

```qsharp
let array = [10, 11, 12, 13, 14, 15];
// The following line returns [10, 12, 15].
let subarray = Excluding([1, 3, 4], array);
```