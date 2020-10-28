---
uid: Microsoft.Quantum.Simulation.TrotterSimulationAlgorithm
title: TrotterSimulationAlgorithm (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterSimulationAlgorithm
qsharp.summary: '`SimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate the time-evolution operator _exp(-iHt)_.'
ms.openlocfilehash: c52acf293e69c78e7a82b0cf5d94de52d0f5a293
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719862"
---
# <a name="trottersimulationalgorithm-function"></a><span data-ttu-id="8398a-102">TrotterSimulationAlgorithm (funzione)</span><span class="sxs-lookup"><span data-stu-id="8398a-102">TrotterSimulationAlgorithm function</span></span>

<span data-ttu-id="8398a-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="8398a-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="8398a-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8398a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8398a-105">`SimulationAlgorithm` funzione che usa una scomposizione Trotter – Suzuki per approssimare l'operatore _Exp (-iHt)_ dell'evoluzione del tempo.</span><span class="sxs-lookup"><span data-stu-id="8398a-105">`SimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate the time-evolution operator _exp(-iHt)_ .</span></span>

```qsharp
function TrotterSimulationAlgorithm (trotterStepSize : Double, trotterOrder : Int) : Microsoft.Quantum.Simulation.SimulationAlgorithm
```


## <a name="input"></a><span data-ttu-id="8398a-106">Input</span><span class="sxs-lookup"><span data-stu-id="8398a-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="8398a-107">trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8398a-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8398a-108">Durata dell'evoluzione del tempo simulato in un singolo passaggio Trotter.</span><span class="sxs-lookup"><span data-stu-id="8398a-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="8398a-109">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8398a-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8398a-110">Ordine di Trotter Integrator.</span><span class="sxs-lookup"><span data-stu-id="8398a-110">Order of Trotter integrator.</span></span> <span data-ttu-id="8398a-111">Deve essere 1 o un numero pari.</span><span class="sxs-lookup"><span data-stu-id="8398a-111">This must be either 1 or an even number.</span></span>



## <a name="output--simulationalgorithm"></a><span data-ttu-id="8398a-112">Output: [SimulationAlgorithm](xref:Microsoft.Quantum.Simulation.SimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="8398a-112">Output : [SimulationAlgorithm](xref:Microsoft.Quantum.Simulation.SimulationAlgorithm)</span></span>

<span data-ttu-id="8398a-113">Tipo `SimulationAlgorithm`.</span><span class="sxs-lookup"><span data-stu-id="8398a-113">A `SimulationAlgorithm` type.</span></span>