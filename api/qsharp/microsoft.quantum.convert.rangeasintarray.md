---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: RangeAsIntArray (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: bd3ac51d2925d7a4450b2bc5e6f7899fcab18f2c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713362"
---
# <a name="rangeasintarray-function"></a><span data-ttu-id="05bf3-102">RangeAsIntArray (funzione)</span><span class="sxs-lookup"><span data-stu-id="05bf3-102">RangeAsIntArray function</span></span>

<span data-ttu-id="05bf3-103">Spazio dei nomi: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="05bf3-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="05bf3-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="05bf3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="05bf3-105">Crea una matrice `arr` di numeri interi enumerati da Start.. passaggio... fine.</span><span class="sxs-lookup"><span data-stu-id="05bf3-105">Creates an array `arr` of integers enumerated by start..step..end.</span></span>

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a><span data-ttu-id="05bf3-106">Input</span><span class="sxs-lookup"><span data-stu-id="05bf3-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="05bf3-107">intervallo: [intervallo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="05bf3-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="05bf3-108">Oggetto `Range` di valori `start..step..end` da convertire in una matrice.</span><span class="sxs-lookup"><span data-stu-id="05bf3-108">A `Range` of values `start..step..end` to be converted to an array.</span></span>



## <a name="output--int"></a><span data-ttu-id="05bf3-109">Output: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="05bf3-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="05bf3-110">Nuova matrice di numeri interi che corrisponde ai valori iterati da `range` .</span><span class="sxs-lookup"><span data-stu-id="05bf3-110">A new array of integers corresponding to values iterated over by `range`.</span></span>