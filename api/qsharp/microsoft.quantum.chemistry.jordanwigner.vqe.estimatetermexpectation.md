---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: Operazione EstimateTermExpectation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: ef689c55f966e63a2ab8bcdccf99d9cb5e6d3a4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713726"
---
# <a name="estimatetermexpectation-operation"></a><span data-ttu-id="d2cd1-102">Operazione EstimateTermExpectation</span><span class="sxs-lookup"><span data-stu-id="d2cd1-102">EstimateTermExpectation operation</span></span>

<span data-ttu-id="d2cd1-103">Spazio dei nomi: [Microsoft. Quantum. Chemistry. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="d2cd1-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="d2cd1-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d2cd1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d2cd1-105">Calcola l'energia associata a un determinato termine di Jordan-Wigner hamiltoniana</span><span class="sxs-lookup"><span data-stu-id="d2cd1-105">Computes the energy associated to a given Jordan-Wigner Hamiltonian term</span></span>

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a><span data-ttu-id="d2cd1-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d2cd1-106">Description</span></span>

<span data-ttu-id="d2cd1-107">Questa operazione consente di stimare il valore di previsione associato a ciascun operatore di misurazione e di moltiplicarlo per il coefficiente corrispondente usando il campionamento.</span><span class="sxs-lookup"><span data-stu-id="d2cd1-107">This operation estimates the expectation value associated to each measurement operator and multiplies it by the corresponding coefficient, using sampling.</span></span>
<span data-ttu-id="d2cd1-108">I risultati vengono aggregati in una variabile che contiene l'energia del termine Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="d2cd1-108">The results are aggregated into a variable containing the energy of the Jordan-Wigner term.</span></span>

## <a name="input"></a><span data-ttu-id="d2cd1-109">Input</span><span class="sxs-lookup"><span data-stu-id="d2cd1-109">Input</span></span>

### <a name="inputstateunitary--qubit--unit-adj"></a><span data-ttu-id="d2cd1-110">inputStateUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ</span><span class="sxs-lookup"><span data-stu-id="d2cd1-110">inputStateUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="d2cd1-111">Unitario utilizzato per la preparazione dello stato.</span><span class="sxs-lookup"><span data-stu-id="d2cd1-111">The unitary used for state preparation.</span></span>


### <a name="ops--pauli"></a><span data-ttu-id="d2cd1-112">Ops: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="d2cd1-112">ops : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="d2cd1-113">Operatori di misurazione del termine del Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="d2cd1-113">The measurement operators of the Jordan-Wigner term.</span></span>


### <a name="coeffs--double"></a><span data-ttu-id="d2cd1-114">coeffs: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="d2cd1-114">coeffs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="d2cd1-115">Coefficienti del termine del Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="d2cd1-115">The coefficients of the Jordan-Wigner term.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="d2cd1-116">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d2cd1-116">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d2cd1-117">Numero di qubits necessari per simulare il sistema molecolare.</span><span class="sxs-lookup"><span data-stu-id="d2cd1-117">The number of qubits required to simulate the molecular system.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="d2cd1-118">nSamples: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d2cd1-118">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d2cd1-119">Numero di campioni da utilizzare per la stima del termine previsto.</span><span class="sxs-lookup"><span data-stu-id="d2cd1-119">The number of samples to use for the estimation of the term expectation.</span></span>



## <a name="output--double"></a><span data-ttu-id="d2cd1-120">Output: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d2cd1-120">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d2cd1-121">Energia associata al termine Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="d2cd1-121">The energy associated to the Jordan-Wigner term.</span></span>