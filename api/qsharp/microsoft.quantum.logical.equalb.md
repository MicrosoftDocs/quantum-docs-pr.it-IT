---
uid: Microsoft.Quantum.Logical.EqualB
title: EqualB (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualB
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: b566f5ba8548eadeecf63a1e91956d936e7e9a20
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198470"
---
# <a name="equalb-function"></a><span data-ttu-id="26d5e-102">EqualB (funzione)</span><span class="sxs-lookup"><span data-stu-id="26d5e-102">EqualB function</span></span>

<span data-ttu-id="26d5e-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="26d5e-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="26d5e-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="26d5e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="26d5e-105">Restituisce true se e solo se due input sono uguali.</span><span class="sxs-lookup"><span data-stu-id="26d5e-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="26d5e-106">Input</span><span class="sxs-lookup"><span data-stu-id="26d5e-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="26d5e-107">a: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="26d5e-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="26d5e-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="26d5e-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="26d5e-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="26d5e-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="26d5e-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="26d5e-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="26d5e-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="26d5e-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="26d5e-112">`true` Se e solo se `a` è uguale a `b` .</span><span class="sxs-lookup"><span data-stu-id="26d5e-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="26d5e-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="26d5e-113">Remarks</span></span>

<span data-ttu-id="26d5e-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="26d5e-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualB(a, b);
```