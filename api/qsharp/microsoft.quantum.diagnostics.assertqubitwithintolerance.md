---
uid: Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance
title: Operazione AssertQubitWithinTolerance
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitWithinTolerance
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.
ms.openlocfilehash: 56b7f93f33ae18146c1fb13d404fc1d119eee72e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202193"
---
# <a name="assertqubitwithintolerance-operation"></a><span data-ttu-id="ff0fa-102">Operazione AssertQubitWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="ff0fa-102">AssertQubitWithinTolerance operation</span></span>

<span data-ttu-id="ff0fa-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="ff0fa-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="ff0fa-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="ff0fa-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="ff0fa-105">Asserisce che qubit `q` si trova nel autostato previsto dell'operatore Pauli Z fino a una determinata tolleranza.</span><span class="sxs-lookup"><span data-stu-id="ff0fa-105">Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.</span></span>

```qsharp
operation AssertQubitWithinTolerance (expected : Result, q : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="ff0fa-106">Input</span><span class="sxs-lookup"><span data-stu-id="ff0fa-106">Input</span></span>

### <a name="expected--__invalidresult__"></a><span data-ttu-id="ff0fa-107">previsto: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="ff0fa-107">expected : __invalid<Result>__</span></span>

<span data-ttu-id="ff0fa-108">Stato in cui si prevede che il qubit sia in: `Zero` o `One` .</span><span class="sxs-lookup"><span data-stu-id="ff0fa-108">Which state the qubit is expected to be in: `Zero` or `One`.</span></span>


### <a name="q--qubit"></a><span data-ttu-id="ff0fa-109">d: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ff0fa-109">q : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ff0fa-110">Qubit di cui viene dichiarato lo stato.</span><span class="sxs-lookup"><span data-stu-id="ff0fa-110">The qubit whose state is asserted.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="ff0fa-111">tolleranza: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ff0fa-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ff0fa-112">Tolleranza sulla probabilità di una misurazione di qubit che restituisce il risultato previsto.</span><span class="sxs-lookup"><span data-stu-id="ff0fa-112">Tolerance on the probability of a measurement of the qubit returning the expected result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ff0fa-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ff0fa-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ff0fa-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="ff0fa-114">Remarks</span></span>

<span data-ttu-id="ff0fa-115"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> consente di dichiarare gli Stati qubit arbitrari anziché solo $Z $ autostati.</span><span class="sxs-lookup"><span data-stu-id="ff0fa-115"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> allows for asserting arbitrary qubit states rather than only $Z$ eigenstates.</span></span>

## <a name="see-also"></a><span data-ttu-id="ff0fa-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff0fa-116">See Also</span></span>

- [<span data-ttu-id="ff0fa-117">Microsoft. Quantum. Diagnostics. AssertQubitIsInStateWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="ff0fa-117">Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)