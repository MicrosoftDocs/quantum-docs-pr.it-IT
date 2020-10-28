---
uid: Microsoft.Quantum.Logical.EqualB
title: EqualB (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualB
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 91ab51180018a9b95a2f9010477c0a24f3a54617
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720783"
---
# <a name="equalb-function"></a><span data-ttu-id="a397e-102">EqualB (funzione)</span><span class="sxs-lookup"><span data-stu-id="a397e-102">EqualB function</span></span>

<span data-ttu-id="a397e-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="a397e-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="a397e-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a397e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a397e-105">Restituisce true se e solo se due input sono uguali.</span><span class="sxs-lookup"><span data-stu-id="a397e-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="a397e-106">Input</span><span class="sxs-lookup"><span data-stu-id="a397e-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="a397e-107">a: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a397e-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a397e-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="a397e-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="a397e-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a397e-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a397e-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="a397e-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="a397e-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a397e-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a397e-112">`true` Se e solo se `a` è uguale a `b` .</span><span class="sxs-lookup"><span data-stu-id="a397e-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a397e-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="a397e-113">Remarks</span></span>

<span data-ttu-id="a397e-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="a397e-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualB(a, b);
```