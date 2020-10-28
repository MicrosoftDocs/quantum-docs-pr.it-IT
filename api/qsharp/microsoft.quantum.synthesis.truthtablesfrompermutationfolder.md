---
uid: Microsoft.Quantum.Synthesis.TruthTablesFromPermutationFolder
title: TruthTablesFromPermutationFolder (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: TruthTablesFromPermutationFolder
qsharp.summary: Decomposition logic for a single variable index
ms.openlocfilehash: 6b00c9e880ed7b7b3bf446dcb17dab3bab7a83a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724454"
---
# <a name="truthtablesfrompermutationfolder-function"></a><span data-ttu-id="c5ebe-102">TruthTablesFromPermutationFolder (funzione)</span><span class="sxs-lookup"><span data-stu-id="c5ebe-102">TruthTablesFromPermutationFolder function</span></span>

<span data-ttu-id="c5ebe-103">Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="c5ebe-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="c5ebe-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c5ebe-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c5ebe-105">Logica di scomposizione per un singolo indice di variabile</span><span class="sxs-lookup"><span data-stu-id="c5ebe-105">Decomposition logic for a single variable index</span></span>

```qsharp
function TruthTablesFromPermutationFolder (numVars : Int, state : Microsoft.Quantum.Synthesis.DecompositionState, index : Int) : Microsoft.Quantum.Synthesis.DecompositionState
```


## <a name="description"></a><span data-ttu-id="c5ebe-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c5ebe-106">Description</span></span>

<span data-ttu-id="c5ebe-107">Questo accetta lo stato corrente e genera una permutazione aggiornata ed eventualmente aggiunge nuove funzioni per le attività di controllo controllate.</span><span class="sxs-lookup"><span data-stu-id="c5ebe-107">This takes the current state and generates an updated permutation and possibly adds new functions for controlled gates.</span></span>

## <a name="input"></a><span data-ttu-id="c5ebe-108">Input</span><span class="sxs-lookup"><span data-stu-id="c5ebe-108">Input</span></span>

### <a name="numvars--int"></a><span data-ttu-id="c5ebe-109">numVars: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c5ebe-109">numVars : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="state--decompositionstate"></a><span data-ttu-id="c5ebe-110">stato: [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span><span class="sxs-lookup"><span data-stu-id="c5ebe-110">state : [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span></span>




### <a name="index--int"></a><span data-ttu-id="c5ebe-111">Indice: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c5ebe-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--decompositionstate"></a><span data-ttu-id="c5ebe-112">Output: [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span><span class="sxs-lookup"><span data-stu-id="c5ebe-112">Output : [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span></span>

