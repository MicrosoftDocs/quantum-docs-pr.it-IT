---
uid: Microsoft.Quantum.Canon.AndLadder
title: Operazione AndLadder
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: AndLadder
qsharp.summary: Performs a controlled "AND ladder" on a register of target qubits.
ms.openlocfilehash: d44c462c7a9fc9521bdecfe2ca7f607e90482baf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845214"
---
# <a name="andladder-operation"></a><span data-ttu-id="03d1a-102">Operazione AndLadder</span><span class="sxs-lookup"><span data-stu-id="03d1a-102">AndLadder operation</span></span>

<span data-ttu-id="03d1a-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="03d1a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="03d1a-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="03d1a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="03d1a-105">Esegue una "e una scala" controllata in un registro di qubits di destinazione.</span><span class="sxs-lookup"><span data-stu-id="03d1a-105">Performs a controlled "AND ladder" on a register of target qubits.</span></span>

```qsharp
operation AndLadder (ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="03d1a-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="03d1a-106">Description</span></span>

<span data-ttu-id="03d1a-107">Questa operazione applica una trasformazione descritta dal mapping seguente di base di calcolo, $ $ \begin{align} \ket{x \_ 1, \dots, x \_ n} \ket{y \_ 1, \dots, y \_ {n-1}} \mapsto \ket{x \_ 1, \dots, x \_ n} \ket{y \_ 1 \oplus (x \_ 1 \land x \_ 2), \dots, y \_ {n-1} \oplus (x \_ 1 \land x \_ 2 \land \cdots \land x \_ {n-1}}, \end{align} $ $ dove $ \ket{x \_ 1, \dots, x \_ n} $ si riferisce agli Stati di base computazionale di `controls` e dove $ \ket{y \_ 1, \dots, y \_ {n-1}} $ fa riferimento agli Stati di base di calcolo di `targets` .</span><span class="sxs-lookup"><span data-stu-id="03d1a-107">This operation applies a transformation described by the following mapping of the computational basis, $$ \begin{align} \ket{x\_1, \dots, x\_n} \ket{y\_1, \dots, y\_{n - 1}} \mapsto \ket{x\_1, \dots, x\_n} \ket{ y\_1 \oplus (x\_1 \land x\_2), \dots, y\_{n - 1} \oplus (x\_1 \land x\_2 \land \cdots \land x\_{n - 1} }, \end{align} $$ where $\ket{x\_1, \dots, x\_n}$ refers to the computational basis states of `controls`, and where $\ket{y\_1, \dots, y\_{n - 1}}$ refers to the computational basis states of `targets`.</span></span>

## <a name="input"></a><span data-ttu-id="03d1a-108">Input</span><span class="sxs-lookup"><span data-stu-id="03d1a-108">Input</span></span>

### <a name="ccnot--ccnotop"></a><span data-ttu-id="03d1a-109">ccnot: [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span><span class="sxs-lookup"><span data-stu-id="03d1a-109">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span></span>

<span data-ttu-id="03d1a-110">Controllo CCNOT da utilizzare per la costruzione.</span><span class="sxs-lookup"><span data-stu-id="03d1a-110">The CCNOT gate to use for the construction.</span></span>


### <a name="controls--qubit"></a><span data-ttu-id="03d1a-111">Controlli: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="03d1a-111">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="03d1a-112">Registro di qubits da usare come controlli per la scala e.</span><span class="sxs-lookup"><span data-stu-id="03d1a-112">A register of qubits to be used as controls for the and ladder.</span></span>
<span data-ttu-id="03d1a-113">Questa operazione lascia gli Stati di base computazionale di `controls` invariante.</span><span class="sxs-lookup"><span data-stu-id="03d1a-113">This operation leaves computational basis states of `controls` invariant.</span></span>
<span data-ttu-id="03d1a-114">La lunghezza di `controls` deve essere almeno 2 e deve essere uguale a uno più la lunghezza di `targets` .</span><span class="sxs-lookup"><span data-stu-id="03d1a-114">The length of `controls` must be at least 2, and must be equal to one plus the length of `targets`.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="03d1a-115">destinazioni: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="03d1a-115">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="03d1a-116">La lunghezza di `targets` deve essere almeno 1 e uguale alla lunghezza di `controls` meno uno.</span><span class="sxs-lookup"><span data-stu-id="03d1a-116">The length of `targets` must be at least 1 and equal to the length of `controls` minus one.</span></span>



## <a name="output--unit"></a><span data-ttu-id="03d1a-117">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="03d1a-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="03d1a-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="03d1a-118">Remarks</span></span>

- <span data-ttu-id="03d1a-119">Utilizzato come parte di <xref:microsoft.quantum.canon.applymulticontrolledc> e <xref:microsoft.quantum.canon.applymulticontrolledca> .</span><span class="sxs-lookup"><span data-stu-id="03d1a-119">Used as a part of <xref:microsoft.quantum.canon.applymulticontrolledc> and <xref:microsoft.quantum.canon.applymulticontrolledca>.</span></span>
- <span data-ttu-id="03d1a-120">Per la spiegazione e il diagramma di circuito, vedere la figura 4,10, sezione 4,3 in Nielsen & Chuang.</span><span class="sxs-lookup"><span data-stu-id="03d1a-120">For the explanation and circuit diagram see Figure 4.10, Section 4.3 in Nielsen & Chuang.</span></span>

## <a name="references"></a><span data-ttu-id="03d1a-121">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="03d1a-121">References</span></span>

- [<span data-ttu-id="03d1a-122">*Michael A. Nielsen, Isaac L. Chuang*, quantum computing e Quantum Information</span><span class="sxs-lookup"><span data-stu-id="03d1a-122"> *Michael A. Nielsen , Isaac L. Chuang*, Quantum Computation and Quantum Information </span></span>](http://doi.org/10.1017/CBO9780511976667)