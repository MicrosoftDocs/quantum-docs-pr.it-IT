---
uid: Microsoft.Quantum.Intrinsic.RFrac
title: Operazione RFrac
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: RFrac
qsharp.summary: >-
  Applies a rotation about the given Pauli axis by an angle specified as a dyadic fraction.

  \begin{align} R_{\mu}(n, k) \mathrel{:=} e^{i \pi n \sigma_{\mu} / 2^k}, \end{align} where $\mu \in \{I, X, Y, Z\}$.

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r".
ms.openlocfilehash: bd182ea50d747e07bb0f8051c5dbc128b7ff7674
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198640"
---
# <a name="rfrac-operation"></a><span data-ttu-id="216e0-102">Operazione RFrac</span><span class="sxs-lookup"><span data-stu-id="216e0-102">RFrac operation</span></span>

<span data-ttu-id="216e0-103">Spazio dei nomi: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="216e0-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="216e0-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="216e0-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="216e0-105">Applica una rotazione sull'asse di Pauli specificato da un angolo specificato come frazione diadico.</span><span class="sxs-lookup"><span data-stu-id="216e0-105">Applies a rotation about the given Pauli axis by an angle specified as a dyadic fraction.</span></span>

<span data-ttu-id="216e0-106">\begin{align} R_ {\mu} (n, k) \mathrel{: =} e ^ {i \Pi n \ sigma_ {\mu}/2 ^ k}, \end{align} dove $ \mu \In \{ i, X, Y, Z \} $.</span><span class="sxs-lookup"><span data-stu-id="216e0-106">\begin{align} R_{\mu}(n, k) \mathrel{:=} e^{i \pi n \sigma_{\mu} / 2^k}, \end{align} where $\mu \in \{I, X, Y, Z\}$.</span></span>

> [!WARNING]
> <span data-ttu-id="216e0-107">Questa operazione usa la convenzione di segno **opposto** da @"microsoft.quantum.intrinsic.r" .</span><span class="sxs-lookup"><span data-stu-id="216e0-107">This operation uses the **opposite** sign convention from @"microsoft.quantum.intrinsic.r".</span></span>

```qsharp
operation RFrac (pauli : Pauli, numerator : Int, power : Int, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="216e0-108">Input</span><span class="sxs-lookup"><span data-stu-id="216e0-108">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="216e0-109">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="216e0-109">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="216e0-110">Operatore Pauli da exponentiated per formare la rotazione.</span><span class="sxs-lookup"><span data-stu-id="216e0-110">Pauli operator to be exponentiated to form the rotation.</span></span>


### <a name="numerator--int"></a><span data-ttu-id="216e0-111">numeratore: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="216e0-111">numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="216e0-112">Numeratore nella rappresentazione della frazione diadico dell'angolo in base al quale deve essere ruotato qubit.</span><span class="sxs-lookup"><span data-stu-id="216e0-112">Numerator in the dyadic fraction representation of the angle by which the qubit is to be rotated.</span></span>


### <a name="power--int"></a><span data-ttu-id="216e0-113">Potenza: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="216e0-113">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="216e0-114">Potenza di due che specifica il denominatore dell'angolo in base al quale deve essere ruotato il qubit.</span><span class="sxs-lookup"><span data-stu-id="216e0-114">Power of two specifying the denominator of the angle by which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="216e0-115">Qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="216e0-115">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="216e0-116">Qubit a cui deve essere applicato il controllo.</span><span class="sxs-lookup"><span data-stu-id="216e0-116">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="216e0-117">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="216e0-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="216e0-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="216e0-118">Remarks</span></span>

<span data-ttu-id="216e0-119">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="216e0-119">Equivalent to:</span></span>

```qsharp
// PI() is a Q# function that returns an approximation of π.
R(pauli, -PI() * IntAsDouble(numerator) / IntAsDouble(2 ^ (power - 1)), qubit);
```