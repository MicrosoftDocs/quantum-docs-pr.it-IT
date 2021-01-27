---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerClusterOperatorPQTerm
title: Operazione _ApplyJordanWignerClusterOperatorPQTerm
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerClusterOperatorPQTerm
qsharp.summary: Applies time-evolution by a cluster operator PQ term described by a `GeneratorIndex`.
ms.openlocfilehash: 67ec6fcfec097a14b1e31f94ac82ecf15109ecf6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851729"
---
# <a name="_applyjordanwignerclusteroperatorpqterm-operation"></a><span data-ttu-id="0b731-102">Operazione _ApplyJordanWignerClusterOperatorPQTerm</span><span class="sxs-lookup"><span data-stu-id="0b731-102">_ApplyJordanWignerClusterOperatorPQTerm operation</span></span>

<span data-ttu-id="0b731-103">Spazio dei nomi: [Microsoft. Quantum. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="0b731-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="0b731-104">Pacchetto: [Microsoft. Quantum. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="0b731-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="0b731-105">Applica l'evoluzione temporale da un operatore cluster termine PQ descritto da un `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="0b731-105">Applies time-evolution by a cluster operator PQ term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerClusterOperatorPQTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="0b731-106">Input</span><span class="sxs-lookup"><span data-stu-id="0b731-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="0b731-107">termine: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="0b731-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="0b731-108">`GeneratorIndex` che rappresenta un termine PQ dell'operatore cluster.</span><span class="sxs-lookup"><span data-stu-id="0b731-108">`GeneratorIndex` representing a cluster operator PQ term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="0b731-109">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0b731-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0b731-110">Durata dell'evoluzione del tempo.</span><span class="sxs-lookup"><span data-stu-id="0b731-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="0b731-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0b731-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0b731-112">Qubits di hamiltoniana.</span><span class="sxs-lookup"><span data-stu-id="0b731-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0b731-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0b731-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

