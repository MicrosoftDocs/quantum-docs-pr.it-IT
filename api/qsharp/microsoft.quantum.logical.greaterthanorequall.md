---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualL
title: GreaterThanOrEqualL (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualL
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 5536c009d6e78eac9ab2320b42aec7d2d82946eb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197756"
---
# <a name="greaterthanorequall-function"></a><span data-ttu-id="a6d0f-102">GreaterThanOrEqualL (funzione)</span><span class="sxs-lookup"><span data-stu-id="a6d0f-102">GreaterThanOrEqualL function</span></span>

<span data-ttu-id="a6d0f-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="a6d0f-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="a6d0f-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a6d0f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a6d0f-105">Restituisce true se e solo se un numero è maggiore o uguale a un altro numero.</span><span class="sxs-lookup"><span data-stu-id="a6d0f-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="a6d0f-106">Input</span><span class="sxs-lookup"><span data-stu-id="a6d0f-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="a6d0f-107">r: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a6d0f-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="a6d0f-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="a6d0f-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="a6d0f-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a6d0f-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="a6d0f-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="a6d0f-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="a6d0f-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a6d0f-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a6d0f-112">`true` Se e solo se `a` è maggiore di o è uguale a `b` .</span><span class="sxs-lookup"><span data-stu-id="a6d0f-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a6d0f-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="a6d0f-113">Remarks</span></span>

<span data-ttu-id="a6d0f-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="a6d0f-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualL(a, b);
```