---
uid: Microsoft.Quantum.Preparation.PrepareArbitraryStateD
title: Operazione PrepareArbitraryStateD
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareArbitraryStateD
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.
ms.openlocfilehash: cca0ea16dca3f3da8ce76a43f1012ffa0e4a72e0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210608"
---
# <a name="preparearbitrarystated-operation"></a><span data-ttu-id="41975-102">Operazione PrepareArbitraryStateD</span><span class="sxs-lookup"><span data-stu-id="41975-102">PrepareArbitraryStateD operation</span></span>

<span data-ttu-id="41975-103">Spazio dei nomi: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="41975-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="41975-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="41975-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="41975-105">Dato un set di coefficienti e un registro Quantum con codifica little-endian, prepara uno stato in tale registro descritto dai coefficienti specificati.</span><span class="sxs-lookup"><span data-stu-id="41975-105">Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.</span></span>

```qsharp
operation PrepareArbitraryStateD (coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="41975-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="41975-106">Description</span></span>

<span data-ttu-id="41975-107">Questa operazione prepara uno stato quantico arbitrario $ \ket{\psi} $ con coefficienti complessi $r _j e ^ {i t_j} $ dallo stato di base di calcolo $n $-qubit $ \ket{0 \cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="41975-107">This operation prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0 \cdots 0}$.</span></span>
<span data-ttu-id="41975-108">In particolare, l'azione di questa operazione può essere simulata dalla trasformazione unitaria $U $ che agisce sullo stato all-zeros come</span><span class="sxs-lookup"><span data-stu-id="41975-108">In particular, the action of this operation can be simulated by the a unitary transformation $U$ that acts on the all-zeros state as</span></span>

<span data-ttu-id="41975-109">$ $ \begin{align} U\ket {0... 0} & = \ket{\psi} \\ \\ & = \frac{\ Sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}} {\sqrt{\ Sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="41975-109">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\\\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{ \sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.</span></span>
<span data-ttu-id="41975-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="41975-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="41975-111">Input</span><span class="sxs-lookup"><span data-stu-id="41975-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="41975-112">coefficienti: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="41975-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="41975-113">Matrice di un massimo di $2 ^ n $ coefficienti reali.</span><span class="sxs-lookup"><span data-stu-id="41975-113">Array of up to $2^n$ real coefficients.</span></span> <span data-ttu-id="41975-114">Il coefficiente $j $ TH indicizza lo stato del numero $ \ket{j} $ codificato in formato little-endian.</span><span class="sxs-lookup"><span data-stu-id="41975-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="41975-115">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="41975-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="41975-116">Qubit registra il numero di codifica in formato little-endian.</span><span class="sxs-lookup"><span data-stu-id="41975-116">Qubit register encoding number states in little-endian format.</span></span> <span data-ttu-id="41975-117">Questo dovrebbe essere inizializzato nello stato di base di calcolo $ \ket{0...0} $.</span><span class="sxs-lookup"><span data-stu-id="41975-117">This is expected to be initialized in the computational basis state $\ket{0...0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="41975-118">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="41975-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="41975-119">Commenti</span><span class="sxs-lookup"><span data-stu-id="41975-119">Remarks</span></span>

<span data-ttu-id="41975-120">I coefficienti di input negativi $r _j < $0 verranno trattati come se fossero positivi con il valore $ | r_j | $.</span><span class="sxs-lookup"><span data-stu-id="41975-120">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="41975-121">`coefficients` verrà riempito con gli elementi $ (r_j, t_j) = (0,0, 0,0) $ se sono specificati meno di $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="41975-121">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="41975-122">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="41975-122">References</span></span>

- <span data-ttu-id="41975-123">Sintesi dei circuiti logici Quantum Simone V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="41975-123">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="41975-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41975-124">See Also</span></span>

- [<span data-ttu-id="41975-125">Microsoft. Quantum. preping. ApproximatelyPrepareArbitraryState</span><span class="sxs-lookup"><span data-stu-id="41975-125">Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState</span></span>](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)