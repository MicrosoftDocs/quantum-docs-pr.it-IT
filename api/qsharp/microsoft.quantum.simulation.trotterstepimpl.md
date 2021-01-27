---
uid: Microsoft.Quantum.Simulation.TrotterStepImpl
title: Operazione TrotterStepImpl
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStepImpl
qsharp.summary: Implements time-evolution by a term contained in a `GeneratorSystem`.
ms.openlocfilehash: 33dc922cd5a60590a1306369fb99615fc6575b22
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856738"
---
# <a name="trotterstepimpl-operation"></a><span data-ttu-id="5fa99-102">Operazione TrotterStepImpl</span><span class="sxs-lookup"><span data-stu-id="5fa99-102">TrotterStepImpl operation</span></span>

<span data-ttu-id="5fa99-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="5fa99-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="5fa99-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5fa99-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5fa99-105">Implementa l'evoluzione del tempo in base a un termine contenuto in un oggetto `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="5fa99-105">Implements time-evolution by a term contained in a `GeneratorSystem`.</span></span>

```qsharp
operation TrotterStepImpl (evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, idx : Int, stepsize : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5fa99-106">Input</span><span class="sxs-lookup"><span data-stu-id="5fa99-106">Input</span></span>

### <a name="evolutiongenerator--evolutiongenerator"></a><span data-ttu-id="5fa99-107">evolutionGenerator: [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="5fa99-107">evolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="5fa99-108">Descrizione completa del sistema da simulare.</span><span class="sxs-lookup"><span data-stu-id="5fa99-108">A complete description of the system to be simulated.</span></span>


### <a name="idx--int"></a><span data-ttu-id="5fa99-109">idx: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5fa99-109">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5fa99-110">Indice Integer a un termine nel sistema descritto.</span><span class="sxs-lookup"><span data-stu-id="5fa99-110">Integer index to a term in the described system.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="5fa99-111">STEPSIZE: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5fa99-111">stepsize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5fa99-112">Moltiplicatore per la durata dell'evoluzione del tempo per termine indicizzato da `idx` .</span><span class="sxs-lookup"><span data-stu-id="5fa99-112">Multiplier on duration of time-evolution by term indexed by `idx`.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="5fa99-113">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5fa99-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="5fa99-114">Qubits agito da simulazione.</span><span class="sxs-lookup"><span data-stu-id="5fa99-114">Qubits acted on by simulation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5fa99-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5fa99-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

