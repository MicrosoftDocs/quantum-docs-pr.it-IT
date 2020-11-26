---
uid: Microsoft.Quantum.Logical.LessThanI
title: LessThanI (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanI
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 5d5b17c8481ccf58b8e4fc4bb958e0adbf6d8f00
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197773"
---
# <a name="lessthani-function"></a><span data-ttu-id="d15dd-102">LessThanI (funzione)</span><span class="sxs-lookup"><span data-stu-id="d15dd-102">LessThanI function</span></span>

<span data-ttu-id="d15dd-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="d15dd-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="d15dd-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d15dd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d15dd-105">Restituisce true se e solo se un numero è minore di un altro numero.</span><span class="sxs-lookup"><span data-stu-id="d15dd-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="d15dd-106">Input</span><span class="sxs-lookup"><span data-stu-id="d15dd-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="d15dd-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d15dd-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d15dd-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="d15dd-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="d15dd-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d15dd-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d15dd-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="d15dd-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="d15dd-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d15dd-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d15dd-112">`true` Se e solo se `a` è strettamente inferiore a `b` .</span><span class="sxs-lookup"><span data-stu-id="d15dd-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d15dd-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="d15dd-113">Remarks</span></span>

<span data-ttu-id="d15dd-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="d15dd-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanI(a, b);
```