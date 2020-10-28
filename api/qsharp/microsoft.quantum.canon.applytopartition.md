---
uid: Microsoft.Quantum.Canon.ApplyToPartition
title: Operazione ApplyToPartition
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartition
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts.
ms.openlocfilehash: c1f43e7936fc1c18fb665388e9892dc3b74cdd05
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717142"
---
# <a name="applytopartition-operation"></a><span data-ttu-id="8aae9-102">Operazione ApplyToPartition</span><span class="sxs-lookup"><span data-stu-id="8aae9-102">ApplyToPartition operation</span></span>

<span data-ttu-id="8aae9-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8aae9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8aae9-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8aae9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8aae9-105">Applica una coppia di operazioni a una determinata partizione di un registro in due parti.</span><span class="sxs-lookup"><span data-stu-id="8aae9-105">Applies a pair of operations to a given partition of a register into two parts.</span></span>

```qsharp
operation ApplyToPartition (op : ((Qubit[], Qubit[]) => Unit), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="8aae9-106">Input</span><span class="sxs-lookup"><span data-stu-id="8aae9-106">Input</span></span>

### <a name="op--qubitqubit--unit"></a><span data-ttu-id="8aae9-107">op: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="8aae9-107">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="8aae9-108">Coppia di operazioni da applicare alla partizione specificata.</span><span class="sxs-lookup"><span data-stu-id="8aae9-108">The pair of operations to be applied to the given partition.</span></span>


### <a name="numberofqubitstofirstargument--int"></a><span data-ttu-id="8aae9-109">numberOfQubitsToFirstArgument: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8aae9-109">numberOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8aae9-110">Numero di qubits dalla destinazione da inserire nella prima parte della partizione.</span><span class="sxs-lookup"><span data-stu-id="8aae9-110">Number of qubits from target to put into the first part of the partition.</span></span>
<span data-ttu-id="8aae9-111">I qubits rimanenti costituiscono la seconda parte della partizione.</span><span class="sxs-lookup"><span data-stu-id="8aae9-111">The remaining qubits constitute the second part of the partition.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="8aae9-112">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="8aae9-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="8aae9-113">Registro di qubits di cui è in corso il partizionamento e l'utilizzo da parte delle due operazioni specificate.</span><span class="sxs-lookup"><span data-stu-id="8aae9-113">A register of qubits that are being partitioned and operated on by the given two operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8aae9-114">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8aae9-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="8aae9-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8aae9-115">See Also</span></span>

- [<span data-ttu-id="8aae9-116">Microsoft. Quantum. Canon. ApplyToPartitionA</span><span class="sxs-lookup"><span data-stu-id="8aae9-116">Microsoft.Quantum.Canon.ApplyToPartitionA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartitionA)
- [<span data-ttu-id="8aae9-117">Microsoft. Quantum. Canon. ApplyToPartitionC</span><span class="sxs-lookup"><span data-stu-id="8aae9-117">Microsoft.Quantum.Canon.ApplyToPartitionC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartitionC)
- [<span data-ttu-id="8aae9-118">Microsoft. Quantum. Canon. ApplyToPartitionCA</span><span class="sxs-lookup"><span data-stu-id="8aae9-118">Microsoft.Quantum.Canon.ApplyToPartitionCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartitionCA)