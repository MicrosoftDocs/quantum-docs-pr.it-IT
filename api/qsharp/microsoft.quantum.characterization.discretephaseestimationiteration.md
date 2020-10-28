---
uid: Microsoft.Quantum.Characterization.DiscretePhaseEstimationIteration
title: Operazione DiscretePhaseEstimationIteration
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: DiscretePhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using integer powers of a unitary oracle.
ms.openlocfilehash: 167b53d7108c64d11a4f258d17e90ba78d7dd8d8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715070"
---
# <a name="discretephaseestimationiteration-operation"></a><span data-ttu-id="ac8e5-102">Operazione DiscretePhaseEstimationIteration</span><span class="sxs-lookup"><span data-stu-id="ac8e5-102">DiscretePhaseEstimationIteration operation</span></span>

<span data-ttu-id="ac8e5-103">Spazio dei nomi: [Microsoft. Quantum. characteration](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="ac8e5-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="ac8e5-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ac8e5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ac8e5-105">Esegue una singola iterazione di un algoritmo di stima della fase iterativo (controllo classico) usando le potenze di un numero intero di un Oracle unitario.</span><span class="sxs-lookup"><span data-stu-id="ac8e5-105">Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using integer powers of a unitary oracle.</span></span>

```qsharp
operation DiscretePhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, power : Int, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="ac8e5-106">Input</span><span class="sxs-lookup"><span data-stu-id="ac8e5-106">Input</span></span>

### <a name="oracle--discreteoracle"></a><span data-ttu-id="ac8e5-107">Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="ac8e5-107">oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="ac8e5-108">Operazione che agisce su un numero intero e un registro, in modo che $U ^ m $ venga applicato al registro specificato, dove $U $ è l'unità di cui è necessario stimare la fase e dove $m $ è la potenza intera assegnata a Oracle</span><span class="sxs-lookup"><span data-stu-id="ac8e5-108">Operation acting on an integer and a register, such that $U^m$ is applied to the given register, where $U$ is the unitary whose phase is to be estimated, and where $m$ is the integer power given to the oracle</span></span>


### <a name="power--int"></a><span data-ttu-id="ac8e5-109">Potenza: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ac8e5-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ac8e5-110">Numero di volte in cui applicare l'oggetto Oracle unitario specificato.</span><span class="sxs-lookup"><span data-stu-id="ac8e5-110">Number of times to apply the given unitary oracle.</span></span>


### <a name="theta--double"></a><span data-ttu-id="ac8e5-111">Theta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ac8e5-111">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ac8e5-112">Angolo in base al quale invertire la fase sul controllo qubit prima di agire sullo stato di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ac8e5-112">Angle by which to invert the phase on the control qubit before acting on the target state.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="ac8e5-113">targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ac8e5-113">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ac8e5-114">Registro dello stato a cui si basa il Oracle unitario specificato.</span><span class="sxs-lookup"><span data-stu-id="ac8e5-114">Register of state acted upon by the given unitary oracle.</span></span>


### <a name="controlqubit--qubit"></a><span data-ttu-id="ac8e5-115">controlQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ac8e5-115">controlQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ac8e5-116">Qubit ausiliario utilizzato per controllare l'applicazione del Oracle specificato.</span><span class="sxs-lookup"><span data-stu-id="ac8e5-116">An auxiliary qubit used to control the application of the given oracle.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ac8e5-117">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ac8e5-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

