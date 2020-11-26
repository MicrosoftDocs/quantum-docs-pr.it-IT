---
uid: Microsoft.Quantum.Logical.NotEqualI
title: NotEqualI (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualI
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: dc132cbab556bd4b5d5c557ad267f1839e8039fc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197212"
---
# <a name="notequali-function"></a><span data-ttu-id="980f2-102">NotEqualI (funzione)</span><span class="sxs-lookup"><span data-stu-id="980f2-102">NotEqualI function</span></span>

<span data-ttu-id="980f2-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="980f2-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="980f2-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="980f2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="980f2-105">Restituisce true se e solo se due input non sono uguali.</span><span class="sxs-lookup"><span data-stu-id="980f2-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="980f2-106">Input</span><span class="sxs-lookup"><span data-stu-id="980f2-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="980f2-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="980f2-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="980f2-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="980f2-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="980f2-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="980f2-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="980f2-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="980f2-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="980f2-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="980f2-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="980f2-112">`true` Se e solo se `a` non è uguale a `b` .</span><span class="sxs-lookup"><span data-stu-id="980f2-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="980f2-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="980f2-113">Remarks</span></span>

<span data-ttu-id="980f2-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="980f2-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualI(a, b);
```