---
uid: Microsoft.Quantum.Canon.ApplyToPartitionCA
title: Operazione ApplyToPartitionCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartitionCA
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 8ea437a0e25ed43eb745a7740ecd8861ced1350a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717125"
---
# <a name="applytopartitionca-operation"></a><span data-ttu-id="6990e-102">Operazione ApplyToPartitionCA</span><span class="sxs-lookup"><span data-stu-id="6990e-102">ApplyToPartitionCA operation</span></span>

<span data-ttu-id="6990e-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6990e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6990e-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6990e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6990e-105">Applica una coppia di operazioni a una determinata partizione di un registro in due parti.</span><span class="sxs-lookup"><span data-stu-id="6990e-105">Applies a pair of operations to a given partition of a register into two parts.</span></span>
<span data-ttu-id="6990e-106">Il modificatore `CA` indica che l'operazione è controllabile e adjointable.</span><span class="sxs-lookup"><span data-stu-id="6990e-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToPartitionCA (op : ((Qubit[], Qubit[]) => Unit is Ctl + Adj), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="6990e-107">Input</span><span class="sxs-lookup"><span data-stu-id="6990e-107">Input</span></span>

### <a name="op--qubitqubit--unit-ctl--adj"></a><span data-ttu-id="6990e-108">op: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [unità](xref:microsoft.quantum.lang-ref.unit) CTL + ADJ</span><span class="sxs-lookup"><span data-stu-id="6990e-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="6990e-109">Coppia di operazioni da applicare alla partizione specificata.</span><span class="sxs-lookup"><span data-stu-id="6990e-109">The pair of operations to be applied to the given partition.</span></span>


### <a name="numberofqubitstofirstargument--int"></a><span data-ttu-id="6990e-110">numberOfQubitsToFirstArgument: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6990e-110">numberOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6990e-111">Numero di qubits dalla destinazione da inserire nella prima parte della partizione.</span><span class="sxs-lookup"><span data-stu-id="6990e-111">Number of qubits from target to put into the first part of the partition.</span></span>
<span data-ttu-id="6990e-112">I qubits rimanenti costituiscono la seconda parte della partizione.</span><span class="sxs-lookup"><span data-stu-id="6990e-112">The remaining qubits constitute the second part of the partition.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="6990e-113">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6990e-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6990e-114">Registro di qubits di cui è in corso il partizionamento e l'utilizzo da parte delle due operazioni specificate.</span><span class="sxs-lookup"><span data-stu-id="6990e-114">A register of qubits that are being partitioned and operated on by the given two operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6990e-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6990e-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="6990e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6990e-116">See Also</span></span>

- [<span data-ttu-id="6990e-117">Microsoft. Quantum. Canon. ApplyToPartition</span><span class="sxs-lookup"><span data-stu-id="6990e-117">Microsoft.Quantum.Canon.ApplyToPartition</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartition)