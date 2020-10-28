---
uid: Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary
title: Operazione ApproximatelyApplyDiagonalUnitary
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyApplyDiagonalUnitary
qsharp.summary: Applies an array of complex phases to numeric basis states of a register of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: 9d9b1ced320b142aef2a2cd8f3335f855d37048f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716820"
---
# <a name="approximatelyapplydiagonalunitary-operation"></a><span data-ttu-id="d6219-102">Operazione ApproximatelyApplyDiagonalUnitary</span><span class="sxs-lookup"><span data-stu-id="d6219-102">ApproximatelyApplyDiagonalUnitary operation</span></span>

<span data-ttu-id="d6219-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d6219-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d6219-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d6219-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d6219-105">Applica una matrice di fasi complesse a stati di base numerica di un registro di qubits, troncando gli angoli di rotazione piccoli in base a una determinata tolleranza.</span><span class="sxs-lookup"><span data-stu-id="d6219-105">Applies an array of complex phases to numeric basis states of a register of qubits, truncating small rotation angles according to a given tolerance.</span></span>

```qsharp
operation ApproximatelyApplyDiagonalUnitary (tolerance : Double, coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="d6219-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d6219-106">Description</span></span>

<span data-ttu-id="d6219-107">Questa operazione implementa un unitario diagonale che applica una fase complessa $e ^ {i \ theta_j} $ sullo stato del numero di $n $-qubit $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="d6219-107">This operation implements a diagonal unitary that applies a complex phase $e^{i \theta_j}$ on the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="d6219-108">In particolare, questa operazione può essere rappresentata dall'unità</span><span class="sxs-lookup"><span data-stu-id="d6219-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="d6219-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} e ^ {i \ theta_j} \ket{j}\bra{j}.</span><span class="sxs-lookup"><span data-stu-id="d6219-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0}e^{i\theta_j}\ket{j}\bra{j}.</span></span>
<span data-ttu-id="d6219-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="d6219-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="d6219-111">Input</span><span class="sxs-lookup"><span data-stu-id="d6219-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="d6219-112">tolleranza: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d6219-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d6219-113">Tolleranza sotto la quale vengono troncati i coefficienti di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="d6219-113">A tolerance below which small coefficients are truncated.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="d6219-114">coefficienti: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="d6219-114">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="d6219-115">Matrice di un massimo di $2 ^ n $ coefficienti $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="d6219-115">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="d6219-116">Il coefficiente $j $ TH indicizza lo stato del numero $ \ket{j} $ codificato in formato little-endian.</span><span class="sxs-lookup"><span data-stu-id="d6219-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="d6219-117">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d6219-117">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d6219-118">$n il registro di controllo $-qubit che codifica gli Stati numerici $ \ket{j} $ in formato little-endian.</span><span class="sxs-lookup"><span data-stu-id="d6219-118">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d6219-119">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d6219-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d6219-120">Commenti</span><span class="sxs-lookup"><span data-stu-id="d6219-120">Remarks</span></span>

<span data-ttu-id="d6219-121">`coefficients` verrà riempito con gli elementi $ \ theta_j = $0,0 se sono specificati meno di $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="d6219-121">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="d6219-122">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="d6219-122">References</span></span>

- <span data-ttu-id="d6219-123">Sintesi dei circuiti logici Quantum Simone V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="d6219-123">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="d6219-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6219-124">See Also</span></span>

- [<span data-ttu-id="d6219-125">Microsoft. Quantum. Canon. ApplyDiagonalUnitary</span><span class="sxs-lookup"><span data-stu-id="d6219-125">Microsoft.Quantum.Canon.ApplyDiagonalUnitary</span></span>](xref:Microsoft.Quantum.Canon.ApplyDiagonalUnitary)