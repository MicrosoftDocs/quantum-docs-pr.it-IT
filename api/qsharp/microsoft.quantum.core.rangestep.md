---
uid: Microsoft.Quantum.Core.RangeStep
title: RangeStep (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: f8e4c42330f2d6afdc1c0a9bdde36081ccab2f94
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713163"
---
# <a name="rangestep-function"></a><span data-ttu-id="9b0a2-102">RangeStep (funzione)</span><span class="sxs-lookup"><span data-stu-id="9b0a2-102">RangeStep function</span></span>

<span data-ttu-id="9b0a2-103">Spazio dei nomi: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="9b0a2-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="9b0a2-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9b0a2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9b0a2-105">Restituisce il numero intero che specifica la modalità di calcolo del valore successivo di un intervallo.</span><span class="sxs-lookup"><span data-stu-id="9b0a2-105">Returns the integer that specifies how the next value of a range is calculated.</span></span>

```qsharp
function RangeStep (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="9b0a2-106">Input</span><span class="sxs-lookup"><span data-stu-id="9b0a2-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="9b0a2-107">intervallo: [intervallo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="9b0a2-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="9b0a2-108">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9b0a2-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9b0a2-109">Valore del passaggio definito dell'intervallo specificato.</span><span class="sxs-lookup"><span data-stu-id="9b0a2-109">The defined step value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="9b0a2-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="9b0a2-110">Remarks</span></span>

<span data-ttu-id="9b0a2-111">Il primo elemento di un'espressione di intervallo è `start` , il secondo elemento è `start+step` , il terzo elemento è `start+step+step` e così via, fino a quando non `end` viene passato.</span><span class="sxs-lookup"><span data-stu-id="9b0a2-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>