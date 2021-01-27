---
uid: Microsoft.Quantum.Logical.EqualL
title: Equall (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualL
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 58086f40ea20b6f1a5fa6996e3a6703e2bf66306
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815981"
---
# <a name="equall-function"></a><span data-ttu-id="c9bee-102">Equall (funzione)</span><span class="sxs-lookup"><span data-stu-id="c9bee-102">EqualL function</span></span>

<span data-ttu-id="c9bee-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="c9bee-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="c9bee-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c9bee-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c9bee-105">Restituisce true se e solo se due input sono uguali.</span><span class="sxs-lookup"><span data-stu-id="c9bee-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="c9bee-106">Input</span><span class="sxs-lookup"><span data-stu-id="c9bee-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="c9bee-107">r: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c9bee-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c9bee-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="c9bee-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="c9bee-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c9bee-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c9bee-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="c9bee-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c9bee-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c9bee-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c9bee-112">`true` Se e solo se `a` è uguale a `b` .</span><span class="sxs-lookup"><span data-stu-id="c9bee-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c9bee-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="c9bee-113">Remarks</span></span>

<span data-ttu-id="c9bee-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="c9bee-114">The following are equivalent:</span></span>

```qsharp
let cond = a == b;
let cond = EqualL(a, b);
```