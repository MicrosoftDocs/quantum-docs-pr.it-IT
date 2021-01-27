---
uid: Microsoft.Quantum.Intrinsic.SWAP
title: Operazione di scambio
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: SWAP
qsharp.summary: >-
  Applies the SWAP gate to a pair of qubits.

  \begin{align} \operatorname{SWAP} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix}, \end{align}

  where rows and columns are ordered as in the quantum concepts guide.
ms.openlocfilehash: 4d8d037404ac835a1dd032790e7fd03f29591c41
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849263"
---
# <a name="swap-operation"></a><span data-ttu-id="5a22d-102">Operazione di scambio</span><span class="sxs-lookup"><span data-stu-id="5a22d-102">SWAP operation</span></span>

<span data-ttu-id="5a22d-103">Spazio dei nomi: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="5a22d-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="5a22d-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="5a22d-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="5a22d-105">Applica lo SWAP Gate a una coppia di qubits.</span><span class="sxs-lookup"><span data-stu-id="5a22d-105">Applies the SWAP gate to a pair of qubits.</span></span>

<span data-ttu-id="5a22d-106">\begin{align} \operatorname{SWAP} \mathrel{: =} \begin{Bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \end{Bmatrix}, \end{align}</span><span class="sxs-lookup"><span data-stu-id="5a22d-106">\begin{align} \operatorname{SWAP} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix}, \end{align}</span></span>

<span data-ttu-id="5a22d-107">dove righe e colonne vengono ordinate come nella Guida ai concetti di Quantum.</span><span class="sxs-lookup"><span data-stu-id="5a22d-107">where rows and columns are ordered as in the quantum concepts guide.</span></span>

```qsharp
operation SWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5a22d-108">Input</span><span class="sxs-lookup"><span data-stu-id="5a22d-108">Input</span></span>

### <a name="qubit1--qubit"></a><span data-ttu-id="5a22d-109">qubit1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="5a22d-109">qubit1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="5a22d-110">Primo qubit da scambiare.</span><span class="sxs-lookup"><span data-stu-id="5a22d-110">First qubit to be swapped.</span></span>


### <a name="qubit2--qubit"></a><span data-ttu-id="5a22d-111">qubit2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="5a22d-111">qubit2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="5a22d-112">Secondo qubit da scambiare.</span><span class="sxs-lookup"><span data-stu-id="5a22d-112">Second qubit to be swapped.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5a22d-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5a22d-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5a22d-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="5a22d-114">Remarks</span></span>

<span data-ttu-id="5a22d-115">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="5a22d-115">Equivalent to:</span></span>

```qsharp
CNOT(qubit1, qubit2);
CNOT(qubit2, qubit1);
CNOT(qubit1, qubit2);
```