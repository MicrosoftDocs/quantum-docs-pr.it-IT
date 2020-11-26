---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation
title: Operazione ApplyPermutationUsingTransformation
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingTransformation
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using transformation-based synthesis.
ms.openlocfilehash: a05b433eae2612bbf5c87522c4ef251976184aa8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192061"
---
# <a name="applypermutationusingtransformation-operation"></a><span data-ttu-id="b10ee-102">Operazione ApplyPermutationUsingTransformation</span><span class="sxs-lookup"><span data-stu-id="b10ee-102">ApplyPermutationUsingTransformation operation</span></span>

<span data-ttu-id="b10ee-103">Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="b10ee-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="b10ee-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b10ee-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b10ee-105">Permuta le ampiezze in uno stato quantum data una permutazione utilizzando la sintesi basata sulla trasformazione.</span><span class="sxs-lookup"><span data-stu-id="b10ee-105">Permutes the amplitudes in a quantum state given a permutation using transformation-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingTransformation (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="b10ee-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b10ee-106">Description</span></span>

<span data-ttu-id="b10ee-107">Questa procedura implementa l'approccio di sintesi basata sulla trasformazione unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="b10ee-107">This procedure implements the unidirectional transformation based synthesis approach.</span></span>  <span data-ttu-id="b10ee-108">L'input è una permutazione $ \Pi $ oltre $2 ^ n $ Elements $ \{ 0, \dots, 2 ^ n-1 \} $, che rappresenta una $N funzione booleana reversibile $-variable.</span><span class="sxs-lookup"><span data-stu-id="b10ee-108">Input is a permutation $\pi$ over $2^n$ elements $\{0, \dots, 2^n-1\}$, which represents an $n$-variable reversible Boolean function.</span></span>
<span data-ttu-id="b10ee-109">L'algoritmo esegue in modo iterativo i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b10ee-109">The algorithm performs iteratively the following steps:</span></span>

1. <span data-ttu-id="b10ee-110">Trova il più piccolo $x $ in modo che $x \ne \Pi (x) = y $.</span><span class="sxs-lookup"><span data-stu-id="b10ee-110">Find smallest $x$ such that $x \ne \pi(x) = y$.</span></span>
2. <span data-ttu-id="b10ee-111">Trovare le operazioni Toffoli a più controlli, che sono state applicate agli output make $ \Pi (x) = x $ e non cambiano $ \Pi (x ') $ per tutti $x ' < x $</span><span class="sxs-lookup"><span data-stu-id="b10ee-111">Find multiple-controlled Toffoli operations, which applied to the outputs make $\pi(x) = x$ and do not change $\pi(x')$ for all $x' < x$</span></span>

## <a name="input"></a><span data-ttu-id="b10ee-112">Input</span><span class="sxs-lookup"><span data-stu-id="b10ee-112">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="b10ee-113">Perm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="b10ee-113">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="b10ee-114">Permutazione di $2 ^ n $ elementi a partire da 0.</span><span class="sxs-lookup"><span data-stu-id="b10ee-114">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="b10ee-115">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b10ee-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b10ee-116">Elenco di $n $ qubits a cui viene applicata la permutazione.</span><span class="sxs-lookup"><span data-stu-id="b10ee-116">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b10ee-117">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b10ee-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="b10ee-118">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="b10ee-118">References</span></span>

- [<span data-ttu-id="b10ee-119">*D. Michael Miller*, *Dmitri Maslov*, *Gerhard W. Dueck*, proc. DAC 2003, IEEE, pp. 318-323, 2003</span><span class="sxs-lookup"><span data-stu-id="b10ee-119">*D. Michael Miller*, *Dmitri Maslov*, *Gerhard W. Dueck*, Proc. DAC 2003, IEEE, pp. 318-323, 2003</span></span>](https://doi.org/10.1145/775832.775915)
- [<span data-ttu-id="b10ee-120">*Mathias Soeken*, *Gerhard W. Dueck*, *D. Michael Miller*, proc. RC 2016, Springer, pp. 307-321, 2016</span><span class="sxs-lookup"><span data-stu-id="b10ee-120">*Mathias Soeken*, *Gerhard W. Dueck*, *D. Michael Miller*, Proc. RC 2016, Springer, pp. 307-321, 2016</span></span>](https://doi.org/10.1007/978-3-319-40578-0_22)

## <a name="see-also"></a><span data-ttu-id="b10ee-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b10ee-121">See Also</span></span>

- [<span data-ttu-id="b10ee-122">Microsoft. Quantum. Synthesis. ApplyPermutationUsingDecomposition</span><span class="sxs-lookup"><span data-stu-id="b10ee-122">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)