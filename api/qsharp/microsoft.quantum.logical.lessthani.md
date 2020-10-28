---
uid: Microsoft.Quantum.Logical.LessThanI
title: LessThanI (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanI
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 204e62a87d2b3d0070946985030d038ead686457
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723485"
---
# <a name="lessthani-function"></a><span data-ttu-id="3981a-102">LessThanI (funzione)</span><span class="sxs-lookup"><span data-stu-id="3981a-102">LessThanI function</span></span>

<span data-ttu-id="3981a-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="3981a-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="3981a-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3981a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3981a-105">Restituisce true se e solo se un numero è minore di un altro numero.</span><span class="sxs-lookup"><span data-stu-id="3981a-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="3981a-106">Input</span><span class="sxs-lookup"><span data-stu-id="3981a-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="3981a-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3981a-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3981a-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="3981a-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="3981a-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3981a-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3981a-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="3981a-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="3981a-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3981a-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3981a-112">`true` Se e solo se `a` è strettamente inferiore a `b` .</span><span class="sxs-lookup"><span data-stu-id="3981a-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="3981a-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="3981a-113">Remarks</span></span>

<span data-ttu-id="3981a-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="3981a-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanI(a, b);
```