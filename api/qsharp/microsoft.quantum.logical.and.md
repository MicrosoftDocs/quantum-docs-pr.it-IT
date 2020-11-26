---
uid: Microsoft.Quantum.Logical.And
title: And (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: And
qsharp.summary: Returns the Boolean conjunction of two values.
ms.openlocfilehash: 279221ed785dd76e28146e4c22e70290936bf529
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198572"
---
# <a name="and-function"></a><span data-ttu-id="03b4c-102">And (funzione)</span><span class="sxs-lookup"><span data-stu-id="03b4c-102">And function</span></span>

<span data-ttu-id="03b4c-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="03b4c-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="03b4c-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="03b4c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="03b4c-105">Restituisce la congiunzione booleana di due valori.</span><span class="sxs-lookup"><span data-stu-id="03b4c-105">Returns the Boolean conjunction of two values.</span></span>

```qsharp
function And (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="03b4c-106">Input</span><span class="sxs-lookup"><span data-stu-id="03b4c-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="03b4c-107">a: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="03b4c-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="03b4c-108">Primo valore da considerare.</span><span class="sxs-lookup"><span data-stu-id="03b4c-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="03b4c-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="03b4c-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="03b4c-110">Secondo valore da considerare.</span><span class="sxs-lookup"><span data-stu-id="03b4c-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="03b4c-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="03b4c-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="03b4c-112">`true` Se e solo se `a` e `b` sono entrambi `true` .</span><span class="sxs-lookup"><span data-stu-id="03b4c-112">`true` if and only if `a` and `b` are both `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="03b4c-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="03b4c-113">Remarks</span></span>

<span data-ttu-id="03b4c-114">A differenza dell' `and` operatore, questa funzione non è a corto circuito, in modo che entrambi gli input siano valutati completamente.</span><span class="sxs-lookup"><span data-stu-id="03b4c-114">Unlike the `and` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="03b4c-115">Fino a un comportamento di corto circuito, gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="03b4c-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = a and b;
let x = And(a, b);
```