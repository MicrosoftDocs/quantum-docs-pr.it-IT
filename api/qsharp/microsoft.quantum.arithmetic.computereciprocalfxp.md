---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalFxP
title: Operazione ComputeReciprocalFxP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalFxP
qsharp.summary: Computes $1/x$ for a fixed-point number $x$.
ms.openlocfilehash: e8f31d82fc69a3d7f4b571c4a679255dffc28b7f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721251"
---
# <a name="computereciprocalfxp-operation"></a><span data-ttu-id="e0544-102">Operazione ComputeReciprocalFxP</span><span class="sxs-lookup"><span data-stu-id="e0544-102">ComputeReciprocalFxP operation</span></span>

<span data-ttu-id="e0544-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e0544-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e0544-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e0544-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e0544-105">Calcola $1/x $ per un numero a virgola fissa $x $.</span><span class="sxs-lookup"><span data-stu-id="e0544-105">Computes $1/x$ for a fixed-point number $x$.</span></span>

```qsharp
operation ComputeReciprocalFxP (x : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a><span data-ttu-id="e0544-106">Input</span><span class="sxs-lookup"><span data-stu-id="e0544-106">Input</span></span>

### <a name="x--fixedpoint"></a><span data-ttu-id="e0544-107">x: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="e0544-107">x : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="e0544-108">Numero a virgola fissa da invertire.</span><span class="sxs-lookup"><span data-stu-id="e0544-108">Fixed-point number to be inverted.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="e0544-109">risultato: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="e0544-109">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="e0544-110">Numero a virgola fissa che conterrà il risultato.</span><span class="sxs-lookup"><span data-stu-id="e0544-110">Fixed-point number that will hold the result.</span></span> <span data-ttu-id="e0544-111">Deve essere inizializzato su $ \ket{0.0} $.</span><span class="sxs-lookup"><span data-stu-id="e0544-111">Must be initialized to $\ket{0.0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e0544-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e0544-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

