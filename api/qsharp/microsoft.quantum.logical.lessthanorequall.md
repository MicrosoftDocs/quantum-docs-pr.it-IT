---
uid: Microsoft.Quantum.Logical.LessThanOrEqualL
title: LessThanOrEqualL (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualL
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 2322ae4dd6025108d322d29770f42953213aa025
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197602"
---
# <a name="lessthanorequall-function"></a><span data-ttu-id="559df-102">LessThanOrEqualL (funzione)</span><span class="sxs-lookup"><span data-stu-id="559df-102">LessThanOrEqualL function</span></span>

<span data-ttu-id="559df-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="559df-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="559df-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="559df-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="559df-105">Restituisce true se e solo se un numero è minore o uguale a un altro numero.</span><span class="sxs-lookup"><span data-stu-id="559df-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="559df-106">Input</span><span class="sxs-lookup"><span data-stu-id="559df-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="559df-107">r: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="559df-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="559df-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="559df-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="559df-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="559df-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="559df-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="559df-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="559df-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="559df-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="559df-112">`true` Se e solo se `a` è minore o uguale a `b` .</span><span class="sxs-lookup"><span data-stu-id="559df-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="559df-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="559df-113">Remarks</span></span>

<span data-ttu-id="559df-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="559df-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualL(a, b);
```