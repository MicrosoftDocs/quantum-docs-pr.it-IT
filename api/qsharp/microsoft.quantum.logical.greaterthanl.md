---
uid: Microsoft.Quantum.Logical.GreaterThanL
title: GreaterThanL (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanL
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 2247c1c1ae8b37b59e87c0c68b06fd1094c9003b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849208"
---
# <a name="greaterthanl-function"></a><span data-ttu-id="41c5d-102">GreaterThanL (funzione)</span><span class="sxs-lookup"><span data-stu-id="41c5d-102">GreaterThanL function</span></span>

<span data-ttu-id="41c5d-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="41c5d-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="41c5d-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="41c5d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="41c5d-105">Restituisce true se e solo se un numero è maggiore di un altro numero.</span><span class="sxs-lookup"><span data-stu-id="41c5d-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="41c5d-106">Input</span><span class="sxs-lookup"><span data-stu-id="41c5d-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="41c5d-107">r: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="41c5d-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="41c5d-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="41c5d-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="41c5d-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="41c5d-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="41c5d-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="41c5d-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="41c5d-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="41c5d-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="41c5d-112">`true` Se e solo se `a` è strettamente maggiore di `b` .</span><span class="sxs-lookup"><span data-stu-id="41c5d-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="41c5d-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="41c5d-113">Remarks</span></span>

<span data-ttu-id="41c5d-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="41c5d-114">The following are equivalent:</span></span>

```qsharp
let cond = a > b;
let cond = GreaterThanL(a, b);
```