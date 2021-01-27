---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledCA
title: Operazione ApplyMultiControlledCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledCA
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: a6549084b1c2fda885823f451d17f9c2ebbb4600
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841687"
---
# <a name="applymulticontrolledca-operation"></a><span data-ttu-id="dc29c-102">Operazione ApplyMultiControlledCA</span><span class="sxs-lookup"><span data-stu-id="dc29c-102">ApplyMultiControlledCA operation</span></span>

<span data-ttu-id="dc29c-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dc29c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dc29c-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dc29c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dc29c-105">Applica una versione controllata multipla di un'operazione controllata singolarmente.</span><span class="sxs-lookup"><span data-stu-id="dc29c-105">Applies a multiply controlled version of a singly controlled operation.</span></span>
<span data-ttu-id="dc29c-106">Il modificatore `CA` indica che l'operazione Single-qubit è controllabile e adjointable.</span><span class="sxs-lookup"><span data-stu-id="dc29c-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyMultiControlledCA (singlyControlledOp : (Qubit[] => Unit is Adj), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="dc29c-107">Input</span><span class="sxs-lookup"><span data-stu-id="dc29c-107">Input</span></span>

### <a name="singlycontrolledop--qubit--unit--is-adj"></a><span data-ttu-id="dc29c-108">singlyControlledOp: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ</span><span class="sxs-lookup"><span data-stu-id="dc29c-108">singlyControlledOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="dc29c-109">Operazione controllata in un singolo qubit.</span><span class="sxs-lookup"><span data-stu-id="dc29c-109">An operation controlled on a single qubit.</span></span>
<span data-ttu-id="dc29c-110">Il primo qubit nell'argomento dell'operazione presuppone che sia un controllo e che si presuppone che il resto sia qubits di destinazione.</span><span class="sxs-lookup"><span data-stu-id="dc29c-110">The first qubit in the argument of the operation assumed to be a control and the rest are assumed to be target qubits.</span></span>
<span data-ttu-id="dc29c-111">`ApplyMultiControlled` chiama sempre `singlyControlledOp` con un argomento di lunghezza almeno 1.</span><span class="sxs-lookup"><span data-stu-id="dc29c-111">`ApplyMultiControlled` always calls `singlyControlledOp` with an argument of length at least 1.</span></span>


### <a name="ccnot--ccnotop"></a><span data-ttu-id="dc29c-112">ccnot: [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span><span class="sxs-lookup"><span data-stu-id="dc29c-112">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span></span>

<span data-ttu-id="dc29c-113">Controllo non controllato da utilizzare per la costruzione.</span><span class="sxs-lookup"><span data-stu-id="dc29c-113">The controlled-controlled-NOT gate to use for the construction.</span></span>


### <a name="controls--qubit"></a><span data-ttu-id="dc29c-114">Controlli: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="dc29c-114">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="dc29c-115">Qubits da `singlyControlledOp` controllare.</span><span class="sxs-lookup"><span data-stu-id="dc29c-115">The qubits that `singlyControlledOp` is to be controlled on.</span></span>
<span data-ttu-id="dc29c-116">La lunghezza di `controls` deve essere almeno 1.</span><span class="sxs-lookup"><span data-stu-id="dc29c-116">The length of `controls` must be at least 1.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="dc29c-117">destinazioni: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="dc29c-117">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="dc29c-118">Qubits di destinazione che `singlyControlledOp` agisce su.</span><span class="sxs-lookup"><span data-stu-id="dc29c-118">The target qubits that `singlyControlledOp` acts upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dc29c-119">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dc29c-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="dc29c-120">Commenti</span><span class="sxs-lookup"><span data-stu-id="dc29c-120">Remarks</span></span>

<span data-ttu-id="dc29c-121">Questa operazione usa solo ancilla qubits puliti.</span><span class="sxs-lookup"><span data-stu-id="dc29c-121">This operation uses only clean ancilla qubits.</span></span>

<span data-ttu-id="dc29c-122">Per la spiegazione e il diagramma di circuito, vedere la figura 4,10, sezione 4,3 in Nielsen & Chuang</span><span class="sxs-lookup"><span data-stu-id="dc29c-122">For the explanation and circuit diagram see Figure 4.10, Section 4.3 in Nielsen & Chuang</span></span>

## <a name="references"></a><span data-ttu-id="dc29c-123">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="dc29c-123">References</span></span>

- [<span data-ttu-id="dc29c-124">*Michael A. Nielsen, Isaac L. Chuang*, quantum computing e Quantum Information</span><span class="sxs-lookup"><span data-stu-id="dc29c-124"> *Michael A. Nielsen , Isaac L. Chuang*, Quantum Computation and Quantum Information </span></span>](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a><span data-ttu-id="dc29c-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc29c-125">See Also</span></span>

- [<span data-ttu-id="dc29c-126">Microsoft. Quantum. Canon. ApplyMultiControlledC</span><span class="sxs-lookup"><span data-stu-id="dc29c-126">Microsoft.Quantum.Canon.ApplyMultiControlledC</span></span>](xref:Microsoft.Quantum.Canon.ApplyMultiControlledC)