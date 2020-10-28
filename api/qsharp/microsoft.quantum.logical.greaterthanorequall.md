---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualL
title: GreaterThanOrEqualL (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualL
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: a59a9eca2941a44a70ec5a379b146ac459390bd4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722645"
---
# <a name="greaterthanorequall-function"></a><span data-ttu-id="2f0a8-102">GreaterThanOrEqualL (funzione)</span><span class="sxs-lookup"><span data-stu-id="2f0a8-102">GreaterThanOrEqualL function</span></span>

<span data-ttu-id="2f0a8-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="2f0a8-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="2f0a8-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2f0a8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2f0a8-105">Restituisce true se e solo se un numero è maggiore o uguale a un altro numero.</span><span class="sxs-lookup"><span data-stu-id="2f0a8-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="2f0a8-106">Input</span><span class="sxs-lookup"><span data-stu-id="2f0a8-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="2f0a8-107">r: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="2f0a8-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="2f0a8-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="2f0a8-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="2f0a8-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="2f0a8-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="2f0a8-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="2f0a8-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="2f0a8-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2f0a8-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2f0a8-112">`true` Se e solo se `a` è maggiore di o è uguale a `b` .</span><span class="sxs-lookup"><span data-stu-id="2f0a8-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="2f0a8-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="2f0a8-113">Remarks</span></span>

<span data-ttu-id="2f0a8-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="2f0a8-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualL(a, b);
```