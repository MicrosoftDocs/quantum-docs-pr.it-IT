---
uid: Microsoft.Quantum.Core.RangeStart
title: RangeStart (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 3e4b0cebe34b4c98cb1d582a9cd11b46ff778517
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713166"
---
# <a name="rangestart-function"></a><span data-ttu-id="44e48-102">RangeStart (funzione)</span><span class="sxs-lookup"><span data-stu-id="44e48-102">RangeStart function</span></span>

<span data-ttu-id="44e48-103">Spazio dei nomi: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="44e48-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="44e48-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="44e48-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="44e48-105">Restituisce il valore iniziale definito dell'intervallo specificato.</span><span class="sxs-lookup"><span data-stu-id="44e48-105">Returns the defined start value of the given range.</span></span>

```qsharp
function RangeStart (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="44e48-106">Input</span><span class="sxs-lookup"><span data-stu-id="44e48-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="44e48-107">intervallo: [intervallo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="44e48-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="44e48-108">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="44e48-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="44e48-109">Valore iniziale definito dell'intervallo specificato.</span><span class="sxs-lookup"><span data-stu-id="44e48-109">The defined start value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="44e48-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="44e48-110">Remarks</span></span>

<span data-ttu-id="44e48-111">Il primo elemento di un'espressione di intervallo è `start` , il secondo elemento è `start+step` , il terzo elemento è `start+step+step` e così via, fino a quando non `end` viene passato.</span><span class="sxs-lookup"><span data-stu-id="44e48-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="44e48-112">Si noti che il valore iniziale definito di un intervallo è uguale al primo elemento della sequenza, a meno che l'intervallo non specifichi una sequenza vuota (ad esempio, 2.</span><span class="sxs-lookup"><span data-stu-id="44e48-112">Note that the defined start value of a range is the same as the first element of the sequence, unless the range specifies an empty sequence (for example, 2 ..</span></span> <span data-ttu-id="44e48-113">1).</span><span class="sxs-lookup"><span data-stu-id="44e48-113">1).</span></span>