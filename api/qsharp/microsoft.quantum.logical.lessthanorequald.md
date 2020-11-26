---
uid: Microsoft.Quantum.Logical.LessThanOrEqualD
title: LessThanOrEqualD (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualD
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 3f4ccb0888e7df7c43ff73be8a3140e3fa84d4dc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197637"
---
# <a name="lessthanorequald-function"></a><span data-ttu-id="7ba94-102">LessThanOrEqualD (funzione)</span><span class="sxs-lookup"><span data-stu-id="7ba94-102">LessThanOrEqualD function</span></span>

<span data-ttu-id="7ba94-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="7ba94-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="7ba94-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7ba94-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7ba94-105">Restituisce true se e solo se un numero è minore o uguale a un altro numero.</span><span class="sxs-lookup"><span data-stu-id="7ba94-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="7ba94-106">Input</span><span class="sxs-lookup"><span data-stu-id="7ba94-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="7ba94-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7ba94-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7ba94-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="7ba94-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="7ba94-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7ba94-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7ba94-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="7ba94-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="7ba94-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7ba94-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7ba94-112">`true` Se e solo se `a` è minore o uguale a `b` .</span><span class="sxs-lookup"><span data-stu-id="7ba94-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="7ba94-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="7ba94-113">Remarks</span></span>

<span data-ttu-id="7ba94-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="7ba94-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualD(a, b);
```