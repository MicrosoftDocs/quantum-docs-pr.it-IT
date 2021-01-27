---
uid: Microsoft.Quantum.Intrinsic.CNOT
title: Operazione CNOT
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CNOT
qsharp.summary: >-
  Applies the controlled-NOT (CNOT) gate to a pair of qubits.

  \begin{align} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}

  where rows and columns are ordered as in the quantum concepts guide.
ms.openlocfilehash: 02ae795c785dcbc25b56ac513a9237540e57ea63
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849445"
---
# <a name="cnot-operation"></a><span data-ttu-id="2a80c-102">Operazione CNOT</span><span class="sxs-lookup"><span data-stu-id="2a80c-102">CNOT operation</span></span>

<span data-ttu-id="2a80c-103">Spazio dei nomi: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="2a80c-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="2a80c-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="2a80c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="2a80c-105">Applica il controllo non controllato (CNOT) a una coppia di qubits.</span><span class="sxs-lookup"><span data-stu-id="2a80c-105">Applies the controlled-NOT (CNOT) gate to a pair of qubits.</span></span>

<span data-ttu-id="2a80c-106">\begin{align} \operatorname{CNOT} \mathrel{: =} \begin{Bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{Bmatrix}, \end{align}</span><span class="sxs-lookup"><span data-stu-id="2a80c-106">\begin{align} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}</span></span>

<span data-ttu-id="2a80c-107">dove righe e colonne vengono ordinate come nella Guida ai concetti di Quantum.</span><span class="sxs-lookup"><span data-stu-id="2a80c-107">where rows and columns are ordered as in the quantum concepts guide.</span></span>

```qsharp
operation CNOT (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="2a80c-108">Input</span><span class="sxs-lookup"><span data-stu-id="2a80c-108">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="2a80c-109">controllo: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2a80c-109">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2a80c-110">Controllare qubit per CNOT Gate.</span><span class="sxs-lookup"><span data-stu-id="2a80c-110">Control qubit for the CNOT gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="2a80c-111">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2a80c-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2a80c-112">Qubit di destinazione per CNOT Gate.</span><span class="sxs-lookup"><span data-stu-id="2a80c-112">Target qubit for the CNOT gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2a80c-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2a80c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2a80c-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="2a80c-114">Remarks</span></span>

<span data-ttu-id="2a80c-115">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="2a80c-115">Equivalent to:</span></span>

```qsharp
Controlled X([control], target);
```