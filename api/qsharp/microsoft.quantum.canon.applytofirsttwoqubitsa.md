---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA
title: Operazione ApplyToFirstTwoQubitsA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsA
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 1a286c167a87372dc89d62ab3733b186298c43a1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208704"
---
# <a name="applytofirsttwoqubitsa-operation"></a><span data-ttu-id="9d40f-102">Operazione ApplyToFirstTwoQubitsA</span><span class="sxs-lookup"><span data-stu-id="9d40f-102">ApplyToFirstTwoQubitsA operation</span></span>

<span data-ttu-id="9d40f-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9d40f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9d40f-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9d40f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9d40f-105">Applica un'operazione ai primi due qubits nel registro.</span><span class="sxs-lookup"><span data-stu-id="9d40f-105">Applies an operation to the first two qubits in the register.</span></span>
<span data-ttu-id="9d40f-106">Il modificatore `A` indica che l'operazione è adjointable.</span><span class="sxs-lookup"><span data-stu-id="9d40f-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToFirstTwoQubitsA (op : ((Qubit, Qubit) => Unit is Adj), register : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="9d40f-107">Input</span><span class="sxs-lookup"><span data-stu-id="9d40f-107">Input</span></span>

### <a name="op--qubitqubit--unit--is-adj"></a><span data-ttu-id="9d40f-108">op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ</span><span class="sxs-lookup"><span data-stu-id="9d40f-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="9d40f-109">Operazione da applicare ai primi due qubits</span><span class="sxs-lookup"><span data-stu-id="9d40f-109">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="9d40f-110">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9d40f-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9d40f-111">Matrice qubit per i primi due qubits di cui viene applicata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="9d40f-111">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9d40f-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9d40f-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9d40f-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="9d40f-113">Remarks</span></span>

<span data-ttu-id="9d40f-114">Equivale a:</span><span class="sxs-lookup"><span data-stu-id="9d40f-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="9d40f-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d40f-115">See Also</span></span>

- [<span data-ttu-id="9d40f-116">Microsoft. Quantum. Canon. ApplyToFirstTwoQubits</span><span class="sxs-lookup"><span data-stu-id="9d40f-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)