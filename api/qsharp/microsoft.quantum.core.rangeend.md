---
uid: Microsoft.Quantum.Core.RangeEnd
title: RangeEnd (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeEnd
qsharp.summary: Returns the defined end value of the given range, which is not necessarily the last element in the sequence.
ms.openlocfilehash: 4dbcf517c4dc17775040444c77deb0e449082390
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713247"
---
# <a name="rangeend-function"></a><span data-ttu-id="2b04d-102">RangeEnd (funzione)</span><span class="sxs-lookup"><span data-stu-id="2b04d-102">RangeEnd function</span></span>

<span data-ttu-id="2b04d-103">Spazio dei nomi: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="2b04d-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="2b04d-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2b04d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2b04d-105">Restituisce il valore finale definito dell'intervallo specificato, che non è necessariamente l'ultimo elemento della sequenza.</span><span class="sxs-lookup"><span data-stu-id="2b04d-105">Returns the defined end value of the given range, which is not necessarily the last element in the sequence.</span></span>

```qsharp
function RangeEnd (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="2b04d-106">Input</span><span class="sxs-lookup"><span data-stu-id="2b04d-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="2b04d-107">intervallo: [intervallo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="2b04d-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="2b04d-108">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2b04d-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2b04d-109">Valore finale definito dell'intervallo specificato.</span><span class="sxs-lookup"><span data-stu-id="2b04d-109">The defined end value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="2b04d-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="2b04d-110">Remarks</span></span>

<span data-ttu-id="2b04d-111">Il primo elemento di un'espressione di intervallo è `start` , il secondo elemento è `start+step` , il terzo elemento è `start+step+step` e così via, fino a quando non `end` viene passato.</span><span class="sxs-lookup"><span data-stu-id="2b04d-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="2b04d-112">Si noti che il valore finale definito di un intervallo può differire dall'ultimo elemento nella sequenza specificata dall'intervallo. ad esempio, in un intervallo compreso tra 0..</span><span class="sxs-lookup"><span data-stu-id="2b04d-112">Note that the defined end value of a range can differ from the last element in the sequence specified by the range; for example, in a range 0 ..</span></span> <span data-ttu-id="2b04d-113">2...</span><span class="sxs-lookup"><span data-stu-id="2b04d-113">2 ..</span></span> <span data-ttu-id="2b04d-114">5 l'ultimo elemento è 4, ma il valore finale è 5.</span><span class="sxs-lookup"><span data-stu-id="2b04d-114">5 the last element is 4 but the end value is 5.</span></span>