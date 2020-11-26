---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimized0123Term
title: Operazione _JWOptimized0123Term
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimized0123Term
qsharp.summary: Applies time-evolution by a PQRS term described by a `GeneratorIndex`.
ms.openlocfilehash: 9d04a866323112944aa922fafdf6fd397851277d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226095"
---
# <a name="_jwoptimized0123term-operation"></a><span data-ttu-id="978c2-102">Operazione _JWOptimized0123Term</span><span class="sxs-lookup"><span data-stu-id="978c2-102">_JWOptimized0123Term operation</span></span>

<span data-ttu-id="978c2-103">Spazio dei nomi: [Microsoft. Quantum. Research. Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="978c2-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="978c2-104">Pacchetto: [Microsoft. Quantum. Research. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="978c2-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="978c2-105">Applica l'evoluzione del tempo in base a un termine PQRS descritto da `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="978c2-105">Applies time-evolution by a PQRS term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _JWOptimized0123Term (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="978c2-106">Input</span><span class="sxs-lookup"><span data-stu-id="978c2-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="978c2-107">termine: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="978c2-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="978c2-108">`GeneratorIndex` che rappresenta un termine PQRS.</span><span class="sxs-lookup"><span data-stu-id="978c2-108">`GeneratorIndex` representing a PQRS term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="978c2-109">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="978c2-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="978c2-110">Durata dell'evoluzione del tempo.</span><span class="sxs-lookup"><span data-stu-id="978c2-110">Duration of time-evolution.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="978c2-111">parityQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="978c2-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="978c2-112">Qubit che determina il segno di evoluzione del tempo.</span><span class="sxs-lookup"><span data-stu-id="978c2-112">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="978c2-113">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="978c2-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="978c2-114">Qubits di hamiltoniana.</span><span class="sxs-lookup"><span data-stu-id="978c2-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="978c2-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="978c2-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

