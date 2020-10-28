---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWigner0123Term_
title: Operazione _ApplyJordanWigner0123Term_
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWigner0123Term_
qsharp.summary: Applies time-evolution by a PQRS term described by a `GeneratorIndex`.
ms.openlocfilehash: 36590b2ee9f6f6c2b5e076f8e334dfe7b0144e5e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714818"
---
# <a name="_applyjordanwigner0123term_-operation"></a><span data-ttu-id="f3589-102">Operazione _ApplyJordanWigner0123Term_</span><span class="sxs-lookup"><span data-stu-id="f3589-102">_ApplyJordanWigner0123Term_ operation</span></span>

<span data-ttu-id="f3589-103">Spazio dei nomi: [Microsoft. Quantum. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="f3589-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="f3589-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f3589-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f3589-105">Applica l'evoluzione del tempo in base a un termine PQRS descritto da `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="f3589-105">Applies time-evolution by a PQRS term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWigner0123Term_ (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="f3589-106">Input</span><span class="sxs-lookup"><span data-stu-id="f3589-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="f3589-107">termine: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="f3589-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="f3589-108">`GeneratorIndex` che rappresenta un termine PQRS.</span><span class="sxs-lookup"><span data-stu-id="f3589-108">`GeneratorIndex` representing a PQRS term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="f3589-109">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f3589-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f3589-110">Durata dell'evoluzione del tempo.</span><span class="sxs-lookup"><span data-stu-id="f3589-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="f3589-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f3589-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f3589-112">Qubits di hamiltoniana.</span><span class="sxs-lookup"><span data-stu-id="f3589-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f3589-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f3589-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

