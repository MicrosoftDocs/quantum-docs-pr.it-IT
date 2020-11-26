---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedPQandPQQRTerm
title: Operazione _JWOptimizedPQandPQQRTerm
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedPQandPQQRTerm
qsharp.summary: Applies time-evolution by a PQ or PQQR term described by a `GeneratorIndex`.
ms.openlocfilehash: 96ea3e4ada66733502af7531c8be99de44596dca
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225891"
---
# <a name="_jwoptimizedpqandpqqrterm-operation"></a><span data-ttu-id="f498e-102">Operazione _JWOptimizedPQandPQQRTerm</span><span class="sxs-lookup"><span data-stu-id="f498e-102">_JWOptimizedPQandPQQRTerm operation</span></span>

<span data-ttu-id="f498e-103">Spazio dei nomi: [Microsoft. Quantum. Research. Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="f498e-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="f498e-104">Pacchetto: [Microsoft. Quantum. Research. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="f498e-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="f498e-105">Applica l'evoluzione del tempo in base a un termine PQ o PQQR descritto da `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="f498e-105">Applies time-evolution by a PQ or PQQR term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _JWOptimizedPQandPQQRTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f498e-106">Input</span><span class="sxs-lookup"><span data-stu-id="f498e-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="f498e-107">termine: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="f498e-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="f498e-108">`GeneratorIndex` che rappresenta un termine PQ o PQQr.</span><span class="sxs-lookup"><span data-stu-id="f498e-108">`GeneratorIndex` representing a PQ or PQQr term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="f498e-109">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f498e-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f498e-110">Durata dell'evoluzione del tempo.</span><span class="sxs-lookup"><span data-stu-id="f498e-110">Duration of time-evolution.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="f498e-111">parityQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f498e-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f498e-112">Qubit che determina il segno di evoluzione del tempo.</span><span class="sxs-lookup"><span data-stu-id="f498e-112">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="f498e-113">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f498e-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f498e-114">Qubits di hamiltoniana.</span><span class="sxs-lookup"><span data-stu-id="f498e-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f498e-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f498e-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

