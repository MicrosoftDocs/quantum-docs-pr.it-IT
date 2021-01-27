---
uid: Microsoft.Quantum.Logical.LessThanL
title: LessThanL (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanL
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: d5753f9e1447fc1bd433703037fe44c86aaa659c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849156"
---
# <a name="lessthanl-function"></a><span data-ttu-id="b1443-102">LessThanL (funzione)</span><span class="sxs-lookup"><span data-stu-id="b1443-102">LessThanL function</span></span>

<span data-ttu-id="b1443-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="b1443-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="b1443-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b1443-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b1443-105">Restituisce true se e solo se un numero è minore di un altro numero.</span><span class="sxs-lookup"><span data-stu-id="b1443-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="b1443-106">Input</span><span class="sxs-lookup"><span data-stu-id="b1443-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="b1443-107">r: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b1443-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b1443-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="b1443-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="b1443-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b1443-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b1443-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="b1443-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="b1443-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b1443-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b1443-112">`true` Se e solo se `a` è strettamente inferiore a `b` .</span><span class="sxs-lookup"><span data-stu-id="b1443-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b1443-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="b1443-113">Remarks</span></span>

<span data-ttu-id="b1443-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="b1443-114">The following are equivalent:</span></span>

```qsharp
let cond = a < b;
let cond = LessThanL(a, b);
```