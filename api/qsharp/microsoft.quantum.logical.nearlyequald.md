---
uid: Microsoft.Quantum.Logical.NearlyEqualD
title: NearlyEqualD (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NearlyEqualD
qsharp.summary: Returns true if and only if two inputs are nearly equal (that is, within a tolerance of 1e-12).
ms.openlocfilehash: 246fad15c691a53fcc5be10f2c713672e0b54e6b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197467"
---
# <a name="nearlyequald-function"></a><span data-ttu-id="8b5ef-102">NearlyEqualD (funzione)</span><span class="sxs-lookup"><span data-stu-id="8b5ef-102">NearlyEqualD function</span></span>

<span data-ttu-id="8b5ef-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="8b5ef-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="8b5ef-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8b5ef-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8b5ef-105">Restituisce true se e solo se due input sono quasi uguali (ovvero, entro la tolleranza di 1e-12).</span><span class="sxs-lookup"><span data-stu-id="8b5ef-105">Returns true if and only if two inputs are nearly equal (that is, within a tolerance of 1e-12).</span></span>

```qsharp
function NearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="8b5ef-106">Input</span><span class="sxs-lookup"><span data-stu-id="8b5ef-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="8b5ef-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8b5ef-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8b5ef-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="8b5ef-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="8b5ef-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8b5ef-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8b5ef-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="8b5ef-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="8b5ef-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8b5ef-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8b5ef-112">`true` Se e solo se `a` è quasi uguale a `b` .</span><span class="sxs-lookup"><span data-stu-id="8b5ef-112">`true` if and only if `a` is nearly equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="8b5ef-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="8b5ef-113">Remarks</span></span>

<span data-ttu-id="8b5ef-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="8b5ef-114">The following are equivalent:</span></span>

```Q#
let cond = Microsoft.Quantum.Math.AbsD(a - b) < 1e-12;
let cond = NearlyEqualD(a, b);
```