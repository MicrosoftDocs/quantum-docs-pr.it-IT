---
uid: Microsoft.Quantum.Logical.NotNearlyEqualD
title: NotNearlyEqualD (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotNearlyEqualD
qsharp.summary: Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).
ms.openlocfilehash: d9e4cc5b0cfba3989ae64e494d0daa52069718a4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720726"
---
# <a name="notnearlyequald-function"></a><span data-ttu-id="18923-102">NotNearlyEqualD (funzione)</span><span class="sxs-lookup"><span data-stu-id="18923-102">NotNearlyEqualD function</span></span>

<span data-ttu-id="18923-103">Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="18923-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="18923-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="18923-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="18923-105">Restituisce true se e solo se due input non sono quasi uguali (ovvero, non sono compresi nella tolleranza di 1e-12).</span><span class="sxs-lookup"><span data-stu-id="18923-105">Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).</span></span>

```qsharp
function NotNearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="18923-106">Input</span><span class="sxs-lookup"><span data-stu-id="18923-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="18923-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="18923-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="18923-108">Primo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="18923-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="18923-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="18923-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="18923-110">Secondo valore da confrontare.</span><span class="sxs-lookup"><span data-stu-id="18923-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="18923-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="18923-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="18923-112">`true` Se e solo se `a` non è quasi uguale a `b` .</span><span class="sxs-lookup"><span data-stu-id="18923-112">`true` if and only if `a` is not nearly equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="18923-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="18923-113">Remarks</span></span>

<span data-ttu-id="18923-114">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="18923-114">The following are equivalent:</span></span>

```Q#
let cond = Microsoft.Quantum.Math.AbsD(a - b) >= 1e-12;
let cond = NotNearlyEqualD(a, b);
```