---
uid: Microsoft.Quantum.Arithmetic.MultiplyByModularInteger
title: Operazione MultiplyByModularInteger
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyByModularInteger
qsharp.summary: Performs modular multiplication by an integer constant on a qubit register.
ms.openlocfilehash: 080414d208a2a0c114857db8e93efb4cd74a4d8d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222576"
---
# <a name="multiplybymodularinteger-operation"></a><span data-ttu-id="c1f2a-102">Operazione MultiplyByModularInteger</span><span class="sxs-lookup"><span data-stu-id="c1f2a-102">MultiplyByModularInteger operation</span></span>

<span data-ttu-id="c1f2a-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c1f2a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c1f2a-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c1f2a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c1f2a-105">Esegue la moltiplicazione modulare in base a una costante Integer in un registro qubit.</span><span class="sxs-lookup"><span data-stu-id="c1f2a-105">Performs modular multiplication by an integer constant on a qubit register.</span></span>

```qsharp
operation MultiplyByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="c1f2a-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c1f2a-106">Description</span></span>

<span data-ttu-id="c1f2a-107">È ora indicata `modulus` da $N $ e `constMultiplier` da $a $.</span><span class="sxs-lookup"><span data-stu-id="c1f2a-107">Let us denote `modulus` by $N$ and `constMultiplier` by $a$.</span></span>
<span data-ttu-id="c1f2a-108">Questa operazione implementa quindi un'operazione unitaria definita dalla mappa seguente in base al calcolo: $ $ \begin{align} \ket{y} \mapsto \ket{(a \cdot y) \operatorname{mod} N} \end{align} $ $ per tutti $y $ tra $0 $ e $N-$1.</span><span class="sxs-lookup"><span data-stu-id="c1f2a-108">Then this operation implements a unitary operation defined by the following map on the computational basis: $$ \begin{align} \ket{y} \mapsto \ket{(a \cdot y) \operatorname{mod} N} \end{align} $$ for all $y$ between $0$ and $N - 1$.</span></span>

## <a name="input"></a><span data-ttu-id="c1f2a-109">Input</span><span class="sxs-lookup"><span data-stu-id="c1f2a-109">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="c1f2a-110">constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c1f2a-110">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c1f2a-111">Costante da cui viene moltiplicato il moltiplicatore.</span><span class="sxs-lookup"><span data-stu-id="c1f2a-111">Constant by which multiplier is being multiplied.</span></span> <span data-ttu-id="c1f2a-112">Deve essere co-primo al modulo.</span><span class="sxs-lookup"><span data-stu-id="c1f2a-112">Must be co-prime to modulus.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="c1f2a-113">modulo: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c1f2a-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c1f2a-114">Viene eseguita l'operazione di moltiplicazione modulo `modulus` .</span><span class="sxs-lookup"><span data-stu-id="c1f2a-114">The multiplication operation is performed modulo `modulus`.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="c1f2a-115">moltiplicatore: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c1f2a-115">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c1f2a-116">Numero moltiplicato per una costante.</span><span class="sxs-lookup"><span data-stu-id="c1f2a-116">The number being multiplied by a constant.</span></span>
<span data-ttu-id="c1f2a-117">Si tratta di una matrice di qubits che codifica un numero intero in formato little-endian.</span><span class="sxs-lookup"><span data-stu-id="c1f2a-117">This is an array of qubits encoding an integer in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c1f2a-118">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c1f2a-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c1f2a-119">Commenti</span><span class="sxs-lookup"><span data-stu-id="c1f2a-119">Remarks</span></span>

- <span data-ttu-id="c1f2a-120">Per il diagramma di circuito e la spiegazione, vedere la figura 7 nella [pagina 8 di arXiv: quanti-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)</span><span class="sxs-lookup"><span data-stu-id="c1f2a-120">For the circuit diagram and explanation see Figure 7 on [Page 8 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)</span></span>
- <span data-ttu-id="c1f2a-121">Questa operazione corrisponde a U ₐ in [arXiv: quanti-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span><span class="sxs-lookup"><span data-stu-id="c1f2a-121">This operation corresponds to Uₐ in [arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span></span>