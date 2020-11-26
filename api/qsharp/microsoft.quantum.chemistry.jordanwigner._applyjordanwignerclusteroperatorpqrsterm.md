---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerClusterOperatorPQRSTerm
title: Operazione _ApplyJordanWignerClusterOperatorPQRSTerm
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerClusterOperatorPQRSTerm
qsharp.summary: Applies time-evolution by a cluster operator PQRS term described by a `GeneratorIndex`.
ms.openlocfilehash: 5e43f81714128629a63befccb31092adbe9c9e82
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204046"
---
# <a name="_applyjordanwignerclusteroperatorpqrsterm-operation"></a><span data-ttu-id="f65f4-102">Operazione _ApplyJordanWignerClusterOperatorPQRSTerm</span><span class="sxs-lookup"><span data-stu-id="f65f4-102">_ApplyJordanWignerClusterOperatorPQRSTerm operation</span></span>

<span data-ttu-id="f65f4-103">Spazio dei nomi: [Microsoft. Quantum. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="f65f4-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="f65f4-104">Pacchetto: [Microsoft. Quantum. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="f65f4-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="f65f4-105">Applica l'evoluzione del tempo da un operatore cluster PQRS termine descritto da `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="f65f4-105">Applies time-evolution by a cluster operator PQRS term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerClusterOperatorPQRSTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f65f4-106">Input</span><span class="sxs-lookup"><span data-stu-id="f65f4-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="f65f4-107">termine: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="f65f4-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="f65f4-108">`GeneratorIndex` che rappresenta un termine PQRS dell'operatore cluster.</span><span class="sxs-lookup"><span data-stu-id="f65f4-108">`GeneratorIndex` representing a cluster operator PQRS term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="f65f4-109">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f65f4-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f65f4-110">Durata dell'evoluzione del tempo.</span><span class="sxs-lookup"><span data-stu-id="f65f4-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="f65f4-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f65f4-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f65f4-112">Qubits di hamiltoniana.</span><span class="sxs-lookup"><span data-stu-id="f65f4-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f65f4-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f65f4-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

