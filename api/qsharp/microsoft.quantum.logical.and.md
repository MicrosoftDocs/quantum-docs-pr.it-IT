---
uid: Microsoft.Quantum.Logical.And
title: And (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: And
qsharp.summary: Returns the Boolean conjunction of two values.
ms.openlocfilehash: cc81f650216c4db219a79c4fe89a42447a4e95b8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720798"
---
# <a name="and-function"></a><span data-ttu-id="fc5f5-102">And (funzione)</span><span class="sxs-lookup"><span data-stu-id="fc5f5-102">And function</span></span>

<span data-ttu-id="fc5f5-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="fc5f5-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="fc5f5-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fc5f5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fc5f5-105">Restituisce la congiunzione booleana di due valori.</span><span class="sxs-lookup"><span data-stu-id="fc5f5-105">Returns the Boolean conjunction of two values.</span></span>

```qsharp
function And (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="fc5f5-106">Input</span><span class="sxs-lookup"><span data-stu-id="fc5f5-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="fc5f5-107">a: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fc5f5-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fc5f5-108">Primo valore da considerare.</span><span class="sxs-lookup"><span data-stu-id="fc5f5-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="fc5f5-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fc5f5-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fc5f5-110">Secondo valore da considerare.</span><span class="sxs-lookup"><span data-stu-id="fc5f5-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="fc5f5-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fc5f5-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fc5f5-112">`true` Se e solo se `a` e `b` sono entrambi `true` .</span><span class="sxs-lookup"><span data-stu-id="fc5f5-112">`true` if and only if `a` and `b` are both `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="fc5f5-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="fc5f5-113">Remarks</span></span>

<span data-ttu-id="fc5f5-114">A differenza dell' `and` operatore, questa funzione non è a corto circuito, in modo che entrambi gli input siano valutati completamente.</span><span class="sxs-lookup"><span data-stu-id="fc5f5-114">Unlike the `and` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="fc5f5-115">Fino a un comportamento di corto circuito, gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="fc5f5-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = a and b;
let x = And(a, b);
```