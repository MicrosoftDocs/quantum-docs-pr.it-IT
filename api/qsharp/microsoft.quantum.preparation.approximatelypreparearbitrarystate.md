---
uid: Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState
title: Operazione ApproximatelyPrepareArbitraryState
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApproximatelyPrepareArbitraryState
qsharp.summary: >-
  > [!WARNING]

  > ApproximatelyPrepareArbitraryState has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryStateCP> instead.


  Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.
ms.openlocfilehash: 9e1b172258acd0cb09b824a773e7e79d44fec20c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193710"
---
# <a name="approximatelypreparearbitrarystate-operation"></a><span data-ttu-id="2617c-102">Operazione ApproximatelyPrepareArbitraryState</span><span class="sxs-lookup"><span data-stu-id="2617c-102">ApproximatelyPrepareArbitraryState operation</span></span>

<span data-ttu-id="2617c-103">Spazio dei nomi: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="2617c-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="2617c-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2617c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="2617c-105">ApproximatelyPrepareArbitraryState è stato deprecato.</span><span class="sxs-lookup"><span data-stu-id="2617c-105">ApproximatelyPrepareArbitraryState has been deprecated.</span></span> <span data-ttu-id="2617c-106">Usare invece <xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryStateCP>.</span><span class="sxs-lookup"><span data-stu-id="2617c-106">Please use <xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryStateCP> instead.</span></span>

<span data-ttu-id="2617c-107">Dato un set di coefficienti e un registro Quantum con codifica little-endian, prepara uno stato in tale registro descritto dai coefficienti specificati, fino a una determinata tolleranza di approssimazione.</span><span class="sxs-lookup"><span data-stu-id="2617c-107">Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.</span></span>

```qsharp
operation ApproximatelyPrepareArbitraryState (tolerance : Double, coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="2617c-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2617c-108">Description</span></span>

<span data-ttu-id="2617c-109">Questa operazione prepara uno stato quantico arbitrario $ \ket{\psi} $ con coefficienti complessi $r _j e ^ {i t_j} $ dallo stato di base di calcolo $n $-qubit $ \ket{0 \cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="2617c-109">This operation prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0 \cdots 0}$.</span></span>
<span data-ttu-id="2617c-110">In particolare, l'azione di questa operazione può essere simulata dalla trasformazione unitaria $U $ che agisce sullo stato all-zero come</span><span class="sxs-lookup"><span data-stu-id="2617c-110">In particular, the action of this operation can be simulated by the a unitary transformation $U$ which acts on the all-zeros state as</span></span>

<span data-ttu-id="2617c-111">$ $ \begin{align} U\ket {0... 0} & = \ket{\psi} \\ \\ & = \frac{\ Sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}} {\sqrt{\ Sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="2617c-111">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\\\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{ \sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.</span></span>
<span data-ttu-id="2617c-112">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="2617c-112">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="2617c-113">Input</span><span class="sxs-lookup"><span data-stu-id="2617c-113">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="2617c-114">tolleranza: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2617c-114">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2617c-115">Tolleranza di approssimazione da utilizzare durante la preparazione dello stato specificato.</span><span class="sxs-lookup"><span data-stu-id="2617c-115">The approximation tolerance to be used when preparing the given state.</span></span>


### <a name="coefficients--complexpolar"></a><span data-ttu-id="2617c-116">coefficienti: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="2617c-116">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="2617c-117">Matrice di un massimo di $2 ^ n $ coefficienti complessi, rappresentati dal valore assoluto e dalla fase $ (r_j, t_j) $.</span><span class="sxs-lookup"><span data-stu-id="2617c-117">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="2617c-118">Il coefficiente $j $ TH indicizza lo stato del numero $ \ket{j} $ codificato in formato little-endian.</span><span class="sxs-lookup"><span data-stu-id="2617c-118">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="2617c-119">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2617c-119">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="2617c-120">Qubit registra il numero di codifica in formato little-endian.</span><span class="sxs-lookup"><span data-stu-id="2617c-120">Qubit register encoding number states in little-endian format.</span></span> <span data-ttu-id="2617c-121">Questo dovrebbe essere inizializzato nello stato di base di calcolo $ \ket{0...0} $.</span><span class="sxs-lookup"><span data-stu-id="2617c-121">This is expected to be initialized in the computational basis state $\ket{0...0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2617c-122">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2617c-122">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2617c-123">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2617c-123">Remarks</span></span>

<span data-ttu-id="2617c-124">I coefficienti di input negativi $r _j < $0 verranno trattati come se fossero positivi con il valore $ | r_j | $.</span><span class="sxs-lookup"><span data-stu-id="2617c-124">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="2617c-125">`coefficients` verrà riempito con gli elementi $ (r_j, t_j) = (0,0, 0,0) $ se sono specificati meno di $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="2617c-125">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="2617c-126">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="2617c-126">References</span></span>

- <span data-ttu-id="2617c-127">Sintesi dei circuiti logici Quantum Simone V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="2617c-127">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="2617c-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2617c-128">See Also</span></span>

- [<span data-ttu-id="2617c-129">Microsoft. Quantum. preping. ApproximatelyPrepareArbitraryState</span><span class="sxs-lookup"><span data-stu-id="2617c-129">Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState</span></span>](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)