---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurementProbability
title: Operazione AssertMeasurementProbability
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurementProbability
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.
ms.openlocfilehash: 032b9224ad728f0637596668c2928a889deeba55
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202363"
---
# <a name="assertmeasurementprobability-operation"></a><span data-ttu-id="70fb9-102">Operazione AssertMeasurementProbability</span><span class="sxs-lookup"><span data-stu-id="70fb9-102">AssertMeasurementProbability operation</span></span>

<span data-ttu-id="70fb9-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="70fb9-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="70fb9-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="70fb9-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="70fb9-105">Le asserzioni che misurano il qubits specificato in base a Pauli specificato avranno il risultato specificato con la probabilità specificata, entro una certa tolleranza.</span><span class="sxs-lookup"><span data-stu-id="70fb9-105">Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.</span></span>

```qsharp
operation AssertMeasurementProbability (bases : Pauli[], qubits : Qubit[], result : Result, prob : Double, msg : String, tol : Double) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="70fb9-106">Input</span><span class="sxs-lookup"><span data-stu-id="70fb9-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="70fb9-107">basi: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="70fb9-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="70fb9-108">Un effetto di misura per dichiarare la probabilità di, espressa come un operatore Pauli multiqubit.</span><span class="sxs-lookup"><span data-stu-id="70fb9-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="70fb9-109">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="70fb9-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="70fb9-110">Registro in cui eseguire l'asserzione.</span><span class="sxs-lookup"><span data-stu-id="70fb9-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="70fb9-111">risultato: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="70fb9-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="70fb9-112">Risultato previsto di `Measure(bases, qubits)` .</span><span class="sxs-lookup"><span data-stu-id="70fb9-112">An expected result of `Measure(bases, qubits)`.</span></span>


### <a name="prob--double"></a><span data-ttu-id="70fb9-113">Probe: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="70fb9-113">prob : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="70fb9-114">Probabilità con cui è previsto il risultato specificato.</span><span class="sxs-lookup"><span data-stu-id="70fb9-114">The probability with which the given result is expected.</span></span>


### <a name="msg--string"></a><span data-ttu-id="70fb9-115">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="70fb9-115">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="70fb9-116">Messaggio da segnalare se l'asserzione ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="70fb9-116">A message to be reported if the assertion fails.</span></span>


### <a name="tol--double"></a><span data-ttu-id="70fb9-117">Tol: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="70fb9-117">tol : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--unit"></a><span data-ttu-id="70fb9-118">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="70fb9-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="70fb9-119">Commenti</span><span class="sxs-lookup"><span data-stu-id="70fb9-119">Remarks</span></span>

<span data-ttu-id="70fb9-120">Si noti che le versioni adiacenti e controllate di questa operazione non verificheranno la condizione.</span><span class="sxs-lookup"><span data-stu-id="70fb9-120">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="70fb9-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70fb9-121">See Also</span></span>

- [<span data-ttu-id="70fb9-122">Microsoft. Quantum. Diagnostics. AssertMeasurement</span><span class="sxs-lookup"><span data-stu-id="70fb9-122">Microsoft.Quantum.Diagnostics.AssertMeasurement</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement)