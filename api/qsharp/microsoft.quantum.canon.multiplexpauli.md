---
uid: Microsoft.Quantum.Canon.MultiplexPauli
title: Operazione MultiplexPauli
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexPauli
qsharp.summary: Applies a Pauli rotation conditioned on an array of qubits.
ms.openlocfilehash: 0714e796c1e5ad097814bcf507f49f59a844e9ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715784"
---
# <a name="multiplexpauli-operation"></a><span data-ttu-id="ff530-102">Operazione MultiplexPauli</span><span class="sxs-lookup"><span data-stu-id="ff530-102">MultiplexPauli operation</span></span>

<span data-ttu-id="ff530-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ff530-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ff530-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ff530-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ff530-105">Applica una rotazione di Pauli con una matrice di qubits.</span><span class="sxs-lookup"><span data-stu-id="ff530-105">Applies a Pauli rotation conditioned on an array of qubits.</span></span>

```qsharp
operation MultiplexPauli (coefficients : Double[], pauli : Pauli, control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="ff530-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ff530-106">Description</span></span>

<span data-ttu-id="ff530-107">Si applica un'operazione unitaria controllata che esegue rotazioni in base all'angolo $ \ theta_j $ about Single-qubit Pauli operator $P $ quando viene controllata dal $n $-qubit numero stato $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="ff530-107">This applies a multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $P$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="ff530-108">In particolare, l'azione di questa operazione è rappresentata dall'unità</span><span class="sxs-lookup"><span data-stu-id="ff530-108">In particular, the action of this operation is represented by the unitary</span></span>

<span data-ttu-id="ff530-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i P \ theta_j}.</span><span class="sxs-lookup"><span data-stu-id="ff530-109">$$ \begin{align} U = \sum^{2^n - 1}_{j=0} \ket{j}\bra{j} \otimes e^{i P \theta_j}.</span></span>
<span data-ttu-id="ff530-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="ff530-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="ff530-111">Input</span><span class="sxs-lookup"><span data-stu-id="ff530-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="ff530-112">coefficienti: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="ff530-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="ff530-113">Matrice di un massimo di $2 ^ n $ coefficienti $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="ff530-113">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="ff530-114">Il coefficiente $j $ TH indicizza lo stato del numero $ \ket{j} $ codificato in formato little-endian.</span><span class="sxs-lookup"><span data-stu-id="ff530-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="pauli--pauli"></a><span data-ttu-id="ff530-115">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="ff530-115">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="ff530-116">Operatore Pauli $P $ che determina l'asse di rotazione.</span><span class="sxs-lookup"><span data-stu-id="ff530-116">Pauli operator $P$ that determines axis of rotation.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="ff530-117">controllo: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ff530-117">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ff530-118">$n il registro di controllo $-qubit che codifica gli Stati numerici $ \ket{j} $ in formato little-endian.</span><span class="sxs-lookup"><span data-stu-id="ff530-118">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="ff530-119">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ff530-119">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ff530-120">Singolo registro qubit ruotato da $e ^ {i P \ theta_j} $.</span><span class="sxs-lookup"><span data-stu-id="ff530-120">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ff530-121">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ff530-121">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ff530-122">Commenti</span><span class="sxs-lookup"><span data-stu-id="ff530-122">Remarks</span></span>

<span data-ttu-id="ff530-123">`coefficients` verrà riempito con gli elementi $ \ theta_j = $0,0 se sono specificati meno di $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="ff530-123">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="see-also"></a><span data-ttu-id="ff530-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff530-124">See Also</span></span>

- [<span data-ttu-id="ff530-125">Microsoft. Quantum. Canon. ApproximatelyMultiplexPauli</span><span class="sxs-lookup"><span data-stu-id="ff530-125">Microsoft.Quantum.Canon.ApproximatelyMultiplexPauli</span></span>](xref:Microsoft.Quantum.Canon.ApproximatelyMultiplexPauli)