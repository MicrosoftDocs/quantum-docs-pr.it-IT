---
uid: Microsoft.Quantum.Simulation.IdxToUnitary
title: IdxToUnitary (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdxToUnitary
qsharp.summary: Used in implementation of `PauliBlockEncoding`
ms.openlocfilehash: dd13b2d2e846dcddb820599ea26aa25b90903dbd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229274"
---
# <a name="idxtounitary-function"></a><span data-ttu-id="052a1-102">IdxToUnitary (funzione)</span><span class="sxs-lookup"><span data-stu-id="052a1-102">IdxToUnitary function</span></span>

<span data-ttu-id="052a1-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="052a1-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="052a1-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="052a1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="052a1-105">Usato nell'implementazione di `PauliBlockEncoding`</span><span class="sxs-lookup"><span data-stu-id="052a1-105">Used in implementation of `PauliBlockEncoding`</span></span>

```qsharp
function IdxToUnitary (idx : Int, genFun : (Int -> Microsoft.Quantum.Simulation.GeneratorIndex), genIdxToUnitary : (Microsoft.Quantum.Simulation.GeneratorIndex -> (Qubit[] => Unit is Adj + Ctl))) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="052a1-106">Input</span><span class="sxs-lookup"><span data-stu-id="052a1-106">Input</span></span>

### <a name="idx--int"></a><span data-ttu-id="052a1-107">idx: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="052a1-107">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="genfun--int---generatorindex"></a><span data-ttu-id="052a1-108">genFun: [int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="052a1-108">genFun : [Int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>




### <a name="genidxtounitary--generatorindex---qubit--unit--is-adj--ctl"></a><span data-ttu-id="052a1-109">genIdxToUnitary: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex) -> [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="052a1-109">genIdxToUnitary : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex) -> [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>





## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="052a1-110">Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="052a1-110">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>



## <a name="see-also"></a><span data-ttu-id="052a1-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="052a1-111">See Also</span></span>

- [<span data-ttu-id="052a1-112">Microsoft. Quantum. Simulation. PauliBlockEncoding</span><span class="sxs-lookup"><span data-stu-id="052a1-112">Microsoft.Quantum.Simulation.PauliBlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.PauliBlockEncoding)