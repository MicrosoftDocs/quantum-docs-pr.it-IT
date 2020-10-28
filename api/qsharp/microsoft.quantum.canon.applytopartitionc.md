---
uid: Microsoft.Quantum.Canon.ApplyToPartitionC
title: Operazione ApplyToPartitionC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartitionC
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 840c93c653d71af1a82fb0dc51d9e056176ba88b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717114"
---
# <a name="applytopartitionc-operation"></a><span data-ttu-id="0c235-102">Operazione ApplyToPartitionC</span><span class="sxs-lookup"><span data-stu-id="0c235-102">ApplyToPartitionC operation</span></span>

<span data-ttu-id="0c235-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0c235-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0c235-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0c235-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0c235-105">Applica una coppia di operazioni a una determinata partizione di un registro in due parti.</span><span class="sxs-lookup"><span data-stu-id="0c235-105">Applies a pair of operations to a given partition of a register into two parts.</span></span>
<span data-ttu-id="0c235-106">Il modificatore `C` indica che l'operazione è controllabile.</span><span class="sxs-lookup"><span data-stu-id="0c235-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToPartitionC (op : ((Qubit[], Qubit[]) => Unit is Ctl), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="0c235-107">Input</span><span class="sxs-lookup"><span data-stu-id="0c235-107">Input</span></span>

### <a name="op--qubitqubit--unit-ctl"></a><span data-ttu-id="0c235-108">op: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => CTL [unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0c235-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="0c235-109">Coppia di operazioni da applicare alla partizione specificata.</span><span class="sxs-lookup"><span data-stu-id="0c235-109">The pair of operations to be applied to the given partition.</span></span>


### <a name="numberofqubitstofirstargument--int"></a><span data-ttu-id="0c235-110">numberOfQubitsToFirstArgument: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0c235-110">numberOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0c235-111">Numero di qubits dalla destinazione da inserire nella prima parte della partizione.</span><span class="sxs-lookup"><span data-stu-id="0c235-111">Number of qubits from target to put into the first part of the partition.</span></span>
<span data-ttu-id="0c235-112">I qubits rimanenti costituiscono la seconda parte della partizione.</span><span class="sxs-lookup"><span data-stu-id="0c235-112">The remaining qubits constitute the second part of the partition.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="0c235-113">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0c235-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0c235-114">Registro di qubits di cui è in corso il partizionamento e l'utilizzo da parte delle due operazioni specificate.</span><span class="sxs-lookup"><span data-stu-id="0c235-114">A register of qubits that are being partitioned and operated on by the given two operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0c235-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0c235-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="0c235-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c235-116">See Also</span></span>

- [<span data-ttu-id="0c235-117">Microsoft. Quantum. Canon. ApplyToPartition</span><span class="sxs-lookup"><span data-stu-id="0c235-117">Microsoft.Quantum.Canon.ApplyToPartition</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartition)