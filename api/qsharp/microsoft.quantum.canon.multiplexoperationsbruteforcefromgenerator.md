---
uid: Microsoft.Quantum.Canon.MultiplexOperationsBruteForceFromGenerator
title: Operazione MultiplexOperationsBruteForceFromGenerator
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsBruteForceFromGenerator
qsharp.summary: >-
  Applies multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 395102c7ffffa81d1a9b6cbf29c9cc22fae6057e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852512"
---
# <a name="multiplexoperationsbruteforcefromgenerator-operation"></a><span data-ttu-id="00dfb-102">Operazione MultiplexOperationsBruteForceFromGenerator</span><span class="sxs-lookup"><span data-stu-id="00dfb-102">MultiplexOperationsBruteForceFromGenerator operation</span></span>

<span data-ttu-id="00dfb-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="00dfb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="00dfb-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="00dfb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="00dfb-105">Applica l'operazione unitaria controllata da moltiplicata $U $ che applica un $V unitario _j $ se controllato da n-qubit numero stato $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="00dfb-105">Applies multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="00dfb-106">$U = \sum ^ {N-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.</span><span class="sxs-lookup"><span data-stu-id="00dfb-106">$U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
operation MultiplexOperationsBruteForceFromGenerator<'T> (unitaryGenerator : (Int, (Int -> ('T => Unit is Adj + Ctl))), index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="00dfb-107">Input</span><span class="sxs-lookup"><span data-stu-id="00dfb-107">Input</span></span>

### <a name="unitarygenerator--intint---t--unit--is-adj--ctl"></a><span data-ttu-id="00dfb-108">unitaryGenerator: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> non => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL)</span><span class="sxs-lookup"><span data-stu-id="00dfb-108">unitaryGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl)</span></span>

<span data-ttu-id="00dfb-109">Tupla in cui il primo elemento `Int` è il numero di unitaries $N $ e il secondo elemento `(Int -> ('T => () is Adj + Ctl))` è una funzione che accetta un intero $j $ in $ [0, N-1] $ e restituisce l'operazione unitaria $V _J $.</span><span class="sxs-lookup"><span data-stu-id="00dfb-109">A tuple where the first element `Int` is the number of unitaries $N$, and the second element `(Int -> ('T => () is Adj + Ctl))` is a function that takes an integer $j$ in $[0,N-1]$ and outputs the unitary operation $V_j$.</span></span>


### <a name="index--littleendian"></a><span data-ttu-id="00dfb-110">Indice: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="00dfb-110">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="00dfb-111">$n il registro di controllo $-qubit che codifica gli Stati numerici $ \ket{j} $ in formato little-endian.</span><span class="sxs-lookup"><span data-stu-id="00dfb-111">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--t"></a><span data-ttu-id="00dfb-112">destinazione:' t</span><span class="sxs-lookup"><span data-stu-id="00dfb-112">target : 'T</span></span>

<span data-ttu-id="00dfb-113">Registro qubit generico su cui $V _j $ agisce.</span><span class="sxs-lookup"><span data-stu-id="00dfb-113">Generic qubit register that $V_j$ acts on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="00dfb-114">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="00dfb-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="00dfb-115">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="00dfb-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="00dfb-116">T</span><span class="sxs-lookup"><span data-stu-id="00dfb-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="00dfb-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="00dfb-117">Remarks</span></span>

<span data-ttu-id="00dfb-118">`coefficients` verranno riempiti con gli elementi Identity se sono specificati meno di $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="00dfb-118">`coefficients` will be padded with identity elements if fewer than $2^n$ are specified.</span></span> <span data-ttu-id="00dfb-119">Questa versione viene implementata direttamente eseguendo il ciclo attraverso gli operatori unitari controllati da n.</span><span class="sxs-lookup"><span data-stu-id="00dfb-119">This version is implemented directly by looping through n-controlled unitary operators.</span></span>