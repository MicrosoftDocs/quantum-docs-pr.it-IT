---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced
title: Operazione AssertOperationsEqualReferenced
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualReferenced
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by using the Choi–Jamiołkowski isomorphism to reduce the assertion to one of a qubit state assertion on two entangled registers. Thus, this operation needs only a single call to each operation being tested, but requires twice as many qubits to be allocated. This assertion can be used to ensure, for instance, that an optimized version of an operation acts identically to its naïve implementation, or that an operation which acts on a range of non-quantum inputs agrees with known cases.
ms.openlocfilehash: 045f00a720e9f4d2e6993c66ace44a81e192ff30
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853475"
---
# <a name="assertoperationsequalreferenced-operation"></a><span data-ttu-id="a8ad3-102">Operazione AssertOperationsEqualReferenced</span><span class="sxs-lookup"><span data-stu-id="a8ad3-102">AssertOperationsEqualReferenced operation</span></span>

<span data-ttu-id="a8ad3-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="a8ad3-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="a8ad3-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a8ad3-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="a8ad3-105">Date due operazioni, asserisce che agiscono in modo identico per tutti gli Stati di input.</span><span class="sxs-lookup"><span data-stu-id="a8ad3-105">Given two operations, asserts that they act identically for all input states.</span></span>

<span data-ttu-id="a8ad3-106">Questa asserzione viene implementata usando il isomorfismo Choi-Jamiołkowski per ridurre l'asserzione a una delle asserzioni di stato qubit su due registri coinvolti.</span><span class="sxs-lookup"><span data-stu-id="a8ad3-106">This assertion is implemented by using the Choi–Jamiołkowski isomorphism to reduce the assertion to one of a qubit state assertion on two entangled registers.</span></span>
<span data-ttu-id="a8ad3-107">Pertanto, per questa operazione è necessaria una sola chiamata a ogni operazione sottoposta a test, ma è necessario allocare un numero di qubits pari al doppio.</span><span class="sxs-lookup"><span data-stu-id="a8ad3-107">Thus, this operation needs only a single call to each operation being tested, but requires twice as many qubits to be allocated.</span></span>
<span data-ttu-id="a8ad3-108">Questa asserzione può essere usata per garantire, ad esempio, che una versione ottimizzata di un'operazione agisca in modo identico alla relativa implementazione ingenua o che un'operazione che agisce su un intervallo di input non quantistici accetti i casi noti.</span><span class="sxs-lookup"><span data-stu-id="a8ad3-108">This assertion can be used to ensure, for instance, that an optimized version of an operation acts identically to its naïve implementation, or that an operation which acts on a range of non-quantum inputs agrees with known cases.</span></span>

```qsharp
operation AssertOperationsEqualReferenced (nQubits : Int, actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="a8ad3-109">Input</span><span class="sxs-lookup"><span data-stu-id="a8ad3-109">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="a8ad3-110">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a8ad3-110">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a8ad3-111">Numero di qubits da passare a ogni operazione.</span><span class="sxs-lookup"><span data-stu-id="a8ad3-111">Number of qubits to pass to each operation.</span></span>


### <a name="actual--qubit--unit"></a><span data-ttu-id="a8ad3-112">effettivo: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="a8ad3-112">actual : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="a8ad3-113">Operazione da verificare.</span><span class="sxs-lookup"><span data-stu-id="a8ad3-113">Operation to be tested.</span></span>


### <a name="expected--qubit--unit--is-adj"></a><span data-ttu-id="a8ad3-114">previsto: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ</span><span class="sxs-lookup"><span data-stu-id="a8ad3-114">expected : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="a8ad3-115">Operazione che definisce il comportamento previsto per l'operazione sottoposta a test.</span><span class="sxs-lookup"><span data-stu-id="a8ad3-115">Operation defining the expected behavior for the operation under test.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a8ad3-116">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a8ad3-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a8ad3-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="a8ad3-117">Remarks</span></span>

<span data-ttu-id="a8ad3-118">Questa operazione richiede che l'operazione di modellazione del comportamento previsto sia adjointable, in modo che l'inverso possa essere eseguito solo sul Registro di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a8ad3-118">This operation requires that the operation modeling the expected behavior is adjointable, so that the inverse can be performed on the target register alone.</span></span>
<span data-ttu-id="a8ad3-119">Formalmente, è possibile specificare un'operazione di trasposizione, che consente di attenuare questo requisito, ma l'operazione di trasposizione non è in genere fisicamente realizzabile per le operazioni Quantum arbitrarie e pertanto non è inclusa in questa opzione.</span><span class="sxs-lookup"><span data-stu-id="a8ad3-119">Formally, one can specify a transpose operation, which relaxes this requirement, but the transpose operation is not in general physically realizable for arbitrary quantum operations and thus is not included here as an option.</span></span>