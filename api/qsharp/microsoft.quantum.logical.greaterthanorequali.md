---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualI
title: GreaterThanOrEqualI (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualI
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: c1a513500c8a70bd7628976974387cba48162e80
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849176"
---
# <a name="greaterthanorequali-function"></a><span data-ttu-id="c75e1-102">GreaterThanOrEqualI (funzione)</span><span class="sxs-lookup"><span data-stu-id="c75e1-102">GreaterThanOrEqualI function</span></span>

<span data-ttu-id="c75e1-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="c75e1-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="c75e1-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c75e1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c75e1-105">Restituisce true se e solo se un numero è maggiore o uguale a un altro numero.</span><span class="sxs-lookup"><span data-stu-id="c75e1-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="c75e1-106">Input</span><span class="sxs-lookup"><span data-stu-id="c75e1-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="c75e1-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c75e1-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c75e1-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="c75e1-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="c75e1-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c75e1-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c75e1-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="c75e1-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c75e1-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c75e1-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c75e1-112">`true` Se e solo se `a` è maggiore di o è uguale a `b` .</span><span class="sxs-lookup"><span data-stu-id="c75e1-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c75e1-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="c75e1-113">Remarks</span></span>

<span data-ttu-id="c75e1-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="c75e1-114">The following are equivalent:</span></span>

```qsharp
let cond = a >= b;
let cond = GreaterThanOrEqualI(a, b);
```