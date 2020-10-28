---
uid: Microsoft.Quantum.Arithmetic.CompareGreaterThanFxP
title: Operazione CompareGreaterThanFxP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGreaterThanFxP
qsharp.summary: Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.
ms.openlocfilehash: bd3bcedd7a4a81fc600f7f4b6bdf1d2a797abbd4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721299"
---
# <a name="comparegreaterthanfxp-operation"></a><span data-ttu-id="d923e-102">Operazione CompareGreaterThanFxP</span><span class="sxs-lookup"><span data-stu-id="d923e-102">CompareGreaterThanFxP operation</span></span>

<span data-ttu-id="d923e-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d923e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d923e-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d923e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d923e-105">Confronta due numeri a virgola fissa archiviati in registri Quantum e controlla un capovolgimento sul risultato.</span><span class="sxs-lookup"><span data-stu-id="d923e-105">Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.</span></span>

```qsharp
operation CompareGreaterThanFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="d923e-106">Input</span><span class="sxs-lookup"><span data-stu-id="d923e-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="d923e-107">FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="d923e-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="d923e-108">Primo numero a virgola fissa da confrontare.</span><span class="sxs-lookup"><span data-stu-id="d923e-108">First fixed-point number to be compared.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="d923e-109">FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="d923e-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="d923e-110">Secondo numero a virgola fissa da confrontare.</span><span class="sxs-lookup"><span data-stu-id="d923e-110">Second fixed-point number to be compared.</span></span>


### <a name="result--qubit"></a><span data-ttu-id="d923e-111">risultato: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d923e-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d923e-112">Risultato del confronto.</span><span class="sxs-lookup"><span data-stu-id="d923e-112">Result of the comparison.</span></span> <span data-ttu-id="d923e-113">Verrà capovolto se `fp1 > fp2` .</span><span class="sxs-lookup"><span data-stu-id="d923e-113">Will be flipped if `fp1 > fp2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d923e-114">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d923e-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d923e-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="d923e-115">Remarks</span></span>

<span data-ttu-id="d923e-116">Per l'implementazione corrente è necessario che i due numeri a virgola fissa abbiano la stessa posizione del punto e lo stesso numero di qubits.</span><span class="sxs-lookup"><span data-stu-id="d923e-116">The current implementation requires the two fixed-point numbers to have the same point position and the same number of qubits.</span></span>