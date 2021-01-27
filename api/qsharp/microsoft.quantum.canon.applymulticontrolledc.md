---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledC
title: Operazione ApplyMultiControlledC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledC
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: bf6b78cd18a827a9a4fd9d61dfd4d240de3503e9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844857"
---
# <a name="applymulticontrolledc-operation"></a><span data-ttu-id="aef58-102">Operazione ApplyMultiControlledC</span><span class="sxs-lookup"><span data-stu-id="aef58-102">ApplyMultiControlledC operation</span></span>

<span data-ttu-id="aef58-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="aef58-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="aef58-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="aef58-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="aef58-105">Applica una versione controllata multipla di un'operazione controllata singolarmente.</span><span class="sxs-lookup"><span data-stu-id="aef58-105">Applies a multiply controlled version of a singly controlled operation.</span></span>
<span data-ttu-id="aef58-106">Il modificatore `C` indica che l'operazione Single-qubit è controllabile.</span><span class="sxs-lookup"><span data-stu-id="aef58-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyMultiControlledC (singlyControlledOp : (Qubit[] => Unit), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="aef58-107">Input</span><span class="sxs-lookup"><span data-stu-id="aef58-107">Input</span></span>

### <a name="singlycontrolledop--qubit--unit"></a><span data-ttu-id="aef58-108">singlyControlledOp: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="aef58-108">singlyControlledOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="aef58-109">Operazione controllata in un singolo qubit.</span><span class="sxs-lookup"><span data-stu-id="aef58-109">An operation controlled on a single qubit.</span></span>
<span data-ttu-id="aef58-110">Si presuppone che il primo qubit nell'argomento dell'operazione sia un controllo e che si presuppone che il resto sia qubits di destinazione.</span><span class="sxs-lookup"><span data-stu-id="aef58-110">The first qubit in the argument of the operation is assumed to be a control and the rest are assumed to be target qubits.</span></span>
<span data-ttu-id="aef58-111">`ApplyMultiControlled` chiama sempre `singlyControlledOp` con un argomento di lunghezza almeno 1.</span><span class="sxs-lookup"><span data-stu-id="aef58-111">`ApplyMultiControlled` always calls `singlyControlledOp` with an argument of length at least 1.</span></span>


### <a name="ccnot--ccnotop"></a><span data-ttu-id="aef58-112">ccnot: [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span><span class="sxs-lookup"><span data-stu-id="aef58-112">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span></span>

<span data-ttu-id="aef58-113">Controllo non controllato da utilizzare per la costruzione.</span><span class="sxs-lookup"><span data-stu-id="aef58-113">The controlled-controlled-NOT gate to use for the construction.</span></span>


### <a name="controls--qubit"></a><span data-ttu-id="aef58-114">Controlli: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="aef58-114">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="aef58-115">Qubits da `singlyControlledOp` controllare.</span><span class="sxs-lookup"><span data-stu-id="aef58-115">The qubits that `singlyControlledOp` is to be controlled on.</span></span>
<span data-ttu-id="aef58-116">La lunghezza di `controls` deve essere almeno 1.</span><span class="sxs-lookup"><span data-stu-id="aef58-116">The length of `controls` must be at least 1.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="aef58-117">destinazioni: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="aef58-117">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="aef58-118">Qubits di destinazione che `singlyControlledOp` agisce su.</span><span class="sxs-lookup"><span data-stu-id="aef58-118">The target qubits that `singlyControlledOp` acts upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="aef58-119">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aef58-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="aef58-120">Commenti</span><span class="sxs-lookup"><span data-stu-id="aef58-120">Remarks</span></span>

<span data-ttu-id="aef58-121">Questa operazione usa solo ancilla qubits puliti.</span><span class="sxs-lookup"><span data-stu-id="aef58-121">This operation uses only clean ancilla qubits.</span></span>

<span data-ttu-id="aef58-122">Per la spiegazione e il diagramma di circuito, vedere la figura 4,10, sezione 4,3 in Nielsen & Chuang</span><span class="sxs-lookup"><span data-stu-id="aef58-122">For the explanation and circuit diagram see Figure 4.10, Section 4.3 in Nielsen & Chuang</span></span>

## <a name="references"></a><span data-ttu-id="aef58-123">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="aef58-123">References</span></span>

- [<span data-ttu-id="aef58-124">*Michael A. Nielsen, Isaac L. Chuang*, quantum computing e Quantum Information</span><span class="sxs-lookup"><span data-stu-id="aef58-124"> *Michael A. Nielsen , Isaac L. Chuang*, Quantum Computation and Quantum Information </span></span>](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a><span data-ttu-id="aef58-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aef58-125">See Also</span></span>

- [<span data-ttu-id="aef58-126">Microsoft. Quantum. Canon. ApplyMultiControlledCA</span><span class="sxs-lookup"><span data-stu-id="aef58-126">Microsoft.Quantum.Canon.ApplyMultiControlledCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyMultiControlledCA)