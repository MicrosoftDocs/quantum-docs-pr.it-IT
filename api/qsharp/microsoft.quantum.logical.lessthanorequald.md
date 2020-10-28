---
uid: Microsoft.Quantum.Logical.LessThanOrEqualD
title: LessThanOrEqualD (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualD
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 7b0e9da379bd67eb78a80e7a535a15dcb8ba85c7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709946"
---
# <a name="lessthanorequald-function"></a><span data-ttu-id="b9a9f-102">LessThanOrEqualD (funzione)</span><span class="sxs-lookup"><span data-stu-id="b9a9f-102">LessThanOrEqualD function</span></span>

<span data-ttu-id="b9a9f-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="b9a9f-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="b9a9f-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b9a9f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b9a9f-105">Restituisce true se e solo se un numero è minore o uguale a un altro numero.</span><span class="sxs-lookup"><span data-stu-id="b9a9f-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="b9a9f-106">Input</span><span class="sxs-lookup"><span data-stu-id="b9a9f-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="b9a9f-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b9a9f-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b9a9f-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="b9a9f-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="b9a9f-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b9a9f-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b9a9f-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="b9a9f-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="b9a9f-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b9a9f-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b9a9f-112">`true` Se e solo se `a` è minore o uguale a `b` .</span><span class="sxs-lookup"><span data-stu-id="b9a9f-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b9a9f-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="b9a9f-113">Remarks</span></span>

<span data-ttu-id="b9a9f-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="b9a9f-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualD(a, b);
```