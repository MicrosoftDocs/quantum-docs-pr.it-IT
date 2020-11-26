---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerPQandPQQRTerm_
title: Operazione _ApplyJordanWignerPQandPQQRTerm_
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerPQandPQQRTerm_
qsharp.summary: Applies time-evolution by a PQ or PQQR term described by a `GeneratorIndex`.
ms.openlocfilehash: 8b6d022c70052a91d3cf6d4549db5ed1434d3fc8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203978"
---
# <a name="_applyjordanwignerpqandpqqrterm_-operation"></a><span data-ttu-id="30b4e-102">Operazione _ApplyJordanWignerPQandPQQRTerm_</span><span class="sxs-lookup"><span data-stu-id="30b4e-102">_ApplyJordanWignerPQandPQQRTerm_ operation</span></span>

<span data-ttu-id="30b4e-103">Spazio dei nomi: [Microsoft. Quantum. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="30b4e-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="30b4e-104">Pacchetto: [Microsoft. Quantum. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="30b4e-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="30b4e-105">Applica l'evoluzione del tempo in base a un termine PQ o PQQR descritto da `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="30b4e-105">Applies time-evolution by a PQ or PQQR term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerPQandPQQRTerm_ (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="30b4e-106">Input</span><span class="sxs-lookup"><span data-stu-id="30b4e-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="30b4e-107">termine: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="30b4e-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="30b4e-108">`GeneratorIndex` che rappresenta un termine PQ o PQQR.</span><span class="sxs-lookup"><span data-stu-id="30b4e-108">`GeneratorIndex` representing a PQ or PQQR term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="30b4e-109">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="30b4e-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="30b4e-110">Durata dell'evoluzione del tempo.</span><span class="sxs-lookup"><span data-stu-id="30b4e-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="30b4e-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="30b4e-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="30b4e-112">Qubits di hamiltoniana.</span><span class="sxs-lookup"><span data-stu-id="30b4e-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="30b4e-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="30b4e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

