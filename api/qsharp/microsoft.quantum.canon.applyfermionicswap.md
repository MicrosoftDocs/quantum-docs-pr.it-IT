---
uid: Microsoft.Quantum.Canon.ApplyFermionicSWAP
title: Operazione ApplyFermionicSWAP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyFermionicSWAP
qsharp.summary: Applies the Fermionic SWAP.
ms.openlocfilehash: 0c470705843a6360df0a72374570d86571397e41
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218802"
---
# <a name="applyfermionicswap-operation"></a><span data-ttu-id="b902d-102">Operazione ApplyFermionicSWAP</span><span class="sxs-lookup"><span data-stu-id="b902d-102">ApplyFermionicSWAP operation</span></span>

<span data-ttu-id="b902d-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b902d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b902d-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b902d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b902d-105">Applica lo scambio fermioniche.</span><span class="sxs-lookup"><span data-stu-id="b902d-105">Applies the Fermionic SWAP.</span></span>

```qsharp
operation ApplyFermionicSWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="b902d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b902d-106">Description</span></span>

<span data-ttu-id="b902d-107">Questa operazione sostanzialmente scambia il qubits durante l'applicazione di una fase globale di-1 se entrambi i qubits sono 1S.</span><span class="sxs-lookup"><span data-stu-id="b902d-107">This essentially swaps the qubits while applying a global phase of -1 if both qubits are 1s.</span></span> <span data-ttu-id="b902d-108">Conserva l'anti-symmetrization degli orbitali.</span><span class="sxs-lookup"><span data-stu-id="b902d-108">Preserves anti-symmetrization of orbitals.</span></span>
<span data-ttu-id="b902d-109">Per altre informazioni, vedere .</span><span class="sxs-lookup"><span data-stu-id="b902d-109">See  for more information.</span></span>

<span data-ttu-id="b902d-110">Questa operazione è rappresentata dall'operatore unitario \begin{align} f_ {swap} \mathrel{: =} \begin{Bmatrix} 1 & 0 & 0 & 0 \\ \\ & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 &-1 \\ \\ \end{Bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="b902d-110">This operation is represented by the unitary operator \begin{align} f_{swap} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -1 \\\\ \end{bmatrix}.</span></span>
<span data-ttu-id="b902d-111">\end{align}</span><span class="sxs-lookup"><span data-stu-id="b902d-111">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="b902d-112">Input</span><span class="sxs-lookup"><span data-stu-id="b902d-112">Input</span></span>

### <a name="qubit1--qubit"></a><span data-ttu-id="b902d-113">qubit1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b902d-113">qubit1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b902d-114">Primo qubit da scambiare.</span><span class="sxs-lookup"><span data-stu-id="b902d-114">The first qubit to be swapped.</span></span>


### <a name="qubit2--qubit"></a><span data-ttu-id="b902d-115">qubit2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b902d-115">qubit2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b902d-116">Secondo qubit da scambiare.</span><span class="sxs-lookup"><span data-stu-id="b902d-116">The second qubit to be swapped.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b902d-117">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b902d-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="b902d-118">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="b902d-118">References</span></span>

- [<span data-ttu-id="b902d-119">*Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, grance Kin-Lic Chan*, arXiv: 1706.00023</span><span class="sxs-lookup"><span data-stu-id="b902d-119"> *Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, Garnet Kin-Lic Chan*, arXiv:1706.00023 </span></span>](https://arxiv.org/pdf/1706.00023.pdf)

## <a name="see-also"></a><span data-ttu-id="b902d-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b902d-120">See Also</span></span>

- [<span data-ttu-id="b902d-121">Microsoft. Quantum. Intrinsic. SWAP</span><span class="sxs-lookup"><span data-stu-id="b902d-121">Microsoft.Quantum.Intrinsic.SWAP</span></span>](xref:Microsoft.Quantum.Intrinsic.SWAP)