---
uid: Microsoft.Quantum.Intrinsic.Exp
title: Operazione exp
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Exp
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator.

  \begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: b923374a954f90aba2deaead79dd419fbf67fea3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711525"
---
# <a name="exp-operation"></a><span data-ttu-id="730f0-102">Operazione exp</span><span class="sxs-lookup"><span data-stu-id="730f0-102">Exp operation</span></span>

<span data-ttu-id="730f0-103">Spazio dei nomi: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="730f0-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="730f0-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="730f0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="730f0-105">Applica il valore esponenziale di un operatore qubit di Pauli.</span><span class="sxs-lookup"><span data-stu-id="730f0-105">Applies the exponential of a multi-qubit Pauli operator.</span></span>

<span data-ttu-id="730f0-106">\begin{align} e ^ {i \theta [P_0 \otimes P_1 \cdots P_ {N-1}]}, \end{align} dove $P _i $ è l'elemento $i $ th di `paulis` e dove $N = $ `Length(paulis)` .</span><span class="sxs-lookup"><span data-stu-id="730f0-106">\begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.</span></span>

```qsharp
operation Exp (paulis : Pauli[], theta : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="730f0-107">Input</span><span class="sxs-lookup"><span data-stu-id="730f0-107">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="730f0-108">Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="730f0-108">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="730f0-109">Matrice di valori Pauli Single-qubit che indicano i fattori del prodotto tensore in ogni qubit.</span><span class="sxs-lookup"><span data-stu-id="730f0-109">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="theta--double"></a><span data-ttu-id="730f0-110">Theta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="730f0-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="730f0-111">Angolo relativo all'operatore Pauli qubit specificato in base al quale deve essere ruotato il registro di destinazione.</span><span class="sxs-lookup"><span data-stu-id="730f0-111">Angle about the given multi-qubit Pauli operator by which the target register is to be rotated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="730f0-112">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="730f0-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="730f0-113">Eseguire la registrazione per applicare la rotazione specificata a.</span><span class="sxs-lookup"><span data-stu-id="730f0-113">Register to apply the given rotation to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="730f0-114">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="730f0-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

