---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedZZTerm
title: Operazione _JWOptimizedZZTerm
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedZZTerm
qsharp.summary: Applies time-evolution by a ZZ term described by a `GeneratorIndex`.
ms.openlocfilehash: 7fdda06b88ce03e0d76b7b589e50b460f0a5ff48
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225806"
---
# <a name="_jwoptimizedzzterm-operation"></a><span data-ttu-id="b8387-102">Operazione _JWOptimizedZZTerm</span><span class="sxs-lookup"><span data-stu-id="b8387-102">_JWOptimizedZZTerm operation</span></span>

<span data-ttu-id="b8387-103">Spazio dei nomi: [Microsoft. Quantum. Research. Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="b8387-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="b8387-104">Pacchetto: [Microsoft. Quantum. Research. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="b8387-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="b8387-105">Applica l'evoluzione del tempo in base a un termine ZZ descritto da un oggetto `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="b8387-105">Applies time-evolution by a ZZ term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _JWOptimizedZZTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="b8387-106">Input</span><span class="sxs-lookup"><span data-stu-id="b8387-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="b8387-107">termine: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="b8387-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="b8387-108">`GeneratorIndex` che rappresenta un termine ZZ.</span><span class="sxs-lookup"><span data-stu-id="b8387-108">`GeneratorIndex` representing a ZZ term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="b8387-109">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b8387-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b8387-110">Durata dell'evoluzione del tempo.</span><span class="sxs-lookup"><span data-stu-id="b8387-110">Duration of time-evolution.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="b8387-111">parityQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b8387-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b8387-112">Qubit che determina il segno di evoluzione del tempo.</span><span class="sxs-lookup"><span data-stu-id="b8387-112">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="b8387-113">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b8387-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b8387-114">Qubits di hamiltoniana.</span><span class="sxs-lookup"><span data-stu-id="b8387-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b8387-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b8387-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

