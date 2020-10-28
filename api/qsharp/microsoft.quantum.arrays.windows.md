---
uid: Microsoft.Quantum.Arrays.Windows
title: Funzione Windows
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: 6071d1c3e5981855c57abd0e741b1de0201c30a3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718746"
---
# <a name="windows-function"></a><span data-ttu-id="e4075-102">Funzione Windows</span><span class="sxs-lookup"><span data-stu-id="e4075-102">Windows function</span></span>

<span data-ttu-id="e4075-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e4075-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e4075-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e4075-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e4075-105">Restituisce tutte le sottomatrici consecutive di lunghezza `size` .</span><span class="sxs-lookup"><span data-stu-id="e4075-105">Returns all consecutive subarrays of length `size`.</span></span>

```qsharp
function Windows<'T> (size : Int, array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="e4075-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e4075-106">Description</span></span>

<span data-ttu-id="e4075-107">Questa funzione restituisce tutte le `n - size + 1` sottomatrici di lunghezza `size` nell'ordine, dove `n` è la lunghezza di `arr` .</span><span class="sxs-lookup"><span data-stu-id="e4075-107">This function returns all `n - size + 1` subarrays of length `size` in order, where `n` is the length of `arr`.</span></span>
<span data-ttu-id="e4075-108">Le prime sottomatrici sono `arr[0..size - 1], arr[1..size], arr[2..size + 1]` fino all'ultima sottomatrice `arr[n - size..n - 1]` .</span><span class="sxs-lookup"><span data-stu-id="e4075-108">The first subarrays are `arr[0..size - 1], arr[1..size], arr[2..size + 1]` until the last subarray `arr[n - size..n - 1]`.</span></span>

<span data-ttu-id="e4075-109">Se `size <= 0` o `size > n` , viene restituita una matrice vuota.</span><span class="sxs-lookup"><span data-stu-id="e4075-109">If `size <= 0` or `size > n`, an empty array is returned.</span></span>

## <a name="input"></a><span data-ttu-id="e4075-110">Input</span><span class="sxs-lookup"><span data-stu-id="e4075-110">Input</span></span>

### <a name="size--int"></a><span data-ttu-id="e4075-111">Dimensioni: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e4075-111">size : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e4075-112">Lunghezza delle sottomatrici.</span><span class="sxs-lookup"><span data-stu-id="e4075-112">Length of the subarrays.</span></span>


### <a name="array--t"></a><span data-ttu-id="e4075-113">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="e4075-113">array : 'T[]</span></span>

<span data-ttu-id="e4075-114">Matrice di elementi.</span><span class="sxs-lookup"><span data-stu-id="e4075-114">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="e4075-115">Output:' t [] []</span><span class="sxs-lookup"><span data-stu-id="e4075-115">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e4075-116">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="e4075-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e4075-117">T</span><span class="sxs-lookup"><span data-stu-id="e4075-117">'T</span></span>

<span data-ttu-id="e4075-118">Tipo di `array` elementi.</span><span class="sxs-lookup"><span data-stu-id="e4075-118">The type of `array` elements.</span></span>