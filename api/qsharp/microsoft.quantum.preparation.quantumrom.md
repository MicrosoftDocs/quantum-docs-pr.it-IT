---
uid: Microsoft.Quantum.Preparation.QuantumROM
title: QuantumROM (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROM
qsharp.summary: >-
  > [!WARNING]

  > QuantumROM has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedState> instead.


  Uses the Quantum ROM technique to represent a given density matrix.

  Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$. In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$. In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}. \end{align} $$
ms.openlocfilehash: 1ee805fb2ea02121daaab7fc3eb5dbbcb134b470
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229886"
---
# <a name="quantumrom-function"></a><span data-ttu-id="37823-102">QuantumROM (funzione)</span><span class="sxs-lookup"><span data-stu-id="37823-102">QuantumROM function</span></span>

<span data-ttu-id="37823-103">Spazio dei nomi: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="37823-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="37823-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="37823-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="37823-105">QuantumROM è stato deprecato.</span><span class="sxs-lookup"><span data-stu-id="37823-105">QuantumROM has been deprecated.</span></span> <span data-ttu-id="37823-106">Usare invece <xref:Microsoft.Quantum.Preparation.PurifiedMixedState>.</span><span class="sxs-lookup"><span data-stu-id="37823-106">Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedState> instead.</span></span>

<span data-ttu-id="37823-107">Usa la tecnica Quantum ROM per rappresentare una matrice di densità specificata.</span><span class="sxs-lookup"><span data-stu-id="37823-107">Uses the Quantum ROM technique to represent a given density matrix.</span></span>

<span data-ttu-id="37823-108">Dato un elenco di $N $ coefficienti $ \ alpha_j $, restituisce un Unity $U $ che usa la tecnica Quantum-ROM per preparare un'approssimazione $ \tilde\rho\ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} $ della purificazione della matrice di densità $ \rho = \ sum_ {j = 0} ^ {N-1} \frac{| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} $.</span><span class="sxs-lookup"><span data-stu-id="37823-108">Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$.</span></span> <span data-ttu-id="37823-109">In questa approssimazione, l'errore $ \epsilon $ è tale che $ | p_j-\frac{| alpha_j |} {\ sum_k | \ alpha_k |} | \Le \epsilon/N $ e $ \| \tilde\rho-\rho \| \Le \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="37823-109">In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$.</span></span> <span data-ttu-id="37823-110">In altre parole, $ $ \begin{align} U\ket {0} ^ {\lceil\ Log_2 N\rceil} \ KET {0} ^ {m} = \ Sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\Text{Garbage} _J}.</span><span class="sxs-lookup"><span data-stu-id="37823-110">In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}.</span></span>
<span data-ttu-id="37823-111">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="37823-111">\end{align} $$</span></span>

```qsharp
function QuantumROM (targetError : Double, coefficients : Double[]) : ((Int, (Int, Int)), Double, ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))
```


## <a name="input"></a><span data-ttu-id="37823-112">Input</span><span class="sxs-lookup"><span data-stu-id="37823-112">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="37823-113">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="37823-113">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="37823-114">Errore di destinazione $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="37823-114">The target error $\epsilon$.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="37823-115">coefficienti: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="37823-115">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="37823-116">Matrice di $N $ coefficienti che specificano la probabilità di Stati di base.</span><span class="sxs-lookup"><span data-stu-id="37823-116">Array of $N$ coefficients specifying the probability of basis states.</span></span>
<span data-ttu-id="37823-117">I numeri negativi $-\ alpha_j $ verranno considerati positivi $ | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="37823-117">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--intintintdoublelittleendianqubit--unit--is-adj--ctl"></a><span data-ttu-id="37823-118">Output:[((int,](xref:microsoft.quantum.lang-ref.int)int[,](xref:microsoft.quantum.lang-ref.int)[int](xref:microsoft.quantum.lang-ref.int)),[Double](xref:microsoft.quantum.lang-ref.double), ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [unit](xref:microsoft.quantum.lang-ref.unit) is ADJ + CTL)</span><span class="sxs-lookup"><span data-stu-id="37823-118">Output : (([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double),([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl)</span></span>

## <a name="first-parameter"></a><span data-ttu-id="37823-119">Primo parametro</span><span class="sxs-lookup"><span data-stu-id="37823-119">First parameter</span></span>

<span data-ttu-id="37823-120">Tupla `(x,(y,z))` `x = y + z` in cui è il numero totale di qubits allocato, `y` è il numero di qubits per il `LittleEndian` registro e `z` è il numero di Garbage qubits.</span><span class="sxs-lookup"><span data-stu-id="37823-120">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="37823-121">Secondo parametro</span><span class="sxs-lookup"><span data-stu-id="37823-121">Second parameter</span></span>

<span data-ttu-id="37823-122">Una regola $ \ sum_j | \ alpha_j | $ della matrice coefficiente.</span><span class="sxs-lookup"><span data-stu-id="37823-122">The one-norm $\sum_j |\alpha_j|$ of the coefficient array.</span></span>

## <a name="third-parameter"></a><span data-ttu-id="37823-123">Terzo parametro</span><span class="sxs-lookup"><span data-stu-id="37823-123">Third parameter</span></span>

<span data-ttu-id="37823-124">Unitario $U $.</span><span class="sxs-lookup"><span data-stu-id="37823-124">The unitary $U$.</span></span>

## <a name="references"></a><span data-ttu-id="37823-125">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="37823-125">References</span></span>

- <span data-ttu-id="37823-126">Codifica di spettri elettronici nei circuiti Quantum con complessità T lineare Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru pallido, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="37823-126">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>