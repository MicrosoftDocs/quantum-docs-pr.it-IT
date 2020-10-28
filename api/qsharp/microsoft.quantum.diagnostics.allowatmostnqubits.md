---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNQubits
title: Operazione AllowAtMostNQubits
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNQubits
qsharp.summary: Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.
ms.openlocfilehash: ddbed96df0d95cfd78730c091a6a81ee6e49c349
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713054"
---
# <a name="allowatmostnqubits-operation"></a><span data-ttu-id="819e5-102">Operazione AllowAtMostNQubits</span><span class="sxs-lookup"><span data-stu-id="819e5-102">AllowAtMostNQubits operation</span></span>

<span data-ttu-id="819e5-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="819e5-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="819e5-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="819e5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="819e5-105">Tra una chiamata a questa operazione e la relativa contigua, asserisce che al massimo un determinato numero di qubits aggiuntivi viene allocato con istruzioni using.</span><span class="sxs-lookup"><span data-stu-id="819e5-105">Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.</span></span>

```qsharp
operation AllowAtMostNQubits (nQubits : Int, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="819e5-106">Input</span><span class="sxs-lookup"><span data-stu-id="819e5-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="819e5-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="819e5-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="819e5-108">Numero massimo di qubits che possono essere allocati.</span><span class="sxs-lookup"><span data-stu-id="819e5-108">The maximum number of qubits that may be allocated.</span></span>


### <a name="message--string"></a><span data-ttu-id="819e5-109">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="819e5-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="819e5-110">Messaggio da visualizzare in caso di errore.</span><span class="sxs-lookup"><span data-stu-id="819e5-110">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="819e5-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="819e5-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="819e5-112">Commenti</span><span class="sxs-lookup"><span data-stu-id="819e5-112">Remarks</span></span>

<span data-ttu-id="819e5-113">Questa operazione può essere sostituita da un no-op sulle destinazioni che non lo supportano.</span><span class="sxs-lookup"><span data-stu-id="819e5-113">This operation may be replaced by a no-op on targets which do not support it.</span></span>