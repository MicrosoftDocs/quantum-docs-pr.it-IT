---
uid: Microsoft.Quantum.Logical.GreaterThanI
title: GreaterThanI (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanI
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: ffd00d8086654a2d783a351fe254fb2ee35b9184
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709985"
---
# <a name="greaterthani-function"></a><span data-ttu-id="159d6-102">GreaterThanI (funzione)</span><span class="sxs-lookup"><span data-stu-id="159d6-102">GreaterThanI function</span></span>

<span data-ttu-id="159d6-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="159d6-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="159d6-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="159d6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="159d6-105">Restituisce true se e solo se un numero è maggiore di un altro numero.</span><span class="sxs-lookup"><span data-stu-id="159d6-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="159d6-106">Input</span><span class="sxs-lookup"><span data-stu-id="159d6-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="159d6-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="159d6-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="159d6-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="159d6-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="159d6-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="159d6-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="159d6-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="159d6-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="159d6-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="159d6-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="159d6-112">`true` Se e solo se `a` è strettamente maggiore di `b` .</span><span class="sxs-lookup"><span data-stu-id="159d6-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="159d6-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="159d6-113">Remarks</span></span>

<span data-ttu-id="159d6-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="159d6-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanI(a, b);
```