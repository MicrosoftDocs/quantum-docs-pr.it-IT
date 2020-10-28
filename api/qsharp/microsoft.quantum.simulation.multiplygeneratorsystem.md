---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorSystem
title: MultiplyGeneratorSystem (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorSystem
qsharp.summary: Multiplies the coefficient of all terms in a `GeneratorSystem`.
ms.openlocfilehash: 1d28de99dab3f7aca4bf3706fe98f5ef7c5286a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720234"
---
# <a name="multiplygeneratorsystem-function"></a><span data-ttu-id="f79af-102">MultiplyGeneratorSystem (funzione)</span><span class="sxs-lookup"><span data-stu-id="f79af-102">MultiplyGeneratorSystem function</span></span>

<span data-ttu-id="f79af-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="f79af-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="f79af-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f79af-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f79af-105">Moltiplica il coefficiente di tutti i termini in un oggetto `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="f79af-105">Multiplies the coefficient of all terms in a `GeneratorSystem`.</span></span>

```qsharp
function MultiplyGeneratorSystem (multiplier : Double, generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="f79af-106">Input</span><span class="sxs-lookup"><span data-stu-id="f79af-106">Input</span></span>

### <a name="multiplier--double"></a><span data-ttu-id="f79af-107">moltiplicatore: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f79af-107">multiplier : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f79af-108">Moltiplicatore sul coefficiente.</span><span class="sxs-lookup"><span data-stu-id="f79af-108">The multiplier on the coefficient.</span></span>


### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="f79af-109">generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="f79af-109">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="f79af-110">Struttura `GeneratorSystem` da moltiplicare.</span><span class="sxs-lookup"><span data-stu-id="f79af-110">The `GeneratorSystem` to be multiplied.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="f79af-111">Output: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="f79af-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="f79af-112">Oggetto `GeneratorSystem` che rappresenta un sistema con coefficienti di un fattore `multiplier` più grande.</span><span class="sxs-lookup"><span data-stu-id="f79af-112">A `GeneratorSystem` representing a system with coefficients a factor `multiplier` larger.</span></span>

## <a name="see-also"></a><span data-ttu-id="f79af-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f79af-113">See Also</span></span>

- [<span data-ttu-id="f79af-114">Microsoft. Quantum. Simulation. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="f79af-114">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)