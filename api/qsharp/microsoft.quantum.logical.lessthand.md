---
uid: Microsoft.Quantum.Logical.LessThanD
title: LessThanD (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanD
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 7135ed4b3414d143f5020496ae524bf89980a8a1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849165"
---
# <a name="lessthand-function"></a><span data-ttu-id="22a40-102">LessThanD (funzione)</span><span class="sxs-lookup"><span data-stu-id="22a40-102">LessThanD function</span></span>

<span data-ttu-id="22a40-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="22a40-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="22a40-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="22a40-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="22a40-105">Restituisce true se e solo se un numero è minore di un altro numero.</span><span class="sxs-lookup"><span data-stu-id="22a40-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="22a40-106">Input</span><span class="sxs-lookup"><span data-stu-id="22a40-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="22a40-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="22a40-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="22a40-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="22a40-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="22a40-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="22a40-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="22a40-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="22a40-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="22a40-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="22a40-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="22a40-112">`true` Se e solo se `a` è strettamente inferiore a `b` .</span><span class="sxs-lookup"><span data-stu-id="22a40-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="22a40-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="22a40-113">Remarks</span></span>

<span data-ttu-id="22a40-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="22a40-114">The following are equivalent:</span></span>

```qsharp
let cond = a < b;
let cond = LessThanD(a, b);
```