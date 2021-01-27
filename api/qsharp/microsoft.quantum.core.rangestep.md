---
uid: Microsoft.Quantum.Core.RangeStep
title: RangeStep (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: 667b579337eec28d6b75de61668bd79de176883e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853607"
---
# <a name="rangestep-function"></a><span data-ttu-id="ef9e6-102">RangeStep (funzione)</span><span class="sxs-lookup"><span data-stu-id="ef9e6-102">RangeStep function</span></span>

<span data-ttu-id="ef9e6-103">Spazio dei nomi: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="ef9e6-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="ef9e6-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="ef9e6-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="ef9e6-105">Restituisce il numero intero che specifica la modalità di calcolo del valore successivo di un intervallo.</span><span class="sxs-lookup"><span data-stu-id="ef9e6-105">Returns the integer that specifies how the next value of a range is calculated.</span></span>

```qsharp
function RangeStep (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="ef9e6-106">Input</span><span class="sxs-lookup"><span data-stu-id="ef9e6-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="ef9e6-107">intervallo: [intervallo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="ef9e6-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="ef9e6-108">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ef9e6-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ef9e6-109">Valore del passaggio definito dell'intervallo specificato.</span><span class="sxs-lookup"><span data-stu-id="ef9e6-109">The defined step value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="ef9e6-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="ef9e6-110">Remarks</span></span>

<span data-ttu-id="ef9e6-111">Il primo elemento di un'espressione di intervallo è `start` , il secondo elemento è `start+step` , il terzo elemento è `start+step+step` e così via, fino a quando non `end` viene passato.</span><span class="sxs-lookup"><span data-stu-id="ef9e6-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>