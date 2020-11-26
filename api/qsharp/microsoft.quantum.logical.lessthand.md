---
uid: Microsoft.Quantum.Logical.LessThanD
title: LessThanD (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanD
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 40f059e49affbb1b5af7dc349f6ee53dfb357873
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197739"
---
# <a name="lessthand-function"></a><span data-ttu-id="9fe2e-102">LessThanD (funzione)</span><span class="sxs-lookup"><span data-stu-id="9fe2e-102">LessThanD function</span></span>

<span data-ttu-id="9fe2e-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="9fe2e-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="9fe2e-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9fe2e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9fe2e-105">Restituisce true se e solo se un numero è minore di un altro numero.</span><span class="sxs-lookup"><span data-stu-id="9fe2e-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="9fe2e-106">Input</span><span class="sxs-lookup"><span data-stu-id="9fe2e-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="9fe2e-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9fe2e-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9fe2e-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="9fe2e-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="9fe2e-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9fe2e-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9fe2e-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="9fe2e-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="9fe2e-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="9fe2e-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="9fe2e-112">`true` Se e solo se `a` è strettamente inferiore a `b` .</span><span class="sxs-lookup"><span data-stu-id="9fe2e-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="9fe2e-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="9fe2e-113">Remarks</span></span>

<span data-ttu-id="9fe2e-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="9fe2e-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanD(a, b);
```