---
uid: Microsoft.Quantum.Arithmetic.CompareGreaterThanFxP
title: Operazione CompareGreaterThanFxP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGreaterThanFxP
qsharp.summary: Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.
ms.openlocfilehash: f49c713c8a1e8a6451f2c54fa59a72f00bfbb4c4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843316"
---
# <a name="comparegreaterthanfxp-operation"></a><span data-ttu-id="172f3-102">Operazione CompareGreaterThanFxP</span><span class="sxs-lookup"><span data-stu-id="172f3-102">CompareGreaterThanFxP operation</span></span>

<span data-ttu-id="172f3-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="172f3-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="172f3-104">Pacchetto: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="172f3-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="172f3-105">Confronta due numeri a virgola fissa archiviati in registri Quantum e controlla un capovolgimento sul risultato.</span><span class="sxs-lookup"><span data-stu-id="172f3-105">Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.</span></span>

```qsharp
operation CompareGreaterThanFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="172f3-106">Input</span><span class="sxs-lookup"><span data-stu-id="172f3-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="172f3-107">FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="172f3-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="172f3-108">Primo numero a virgola fissa da confrontare.</span><span class="sxs-lookup"><span data-stu-id="172f3-108">First fixed-point number to be compared.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="172f3-109">FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="172f3-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="172f3-110">Secondo numero a virgola fissa da confrontare.</span><span class="sxs-lookup"><span data-stu-id="172f3-110">Second fixed-point number to be compared.</span></span>


### <a name="result--qubit"></a><span data-ttu-id="172f3-111">risultato: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="172f3-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="172f3-112">Risultato del confronto.</span><span class="sxs-lookup"><span data-stu-id="172f3-112">Result of the comparison.</span></span> <span data-ttu-id="172f3-113">Verrà capovolto se `fp1 > fp2` .</span><span class="sxs-lookup"><span data-stu-id="172f3-113">Will be flipped if `fp1 > fp2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="172f3-114">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="172f3-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="172f3-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="172f3-115">Remarks</span></span>

<span data-ttu-id="172f3-116">Per l'implementazione corrente è necessario che i due numeri a virgola fissa abbiano la stessa posizione del punto e lo stesso numero di qubits.</span><span class="sxs-lookup"><span data-stu-id="172f3-116">The current implementation requires the two fixed-point numbers to have the same point position and the same number of qubits.</span></span>