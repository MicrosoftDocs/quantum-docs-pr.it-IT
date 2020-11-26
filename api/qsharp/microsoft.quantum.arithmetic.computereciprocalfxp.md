---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalFxP
title: Operazione ComputeReciprocalFxP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalFxP
qsharp.summary: Computes $1/x$ for a fixed-point number $x$.
ms.openlocfilehash: 3ca050d6ce9daaa10e14c2f12dd571398cf436b0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223392"
---
# <a name="computereciprocalfxp-operation"></a><span data-ttu-id="14b4d-102">Operazione ComputeReciprocalFxP</span><span class="sxs-lookup"><span data-stu-id="14b4d-102">ComputeReciprocalFxP operation</span></span>

<span data-ttu-id="14b4d-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="14b4d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="14b4d-104">Pacchetto: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="14b4d-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="14b4d-105">Calcola $1/x $ per un numero a virgola fissa $x $.</span><span class="sxs-lookup"><span data-stu-id="14b4d-105">Computes $1/x$ for a fixed-point number $x$.</span></span>

```qsharp
operation ComputeReciprocalFxP (x : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="14b4d-106">Input</span><span class="sxs-lookup"><span data-stu-id="14b4d-106">Input</span></span>

### <a name="x--fixedpoint"></a><span data-ttu-id="14b4d-107">x: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="14b4d-107">x : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="14b4d-108">Numero a virgola fissa da invertire.</span><span class="sxs-lookup"><span data-stu-id="14b4d-108">Fixed-point number to be inverted.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="14b4d-109">risultato: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="14b4d-109">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="14b4d-110">Numero a virgola fissa che conterrà il risultato.</span><span class="sxs-lookup"><span data-stu-id="14b4d-110">Fixed-point number that will hold the result.</span></span> <span data-ttu-id="14b4d-111">Deve essere inizializzato su $ \ket{0.0} $.</span><span class="sxs-lookup"><span data-stu-id="14b4d-111">Must be initialized to $\ket{0.0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="14b4d-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="14b4d-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

