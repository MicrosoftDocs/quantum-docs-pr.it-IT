---
uid: Microsoft.Quantum.Logical.And
title: And (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: And
qsharp.summary: Returns the Boolean conjunction of two values.
ms.openlocfilehash: 6c405bdb4182cc7f32bd04952dec25a974c03445
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849236"
---
# <a name="and-function"></a><span data-ttu-id="109ad-102">And (funzione)</span><span class="sxs-lookup"><span data-stu-id="109ad-102">And function</span></span>

<span data-ttu-id="109ad-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="109ad-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="109ad-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="109ad-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="109ad-105">Restituisce la congiunzione booleana di due valori.</span><span class="sxs-lookup"><span data-stu-id="109ad-105">Returns the Boolean conjunction of two values.</span></span>

```qsharp
function And (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="109ad-106">Input</span><span class="sxs-lookup"><span data-stu-id="109ad-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="109ad-107">a: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="109ad-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="109ad-108">Primo valore da considerare.</span><span class="sxs-lookup"><span data-stu-id="109ad-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="109ad-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="109ad-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="109ad-110">Secondo valore da considerare.</span><span class="sxs-lookup"><span data-stu-id="109ad-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="109ad-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="109ad-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="109ad-112">`true` Se e solo se `a` e `b` sono entrambi `true` .</span><span class="sxs-lookup"><span data-stu-id="109ad-112">`true` if and only if `a` and `b` are both `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="109ad-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="109ad-113">Remarks</span></span>

<span data-ttu-id="109ad-114">A differenza dell' `and` operatore, questa funzione non è a corto circuito, in modo che entrambi gli input siano valutati completamente.</span><span class="sxs-lookup"><span data-stu-id="109ad-114">Unlike the `and` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="109ad-115">Fino a un comportamento di corto circuito, gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="109ad-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```qsharp
let x = a and b;
let x = And(a, b);
```