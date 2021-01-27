---
uid: Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance
title: Operazione AssertQubitWithinTolerance
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitWithinTolerance
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.
ms.openlocfilehash: 7f57fc7a29d3eb86dc94cb24230d52b37eb6971d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853428"
---
# <a name="assertqubitwithintolerance-operation"></a><span data-ttu-id="3a4db-102">Operazione AssertQubitWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="3a4db-102">AssertQubitWithinTolerance operation</span></span>

<span data-ttu-id="3a4db-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="3a4db-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="3a4db-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="3a4db-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="3a4db-105">Asserisce che qubit `q` si trova nel autostato previsto dell'operatore Pauli Z fino a una determinata tolleranza.</span><span class="sxs-lookup"><span data-stu-id="3a4db-105">Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.</span></span>

```qsharp
operation AssertQubitWithinTolerance (expected : Result, q : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="3a4db-106">Input</span><span class="sxs-lookup"><span data-stu-id="3a4db-106">Input</span></span>

### <a name="expected--__invalidresult__"></a><span data-ttu-id="3a4db-107">previsto: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="3a4db-107">expected : __invalid<Result>__</span></span>

<span data-ttu-id="3a4db-108">Stato in cui si prevede che il qubit sia in: `Zero` o `One` .</span><span class="sxs-lookup"><span data-stu-id="3a4db-108">Which state the qubit is expected to be in: `Zero` or `One`.</span></span>


### <a name="q--qubit"></a><span data-ttu-id="3a4db-109">d: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="3a4db-109">q : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="3a4db-110">Qubit di cui viene dichiarato lo stato.</span><span class="sxs-lookup"><span data-stu-id="3a4db-110">The qubit whose state is asserted.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="3a4db-111">tolleranza: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3a4db-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3a4db-112">Tolleranza sulla probabilità di una misurazione di qubit che restituisce il risultato previsto.</span><span class="sxs-lookup"><span data-stu-id="3a4db-112">Tolerance on the probability of a measurement of the qubit returning the expected result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3a4db-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3a4db-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3a4db-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="3a4db-114">Remarks</span></span>

<span data-ttu-id="3a4db-115"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> consente di dichiarare gli Stati qubit arbitrari anziché solo $Z $ autostati.</span><span class="sxs-lookup"><span data-stu-id="3a4db-115"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> allows for asserting arbitrary qubit states rather than only $Z$ eigenstates.</span></span>

## <a name="see-also"></a><span data-ttu-id="3a4db-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a4db-116">See Also</span></span>

- [<span data-ttu-id="3a4db-117">Microsoft. Quantum. Diagnostics. AssertQubitIsInStateWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="3a4db-117">Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)