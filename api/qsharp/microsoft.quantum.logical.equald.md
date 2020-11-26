---
uid: Microsoft.Quantum.Logical.EqualD
title: Equald (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualD
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: d6731b293ba402f5cd43591d3c2bcd258e8ebe32
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198147"
---
# <a name="equald-function"></a><span data-ttu-id="35668-102">Equald (funzione)</span><span class="sxs-lookup"><span data-stu-id="35668-102">EqualD function</span></span>

<span data-ttu-id="35668-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="35668-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="35668-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="35668-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="35668-105">Restituisce true se e solo se due input sono uguali.</span><span class="sxs-lookup"><span data-stu-id="35668-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="35668-106">Input</span><span class="sxs-lookup"><span data-stu-id="35668-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="35668-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="35668-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="35668-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="35668-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="35668-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="35668-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="35668-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="35668-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="35668-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="35668-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="35668-112">`true` Se e solo se `a` è uguale a `b` .</span><span class="sxs-lookup"><span data-stu-id="35668-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="35668-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="35668-113">Remarks</span></span>

<span data-ttu-id="35668-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="35668-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualD(a, b);
```