---
uid: Microsoft.Quantum.Logical.Or
title: Funzione or
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Or
qsharp.summary: Returns the Boolean disjunction of two values.
ms.openlocfilehash: 7093d908696a8cfda6b5ef648f9dfafcfac97144
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197127"
---
# <a name="or-function"></a><span data-ttu-id="f0538-102">Funzione or</span><span class="sxs-lookup"><span data-stu-id="f0538-102">Or function</span></span>

<span data-ttu-id="f0538-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="f0538-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="f0538-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f0538-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f0538-105">Restituisce la disgiunzione booleana di due valori.</span><span class="sxs-lookup"><span data-stu-id="f0538-105">Returns the Boolean disjunction of two values.</span></span>

```qsharp
function Or (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="f0538-106">Input</span><span class="sxs-lookup"><span data-stu-id="f0538-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="f0538-107">a: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f0538-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f0538-108">Primo valore da considerare.</span><span class="sxs-lookup"><span data-stu-id="f0538-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="f0538-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f0538-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f0538-110">Secondo valore da considerare.</span><span class="sxs-lookup"><span data-stu-id="f0538-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="f0538-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f0538-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f0538-112">`true` Se e solo se `a` o `b` sono `true` .</span><span class="sxs-lookup"><span data-stu-id="f0538-112">`true` if and only if either `a` or `b` are `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f0538-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="f0538-113">Remarks</span></span>

<span data-ttu-id="f0538-114">A differenza dell' `or` operatore, questa funzione non è a corto circuito, in modo che entrambi gli input siano valutati completamente.</span><span class="sxs-lookup"><span data-stu-id="f0538-114">Unlike the `or` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="f0538-115">Fino a un comportamento di corto circuito, gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="f0538-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = a or b;
let x = Or(a, b);
```