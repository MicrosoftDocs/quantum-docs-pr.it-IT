---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition
title: Operazione ApplyPermutationUsingDecomposition
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecomposition
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: 765b6d301363021f5b57a22f90e2ada38c9c09ec
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857402"
---
# <a name="applypermutationusingdecomposition-operation"></a><span data-ttu-id="6ac7a-102">Operazione ApplyPermutationUsingDecomposition</span><span class="sxs-lookup"><span data-stu-id="6ac7a-102">ApplyPermutationUsingDecomposition operation</span></span>

<span data-ttu-id="6ac7a-103">Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="6ac7a-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="6ac7a-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6ac7a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6ac7a-105">Permuta le ampiezze in uno stato quantum data una permutazione usando la sintesi basata sulla scomposizione.</span><span class="sxs-lookup"><span data-stu-id="6ac7a-105">Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingDecomposition (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="6ac7a-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6ac7a-106">Description</span></span>

<span data-ttu-id="6ac7a-107">Questa procedura implementa l'approccio di sintesi basato sulla scomposizione.</span><span class="sxs-lookup"><span data-stu-id="6ac7a-107">This procedure implements the decomposition based synthesis approach.</span></span>  <span data-ttu-id="6ac7a-108">L'input è una permutazione $ \Pi $ oltre $2 ^ n $ Elements $ \{ 0, \dots, 2 ^ n-1 \} $, che rappresenta una $N funzione booleana reversibile $-variable.</span><span class="sxs-lookup"><span data-stu-id="6ac7a-108">The input is a permutation $\pi$ over $2^n$ elements $\{0, \dots, 2^n-1\}$, which represents an $n$-variable reversible Boolean function.</span></span>
<span data-ttu-id="6ac7a-109">L'algoritmo esegue in modo iterativo i passaggi seguenti per ogni indice di variabile $i $:</span><span class="sxs-lookup"><span data-stu-id="6ac7a-109">The algorithm iteratively performs the following steps for each variable index $i$:</span></span>

1. <span data-ttu-id="6ac7a-110">Compute $ ((\ pi_l, \ pi_r), \Pi ') $ in modo che le immagini di $ \ pi_l $ e $ \ pi_r $ non modifichino i bit nei rispettivi elementi con indici diversi da $i $ e immagini di $ \Pi ' $ non cambiano bit $i $ nei relativi elementi.</span><span class="sxs-lookup"><span data-stu-id="6ac7a-110">Compute $((\pi_l, \pi_r), \pi')$ such that the images of $\pi_l$ and $\pi_r$ do not change bits in their elements at indexes other than $i$ and images of $\pi'$ do not change bit $i$ in their elements.</span></span>
2. <span data-ttu-id="6ac7a-111">Impostare $ \Pi \leftarrow \Pi ' $ e derivare le tabelle di verità da $ \ pi_l $ e $ \ pi_r $ in base a elementi che non sono punti fissi.</span><span class="sxs-lookup"><span data-stu-id="6ac7a-111">Set $\pi \leftarrow \pi'$, and derive truth tables from $\pi_l$ and $\pi_r$ based on elements that are not fixed-points.</span></span>

<span data-ttu-id="6ac7a-112">Dopo aver applicato questi passaggi per tutti gli indici delle variabili, la permutazione rimanente $ \Pi $ sarà l'identità e, in base agli indici e alle tabelle di verità raccolte, è possibile applicare le operazioni controllate dalla tabella di verità @"microsoft.quantum.intrinsic.x" usando l' @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" operazione.</span><span class="sxs-lookup"><span data-stu-id="6ac7a-112">After applying these steps for all variable indexes, the remaining permutation $\pi$ will be the identity, and based on the collected truth tables and indexes, one can apply truth-table controlled @"microsoft.quantum.intrinsic.x" operations using the @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" operation.</span></span>

<span data-ttu-id="6ac7a-113">L'ordine della variabile è $0, \dots, n-$1.</span><span class="sxs-lookup"><span data-stu-id="6ac7a-113">The variable order is $0, \dots, n - 1$.</span></span>  <span data-ttu-id="6ac7a-114">Nell'operazione è possibile specificare un ordine di variabili personalizzato @"microsoft.quantum.synthesis.applypermutationusingdecompositionwithvariableorder" .</span><span class="sxs-lookup"><span data-stu-id="6ac7a-114">A custom variable order can be specified in the operation @"microsoft.quantum.synthesis.applypermutationusingdecompositionwithvariableorder".</span></span>

## <a name="input"></a><span data-ttu-id="6ac7a-115">Input</span><span class="sxs-lookup"><span data-stu-id="6ac7a-115">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="6ac7a-116">Perm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="6ac7a-116">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="6ac7a-117">Permutazione di $2 ^ n $ elementi a partire da 0.</span><span class="sxs-lookup"><span data-stu-id="6ac7a-117">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="6ac7a-118">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="6ac7a-118">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="6ac7a-119">Elenco di $n $ qubits a cui viene applicata la permutazione.</span><span class="sxs-lookup"><span data-stu-id="6ac7a-119">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6ac7a-120">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6ac7a-120">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="6ac7a-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="6ac7a-121">Example</span></span>

<span data-ttu-id="6ac7a-122">Per sintetizzare un' `SWAP` operazione:</span><span class="sxs-lookup"><span data-stu-id="6ac7a-122">To synthesize a `SWAP` operation:</span></span>

```qsharp
using (qubits = Qubit[2]) {
  ApplyPermutationUsingDecomposition([0, 2, 1, 3], LittleEndian(qubits));
}
```

## <a name="references"></a><span data-ttu-id="6ac7a-123">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="6ac7a-123">References</span></span>

- [<span data-ttu-id="6ac7a-124">*Alexis de vos*, *Yvan van Rentergem*, ADV. in Math. of comm. 2 (2), 2008, pp. 183--200</span><span class="sxs-lookup"><span data-stu-id="6ac7a-124">*Alexis De Vos*, *Yvan Van Rentergem*, Adv. in Math. of Comm. 2(2), 2008, pp. 183--200</span></span>](http://www.aimsciences.org/article/doi/10.3934/amc.2008.2.183)
- [<span data-ttu-id="6ac7a-125">*Mathias Soeken*, *Laura Tague*, *Gerhard W. Dueck*, *Rolf Drechsler*, Journal of simbologie computing 73 (2016), pp. 1--26</span><span class="sxs-lookup"><span data-stu-id="6ac7a-125">*Mathias Soeken*, *Laura Tague*, *Gerhard W. Dueck*, *Rolf Drechsler*, Journal of Symbolic Computation 73 (2016), pp. 1--26</span></span>](https://www.sciencedirect.com/science/article/pii/S0747717115000188?via%3Dihub)

## <a name="see-also"></a><span data-ttu-id="6ac7a-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ac7a-126">See Also</span></span>

- [<span data-ttu-id="6ac7a-127">Microsoft. Quantum. Synthesis. ApplyPermutationUsingDecompositionWithVariableOrder</span><span class="sxs-lookup"><span data-stu-id="6ac7a-127">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder)
- [<span data-ttu-id="6ac7a-128">Microsoft. Quantum. Synthesis. ApplyPermutationUsingTransformation</span><span class="sxs-lookup"><span data-stu-id="6ac7a-128">Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)