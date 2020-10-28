---
uid: Microsoft.Quantum.Canon.ApplyFermionicSWAP
title: Operazione ApplyFermionicSWAP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyFermionicSWAP
qsharp.summary: Applies the Fermionic SWAP.
ms.openlocfilehash: 25dd91b200700d1474cf27bf1d0fa71d57f2e09b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718275"
---
# <a name="applyfermionicswap-operation"></a><span data-ttu-id="47a0a-102">Operazione ApplyFermionicSWAP</span><span class="sxs-lookup"><span data-stu-id="47a0a-102">ApplyFermionicSWAP operation</span></span>

<span data-ttu-id="47a0a-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="47a0a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="47a0a-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="47a0a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="47a0a-105">Applica lo scambio fermioniche.</span><span class="sxs-lookup"><span data-stu-id="47a0a-105">Applies the Fermionic SWAP.</span></span>

```qsharp
operation ApplyFermionicSWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="47a0a-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="47a0a-106">Description</span></span>

<span data-ttu-id="47a0a-107">Questa operazione sostanzialmente scambia il qubits durante l'applicazione di una fase globale di-1 se entrambi i qubits sono 1S.</span><span class="sxs-lookup"><span data-stu-id="47a0a-107">This essentially swaps the qubits while applying a global phase of -1 if both qubits are 1s.</span></span> <span data-ttu-id="47a0a-108">Conserva l'anti-symmetrization degli orbitali.</span><span class="sxs-lookup"><span data-stu-id="47a0a-108">Preserves anti-symmetrization of orbitals.</span></span>
<span data-ttu-id="47a0a-109">Per altre informazioni, vedere .</span><span class="sxs-lookup"><span data-stu-id="47a0a-109">See  for more information.</span></span>

<span data-ttu-id="47a0a-110">Questa operazione è rappresentata dall'operatore unitario \begin{align} f_ {swap} \mathrel{: =} \begin{Bmatrix} 1 & 0 & 0 & 0 \\ \\ & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 &-1 \\ \\ \end{Bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="47a0a-110">This operation is represented by the unitary operator \begin{align} f_{swap} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -1 \\\\ \end{bmatrix}.</span></span>
<span data-ttu-id="47a0a-111">\end{align}</span><span class="sxs-lookup"><span data-stu-id="47a0a-111">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="47a0a-112">Input</span><span class="sxs-lookup"><span data-stu-id="47a0a-112">Input</span></span>

### <a name="qubit1--qubit"></a><span data-ttu-id="47a0a-113">qubit1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="47a0a-113">qubit1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="47a0a-114">Primo qubit da scambiare.</span><span class="sxs-lookup"><span data-stu-id="47a0a-114">The first qubit to be swapped.</span></span>


### <a name="qubit2--qubit"></a><span data-ttu-id="47a0a-115">qubit2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="47a0a-115">qubit2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="47a0a-116">Secondo qubit da scambiare.</span><span class="sxs-lookup"><span data-stu-id="47a0a-116">The second qubit to be swapped.</span></span>



## <a name="output--unit"></a><span data-ttu-id="47a0a-117">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="47a0a-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="47a0a-118">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="47a0a-118">References</span></span>

- [<span data-ttu-id="47a0a-119">*Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, grance Kin-Lic Chan* , arXiv: 1706.00023</span><span class="sxs-lookup"><span data-stu-id="47a0a-119"> *Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, Garnet Kin-Lic Chan* , arXiv:1706.00023 </span></span>](https://arxiv.org/pdf/1706.00023.pdf)

## <a name="see-also"></a><span data-ttu-id="47a0a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47a0a-120">See Also</span></span>

- [<span data-ttu-id="47a0a-121">Microsoft. Quantum. Intrinsic. SWAP</span><span class="sxs-lookup"><span data-stu-id="47a0a-121">Microsoft.Quantum.Intrinsic.SWAP</span></span>](xref:Microsoft.Quantum.Intrinsic.SWAP)