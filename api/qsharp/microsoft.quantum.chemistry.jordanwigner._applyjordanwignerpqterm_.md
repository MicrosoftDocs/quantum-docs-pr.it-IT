---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerPQTerm_
title: Operazione _ApplyJordanWignerPQTerm_
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerPQTerm_
qsharp.summary: Applies time-evolution by a PQ term described by a `GeneratorIndex`.
ms.openlocfilehash: 6e7d3e422ea751371eeb3111dce88acc6eaf3b62
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851724"
---
# <a name="_applyjordanwignerpqterm_-operation"></a><span data-ttu-id="9910b-102">Operazione _ApplyJordanWignerPQTerm_</span><span class="sxs-lookup"><span data-stu-id="9910b-102">_ApplyJordanWignerPQTerm_ operation</span></span>

<span data-ttu-id="9910b-103">Spazio dei nomi: [Microsoft. Quantum. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="9910b-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="9910b-104">Pacchetto: [Microsoft. Quantum. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="9910b-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="9910b-105">Applica l'evoluzione del tempo in base a un termine PQ descritto da un oggetto `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="9910b-105">Applies time-evolution by a PQ term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerPQTerm_ (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, extraParityQubits : Qubit[], qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="9910b-106">Input</span><span class="sxs-lookup"><span data-stu-id="9910b-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="9910b-107">termine: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="9910b-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="9910b-108">`GeneratorIndex` che rappresenta un termine PQ.</span><span class="sxs-lookup"><span data-stu-id="9910b-108">`GeneratorIndex` representing a PQ term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="9910b-109">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9910b-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9910b-110">Durata dell'evoluzione del tempo.</span><span class="sxs-lookup"><span data-stu-id="9910b-110">Duration of time-evolution.</span></span>


### <a name="extraparityqubits--qubit"></a><span data-ttu-id="9910b-111">extraParityQubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9910b-111">extraParityQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9910b-112">Qubits di parità facoltativa che capovolge il segno di evoluzione del tempo.</span><span class="sxs-lookup"><span data-stu-id="9910b-112">Optional parity qubits that flip the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="9910b-113">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9910b-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9910b-114">Qubits di hamiltoniana.</span><span class="sxs-lookup"><span data-stu-id="9910b-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9910b-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9910b-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

