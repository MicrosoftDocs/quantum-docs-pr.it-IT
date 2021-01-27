---
uid: Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator
title: Operazione MultiplexOperationsFromGenerator
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsFromGenerator
qsharp.summary: >-
  Applies a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 59afa9d9a34fe74206118680940d243ed8b2496e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852505"
---
# <a name="multiplexoperationsfromgenerator-operation"></a><span data-ttu-id="947c2-102">Operazione MultiplexOperationsFromGenerator</span><span class="sxs-lookup"><span data-stu-id="947c2-102">MultiplexOperationsFromGenerator operation</span></span>

<span data-ttu-id="947c2-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="947c2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="947c2-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="947c2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="947c2-105">Applica un'operazione unitaria controllata da Multiply $U $ che applica un $V unitario _j $ se controllato da n-qubit numero stato $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="947c2-105">Applies a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="947c2-106">$U = \sum ^ {N-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.</span><span class="sxs-lookup"><span data-stu-id="947c2-106">$U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
operation MultiplexOperationsFromGenerator<'T> (unitaryGenerator : (Int, (Int -> ('T => Unit is Adj + Ctl))), index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="947c2-107">Input</span><span class="sxs-lookup"><span data-stu-id="947c2-107">Input</span></span>

### <a name="unitarygenerator--intint---t--unit--is-adj--ctl"></a><span data-ttu-id="947c2-108">unitaryGenerator: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> non => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL)</span><span class="sxs-lookup"><span data-stu-id="947c2-108">unitaryGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl)</span></span>

<span data-ttu-id="947c2-109">Tupla in cui il primo elemento `Int` è il numero di unitaries $N $ e il secondo elemento `(Int -> ('T => () is Adj + Ctl))` è una funzione che accetta un intero $j $ in $ [0, N-1] $ e restituisce l'operazione unitaria $V _J $.</span><span class="sxs-lookup"><span data-stu-id="947c2-109">A tuple where the first element `Int` is the number of unitaries $N$, and the second element `(Int -> ('T => () is Adj + Ctl))` is a function that takes an integer $j$ in $[0,N-1]$ and outputs the unitary operation $V_j$.</span></span>


### <a name="index--littleendian"></a><span data-ttu-id="947c2-110">Indice: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="947c2-110">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="947c2-111">$n il registro di controllo $-qubit che codifica gli Stati numerici $ \ket{j} $ in formato little-endian.</span><span class="sxs-lookup"><span data-stu-id="947c2-111">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--t"></a><span data-ttu-id="947c2-112">destinazione:' t</span><span class="sxs-lookup"><span data-stu-id="947c2-112">target : 'T</span></span>

<span data-ttu-id="947c2-113">Registro qubit generico su cui $V _j $ agisce.</span><span class="sxs-lookup"><span data-stu-id="947c2-113">Generic qubit register that $V_j$ acts on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="947c2-114">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="947c2-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="947c2-115">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="947c2-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="947c2-116">T</span><span class="sxs-lookup"><span data-stu-id="947c2-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="947c2-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="947c2-117">Remarks</span></span>

<span data-ttu-id="947c2-118">`coefficients` verranno riempiti con gli elementi Identity se sono specificati meno di $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="947c2-118">`coefficients` will be padded with identity elements if fewer than $2^n$ are specified.</span></span> <span data-ttu-id="947c2-119">Questa implementazione USA qubits ausiliari $n-$1.</span><span class="sxs-lookup"><span data-stu-id="947c2-119">This implementation uses $n-1$ auxiliary qubits.</span></span>

## <a name="references"></a><span data-ttu-id="947c2-120">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="947c2-120">References</span></span>

- [<span data-ttu-id="947c2-121">*Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan su*, arXiv: 1711.10980</span><span class="sxs-lookup"><span data-stu-id="947c2-121"> *Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan Su*, arXiv:1711.10980</span></span>](https://arxiv.org/abs/1711.10980)