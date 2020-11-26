---
uid: Microsoft.Quantum.Core.RangeStart
title: RangeStart (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 44683b204ecd469f5f5412a7ec06e98ec8a4f37e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224004"
---
# <a name="rangestart-function"></a><span data-ttu-id="8c1d8-102">RangeStart (funzione)</span><span class="sxs-lookup"><span data-stu-id="8c1d8-102">RangeStart function</span></span>

<span data-ttu-id="8c1d8-103">Spazio dei nomi: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="8c1d8-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="8c1d8-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="8c1d8-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="8c1d8-105">Restituisce il valore iniziale definito dell'intervallo specificato.</span><span class="sxs-lookup"><span data-stu-id="8c1d8-105">Returns the defined start value of the given range.</span></span>

```qsharp
function RangeStart (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="8c1d8-106">Input</span><span class="sxs-lookup"><span data-stu-id="8c1d8-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="8c1d8-107">intervallo: [intervallo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="8c1d8-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="8c1d8-108">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8c1d8-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8c1d8-109">Valore iniziale definito dell'intervallo specificato.</span><span class="sxs-lookup"><span data-stu-id="8c1d8-109">The defined start value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="8c1d8-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="8c1d8-110">Remarks</span></span>

<span data-ttu-id="8c1d8-111">Il primo elemento di un'espressione di intervallo è `start` , il secondo elemento è `start+step` , il terzo elemento è `start+step+step` e così via, fino a quando non `end` viene passato.</span><span class="sxs-lookup"><span data-stu-id="8c1d8-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="8c1d8-112">Si noti che il valore iniziale definito di un intervallo è uguale al primo elemento della sequenza, a meno che l'intervallo non specifichi una sequenza vuota (ad esempio, 2.</span><span class="sxs-lookup"><span data-stu-id="8c1d8-112">Note that the defined start value of a range is the same as the first element of the sequence, unless the range specifies an empty sequence (for example, 2 ..</span></span> <span data-ttu-id="8c1d8-113">1).</span><span class="sxs-lookup"><span data-stu-id="8c1d8-113">1).</span></span>