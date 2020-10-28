---
uid: Microsoft.Quantum.Canon.CY
title: Operazione CY
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CY
qsharp.summary: >-
  Applies the controlled-Y (CY) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 291891457ff39cf7092d17aa1d900dd0d35d9cf8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716358"
---
# <a name="cy-operation"></a><span data-ttu-id="a8d73-102">Operazione CY</span><span class="sxs-lookup"><span data-stu-id="a8d73-102">CY operation</span></span>

<span data-ttu-id="a8d73-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a8d73-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a8d73-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a8d73-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a8d73-105">Applica il controllo CY (controllata-Y) a una coppia di qubits.</span><span class="sxs-lookup"><span data-stu-id="a8d73-105">Applies the controlled-Y (CY) gate to a pair of qubits.</span></span>

<span data-ttu-id="a8d73-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 &-i \\ \\ 0 & 0 & i & 0 \end{align}, $ $ dove le righe e le colonne sono organizzate come nella Guida ai concetti di Quantum.</span><span class="sxs-lookup"><span data-stu-id="a8d73-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CY (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="a8d73-107">Input</span><span class="sxs-lookup"><span data-stu-id="a8d73-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="a8d73-108">controllo: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a8d73-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a8d73-109">Controllare qubit per la barriera CY.</span><span class="sxs-lookup"><span data-stu-id="a8d73-109">Control qubit for the CY gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="a8d73-110">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a8d73-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a8d73-111">Qubit di destinazione per il controllo CY.</span><span class="sxs-lookup"><span data-stu-id="a8d73-111">Target qubit for the CY gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a8d73-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a8d73-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a8d73-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="a8d73-113">Remarks</span></span>

<span data-ttu-id="a8d73-114">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="a8d73-114">Equivalent to:</span></span>

```qsharp
Controlled Y([control], target);
```