---
uid: Microsoft.Quantum.Logical.EqualD
title: Equald (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualD
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 024ddee785a6a907b4a39d0eccc5990b4c5d5d83
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711399"
---
# <a name="equald-function"></a><span data-ttu-id="a1287-102">Equald (funzione)</span><span class="sxs-lookup"><span data-stu-id="a1287-102">EqualD function</span></span>

<span data-ttu-id="a1287-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="a1287-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="a1287-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a1287-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a1287-105">Restituisce true se e solo se due input sono uguali.</span><span class="sxs-lookup"><span data-stu-id="a1287-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="a1287-106">Input</span><span class="sxs-lookup"><span data-stu-id="a1287-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="a1287-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a1287-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a1287-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="a1287-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="a1287-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a1287-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a1287-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="a1287-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="a1287-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a1287-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a1287-112">`true` Se e solo se `a` è uguale a `b` .</span><span class="sxs-lookup"><span data-stu-id="a1287-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a1287-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="a1287-113">Remarks</span></span>

<span data-ttu-id="a1287-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="a1287-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualD(a, b);
```