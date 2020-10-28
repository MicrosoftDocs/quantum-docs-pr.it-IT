---
uid: Microsoft.Quantum.Characterization.ContinuousPhaseEstimationIteration
title: Operazione ContinuousPhaseEstimationIteration
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: ContinuousPhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.
ms.openlocfilehash: a3914a4b19e3b898b6de8808699da09d386f487a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715081"
---
# <a name="continuousphaseestimationiteration-operation"></a><span data-ttu-id="53831-102">Operazione ContinuousPhaseEstimationIteration</span><span class="sxs-lookup"><span data-stu-id="53831-102">ContinuousPhaseEstimationIteration operation</span></span>

<span data-ttu-id="53831-103">Spazio dei nomi: [Microsoft. Quantum. characteration](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="53831-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="53831-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="53831-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="53831-105">Esegue una singola iterazione di un algoritmo di stima della fase iterativo (controllo classico) utilizzando poteri reali arbitrari di un Oracle unitario.</span><span class="sxs-lookup"><span data-stu-id="53831-105">Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.</span></span>

```qsharp
operation ContinuousPhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.ContinuousOracle, time : Double, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="53831-106">Input</span><span class="sxs-lookup"><span data-stu-id="53831-106">Input</span></span>

### <a name="oracle--continuousoracle"></a><span data-ttu-id="53831-107">Oracle: [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span><span class="sxs-lookup"><span data-stu-id="53831-107">oracle : [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span></span>

<span data-ttu-id="53831-108">Operazione che agisce su un valore Double $t $ e un Register, in modo che $U ^ t $ venga applicato al registro specificato, dove $U $ è l'unità di cui è necessario stimare la fase e dove $t $ è la potenza Integer assegnata a Oracle</span><span class="sxs-lookup"><span data-stu-id="53831-108">Operation acting on a double $t$ and a register, such that $U^t$ is applied to the given register, where $U$ is the unitary whose phase is to be estimated, and where $t$ is the integer power given to the oracle</span></span>


### <a name="time--double"></a><span data-ttu-id="53831-109">Ora: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="53831-109">time : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="53831-110">Numero di volte in cui applicare l'oggetto Oracle unitario specificato.</span><span class="sxs-lookup"><span data-stu-id="53831-110">Number of times to apply the given unitary oracle.</span></span>


### <a name="theta--double"></a><span data-ttu-id="53831-111">Theta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="53831-111">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="53831-112">Angolo in base al quale invertire la fase sul controllo qubit prima di agire sullo stato di destinazione.</span><span class="sxs-lookup"><span data-stu-id="53831-112">Angle by which to invert the phase on the control qubit before acting on the target state.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="53831-113">targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="53831-113">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="53831-114">Registro dello stato a cui si basa il Oracle unitario specificato.</span><span class="sxs-lookup"><span data-stu-id="53831-114">Register of state acted upon by the given unitary oracle.</span></span>


### <a name="controlqubit--qubit"></a><span data-ttu-id="53831-115">controlQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="53831-115">controlQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="53831-116">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="53831-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

