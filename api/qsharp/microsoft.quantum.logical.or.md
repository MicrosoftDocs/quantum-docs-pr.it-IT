---
uid: Microsoft.Quantum.Logical.Or
title: Funzione or
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Or
qsharp.summary: Returns the Boolean disjunction of two values.
ms.openlocfilehash: 4a29b7684b28b904b43ccceb8e63280999690349
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848471"
---
# <a name="or-function"></a><span data-ttu-id="c6129-102">Funzione or</span><span class="sxs-lookup"><span data-stu-id="c6129-102">Or function</span></span>

<span data-ttu-id="c6129-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="c6129-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="c6129-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c6129-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c6129-105">Restituisce la disgiunzione booleana di due valori.</span><span class="sxs-lookup"><span data-stu-id="c6129-105">Returns the Boolean disjunction of two values.</span></span>

```qsharp
function Or (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="c6129-106">Input</span><span class="sxs-lookup"><span data-stu-id="c6129-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="c6129-107">a: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c6129-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c6129-108">Primo valore da considerare.</span><span class="sxs-lookup"><span data-stu-id="c6129-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="c6129-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c6129-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c6129-110">Secondo valore da considerare.</span><span class="sxs-lookup"><span data-stu-id="c6129-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c6129-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c6129-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c6129-112">`true` Se e solo se `a` o `b` sono `true` .</span><span class="sxs-lookup"><span data-stu-id="c6129-112">`true` if and only if either `a` or `b` are `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c6129-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="c6129-113">Remarks</span></span>

<span data-ttu-id="c6129-114">A differenza dell' `or` operatore, questa funzione non è a corto circuito, in modo che entrambi gli input siano valutati completamente.</span><span class="sxs-lookup"><span data-stu-id="c6129-114">Unlike the `or` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="c6129-115">Fino a un comportamento di corto circuito, gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="c6129-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```qsharp
let x = a or b;
let x = Or(a, b);
```