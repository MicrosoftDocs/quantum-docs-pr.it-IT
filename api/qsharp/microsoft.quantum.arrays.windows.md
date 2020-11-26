---
uid: Microsoft.Quantum.Arrays.Windows
title: Funzione Windows
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: 8f32a23aa4379744b84c3b8d9c8f565e61c3c64e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219890"
---
# <a name="windows-function"></a><span data-ttu-id="b393b-102">Funzione Windows</span><span class="sxs-lookup"><span data-stu-id="b393b-102">Windows function</span></span>

<span data-ttu-id="b393b-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b393b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b393b-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b393b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b393b-105">Restituisce tutte le sottomatrici consecutive di lunghezza `size` .</span><span class="sxs-lookup"><span data-stu-id="b393b-105">Returns all consecutive subarrays of length `size`.</span></span>

```qsharp
function Windows<'T> (size : Int, array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="b393b-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b393b-106">Description</span></span>

<span data-ttu-id="b393b-107">Questa funzione restituisce tutte le `n - size + 1` sottomatrici di lunghezza `size` nell'ordine, dove `n` è la lunghezza di `arr` .</span><span class="sxs-lookup"><span data-stu-id="b393b-107">This function returns all `n - size + 1` subarrays of length `size` in order, where `n` is the length of `arr`.</span></span>
<span data-ttu-id="b393b-108">Le prime sottomatrici sono `arr[0..size - 1], arr[1..size], arr[2..size + 1]` fino all'ultima sottomatrice `arr[n - size..n - 1]` .</span><span class="sxs-lookup"><span data-stu-id="b393b-108">The first subarrays are `arr[0..size - 1], arr[1..size], arr[2..size + 1]` until the last subarray `arr[n - size..n - 1]`.</span></span>

<span data-ttu-id="b393b-109">Se `size <= 0` o `size > n` , viene restituita una matrice vuota.</span><span class="sxs-lookup"><span data-stu-id="b393b-109">If `size <= 0` or `size > n`, an empty array is returned.</span></span>

## <a name="input"></a><span data-ttu-id="b393b-110">Input</span><span class="sxs-lookup"><span data-stu-id="b393b-110">Input</span></span>

### <a name="size--int"></a><span data-ttu-id="b393b-111">Dimensioni: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b393b-111">size : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b393b-112">Lunghezza delle sottomatrici.</span><span class="sxs-lookup"><span data-stu-id="b393b-112">Length of the subarrays.</span></span>


### <a name="array--t"></a><span data-ttu-id="b393b-113">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="b393b-113">array : 'T[]</span></span>

<span data-ttu-id="b393b-114">Matrice di elementi.</span><span class="sxs-lookup"><span data-stu-id="b393b-114">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="b393b-115">Output:' t [] []</span><span class="sxs-lookup"><span data-stu-id="b393b-115">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b393b-116">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="b393b-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b393b-117">T</span><span class="sxs-lookup"><span data-stu-id="b393b-117">'T</span></span>

<span data-ttu-id="b393b-118">Tipo di `array` elementi.</span><span class="sxs-lookup"><span data-stu-id="b393b-118">The type of `array` elements.</span></span>