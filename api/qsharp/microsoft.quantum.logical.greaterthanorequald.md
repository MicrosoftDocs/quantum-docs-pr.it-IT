---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualD
title: GreaterThanOrEqualD (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualD
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 0c9fa353b549d3c137beac3bcc3cfb0e742f6d07
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197807"
---
# <a name="greaterthanorequald-function"></a><span data-ttu-id="88888-102">GreaterThanOrEqualD (funzione)</span><span class="sxs-lookup"><span data-stu-id="88888-102">GreaterThanOrEqualD function</span></span>

<span data-ttu-id="88888-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="88888-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="88888-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="88888-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="88888-105">Restituisce true se e solo se un numero è maggiore o uguale a un altro numero.</span><span class="sxs-lookup"><span data-stu-id="88888-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="88888-106">Input</span><span class="sxs-lookup"><span data-stu-id="88888-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="88888-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="88888-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="88888-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="88888-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="88888-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="88888-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="88888-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="88888-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="88888-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="88888-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="88888-112">`true` Se e solo se `a` è maggiore di o è uguale a `b` .</span><span class="sxs-lookup"><span data-stu-id="88888-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="88888-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="88888-113">Remarks</span></span>

<span data-ttu-id="88888-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="88888-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualD(a, b);
```