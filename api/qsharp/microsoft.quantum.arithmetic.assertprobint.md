---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: Operazione AssertProbInt
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: 85ff04bbad9dc2ed0f803db65508fdfbb0d22c56
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843413"
---
# <a name="assertprobint-operation"></a><span data-ttu-id="ffd5d-102">Operazione AssertProbInt</span><span class="sxs-lookup"><span data-stu-id="ffd5d-102">AssertProbInt operation</span></span>

<span data-ttu-id="ffd5d-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ffd5d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ffd5d-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ffd5d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ffd5d-105">Asserisce che la probabilità di uno stato specifico di un registro Quantum presenta il valore previsto.</span><span class="sxs-lookup"><span data-stu-id="ffd5d-105">Asserts that the probability of a specific state of a quantum register has the expected value.</span></span>

```qsharp
operation AssertProbInt (stateIndex : Int, expected : Double, qubits : Microsoft.Quantum.Arithmetic.LittleEndian, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="ffd5d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ffd5d-106">Description</span></span>

<span data-ttu-id="ffd5d-107">Dato un $n $-qubit quantum state $ \ket{\psi} = \sum ^ {2 ^ n-1} _ {j = 0} \ alpha_j \ket{j} $, asserisce che la probabilità $ | \ alpha_j | ^ 2 $ dello stato $ \ket{j} $ indicizzato da $j $ presenta il valore previsto.</span><span class="sxs-lookup"><span data-stu-id="ffd5d-107">Given an $n$-qubit quantum state $\ket{\psi}=\sum^{2^n-1}_{j=0}\alpha_j \ket{j}$, asserts that the probability $|\alpha_j|^2$ of the state $\ket{j}$ indexed by $j$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="ffd5d-108">Input</span><span class="sxs-lookup"><span data-stu-id="ffd5d-108">Input</span></span>

### <a name="stateindex--int"></a><span data-ttu-id="ffd5d-109">stateIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ffd5d-109">stateIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ffd5d-110">Indice $j $ dello stato $ \ket{j} $ rappresentato da un `LittleEndian` registro.</span><span class="sxs-lookup"><span data-stu-id="ffd5d-110">The index $j$ of the state $\ket{j}$ represented by a `LittleEndian` register.</span></span>


### <a name="expected--double"></a><span data-ttu-id="ffd5d-111">previsto: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ffd5d-111">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ffd5d-112">Il valore previsto di $ | \ alpha_j | ^ 2 $.</span><span class="sxs-lookup"><span data-stu-id="ffd5d-112">The expected value of $|\alpha_j|^2$.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="ffd5d-113">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ffd5d-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ffd5d-114">Registro qubit che archivia $ \ket{\psi} $ in formato little-endian.</span><span class="sxs-lookup"><span data-stu-id="ffd5d-114">The qubit register that stores $\ket{\psi}$ in little-endian format.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="ffd5d-115">tolleranza: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ffd5d-115">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ffd5d-116">Tolleranza assoluta sulla differenza tra il valore effettivo e quello previsto.</span><span class="sxs-lookup"><span data-stu-id="ffd5d-116">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ffd5d-117">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ffd5d-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="ffd5d-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="ffd5d-118">Example</span></span>

<span data-ttu-id="ffd5d-119">Si supponga che il `qubits` registro codifichi uno stato quantum 3-qubit $ \ket{\psi} = \ sqrt {1/8} \ KET {0} + \ sqrt {7/8} \ KET {6} $ in formato little-endian.</span><span class="sxs-lookup"><span data-stu-id="ffd5d-119">Suppose that the `qubits` register encodes a 3-qubit quantum state $\ket{\psi}=\sqrt{1/8}\ket{0}+\sqrt{7/8}\ket{6}$ in little-endian format.</span></span>
<span data-ttu-id="ffd5d-120">Ciò significa che il numero indica $ \ket {0} \equiv\ket {0} \ket {0} \ket {0} $ e $ \ket {6} \equiv\ket \ket \ket {0} {1} {1} $.</span><span class="sxs-lookup"><span data-stu-id="ffd5d-120">This means that the number states $\ket{0}\equiv\ket{0}\ket{0}\ket{0}$ and $\ket{6}\equiv\ket{0}\ket{1}\ket{1}$.</span></span> <span data-ttu-id="ffd5d-121">Quindi, le asserzioni seguenti hanno esito positivo:</span><span class="sxs-lookup"><span data-stu-id="ffd5d-121">Then the following asserts succeed:</span></span>

```qsharp
AssertProbInt(0, 0.125, qubits, 10e-10);
AssertProbInt(6, 0.875, qubits, 10e-10);
```