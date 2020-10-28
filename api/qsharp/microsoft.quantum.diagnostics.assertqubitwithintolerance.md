---
uid: Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance
title: Operazione AssertQubitWithinTolerance
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitWithinTolerance
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.
ms.openlocfilehash: 3fe4aa739c5e15199401aecb76ef551e52f6dcff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712883"
---
# <a name="assertqubitwithintolerance-operation"></a><span data-ttu-id="849c2-102">Operazione AssertQubitWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="849c2-102">AssertQubitWithinTolerance operation</span></span>

<span data-ttu-id="849c2-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="849c2-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="849c2-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="849c2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="849c2-105">Asserisce che qubit `q` si trova nel autostato previsto dell'operatore Pauli Z fino a una determinata tolleranza.</span><span class="sxs-lookup"><span data-stu-id="849c2-105">Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.</span></span>

```qsharp
operation AssertQubitWithinTolerance (expected : Result, q : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="849c2-106">Input</span><span class="sxs-lookup"><span data-stu-id="849c2-106">Input</span></span>

### <a name="expected--__invalidresult__"></a><span data-ttu-id="849c2-107">previsto: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="849c2-107">expected : __invalid<Result>__</span></span>

<span data-ttu-id="849c2-108">Stato in cui si prevede che il qubit sia in: `Zero` o `One` .</span><span class="sxs-lookup"><span data-stu-id="849c2-108">Which state the qubit is expected to be in: `Zero` or `One`.</span></span>


### <a name="q--qubit"></a><span data-ttu-id="849c2-109">d: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="849c2-109">q : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="849c2-110">Qubit di cui viene dichiarato lo stato.</span><span class="sxs-lookup"><span data-stu-id="849c2-110">The qubit whose state is asserted.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="849c2-111">tolleranza: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="849c2-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="849c2-112">Tolleranza sulla probabilità di una misurazione di qubit che restituisce il risultato previsto.</span><span class="sxs-lookup"><span data-stu-id="849c2-112">Tolerance on the probability of a measurement of the qubit returning the expected result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="849c2-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="849c2-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="849c2-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="849c2-114">Remarks</span></span>

<span data-ttu-id="849c2-115"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> consente di dichiarare gli Stati qubit arbitrari anziché solo $Z $ autostati.</span><span class="sxs-lookup"><span data-stu-id="849c2-115"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> allows for asserting arbitrary qubit states rather than only $Z$ eigenstates.</span></span>

## <a name="see-also"></a><span data-ttu-id="849c2-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="849c2-116">See Also</span></span>

- [<span data-ttu-id="849c2-117">Microsoft. Quantum. Diagnostics. AssertQubitIsInStateWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="849c2-117">Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)