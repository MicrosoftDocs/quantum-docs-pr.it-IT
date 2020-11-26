---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateWithData
title: PurifiedMixedStateWithData (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateWithData
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed\rstate, entangled with a register representing a given collection of data.\rA \"purified mixed state with data\" refers to a state of the form Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |\U0001D465ᵢ⟩ |garbageᵢ⟩,\rwhere each \U0001D465ᵢ is a bitstring encoding additional data associated with the register |\U0001D456⟩.\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: c89ee8f5df58e5d6b154b67d2b39db208bc8a215
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229954"
---
# <a name="purifiedmixedstatewithdata-function"></a><span data-ttu-id="860d4-102">PurifiedMixedStateWithData (funzione)</span><span class="sxs-lookup"><span data-stu-id="860d4-102">PurifiedMixedStateWithData function</span></span>

<span data-ttu-id="860d4-103">Spazio dei nomi: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="860d4-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="860d4-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="860d4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="860d4-105">Restituisce un'operazione che prepara una purificazione di uno stato misto specificato, correlata a un registro che rappresenta una raccolta di dati specificata.</span><span class="sxs-lookup"><span data-stu-id="860d4-105">Returns an operation that prepares a a purification of a given mixed state, entangled with a register representing a given collection of data.</span></span>
<span data-ttu-id="860d4-106">Uno "stato misto purificato con dati" si riferisce allo stato del formato σi √ pi | i ⟩ | XI ⟩ | garbagei ⟩, in cui ogni XI è un Bitstring di codifica dei dati aggiuntivi associati al registro | i ⟩.</span><span class="sxs-lookup"><span data-stu-id="860d4-106">A "purified mixed state with data" refers to a state of the form Σᵢ √𝑝ᵢ |𝑖⟩ |𝑥ᵢ⟩ |garbageᵢ⟩, where each 𝑥ᵢ is a bitstring encoding additional data associated with the register |𝑖⟩.</span></span>

<span data-ttu-id="860d4-107"> https://arxiv.org/pdf/1805.03662.pdf?page=15Per ulteriori informazioni, vedere.</span><span class="sxs-lookup"><span data-stu-id="860d4-107">See https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion.</span></span>

```qsharp
function PurifiedMixedStateWithData (targetError : Double, coefficients : (Double, Bool[])[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a><span data-ttu-id="860d4-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="860d4-108">Description</span></span>

<span data-ttu-id="860d4-109">Usa la tecnica Quantum ROM per rappresentare una matrice di densità specificata, restituendo tale rappresentazione come operazione di preparazione dello stato.</span><span class="sxs-lookup"><span data-stu-id="860d4-109">Uses the Quantum ROM technique to represent a given density matrix, returning that representation as a state preparation operation.</span></span>

<span data-ttu-id="860d4-110">In particolare, in base a un elenco di $N $ coefficienti $ \ alpha_j $ e a un Bitstring $ \vec{x}_j $ associato a ogni coefficiente, questa funzione restituisce un'operazione che usa la tecnica Quantum ROM per preparare un'approssimazione $ $ \begin{align} \tilde\rho = \sum_{j = 0} ^ {n-1} p_j \ket{j}\bra{j} \otimes \ket{\vec{x} _J} \bra{\vec{x}_j} \end{align} $ $ dello stato misto $ $ \begin{align} \rho = \sum_{j = 0} ^ {n-1} \ frac {| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} \otimes \ket{\vec{x} _j} \bra{\vec{x} _j}, \end{align} $ $ dove ogni $p _j $ è un'approssimazione al coefficiente specificato $ \ alpha_j $ in modo tale che $ $ \begin{align} \left | p_j-\frac{| \ alpha_j |} {\ sum_k | \ alpha_k |} \Le \frac{\epsilon}{N} \end{align} $ $ per ogni $j $.</span><span class="sxs-lookup"><span data-stu-id="860d4-110">In particular, given a list of $N$ coefficients $\alpha_j$, and a bitstring $\vec{x}_j$ associated with each coefficient, this function returns an operation that uses the Quantum ROM technique to prepare an approximation $$ \begin{align} \tilde\rho = \sum_{j = 0}^{N - 1} p_j \ket{j}\bra{j} \otimes \ket{\vec{x}_j}\bra{\vec{x}_j} \end{align} $$ of the mixed state $$ \begin{align} \rho = \sum_{j = 0}^{N-1}\ frac{|alpha_j|}{\sum_k |\alpha_k|} \ket{j}\bra{j} \otimes \ket{\vec{x}_j}\bra{\vec{x}_j}, \end{align} $$ where each $p_j$ is an approximation to the given coefficient $\alpha_j$ such that $$ \begin{align} \left| p_j - \frac{ |\alpha_j| }{ \sum_k |\alpha_k| } \le \frac{\epsilon}{N} \end{align} $$ for each $j$.</span></span>

<span data-ttu-id="860d4-111">Quando viene passato un registro di indice e un registro di Garbage qubits, inizialmente nello stato $ \ket {0} \ket{00\cdots 0}, l'operazione restituita prepara entrambi i registri per la purificazione di $ \tilde \rho $, $ $ \begin{align} \ Sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j} \ket{\vec{x} _J} \ket{\text{garbage} _J}, \end{align} $ $, in modo che la reimpostazione e la deallocazione del registro di Garbage Collection comportino la preparazione desiderata nell'errore di destinazione $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="860d4-111">When passed an index register and a register of garbage qubits, initially in the state $\ket{0} \ket{00\cdots 0}, the returned operation prepares both registers into the purification of $\tilde \rho$, $$ \begin{align} \sum_{j=0}^{N-1} \sqrt{p_j} \ket{j} \ket{\vec{x}_j} \ket{\text{garbage}_j}, \end{align} $$ such that resetting and deallocating the garbage register enacts the desired preparation to within the target error $\epsilon$.</span></span>

## <a name="input"></a><span data-ttu-id="860d4-112">Input</span><span class="sxs-lookup"><span data-stu-id="860d4-112">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="860d4-113">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="860d4-113">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="860d4-114">Errore di destinazione $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="860d4-114">The target error $\epsilon$.</span></span>


### <a name="coefficients--doublebool"></a><span data-ttu-id="860d4-115">coefficienti: ([Double](xref:microsoft.quantum.lang-ref.double),[bool](xref:microsoft.quantum.lang-ref.bool)[]) []</span><span class="sxs-lookup"><span data-stu-id="860d4-115">coefficients : ([Double](xref:microsoft.quantum.lang-ref.double),[Bool](xref:microsoft.quantum.lang-ref.bool)[])[]</span></span>

<span data-ttu-id="860d4-116">Matrice di $N $ coefficienti che specificano la probabilità degli Stati di base, insieme al Bitstring $ \vec{x} _j $ associato a ogni coefficiente.</span><span class="sxs-lookup"><span data-stu-id="860d4-116">Array of $N$ coefficients specifying the probability of basis states, along with the bitstring $\vec{x}_j$ associated with each coefficient.</span></span>
<span data-ttu-id="860d4-117">I numeri negativi $-\ alpha_j $ verranno considerati positivi $ | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="860d4-117">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--mixedstatepreparation"></a><span data-ttu-id="860d4-118">Output: [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span><span class="sxs-lookup"><span data-stu-id="860d4-118">Output : [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span></span>

<span data-ttu-id="860d4-119">Operazione che prepara $ \tilde \rho $ come purificazione su un indice misto e un registro di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="860d4-119">An operation that prepares $\tilde \rho$ as a purification onto a joint index and garbage register.</span></span>

## <a name="remarks"></a><span data-ttu-id="860d4-120">Commenti</span><span class="sxs-lookup"><span data-stu-id="860d4-120">Remarks</span></span>

<span data-ttu-id="860d4-121">I coefficienti forniti a questa operazione vengono normalizzati secondo la norma 1, in modo che i coefficienti vengano sempre considerati per descrivere una distribuzione di probabilità categorica valida.</span><span class="sxs-lookup"><span data-stu-id="860d4-121">The coefficients provided to this operation are normalized following the 1-norm, such that the coefficients are always considered to describe a valid categorical probability distribution.</span></span>

## <a name="references"></a><span data-ttu-id="860d4-122">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="860d4-122">References</span></span>

- <span data-ttu-id="860d4-123">Codifica di spettri elettronici nei circuiti Quantum con complessità T lineare Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru pallido, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="860d4-123">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>

## <a name="see-also"></a><span data-ttu-id="860d4-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="860d4-124">See Also</span></span>

- [<span data-ttu-id="860d4-125">Microsoft. Quantum. preping. PurifiedMixedState</span><span class="sxs-lookup"><span data-stu-id="860d4-125">Microsoft.Quantum.Preparation.PurifiedMixedState</span></span>](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)