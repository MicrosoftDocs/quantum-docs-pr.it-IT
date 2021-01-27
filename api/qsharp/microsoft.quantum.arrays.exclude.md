---
uid: Microsoft.Quantum.Arrays.Exclude
title: Escludi funzione
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Exclude
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 76cdee56e84951c63e80babfdca6a3de33583cab
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848670"
---
# <a name="exclude-function"></a><span data-ttu-id="a7f2b-102">Escludi funzione</span><span class="sxs-lookup"><span data-stu-id="a7f2b-102">Exclude function</span></span>

<span data-ttu-id="a7f2b-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a7f2b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a7f2b-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a7f2b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a7f2b-105">Restituisce una matrice contenente gli elementi di un'altra matrice, esclusi gli elementi in un determinato elenco di indici.</span><span class="sxs-lookup"><span data-stu-id="a7f2b-105">Returns an array containing the elements of another array, excluding elements at a given list of indices.</span></span>

```qsharp
function Exclude<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="a7f2b-106">Input</span><span class="sxs-lookup"><span data-stu-id="a7f2b-106">Input</span></span>

### <a name="remove--int"></a><span data-ttu-id="a7f2b-107">Remove: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a7f2b-107">remove : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="a7f2b-108">Matrice di indici che indica gli elementi che devono essere esclusi dall'output.</span><span class="sxs-lookup"><span data-stu-id="a7f2b-108">An array of indices denoting which elements should be excluded from the output.</span></span>


### <a name="array--t"></a><span data-ttu-id="a7f2b-109">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="a7f2b-109">array : 'T[]</span></span>

<span data-ttu-id="a7f2b-110">Matrice di cui vengono presi i valori nella matrice di output.</span><span class="sxs-lookup"><span data-stu-id="a7f2b-110">Array of which the values in the output array are taken.</span></span>



## <a name="output--t"></a><span data-ttu-id="a7f2b-111">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="a7f2b-111">Output : 'T[]</span></span>

<span data-ttu-id="a7f2b-112">Matrice `output` che `output[0]` rappresenta il primo elemento di `array` il cui indice non è presente in `remove` , ovvero `output[1]` il secondo elemento e così via.</span><span class="sxs-lookup"><span data-stu-id="a7f2b-112">An array `output` such that `output[0]` is the first element of `array` whose index does not appear in `remove`, such that `output[1]` is the second such element, and so forth.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a7f2b-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="a7f2b-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a7f2b-114">T</span><span class="sxs-lookup"><span data-stu-id="a7f2b-114">'T</span></span>

<span data-ttu-id="a7f2b-115">Tipo degli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="a7f2b-115">The type of the array elements.</span></span>

## <a name="example"></a><span data-ttu-id="a7f2b-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="a7f2b-116">Example</span></span>

```qsharp
let array = [10, 11, 12, 13, 14, 15];
// The following line returns [10, 12, 15].
let subarray = Exclude([1, 3, 4], array);
```