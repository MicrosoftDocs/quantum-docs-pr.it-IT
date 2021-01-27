---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder
title: Operazione ApplyPermutationUsingDecompositionWithVariableOrder
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecompositionWithVariableOrder
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: f33d2980ff1775b1ae8d2e2e7a4fa1e5cbe7d5ba
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858872"
---
# <a name="applypermutationusingdecompositionwithvariableorder-operation"></a><span data-ttu-id="53181-102">Operazione ApplyPermutationUsingDecompositionWithVariableOrder</span><span class="sxs-lookup"><span data-stu-id="53181-102">ApplyPermutationUsingDecompositionWithVariableOrder operation</span></span>

<span data-ttu-id="53181-103">Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="53181-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="53181-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="53181-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="53181-105">Permuta le ampiezze in uno stato quantum data una permutazione usando la sintesi basata sulla scomposizione.</span><span class="sxs-lookup"><span data-stu-id="53181-105">Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingDecompositionWithVariableOrder (perm : Int[], variableOrder : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="53181-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53181-106">Description</span></span>

<span data-ttu-id="53181-107">Questa operazione è una versione più generale di @"microsoft.quantum.synthesis.applypermutationusingdecomposition" in cui è possibile specificare l'ordine delle variabili.</span><span class="sxs-lookup"><span data-stu-id="53181-107">This operation is a more general version of @"microsoft.quantum.synthesis.applypermutationusingdecomposition" in which the variable order can be specified.</span></span> <span data-ttu-id="53181-108">Un ordine variabile diverso modifica la sequenza di scomposizione e le tabelle di verità usate per le attività di controllo @"microsoft.quantum.intrinsic.x" .</span><span class="sxs-lookup"><span data-stu-id="53181-108">A different variable order changes the decomposition sequence and the truth tables used for the controlled @"microsoft.quantum.intrinsic.x" gates.</span></span>  <span data-ttu-id="53181-109">Pertanto, la modifica dell'ordine delle variabili cambia il numero di controlli generali utilizzati per realizzare la permutazione.</span><span class="sxs-lookup"><span data-stu-id="53181-109">Therefore, changing the variable order changes the number of overall gates used to realize the permutation.</span></span>

## <a name="input"></a><span data-ttu-id="53181-110">Input</span><span class="sxs-lookup"><span data-stu-id="53181-110">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="53181-111">Perm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="53181-111">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="53181-112">Permutazione di $2 ^ n $ elementi a partire da 0.</span><span class="sxs-lookup"><span data-stu-id="53181-112">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="variableorder--int"></a><span data-ttu-id="53181-113">variableOrder: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="53181-113">variableOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="53181-114">Permutazione di $n $ Elements a partire da 0.</span><span class="sxs-lookup"><span data-stu-id="53181-114">A permutation of $n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="53181-115">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="53181-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="53181-116">Elenco di $n $ qubits a cui viene applicata la permutazione.</span><span class="sxs-lookup"><span data-stu-id="53181-116">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="53181-117">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="53181-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="53181-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="53181-118">Example</span></span>

<span data-ttu-id="53181-119">Per sintetizzare un' `SWAP` operazione:</span><span class="sxs-lookup"><span data-stu-id="53181-119">To synthesize a `SWAP` operation:</span></span>

```qsharp
using (qubits = Qubit[2]) {
  ApplyPermutationUsingDecompositionWithVariableOrder([0, 2, 1, 3], [1, 0], LittleEndian(qubits));
}
```

## <a name="see-also"></a><span data-ttu-id="53181-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53181-120">See Also</span></span>

- [<span data-ttu-id="53181-121">Microsoft. Quantum. Synthesis. ApplyPermutationUsingDecomposition</span><span class="sxs-lookup"><span data-stu-id="53181-121">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)
- [<span data-ttu-id="53181-122">Microsoft. Quantum. Synthesis. ApplyPermutationUsingTransformation</span><span class="sxs-lookup"><span data-stu-id="53181-122">Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)