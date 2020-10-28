---
uid: Microsoft.Quantum.Canon.CZ
title: Operazione CZ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CZ
qsharp.summary: >-
  Applies the controlled-Z (CZ) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: bc38cd43a0dcaf7aea735ef6468a394e91c85593
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716344"
---
# <a name="cz-operation"></a><span data-ttu-id="d01f7-102">Operazione CZ</span><span class="sxs-lookup"><span data-stu-id="d01f7-102">CZ operation</span></span>

<span data-ttu-id="d01f7-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d01f7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d01f7-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d01f7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d01f7-105">Applica il Gate controllato Z (CZ) a una coppia di qubits.</span><span class="sxs-lookup"><span data-stu-id="d01f7-105">Applies the controlled-Z (CZ) gate to a pair of qubits.</span></span>

<span data-ttu-id="d01f7-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 0 & 0 &-1 \end{align}, $ $ dove le righe e le colonne sono organizzate come nella Guida ai concetti di Quantum.</span><span class="sxs-lookup"><span data-stu-id="d01f7-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CZ (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="d01f7-107">Input</span><span class="sxs-lookup"><span data-stu-id="d01f7-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="d01f7-108">controllo: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d01f7-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d01f7-109">Controllare qubit per il Gate CZ.</span><span class="sxs-lookup"><span data-stu-id="d01f7-109">Control qubit for the CZ gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="d01f7-110">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d01f7-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d01f7-111">Qubit di destinazione per il Gate CZ.</span><span class="sxs-lookup"><span data-stu-id="d01f7-111">Target qubit for the CZ gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d01f7-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d01f7-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d01f7-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="d01f7-113">Remarks</span></span>

<span data-ttu-id="d01f7-114">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="d01f7-114">Equivalent to:</span></span>

```qsharp
Controlled Z([control], target);
```