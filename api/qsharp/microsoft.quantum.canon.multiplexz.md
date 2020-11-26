---
uid: Microsoft.Quantum.Canon.MultiplexZ
title: Operazione MultiplexZ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexZ
qsharp.summary: Applies a Pauli Z rotation conditioned on an array of qubits.
ms.openlocfilehash: 364d23a0e57a2510f069b6db66b085368f20162e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206069"
---
# <a name="multiplexz-operation"></a><span data-ttu-id="7a178-102">Operazione MultiplexZ</span><span class="sxs-lookup"><span data-stu-id="7a178-102">MultiplexZ operation</span></span>

<span data-ttu-id="7a178-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7a178-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7a178-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7a178-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7a178-105">Applica una rotazione di Pauli Z condizionata su una matrice di qubits.</span><span class="sxs-lookup"><span data-stu-id="7a178-105">Applies a Pauli Z rotation conditioned on an array of qubits.</span></span>

```qsharp
operation MultiplexZ (coefficients : Double[], control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="7a178-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7a178-106">Description</span></span>

<span data-ttu-id="7a178-107">Questa operazione applica l'operazione unitaria controllata di moltiplicazione che esegue rotazioni in base all'angolo $ \ theta_j $ about Single-qubit Pauli operator $Z $ quando viene controllata dallo $n $-qubit numero stato $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="7a178-107">This applies the multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $Z$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="7a178-108">In particolare, questa operazione può essere rappresentata dall'unità</span><span class="sxs-lookup"><span data-stu-id="7a178-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="7a178-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i Z \ theta_j}.</span><span class="sxs-lookup"><span data-stu-id="7a178-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0} \ket{j}\bra{j} \otimes e^{i Z \theta_j}.</span></span>
<span data-ttu-id="7a178-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="7a178-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="7a178-111">Input</span><span class="sxs-lookup"><span data-stu-id="7a178-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="7a178-112">coefficienti: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="7a178-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="7a178-113">Matrice di un massimo di $2 ^ n $ coefficienti $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="7a178-113">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="7a178-114">Il coefficiente $j $ TH indicizza lo stato del numero $ \ket{j} $ codificato in formato little-endian.</span><span class="sxs-lookup"><span data-stu-id="7a178-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="7a178-115">controllo: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7a178-115">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="7a178-116">$n il registro di controllo $-qubit che codifica gli Stati numerici $ \ket{j} $ in formato little-endian.</span><span class="sxs-lookup"><span data-stu-id="7a178-116">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="7a178-117">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7a178-117">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7a178-118">Singolo registro qubit ruotato da $e ^ {i P \ theta_j} $.</span><span class="sxs-lookup"><span data-stu-id="7a178-118">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7a178-119">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7a178-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="7a178-120">Commenti</span><span class="sxs-lookup"><span data-stu-id="7a178-120">Remarks</span></span>

<span data-ttu-id="7a178-121">`coefficients` verrà riempito con gli elementi $ \ theta_j = $0,0 se sono specificati meno di $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="7a178-121">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="7a178-122">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="7a178-122">References</span></span>

- <span data-ttu-id="7a178-123">Sintesi dei circuiti logici Quantum Simone V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="7a178-123">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="7a178-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a178-124">See Also</span></span>

- [<span data-ttu-id="7a178-125">Microsoft. Quantum. Canon. ApproximatelyMultiplexZ</span><span class="sxs-lookup"><span data-stu-id="7a178-125">Microsoft.Quantum.Canon.ApproximatelyMultiplexZ</span></span>](xref:Microsoft.Quantum.Canon.ApproximatelyMultiplexZ)