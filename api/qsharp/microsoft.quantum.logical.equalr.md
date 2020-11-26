---
uid: Microsoft.Quantum.Logical.EqualR
title: Equalr (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualR
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: d68b2f1a26bf318400d3c88b37d9aabcc38cbdfe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198007"
---
# <a name="equalr-function"></a><span data-ttu-id="6f959-102">Equalr (funzione)</span><span class="sxs-lookup"><span data-stu-id="6f959-102">EqualR function</span></span>

<span data-ttu-id="6f959-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="6f959-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="6f959-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6f959-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6f959-105">Restituisce true se e solo se due input sono uguali.</span><span class="sxs-lookup"><span data-stu-id="6f959-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="6f959-106">Input</span><span class="sxs-lookup"><span data-stu-id="6f959-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="6f959-107">r: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="6f959-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="6f959-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="6f959-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="6f959-109">b: __non <Result> valida__</span><span class="sxs-lookup"><span data-stu-id="6f959-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="6f959-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="6f959-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="6f959-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6f959-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6f959-112">`true` Se e solo se `a` è uguale a `b` .</span><span class="sxs-lookup"><span data-stu-id="6f959-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="6f959-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="6f959-113">Remarks</span></span>

<span data-ttu-id="6f959-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="6f959-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualR(a, b);
```