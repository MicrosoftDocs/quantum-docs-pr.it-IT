---
uid: Microsoft.Quantum.Arrays.ElementsAt
title: ElementsAt (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ElementsAt
qsharp.summary: Returns the array's elements at a given range of indices.
ms.openlocfilehash: 83b5e97085234e8249869f858400cba265d13058
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221454"
---
# <a name="elementsat-function"></a><span data-ttu-id="08ed5-102">ElementsAt (funzione)</span><span class="sxs-lookup"><span data-stu-id="08ed5-102">ElementsAt function</span></span>

<span data-ttu-id="08ed5-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="08ed5-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="08ed5-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="08ed5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="08ed5-105">Restituisce gli elementi della matrice in un intervallo di indici specificato.</span><span class="sxs-lookup"><span data-stu-id="08ed5-105">Returns the array's elements at a given range of indices.</span></span>

```qsharp
function ElementsAt<'T> (range : Range, array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="08ed5-106">Input</span><span class="sxs-lookup"><span data-stu-id="08ed5-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="08ed5-107">intervallo: [intervallo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="08ed5-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="08ed5-108">Intervallo di indici di matrici</span><span class="sxs-lookup"><span data-stu-id="08ed5-108">Range of array indexes</span></span>


### <a name="array--t"></a><span data-ttu-id="08ed5-109">matrice:' t []</span><span class="sxs-lookup"><span data-stu-id="08ed5-109">array : 'T[]</span></span>

<span data-ttu-id="08ed5-110">Array</span><span class="sxs-lookup"><span data-stu-id="08ed5-110">Array</span></span>



## <a name="output--t"></a><span data-ttu-id="08ed5-111">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="08ed5-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="08ed5-112">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="08ed5-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="08ed5-113">T</span><span class="sxs-lookup"><span data-stu-id="08ed5-113">'T</span></span>

<span data-ttu-id="08ed5-114">Tipo di ogni elemento di `array` .</span><span class="sxs-lookup"><span data-stu-id="08ed5-114">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="08ed5-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08ed5-115">See Also</span></span>

- [<span data-ttu-id="08ed5-116">Microsoft. Quantum. Arrays. ElementAt</span><span class="sxs-lookup"><span data-stu-id="08ed5-116">Microsoft.Quantum.Arrays.ElementAt</span></span>](xref:Microsoft.Quantum.Arrays.ElementAt)
- [<span data-ttu-id="08ed5-117">Microsoft. Quantum. Arrays. LookupFunction</span><span class="sxs-lookup"><span data-stu-id="08ed5-117">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)