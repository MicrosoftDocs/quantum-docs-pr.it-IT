---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurement
title: Operazione AssertMeasurement
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurement
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will always have the given result.
ms.openlocfilehash: 09024cd8cd6e713360dcf7f42f55941590f35883
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713037"
---
# <a name="assertmeasurement-operation"></a><span data-ttu-id="ea053-102">Operazione AssertMeasurement</span><span class="sxs-lookup"><span data-stu-id="ea053-102">AssertMeasurement operation</span></span>

<span data-ttu-id="ea053-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="ea053-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="ea053-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ea053-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ea053-105">Le asserzioni che misurano il qubits specificato in base a Pauli specificato avranno sempre il risultato specificato.</span><span class="sxs-lookup"><span data-stu-id="ea053-105">Asserts that measuring the given qubits in the given Pauli basis will always have the given result.</span></span>

```qsharp
operation AssertMeasurement (bases : Pauli[], qubits : Qubit[], result : Result, msg : String) : Unit
```


## <a name="input"></a><span data-ttu-id="ea053-106">Input</span><span class="sxs-lookup"><span data-stu-id="ea053-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="ea053-107">basi: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="ea053-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="ea053-108">Un effetto di misura per dichiarare la probabilità di, espressa come un operatore Pauli multiqubit.</span><span class="sxs-lookup"><span data-stu-id="ea053-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="ea053-109">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ea053-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ea053-110">Registro in cui eseguire l'asserzione.</span><span class="sxs-lookup"><span data-stu-id="ea053-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="ea053-111">risultato: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="ea053-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="ea053-112">Risultato previsto di `Measure(bases, qubits)` .</span><span class="sxs-lookup"><span data-stu-id="ea053-112">The expected result of `Measure(bases, qubits)`.</span></span>


### <a name="msg--string"></a><span data-ttu-id="ea053-113">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="ea053-113">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="ea053-114">Messaggio da segnalare se l'asserzione ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="ea053-114">A message to be reported if the assertion fails.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ea053-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ea053-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ea053-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="ea053-116">Remarks</span></span>

<span data-ttu-id="ea053-117">Si noti che le versioni adiacenti e controllate di questa operazione non verificheranno la condizione.</span><span class="sxs-lookup"><span data-stu-id="ea053-117">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="ea053-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea053-118">See Also</span></span>

- [<span data-ttu-id="ea053-119">Microsoft. Quantum. Diagnostics. AssertMeasurementProbability</span><span class="sxs-lookup"><span data-stu-id="ea053-119">Microsoft.Quantum.Diagnostics.AssertMeasurementProbability</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability)