---
uid: Microsoft.Quantum.Logical.EqualD
title: Equald (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualD
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: f8a24d7bfb9b4f7b8b0e1f68a94bfb341716b024
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98816876"
---
# <a name="equald-function"></a><span data-ttu-id="dea15-102">Equald (funzione)</span><span class="sxs-lookup"><span data-stu-id="dea15-102">EqualD function</span></span>

<span data-ttu-id="dea15-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="dea15-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="dea15-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dea15-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dea15-105">Restituisce true se e solo se due input sono uguali.</span><span class="sxs-lookup"><span data-stu-id="dea15-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="dea15-106">Input</span><span class="sxs-lookup"><span data-stu-id="dea15-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="dea15-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="dea15-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="dea15-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="dea15-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="dea15-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="dea15-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="dea15-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="dea15-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="dea15-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="dea15-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="dea15-112">`true` Se e solo se `a` è uguale a `b` .</span><span class="sxs-lookup"><span data-stu-id="dea15-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="dea15-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="dea15-113">Remarks</span></span>

<span data-ttu-id="dea15-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="dea15-114">The following are equivalent:</span></span>

```qsharp
let cond = a == b;
let cond = EqualD(a, b);
```