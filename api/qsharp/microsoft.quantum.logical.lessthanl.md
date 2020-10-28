---
uid: Microsoft.Quantum.Logical.LessThanL
title: LessThanL (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanL
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: fde57bcd9960056461bddac54300c298def8f7d5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709957"
---
# <a name="lessthanl-function"></a><span data-ttu-id="23783-102">LessThanL (funzione)</span><span class="sxs-lookup"><span data-stu-id="23783-102">LessThanL function</span></span>

<span data-ttu-id="23783-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="23783-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="23783-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="23783-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="23783-105">Restituisce true se e solo se un numero è minore di un altro numero.</span><span class="sxs-lookup"><span data-stu-id="23783-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="23783-106">Input</span><span class="sxs-lookup"><span data-stu-id="23783-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="23783-107">r: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="23783-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="23783-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="23783-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="23783-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="23783-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="23783-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="23783-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="23783-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="23783-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="23783-112">`true` Se e solo se `a` è strettamente inferiore a `b` .</span><span class="sxs-lookup"><span data-stu-id="23783-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="23783-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="23783-113">Remarks</span></span>

<span data-ttu-id="23783-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="23783-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanL(a, b);
```