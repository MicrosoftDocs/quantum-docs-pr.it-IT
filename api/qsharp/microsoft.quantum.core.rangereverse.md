---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: 7bd7c55abe0b56b9d30b4c6e91f7175101dd2948
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213838"
---
# <a name="rangereverse-function"></a><span data-ttu-id="75911-102">RangeReverse (funzione)</span><span class="sxs-lookup"><span data-stu-id="75911-102">RangeReverse function</span></span>

<span data-ttu-id="75911-103">Spazio dei nomi: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="75911-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="75911-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="75911-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="75911-105">Restituisce un nuovo intervallo che è l'inverso dell'intervallo di input.</span><span class="sxs-lookup"><span data-stu-id="75911-105">Returns a new range which is the reverse of the input range.</span></span>

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a><span data-ttu-id="75911-106">Input</span><span class="sxs-lookup"><span data-stu-id="75911-106">Input</span></span>

### <a name="r--range"></a><span data-ttu-id="75911-107">r: [intervallo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="75911-107">r : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="75911-108">Intervallo di input.</span><span class="sxs-lookup"><span data-stu-id="75911-108">Input range.</span></span>



## <a name="output--range"></a><span data-ttu-id="75911-109">Output: [intervallo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="75911-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="75911-110">Nuovo intervallo che è l'inverso dell'intervallo specificato.</span><span class="sxs-lookup"><span data-stu-id="75911-110">A new range that is the reverse of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="75911-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="75911-111">Remarks</span></span>

<span data-ttu-id="75911-112">Si noti che l'inverso di un intervallo non è semplicemente `end` .. `-step` .. `start` , perché l'ultimo elemento effettivo di un intervallo potrebbe non essere uguale a `end` .</span><span class="sxs-lookup"><span data-stu-id="75911-112">Note that the reverse of a range is not simply `end`..`-step`..`start`, because the actual last element of a range may not be the same as `end`.</span></span>