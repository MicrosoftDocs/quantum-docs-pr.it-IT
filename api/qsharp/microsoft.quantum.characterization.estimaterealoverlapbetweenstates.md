---
uid: Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates
title: Operazione EstimateRealOverlapBetweenStates
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateRealOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the real part of the overlap between the states prepared by each operation.
ms.openlocfilehash: 01631bcbff2bff26ddc1db4e42d90ac4f8380bd4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714972"
---
# <a name="estimaterealoverlapbetweenstates-operation"></a><span data-ttu-id="2a59a-102">Operazione EstimateRealOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="2a59a-102">EstimateRealOverlapBetweenStates operation</span></span>

<span data-ttu-id="2a59a-103">Spazio dei nomi: [Microsoft. Quantum. characteration](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="2a59a-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="2a59a-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2a59a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2a59a-105">Date due operazioni, ciascuna delle quali prepara copie di uno stato, stima la parte reale della sovrapposizione tra gli stati preparati da ogni operazione.</span><span class="sxs-lookup"><span data-stu-id="2a59a-105">Given two operations which each prepare copies of a state, estimates the real part of the overlap between the states prepared by each operation.</span></span>

```qsharp
operation EstimateRealOverlapBetweenStates (commonPreparation : (Qubit[] => Unit is Adj), preparation1 : (Qubit[] => Unit is Adj + Ctl), preparation2 : (Qubit[] => Unit is Adj + Ctl), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="2a59a-106">Input</span><span class="sxs-lookup"><span data-stu-id="2a59a-106">Input</span></span>

### <a name="commonpreparation--qubit--unit-adj"></a><span data-ttu-id="2a59a-107">commonPreparation: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ</span><span class="sxs-lookup"><span data-stu-id="2a59a-107">commonPreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="2a59a-108">Operazione che prepara uno stato di input fisso.</span><span class="sxs-lookup"><span data-stu-id="2a59a-108">An operation that prepares a fixed input state.</span></span>


### <a name="preparation1--qubit--unit-adj--ctl"></a><span data-ttu-id="2a59a-109">preparation1: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="2a59a-109">preparation1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="2a59a-110">Prima delle due operazioni di preparazione dello stato da confrontare.</span><span class="sxs-lookup"><span data-stu-id="2a59a-110">The first of the two state preparation operations to be compared.</span></span>


### <a name="preparation2--qubit--unit-adj--ctl"></a><span data-ttu-id="2a59a-111">Preparazione2: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="2a59a-111">preparation2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="2a59a-112">Secondo delle due operazioni di preparazione dello stato da confrontare.</span><span class="sxs-lookup"><span data-stu-id="2a59a-112">The second of the two state preparation operations to be compared.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="2a59a-113">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2a59a-113">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2a59a-114">Numero di qubits in cui `commonPreparation` agiscono, `preparation1` e `preparation2` .</span><span class="sxs-lookup"><span data-stu-id="2a59a-114">The number of qubits on which `commonPreparation`, `preparation1`, and `preparation2` all act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="2a59a-115">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2a59a-115">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2a59a-116">Numero di misurazioni da utilizzare per stimare la sovrapposizione.</span><span class="sxs-lookup"><span data-stu-id="2a59a-116">The number of measurements to use in estimating the overlap.</span></span>



## <a name="output--double"></a><span data-ttu-id="2a59a-117">Output: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2a59a-117">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="2a59a-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="2a59a-118">Remarks</span></span>

<span data-ttu-id="2a59a-119">Questa operazione usa il test Hadamard per trovare la parte reale di $ $ \begin{align} \braket{\psi | V ^ {\dagger} U | \psi} \end{align} $ $ dove $ \ket{\psi} $ è lo stato preparato da `commonPreparation` , $U $ è la rappresentazione unitaria dell'azione di `preparation1` e dove $V $ corrisponde a `preparation2` .</span><span class="sxs-lookup"><span data-stu-id="2a59a-119">This operation uses the Hadamard test to find the real part of $$ \begin{align} \braket{\psi | V^{\dagger} U | \psi} \end{align} $$ where $\ket{\psi}$ is the state prepared by `commonPreparation`, $U$ is the unitary representation of the action of `preparation1`, and where $V$ corresponds to `preparation2`.</span></span>

## <a name="references"></a><span data-ttu-id="2a59a-120">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="2a59a-120">References</span></span>

- <span data-ttu-id="2a59a-121">Aharonov *et al.* [quante-pH/0511096](https://arxiv.org/abs/quant-ph/0511096).</span><span class="sxs-lookup"><span data-stu-id="2a59a-121">Aharonov *et al.* [quant-ph/0511096](https://arxiv.org/abs/quant-ph/0511096).</span></span>

## <a name="see-also"></a><span data-ttu-id="2a59a-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a59a-122">See Also</span></span>

- [<span data-ttu-id="2a59a-123">Microsoft. Quantum. Characteration. EstimateImagOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="2a59a-123">Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates)
- [<span data-ttu-id="2a59a-124">Microsoft. Quantum. Characteration. EstimateOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="2a59a-124">Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates)