---
uid: Microsoft.Quantum.Canon.ApproximatelyMultiplexZ
title: Operazione ApproximatelyMultiplexZ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyMultiplexZ
qsharp.summary: Applies a Pauli Z rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: 5e254c2b2d6cbf29b428f4d55aef0e61356e3480
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217102"
---
# <a name="approximatelymultiplexz-operation"></a><span data-ttu-id="c90f3-102">Operazione ApproximatelyMultiplexZ</span><span class="sxs-lookup"><span data-stu-id="c90f3-102">ApproximatelyMultiplexZ operation</span></span>

<span data-ttu-id="c90f3-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c90f3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c90f3-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c90f3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c90f3-105">Applica una rotazione di Pauli Z condizionata su una matrice di qubits, troncando gli angoli di rotazione piccoli in base a una determinata tolleranza.</span><span class="sxs-lookup"><span data-stu-id="c90f3-105">Applies a Pauli Z rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.</span></span>

```qsharp
operation ApproximatelyMultiplexZ (tolerance : Double, coefficients : Double[], control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="c90f3-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c90f3-106">Description</span></span>

<span data-ttu-id="c90f3-107">Questa operazione applica l'operazione unitaria controllata di moltiplicazione che esegue rotazioni in base all'angolo $ \ theta_j $ about Single-qubit Pauli operator $Z $ quando viene controllata dallo $n $-qubit numero stato $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="c90f3-107">This applies the multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $Z$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="c90f3-108">In particolare, questa operazione può essere rappresentata dall'unità</span><span class="sxs-lookup"><span data-stu-id="c90f3-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="c90f3-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i Z \ theta_j}.</span><span class="sxs-lookup"><span data-stu-id="c90f3-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0} \ket{j}\bra{j} \otimes e^{i Z \theta_j}.</span></span>
<span data-ttu-id="c90f3-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="c90f3-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="c90f3-111">Input</span><span class="sxs-lookup"><span data-stu-id="c90f3-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="c90f3-112">tolleranza: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c90f3-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c90f3-113">Tolleranza sotto la quale vengono troncati i coefficienti di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="c90f3-113">A tolerance below which small coefficients are truncated.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="c90f3-114">coefficienti: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="c90f3-114">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="c90f3-115">Matrice di un massimo di $2 ^ n $ coefficienti $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="c90f3-115">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="c90f3-116">Il coefficiente $j $ TH indicizza lo stato del numero $ \ket{j} $ codificato in formato little-endian.</span><span class="sxs-lookup"><span data-stu-id="c90f3-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="c90f3-117">controllo: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c90f3-117">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c90f3-118">$n il registro di controllo $-qubit che codifica gli Stati numerici $ \ket{j} $ in formato little-endian.</span><span class="sxs-lookup"><span data-stu-id="c90f3-118">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="c90f3-119">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c90f3-119">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c90f3-120">Singolo registro qubit ruotato da $e ^ {i P \ theta_j} $.</span><span class="sxs-lookup"><span data-stu-id="c90f3-120">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c90f3-121">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c90f3-121">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c90f3-122">Commenti</span><span class="sxs-lookup"><span data-stu-id="c90f3-122">Remarks</span></span>

<span data-ttu-id="c90f3-123">`coefficients` verrà riempito con gli elementi $ \ theta_j = $0,0 se sono specificati meno di $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="c90f3-123">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="c90f3-124">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="c90f3-124">References</span></span>

- <span data-ttu-id="c90f3-125">Sintesi dei circuiti logici Quantum Simone V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="c90f3-125">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="c90f3-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c90f3-126">See Also</span></span>

- [<span data-ttu-id="c90f3-127">Microsoft. Quantum. Canon. MultiplexZ</span><span class="sxs-lookup"><span data-stu-id="c90f3-127">Microsoft.Quantum.Canon.MultiplexZ</span></span>](xref:Microsoft.Quantum.Canon.MultiplexZ)