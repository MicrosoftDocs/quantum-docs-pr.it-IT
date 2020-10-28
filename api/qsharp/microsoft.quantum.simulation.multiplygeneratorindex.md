---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorIndex
title: MultiplyGeneratorIndex (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorIndex
qsharp.summary: Multiplies the coefficient in a `GeneratorIndex`.
ms.openlocfilehash: 9ee0568073b65b027cc98eb56934e9286b59c27f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724493"
---
# <a name="multiplygeneratorindex-function"></a><span data-ttu-id="e4e47-102">MultiplyGeneratorIndex (funzione)</span><span class="sxs-lookup"><span data-stu-id="e4e47-102">MultiplyGeneratorIndex function</span></span>

<span data-ttu-id="e4e47-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="e4e47-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="e4e47-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e4e47-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e4e47-105">Moltiplica il coefficiente in un oggetto `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="e4e47-105">Multiplies the coefficient in a `GeneratorIndex`.</span></span>

```qsharp
function MultiplyGeneratorIndex (multiplier : Double, generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="e4e47-106">Input</span><span class="sxs-lookup"><span data-stu-id="e4e47-106">Input</span></span>

### <a name="multiplier--double"></a><span data-ttu-id="e4e47-107">moltiplicatore: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e4e47-107">multiplier : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e4e47-108">Moltiplicatore sul coefficiente.</span><span class="sxs-lookup"><span data-stu-id="e4e47-108">The multiplier on the coefficient.</span></span>


### <a name="generatorindex--generatorindex"></a><span data-ttu-id="e4e47-109">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="e4e47-109">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="e4e47-110">Struttura `GeneratorIndex` da moltiplicare.</span><span class="sxs-lookup"><span data-stu-id="e4e47-110">The `GeneratorIndex` to be multiplied.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="e4e47-111">Output: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="e4e47-111">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="e4e47-112">Oggetto `GeneratorIndex` che rappresenta un termine con un fattore più grande del coefficiente `multiplier` .</span><span class="sxs-lookup"><span data-stu-id="e4e47-112">A `GeneratorIndex` representing a term with coefficient a factor `multiplier` larger.</span></span>

## <a name="see-also"></a><span data-ttu-id="e4e47-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4e47-113">See Also</span></span>

- [<span data-ttu-id="e4e47-114">Microsoft. Quantum. Simulation. GeneratorIndex</span><span class="sxs-lookup"><span data-stu-id="e4e47-114">Microsoft.Quantum.Simulation.GeneratorIndex</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorIndex)