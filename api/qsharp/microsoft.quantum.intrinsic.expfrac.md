---
uid: Microsoft.Quantum.Intrinsic.ExpFrac
title: Operazione ExpFrac
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ExpFrac
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator with an argument given by a dyadic fraction.

  \begin{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: d11912a272387b087098f59e7ac071534b01c054
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711486"
---
# <a name="expfrac-operation"></a><span data-ttu-id="cec16-102">Operazione ExpFrac</span><span class="sxs-lookup"><span data-stu-id="cec16-102">ExpFrac operation</span></span>

<span data-ttu-id="cec16-103">Spazio dei nomi: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="cec16-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="cec16-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cec16-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cec16-105">Applica il valore esponenziale di un operatore qubit di Pauli con un argomento fornito da una frazione diadico.</span><span class="sxs-lookup"><span data-stu-id="cec16-105">Applies the exponential of a multi-qubit Pauli operator with an argument given by a dyadic fraction.</span></span>

<span data-ttu-id="cec16-106">\begin{align} e ^ {i \Pi k [P_0 \otimes P_1 \cdots P_ {N-1}]/2 ^ N}, \end{align} dove $P _i $ è l'elemento $i $ th di `paulis` e dove $N = $ `Length(paulis)` .</span><span class="sxs-lookup"><span data-stu-id="cec16-106">\begin{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.</span></span>

```qsharp
operation ExpFrac (paulis : Pauli[], numerator : Int, power : Int, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="cec16-107">Input</span><span class="sxs-lookup"><span data-stu-id="cec16-107">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="cec16-108">Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="cec16-108">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="cec16-109">Matrice di valori Pauli Single-qubit che indicano i fattori del prodotto tensore in ogni qubit.</span><span class="sxs-lookup"><span data-stu-id="cec16-109">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="numerator--int"></a><span data-ttu-id="cec16-110">numeratore: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cec16-110">numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cec16-111">Numeratore ($k $) nella rappresentazione della frazione diadico dell'angolo in base al quale deve essere ruotato il registro qubit.</span><span class="sxs-lookup"><span data-stu-id="cec16-111">Numerator ($k$) in the dyadic fraction representation of the angle by which the qubit register is to be rotated.</span></span>


### <a name="power--int"></a><span data-ttu-id="cec16-112">Potenza: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cec16-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cec16-113">Potenza di due ($n $) che specifica il denominatore dell'angolo in base al quale deve essere ruotato il registro qubit.</span><span class="sxs-lookup"><span data-stu-id="cec16-113">Power of two ($n$) specifying the denominator of the angle by which the qubit register is to be rotated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="cec16-114">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="cec16-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="cec16-115">Eseguire la registrazione per applicare la rotazione specificata a.</span><span class="sxs-lookup"><span data-stu-id="cec16-115">Register to apply the given rotation to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cec16-116">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cec16-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

