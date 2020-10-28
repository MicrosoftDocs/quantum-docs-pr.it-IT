---
uid: Microsoft.Quantum.Intrinsic.R1Frac
title: Operazione R1Frac
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R1Frac
qsharp.summary: >-
  Applies a rotation about the $\ket{1}$ state by an angle specified as a dyadic fraction.

  \begin{align} R_1(n, k) \mathrel{:=} \operatorname{diag}(1, e^{i \pi k / 2^n}). \end{align}

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r", and does not include the > factor of $1/ 2$ included by @"microsoft.quantum.intrinsic.r1".
ms.openlocfilehash: bfa6cd60eebd05feec8cfa2bf71e09dc0d02843a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720903"
---
# <a name="r1frac-operation"></a><span data-ttu-id="0df80-102">Operazione R1Frac</span><span class="sxs-lookup"><span data-stu-id="0df80-102">R1Frac operation</span></span>

<span data-ttu-id="0df80-103">Spazio dei nomi: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="0df80-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="0df80-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0df80-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0df80-105">Applica una rotazione sullo {1} stato di $ \ket $ da un angolo specificato come frazione diadico.</span><span class="sxs-lookup"><span data-stu-id="0df80-105">Applies a rotation about the $\ket{1}$ state by an angle specified as a dyadic fraction.</span></span>

<span data-ttu-id="0df80-106">\begin{align} R_1 (n, k) \mathrel{: =} \operatorname{diag} (1, e ^ {i \Pi k/2 ^ n}).</span><span class="sxs-lookup"><span data-stu-id="0df80-106">\begin{align} R_1(n, k) \mathrel{:=} \operatorname{diag}(1, e^{i \pi k / 2^n}).</span></span>
<span data-ttu-id="0df80-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="0df80-107">\end{align}</span></span>

> [!WARNING]
> <span data-ttu-id="0df80-108">Questa operazione usa la convenzione di segno **opposto** da @"microsoft.quantum.intrinsic.r" e non include il fattore di $1/2 $ incluso in @"microsoft.quantum.intrinsic.r1" .</span><span class="sxs-lookup"><span data-stu-id="0df80-108">This operation uses the **opposite** sign convention from @"microsoft.quantum.intrinsic.r", and does not include the factor of $1/ 2$ included by @"microsoft.quantum.intrinsic.r1".</span></span>

```qsharp
operation R1Frac (numerator : Int, power : Int, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="0df80-109">Input</span><span class="sxs-lookup"><span data-stu-id="0df80-109">Input</span></span>

### <a name="numerator--int"></a><span data-ttu-id="0df80-110">numeratore: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0df80-110">numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0df80-111">Numeratore nella rappresentazione della frazione diadico dell'angolo in base al quale deve essere ruotato qubit.</span><span class="sxs-lookup"><span data-stu-id="0df80-111">Numerator in the dyadic fraction representation of the angle by which the qubit is to be rotated.</span></span>


### <a name="power--int"></a><span data-ttu-id="0df80-112">Potenza: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0df80-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0df80-113">Potenza di due che specifica il denominatore dell'angolo in base al quale deve essere ruotato il qubit.</span><span class="sxs-lookup"><span data-stu-id="0df80-113">Power of two specifying the denominator of the angle by which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="0df80-114">Qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0df80-114">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="0df80-115">Qubit a cui deve essere applicato il controllo.</span><span class="sxs-lookup"><span data-stu-id="0df80-115">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0df80-116">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0df80-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="0df80-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="0df80-117">Remarks</span></span>

<span data-ttu-id="0df80-118">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="0df80-118">Equivalent to:</span></span>

```qsharp
RFrac(PauliZ, -numerator, denominator + 1, qubit);
RFrac(PauliI, numerator, denominator + 1, qubit);
```