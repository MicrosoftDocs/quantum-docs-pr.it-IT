---
uid: Microsoft.Quantum.Canon.ApproximatelyMultiplexPauli
title: Operazione ApproximatelyMultiplexPauli
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyMultiplexPauli
qsharp.summary: Applies a Pauli rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: c91937d9e82a2a1514d81529adb35a5f804a0e13
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716817"
---
# <a name="approximatelymultiplexpauli-operation"></a><span data-ttu-id="fed63-102">Operazione ApproximatelyMultiplexPauli</span><span class="sxs-lookup"><span data-stu-id="fed63-102">ApproximatelyMultiplexPauli operation</span></span>

<span data-ttu-id="fed63-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fed63-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fed63-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fed63-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fed63-105">Applica una rotazione di Pauli con una matrice di qubits, troncando gli angoli di rotazione piccoli in base a una determinata tolleranza.</span><span class="sxs-lookup"><span data-stu-id="fed63-105">Applies a Pauli rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.</span></span>

```qsharp
operation ApproximatelyMultiplexPauli (tolerance : Double, coefficients : Double[], pauli : Pauli, control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="fed63-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fed63-106">Description</span></span>

<span data-ttu-id="fed63-107">Si applica un'operazione unitaria controllata che esegue rotazioni in base all'angolo $ \ theta_j $ about Single-qubit Pauli operator $P $ quando viene controllata dal $n $-qubit numero stato $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="fed63-107">This applies a multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $P$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="fed63-108">In particolare, l'azione di questa operazione è rappresentata dall'unità</span><span class="sxs-lookup"><span data-stu-id="fed63-108">In particular, the action of this operation is represented by the unitary</span></span>

<span data-ttu-id="fed63-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i P \ theta_j}.</span><span class="sxs-lookup"><span data-stu-id="fed63-109">$$ \begin{align} U = \sum^{2^n - 1}_{j=0} \ket{j}\bra{j} \otimes e^{i P \theta_j}.</span></span>
<span data-ttu-id="fed63-110">\end{align}</span><span class="sxs-lookup"><span data-stu-id="fed63-110">\end{align}</span></span>

##

## <a name="input"></a><span data-ttu-id="fed63-111">Input</span><span class="sxs-lookup"><span data-stu-id="fed63-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="fed63-112">tolleranza: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fed63-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fed63-113">Tolleranza sotto la quale vengono troncati i coefficienti di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="fed63-113">A tolerance below which small coefficients are truncated.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="fed63-114">coefficienti: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="fed63-114">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="fed63-115">Matrice di un massimo di $2 ^ n $ coefficienti $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="fed63-115">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="fed63-116">Il coefficiente $j $ TH indicizza lo stato del numero $ \ket{j} $ codificato in formato little-endian.</span><span class="sxs-lookup"><span data-stu-id="fed63-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="pauli--pauli"></a><span data-ttu-id="fed63-117">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="fed63-117">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="fed63-118">Operatore Pauli $P $ che determina l'asse di rotazione.</span><span class="sxs-lookup"><span data-stu-id="fed63-118">Pauli operator $P$ that determines axis of rotation.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="fed63-119">controllo: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="fed63-119">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="fed63-120">$n il registro di controllo $-qubit che codifica gli Stati numerici $ \ket{j} $ in formato little-endian.</span><span class="sxs-lookup"><span data-stu-id="fed63-120">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="fed63-121">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="fed63-121">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="fed63-122">Singolo registro qubit ruotato da $e ^ {i P \ theta_j} $.</span><span class="sxs-lookup"><span data-stu-id="fed63-122">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fed63-123">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fed63-123">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="fed63-124">Commenti</span><span class="sxs-lookup"><span data-stu-id="fed63-124">Remarks</span></span>

<span data-ttu-id="fed63-125">`coefficients` verrà riempito con gli elementi $ \ theta_j = $0,0 se sono specificati meno di $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="fed63-125">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="see-also"></a><span data-ttu-id="fed63-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fed63-126">See Also</span></span>

- [<span data-ttu-id="fed63-127">Microsoft. Quantum. Canon. MultiplexPauli</span><span class="sxs-lookup"><span data-stu-id="fed63-127">Microsoft.Quantum.Canon.MultiplexPauli</span></span>](xref:Microsoft.Quantum.Canon.MultiplexPauli)