---
uid: Microsoft.Quantum.Logical.GreaterThanD
title: GreaterThanD (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanD
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 20414e80e08993a18331a8f0b385a1e4cc1255b3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710002"
---
# <a name="greaterthand-function"></a><span data-ttu-id="030c4-102">GreaterThanD (funzione)</span><span class="sxs-lookup"><span data-stu-id="030c4-102">GreaterThanD function</span></span>

<span data-ttu-id="030c4-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="030c4-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="030c4-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="030c4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="030c4-105">Restituisce true se e solo se un numero è maggiore di un altro numero.</span><span class="sxs-lookup"><span data-stu-id="030c4-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="030c4-106">Input</span><span class="sxs-lookup"><span data-stu-id="030c4-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="030c4-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="030c4-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="030c4-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="030c4-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="030c4-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="030c4-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="030c4-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="030c4-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="030c4-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="030c4-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="030c4-112">`true` Se e solo se `a` è strettamente maggiore di `b` .</span><span class="sxs-lookup"><span data-stu-id="030c4-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="030c4-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="030c4-113">Remarks</span></span>

<span data-ttu-id="030c4-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="030c4-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanD(a, b);
```