---
uid: Microsoft.Quantum.ErrorCorrection.MeasureStabilizerGenerators
title: Operazione MeasureStabilizerGenerators
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: MeasureStabilizerGenerators
qsharp.summary: Measures the given set of generators of a stabilizer group.
ms.openlocfilehash: d7c8df079e49b2ce0a5106e430ef4060df85cdc4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98825763"
---
# <a name="measurestabilizergenerators-operation"></a><span data-ttu-id="f5d86-102">Operazione MeasureStabilizerGenerators</span><span class="sxs-lookup"><span data-stu-id="f5d86-102">MeasureStabilizerGenerators operation</span></span>

<span data-ttu-id="f5d86-103">Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="f5d86-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="f5d86-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f5d86-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f5d86-105">Misura il set specificato di generatori di un gruppo stabilizzatore.</span><span class="sxs-lookup"><span data-stu-id="f5d86-105">Measures the given set of generators of a stabilizer group.</span></span>

```qsharp
operation MeasureStabilizerGenerators (stabilizerGroup : Pauli[][], logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister, gadget : ((Pauli[], Qubit[]) => Result)) : Microsoft.Quantum.ErrorCorrection.Syndrome
```


## <a name="input"></a><span data-ttu-id="f5d86-106">Input</span><span class="sxs-lookup"><span data-stu-id="f5d86-106">Input</span></span>

### <a name="stabilizergroup--pauli"></a><span data-ttu-id="f5d86-107">stabilizerGroup: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="f5d86-107">stabilizerGroup : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="f5d86-108">Matrice di operatori multiqubit Pauli.</span><span class="sxs-lookup"><span data-stu-id="f5d86-108">An array of multiqubit Pauli operators.</span></span>
<span data-ttu-id="f5d86-109">Ad esempio, `stabilizerGroup[0]` è un elenco di matrici Pauli Single-qubit, il prodotto tensore di che è un generatore di stabilizzatori.</span><span class="sxs-lookup"><span data-stu-id="f5d86-109">For example, `stabilizerGroup[0]` is a list of single-qubit Pauli matrices, the tensor product of which is a stabilizer generator.</span></span>


### <a name="logicalregister--logicalregister"></a><span data-ttu-id="f5d86-110">logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="f5d86-110">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="f5d86-111">Matrice di qubits in cui è definito il codice di stabilizzazione.</span><span class="sxs-lookup"><span data-stu-id="f5d86-111">An array of qubits where the stabilizer code is defined.</span></span>


### <a name="gadget--pauliqubit--__invalidresult__"></a><span data-ttu-id="f5d86-112">Gadget: ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="f5d86-112">gadget : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __invalid<Result>__</span></span> 

<span data-ttu-id="f5d86-113">Operazione che specifica come misurare un operatore multiqubit Pauli.</span><span class="sxs-lookup"><span data-stu-id="f5d86-113">An operation that specifies how to measure a multiqubit Pauli operator.</span></span>



## <a name="output--syndrome"></a><span data-ttu-id="f5d86-114">Output: [sindrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span><span class="sxs-lookup"><span data-stu-id="f5d86-114">Output : [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span></span>

<span data-ttu-id="f5d86-115">Risultato delle misurazioni.</span><span class="sxs-lookup"><span data-stu-id="f5d86-115">The result of measurements.</span></span>

## <a name="remarks"></a><span data-ttu-id="f5d86-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="f5d86-116">Remarks</span></span>

<span data-ttu-id="f5d86-117">Questa operazione non controlla se il set specificato di generatori è in permuta.</span><span class="sxs-lookup"><span data-stu-id="f5d86-117">This does not check if the given set of generators are commuting.</span></span>
<span data-ttu-id="f5d86-118">Se non eseguono la permuta, il risultato delle misurazioni può essere arbitrario.</span><span class="sxs-lookup"><span data-stu-id="f5d86-118">If they are not commuting, the result of measurements may be arbitrary.</span></span>