---
uid: Microsoft.Quantum.Arithmetic.MultiplyByModularInteger
title: Operazione MultiplyByModularInteger
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyByModularInteger
qsharp.summary: Performs modular multiplication by an integer constant on a qubit register.
ms.openlocfilehash: bd4e0ad6c5bad779d9a31139690021fd9fcda210
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846501"
---
# <a name="multiplybymodularinteger-operation"></a><span data-ttu-id="a6694-102">Operazione MultiplyByModularInteger</span><span class="sxs-lookup"><span data-stu-id="a6694-102">MultiplyByModularInteger operation</span></span>

<span data-ttu-id="a6694-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a6694-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a6694-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a6694-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a6694-105">Esegue la moltiplicazione modulare in base a una costante Integer in un registro qubit.</span><span class="sxs-lookup"><span data-stu-id="a6694-105">Performs modular multiplication by an integer constant on a qubit register.</span></span>

```qsharp
operation MultiplyByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="a6694-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a6694-106">Description</span></span>

<span data-ttu-id="a6694-107">È ora indicata `modulus` da $N $ e `constMultiplier` da $a $.</span><span class="sxs-lookup"><span data-stu-id="a6694-107">Let us denote `modulus` by $N$ and `constMultiplier` by $a$.</span></span>
<span data-ttu-id="a6694-108">Questa operazione implementa quindi un'operazione unitaria definita dalla mappa seguente in base al calcolo: $ $ \begin{align} \ket{y} \mapsto \ket{(a \cdot y) \operatorname{mod} N} \end{align} $ $ per tutti $y $ tra $0 $ e $N-$1.</span><span class="sxs-lookup"><span data-stu-id="a6694-108">Then this operation implements a unitary operation defined by the following map on the computational basis: $$ \begin{align} \ket{y} \mapsto \ket{(a \cdot y) \operatorname{mod} N} \end{align} $$ for all $y$ between $0$ and $N - 1$.</span></span>

## <a name="input"></a><span data-ttu-id="a6694-109">Input</span><span class="sxs-lookup"><span data-stu-id="a6694-109">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="a6694-110">constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a6694-110">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a6694-111">Costante da cui viene moltiplicato il moltiplicatore.</span><span class="sxs-lookup"><span data-stu-id="a6694-111">Constant by which multiplier is being multiplied.</span></span> <span data-ttu-id="a6694-112">Deve essere co-primo al modulo.</span><span class="sxs-lookup"><span data-stu-id="a6694-112">Must be co-prime to modulus.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="a6694-113">modulo: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a6694-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a6694-114">Viene eseguita l'operazione di moltiplicazione modulo `modulus` .</span><span class="sxs-lookup"><span data-stu-id="a6694-114">The multiplication operation is performed modulo `modulus`.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="a6694-115">moltiplicatore: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a6694-115">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a6694-116">Numero moltiplicato per una costante.</span><span class="sxs-lookup"><span data-stu-id="a6694-116">The number being multiplied by a constant.</span></span>
<span data-ttu-id="a6694-117">Si tratta di una matrice di qubits che codifica un numero intero in formato little-endian.</span><span class="sxs-lookup"><span data-stu-id="a6694-117">This is an array of qubits encoding an integer in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a6694-118">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a6694-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a6694-119">Commenti</span><span class="sxs-lookup"><span data-stu-id="a6694-119">Remarks</span></span>

- <span data-ttu-id="a6694-120">Per il diagramma di circuito e la spiegazione, vedere la figura 7 nella [pagina 8 di arXiv: quanti-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)</span><span class="sxs-lookup"><span data-stu-id="a6694-120">For the circuit diagram and explanation see Figure 7 on [Page 8 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)</span></span>
- <span data-ttu-id="a6694-121">Questa operazione corrisponde a U ₐ in [arXiv: quanti-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span><span class="sxs-lookup"><span data-stu-id="a6694-121">This operation corresponds to Uₐ in [arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span></span>