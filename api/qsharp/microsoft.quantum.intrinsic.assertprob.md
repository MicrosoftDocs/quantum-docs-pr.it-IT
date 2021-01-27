---
uid: Microsoft.Quantum.Intrinsic.AssertProb
title: Operazione AssertProb
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: AssertProb
qsharp.summary: >-
  > [!WARNING]

  > AssertProb has been deprecated. Please use <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> instead.
ms.openlocfilehash: a3bdf8d6ae64f0d462da1781a723b27b6e1db05e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849447"
---
# <a name="assertprob-operation"></a><span data-ttu-id="59c8a-102">Operazione AssertProb</span><span class="sxs-lookup"><span data-stu-id="59c8a-102">AssertProb operation</span></span>

<span data-ttu-id="59c8a-103">Spazio dei nomi: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="59c8a-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="59c8a-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="59c8a-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


> [!WARNING]
> <span data-ttu-id="59c8a-105">AssertProb è stato deprecato.</span><span class="sxs-lookup"><span data-stu-id="59c8a-105">AssertProb has been deprecated.</span></span> <span data-ttu-id="59c8a-106">Usare invece <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability>.</span><span class="sxs-lookup"><span data-stu-id="59c8a-106">Please use <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> instead.</span></span>



```qsharp
operation AssertProb (bases : Pauli[], qubits : Qubit[], result : Result, prob : Double, msg : String, tol : Double) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="59c8a-107">Input</span><span class="sxs-lookup"><span data-stu-id="59c8a-107">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="59c8a-108">basi: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="59c8a-108">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>




### <a name="qubits--qubit"></a><span data-ttu-id="59c8a-109">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="59c8a-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="result--__invalidresult__"></a><span data-ttu-id="59c8a-110">risultato: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="59c8a-110">result : __invalid<Result>__</span></span>




### <a name="prob--double"></a><span data-ttu-id="59c8a-111">Probe: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="59c8a-111">prob : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="msg--string"></a><span data-ttu-id="59c8a-112">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="59c8a-112">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>




### <a name="tol--double"></a><span data-ttu-id="59c8a-113">Tol: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="59c8a-113">tol : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--unit"></a><span data-ttu-id="59c8a-114">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="59c8a-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

