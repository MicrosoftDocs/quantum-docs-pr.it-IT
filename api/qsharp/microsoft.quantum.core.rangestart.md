---
uid: Microsoft.Quantum.Core.RangeStart
title: RangeStart (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 5b04e8c860a4bd6af7b10b4dbf803b1eb69ef5d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98831109"
---
# <a name="rangestart-function"></a><span data-ttu-id="34e97-102">RangeStart (funzione)</span><span class="sxs-lookup"><span data-stu-id="34e97-102">RangeStart function</span></span>

<span data-ttu-id="34e97-103">Spazio dei nomi: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="34e97-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="34e97-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="34e97-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="34e97-105">Restituisce il valore iniziale definito dell'intervallo specificato.</span><span class="sxs-lookup"><span data-stu-id="34e97-105">Returns the defined start value of the given range.</span></span>

```qsharp
function RangeStart (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="34e97-106">Input</span><span class="sxs-lookup"><span data-stu-id="34e97-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="34e97-107">intervallo: [intervallo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="34e97-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="34e97-108">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="34e97-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="34e97-109">Valore iniziale definito dell'intervallo specificato.</span><span class="sxs-lookup"><span data-stu-id="34e97-109">The defined start value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="34e97-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="34e97-110">Remarks</span></span>

<span data-ttu-id="34e97-111">Il primo elemento di un'espressione di intervallo è `start` , il secondo elemento è `start+step` , il terzo elemento è `start+step+step` e così via, fino a quando non `end` viene passato.</span><span class="sxs-lookup"><span data-stu-id="34e97-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="34e97-112">Si noti che il valore iniziale definito di un intervallo è uguale al primo elemento della sequenza, a meno che l'intervallo non specifichi una sequenza vuota (ad esempio, 2.</span><span class="sxs-lookup"><span data-stu-id="34e97-112">Note that the defined start value of a range is the same as the first element of the sequence, unless the range specifies an empty sequence (for example, 2 ..</span></span> <span data-ttu-id="34e97-113">1).</span><span class="sxs-lookup"><span data-stu-id="34e97-113">1).</span></span>