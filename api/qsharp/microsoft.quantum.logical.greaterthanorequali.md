---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualI
title: GreaterThanOrEqualI (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualI
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 0435aae4a824bd19d972e9f6b331260bbe21f692
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197790"
---
# <a name="greaterthanorequali-function"></a><span data-ttu-id="b0124-102">GreaterThanOrEqualI (funzione)</span><span class="sxs-lookup"><span data-stu-id="b0124-102">GreaterThanOrEqualI function</span></span>

<span data-ttu-id="b0124-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="b0124-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="b0124-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b0124-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b0124-105">Restituisce true se e solo se un numero è maggiore o uguale a un altro numero.</span><span class="sxs-lookup"><span data-stu-id="b0124-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="b0124-106">Input</span><span class="sxs-lookup"><span data-stu-id="b0124-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="b0124-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b0124-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b0124-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="b0124-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="b0124-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b0124-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b0124-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="b0124-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="b0124-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b0124-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b0124-112">`true` Se e solo se `a` è maggiore di o è uguale a `b` .</span><span class="sxs-lookup"><span data-stu-id="b0124-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b0124-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="b0124-113">Remarks</span></span>

<span data-ttu-id="b0124-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="b0124-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualI(a, b);
```