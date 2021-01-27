---
uid: Microsoft.Quantum.Simulation.TrotterStep
title: TrotterStep (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStep
qsharp.summary: Implements a single time-step of time-evolution by the system described in an `EvolutionGenerator` using a Trotter–Suzuki decomposition.
ms.openlocfilehash: 4c0e7dd89b1beae9fb6a35ae5b8d16e09d355ab8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854713"
---
# <a name="trotterstep-function"></a><span data-ttu-id="ebd5b-102">TrotterStep (funzione)</span><span class="sxs-lookup"><span data-stu-id="ebd5b-102">TrotterStep function</span></span>

<span data-ttu-id="ebd5b-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="ebd5b-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="ebd5b-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ebd5b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ebd5b-105">Implementa un'unica fase temporale dell'evoluzione del sistema descritta in un oggetto `EvolutionGenerator` utilizzando una scomposizione Trotter-Suzuki.</span><span class="sxs-lookup"><span data-stu-id="ebd5b-105">Implements a single time-step of time-evolution by the system described in an `EvolutionGenerator` using a Trotter–Suzuki decomposition.</span></span>

```qsharp
function TrotterStep (evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, trotterOrder : Int, trotterStepSize : Double) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="ebd5b-106">Input</span><span class="sxs-lookup"><span data-stu-id="ebd5b-106">Input</span></span>

### <a name="evolutiongenerator--evolutiongenerator"></a><span data-ttu-id="ebd5b-107">evolutionGenerator: [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="ebd5b-107">evolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="ebd5b-108">Descrizione completa del sistema da simulare.</span><span class="sxs-lookup"><span data-stu-id="ebd5b-108">A complete description of the system to be simulated.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="ebd5b-109">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ebd5b-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ebd5b-110">Ordine di Trotter Integrator.</span><span class="sxs-lookup"><span data-stu-id="ebd5b-110">Order of Trotter integrator.</span></span> <span data-ttu-id="ebd5b-111">Deve essere 1 o un numero pari.</span><span class="sxs-lookup"><span data-stu-id="ebd5b-111">This must be either 1 or an even number.</span></span>


### <a name="trotterstepsize--double"></a><span data-ttu-id="ebd5b-112">trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ebd5b-112">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ebd5b-113">Durata dell'evoluzione del tempo simulato in un singolo passaggio Trotter.</span><span class="sxs-lookup"><span data-stu-id="ebd5b-113">Duration of simulated time-evolution in single Trotter step.</span></span>



## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="ebd5b-114">Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="ebd5b-114">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="ebd5b-115">Operazione unitaria che si avvicina a un singolo passaggio di tempo-evoluzione per la durata `trotterStepSize` .</span><span class="sxs-lookup"><span data-stu-id="ebd5b-115">Unitary operation that approximates a single step of time-evolution for duration `trotterStepSize`.</span></span>

## <a name="remarks"></a><span data-ttu-id="ebd5b-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="ebd5b-116">Remarks</span></span>

<span data-ttu-id="ebd5b-117">Per altre informazioni sulla decomposizione Trotter-Suzuki, vedere [composizione ordinata](/quantum/libraries/control-flow#time-ordered-composition)in un momento specifico.</span><span class="sxs-lookup"><span data-stu-id="ebd5b-117">For more on the Trotter–Suzuki decomposition, see [Time-Ordered Composition](/quantum/libraries/control-flow#time-ordered-composition).</span></span>