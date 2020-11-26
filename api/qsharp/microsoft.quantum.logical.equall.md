---
uid: Microsoft.Quantum.Logical.EqualL
title: Equall (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualL
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 395b8fedd3b3334939c2a4b5602ee19e0c6e34b0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198113"
---
# <a name="equall-function"></a><span data-ttu-id="c76e9-102">Equall (funzione)</span><span class="sxs-lookup"><span data-stu-id="c76e9-102">EqualL function</span></span>

<span data-ttu-id="c76e9-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="c76e9-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="c76e9-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c76e9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c76e9-105">Restituisce true se e solo se due input sono uguali.</span><span class="sxs-lookup"><span data-stu-id="c76e9-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="c76e9-106">Input</span><span class="sxs-lookup"><span data-stu-id="c76e9-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="c76e9-107">r: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c76e9-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c76e9-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="c76e9-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="c76e9-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c76e9-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c76e9-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="c76e9-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c76e9-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c76e9-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c76e9-112">`true` Se e solo se `a` è uguale a `b` .</span><span class="sxs-lookup"><span data-stu-id="c76e9-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c76e9-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="c76e9-113">Remarks</span></span>

<span data-ttu-id="c76e9-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="c76e9-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualL(a, b);
```