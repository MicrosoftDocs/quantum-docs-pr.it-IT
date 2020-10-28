---
uid: Microsoft.Quantum.Logical.EqualR
title: Equalr (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualR
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 5aaa17303d75b27c3ac82cbe7d739a60016fdcb1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710030"
---
# <a name="equalr-function"></a><span data-ttu-id="7bacc-102">Equalr (funzione)</span><span class="sxs-lookup"><span data-stu-id="7bacc-102">EqualR function</span></span>

<span data-ttu-id="7bacc-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="7bacc-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="7bacc-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7bacc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7bacc-105">Restituisce true se e solo se due input sono uguali.</span><span class="sxs-lookup"><span data-stu-id="7bacc-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="7bacc-106">Input</span><span class="sxs-lookup"><span data-stu-id="7bacc-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="7bacc-107">r: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="7bacc-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="7bacc-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="7bacc-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="7bacc-109">b: __non <Result> valida__</span><span class="sxs-lookup"><span data-stu-id="7bacc-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="7bacc-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="7bacc-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="7bacc-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7bacc-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7bacc-112">`true` Se e solo se `a` è uguale a `b` .</span><span class="sxs-lookup"><span data-stu-id="7bacc-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="7bacc-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="7bacc-113">Remarks</span></span>

<span data-ttu-id="7bacc-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="7bacc-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualR(a, b);
```