---
uid: Microsoft.Quantum.Core.RangeStep
title: RangeStep (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: 39c8581fe795a1b76d2a6e81c238a271287c2c38
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213804"
---
# <a name="rangestep-function"></a><span data-ttu-id="48be0-102">RangeStep (funzione)</span><span class="sxs-lookup"><span data-stu-id="48be0-102">RangeStep function</span></span>

<span data-ttu-id="48be0-103">Spazio dei nomi: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="48be0-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="48be0-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="48be0-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="48be0-105">Restituisce il numero intero che specifica la modalità di calcolo del valore successivo di un intervallo.</span><span class="sxs-lookup"><span data-stu-id="48be0-105">Returns the integer that specifies how the next value of a range is calculated.</span></span>

```qsharp
function RangeStep (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="48be0-106">Input</span><span class="sxs-lookup"><span data-stu-id="48be0-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="48be0-107">intervallo: [intervallo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="48be0-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="48be0-108">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="48be0-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="48be0-109">Valore del passaggio definito dell'intervallo specificato.</span><span class="sxs-lookup"><span data-stu-id="48be0-109">The defined step value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="48be0-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="48be0-110">Remarks</span></span>

<span data-ttu-id="48be0-111">Il primo elemento di un'espressione di intervallo è `start` , il secondo elemento è `start+step` , il terzo elemento è `start+step+step` e così via, fino a quando non `end` viene passato.</span><span class="sxs-lookup"><span data-stu-id="48be0-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>