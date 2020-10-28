---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: d4e612d2f175015b7193634aeec12f9df12df7d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713233"
---
# <a name="rangereverse-function"></a><span data-ttu-id="f6bca-102">RangeReverse (funzione)</span><span class="sxs-lookup"><span data-stu-id="f6bca-102">RangeReverse function</span></span>

<span data-ttu-id="f6bca-103">Spazio dei nomi: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="f6bca-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="f6bca-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f6bca-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f6bca-105">Restituisce un nuovo intervallo che è l'inverso dell'intervallo di input.</span><span class="sxs-lookup"><span data-stu-id="f6bca-105">Returns a new range which is the reverse of the input range.</span></span>

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a><span data-ttu-id="f6bca-106">Input</span><span class="sxs-lookup"><span data-stu-id="f6bca-106">Input</span></span>

### <a name="r--range"></a><span data-ttu-id="f6bca-107">r: [intervallo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="f6bca-107">r : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="f6bca-108">Intervallo di input.</span><span class="sxs-lookup"><span data-stu-id="f6bca-108">Input range.</span></span>



## <a name="output--range"></a><span data-ttu-id="f6bca-109">Output: [intervallo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="f6bca-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="f6bca-110">Nuovo intervallo che è l'inverso dell'intervallo specificato.</span><span class="sxs-lookup"><span data-stu-id="f6bca-110">A new range that is the reverse of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="f6bca-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="f6bca-111">Remarks</span></span>

<span data-ttu-id="f6bca-112">Si noti che l'inverso di un intervallo non è semplicemente `end` .. `-step` .. `start` , perché l'ultimo elemento effettivo di un intervallo potrebbe non essere uguale a `end` .</span><span class="sxs-lookup"><span data-stu-id="f6bca-112">Note that the reverse of a range is not simply `end`..`-step`..`start`, because the actual last element of a range may not be the same as `end`.</span></span>