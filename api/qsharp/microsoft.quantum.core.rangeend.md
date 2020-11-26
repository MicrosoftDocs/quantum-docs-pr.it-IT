---
uid: Microsoft.Quantum.Core.RangeEnd
title: RangeEnd (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeEnd
qsharp.summary: Returns the defined end value of the given range, which is not necessarily the last element in the sequence.
ms.openlocfilehash: 90a9e31bf5c4a5e92a35998ddaec8c9e9de9888e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224038"
---
# <a name="rangeend-function"></a><span data-ttu-id="2f32b-102">RangeEnd (funzione)</span><span class="sxs-lookup"><span data-stu-id="2f32b-102">RangeEnd function</span></span>

<span data-ttu-id="2f32b-103">Spazio dei nomi: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="2f32b-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="2f32b-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="2f32b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="2f32b-105">Restituisce il valore finale definito dell'intervallo specificato, che non è necessariamente l'ultimo elemento della sequenza.</span><span class="sxs-lookup"><span data-stu-id="2f32b-105">Returns the defined end value of the given range, which is not necessarily the last element in the sequence.</span></span>

```qsharp
function RangeEnd (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="2f32b-106">Input</span><span class="sxs-lookup"><span data-stu-id="2f32b-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="2f32b-107">intervallo: [intervallo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="2f32b-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="2f32b-108">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2f32b-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2f32b-109">Valore finale definito dell'intervallo specificato.</span><span class="sxs-lookup"><span data-stu-id="2f32b-109">The defined end value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="2f32b-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="2f32b-110">Remarks</span></span>

<span data-ttu-id="2f32b-111">Il primo elemento di un'espressione di intervallo è `start` , il secondo elemento è `start+step` , il terzo elemento è `start+step+step` e così via, fino a quando non `end` viene passato.</span><span class="sxs-lookup"><span data-stu-id="2f32b-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="2f32b-112">Si noti che il valore finale definito di un intervallo può differire dall'ultimo elemento nella sequenza specificata dall'intervallo. ad esempio, in un intervallo compreso tra 0..</span><span class="sxs-lookup"><span data-stu-id="2f32b-112">Note that the defined end value of a range can differ from the last element in the sequence specified by the range; for example, in a range 0 ..</span></span> <span data-ttu-id="2f32b-113">2...</span><span class="sxs-lookup"><span data-stu-id="2f32b-113">2 ..</span></span> <span data-ttu-id="2f32b-114">5 l'ultimo elemento è 4, ma il valore finale è 5.</span><span class="sxs-lookup"><span data-stu-id="2f32b-114">5 the last element is 4 but the end value is 5.</span></span>