---
uid: Microsoft.Quantum.Logical.GreaterThanI
title: GreaterThanI (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanI
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 06cae04150f9f0164b06a4e3d4bb78242b41dc0b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197994"
---
# <a name="greaterthani-function"></a><span data-ttu-id="2995e-102">GreaterThanI (funzione)</span><span class="sxs-lookup"><span data-stu-id="2995e-102">GreaterThanI function</span></span>

<span data-ttu-id="2995e-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="2995e-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="2995e-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2995e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2995e-105">Restituisce true se e solo se un numero è maggiore di un altro numero.</span><span class="sxs-lookup"><span data-stu-id="2995e-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="2995e-106">Input</span><span class="sxs-lookup"><span data-stu-id="2995e-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="2995e-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2995e-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2995e-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="2995e-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="2995e-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2995e-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2995e-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="2995e-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="2995e-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2995e-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2995e-112">`true` Se e solo se `a` è strettamente maggiore di `b` .</span><span class="sxs-lookup"><span data-stu-id="2995e-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="2995e-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="2995e-113">Remarks</span></span>

<span data-ttu-id="2995e-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="2995e-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanI(a, b);
```