---
uid: Microsoft.Quantum.Logical.NotEqualI
title: NotEqualI (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualI
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: f88ae08f45c284f65151419c214705c74c3fadac
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814511"
---
# <a name="notequali-function"></a><span data-ttu-id="fa53b-102">NotEqualI (funzione)</span><span class="sxs-lookup"><span data-stu-id="fa53b-102">NotEqualI function</span></span>

<span data-ttu-id="fa53b-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="fa53b-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="fa53b-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fa53b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fa53b-105">Restituisce true se e solo se due input non sono uguali.</span><span class="sxs-lookup"><span data-stu-id="fa53b-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="fa53b-106">Input</span><span class="sxs-lookup"><span data-stu-id="fa53b-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="fa53b-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fa53b-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fa53b-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="fa53b-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="fa53b-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fa53b-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fa53b-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="fa53b-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="fa53b-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fa53b-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fa53b-112">`true` Se e solo se `a` non è uguale a `b` .</span><span class="sxs-lookup"><span data-stu-id="fa53b-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="fa53b-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="fa53b-113">Remarks</span></span>

<span data-ttu-id="fa53b-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="fa53b-114">The following are equivalent:</span></span>

```qsharp
let cond = a != b;
let cond = NotEqualI(a, b);
```