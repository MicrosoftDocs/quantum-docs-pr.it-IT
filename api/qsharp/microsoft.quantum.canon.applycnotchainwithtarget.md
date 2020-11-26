---
uid: Microsoft.Quantum.Canon.ApplyCNOTChainWithTarget
title: Operazione ApplyCNOTChainWithTarget
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChainWithTarget
qsharp.summary: Computes the parity of an array of qubits into a target qubit.
ms.openlocfilehash: 8ec85ce5805b3bbd1e1f7c739f27de3a861bc79e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219108"
---
# <a name="applycnotchainwithtarget-operation"></a><span data-ttu-id="28d41-102">Operazione ApplyCNOTChainWithTarget</span><span class="sxs-lookup"><span data-stu-id="28d41-102">ApplyCNOTChainWithTarget operation</span></span>

<span data-ttu-id="28d41-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="28d41-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="28d41-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="28d41-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="28d41-105">Calcola la parità di una matrice di qubits in un qubit di destinazione.</span><span class="sxs-lookup"><span data-stu-id="28d41-105">Computes the parity of an array of qubits into a target qubit.</span></span>

```qsharp
operation ApplyCNOTChainWithTarget (qubits : Qubit[], targetQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="28d41-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="28d41-106">Description</span></span>

<span data-ttu-id="28d41-107">Se la matrice è inizialmente nello stato $ \ket{q_0} \ket{q_1} \cdots \ket{q_ {\Text{target}}} $, lo stato finale viene fornito da $ \ket{q_0} \ket{q_1 \oplus q_0} \cdots \ket{q_ {n-1} \oplus \cdots \oplus q_0 \oplus q_ {\Text{target}}} $.</span><span class="sxs-lookup"><span data-stu-id="28d41-107">If the array is initially in the state $\ket{q_0} \ket{q_1} \cdots \ket{q_{\text{target}}}$, the final state is given by $\ket{q_0} \ket{q_1 \oplus q_0} \cdots \ket{q_{n - 1} \oplus \cdots \oplus q_0 \oplus q_{\text{target}}}$.</span></span>

## <a name="input"></a><span data-ttu-id="28d41-108">Input</span><span class="sxs-lookup"><span data-stu-id="28d41-108">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="28d41-109">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="28d41-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="28d41-110">Matrice di qubits in cui viene calcolata la parità.</span><span class="sxs-lookup"><span data-stu-id="28d41-110">Array of qubits on which the parity is computed.</span></span>


### <a name="targetqubit--qubit"></a><span data-ttu-id="28d41-111">targetQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="28d41-111">targetQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="28d41-112">Qubit finale in cui la parità di ' qubits ' è XORed.</span><span class="sxs-lookup"><span data-stu-id="28d41-112">Final qubit into which the parity of 'qubits' is XORed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="28d41-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="28d41-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="28d41-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="28d41-114">Remarks</span></span>

<span data-ttu-id="28d41-115">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="28d41-115">The following are equivalent:</span></span>

```qsharp
ApplyCNOTChainWithTarget(Most(qs), Last(qs));
```

<span data-ttu-id="28d41-116">e</span><span class="sxs-lookup"><span data-stu-id="28d41-116">and</span></span>

```qsharp
ApplyCNOTChain(qs);
```