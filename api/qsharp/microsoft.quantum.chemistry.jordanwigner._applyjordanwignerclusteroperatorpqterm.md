---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerClusterOperatorPQTerm
title: Operazione _ApplyJordanWignerClusterOperatorPQTerm
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerClusterOperatorPQTerm
qsharp.summary: Applies time-evolution by a cluster operator PQ term described by a `GeneratorIndex`.
ms.openlocfilehash: d72ddea439c45936caefa74add4a0444afe4318e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714815"
---
# <a name="_applyjordanwignerclusteroperatorpqterm-operation"></a><span data-ttu-id="72a62-102">Operazione _ApplyJordanWignerClusterOperatorPQTerm</span><span class="sxs-lookup"><span data-stu-id="72a62-102">_ApplyJordanWignerClusterOperatorPQTerm operation</span></span>

<span data-ttu-id="72a62-103">Spazio dei nomi: [Microsoft. Quantum. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="72a62-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="72a62-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="72a62-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="72a62-105">Applica l'evoluzione temporale da un operatore cluster termine PQ descritto da un `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="72a62-105">Applies time-evolution by a cluster operator PQ term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerClusterOperatorPQTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="72a62-106">Input</span><span class="sxs-lookup"><span data-stu-id="72a62-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="72a62-107">termine: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="72a62-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="72a62-108">`GeneratorIndex` che rappresenta un termine PQ dell'operatore cluster.</span><span class="sxs-lookup"><span data-stu-id="72a62-108">`GeneratorIndex` representing a cluster operator PQ term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="72a62-109">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="72a62-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="72a62-110">Durata dell'evoluzione del tempo.</span><span class="sxs-lookup"><span data-stu-id="72a62-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="72a62-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="72a62-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="72a62-112">Qubits di hamiltoniana.</span><span class="sxs-lookup"><span data-stu-id="72a62-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="72a62-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="72a62-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

