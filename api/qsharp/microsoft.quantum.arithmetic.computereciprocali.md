---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalI
title: Operazione ComputeReciprocalI
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalI
qsharp.summary: Computes the reciprocal 1/x for an unsigned integer x using integer division. The result, interpreted as an integer, will be `floor(2^(2*n-1) / x)`.
ms.openlocfilehash: c28027f7a2533885102a54a028bec37eb608f2b4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846714"
---
# <a name="computereciprocali-operation"></a><span data-ttu-id="a54e8-102">Operazione ComputeReciprocalI</span><span class="sxs-lookup"><span data-stu-id="a54e8-102">ComputeReciprocalI operation</span></span>

<span data-ttu-id="a54e8-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a54e8-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a54e8-104">Pacchetto: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="a54e8-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="a54e8-105">Calcola il reciproco 1/x per un Unsigned Integer x usando la divisione di interi.</span><span class="sxs-lookup"><span data-stu-id="a54e8-105">Computes the reciprocal 1/x for an unsigned integer x using integer division.</span></span> <span data-ttu-id="a54e8-106">Il risultato, interpretato come un numero intero, sarà `floor(2^(2*n-1) / x)` .</span><span class="sxs-lookup"><span data-stu-id="a54e8-106">The result, interpreted as an integer, will be `floor(2^(2*n-1) / x)`.</span></span>

```qsharp
operation ComputeReciprocalI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a54e8-107">Input</span><span class="sxs-lookup"><span data-stu-id="a54e8-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="a54e8-108">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a54e8-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a54e8-109">Unsigned Integer a n bit</span><span class="sxs-lookup"><span data-stu-id="a54e8-109">n-bit unsigned integer</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="a54e8-110">risultato: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a54e8-110">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a54e8-111">l'output a 2n bit deve essere inizialmente in $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="a54e8-111">2n-bit output, must be in $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a54e8-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a54e8-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a54e8-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="a54e8-113">Remarks</span></span>

<span data-ttu-id="a54e8-114">Per l'input x = 0, l'output sarà tutti quelli.</span><span class="sxs-lookup"><span data-stu-id="a54e8-114">For the input x=0, the output will be all-ones.</span></span>