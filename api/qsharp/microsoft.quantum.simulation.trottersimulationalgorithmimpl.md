---
uid: Microsoft.Quantum.Simulation.TrotterSimulationAlgorithmImpl
title: Operazione TrotterSimulationAlgorithmImpl
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterSimulationAlgorithmImpl
qsharp.summary: Makes repeated calls to `TrotterStep` to approximate the time-evolution operator exp(_-iHt_).
ms.openlocfilehash: b2411950b90eb676b1da53bd06bde648099e2db4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858897"
---
# <a name="trottersimulationalgorithmimpl-operation"></a><span data-ttu-id="53b40-102">Operazione TrotterSimulationAlgorithmImpl</span><span class="sxs-lookup"><span data-stu-id="53b40-102">TrotterSimulationAlgorithmImpl operation</span></span>

<span data-ttu-id="53b40-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="53b40-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="53b40-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="53b40-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="53b40-105">Effettua chiamate ripetute a `TrotterStep` per approssimare l'operatore Time-Evolution exp (_-iHt_).</span><span class="sxs-lookup"><span data-stu-id="53b40-105">Makes repeated calls to `TrotterStep` to approximate the time-evolution operator exp(_-iHt_).</span></span>

```qsharp
operation TrotterSimulationAlgorithmImpl (trotterStepSize : Double, trotterOrder : Int, maxTime : Double, evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="53b40-106">Input</span><span class="sxs-lookup"><span data-stu-id="53b40-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="53b40-107">trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="53b40-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="53b40-108">Durata dell'evoluzione del tempo simulato in un singolo passaggio Trotter.</span><span class="sxs-lookup"><span data-stu-id="53b40-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="53b40-109">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="53b40-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="53b40-110">Ordine di Trotter Integrator.</span><span class="sxs-lookup"><span data-stu-id="53b40-110">Order of Trotter integrator.</span></span> <span data-ttu-id="53b40-111">Deve essere 1 o un numero pari.</span><span class="sxs-lookup"><span data-stu-id="53b40-111">This must be either 1 or an even number.</span></span>


### <a name="maxtime--double"></a><span data-ttu-id="53b40-112">maxTime: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="53b40-112">maxTime : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="53b40-113">Durata totale della simulazione $t $.</span><span class="sxs-lookup"><span data-stu-id="53b40-113">Total duration of simulation $t$.</span></span>


### <a name="evolutiongenerator--evolutiongenerator"></a><span data-ttu-id="53b40-114">evolutionGenerator: [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="53b40-114">evolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="53b40-115">Descrizione completa del sistema da simulare.</span><span class="sxs-lookup"><span data-stu-id="53b40-115">A complete description of the system to be simulated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="53b40-116">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="53b40-116">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="53b40-117">Qubits agito da simulazione.</span><span class="sxs-lookup"><span data-stu-id="53b40-117">Qubits acted on by simulation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="53b40-118">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="53b40-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

