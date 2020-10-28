---
uid: Microsoft.Quantum.Logical.NotEqualI
title: NotEqualI (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualI
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 68e0e105a6b3742ec11e80ff92c39578a786aa85
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709831"
---
# <a name="notequali-function"></a><span data-ttu-id="72081-102">NotEqualI (funzione)</span><span class="sxs-lookup"><span data-stu-id="72081-102">NotEqualI function</span></span>

<span data-ttu-id="72081-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="72081-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="72081-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="72081-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="72081-105">Restituisce true se e solo se due input non sono uguali.</span><span class="sxs-lookup"><span data-stu-id="72081-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="72081-106">Input</span><span class="sxs-lookup"><span data-stu-id="72081-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="72081-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="72081-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="72081-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="72081-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="72081-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="72081-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="72081-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="72081-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="72081-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="72081-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="72081-112">`true` Se e solo se `a` non è uguale a `b` .</span><span class="sxs-lookup"><span data-stu-id="72081-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="72081-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="72081-113">Remarks</span></span>

<span data-ttu-id="72081-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="72081-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualI(a, b);
```