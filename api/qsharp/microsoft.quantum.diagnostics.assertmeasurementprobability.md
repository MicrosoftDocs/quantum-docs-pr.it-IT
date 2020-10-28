---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurementProbability
title: Operazione AssertMeasurementProbability
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurementProbability
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.
ms.openlocfilehash: ff0419706d825442492f82e564f1cce86f1b112f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712981"
---
# <a name="assertmeasurementprobability-operation"></a><span data-ttu-id="2c1ab-102">Operazione AssertMeasurementProbability</span><span class="sxs-lookup"><span data-stu-id="2c1ab-102">AssertMeasurementProbability operation</span></span>

<span data-ttu-id="2c1ab-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="2c1ab-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="2c1ab-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2c1ab-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2c1ab-105">Le asserzioni che misurano il qubits specificato in base a Pauli specificato avranno il risultato specificato con la probabilità specificata, entro una certa tolleranza.</span><span class="sxs-lookup"><span data-stu-id="2c1ab-105">Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.</span></span>

```qsharp
operation AssertMeasurementProbability (bases : Pauli[], qubits : Qubit[], result : Result, prob : Double, msg : String, tol : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="2c1ab-106">Input</span><span class="sxs-lookup"><span data-stu-id="2c1ab-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="2c1ab-107">basi: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="2c1ab-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="2c1ab-108">Un effetto di misura per dichiarare la probabilità di, espressa come un operatore Pauli multiqubit.</span><span class="sxs-lookup"><span data-stu-id="2c1ab-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="2c1ab-109">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2c1ab-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2c1ab-110">Registro in cui eseguire l'asserzione.</span><span class="sxs-lookup"><span data-stu-id="2c1ab-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="2c1ab-111">risultato: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="2c1ab-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="2c1ab-112">Risultato previsto di `Measure(bases, qubits)` .</span><span class="sxs-lookup"><span data-stu-id="2c1ab-112">An expected result of `Measure(bases, qubits)`.</span></span>


### <a name="prob--double"></a><span data-ttu-id="2c1ab-113">Probe: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2c1ab-113">prob : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2c1ab-114">Probabilità con cui è previsto il risultato specificato.</span><span class="sxs-lookup"><span data-stu-id="2c1ab-114">The probability with which the given result is expected.</span></span>


### <a name="msg--string"></a><span data-ttu-id="2c1ab-115">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="2c1ab-115">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="2c1ab-116">Messaggio da segnalare se l'asserzione ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="2c1ab-116">A message to be reported if the assertion fails.</span></span>


### <a name="tol--double"></a><span data-ttu-id="2c1ab-117">Tol: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2c1ab-117">tol : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--unit"></a><span data-ttu-id="2c1ab-118">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2c1ab-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2c1ab-119">Commenti</span><span class="sxs-lookup"><span data-stu-id="2c1ab-119">Remarks</span></span>

<span data-ttu-id="2c1ab-120">Si noti che le versioni adiacenti e controllate di questa operazione non verificheranno la condizione.</span><span class="sxs-lookup"><span data-stu-id="2c1ab-120">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="2c1ab-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c1ab-121">See Also</span></span>

- [<span data-ttu-id="2c1ab-122">Microsoft. Quantum. Diagnostics. AssertMeasurement</span><span class="sxs-lookup"><span data-stu-id="2c1ab-122">Microsoft.Quantum.Diagnostics.AssertMeasurement</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement)