---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: Operazione AssertProbInt
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: a8e4217e18528adc0aa9923f1c0dcfb59e1d2488
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721362"
---
# <a name="assertprobint-operation"></a><span data-ttu-id="54205-102">Operazione AssertProbInt</span><span class="sxs-lookup"><span data-stu-id="54205-102">AssertProbInt operation</span></span>

<span data-ttu-id="54205-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="54205-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="54205-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="54205-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="54205-105">Asserisce che la probabilità di uno stato specifico di un registro Quantum presenta il valore previsto.</span><span class="sxs-lookup"><span data-stu-id="54205-105">Asserts that the probability of a specific state of a quantum register has the expected value.</span></span>

```qsharp
operation AssertProbInt (stateIndex : Int, expected : Double, qubits : Microsoft.Quantum.Arithmetic.LittleEndian, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="54205-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="54205-106">Description</span></span>

<span data-ttu-id="54205-107">Dato un $n $-qubit quantum state $ \ket{\psi} = \sum ^ {2 ^ n-1} _ {j = 0} \ alpha_j \ket{j} $, asserisce che la probabilità $ | \ alpha_j | ^ 2 $ dello stato $ \ket{j} $ indicizzato da $j $ presenta il valore previsto.</span><span class="sxs-lookup"><span data-stu-id="54205-107">Given an $n$-qubit quantum state $\ket{\psi}=\sum^{2^n-1}_{j=0}\alpha_j \ket{j}$, asserts that the probability $|\alpha_j|^2$ of the state $\ket{j}$ indexed by $j$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="54205-108">Input</span><span class="sxs-lookup"><span data-stu-id="54205-108">Input</span></span>

### <a name="stateindex--int"></a><span data-ttu-id="54205-109">stateIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="54205-109">stateIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="54205-110">Indice $j $ dello stato $ \ket{j} $ rappresentato da un `LittleEndian` registro.</span><span class="sxs-lookup"><span data-stu-id="54205-110">The index $j$ of the state $\ket{j}$ represented by a `LittleEndian` register.</span></span>


### <a name="expected--double"></a><span data-ttu-id="54205-111">previsto: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="54205-111">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="54205-112">Il valore previsto di $ | \ alpha_j | ^ 2 $.</span><span class="sxs-lookup"><span data-stu-id="54205-112">The expected value of $|\alpha_j|^2$.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="54205-113">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="54205-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="54205-114">Registro qubit che archivia $ \ket{\psi} $ in formato little-endian.</span><span class="sxs-lookup"><span data-stu-id="54205-114">The qubit register that stores $\ket{\psi}$ in little-endian format.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="54205-115">tolleranza: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="54205-115">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="54205-116">Tolleranza assoluta sulla differenza tra il valore effettivo e quello previsto.</span><span class="sxs-lookup"><span data-stu-id="54205-116">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="54205-117">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="54205-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

