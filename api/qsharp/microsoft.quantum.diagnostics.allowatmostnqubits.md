---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNQubits
title: Operazione AllowAtMostNQubits
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNQubits
qsharp.summary: Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.
ms.openlocfilehash: 5376b6f39d12d664342fbf71e67442c6ef8a0827
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202550"
---
# <a name="allowatmostnqubits-operation"></a><span data-ttu-id="ce150-102">Operazione AllowAtMostNQubits</span><span class="sxs-lookup"><span data-stu-id="ce150-102">AllowAtMostNQubits operation</span></span>

<span data-ttu-id="ce150-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="ce150-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="ce150-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ce150-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ce150-105">Tra una chiamata a questa operazione e la relativa contigua, asserisce che al massimo un determinato numero di qubits aggiuntivi viene allocato con istruzioni using.</span><span class="sxs-lookup"><span data-stu-id="ce150-105">Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.</span></span>

```qsharp
operation AllowAtMostNQubits (nQubits : Int, message : String) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="ce150-106">Input</span><span class="sxs-lookup"><span data-stu-id="ce150-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="ce150-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ce150-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ce150-108">Numero massimo di qubits che possono essere allocati.</span><span class="sxs-lookup"><span data-stu-id="ce150-108">The maximum number of qubits that may be allocated.</span></span>


### <a name="message--string"></a><span data-ttu-id="ce150-109">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="ce150-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="ce150-110">Messaggio da visualizzare in caso di errore.</span><span class="sxs-lookup"><span data-stu-id="ce150-110">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ce150-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ce150-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ce150-112">Commenti</span><span class="sxs-lookup"><span data-stu-id="ce150-112">Remarks</span></span>

<span data-ttu-id="ce150-113">Questa operazione può essere sostituita da un no-op sulle destinazioni che non lo supportano.</span><span class="sxs-lookup"><span data-stu-id="ce150-113">This operation may be replaced by a no-op on targets which do not support it.</span></span>