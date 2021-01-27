---
uid: Microsoft.Quantum.Logical.NotEqualR
title: NotEqualR (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 39601396a75d8c1b9193d4b8f34fa05466beff06
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848509"
---
# <a name="notequalr-function"></a><span data-ttu-id="855db-102">NotEqualR (funzione)</span><span class="sxs-lookup"><span data-stu-id="855db-102">NotEqualR function</span></span>

<span data-ttu-id="855db-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="855db-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="855db-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="855db-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="855db-105">Restituisce true se e solo se due input non sono uguali.</span><span class="sxs-lookup"><span data-stu-id="855db-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="855db-106">Input</span><span class="sxs-lookup"><span data-stu-id="855db-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="855db-107">r: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="855db-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="855db-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="855db-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="855db-109">b: __non <Result> valida__</span><span class="sxs-lookup"><span data-stu-id="855db-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="855db-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="855db-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="855db-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="855db-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="855db-112">`true` Se e solo se `a` non è uguale a `b` .</span><span class="sxs-lookup"><span data-stu-id="855db-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="855db-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="855db-113">Remarks</span></span>

<span data-ttu-id="855db-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="855db-114">The following are equivalent:</span></span>

```qsharp
let cond = a != b;
let cond = NotEqualR(a, b);
```