---
uid: Microsoft.Quantum.Logical.EqualL
title: Equall (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualL
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: f0a2bfa866068746e9c6e249573eb61c0d08c0f0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710041"
---
# <a name="equall-function"></a><span data-ttu-id="2f0e3-102">Equall (funzione)</span><span class="sxs-lookup"><span data-stu-id="2f0e3-102">EqualL function</span></span>

<span data-ttu-id="2f0e3-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="2f0e3-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="2f0e3-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2f0e3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2f0e3-105">Restituisce true se e solo se due input sono uguali.</span><span class="sxs-lookup"><span data-stu-id="2f0e3-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="2f0e3-106">Input</span><span class="sxs-lookup"><span data-stu-id="2f0e3-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="2f0e3-107">r: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="2f0e3-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="2f0e3-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="2f0e3-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="2f0e3-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="2f0e3-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="2f0e3-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="2f0e3-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="2f0e3-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2f0e3-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2f0e3-112">`true` Se e solo se `a` è uguale a `b` .</span><span class="sxs-lookup"><span data-stu-id="2f0e3-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="2f0e3-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="2f0e3-113">Remarks</span></span>

<span data-ttu-id="2f0e3-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="2f0e3-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualL(a, b);
```