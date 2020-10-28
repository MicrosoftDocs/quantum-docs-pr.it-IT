---
uid: Microsoft.Quantum.Logical.NotEqualR
title: NotEqualR (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 06615c7ffb6aafc296077990dfca0ce25e1e00fa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709792"
---
# <a name="notequalr-function"></a><span data-ttu-id="3b09b-102">NotEqualR (funzione)</span><span class="sxs-lookup"><span data-stu-id="3b09b-102">NotEqualR function</span></span>

<span data-ttu-id="3b09b-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="3b09b-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="3b09b-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3b09b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3b09b-105">Restituisce true se e solo se due input non sono uguali.</span><span class="sxs-lookup"><span data-stu-id="3b09b-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="3b09b-106">Input</span><span class="sxs-lookup"><span data-stu-id="3b09b-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="3b09b-107">r: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="3b09b-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="3b09b-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="3b09b-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="3b09b-109">b: __non <Result> valida__</span><span class="sxs-lookup"><span data-stu-id="3b09b-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="3b09b-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="3b09b-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="3b09b-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3b09b-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3b09b-112">`true` Se e solo se `a` non è uguale a `b` .</span><span class="sxs-lookup"><span data-stu-id="3b09b-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="3b09b-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="3b09b-113">Remarks</span></span>

<span data-ttu-id="3b09b-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="3b09b-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualR(a, b);
```