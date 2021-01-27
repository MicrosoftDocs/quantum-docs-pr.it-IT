---
uid: Microsoft.Quantum.Canon.MultiplexOperations
title: Operazione MultiplexOperations
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperations
qsharp.summary: >-
  Applies an array of operations controlled by an array of number states.

  That is, applies Multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by $n$-qubit number state $\ket{j}$.

  $U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 1cf483bb0d3b7cc43d271b65a2363fab95ff0f3b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852537"
---
# <a name="multiplexoperations-operation"></a><span data-ttu-id="41753-102">Operazione MultiplexOperations</span><span class="sxs-lookup"><span data-stu-id="41753-102">MultiplexOperations operation</span></span>

<span data-ttu-id="41753-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="41753-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="41753-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="41753-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="41753-105">Applica una matrice di operazioni controllate da una matrice di stati numerici.</span><span class="sxs-lookup"><span data-stu-id="41753-105">Applies an array of operations controlled by an array of number states.</span></span>

<span data-ttu-id="41753-106">Ovvero applica un'operazione unitaria controllata da moltiplicazione $U $ che applica una $V unitaria _j $ se controllata dal $n $-qubit numero stato $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="41753-106">That is, applies Multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by $n$-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="41753-107">$U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.</span><span class="sxs-lookup"><span data-stu-id="41753-107">$U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
operation MultiplexOperations<'T> (unitaries : ('T => Unit is Adj + Ctl)[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="41753-108">Input</span><span class="sxs-lookup"><span data-stu-id="41753-108">Input</span></span>

### <a name="unitaries--t--unit--is-adj--ctl"></a><span data-ttu-id="41753-109">unitaries:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL []</span><span class="sxs-lookup"><span data-stu-id="41753-109">unitaries : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>

<span data-ttu-id="41753-110">Matrice di un massimo di $2 ^ n $ operazioni unitarie.</span><span class="sxs-lookup"><span data-stu-id="41753-110">Array of up to $2^n$ unitary operations.</span></span> <span data-ttu-id="41753-111">L'operazione $j $ th viene indicizzata in base al numero di stato $ \ket{j} $ codificato in formato little-endian.</span><span class="sxs-lookup"><span data-stu-id="41753-111">The $j$th operation is indexed by the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="index--littleendian"></a><span data-ttu-id="41753-112">Indice: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="41753-112">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="41753-113">$n il registro di controllo $-qubit che codifica gli Stati numerici $ \ket{j} $ in formato little-endian.</span><span class="sxs-lookup"><span data-stu-id="41753-113">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--t"></a><span data-ttu-id="41753-114">destinazione:' t</span><span class="sxs-lookup"><span data-stu-id="41753-114">target : 'T</span></span>

<span data-ttu-id="41753-115">Registro qubit generico su cui $V _j $ agisce.</span><span class="sxs-lookup"><span data-stu-id="41753-115">Generic qubit register that $V_j$ acts on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="41753-116">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="41753-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="41753-117">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="41753-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="41753-118">T</span><span class="sxs-lookup"><span data-stu-id="41753-118">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="41753-119">Commenti</span><span class="sxs-lookup"><span data-stu-id="41753-119">Remarks</span></span>

<span data-ttu-id="41753-120">`coefficients` verranno riempiti con gli elementi Identity se sono specificati meno di $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="41753-120">`coefficients` will be padded with identity elements if fewer than $2^n$ are specified.</span></span> <span data-ttu-id="41753-121">Questa implementazione USA qubits ausiliari $n-$1.</span><span class="sxs-lookup"><span data-stu-id="41753-121">This implementation uses $n - 1$ auxiliary qubits.</span></span>

## <a name="references"></a><span data-ttu-id="41753-122">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="41753-122">References</span></span>

- <span data-ttu-id="41753-123">Verso la prima simulazione quantistica con aumento della velocità di Quantum Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan su https://arxiv.org/abs/1711.10980</span><span class="sxs-lookup"><span data-stu-id="41753-123">Toward the first quantum simulation with quantum speedup Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan Su https://arxiv.org/abs/1711.10980</span></span>