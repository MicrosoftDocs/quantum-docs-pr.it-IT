---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: f3b94d3c6fa6350a2c337f8bc8d889d24d87a85b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853649"
---
# <a name="rangereverse-function"></a><span data-ttu-id="d3e26-102">RangeReverse (funzione)</span><span class="sxs-lookup"><span data-stu-id="d3e26-102">RangeReverse function</span></span>

<span data-ttu-id="d3e26-103">Spazio dei nomi: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="d3e26-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="d3e26-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="d3e26-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="d3e26-105">Restituisce un nuovo intervallo che è l'inverso dell'intervallo di input.</span><span class="sxs-lookup"><span data-stu-id="d3e26-105">Returns a new range which is the reverse of the input range.</span></span>

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a><span data-ttu-id="d3e26-106">Input</span><span class="sxs-lookup"><span data-stu-id="d3e26-106">Input</span></span>

### <a name="r--range"></a><span data-ttu-id="d3e26-107">r: [intervallo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="d3e26-107">r : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="d3e26-108">Intervallo di input.</span><span class="sxs-lookup"><span data-stu-id="d3e26-108">Input range.</span></span>



## <a name="output--range"></a><span data-ttu-id="d3e26-109">Output: [intervallo](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="d3e26-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="d3e26-110">Nuovo intervallo che è l'inverso dell'intervallo specificato.</span><span class="sxs-lookup"><span data-stu-id="d3e26-110">A new range that is the reverse of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="d3e26-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="d3e26-111">Remarks</span></span>

<span data-ttu-id="d3e26-112">Si noti che l'inverso di un intervallo non è semplicemente `end` .. `-step` .. `start` , perché l'ultimo elemento effettivo di un intervallo potrebbe non essere uguale a `end` .</span><span class="sxs-lookup"><span data-stu-id="d3e26-112">Note that the reverse of a range is not simply `end`..`-step`..`start`, because the actual last element of a range may not be the same as `end`.</span></span>