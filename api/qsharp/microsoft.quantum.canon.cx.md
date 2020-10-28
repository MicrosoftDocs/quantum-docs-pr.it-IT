---
uid: Microsoft.Quantum.Canon.CX
title: Operazione CX
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CX
qsharp.summary: >-
  Applies the controlled-X (CX) gate to a pair of qubits.

  $$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: c430525b71ad4ef0812d90a8ff20c41a5d5b8708
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716372"
---
# <a name="cx-operation"></a><span data-ttu-id="cc09a-102">Operazione CX</span><span class="sxs-lookup"><span data-stu-id="cc09a-102">CX operation</span></span>

<span data-ttu-id="cc09a-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cc09a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cc09a-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cc09a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cc09a-105">Applica la porta controllata-X (CX) a una coppia di qubits.</span><span class="sxs-lookup"><span data-stu-id="cc09a-105">Applies the controlled-X (CX) gate to a pair of qubits.</span></span>

<span data-ttu-id="cc09a-106">$ $ \begin{align} \left (\begin{Matrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{Matrix}\right) \end{align}, $ $ dove le righe e le colonne sono organizzate come nella Guida ai concetti di Quantum.</span><span class="sxs-lookup"><span data-stu-id="cc09a-106">$$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CX (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="cc09a-107">Input</span><span class="sxs-lookup"><span data-stu-id="cc09a-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="cc09a-108">controllo: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="cc09a-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="cc09a-109">Controllare qubit per la barriera CX.</span><span class="sxs-lookup"><span data-stu-id="cc09a-109">Control qubit for the CX gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="cc09a-110">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="cc09a-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="cc09a-111">Qubit di destinazione per il controllo CX.</span><span class="sxs-lookup"><span data-stu-id="cc09a-111">Target qubit for the CX gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cc09a-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cc09a-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="cc09a-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="cc09a-113">Remarks</span></span>

<span data-ttu-id="cc09a-114">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="cc09a-114">Equivalent to:</span></span>

```qsharp
Controlled X([control], target);
```

<span data-ttu-id="cc09a-115">e a:</span><span class="sxs-lookup"><span data-stu-id="cc09a-115">and to:</span></span>

```qsharp
CNOT(control, target);
```