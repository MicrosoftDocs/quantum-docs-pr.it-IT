---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorIndex
title: MultiplyGeneratorIndex (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorIndex
qsharp.summary: Multiplies the coefficient in a `GeneratorIndex`.
ms.openlocfilehash: dc2bd02c40b53eca726f70578e3c5918add8f1bb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230447"
---
# <a name="multiplygeneratorindex-function"></a><span data-ttu-id="83b25-102">MultiplyGeneratorIndex (funzione)</span><span class="sxs-lookup"><span data-stu-id="83b25-102">MultiplyGeneratorIndex function</span></span>

<span data-ttu-id="83b25-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="83b25-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="83b25-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="83b25-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="83b25-105">Moltiplica il coefficiente in un oggetto `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="83b25-105">Multiplies the coefficient in a `GeneratorIndex`.</span></span>

```qsharp
function MultiplyGeneratorIndex (multiplier : Double, generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="83b25-106">Input</span><span class="sxs-lookup"><span data-stu-id="83b25-106">Input</span></span>

### <a name="multiplier--double"></a><span data-ttu-id="83b25-107">moltiplicatore: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="83b25-107">multiplier : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="83b25-108">Moltiplicatore sul coefficiente.</span><span class="sxs-lookup"><span data-stu-id="83b25-108">The multiplier on the coefficient.</span></span>


### <a name="generatorindex--generatorindex"></a><span data-ttu-id="83b25-109">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="83b25-109">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="83b25-110">Struttura `GeneratorIndex` da moltiplicare.</span><span class="sxs-lookup"><span data-stu-id="83b25-110">The `GeneratorIndex` to be multiplied.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="83b25-111">Output: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="83b25-111">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="83b25-112">Oggetto `GeneratorIndex` che rappresenta un termine con un fattore più grande del coefficiente `multiplier` .</span><span class="sxs-lookup"><span data-stu-id="83b25-112">A `GeneratorIndex` representing a term with coefficient a factor `multiplier` larger.</span></span>

## <a name="see-also"></a><span data-ttu-id="83b25-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83b25-113">See Also</span></span>

- [<span data-ttu-id="83b25-114">Microsoft. Quantum. Simulation. GeneratorIndex</span><span class="sxs-lookup"><span data-stu-id="83b25-114">Microsoft.Quantum.Simulation.GeneratorIndex</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorIndex)