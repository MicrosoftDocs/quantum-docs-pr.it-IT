---
uid: Microsoft.Quantum.Simulation.SumGeneratorSystems
title: SumGeneratorSystems (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: SumGeneratorSystems
qsharp.summary: Adds multiple `GeneratorSystem`s to create a new GeneratorSystem.
ms.openlocfilehash: b667a6af313b5bb8950a34a6d0406976bde49311
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719883"
---
# <a name="sumgeneratorsystems-function"></a><span data-ttu-id="4dbec-102">SumGeneratorSystems (funzione)</span><span class="sxs-lookup"><span data-stu-id="4dbec-102">SumGeneratorSystems function</span></span>

<span data-ttu-id="4dbec-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="4dbec-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="4dbec-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4dbec-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4dbec-105">Aggiunge più istanze `GeneratorSystem` di per creare un nuovo GeneratorSystem.</span><span class="sxs-lookup"><span data-stu-id="4dbec-105">Adds multiple `GeneratorSystem`s to create a new GeneratorSystem.</span></span>

```qsharp
function SumGeneratorSystems (generatorSystems : Microsoft.Quantum.Simulation.GeneratorSystem[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="4dbec-106">Input</span><span class="sxs-lookup"><span data-stu-id="4dbec-106">Input</span></span>

### <a name="generatorsystems--generatorsystem"></a><span data-ttu-id="4dbec-107">generatorSystems: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)[]</span><span class="sxs-lookup"><span data-stu-id="4dbec-107">generatorSystems : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)[]</span></span>

<span data-ttu-id="4dbec-108">Matrice di tipo `GeneratorSystem[]`.</span><span class="sxs-lookup"><span data-stu-id="4dbec-108">An array of type `GeneratorSystem[]`.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="4dbec-109">Output: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="4dbec-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="4dbec-110">Oggetto `GeneratorSystem` che rappresenta un sistema che rappresenta la somma dei sistemi del generatore di input.</span><span class="sxs-lookup"><span data-stu-id="4dbec-110">A `GeneratorSystem` representing a system that is the sum of the input generator systems.</span></span>

## <a name="see-also"></a><span data-ttu-id="4dbec-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4dbec-111">See Also</span></span>

- [<span data-ttu-id="4dbec-112">Microsoft. Quantum. Simulation. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="4dbec-112">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)