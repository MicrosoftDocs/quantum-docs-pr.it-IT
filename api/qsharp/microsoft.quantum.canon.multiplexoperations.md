---
uid: Microsoft.Quantum.Canon.MultiplexOperations
title: Operazione MultiplexOperations
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperations
qsharp.summary: >-
  Applies an array of operations controlled by an array of number states.

  That is, applies Multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by $n$-qubit number state $\ket{j}$.

  $U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 267c9c2858090ebe024fd387938e8bd2f8c76867
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715837"
---
# <a name="multiplexoperations-operation"></a><span data-ttu-id="3b491-102">Operazione MultiplexOperations</span><span class="sxs-lookup"><span data-stu-id="3b491-102">MultiplexOperations operation</span></span>

<span data-ttu-id="3b491-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3b491-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3b491-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3b491-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3b491-105">Applica una matrice di operazioni controllate da una matrice di stati numerici.</span><span class="sxs-lookup"><span data-stu-id="3b491-105">Applies an array of operations controlled by an array of number states.</span></span>

<span data-ttu-id="3b491-106">Ovvero applica un'operazione unitaria controllata da moltiplicazione $U $ che applica una $V unitaria _j $ se controllata dal $n $-qubit numero stato $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="3b491-106">That is, applies Multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by $n$-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="3b491-107">$U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.</span><span class="sxs-lookup"><span data-stu-id="3b491-107">$U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
operation MultiplexOperations<'T> (unitaries : ('T => Unit is Adj + Ctl)[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="3b491-108">Input</span><span class="sxs-lookup"><span data-stu-id="3b491-108">Input</span></span>

### <a name="unitaries--t--unit-adj--ctl"></a><span data-ttu-id="3b491-109">unitaries:' t => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL []</span><span class="sxs-lookup"><span data-stu-id="3b491-109">unitaries : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl[]</span></span>

<span data-ttu-id="3b491-110">Matrice di un massimo di $2 ^ n $ operazioni unitarie.</span><span class="sxs-lookup"><span data-stu-id="3b491-110">Array of up to $2^n$ unitary operations.</span></span> <span data-ttu-id="3b491-111">L'operazione $j $ th viene indicizzata in base al numero di stato $ \ket{j} $ codificato in formato little-endian.</span><span class="sxs-lookup"><span data-stu-id="3b491-111">The $j$th operation is indexed by the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="index--littleendian"></a><span data-ttu-id="3b491-112">Indice: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3b491-112">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="3b491-113">$n il registro di controllo $-qubit che codifica gli Stati numerici $ \ket{j} $ in formato little-endian.</span><span class="sxs-lookup"><span data-stu-id="3b491-113">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--t"></a><span data-ttu-id="3b491-114">destinazione:' t</span><span class="sxs-lookup"><span data-stu-id="3b491-114">target : 'T</span></span>

<span data-ttu-id="3b491-115">Registro qubit generico su cui $V _j $ agisce.</span><span class="sxs-lookup"><span data-stu-id="3b491-115">Generic qubit register that $V_j$ acts on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3b491-116">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3b491-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3b491-117">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="3b491-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3b491-118">T</span><span class="sxs-lookup"><span data-stu-id="3b491-118">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="3b491-119">Commenti</span><span class="sxs-lookup"><span data-stu-id="3b491-119">Remarks</span></span>

<span data-ttu-id="3b491-120">`coefficients` verranno riempiti con gli elementi Identity se sono specificati meno di $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="3b491-120">`coefficients` will be padded with identity elements if fewer than $2^n$ are specified.</span></span> <span data-ttu-id="3b491-121">Questa implementazione USA qubits ausiliari $n-$1.</span><span class="sxs-lookup"><span data-stu-id="3b491-121">This implementation uses $n - 1$ auxiliary qubits.</span></span>

## <a name="references"></a><span data-ttu-id="3b491-122">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="3b491-122">References</span></span>

- <span data-ttu-id="3b491-123">Verso la prima simulazione quantistica con aumento della velocità di Quantum Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan su https://arxiv.org/abs/1711.10980</span><span class="sxs-lookup"><span data-stu-id="3b491-123">Toward the first quantum simulation with quantum speedup Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan Su https://arxiv.org/abs/1711.10980</span></span>