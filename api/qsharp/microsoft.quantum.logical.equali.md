---
uid: Microsoft.Quantum.Logical.EqualI
title: Equali (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualI
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: be92ef2b63981094e1a95c38e02de95c3c2bbf3a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198164"
---
# <a name="equali-function"></a><span data-ttu-id="dd5a1-102">Equali (funzione)</span><span class="sxs-lookup"><span data-stu-id="dd5a1-102">EqualI function</span></span>

<span data-ttu-id="dd5a1-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="dd5a1-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="dd5a1-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dd5a1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dd5a1-105">Restituisce true se e solo se due input sono uguali.</span><span class="sxs-lookup"><span data-stu-id="dd5a1-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="dd5a1-106">Input</span><span class="sxs-lookup"><span data-stu-id="dd5a1-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="dd5a1-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dd5a1-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dd5a1-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="dd5a1-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="dd5a1-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dd5a1-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dd5a1-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="dd5a1-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="dd5a1-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="dd5a1-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="dd5a1-112">`true` Se e solo se `a` è uguale a `b` .</span><span class="sxs-lookup"><span data-stu-id="dd5a1-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="dd5a1-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="dd5a1-113">Remarks</span></span>

<span data-ttu-id="dd5a1-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="dd5a1-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualI(a, b);
```