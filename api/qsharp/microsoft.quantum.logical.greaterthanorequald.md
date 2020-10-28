---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualD
title: GreaterThanOrEqualD (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualD
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 9d794fa94c1ccbde4030c90198fd7c7654469876
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711374"
---
# <a name="greaterthanorequald-function"></a><span data-ttu-id="b34bd-102">GreaterThanOrEqualD (funzione)</span><span class="sxs-lookup"><span data-stu-id="b34bd-102">GreaterThanOrEqualD function</span></span>

<span data-ttu-id="b34bd-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="b34bd-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="b34bd-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b34bd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b34bd-105">Restituisce true se e solo se un numero è maggiore o uguale a un altro numero.</span><span class="sxs-lookup"><span data-stu-id="b34bd-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="b34bd-106">Input</span><span class="sxs-lookup"><span data-stu-id="b34bd-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="b34bd-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b34bd-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b34bd-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="b34bd-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="b34bd-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b34bd-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b34bd-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="b34bd-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="b34bd-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b34bd-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b34bd-112">`true` Se e solo se `a` è maggiore di o è uguale a `b` .</span><span class="sxs-lookup"><span data-stu-id="b34bd-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b34bd-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="b34bd-113">Remarks</span></span>

<span data-ttu-id="b34bd-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="b34bd-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualD(a, b);
```