---
uid: Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates
title: Operazione EstimateImagOverlapBetweenStates
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateImagOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the imaginary part of the overlap between the states prepared by each operation.
ms.openlocfilehash: f18ce43f9e5ebada4c5cc0aeff1538ac640c7390
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851877"
---
# <a name="estimateimagoverlapbetweenstates-operation"></a><span data-ttu-id="f6867-102">Operazione EstimateImagOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="f6867-102">EstimateImagOverlapBetweenStates operation</span></span>

<span data-ttu-id="f6867-103">Spazio dei nomi: [Microsoft. Quantum. characteration](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="f6867-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="f6867-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f6867-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f6867-105">Date due operazioni, ciascuna delle quali prepara copie di uno stato, stima la parte immaginaria della sovrapposizione tra gli stati preparati da ogni operazione.</span><span class="sxs-lookup"><span data-stu-id="f6867-105">Given two operations which each prepare copies of a state, estimates the imaginary part of the overlap between the states prepared by each operation.</span></span>

```qsharp
operation EstimateImagOverlapBetweenStates (commonPreparation : (Qubit[] => Unit is Adj), preparation1 : (Qubit[] => Unit is Adj + Ctl), preparation2 : (Qubit[] => Unit is Adj + Ctl), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="f6867-106">Input</span><span class="sxs-lookup"><span data-stu-id="f6867-106">Input</span></span>

### <a name="commonpreparation--qubit--unit--is-adj"></a><span data-ttu-id="f6867-107">commonPreparation: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ</span><span class="sxs-lookup"><span data-stu-id="f6867-107">commonPreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="f6867-108">Operazione che prepara uno stato di input fisso.</span><span class="sxs-lookup"><span data-stu-id="f6867-108">An operation that prepares a fixed input state.</span></span>


### <a name="preparation1--qubit--unit--is-adj--ctl"></a><span data-ttu-id="f6867-109">preparation1: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="f6867-109">preparation1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="f6867-110">Prima delle due operazioni di preparazione dello stato da confrontare.</span><span class="sxs-lookup"><span data-stu-id="f6867-110">The first of the two state preparation operations to be compared.</span></span>


### <a name="preparation2--qubit--unit--is-adj--ctl"></a><span data-ttu-id="f6867-111">Preparazione2: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="f6867-111">preparation2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="f6867-112">Secondo delle due operazioni di preparazione dello stato da confrontare.</span><span class="sxs-lookup"><span data-stu-id="f6867-112">The second of the two state preparation operations to be compared.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="f6867-113">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f6867-113">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f6867-114">Numero di qubits in cui `commonPreparation` agiscono, `preparation1` e `preparation2` .</span><span class="sxs-lookup"><span data-stu-id="f6867-114">The number of qubits on which `commonPreparation`, `preparation1`, and `preparation2` all act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="f6867-115">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f6867-115">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f6867-116">Numero di misurazioni da utilizzare per stimare la sovrapposizione.</span><span class="sxs-lookup"><span data-stu-id="f6867-116">The number of measurements to use in estimating the overlap.</span></span>



## <a name="output--double"></a><span data-ttu-id="f6867-117">Output: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f6867-117">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="f6867-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="f6867-118">Remarks</span></span>

<span data-ttu-id="f6867-119">Questa operazione usa il test Hadamard per trovare la parte immaginaria di $ $ \begin{align} \braket{\psi | V ^ {\dagger} U | \psi} \end{align} $ $ dove $ \ket{\psi} $ è lo stato preparato da `commonPreparation` , $U $ è la rappresentazione unitaria dell'azione di `preparation1` e dove $V $ corrisponde a `preparation2` .</span><span class="sxs-lookup"><span data-stu-id="f6867-119">This operation uses the Hadamard test to find the imaginary part of $$ \begin{align} \braket{\psi | V^{\dagger} U | \psi} \end{align} $$ where $\ket{\psi}$ is the state prepared by `commonPreparation`, $U$ is the unitary representation of the action of `preparation1`, and where $V$ corresponds to `preparation2`.</span></span>

## <a name="references"></a><span data-ttu-id="f6867-120">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="f6867-120">References</span></span>

- <span data-ttu-id="f6867-121">Aharonov *et al.* [quante-pH/0511096](https://arxiv.org/abs/quant-ph/0511096).</span><span class="sxs-lookup"><span data-stu-id="f6867-121">Aharonov *et al.* [quant-ph/0511096](https://arxiv.org/abs/quant-ph/0511096).</span></span>

## <a name="see-also"></a><span data-ttu-id="f6867-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6867-122">See Also</span></span>

- [<span data-ttu-id="f6867-123">Microsoft. Quantum. Characteration. EstimateRealOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="f6867-123">Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates)
- [<span data-ttu-id="f6867-124">Microsoft. Quantum. Characteration. EstimateOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="f6867-124">Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates)