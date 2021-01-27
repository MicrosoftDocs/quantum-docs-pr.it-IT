---
uid: Microsoft.Quantum.Simulation.EstimateEnergyWithAdiabaticEvolution
title: Operazione EstimateEnergyWithAdiabaticEvolution
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EstimateEnergyWithAdiabaticEvolution
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state, followed by adiabatic state preparation using a `adiabaticUnitary`, and finally phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: 498955a712db61952d69f28cbbb4715a3efe4c5e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858288"
---
# <a name="estimateenergywithadiabaticevolution-operation"></a><span data-ttu-id="ab452-102">Operazione EstimateEnergyWithAdiabaticEvolution</span><span class="sxs-lookup"><span data-stu-id="ab452-102">EstimateEnergyWithAdiabaticEvolution operation</span></span>

<span data-ttu-id="ab452-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="ab452-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="ab452-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ab452-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ab452-105">Esegue la preparazione dello stato applicando un oggetto `statePrepUnitary` in uno stato di input allocato automaticamente, seguito dalla preparazione dello stato adiabatica usando un oggetto `adiabaticUnitary` e infine la stima della fase per quanto riguarda `qpeUnitary` lo stato risultante utilizzando un oggetto `phaseEstAlgorithm` .</span><span class="sxs-lookup"><span data-stu-id="ab452-105">Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state, followed by adiabatic state preparation using a `adiabaticUnitary`, and finally phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.</span></span>

```qsharp
operation EstimateEnergyWithAdiabaticEvolution (nQubits : Int, statePrepUnitary : (Qubit[] => Unit), adiabaticUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double)) : Double
```


## <a name="input"></a><span data-ttu-id="ab452-106">Input</span><span class="sxs-lookup"><span data-stu-id="ab452-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="ab452-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ab452-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ab452-108">Numero di qubits usati per la simulazione.</span><span class="sxs-lookup"><span data-stu-id="ab452-108">Number of qubits used for the simulation.</span></span>


### <a name="stateprepunitary--qubit--unit"></a><span data-ttu-id="ab452-109">statePrepUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="ab452-109">statePrepUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="ab452-110">Oggetto Oracle che rappresenta la preparazione dello stato per il generatore dinamico iniziale.</span><span class="sxs-lookup"><span data-stu-id="ab452-110">An oracle representing state preparation for the initial dynamical generator.</span></span>


### <a name="adiabaticunitary--qubit--unit"></a><span data-ttu-id="ab452-111">adiabaticUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="ab452-111">adiabaticUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="ab452-112">Oracle che rappresenta l'algoritmo di adiabatica Evolution da usare per implementare gli sweep allo stato finale dell'algoritmo.</span><span class="sxs-lookup"><span data-stu-id="ab452-112">An oracle representing the adiabatic evolution algorithm to be used to implement the sweeps to the final state of the algorithm.</span></span>


### <a name="qpeunitary--qubit--unit--is-adj--ctl"></a><span data-ttu-id="ab452-113">qpeUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="ab452-113">qpeUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="ab452-114">Oracle che rappresenta un operatore unitario $U $ che rappresenta l'evoluzione per il tempo $ \delta t $ in un generatore dinamico con stato di base $ \ket{\Phi} $ e l'energia dello stato di base $E = \Phi \\ , \delta t $.</span><span class="sxs-lookup"><span data-stu-id="ab452-114">An oracle representing a unitary operator $U$ representing evolution for time $\delta t$ under a dynamical generator with ground state $\ket{\phi}$ and ground state energy $E = \phi\\,\delta t$.</span></span>


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a><span data-ttu-id="ab452-115">phaseEstAlgorithm: ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ab452-115">phaseEstAlgorithm : ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span></span> 

<span data-ttu-id="ab452-116">Operazione che esegue la stima della fase su una determinata operazione unitaria.</span><span class="sxs-lookup"><span data-stu-id="ab452-116">An operation that performs phase estimation on a given unitary operation.</span></span>
<span data-ttu-id="ab452-117">Per ulteriori informazioni, vedere la [stima della fase iterativa](/quantum/libraries/characterization#iterative-phase-estimation) .</span><span class="sxs-lookup"><span data-stu-id="ab452-117">See [iterative phase estimation](/quantum/libraries/characterization#iterative-phase-estimation) for more details.</span></span>



## <a name="output--double"></a><span data-ttu-id="ab452-118">Output: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ab452-118">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ab452-119">Una stima di $ \hat{\Phi} $ dell'energia di stato di base $ \Phi $ del generatore rappresentato da $U $.</span><span class="sxs-lookup"><span data-stu-id="ab452-119">An estimate $\hat{\phi}$ of the ground state energy $\phi$ of the generator represented by $U$.</span></span>