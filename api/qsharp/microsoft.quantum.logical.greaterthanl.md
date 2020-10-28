---
uid: Microsoft.Quantum.Logical.GreaterThanL
title: GreaterThanL (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanL
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 676defa7824e53578504c559c6d8f24b2ffc1a88
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711385"
---
# <a name="greaterthanl-function"></a><span data-ttu-id="eff14-102">GreaterThanL (funzione)</span><span class="sxs-lookup"><span data-stu-id="eff14-102">GreaterThanL function</span></span>

<span data-ttu-id="eff14-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="eff14-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="eff14-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="eff14-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="eff14-105">Restituisce true se e solo se un numero è maggiore di un altro numero.</span><span class="sxs-lookup"><span data-stu-id="eff14-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="eff14-106">Input</span><span class="sxs-lookup"><span data-stu-id="eff14-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="eff14-107">r: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="eff14-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="eff14-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="eff14-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="eff14-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="eff14-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="eff14-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="eff14-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="eff14-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="eff14-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="eff14-112">`true` Se e solo se `a` è strettamente maggiore di `b` .</span><span class="sxs-lookup"><span data-stu-id="eff14-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="eff14-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="eff14-113">Remarks</span></span>

<span data-ttu-id="eff14-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="eff14-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanL(a, b);
```