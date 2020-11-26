---
uid: Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates
title: Operazione EstimateOverlapBetweenStates
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the squared overlap between the states prepared by each operation.
ms.openlocfilehash: 07693ccf4b8e7bbde189674d9e6b2bf7f92222f6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204301"
---
# <a name="estimateoverlapbetweenstates-operation"></a><span data-ttu-id="1a89f-102">Operazione EstimateOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="1a89f-102">EstimateOverlapBetweenStates operation</span></span>

<span data-ttu-id="1a89f-103">Spazio dei nomi: [Microsoft. Quantum. characteration](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="1a89f-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="1a89f-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1a89f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1a89f-105">Date due operazioni, ciascuna delle quali prepara copie di uno stato, stima la sovrapposizione quadrata tra gli stati preparati da ogni operazione.</span><span class="sxs-lookup"><span data-stu-id="1a89f-105">Given two operations which each prepare copies of a state, estimates the squared overlap between the states prepared by each operation.</span></span>

```qsharp
operation EstimateOverlapBetweenStates (preparation1 : (Qubit[] => Unit is Adj), preparation2 : (Qubit[] => Unit is Adj), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="1a89f-106">Input</span><span class="sxs-lookup"><span data-stu-id="1a89f-106">Input</span></span>

### <a name="preparation1--qubit--unit--is-adj"></a><span data-ttu-id="1a89f-107">preparation1: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ</span><span class="sxs-lookup"><span data-stu-id="1a89f-107">preparation1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="1a89f-108">Prima delle due operazioni di preparazione dello stato da confrontare.</span><span class="sxs-lookup"><span data-stu-id="1a89f-108">The first of the two state preparation operations to be compared.</span></span>


### <a name="preparation2--qubit--unit--is-adj"></a><span data-ttu-id="1a89f-109">Preparazione2: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ</span><span class="sxs-lookup"><span data-stu-id="1a89f-109">preparation2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="1a89f-110">Secondo delle due operazioni di preparazione dello stato da confrontare.</span><span class="sxs-lookup"><span data-stu-id="1a89f-110">The second of the two state preparation operations to be compared.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="1a89f-111">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1a89f-111">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1a89f-112">Numero di qubits in cui `commonPreparation` agiscono, `preparation1` e `preparation2` .</span><span class="sxs-lookup"><span data-stu-id="1a89f-112">The number of qubits on which `commonPreparation`, `preparation1`, and `preparation2` all act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="1a89f-113">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1a89f-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1a89f-114">Numero di misurazioni da utilizzare per stimare la sovrapposizione.</span><span class="sxs-lookup"><span data-stu-id="1a89f-114">The number of measurements to use in estimating the overlap.</span></span>



## <a name="output--double"></a><span data-ttu-id="1a89f-115">Output: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1a89f-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="1a89f-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="1a89f-116">Remarks</span></span>

<span data-ttu-id="1a89f-117">Questa operazione usa il test di scambio per trovare $ $ \begin{align} \left | \braket{00\cdots 0 | V ^ {\dagger} U | 00 \ cdots 0} \right | ^ 2 \end{align} $ $ where $U $ è la rappresentazione unitaria dell'azione di `preparation1` e dove $V $ corrisponde a `preparation2` .</span><span class="sxs-lookup"><span data-stu-id="1a89f-117">This operation uses the SWAP test to find $$ \begin{align} \left| \braket{00\cdots 0 | V^{\dagger} U | 00\cdots 0} \right|^2 \end{align} $$ where $U$ is the unitary representation of the action of `preparation1`, and where $V$ corresponds to `preparation2`.</span></span>

## <a name="see-also"></a><span data-ttu-id="1a89f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a89f-118">See Also</span></span>

- [<span data-ttu-id="1a89f-119">Microsoft. Quantum. Characteration. EstimateRealOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="1a89f-119">Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates)
- [<span data-ttu-id="1a89f-120">Microsoft. Quantum. Characteration. EstimateImagOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="1a89f-120">Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates)