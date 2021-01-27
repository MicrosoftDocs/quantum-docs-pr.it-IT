---
uid: Microsoft.Quantum.Synthesis.FlipMasks
title: FlipMasks (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FlipMasks
qsharp.summary: For every 2-level unitary calculates "flip mask", which denotes qubits which should be inverted before and after applying corresponding 1-qubit gate. For convenience prepends result with 0.
ms.openlocfilehash: ca0ce69b3353379a42cc109cebb32efe4e364825
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859202"
---
# <a name="flipmasks-function"></a><span data-ttu-id="ee981-102">FlipMasks (funzione)</span><span class="sxs-lookup"><span data-stu-id="ee981-102">FlipMasks function</span></span>

<span data-ttu-id="ee981-103">Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="ee981-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="ee981-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ee981-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ee981-105">Per ogni unità a 2 livelli viene calcolato "Flip mask", che indica qubits che devono essere invertiti prima e dopo l'applicazione del controllo 1 qubit corrispondente.</span><span class="sxs-lookup"><span data-stu-id="ee981-105">For every 2-level unitary calculates "flip mask", which denotes qubits which should be inverted before and after applying corresponding 1-qubit gate.</span></span>
<span data-ttu-id="ee981-106">Per convenienza il risultato viene anteposto con 0.</span><span class="sxs-lookup"><span data-stu-id="ee981-106">For convenience prepends result with 0.</span></span>

```qsharp
function FlipMasks (decomposition : (Microsoft.Quantum.Math.Complex[][], Int, Int)[], allQubitsMask : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="ee981-107">Input</span><span class="sxs-lookup"><span data-stu-id="ee981-107">Input</span></span>

### <a name="decomposition--complexintint"></a><span data-ttu-id="ee981-108">scomposizione: ([complesso](xref:Microsoft.Quantum.Math.Complex)[] [],[int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="ee981-108">decomposition : ([Complex](xref:Microsoft.Quantum.Math.Complex)[][],[Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>




### <a name="allqubitsmask--int"></a><span data-ttu-id="ee981-109">allQubitsMask: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ee981-109">allQubitsMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="ee981-110">Output: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ee981-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

