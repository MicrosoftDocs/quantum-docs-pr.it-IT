---
uid: Microsoft.Quantum.Logical.EqualI
title: Equali (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualI
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 87cf00ea8bb738cda30092b3d80940291beb1fb9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98816742"
---
# <a name="equali-function"></a><span data-ttu-id="52942-102">Equali (funzione)</span><span class="sxs-lookup"><span data-stu-id="52942-102">EqualI function</span></span>

<span data-ttu-id="52942-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="52942-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="52942-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="52942-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="52942-105">Restituisce true se e solo se due input sono uguali.</span><span class="sxs-lookup"><span data-stu-id="52942-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="52942-106">Input</span><span class="sxs-lookup"><span data-stu-id="52942-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="52942-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="52942-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="52942-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="52942-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="52942-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="52942-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="52942-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="52942-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="52942-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="52942-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="52942-112">`true` Se e solo se `a` è uguale a `b` .</span><span class="sxs-lookup"><span data-stu-id="52942-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="52942-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="52942-113">Remarks</span></span>

<span data-ttu-id="52942-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="52942-114">The following are equivalent:</span></span>

```qsharp
let cond = a == b;
let cond = EqualI(a, b);
```