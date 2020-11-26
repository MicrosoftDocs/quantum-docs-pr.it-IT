---
uid: Microsoft.Quantum.Canon.ApplyLowDepthAnd
title: Operazione ApplyLowDepthAnd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyLowDepthAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.
ms.openlocfilehash: 4c5e381227bf82415121add38d0c0d2959fb529d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209316"
---
# <a name="applylowdepthand-operation"></a><span data-ttu-id="14214-102">Operazione ApplyLowDepthAnd</span><span class="sxs-lookup"><span data-stu-id="14214-102">ApplyLowDepthAnd operation</span></span>

<span data-ttu-id="14214-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="14214-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="14214-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="14214-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="14214-105">Inverte un qubit di destinazione specificato se e solo se entrambi i qubits di controllo si trovano nello stato 1, con T-depth 1, usando la misurazione per eseguire l'operazione di aggiunta.</span><span class="sxs-lookup"><span data-stu-id="14214-105">Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.</span></span>

```qsharp
operation ApplyLowDepthAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="14214-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="14214-106">Description</span></span>

<span data-ttu-id="14214-107">Inverte `target` se e solo se entrambi i controlli sono pari a 1, ma presuppone che `target` si trovi nello stato 0.</span><span class="sxs-lookup"><span data-stu-id="14214-107">Inverts `target` if and only if both controls are 1, but assumes that `target` is in state 0.</span></span>  <span data-ttu-id="14214-108">L'operazione ha T-Count 4, T-depth 1 e richiede un qubit helper e può pertanto essere preferibile a un'operazione CCNOT, se `target` è noto come 0.</span><span class="sxs-lookup"><span data-stu-id="14214-108">The operation has T-count 4, T-depth 1 and requires one helper qubit, and may therefore be preferable to a CCNOT operation, if `target` is known to be 0.</span></span>  <span data-ttu-id="14214-109">Il contiguo di questa operazione è basato sulla misurazione e non richiede alcun controllo T e nessun qubit helper.</span><span class="sxs-lookup"><span data-stu-id="14214-109">The adjoint of this operation is measurement based and requires no T gates, and no helper qubit.</span></span>

## <a name="input"></a><span data-ttu-id="14214-110">Input</span><span class="sxs-lookup"><span data-stu-id="14214-110">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="14214-111">Control1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="14214-111">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="14214-112">Primo controllo qubit</span><span class="sxs-lookup"><span data-stu-id="14214-112">First control qubit</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="14214-113">controllo2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="14214-113">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="14214-114">Secondo qubit di controllo</span><span class="sxs-lookup"><span data-stu-id="14214-114">Second control qubit</span></span>


### <a name="target--qubit"></a><span data-ttu-id="14214-115">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="14214-115">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="14214-116">Qubit ausiliari di destinazione; deve essere nello stato 0</span><span class="sxs-lookup"><span data-stu-id="14214-116">Target auxiliary qubit; must be in state 0</span></span>



## <a name="output--unit"></a><span data-ttu-id="14214-117">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="14214-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="14214-118">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="14214-118">References</span></span>

- <span data-ttu-id="14214-119">Cody Jones: "costruzioni innovative per il controllo Toffoli A tolleranza di errore", fisico. Rev. A 87, 022328, 2013 [arXiv: 1212.5069](https://arxiv.org/abs/1212.5069) DOI: 10.1103/PhysRevA. 87.022328</span><span class="sxs-lookup"><span data-stu-id="14214-119">Cody Jones: "Novel constructions for the fault-tolerant Toffoli gate", Phys. Rev. A 87, 022328, 2013 [arXiv:1212.5069](https://arxiv.org/abs/1212.5069) doi:10.1103/PhysRevA.87.022328</span></span>
- <span data-ttu-id="14214-120">Peter Selinger: "Quantum Circuits of T-Depth One", fisico. Rev. A 87, 042302, 2013 [arXiv: 1210.0974](https://arxiv.org/abs/1210.0974) DOI: 10.1103/PhysRevA. 87.042302</span><span class="sxs-lookup"><span data-stu-id="14214-120">Peter Selinger: "Quantum circuits of T-depth one", Phys. Rev. A 87, 042302, 2013 [arXiv:1210.0974](https://arxiv.org/abs/1210.0974) doi:10.1103/PhysRevA.87.042302</span></span>