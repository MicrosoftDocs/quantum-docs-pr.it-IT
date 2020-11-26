---
uid: Microsoft.Quantum.Simulation.TrotterSimulationAlgorithmImpl
title: Operazione TrotterSimulationAlgorithmImpl
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterSimulationAlgorithmImpl
qsharp.summary: Makes repeated calls to `TrotterStep` to approximate the time-evolution operator exp(_-iHt_).
ms.openlocfilehash: 5b796245e2a4434228260a229cb61be66f3e38d6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203400"
---
# <a name="trottersimulationalgorithmimpl-operation"></a><span data-ttu-id="e6c27-102">Operazione TrotterSimulationAlgorithmImpl</span><span class="sxs-lookup"><span data-stu-id="e6c27-102">TrotterSimulationAlgorithmImpl operation</span></span>

<span data-ttu-id="e6c27-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="e6c27-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="e6c27-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e6c27-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e6c27-105">Effettua chiamate ripetute a `TrotterStep` per approssimare l'operatore Time-Evolution exp (_-iHt_).</span><span class="sxs-lookup"><span data-stu-id="e6c27-105">Makes repeated calls to `TrotterStep` to approximate the time-evolution operator exp(_-iHt_).</span></span>

```qsharp
operation TrotterSimulationAlgorithmImpl (trotterStepSize : Double, trotterOrder : Int, maxTime : Double, evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="e6c27-106">Input</span><span class="sxs-lookup"><span data-stu-id="e6c27-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="e6c27-107">trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e6c27-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e6c27-108">Durata dell'evoluzione del tempo simulato in un singolo passaggio Trotter.</span><span class="sxs-lookup"><span data-stu-id="e6c27-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="e6c27-109">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e6c27-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e6c27-110">Ordine di Trotter Integrator.</span><span class="sxs-lookup"><span data-stu-id="e6c27-110">Order of Trotter integrator.</span></span> <span data-ttu-id="e6c27-111">Deve essere 1 o un numero pari.</span><span class="sxs-lookup"><span data-stu-id="e6c27-111">This must be either 1 or an even number.</span></span>


### <a name="maxtime--double"></a><span data-ttu-id="e6c27-112">maxTime: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e6c27-112">maxTime : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e6c27-113">Durata totale della simulazione $t $.</span><span class="sxs-lookup"><span data-stu-id="e6c27-113">Total duration of simulation $t$.</span></span>


### <a name="evolutiongenerator--evolutiongenerator"></a><span data-ttu-id="e6c27-114">evolutionGenerator: [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="e6c27-114">evolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="e6c27-115">Descrizione completa del sistema da simulare.</span><span class="sxs-lookup"><span data-stu-id="e6c27-115">A complete description of the system to be simulated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="e6c27-116">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e6c27-116">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e6c27-117">Qubits agito da simulazione.</span><span class="sxs-lookup"><span data-stu-id="e6c27-117">Qubits acted on by simulation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e6c27-118">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e6c27-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

