---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace
title: Operazione AssertOperationsEqualInPlace
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlace
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).

  This assertion uses $n$ qubits and requires multiple calls of the operations being compared.
ms.openlocfilehash: 407a139da816281346eb06849f81e91b83202653
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712970"
---
# <a name="assertoperationsequalinplace-operation"></a><span data-ttu-id="e24e9-102">Operazione AssertOperationsEqualInPlace</span><span class="sxs-lookup"><span data-stu-id="e24e9-102">AssertOperationsEqualInPlace operation</span></span>

<span data-ttu-id="e24e9-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="e24e9-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="e24e9-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e24e9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e24e9-105">Date due operazioni, asserisce che agiscono in modo identico per tutti gli Stati di input.</span><span class="sxs-lookup"><span data-stu-id="e24e9-105">Given two operations, asserts that they act identically for all input states.</span></span>

<span data-ttu-id="e24e9-106">Questa asserzione viene implementata controllando l'azione delle operazioni su tutti gli Stati nel formato $V _0 \otimes... \otimes V_ {n-1} $, dove $V _k $ è uno degli Stati $ \ket {0} $, $ \ket {1} $, $ \ket{+} $ e $ \ket{i} $ (+ 1 autostato dell'operatore Pauli Y).</span><span class="sxs-lookup"><span data-stu-id="e24e9-106">This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).</span></span>

<span data-ttu-id="e24e9-107">Questa asserzione USA $n $ qubits e richiede il confronto di più chiamate delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="e24e9-107">This assertion uses $n$ qubits and requires multiple calls of the operations being compared.</span></span>

```qsharp
operation AssertOperationsEqualInPlace (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="e24e9-108">Input</span><span class="sxs-lookup"><span data-stu-id="e24e9-108">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="e24e9-109">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e24e9-109">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e24e9-110">Il numero di qubits $n $ `givenU` su cui operano le operazioni e `expectedU` .</span><span class="sxs-lookup"><span data-stu-id="e24e9-110">The number of qubits $n$ that the operations `givenU` and `expectedU` operate on.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="e24e9-111">dato: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="e24e9-111">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="e24e9-112">Operazione su $n $ qubits da controllare.</span><span class="sxs-lookup"><span data-stu-id="e24e9-112">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit-adj"></a><span data-ttu-id="e24e9-113">previsto: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ</span><span class="sxs-lookup"><span data-stu-id="e24e9-113">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="e24e9-114">Operazione di riferimento su $n $ qubits da `givenU` confrontare con.</span><span class="sxs-lookup"><span data-stu-id="e24e9-114">Reference operation on $n$ qubits that `givenU` is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e24e9-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e24e9-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="e24e9-116">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="e24e9-116">References</span></span>

<span data-ttu-id="e24e9-117">La base degli Stati $ \ket {0} $, $ \ket {1} $, $ \ket{+} $ e $ \ket{i} $ è la Chuang-Nielsen, descritta in [ *i. L. Chuang, M. A. Nielsen*](https://arxiv.org/abs/quant-ph/9610001).</span><span class="sxs-lookup"><span data-stu-id="e24e9-117">The basis of states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ is the Chuang-Nielsen basis, described in [ *I. L. Chuang, M. A. Nielsen* ](https://arxiv.org/abs/quant-ph/9610001).</span></span>

## <a name="see-also"></a><span data-ttu-id="e24e9-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e24e9-118">See Also</span></span>

- [<span data-ttu-id="e24e9-119">Microsoft. Quantum. Diagnostics. AssertOperationsEqualReferenced</span><span class="sxs-lookup"><span data-stu-id="e24e9-119">Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced)