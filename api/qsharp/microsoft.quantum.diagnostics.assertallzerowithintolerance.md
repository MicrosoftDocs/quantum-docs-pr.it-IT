---
uid: Microsoft.Quantum.Diagnostics.AssertAllZeroWithinTolerance
title: Operazione AssertAllZeroWithinTolerance
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertAllZeroWithinTolerance
qsharp.summary: Assert that given qubits are all in $\ket{0}$ state up to a given tolerance.
ms.openlocfilehash: a2e73bbc8949b3cdb7733cfc8aae35680e54d2cf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202482"
---
# <a name="assertallzerowithintolerance-operation"></a><span data-ttu-id="b2e54-102">Operazione AssertAllZeroWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="b2e54-102">AssertAllZeroWithinTolerance operation</span></span>

<span data-ttu-id="b2e54-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="b2e54-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="b2e54-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="b2e54-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="b2e54-105">Dichiarare che i qubits specificati sono tutti nello stato $ \ket {0} $ fino a una determinata tolleranza.</span><span class="sxs-lookup"><span data-stu-id="b2e54-105">Assert that given qubits are all in $\ket{0}$ state up to a given tolerance.</span></span>

```qsharp
operation AssertAllZeroWithinTolerance (qubits : Qubit[], tolerance : Double) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="b2e54-106">Input</span><span class="sxs-lookup"><span data-stu-id="b2e54-106">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="b2e54-107">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b2e54-107">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b2e54-108">Qubits che vengono dichiarati come nello stato $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="b2e54-108">Qubits that are asserted to be in $\ket{0}$ state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="b2e54-109">tolleranza: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b2e54-109">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b2e54-110">Accuratezza con cui lo stato deve essere nello stato di $ \ket {0} $</span><span class="sxs-lookup"><span data-stu-id="b2e54-110">Accuracy with which the state should be in $\ket{0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="b2e54-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b2e54-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="b2e54-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2e54-112">See Also</span></span>

- [<span data-ttu-id="b2e54-113">Microsoft. Quantum. Diagnostics. AssertQubitWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="b2e54-113">Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance)