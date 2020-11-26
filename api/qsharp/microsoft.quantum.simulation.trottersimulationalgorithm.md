---
uid: Microsoft.Quantum.Simulation.TrotterSimulationAlgorithm
title: TrotterSimulationAlgorithm (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterSimulationAlgorithm
qsharp.summary: '`SimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate the time-evolution operator _exp(-iHt)_.'
ms.openlocfilehash: aa8338ab359441765db72a12f84a3a51e5bee3ce
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192537"
---
# <a name="trottersimulationalgorithm-function"></a><span data-ttu-id="d2584-102">TrotterSimulationAlgorithm (funzione)</span><span class="sxs-lookup"><span data-stu-id="d2584-102">TrotterSimulationAlgorithm function</span></span>

<span data-ttu-id="d2584-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="d2584-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="d2584-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d2584-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d2584-105">`SimulationAlgorithm` funzione che usa una scomposizione Trotter – Suzuki per approssimare l'operatore _Exp (-iHt)_ dell'evoluzione del tempo.</span><span class="sxs-lookup"><span data-stu-id="d2584-105">`SimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate the time-evolution operator _exp(-iHt)_.</span></span>

```qsharp
function TrotterSimulationAlgorithm (trotterStepSize : Double, trotterOrder : Int) : Microsoft.Quantum.Simulation.SimulationAlgorithm
```


## <a name="input"></a><span data-ttu-id="d2584-106">Input</span><span class="sxs-lookup"><span data-stu-id="d2584-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="d2584-107">trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d2584-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d2584-108">Durata dell'evoluzione del tempo simulato in un singolo passaggio Trotter.</span><span class="sxs-lookup"><span data-stu-id="d2584-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="d2584-109">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d2584-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d2584-110">Ordine di Trotter Integrator.</span><span class="sxs-lookup"><span data-stu-id="d2584-110">Order of Trotter integrator.</span></span> <span data-ttu-id="d2584-111">Deve essere 1 o un numero pari.</span><span class="sxs-lookup"><span data-stu-id="d2584-111">This must be either 1 or an even number.</span></span>



## <a name="output--simulationalgorithm"></a><span data-ttu-id="d2584-112">Output: [SimulationAlgorithm](xref:Microsoft.Quantum.Simulation.SimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="d2584-112">Output : [SimulationAlgorithm](xref:Microsoft.Quantum.Simulation.SimulationAlgorithm)</span></span>

<span data-ttu-id="d2584-113">Tipo `SimulationAlgorithm`.</span><span class="sxs-lookup"><span data-stu-id="d2584-113">A `SimulationAlgorithm` type.</span></span>