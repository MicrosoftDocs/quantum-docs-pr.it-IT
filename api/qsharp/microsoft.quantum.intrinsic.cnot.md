---
uid: Microsoft.Quantum.Intrinsic.CNOT
title: Operazione CNOT
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CNOT
qsharp.summary: >-
  Applies the controlled-NOT (CNOT) gate to a pair of qubits.

  \begin{align} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}

  where rows and columns are ordered as in the quantum concepts guide.
ms.openlocfilehash: 2fb5b4df189fb3ab23b2ca5cb273b2451ffcc067
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722673"
---
# <a name="cnot-operation"></a><span data-ttu-id="96034-102">Operazione CNOT</span><span class="sxs-lookup"><span data-stu-id="96034-102">CNOT operation</span></span>

<span data-ttu-id="96034-103">Spazio dei nomi: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="96034-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="96034-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="96034-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="96034-105">Applica il controllo non controllato (CNOT) a una coppia di qubits.</span><span class="sxs-lookup"><span data-stu-id="96034-105">Applies the controlled-NOT (CNOT) gate to a pair of qubits.</span></span>

<span data-ttu-id="96034-106">\begin{align} \operatorname{CNOT} \mathrel{: =} \begin{Bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{Bmatrix}, \end{align}</span><span class="sxs-lookup"><span data-stu-id="96034-106">\begin{align} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}</span></span>

<span data-ttu-id="96034-107">dove righe e colonne vengono ordinate come nella Guida ai concetti di Quantum.</span><span class="sxs-lookup"><span data-stu-id="96034-107">where rows and columns are ordered as in the quantum concepts guide.</span></span>

```qsharp
operation CNOT (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="96034-108">Input</span><span class="sxs-lookup"><span data-stu-id="96034-108">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="96034-109">controllo: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="96034-109">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="96034-110">Controllare qubit per CNOT Gate.</span><span class="sxs-lookup"><span data-stu-id="96034-110">Control qubit for the CNOT gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="96034-111">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="96034-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="96034-112">Qubit di destinazione per CNOT Gate.</span><span class="sxs-lookup"><span data-stu-id="96034-112">Target qubit for the CNOT gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="96034-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="96034-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="96034-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="96034-114">Remarks</span></span>

<span data-ttu-id="96034-115">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="96034-115">Equivalent to:</span></span>

```qsharp
Controlled X([control], target);
```