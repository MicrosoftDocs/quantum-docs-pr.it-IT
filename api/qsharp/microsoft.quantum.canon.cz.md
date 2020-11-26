---
uid: Microsoft.Quantum.Canon.CZ
title: Operazione CZ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CZ
qsharp.summary: >-
  Applies the controlled-Z (CZ) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 419082dbf8f96a9fe2dfabeab77e1823cb59a8f2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207208"
---
# <a name="cz-operation"></a><span data-ttu-id="6617c-102">Operazione CZ</span><span class="sxs-lookup"><span data-stu-id="6617c-102">CZ operation</span></span>

<span data-ttu-id="6617c-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6617c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6617c-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6617c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6617c-105">Applica il Gate controllato Z (CZ) a una coppia di qubits.</span><span class="sxs-lookup"><span data-stu-id="6617c-105">Applies the controlled-Z (CZ) gate to a pair of qubits.</span></span>

<span data-ttu-id="6617c-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 0 & 0 &-1 \end{align}, $ $ dove le righe e le colonne sono organizzate come nella Guida ai concetti di Quantum.</span><span class="sxs-lookup"><span data-stu-id="6617c-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CZ (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="6617c-107">Input</span><span class="sxs-lookup"><span data-stu-id="6617c-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="6617c-108">controllo: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="6617c-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="6617c-109">Controllare qubit per il Gate CZ.</span><span class="sxs-lookup"><span data-stu-id="6617c-109">Control qubit for the CZ gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="6617c-110">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="6617c-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="6617c-111">Qubit di destinazione per il Gate CZ.</span><span class="sxs-lookup"><span data-stu-id="6617c-111">Target qubit for the CZ gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6617c-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6617c-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="6617c-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="6617c-113">Remarks</span></span>

<span data-ttu-id="6617c-114">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="6617c-114">Equivalent to:</span></span>

```qsharp
Controlled Z([control], target);
```