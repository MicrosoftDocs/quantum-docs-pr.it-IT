---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlaceCompBasis
title: Operazione AssertOperationsEqualInPlaceCompBasis
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlaceCompBasis
qsharp.summary: Checks if the operation `givenU` is equal to the operation `expectedU` on the given input size  by checking the action of the operations only on the vectors from the computational basis. This is a necessary, but not sufficient, condition for the equality of two unitaries.
ms.openlocfilehash: 3275680f86ca2a178c7f044b97d226fe41c3186c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712967"
---
# <a name="assertoperationsequalinplacecompbasis-operation"></a><span data-ttu-id="52b84-102">Operazione AssertOperationsEqualInPlaceCompBasis</span><span class="sxs-lookup"><span data-stu-id="52b84-102">AssertOperationsEqualInPlaceCompBasis operation</span></span>

<span data-ttu-id="52b84-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="52b84-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="52b84-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="52b84-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="52b84-105">Verifica se l'operazione `givenU` è uguale all'operazione `expectedU` sulla dimensione di input specificata controllando l'azione delle operazioni solo sui vettori dalla base computazionale.</span><span class="sxs-lookup"><span data-stu-id="52b84-105">Checks if the operation `givenU` is equal to the operation `expectedU` on the given input size  by checking the action of the operations only on the vectors from the computational basis.</span></span>
<span data-ttu-id="52b84-106">Si tratta di una condizione necessaria, ma non sufficiente, per l'uguaglianza di due unitaries.</span><span class="sxs-lookup"><span data-stu-id="52b84-106">This is a necessary, but not sufficient, condition for the equality of two unitaries.</span></span>

```qsharp
operation AssertOperationsEqualInPlaceCompBasis (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="52b84-107">Input</span><span class="sxs-lookup"><span data-stu-id="52b84-107">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="52b84-108">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="52b84-108">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="52b84-109">Il numero di qubits $n $ `givenU` su cui operano le operazioni e `expectedU` .</span><span class="sxs-lookup"><span data-stu-id="52b84-109">The number of qubits $n$ that the operations `givenU` and `expectedU` operate on.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="52b84-110">dato: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="52b84-110">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="52b84-111">Operazione su $n $ qubits da controllare.</span><span class="sxs-lookup"><span data-stu-id="52b84-111">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit-adj"></a><span data-ttu-id="52b84-112">previsto: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ</span><span class="sxs-lookup"><span data-stu-id="52b84-112">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="52b84-113">Operazione di riferimento su $n $ qubits da `givenU` confrontare con.</span><span class="sxs-lookup"><span data-stu-id="52b84-113">Reference operation on $n$ qubits that `givenU` is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="52b84-114">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="52b84-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

