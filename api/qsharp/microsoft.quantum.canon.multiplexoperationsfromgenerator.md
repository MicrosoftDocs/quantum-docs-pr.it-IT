---
uid: Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator
title: Operazione MultiplexOperationsFromGenerator
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsFromGenerator
qsharp.summary: >-
  Applies a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 9fbbd9268d4a6b9f3d5fd203969f4bbeebe81b68
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205950"
---
# <a name="multiplexoperationsfromgenerator-operation"></a><span data-ttu-id="f2b2b-102">Operazione MultiplexOperationsFromGenerator</span><span class="sxs-lookup"><span data-stu-id="f2b2b-102">MultiplexOperationsFromGenerator operation</span></span>

<span data-ttu-id="f2b2b-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f2b2b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f2b2b-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f2b2b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f2b2b-105">Applica un'operazione unitaria controllata da Multiply $U $ che applica un $V unitario _j $ se controllato da n-qubit numero stato $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-105">Applies a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="f2b2b-106">$U = \sum ^ {N-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-106">$U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
operation MultiplexOperationsFromGenerator<'T> (unitaryGenerator : (Int, (Int -> ('T => Unit is Adj + Ctl))), index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f2b2b-107">Input</span><span class="sxs-lookup"><span data-stu-id="f2b2b-107">Input</span></span>

### <a name="unitarygenerator--intint---t--unit--is-adj--ctl"></a><span data-ttu-id="f2b2b-108">unitaryGenerator: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> non => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL)</span><span class="sxs-lookup"><span data-stu-id="f2b2b-108">unitaryGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl)</span></span>

<span data-ttu-id="f2b2b-109">Tupla in cui il primo elemento `Int` è il numero di unitaries $N $ e il secondo elemento `(Int -> ('T => () is Adj + Ctl))` è una funzione che accetta un intero $j $ in $ [0, N-1] $ e restituisce l'operazione unitaria $V _J $.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-109">A tuple where the first element `Int` is the number of unitaries $N$, and the second element `(Int -> ('T => () is Adj + Ctl))` is a function that takes an integer $j$ in $[0,N-1]$ and outputs the unitary operation $V_j$.</span></span>


### <a name="index--littleendian"></a><span data-ttu-id="f2b2b-110">Indice: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f2b2b-110">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f2b2b-111">$n il registro di controllo $-qubit che codifica gli Stati numerici $ \ket{j} $ in formato little-endian.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-111">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--t"></a><span data-ttu-id="f2b2b-112">destinazione:' t</span><span class="sxs-lookup"><span data-stu-id="f2b2b-112">target : 'T</span></span>

<span data-ttu-id="f2b2b-113">Registro qubit generico su cui $V _j $ agisce.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-113">Generic qubit register that $V_j$ acts on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f2b2b-114">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f2b2b-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f2b2b-115">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="f2b2b-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f2b2b-116">T</span><span class="sxs-lookup"><span data-stu-id="f2b2b-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="f2b2b-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="f2b2b-117">Remarks</span></span>

<span data-ttu-id="f2b2b-118">`coefficients` verranno riempiti con gli elementi Identity se sono specificati meno di $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-118">`coefficients` will be padded with identity elements if fewer than $2^n$ are specified.</span></span> <span data-ttu-id="f2b2b-119">Questa implementazione USA qubits ausiliari $n-$1.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-119">This implementation uses $n-1$ auxiliary qubits.</span></span>

## <a name="references"></a><span data-ttu-id="f2b2b-120">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="f2b2b-120">References</span></span>

- [<span data-ttu-id="f2b2b-121">*Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan su*, arXiv: 1711.10980</span><span class="sxs-lookup"><span data-stu-id="f2b2b-121"> *Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan Su*, arXiv:1711.10980</span></span>](https://arxiv.org/abs/1711.10980)