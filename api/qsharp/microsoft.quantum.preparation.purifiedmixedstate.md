---
uid: Microsoft.Quantum.Preparation.PurifiedMixedState
title: PurifiedMixedState (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedState
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed state.\rA \"purified mixed state\" refers to states of the form |ψ⟩ = Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |garbageᵢ⟩ specified by a vector of\rcoefficients {\U0001D45Dᵢ}. States of this form can be reduced to mixed states ρ ≔ \U0001D45Dᵢ |\U0001D456⟩⟨\U0001D456| by tracing over the \"garbage\"\rregister (that is, a mixed state that is diagonal in the computational basis).\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: 73b031f1082d0a12975abad074b07184dcbabdbe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230022"
---
# <a name="purifiedmixedstate-function"></a><span data-ttu-id="ac5a4-102">PurifiedMixedState (funzione)</span><span class="sxs-lookup"><span data-stu-id="ac5a4-102">PurifiedMixedState function</span></span>

<span data-ttu-id="ac5a4-103">Spazio dei nomi: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="ac5a4-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="ac5a4-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ac5a4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ac5a4-105">Restituisce un'operazione che prepara una purificazione di uno stato misto specificato.</span><span class="sxs-lookup"><span data-stu-id="ac5a4-105">Returns an operation that prepares a a purification of a given mixed state.</span></span>
<span data-ttu-id="ac5a4-106">Uno "stato misto purificato" si riferisce agli Stati del formato | ψ ⟩ = σi √ pi | i ⟩ | garbagei ⟩ specificato da un vettore di coefficienti {pi}.</span><span class="sxs-lookup"><span data-stu-id="ac5a4-106">A "purified mixed state" refers to states of the form |ψ⟩ = Σᵢ √𝑝ᵢ |𝑖⟩ |garbageᵢ⟩ specified by a vector of coefficients {𝑝ᵢ}.</span></span> <span data-ttu-id="ac5a4-107">Gli Stati di questo modulo possono essere ridotti a stati misti ρ ≔ pi | i ⟩ ⟨ | eseguendo la traccia sul Registro di Garbage Collection, ovvero uno stato misto diagonale nella base computazionale.</span><span class="sxs-lookup"><span data-stu-id="ac5a4-107">States of this form can be reduced to mixed states ρ ≔ 𝑝ᵢ |𝑖⟩⟨𝑖| by tracing over the "garbage" register (that is, a mixed state that is diagonal in the computational basis).</span></span>

<span data-ttu-id="ac5a4-108"> https://arxiv.org/pdf/1805.03662.pdf?page=15Per ulteriori informazioni, vedere.</span><span class="sxs-lookup"><span data-stu-id="ac5a4-108">See https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion.</span></span>

```qsharp
function PurifiedMixedState (targetError : Double, coefficients : Double[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a><span data-ttu-id="ac5a4-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ac5a4-109">Description</span></span>

<span data-ttu-id="ac5a4-110">Usa la tecnica Quantum ROM per rappresentare una matrice di densità specificata, restituendo tale rappresentazione come operazione di preparazione dello stato.</span><span class="sxs-lookup"><span data-stu-id="ac5a4-110">Uses the Quantum ROM technique to represent a given density matrix, returning that representation as a state preparation operation.</span></span>

<span data-ttu-id="ac5a4-111">In particolare, dato un elenco di $N $ coefficienti $ \ alpha_j $, questa funzione restituisce un'operazione che usa la tecnica Quantum ROM per preparare un'approssimazione $ $ \begin{align} \tilde\rho = \ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} \end{align} $ $ dello stato misto $ $ \begin{align} \rho = \ sum_ {j = 0} ^ {N-1} \ frac {| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j}, \end{align} $ $ dove ogni $p _j $ è un'approssimazione al coefficiente specificato $ \ alpha_j $ tale che $ $ \begin{align} \left | p_j-\frac{| \ alpha_j |} {\ sum_k | \ alpha_k |} \Le \frac{\epsilon}{N} \end{align} $ $ per ogni $j $.</span><span class="sxs-lookup"><span data-stu-id="ac5a4-111">In particular, given a list of $N$ coefficients $\alpha_j$, this function returns an operation that uses the Quantum ROM technique to prepare an approximation $$ \begin{align} \tilde\rho = \sum_{j = 0}^{N - 1} p_j \ket{j}\bra{j} \end{align} $$ of the mixed state $$ \begin{align} \rho = \sum_{j = 0}^{N-1}\ frac{|alpha_j|}{\sum_k |\alpha_k|} \ket{j}\bra{j}, \end{align} $$ where each $p_j$ is an approximation to the given coefficient $\alpha_j$ such that $$ \begin{align} \left| p_j - \frac{ |\alpha_j| }{ \sum_k |\alpha_k| } \le \frac{\epsilon}{N} \end{align} $$ for each $j$.</span></span>

<span data-ttu-id="ac5a4-112">Quando viene passato un registro di indice e un registro di Garbage qubits, inizialmente nello stato $ \ket {0} \ket{00\cdots 0}, l'operazione restituita prepara entrambi i registri per la purificazione di $ \tilde \rho $, $ $ \begin{align} \ Sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\text{garbage} _J}, \end{align} $ $, in modo che la reimpostazione e la deallocazione del registro di Garbage Collection interagisce con la preparazione desiderata nell'errore $ \epsilon</span><span class="sxs-lookup"><span data-stu-id="ac5a4-112">When passed an index register and a register of garbage qubits, initially in the state $\ket{0} \ket{00\cdots 0}, the returned operation prepares both registers into the purification of $\tilde \rho$, $$ \begin{align} \sum_{j=0}^{N-1} \sqrt{p_j} \ket{j}\ket{\text{garbage}_j}, \end{align} $$ such that resetting and deallocating the garbage register enacts the desired preparation to within the target error $\epsilon$.</span></span>

## <a name="input"></a><span data-ttu-id="ac5a4-113">Input</span><span class="sxs-lookup"><span data-stu-id="ac5a4-113">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="ac5a4-114">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ac5a4-114">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ac5a4-115">Errore di destinazione $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="ac5a4-115">The target error $\epsilon$.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="ac5a4-116">coefficienti: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="ac5a4-116">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="ac5a4-117">Matrice di $N $ coefficienti che specificano la probabilità di Stati di base.</span><span class="sxs-lookup"><span data-stu-id="ac5a4-117">Array of $N$ coefficients specifying the probability of basis states.</span></span>
<span data-ttu-id="ac5a4-118">I numeri negativi $-\ alpha_j $ verranno considerati positivi $ | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="ac5a4-118">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--mixedstatepreparation"></a><span data-ttu-id="ac5a4-119">Output: [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span><span class="sxs-lookup"><span data-stu-id="ac5a4-119">Output : [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span></span>

<span data-ttu-id="ac5a4-120">Operazione che prepara $ \tilde \rho $ come purificazione su un indice misto e un registro di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="ac5a4-120">An operation that prepares $\tilde \rho$ as a purification onto a joint index and garbage register.</span></span>

## <a name="remarks"></a><span data-ttu-id="ac5a4-121">Commenti</span><span class="sxs-lookup"><span data-stu-id="ac5a4-121">Remarks</span></span>

<span data-ttu-id="ac5a4-122">I coefficienti forniti a questa operazione vengono normalizzati secondo la norma 1, in modo che i coefficienti vengano sempre considerati per descrivere una distribuzione di probabilità categorica valida.</span><span class="sxs-lookup"><span data-stu-id="ac5a4-122">The coefficients provided to this operation are normalized following the 1-norm, such that the coefficients are always considered to describe a valid categorical probability distribution.</span></span>

## <a name="references"></a><span data-ttu-id="ac5a4-123">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="ac5a4-123">References</span></span>

- <span data-ttu-id="ac5a4-124">Codifica di spettri elettronici nei circuiti Quantum con complessità T lineare Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru pallido, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="ac5a4-124">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>

## <a name="see-also"></a><span data-ttu-id="ac5a4-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac5a4-125">See Also</span></span>

- [<span data-ttu-id="ac5a4-126">Microsoft. Quantum. preping. PurifiedMixedStateWithData</span><span class="sxs-lookup"><span data-stu-id="ac5a4-126">Microsoft.Quantum.Preparation.PurifiedMixedStateWithData</span></span>](xref:Microsoft.Quantum.Preparation.PurifiedMixedStateWithData)