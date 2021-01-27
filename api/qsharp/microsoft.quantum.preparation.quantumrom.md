---
uid: Microsoft.Quantum.Preparation.QuantumROM
title: QuantumROM (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROM
qsharp.summary: >-
  > [!WARNING]

  > QuantumROM has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedState> instead.


  Uses the Quantum ROM technique to represent a given density matrix.

  Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$. In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$. In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}. \end{align} $$
ms.openlocfilehash: 64ed9aed7c9d9a4a689c5926f3cd085a2521c4db
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856811"
---
# <a name="quantumrom-function"></a><span data-ttu-id="3c237-102">QuantumROM (funzione)</span><span class="sxs-lookup"><span data-stu-id="3c237-102">QuantumROM function</span></span>

<span data-ttu-id="3c237-103">Spazio dei nomi: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="3c237-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="3c237-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3c237-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="3c237-105">QuantumROM è stato deprecato.</span><span class="sxs-lookup"><span data-stu-id="3c237-105">QuantumROM has been deprecated.</span></span> <span data-ttu-id="3c237-106">Usare invece <xref:Microsoft.Quantum.Preparation.PurifiedMixedState>.</span><span class="sxs-lookup"><span data-stu-id="3c237-106">Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedState> instead.</span></span>

<span data-ttu-id="3c237-107">Usa la tecnica Quantum ROM per rappresentare una matrice di densità specificata.</span><span class="sxs-lookup"><span data-stu-id="3c237-107">Uses the Quantum ROM technique to represent a given density matrix.</span></span>

<span data-ttu-id="3c237-108">Dato un elenco di $N $ coefficienti $ \ alpha_j $, restituisce un Unity $U $ che usa la tecnica Quantum-ROM per preparare un'approssimazione $ \tilde\rho\ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} $ della purificazione della matrice di densità $ \rho = \ sum_ {j = 0} ^ {N-1} \frac{| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} $.</span><span class="sxs-lookup"><span data-stu-id="3c237-108">Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$.</span></span> <span data-ttu-id="3c237-109">In questa approssimazione, l'errore $ \epsilon $ è tale che $ | p_j-\frac{| alpha_j |} {\ sum_k | \ alpha_k |} | \Le \epsilon/N $ e $ \| \tilde\rho-\rho \| \Le \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="3c237-109">In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$.</span></span> <span data-ttu-id="3c237-110">In altre parole, $ $ \begin{align} U\ket {0} ^ {\lceil\ Log_2 N\rceil} \ KET {0} ^ {m} = \ Sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\Text{Garbage} _J}.</span><span class="sxs-lookup"><span data-stu-id="3c237-110">In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}.</span></span>
<span data-ttu-id="3c237-111">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="3c237-111">\end{align} $$</span></span>

```qsharp
function QuantumROM (targetError : Double, coefficients : Double[]) : ((Int, (Int, Int)), Double, ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))
```


## <a name="input"></a><span data-ttu-id="3c237-112">Input</span><span class="sxs-lookup"><span data-stu-id="3c237-112">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="3c237-113">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3c237-113">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3c237-114">Errore di destinazione $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="3c237-114">The target error $\epsilon$.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="3c237-115">coefficienti: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="3c237-115">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="3c237-116">Matrice di $N $ coefficienti che specificano la probabilità di Stati di base.</span><span class="sxs-lookup"><span data-stu-id="3c237-116">Array of $N$ coefficients specifying the probability of basis states.</span></span>
<span data-ttu-id="3c237-117">I numeri negativi $-\ alpha_j $ verranno considerati positivi $ | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="3c237-117">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--intintintdoublelittleendianqubit--unit--is-adj--ctl"></a><span data-ttu-id="3c237-118">Output:[((int,](xref:microsoft.quantum.lang-ref.int)int[,](xref:microsoft.quantum.lang-ref.int)[int](xref:microsoft.quantum.lang-ref.int)),[Double](xref:microsoft.quantum.lang-ref.double), ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [unit](xref:microsoft.quantum.lang-ref.unit) is ADJ + CTL)</span><span class="sxs-lookup"><span data-stu-id="3c237-118">Output : (([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double),([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl)</span></span>

## <a name="first-parameter"></a><span data-ttu-id="3c237-119">Primo parametro</span><span class="sxs-lookup"><span data-stu-id="3c237-119">First parameter</span></span>

<span data-ttu-id="3c237-120">Tupla `(x,(y,z))` `x = y + z` in cui è il numero totale di qubits allocato, `y` è il numero di qubits per il `LittleEndian` registro e `z` è il numero di Garbage qubits.</span><span class="sxs-lookup"><span data-stu-id="3c237-120">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="3c237-121">Secondo parametro</span><span class="sxs-lookup"><span data-stu-id="3c237-121">Second parameter</span></span>

<span data-ttu-id="3c237-122">Una regola $ \ sum_j | \ alpha_j | $ della matrice coefficiente.</span><span class="sxs-lookup"><span data-stu-id="3c237-122">The one-norm $\sum_j |\alpha_j|$ of the coefficient array.</span></span>

## <a name="third-parameter"></a><span data-ttu-id="3c237-123">Terzo parametro</span><span class="sxs-lookup"><span data-stu-id="3c237-123">Third parameter</span></span>

<span data-ttu-id="3c237-124">Unitario $U $.</span><span class="sxs-lookup"><span data-stu-id="3c237-124">The unitary $U$.</span></span>

## <a name="example"></a><span data-ttu-id="3c237-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="3c237-125">Example</span></span>

<span data-ttu-id="3c237-126">Il seguente frammento di codice prepara una purificazione dello stato $3 $-qubit $ \rho = \ sum_ {j = 0} ^ {4} \frac{| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} $, dove $ \vec\alpha = (1.0, 2.0, 3.0, 4.0, 5.0) $ e l'errore è `1e-3` ;</span><span class="sxs-lookup"><span data-stu-id="3c237-126">The following code snippet prepares an purification of the $3$-qubit state $\rho=\sum_{j=0}^{4}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$, where $\vec\alpha=(1.0,2.0,3.0,4.0,5.0)$, and the error is `1e-3`;</span></span>

```qsharp
let coefficients = [1.0,2.0,3.0,4.0,5.0];
let targetError = 1e-3;
let ((nTotalQubits, (nIndexQubits, nGarbageQubits)), oneNorm, op) = QuantumROM(targetError, coefficients);
using (indexRegister = Qubit[nIndexQubits]) {
    using (garbageRegister = Qubit[nGarbageQubits]) {
        op(LittleEndian(indexRegister), garbageRegister);
    }
}
```

## <a name="references"></a><span data-ttu-id="3c237-127">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="3c237-127">References</span></span>

- <span data-ttu-id="3c237-128">Codifica di spettri elettronici nei circuiti Quantum con complessità T lineare Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru pallido, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="3c237-128">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>