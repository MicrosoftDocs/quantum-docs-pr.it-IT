---
uid: Microsoft.Quantum.Logical.LessThanOrEqualL
title: LessThanOrEqualL (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualL
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 333b76fc4885104e107dd25003a4e0dd5a9dd4af
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709918"
---
# <a name="lessthanorequall-function"></a><span data-ttu-id="49073-102">LessThanOrEqualL (funzione)</span><span class="sxs-lookup"><span data-stu-id="49073-102">LessThanOrEqualL function</span></span>

<span data-ttu-id="49073-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="49073-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="49073-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="49073-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="49073-105">Restituisce true se e solo se un numero è minore o uguale a un altro numero.</span><span class="sxs-lookup"><span data-stu-id="49073-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="49073-106">Input</span><span class="sxs-lookup"><span data-stu-id="49073-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="49073-107">r: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="49073-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="49073-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="49073-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="49073-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="49073-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="49073-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="49073-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="49073-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="49073-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="49073-112">`true` Se e solo se `a` è minore o uguale a `b` .</span><span class="sxs-lookup"><span data-stu-id="49073-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="49073-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="49073-113">Remarks</span></span>

<span data-ttu-id="49073-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="49073-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualL(a, b);
```