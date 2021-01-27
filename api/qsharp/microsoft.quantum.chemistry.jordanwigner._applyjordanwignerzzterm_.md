---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerZZTerm_
title: Operazione _ApplyJordanWignerZZTerm_
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerZZTerm_
qsharp.summary: Applies time-evolution by a ZZ term described by a `GeneratorIndex`.
ms.openlocfilehash: 4ecf6279595d12d4262aa6786d908270707b95bc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851675"
---
# <a name="_applyjordanwignerzzterm_-operation"></a><span data-ttu-id="d50b8-102">Operazione _ApplyJordanWignerZZTerm_</span><span class="sxs-lookup"><span data-stu-id="d50b8-102">_ApplyJordanWignerZZTerm_ operation</span></span>

<span data-ttu-id="d50b8-103">Spazio dei nomi: [Microsoft. Quantum. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="d50b8-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="d50b8-104">Pacchetto: [Microsoft. Quantum. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="d50b8-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="d50b8-105">Applica l'evoluzione del tempo in base a un termine ZZ descritto da un oggetto `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="d50b8-105">Applies time-evolution by a ZZ term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerZZTerm_ (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d50b8-106">Input</span><span class="sxs-lookup"><span data-stu-id="d50b8-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="d50b8-107">termine: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="d50b8-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="d50b8-108">`GeneratorIndex` che rappresenta un termine ZZ.</span><span class="sxs-lookup"><span data-stu-id="d50b8-108">`GeneratorIndex` representing a ZZ term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="d50b8-109">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d50b8-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d50b8-110">Durata dell'evoluzione del tempo.</span><span class="sxs-lookup"><span data-stu-id="d50b8-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="d50b8-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d50b8-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d50b8-112">Qubits di hamiltoniana.</span><span class="sxs-lookup"><span data-stu-id="d50b8-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d50b8-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d50b8-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

