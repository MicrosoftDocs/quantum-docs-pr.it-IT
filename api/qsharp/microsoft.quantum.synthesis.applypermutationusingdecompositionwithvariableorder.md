---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder
title: Operazione ApplyPermutationUsingDecompositionWithVariableOrder
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecompositionWithVariableOrder
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: a5ca9b366f7ff477070e21fea047ff04b425439c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203434"
---
# <a name="applypermutationusingdecompositionwithvariableorder-operation"></a><span data-ttu-id="34b55-102">Operazione ApplyPermutationUsingDecompositionWithVariableOrder</span><span class="sxs-lookup"><span data-stu-id="34b55-102">ApplyPermutationUsingDecompositionWithVariableOrder operation</span></span>

<span data-ttu-id="34b55-103">Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="34b55-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="34b55-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="34b55-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="34b55-105">Permuta le ampiezze in uno stato quantum data una permutazione usando la sintesi basata sulla scomposizione.</span><span class="sxs-lookup"><span data-stu-id="34b55-105">Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingDecompositionWithVariableOrder (perm : Int[], variableOrder : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="34b55-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="34b55-106">Description</span></span>

<span data-ttu-id="34b55-107">Questa operazione è una versione più generale di @"microsoft.quantum.synthesis.applypermutationusingdecomposition" in cui è possibile specificare l'ordine delle variabili.</span><span class="sxs-lookup"><span data-stu-id="34b55-107">This operation is a more general version of @"microsoft.quantum.synthesis.applypermutationusingdecomposition" in which the variable order can be specified.</span></span> <span data-ttu-id="34b55-108">Un ordine variabile diverso modifica la sequenza di scomposizione e le tabelle di verità usate per le attività di controllo @"microsoft.quantum.intrinsic.x" .</span><span class="sxs-lookup"><span data-stu-id="34b55-108">A different variable order changes the decomposition sequence and the truth tables used for the controlled @"microsoft.quantum.intrinsic.x" gates.</span></span>  <span data-ttu-id="34b55-109">Pertanto, la modifica dell'ordine delle variabili cambia il numero di controlli generali utilizzati per realizzare la permutazione.</span><span class="sxs-lookup"><span data-stu-id="34b55-109">Therefore, changing the variable order changes the number of overall gates used to realize the permutation.</span></span>

## <a name="input"></a><span data-ttu-id="34b55-110">Input</span><span class="sxs-lookup"><span data-stu-id="34b55-110">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="34b55-111">Perm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="34b55-111">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="34b55-112">Permutazione di $2 ^ n $ elementi a partire da 0.</span><span class="sxs-lookup"><span data-stu-id="34b55-112">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="variableorder--int"></a><span data-ttu-id="34b55-113">variableOrder: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="34b55-113">variableOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="34b55-114">Permutazione di $n $ Elements a partire da 0.</span><span class="sxs-lookup"><span data-stu-id="34b55-114">A permutation of $n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="34b55-115">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="34b55-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="34b55-116">Elenco di $n $ qubits a cui viene applicata la permutazione.</span><span class="sxs-lookup"><span data-stu-id="34b55-116">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="34b55-117">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="34b55-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="34b55-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34b55-118">See Also</span></span>

- [<span data-ttu-id="34b55-119">Microsoft. Quantum. Synthesis. ApplyPermutationUsingDecomposition</span><span class="sxs-lookup"><span data-stu-id="34b55-119">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)
- [<span data-ttu-id="34b55-120">Microsoft. Quantum. Synthesis. ApplyPermutationUsingTransformation</span><span class="sxs-lookup"><span data-stu-id="34b55-120">Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)