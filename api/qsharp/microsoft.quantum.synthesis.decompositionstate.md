---
uid: Microsoft.Quantum.Synthesis.DecompositionState
title: Tipo definito dall'utente DecompositionState
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecompositionState
qsharp.summary: State during decomposition based on variable indexes
ms.openlocfilehash: eb2aed53b4116a4ea72ee732ff46c4a10eb3d67b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855513"
---
# <a name="decompositionstate-user-defined-type"></a><span data-ttu-id="7c73e-102">Tipo definito dall'utente DecompositionState</span><span class="sxs-lookup"><span data-stu-id="7c73e-102">DecompositionState user defined type</span></span>

<span data-ttu-id="7c73e-103">Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="7c73e-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="7c73e-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7c73e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7c73e-105">Stato durante la scomposizione in base agli indici delle variabili</span><span class="sxs-lookup"><span data-stu-id="7c73e-105">State during decomposition based on variable indexes</span></span>

```qsharp

newtype DecompositionState = (Perm : Int[], Lfunctions : (BigInt, Int)[], Rfunctions : (BigInt, Int)[]);
```



## <a name="named-items"></a><span data-ttu-id="7c73e-106">Elementi denominati</span><span class="sxs-lookup"><span data-stu-id="7c73e-106">Named Items</span></span>

### <a name="perm--int"></a><span data-ttu-id="7c73e-107">Perm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="7c73e-107">Perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>


### <a name="lfunctions--bigintint"></a><span data-ttu-id="7c73e-108">Lfunctions: ([bigint](xref:microsoft.quantum.lang-ref.bigint),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="7c73e-108">Lfunctions : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>


### <a name="rfunctions--bigintint"></a><span data-ttu-id="7c73e-109">Rfunctions: ([bigint](xref:microsoft.quantum.lang-ref.bigint),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="7c73e-109">Rfunctions : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>



## <a name="description"></a><span data-ttu-id="7c73e-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7c73e-110">Description</span></span>

<span data-ttu-id="7c73e-111">Lo stato include la permutazione corrente e le funzioni attualmente generate per i cancelli controllati a sinistra e i cancelli controllati a destra.</span><span class="sxs-lookup"><span data-stu-id="7c73e-111">The state holds the current permutation and the currently generated functions for controlled gates on the left, and controlled gates on the right.</span></span>