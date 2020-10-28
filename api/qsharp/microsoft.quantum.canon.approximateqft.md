---
uid: Microsoft.Quantum.Canon.ApproximateQFT
title: Operazione ApproximateQFT
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximateQFT
qsharp.summary: Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.
ms.openlocfilehash: ffa3a3737a43fbe6acc57700ae122a13586482e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716775"
---
# <a name="approximateqft-operation"></a><span data-ttu-id="d0792-102">Operazione ApproximateQFT</span><span class="sxs-lookup"><span data-stu-id="d0792-102">ApproximateQFT operation</span></span>

<span data-ttu-id="d0792-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d0792-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d0792-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d0792-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d0792-105">Applicare la trasformazione AQFT (Quantum Fourier Transform) approssimativa a un registro Quantum.</span><span class="sxs-lookup"><span data-stu-id="d0792-105">Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.</span></span>

```qsharp
operation ApproximateQFT (a : Int, qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="d0792-106">Input</span><span class="sxs-lookup"><span data-stu-id="d0792-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="d0792-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d0792-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d0792-108">parametro di approssimazione che determina a quale livello vengono eliminate le rotazioni Z controllate che si verificano nel circuito QFT.</span><span class="sxs-lookup"><span data-stu-id="d0792-108">approximation parameter which determines at which level the controlled Z-rotations that occur in the QFT circuit are pruned.</span></span>

<span data-ttu-id="d0792-109">Il parametro di approssimazione a determina il livello di eliminazione delle rotazioni Z, ovvero un ∈ {0.. n} e tutte le rotazioni Z 2 π/2K, dove k>a vengono rimosse dal circuito QFT.</span><span class="sxs-lookup"><span data-stu-id="d0792-109">The approximation parameter a determines the pruning level of the Z-rotations, i.e., a ∈ {0..n} and all Z-rotations 2π/2ᵏ where k>a are removed from the QFT circuit.</span></span> <span data-ttu-id="d0792-110">È noto che per k >= log ₂ (n) + log ₂ (1/ε) + 3 One può associare | | QFT-AQFT | |<ε.</span><span class="sxs-lookup"><span data-stu-id="d0792-110">It is known that for k >= log₂(n)+log₂(1/ε)+3 one can bound ||QFT-AQFT||<ε.</span></span>


### <a name="qs--bigendian"></a><span data-ttu-id="d0792-111">QS: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="d0792-111">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="d0792-112">registro Quantum di n qubits a cui viene applicata la trasformazione del quantum Quantum approssimativo.</span><span class="sxs-lookup"><span data-stu-id="d0792-112">quantum register of n qubits to which the Approximate Quantum Fourier Transform is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d0792-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d0792-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d0792-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="d0792-114">Remarks</span></span>

<span data-ttu-id="d0792-115">AQFT richiede i cancelli a rotazione Z nel formato 2 π/2K e Hadamard.</span><span class="sxs-lookup"><span data-stu-id="d0792-115">AQFT requires Z-rotation gates of the form 2π/2ᵏ and Hadamard gates.</span></span>

<span data-ttu-id="d0792-116">Si presuppone che l'input e l'output siano codificati nella codifica big endian.</span><span class="sxs-lookup"><span data-stu-id="d0792-116">The input and output are assumed to be encoded in big endian encoding.</span></span>

## <a name="references"></a><span data-ttu-id="d0792-117">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="d0792-117">References</span></span>

- [<span data-ttu-id="d0792-118">*M. Roetteler, th. Beth* , appl. algebra ENG. commune. Comput. 19 (3): 177-193 (2008)</span><span class="sxs-lookup"><span data-stu-id="d0792-118"> *M. Roetteler, Th. Beth* , Appl. Algebra Eng. Commun. Comput. 19(3): 177-193 (2008) </span></span>](http://doi.org/10.1007/s00200-008-0072-2)
- [<span data-ttu-id="d0792-119">*D. Coppersmith* arXiv: quanti-pH/0201067v1</span><span class="sxs-lookup"><span data-stu-id="d0792-119"> *D. Coppersmith* arXiv:quant-ph/0201067v1 </span></span>](https://arxiv.org/abs/quant-ph/0201067)