---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNQubits
title: Operazione AllowAtMostNQubits
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNQubits
qsharp.summary: Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.
ms.openlocfilehash: 3aa80767ac0f752e7be0efa2966c580ca3cb8f19
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830908"
---
# <a name="allowatmostnqubits-operation"></a><span data-ttu-id="6b1aa-102">Operazione AllowAtMostNQubits</span><span class="sxs-lookup"><span data-stu-id="6b1aa-102">AllowAtMostNQubits operation</span></span>

<span data-ttu-id="6b1aa-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="6b1aa-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="6b1aa-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6b1aa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6b1aa-105">Tra una chiamata a questa operazione e la relativa contigua, asserisce che al massimo un determinato numero di qubits aggiuntivi viene allocato con istruzioni using.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-105">Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.</span></span>

```qsharp
operation AllowAtMostNQubits (nQubits : Int, message : String) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="6b1aa-106">Input</span><span class="sxs-lookup"><span data-stu-id="6b1aa-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="6b1aa-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6b1aa-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6b1aa-108">Numero massimo di qubits che possono essere allocati.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-108">The maximum number of qubits that may be allocated.</span></span>


### <a name="message--string"></a><span data-ttu-id="6b1aa-109">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="6b1aa-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="6b1aa-110">Messaggio da visualizzare in caso di errore.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-110">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6b1aa-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6b1aa-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="6b1aa-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="6b1aa-112">Example</span></span>

<span data-ttu-id="6b1aa-113">Il frammento di codice seguente avrà esito negativo quando viene eseguito nei computer che supportano questa diagnostica:</span><span class="sxs-lookup"><span data-stu-id="6b1aa-113">The following snippet will fail when executed on machines which support this diagnostic:</span></span>

```qsharp
within {
    AllowAtMostNQubits(3, "Too many qubits allocated.");
} apply {
    // Fails since this allocates four qubits.
    using (register = Qubit[4]) {
    }
}
```

## <a name="remarks"></a><span data-ttu-id="6b1aa-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="6b1aa-114">Remarks</span></span>

<span data-ttu-id="6b1aa-115">Questa operazione può essere sostituita da un no-op sulle destinazioni che non lo supportano.</span><span class="sxs-lookup"><span data-stu-id="6b1aa-115">This operation may be replaced by a no-op on targets which do not support it.</span></span>