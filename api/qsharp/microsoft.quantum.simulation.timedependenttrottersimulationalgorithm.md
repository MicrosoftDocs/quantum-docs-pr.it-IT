---
uid: Microsoft.Quantum.Simulation.TimeDependentTrotterSimulationAlgorithm
title: TimeDependentTrotterSimulationAlgorithm (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentTrotterSimulationAlgorithm
qsharp.summary: '`TimeDependentSimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate a unitary operator that solves the time-dependent Schrodinger equation.'
ms.openlocfilehash: c827dd79af6f4b745adf8903ed2664d9e8255785
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858365"
---
# <a name="timedependenttrottersimulationalgorithm-function"></a><span data-ttu-id="2bccf-102">TimeDependentTrotterSimulationAlgorithm (funzione)</span><span class="sxs-lookup"><span data-stu-id="2bccf-102">TimeDependentTrotterSimulationAlgorithm function</span></span>

<span data-ttu-id="2bccf-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="2bccf-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="2bccf-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2bccf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2bccf-105">`TimeDependentSimulationAlgorithm` funzione che usa una scomposizione Trotter-Suzuki per approssimare un operatore unitario che risolve l'equazione Schrodinger dipendente dal tempo.</span><span class="sxs-lookup"><span data-stu-id="2bccf-105">`TimeDependentSimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate a unitary operator that solves the time-dependent Schrodinger equation.</span></span>

```qsharp
function TimeDependentTrotterSimulationAlgorithm (trotterStepSize : Double, trotterOrder : Int) : Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm
```


## <a name="input"></a><span data-ttu-id="2bccf-106">Input</span><span class="sxs-lookup"><span data-stu-id="2bccf-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="2bccf-107">trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2bccf-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2bccf-108">Durata dell'evoluzione del tempo simulato in un singolo passaggio Trotter.</span><span class="sxs-lookup"><span data-stu-id="2bccf-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="2bccf-109">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2bccf-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2bccf-110">Ordine di Trotter Integrator.</span><span class="sxs-lookup"><span data-stu-id="2bccf-110">Order of Trotter integrator.</span></span> <span data-ttu-id="2bccf-111">Deve essere 1 o un numero pari.</span><span class="sxs-lookup"><span data-stu-id="2bccf-111">This must be either 1 or an even number.</span></span>



## <a name="output--timedependentsimulationalgorithm"></a><span data-ttu-id="2bccf-112">Output: [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="2bccf-112">Output : [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span></span>

<span data-ttu-id="2bccf-113">Tipo `TimeDependentSimulationAlgorithm`.</span><span class="sxs-lookup"><span data-stu-id="2bccf-113">A `TimeDependentSimulationAlgorithm` type.</span></span>