---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorSystem
title: MultiplyGeneratorSystem (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorSystem
qsharp.summary: Multiplies the coefficient of all terms in a `GeneratorSystem`.
ms.openlocfilehash: effb9e3ca754f77bbe1ea0fb6ca30ae49e92d531
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229155"
---
# <a name="multiplygeneratorsystem-function"></a><span data-ttu-id="f1879-102">MultiplyGeneratorSystem (funzione)</span><span class="sxs-lookup"><span data-stu-id="f1879-102">MultiplyGeneratorSystem function</span></span>

<span data-ttu-id="f1879-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="f1879-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="f1879-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f1879-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f1879-105">Moltiplica il coefficiente di tutti i termini in un oggetto `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="f1879-105">Multiplies the coefficient of all terms in a `GeneratorSystem`.</span></span>

```qsharp
function MultiplyGeneratorSystem (multiplier : Double, generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="f1879-106">Input</span><span class="sxs-lookup"><span data-stu-id="f1879-106">Input</span></span>

### <a name="multiplier--double"></a><span data-ttu-id="f1879-107">moltiplicatore: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f1879-107">multiplier : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f1879-108">Moltiplicatore sul coefficiente.</span><span class="sxs-lookup"><span data-stu-id="f1879-108">The multiplier on the coefficient.</span></span>


### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="f1879-109">generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="f1879-109">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="f1879-110">Struttura `GeneratorSystem` da moltiplicare.</span><span class="sxs-lookup"><span data-stu-id="f1879-110">The `GeneratorSystem` to be multiplied.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="f1879-111">Output: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="f1879-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="f1879-112">Oggetto `GeneratorSystem` che rappresenta un sistema con coefficienti di un fattore `multiplier` più grande.</span><span class="sxs-lookup"><span data-stu-id="f1879-112">A `GeneratorSystem` representing a system with coefficients a factor `multiplier` larger.</span></span>

## <a name="see-also"></a><span data-ttu-id="f1879-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1879-113">See Also</span></span>

- [<span data-ttu-id="f1879-114">Microsoft. Quantum. Simulation. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="f1879-114">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)