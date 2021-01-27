---
uid: Microsoft.Quantum.Canon.ApplyFermionicSWAP
title: Operazione ApplyFermionicSWAP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyFermionicSWAP
qsharp.summary: Applies the Fermionic SWAP.
ms.openlocfilehash: 334f407a32dabc8f4e0a1a29c8f06a1b9f40dc59
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845059"
---
# <a name="applyfermionicswap-operation"></a><span data-ttu-id="44d86-102">Operazione ApplyFermionicSWAP</span><span class="sxs-lookup"><span data-stu-id="44d86-102">ApplyFermionicSWAP operation</span></span>

<span data-ttu-id="44d86-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="44d86-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="44d86-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="44d86-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="44d86-105">Applica lo scambio fermioniche.</span><span class="sxs-lookup"><span data-stu-id="44d86-105">Applies the Fermionic SWAP.</span></span>

```qsharp
operation ApplyFermionicSWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="44d86-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44d86-106">Description</span></span>

<span data-ttu-id="44d86-107">Questa operazione sostanzialmente scambia il qubits durante l'applicazione di una fase globale di-1 se entrambi i qubits sono 1S.</span><span class="sxs-lookup"><span data-stu-id="44d86-107">This essentially swaps the qubits while applying a global phase of -1 if both qubits are 1s.</span></span> <span data-ttu-id="44d86-108">Conserva l'anti-symmetrization degli orbitali.</span><span class="sxs-lookup"><span data-stu-id="44d86-108">Preserves anti-symmetrization of orbitals.</span></span>
<span data-ttu-id="44d86-109">Per altre informazioni, vedere .</span><span class="sxs-lookup"><span data-stu-id="44d86-109">See  for more information.</span></span>

<span data-ttu-id="44d86-110">Questa operazione è rappresentata dall'operatore unitario \begin{align} f_ {swap} \mathrel{: =} \begin{Bmatrix} 1 & 0 & 0 & 0 \\ \\ & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 &-1 \\ \\ \end{Bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="44d86-110">This operation is represented by the unitary operator \begin{align} f_{swap} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -1 \\\\ \end{bmatrix}.</span></span>
<span data-ttu-id="44d86-111">\end{align}</span><span class="sxs-lookup"><span data-stu-id="44d86-111">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="44d86-112">Input</span><span class="sxs-lookup"><span data-stu-id="44d86-112">Input</span></span>

### <a name="qubit1--qubit"></a><span data-ttu-id="44d86-113">qubit1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="44d86-113">qubit1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="44d86-114">Primo qubit da scambiare.</span><span class="sxs-lookup"><span data-stu-id="44d86-114">The first qubit to be swapped.</span></span>


### <a name="qubit2--qubit"></a><span data-ttu-id="44d86-115">qubit2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="44d86-115">qubit2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="44d86-116">Secondo qubit da scambiare.</span><span class="sxs-lookup"><span data-stu-id="44d86-116">The second qubit to be swapped.</span></span>



## <a name="output--unit"></a><span data-ttu-id="44d86-117">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="44d86-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="44d86-118">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="44d86-118">References</span></span>

- [<span data-ttu-id="44d86-119">*Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, grance Kin-Lic Chan*, arXiv: 1706.00023</span><span class="sxs-lookup"><span data-stu-id="44d86-119"> *Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, Garnet Kin-Lic Chan*, arXiv:1706.00023 </span></span>](https://arxiv.org/pdf/1706.00023.pdf)

## <a name="see-also"></a><span data-ttu-id="44d86-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44d86-120">See Also</span></span>

- [<span data-ttu-id="44d86-121">Microsoft. Quantum. Intrinsic. SWAP</span><span class="sxs-lookup"><span data-stu-id="44d86-121">Microsoft.Quantum.Intrinsic.SWAP</span></span>](xref:Microsoft.Quantum.Intrinsic.SWAP)