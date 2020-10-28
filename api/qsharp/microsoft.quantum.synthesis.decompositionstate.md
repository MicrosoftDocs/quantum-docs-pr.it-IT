---
uid: Microsoft.Quantum.Synthesis.DecompositionState
title: Tipo definito dall'utente DecompositionState
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecompositionState
qsharp.summary: State during decomposition based on variable indexes
ms.openlocfilehash: 0547c04828a80b4f696cc17e13c8cc57d0379f96
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725210"
---
# <a name="decompositionstate-user-defined-type"></a><span data-ttu-id="6567a-102">Tipo definito dall'utente DecompositionState</span><span class="sxs-lookup"><span data-stu-id="6567a-102">DecompositionState user defined type</span></span>

<span data-ttu-id="6567a-103">Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="6567a-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="6567a-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6567a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6567a-105">Stato durante la scomposizione in base agli indici delle variabili</span><span class="sxs-lookup"><span data-stu-id="6567a-105">State during decomposition based on variable indexes</span></span>

```qsharp

newtype DecompositionState = (Perm : Int[], Lfunctions : (BigInt, Int)[], Rfunctions : (BigInt, Int)[]);
```



## <a name="named-items"></a><span data-ttu-id="6567a-106">Elementi denominati</span><span class="sxs-lookup"><span data-stu-id="6567a-106">Named Items</span></span>

### <a name="perm--int"></a><span data-ttu-id="6567a-107">Perm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="6567a-107">Perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>


### <a name="lfunctions--bigintint"></a><span data-ttu-id="6567a-108">Lfunctions: ([bigint](xref:microsoft.quantum.lang-ref.bigint),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="6567a-108">Lfunctions : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>


### <a name="rfunctions--bigintint"></a><span data-ttu-id="6567a-109">Rfunctions: ([bigint](xref:microsoft.quantum.lang-ref.bigint),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="6567a-109">Rfunctions : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>



## <a name="description"></a><span data-ttu-id="6567a-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6567a-110">Description</span></span>

<span data-ttu-id="6567a-111">Lo stato include la permutazione corrente e le funzioni attualmente generate per i cancelli controllati a sinistra e i cancelli controllati a destra.</span><span class="sxs-lookup"><span data-stu-id="6567a-111">The state holds the current permutation and the currently generated functions for controlled gates on the left, and controlled gates on the right.</span></span>