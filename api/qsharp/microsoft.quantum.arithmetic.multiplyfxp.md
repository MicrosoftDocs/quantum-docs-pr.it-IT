---
uid: Microsoft.Quantum.Arithmetic.MultiplyFxP
title: Operazione MultiplyFxP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyFxP
qsharp.summary: Multiplies two fixed-point numbers in quantum registers.
ms.openlocfilehash: 776ccb7a9e1ba1a34b28da6e1cf3a0aafe9da76b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843042"
---
# <a name="multiplyfxp-operation"></a><span data-ttu-id="5a25f-102">Operazione MultiplyFxP</span><span class="sxs-lookup"><span data-stu-id="5a25f-102">MultiplyFxP operation</span></span>

<span data-ttu-id="5a25f-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="5a25f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="5a25f-104">Pacchetto: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="5a25f-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="5a25f-105">Moltiplica due numeri a virgola fissa nei registri Quantum.</span><span class="sxs-lookup"><span data-stu-id="5a25f-105">Multiplies two fixed-point numbers in quantum registers.</span></span>

```qsharp
operation MultiplyFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5a25f-106">Input</span><span class="sxs-lookup"><span data-stu-id="5a25f-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="5a25f-107">FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="5a25f-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="5a25f-108">Primo numero a virgola fissa.</span><span class="sxs-lookup"><span data-stu-id="5a25f-108">First fixed-point number.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="5a25f-109">FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="5a25f-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="5a25f-110">Secondo numero a virgola fissa.</span><span class="sxs-lookup"><span data-stu-id="5a25f-110">Second fixed-point number.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="5a25f-111">risultato: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="5a25f-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="5a25f-112">Il numero a virgola fissa risultato deve trovarsi nello stato $ \ket {0} $ inizialmente.</span><span class="sxs-lookup"><span data-stu-id="5a25f-112">Result fixed-point number, must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5a25f-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5a25f-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5a25f-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="5a25f-114">Remarks</span></span>

<span data-ttu-id="5a25f-115">Per l'implementazione corrente è necessario che i tre numeri a virgola fissa abbiano la stessa posizione del punto e lo stesso numero di qubits.</span><span class="sxs-lookup"><span data-stu-id="5a25f-115">The current implementation requires the three fixed-point numbers to have the same point position and the same number of qubits.</span></span>