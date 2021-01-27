---
uid: Microsoft.Quantum.Simulation.EstimateEnergy
title: Operazione EstimateEnergy
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EstimateEnergy
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: f9243557718e12d168afadbf641492291afd1704
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856757"
---
# <a name="estimateenergy-operation"></a><span data-ttu-id="2cef6-102">Operazione EstimateEnergy</span><span class="sxs-lookup"><span data-stu-id="2cef6-102">EstimateEnergy operation</span></span>

<span data-ttu-id="2cef6-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="2cef6-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="2cef6-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2cef6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2cef6-105">Esegue la preparazione dello stato applicando un oggetto `statePrepUnitary` in una stima della fase dello stato di input allocata automaticamente rispetto a nello `qpeUnitary` stato risultante utilizzando un oggetto `phaseEstAlgorithm` .</span><span class="sxs-lookup"><span data-stu-id="2cef6-105">Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.</span></span>

```qsharp
operation EstimateEnergy (nQubits : Int, statePrepUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double)) : Double
```


## <a name="input"></a><span data-ttu-id="2cef6-106">Input</span><span class="sxs-lookup"><span data-stu-id="2cef6-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="2cef6-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2cef6-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2cef6-108">Numero di qubits usati per eseguire la simulazione.</span><span class="sxs-lookup"><span data-stu-id="2cef6-108">Number of qubits used to perform simulation.</span></span>


### <a name="stateprepunitary--qubit--unit"></a><span data-ttu-id="2cef6-109">statePrepUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="2cef6-109">statePrepUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="2cef6-110">Oggetto Oracle che rappresenta la preparazione dello stato per il generatore dinamico iniziale.</span><span class="sxs-lookup"><span data-stu-id="2cef6-110">An oracle representing state preparation for the initial dynamical generator.</span></span>


### <a name="qpeunitary--qubit--unit--is-adj--ctl"></a><span data-ttu-id="2cef6-111">qpeUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="2cef6-111">qpeUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="2cef6-112">Oracle che rappresenta un operatore unitario $U $ che rappresenta l'evoluzione per il tempo $ \delta t $ in un generatore dinamico con stato di base $ \ket{\Phi} $ e l'energia dello stato di base $E = \Phi \\ , \delta t $.</span><span class="sxs-lookup"><span data-stu-id="2cef6-112">An oracle representing a unitary operator $U$ representing evolution for time $\delta t$ under a dynamical generator with ground state $\ket{\phi}$ and ground state energy $E = \phi\\,\delta t$.</span></span>


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a><span data-ttu-id="2cef6-113">phaseEstAlgorithm: ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2cef6-113">phaseEstAlgorithm : ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span></span> 

<span data-ttu-id="2cef6-114">Operazione che esegue la stima della fase su una determinata operazione unitaria.</span><span class="sxs-lookup"><span data-stu-id="2cef6-114">An operation that performs phase estimation on a given unitary operation.</span></span>
<span data-ttu-id="2cef6-115">Per ulteriori informazioni, vedere la [stima della fase iterativa](/quantum/libraries/characterization#iterative-phase-estimation) .</span><span class="sxs-lookup"><span data-stu-id="2cef6-115">See [iterative phase estimation](/quantum/libraries/characterization#iterative-phase-estimation) for more details.</span></span>



## <a name="output--double"></a><span data-ttu-id="2cef6-116">Output: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2cef6-116">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2cef6-117">Una stima $ \hat{\Phi} $ dell'energia dello stato di base $ \Phi $ dell'energia di stato di base del generatore rappresentato da $U $.</span><span class="sxs-lookup"><span data-stu-id="2cef6-117">An estimate $\hat{\phi}$ of the ground state energy $\phi$ of the ground state energy of the generator represented by $U$.</span></span>