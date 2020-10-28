---
title: Simulazione di Dynamics hamiltoniana
description: Informazioni su come usare formule Trotter-Suzuki e qubitization per lavorare con le simulazioni hamiltoniana.
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.simulationalgorithms
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: a303d54476e42b98a14c6b452227b0e1346567c8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691896"
---
# <a name="simulating-hamiltonian-dynamics"></a><span data-ttu-id="44494-103">Simulazione di Dynamics hamiltoniana</span><span class="sxs-lookup"><span data-stu-id="44494-103">Simulating Hamiltonian Dynamics</span></span>

<span data-ttu-id="44494-104">Una volta che l'hamiltoniana è stata espressa come una somma di operatori elementari, le dinamiche possono essere compilate in operazioni Gate fondamentali usando una serie di tecniche ben note.</span><span class="sxs-lookup"><span data-stu-id="44494-104">Once the Hamiltonian has been expressed as a sum of elementary operators the dynamics can then be compiled into fundamental gate operations using a host of well-known techniques.</span></span>
<span data-ttu-id="44494-105">Tre approcci efficienti includono le formule Trotter – Suzuki, le combinazioni lineari di unitaries e qubitization.</span><span class="sxs-lookup"><span data-stu-id="44494-105">Three efficient approaches include are Trotter–Suzuki formulas, linear combinations of unitaries, and qubitization.</span></span>
<span data-ttu-id="44494-106">Questi tre approcci vengono illustrati di seguito e vengono :::no-loc(Q#)::: forniti esempi concreti di come implementare questi metodi usando la libreria di simulazione hamiltoniana.</span><span class="sxs-lookup"><span data-stu-id="44494-106">We explain these three approaches below and give concrete :::no-loc(Q#)::: examples of how to implement these methods using the Hamiltonian simulation library.</span></span>


## <a name="trottersuzuki-formulas"></a><span data-ttu-id="44494-107">Trotter-formule Suzuki</span><span class="sxs-lookup"><span data-stu-id="44494-107">Trotter–Suzuki Formulas</span></span>
<span data-ttu-id="44494-108">L'idea dietro le formule Trotter – Suzuki è semplice: esprimere l'Hamiltoniana come una somma di facile simulazione di hamiltonians e quindi approssimare l'evoluzione totale come una sequenza di queste evoluzioni più semplici.</span><span class="sxs-lookup"><span data-stu-id="44494-108">The idea behind Trotter–Suzuki formulas is simple: express the Hamiltonian as a sum of easy to simulate Hamiltonians and then approximate the total evolution as a sequence of these simpler evolutions.</span></span>
<span data-ttu-id="44494-109">In particolare, consentire a $H = \ sum_ {j = 1} ^ m H_j $ be the hamiltoniana.</span><span class="sxs-lookup"><span data-stu-id="44494-109">In particular, let $H=\sum_{j=1}^m H_j$ be the Hamiltonian.</span></span>
<span data-ttu-id="44494-110">Quindi, $ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \ prod_ {j = 1} ^ m e ^ {-iH_j t} + O (m ^ 2 t ^ 2), $ $, vale a dire che, se $t \ll $1, l'errore in questa approssimazione diventa irrilevante.</span><span class="sxs-lookup"><span data-stu-id="44494-110">Then, $$ e^{-i\sum_{j=1}^m H_j t} =\prod_{j=1}^m e^{-iH_j t} + O(m^2 t^2), $$ which is to say that, if $t\ll 1$, then the error in this approximation becomes negligible.</span></span>
<span data-ttu-id="44494-111">Si noti che se $e ^ {-i H t} $ era un esponenziale normale, l'errore in questa approssimazione non sarebbe $O (m ^ 2 t ^ 2) $: sarebbe zero.</span><span class="sxs-lookup"><span data-stu-id="44494-111">Note that if $e^{-i H t}$ were an ordinary exponential then the error in this approximation would not be $O(m^2 t^2)$: it would be zero.</span></span>
<span data-ttu-id="44494-112">Questo errore si verifica perché $e ^ {-iHt} $ è un operatore esponenziale e, di conseguenza, si verifica un errore durante l'utilizzo di questa formula a causa del fatto che i $H _j $ terms non vengono commutati, *ad esempio* $H _J H_k \ne H_k H_j $ in generale.</span><span class="sxs-lookup"><span data-stu-id="44494-112">This error occurs because $e^{-iHt}$ is an operator exponential and as a result there is an error incurred when using this formula due to the fact that the $H_j$ terms do not commute ( *i.e.* , $H_j H_k \ne H_k H_j$ in general).</span></span>

<span data-ttu-id="44494-113">Se $t $ è di grandi dimensioni, le formule Trotter-Suzuki possono comunque essere usate per simulare la dinamica in modo accurato suddividendo il valore in una sequenza di brevi passaggi temporali.</span><span class="sxs-lookup"><span data-stu-id="44494-113">If $t$ is large, Trotter–Suzuki formulas can still be used to simulate the dynamics accurately by breaking it up into a sequence of short time-steps.</span></span>
<span data-ttu-id="44494-114">$R $ sia il numero di passaggi eseguiti nell'evoluzione del tempo, quindi ogni fase viene eseguita per ora $t/r $.</span><span class="sxs-lookup"><span data-stu-id="44494-114">Let $r$ be the number of steps taken in the time evolution, so each time step runs for time $t/r$.</span></span> <span data-ttu-id="44494-115">Quindi, è necessario che $ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \left (\ prod_ {j = 1} ^ m e ^ {-iH_j t/r} \ Right) ^ r + O (m ^ 2 t ^ 2/r), $ $, che implica che se $r $ Scales come $m ^ 2 t ^ 2/\ Epsilon $, l'errore può essere eseguito al massimo $ \epsilon $ per qualsiasi $ \epsilon>$0.</span><span class="sxs-lookup"><span data-stu-id="44494-115">Then, we have that $$ e^{-i\sum_{j=1}^m H_j t} =\left(\prod_{j=1}^m e^{-iH_j t/r}\right)^r + O(m^2 t^2/r), $$ which implies that if $r$ scales as $m^2 t^2/\epsilon$ then the error can be made at most $\epsilon$ for any $\epsilon>0$.</span></span>

<span data-ttu-id="44494-116">È possibile creare approssimazioni più accurate creando una sequenza di operatori esponenziali in modo che i termini di errore vengano annullati.</span><span class="sxs-lookup"><span data-stu-id="44494-116">More accurate approximations can be built by constructing a sequence of operator exponentials such that the error terms cancel.</span></span>
<span data-ttu-id="44494-117">La formula più semplice, il secondo ordine Trotter-Suzuki formula, assume il formato $ $ U_2 (t) = \left (\ prod_ {j = 1} ^ {m} e ^ {-iH_j t/2R} \ prod_ {j = m} ^ 1 e ^ {-iH_j t/2R} \ Right) ^ r = e ^ {-iHt} + O (m ^ 3 t ^ 3/r ^ 2), $ $. errore che può essere reso minore di $ \epsilon $ per qualsiasi $ \epsilon>$0 scegliendo $r $ per la scalabilità come $m ^ {3/2} t ^ {3/2}/\sqrt {\ Epsilon} $.</span><span class="sxs-lookup"><span data-stu-id="44494-117">The simplest such formula, the second order Trotter-Suzuki formula, takes the form $$ U_2(t) = \left(\prod_{j=1}^{m} e^{-iH_j t/2r} \prod_{j=m}^1 e^{-iH_j t/2r}\right)^r = e^{-iHt} + O(m^3 t^3/r^2), $$ the error of which can be made less than $\epsilon$ for any $\epsilon>0$ by choosing $r$ to scale as $m^{3/2}t^{3/2}/\sqrt{\epsilon}$.</span></span>

<span data-ttu-id="44494-118">Anche le formule di ordine superiore, in particolare ($ 2K $) per $k>$0, possono essere costruite in modo ricorsivo: $ $ U_ {2K} (t) = [U_ {2K-2} (s_k \~ t)] ^ 2 U_ {2K-2} ([1-4s_k] t) [U_ {2K-2} (s_k \~ t)] ^ 2 = e ^ {-iHt} + O ((m t) ^ {2K + 1}/r ^ {2K}), $ $ where $s _K = (4-4 ^ {1/(2K-1)}) ^ {-1} $.</span><span class="sxs-lookup"><span data-stu-id="44494-118">Even higher-order formulas, specifically ($2k$)th-order for $k>0$, can be constructed recursively: $$ U_{2k}(t) = [U_{2k-2}(s_k\~ t)]^2 U_{2k-2}([1-4s_k]t) [U_{2k-2}(s_k\~ t)]^2 = e^{-iHt} + O((m t)^{2k+1}/r^{2k}), $$ where $s_k = (4-4^{1/(2k-1)})^{-1}$.</span></span>

<span data-ttu-id="44494-119">Il più semplice è la formula del quarto ordine seguente ($k = $2), originariamente introdotta da Suzuki: $ $ U_4 (t) = [U_2 (s_2 \~ t)] ^ 2 U_2 ([1-4s_2] t) [U_2 (S_2 \~ t)] ^ 2 = e ^ {-iHt} + O (m ^ 5T ^ 5/r ^ 4), $ $ where $s _2 = (4-4 ^ {1/3}) ^ {-1} $.</span><span class="sxs-lookup"><span data-stu-id="44494-119">The simplest is the following fourth order ($k=2$) formula, originally introduced by Suzuki: $$ U_4(t) = [U_2(s_2\~ t)]^2 U_2([1-4s_2]t) [U_2(s_2\~ t)]^2 = e^{-iHt} +O(m^5t^5/r^4), $$ where $s_2 = (4-4^{1/3})^{-1}$.</span></span>
<span data-ttu-id="44494-120">In generale, le formule arbitrariamente più ordinate possono essere costruite in modo analogo; Tuttavia, i costi sostenuti dall'utilizzo di integratori più complessi spesso superano i vantaggi oltre il quarto ordine per la maggior parte dei problemi pratici.</span><span class="sxs-lookup"><span data-stu-id="44494-120">In general, arbitrarily high-order formulas can be similarly constructed; however, the costs incurred from using more complex integrators often outweigh the benefits beyond fourth order for most practical problems.</span></span>

<span data-ttu-id="44494-121">Per far funzionare le strategie precedenti, è necessario disporre di un metodo per simulare un'ampia classe di $e ^ {-iH_j t} $.</span><span class="sxs-lookup"><span data-stu-id="44494-121">In order to make the above strategies work, we need to have a method for simulating a wide class of $e^{-iH_j t}$.</span></span>
<span data-ttu-id="44494-122">La famiglia più semplice di hamiltonians e probabilmente più utile, che potremmo usare qui, sono gli operatori di Pauli.</span><span class="sxs-lookup"><span data-stu-id="44494-122">The simplest family of Hamiltonians, and arguably most useful, that we could use here are Pauli operators.</span></span>
<span data-ttu-id="44494-123">Gli operatori di Pauli possono essere facilmente simulati perché possono essere diagonali usando le operazioni di Clifford, ovvero le porte standard nel quantum computing.</span><span class="sxs-lookup"><span data-stu-id="44494-123">Pauli operators can be easily simulated because they can be diagonalized using Clifford operations (which are standard gates in quantum computing).</span></span>
<span data-ttu-id="44494-124">Inoltre, una volta che sono state spostate in diagonale, è possibile trovare gli autovalori calcolando la parità di qubits su cui agiscono.</span><span class="sxs-lookup"><span data-stu-id="44494-124">Further, once they have been diagonalized, their eigenvalues can be found by computing the parity of the qubits on which they act.</span></span>

<span data-ttu-id="44494-125">Ad esempio, $ $ e ^ {-iX\otimes X t} = (H\otimes H) e ^ {-iZ\otimes Z t} (H\otimes H), $ $ where $ $ e ^ {-i Z \otimes Z t} = \begin{Bmatrix} e ^ {-it} & 0 & 0 & 0 </span><span class="sxs-lookup"><span data-stu-id="44494-125">For example, $$ e^{-iX\otimes X t}= (H\otimes H)e^{-iZ\otimes Z t}(H\otimes H), $$ where $$ e^{-i Z \otimes Z t} = \begin{bmatrix} e^{-it} & 0  & 0  & 0 </span></span>\\\
        <span data-ttu-id="44494-126">0 & e ^ {i t} & 0 & 0 </span><span class="sxs-lookup"><span data-stu-id="44494-126">0 & e^{i t}  & 0 & 0 </span></span>\\\
        <span data-ttu-id="44494-127">0 & 0 & e ^ {it} & 0 </span><span class="sxs-lookup"><span data-stu-id="44494-127">0 & 0 & e^{it} & 0 </span></span>\\\
        <span data-ttu-id="44494-128">0 & 0 & 0 & e ^ {-it} \end{Bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="44494-128">0 & 0 & 0 & e^{-it} \end{bmatrix}.</span></span>
<span data-ttu-id="44494-129">$ $ Here, $e ^ {-iHt} \ket {00} = e ^ {it} \ket {00} $ and $e ^ {-iHt} \ket {01} = e ^ {-it} \ket {01} $, che può essere visto direttamente come conseguenza del fatto che la parità di $0 $ è $0 $, mentre la parità della stringa di bit $1 $ è $1 $.</span><span class="sxs-lookup"><span data-stu-id="44494-129">$$ Here, $e^{-iHt} \ket{00} = e^{it} \ket{00}$ and $e^{-iHt} \ket{01} = e^{-it} \ket{01}$, which can be seen directly as a consequence of the fact that the parity of $00$ is $0$ while the parity of the bit string $01$ is $1$.</span></span>

<span data-ttu-id="44494-130">Gli esponenziali degli operatori di Pauli possono essere implementati direttamente in :::no-loc(Q#)::: usando l' <xref:Microsoft.Quantum.Intrinsic.Exp> operazione:</span><span class="sxs-lookup"><span data-stu-id="44494-130">Exponentials of Pauli operators can be implemented directly in :::no-loc(Q#)::: using the <xref:Microsoft.Quantum.Intrinsic.Exp> operation:</span></span>
```qsharp
    using(qubits = Qubit[2]){
        let pauliString = [PauliX, PauliX];
        let evolutionTime = 1.0;

        // This applies 𝑒^{- 𝑖 𝑋⊗𝑋 𝑡} to qubits 0 and 1.
        Exp(pauliString, - evolutionTime, qubits);
    }
```

<span data-ttu-id="44494-131">Per fermioniche hamiltonians, la [scomposizione Giordania-Wigner](xref:microsoft.quantum.chemistry.concepts.jordanwigner) esegue la mappatura dell'Hamiltoniana in una somma di operatori Pauli.</span><span class="sxs-lookup"><span data-stu-id="44494-131">For Fermionic Hamiltonians, the [Jordan–Wigner decomposition](xref:microsoft.quantum.chemistry.concepts.jordanwigner) conveniently maps the Hamiltonian into a sum of Pauli operators.</span></span>
<span data-ttu-id="44494-132">Questo significa che l'approccio precedente può essere facilmente adattato alla simulazione della chimica.</span><span class="sxs-lookup"><span data-stu-id="44494-132">This means that the above approach can easily be adapted to simulating chemistry.</span></span>
<span data-ttu-id="44494-133">Anziché eseguire manualmente il ciclo su tutti i termini di Pauli nella rappresentazione Jordan-Wigner, di seguito è riportato un semplice esempio di come l'esecuzione di tale simulazione all'interno della chimica.</span><span class="sxs-lookup"><span data-stu-id="44494-133">Rather than manually looping over all Pauli terms in the Jordan-Wigner representation, below is a simple example of how running such a simulation within the chemistry would look.</span></span>
<span data-ttu-id="44494-134">Il punto di partenza è una [codifica Giordania-Wigner](xref:microsoft.quantum.chemistry.concepts.jordanwigner) dell'Hamiltoniana fermioniche, espressa nel codice come un'istanza della `JordanWignerEncoding` classe.</span><span class="sxs-lookup"><span data-stu-id="44494-134">Our starting point is a [Jordan–Wigner encoding](xref:microsoft.quantum.chemistry.concepts.jordanwigner) of the Fermionic Hamiltonian, expressed in code as an instance of the `JordanWignerEncoding` class.</span></span>

```csharp
    // This example uses the following namespaces:
    // using Microsoft.Quantum.Chemistry.OrbitalIntegrals;
    // using Microsoft.Quantum.Chemistry.Fermion;
    // using Microsoft.Quantum.Chemistry.Pauli;
    // using Microsoft.Quantum.Chemistry.QSharpFormat;

    // We create an instance of the `FermionHamiltonian` objecclasst to store the terms.
    var hamiltonian = new OrbitalIntegralHamiltonian(new[] 
    {
        new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123),
        new OrbitalIntegral(new[] { 0, 1 }, 0.456)
    }).ToFermionHamiltonian(IndexConvention.UpDown);

    // We convert this fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = hamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);

    // We now convert this representation into a format consumable by :::no-loc(Q#):::.
    var qSharpData = jordanWignerEncoding.ToQSharpFormat();
```

<span data-ttu-id="44494-135">Questo formato della rappresentazione Giordania-Wigner che può essere utilizzato dagli algoritmi di :::no-loc(Q#)::: simulazione è un tipo definito dall'utente `JordanWignerEncodingData` .</span><span class="sxs-lookup"><span data-stu-id="44494-135">This format of the Jordan–Wigner representation that is consumable by the :::no-loc(Q#)::: simulation algorithms is a user-defined type `JordanWignerEncodingData`.</span></span>
<span data-ttu-id="44494-136">All'interno :::no-loc(Q#)::: di questo formato viene passato a una funzione di praticità `TrotterStepOracle` che restituisce un'evoluzione del tempo di operatore approssimativa usando il Trotter, ovvero Suzuki Integrator, oltre ad altri parametri richiesti per la relativa esecuzione.</span><span class="sxs-lookup"><span data-stu-id="44494-136">Within :::no-loc(Q#):::, this format is passed to a convenience function `TrotterStepOracle` that returns an operator approximating time-evolution using the Trotter—Suzuki integrator, in addition to other parameters required for its run.</span></span>

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single time-step.
using(qubits = Qubit[nQubits]){

    // Apply single step of time-evolution
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

<span data-ttu-id="44494-137">In particolare, questa implementazione applica alcune ottimizzazioni illustrate nella [simulazione della struttura elettronica hamiltonians usando i computer Quantum](https://arxiv.org/abs/1001.3855) e [migliorando gli algoritmi quantistici per la chimica quantistica](https://arxiv.org/abs/1403.1539) per ridurre al minimo il numero di rotazioni singole qubit necessarie, nonché ridurre gli errori di simulazione.</span><span class="sxs-lookup"><span data-stu-id="44494-137">Importantly, this implementation applies some optimizations discussed in [Simulation of Electronic Structure Hamiltonians Using Quantum Computers](https://arxiv.org/abs/1001.3855) and [Improving Quantum Algorithms for Quantum Chemistry](https://arxiv.org/abs/1403.1539) to minimize the number of single-qubit rotations required, as well as reduce simulation errors.</span></span>

## <a name="qubitization"></a><span data-ttu-id="44494-138">Qubitization</span><span class="sxs-lookup"><span data-stu-id="44494-138">Qubitization</span></span>

<span data-ttu-id="44494-139">Qubitization è un approccio alternativo alla simulazione che usa le idee dei percorsi quantistici per simulare la dinamica quantistica.</span><span class="sxs-lookup"><span data-stu-id="44494-139">Qubitization is an alternative approach to simulation that uses ideas from quantum walks to simulate quantum dynamics.</span></span>
<span data-ttu-id="44494-140">Mentre qubitization richiede più qubits delle formule Trotter, il metodo promette la scalabilità ottimale con il tempo di evoluzione e la tolleranza di errore.</span><span class="sxs-lookup"><span data-stu-id="44494-140">While qubitization requires more qubits than Trotter formulas, the method promises optimal scaling with the evolution time and the error tolerance.</span></span>
<span data-ttu-id="44494-141">Per questi motivi, è diventato un metodo favorito per simulare in generale la dinamica Hamiltoniana e per risolvere il problema di struttura elettronica in particolare.</span><span class="sxs-lookup"><span data-stu-id="44494-141">For these reasons it has become a favored method for simulating Hamiltonian dynamics in general, and for solving the electronic structure problem in particular.</span></span>

<span data-ttu-id="44494-142">A livello generale, qubitization esegue questa operazione tramite i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="44494-142">At a high level, qubitization accomplishes this through the following steps.</span></span>
<span data-ttu-id="44494-143">Per prima cosa, lasciare $H = \ sum_j h_j H_j $ per Unity e Hermitiane $H _J $ e $h _J \ge $0.</span><span class="sxs-lookup"><span data-stu-id="44494-143">First, let $H=\sum_j h_j H_j$ for unitary and Hermitian $H_j$ and $h_j\ge 0$.</span></span>
<span data-ttu-id="44494-144">Eseguendo una coppia di riflessioni, qubitization implementa un operatore equivalente a $ $W = e ^ {\pm i \cos ^ {-1} (H/| h | _1)}, $ $ where $ | H | _1 = \ sum_j | h_j | $.</span><span class="sxs-lookup"><span data-stu-id="44494-144">By performing a pair of reflections, qubitization implements an operator that is equivalent to $$W=e^{\pm i \cos^{-1}(H/|h|_1)},$$ where $|h|_1 = \sum_j |h_j|$.</span></span>
<span data-ttu-id="44494-145">Il passaggio successivo prevede la trasformazione degli autovalori dell'operatore Walk da $e ^ {i\pm \cos ^ {-1} (E_k/| h | _1)} $, in cui $E _K $ sono gli autovalori di $H $ a $e ^ {-iE_k t} $.</span><span class="sxs-lookup"><span data-stu-id="44494-145">The next step involves transforming the eigenvalues of the walk operator from $e^{i\pm \cos^{-1}(E_k/|h|_1)}$, where $E_k$ are the eigenvalues of $H$ to $e^{-iE_k t}$.</span></span>
<span data-ttu-id="44494-146">Questa operazione può essere eseguita usando un'ampia gamma di metodi di trasformazione del valore singolare Quantum, inclusa l' [elaborazione del segnale Quantum](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501).</span><span class="sxs-lookup"><span data-stu-id="44494-146">This can be achieved using a variety of quantum singular value transformation methods including [quantum signal processing](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501).</span></span>

<span data-ttu-id="44494-147">In alternativa, se si desiderano solo quantità statiche (ad esempio, l'energia dello stato di base dell'Hamiltoniana), è sufficiente applicare la [stima della fase](xref:microsoft.quantum.libraries.characterization) direttamente a $W $ per stimare l'energia dello stato di base dal risultato prendendo il coseno del risultato.</span><span class="sxs-lookup"><span data-stu-id="44494-147">Alternatively, if only static quantities are desired (such as the ground state energy of the Hamiltonian) then it suffices to apply [phase estimation](xref:microsoft.quantum.libraries.characterization) directly to $W$ to estimate the ground state energy from the result by taking the cosine of the result.</span></span>
<span data-ttu-id="44494-148">Questa operazione è significativa perché consente di eseguire la trasformazione spettrale in modo classico anziché utilizzare un metodo di trasformazione di valori singolari Quantum.</span><span class="sxs-lookup"><span data-stu-id="44494-148">This is significant because it allows the spectral transformation to be performed classically rather than using a quantum singular value transformation method.</span></span>

<span data-ttu-id="44494-149">A un livello più dettagliato, l'implementazione di qubitization richiede due subroutine che forniscono le interfacce per l'hamiltoniana.</span><span class="sxs-lookup"><span data-stu-id="44494-149">On a more detailed level, the implementation of qubitization requires two subroutines that provide the interfaces for the Hamiltonian.</span></span>
<span data-ttu-id="44494-150">A differenza dei metodi Trotter – Suzuki, queste subroutine sono quantum non classico e la loro implementazione richiederà l'uso di logaritmicamente più qubits che sarebbero necessari per una simulazione basata su Trotter.</span><span class="sxs-lookup"><span data-stu-id="44494-150">Unlike Trotter–Suzuki methods, these subroutines are quantum not classical and their implementation will necessitate using logarithmically more qubits than would be required for a Trotter-based simulation.</span></span>

<span data-ttu-id="44494-151">La prima subroutine quantistica utilizzata da qubitization viene chiamata $ \operatorname{Select} $ ed è stata promessa di produrre \begin{Equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}, \end{Equation} in cui si presuppone che ogni $H _j $ sia Hermitiane e unitario.</span><span class="sxs-lookup"><span data-stu-id="44494-151">The first quantum subroutine that qubitization uses is called $\operatorname{Select}$ and it is promised to yield \begin{equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}, \end{equation} where each $H_j$ is assumed to be Hermitian and unitary.</span></span>
<span data-ttu-id="44494-152">Sebbene possa sembrare restrittivo, tenere presente che gli operatori di Pauli sono Hermitiane e Unity, quindi le applicazioni come la simulazione della chimica quantistica rientrano naturalmente in questo Framework.</span><span class="sxs-lookup"><span data-stu-id="44494-152">While this may seem to be restrictive, recall that Pauli operators are Hermitian and unitary and so applications like quantum chemistry simulation naturally fall into this framework.</span></span>
<span data-ttu-id="44494-153">L'operazione $ \operatorname{Select} $, probabilmente sorprendentemente, è in realtà un'operazione di Reflection.</span><span class="sxs-lookup"><span data-stu-id="44494-153">The $\operatorname{Select}$ operation, perhaps surprisingly, is actually a reflection operation.</span></span>
<span data-ttu-id="44494-154">Questa situazione si verifica dal fatto che $ \operatorname{Select} ^ 2 \ KET {j} \ket{\psi} = \ket{j} \ket{\psi} $ poiché ogni $H _j $ è unitario e Hermitiane e pertanto dispone di autovalori $ \pm $1.</span><span class="sxs-lookup"><span data-stu-id="44494-154">This can be seen from the fact that $\operatorname{Select}^2\ket{j} \ket{\psi} = \ket{j} \ket{\psi}$ since each $H_j$ is unitary and Hermitian and thus has eigenvalues $\pm 1$.</span></span>

<span data-ttu-id="44494-155">La seconda subroutine è chiamata $ \operatorname{Prepare} $.</span><span class="sxs-lookup"><span data-stu-id="44494-155">The second subroutine is called $\operatorname{Prepare}$.</span></span>
<span data-ttu-id="44494-156">Mentre l'operazione Select consente di accedere in modo coerente a ognuno dei termini hamiltoniana $H _j $ la subroutine Prep fornisce un metodo per accedere ai coefficienti $h _j $, \begin{Equation} \operatorname{Prepare}\ket {0} = \ sum_j \sqrt{\frac{h_j} {| H | _1}} \ket{j}.</span><span class="sxs-lookup"><span data-stu-id="44494-156">While the select operation provides a means to coherently access each of the Hamiltonian terms $H_j$ the prepare subroutine gives a method for accessing the coefficients $h_j$, \begin{equation} \operatorname{Prepare}\ket{0} = \sum_j \sqrt{\frac{h_j}{|h|_1}}\ket{j}.</span></span>
<span data-ttu-id="44494-157">\end{Equation} quindi, usando un controllo della fase di moltiplicazione controllata, si noterà che $ $ \Lambda\ket {0} ^ {\otimes n} = \begin{cases} \- \ket{x} & \Text{If} x = 0 </span><span class="sxs-lookup"><span data-stu-id="44494-157">\end{equation} Then, by using a multiply controlled phase gate, we see that $$ \Lambda\ket{0}^{\otimes n} = \begin{cases} \-\ket{x} & \text{if } x = 0 </span></span>\\\
        <span data-ttu-id="44494-158">\ket{x} & \Text{otherwise} \end{Cases}.</span><span class="sxs-lookup"><span data-stu-id="44494-158">\ket{x}   & \text{otherwise} \end{cases}.</span></span>
$$

<span data-ttu-id="44494-159">L'operazione $ \operatorname{Prepare} $ non viene utilizzata direttamente in qubitization, bensì viene utilizzata per implementare una reflection sullo stato che $ \operatorname{prepare} $ crea $ $ \begin{align} R &amp; = 1-2 \ operatorName {prepare} \ket {0} \bra \operatorname{prepare} {0} ^ {-1} \\ \\ &amp; = \operatorname{prepare} \Lambda \operatorname{prepare} ^ {-1} .</span><span class="sxs-lookup"><span data-stu-id="44494-159">The $\operatorname{Prepare}$ operation is not used directly in qubitization, but rather is used to implement a reflection about the state that $\operatorname{Prepare}$ creates $$ \begin{align} R &amp; = 1 - 2\operatorname{Prepare} \ket{0}\bra{0} \operatorname{Prepare}^{-1} \\\\ &amp; = \operatorname{Prepare} \Lambda \operatorname{Prepare}^{-1}.</span></span>
<span data-ttu-id="44494-160">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="44494-160">\end{align} $$</span></span>

<span data-ttu-id="44494-161">L'operatore Walk, $W $, può essere espresso in termini di $ \operatorname{Select} $ e $R $ Operations come $ $ W = \operatorname{Select} R, $ $, che può essere visualizzato di nuovo per implementare un operatore equivalente (fino a un isometria) a $e ^ {\pm i \cos ^ {-1} (H/| h | _1)} $.</span><span class="sxs-lookup"><span data-stu-id="44494-161">The walk operator, $W$, can be expressed in terms of the $\operatorname{Select}$ and $R$ operations as $$ W = \operatorname{Select} R, $$ which again can be seen to implement an operator that is equivalent (up to an isometry) to $e^{\pm i \cos^{-1}(H/|h|_1)}$.</span></span>

<span data-ttu-id="44494-162">Queste subroutine sono facili da configurare in :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="44494-162">These subroutines are easy to set up in :::no-loc(Q#):::.</span></span>
<span data-ttu-id="44494-163">Si consideri ad esempio la semplice hamiltoniana qubit trasversale Ising in cui $H = X_1 + X_2 + Z_1 Z_2 $.</span><span class="sxs-lookup"><span data-stu-id="44494-163">As an example, consider the simple qubit transverse-Ising Hamiltonian where $H = X_1 + X_2 + Z_1 Z_2$.</span></span>
<span data-ttu-id="44494-164">In questo caso, :::no-loc(Q#)::: il codice che implementa l'operazione $ \operatorname{SELECT} $ viene richiamato da <xref:Microsoft.Quantum.Canon.MultiplexOperations> , mentre l'operazione $ \operatorname{prepare} $ può essere implementata utilizzando <xref:Microsoft.Quantum.Preparation.PrepareArbitraryState> .</span><span class="sxs-lookup"><span data-stu-id="44494-164">In this case, :::no-loc(Q#)::: code that would implement the $\operatorname{Select}$ operation is invoked by <xref:Microsoft.Quantum.Canon.MultiplexOperations>, whereas the $\operatorname{Prepare}$ operation can be implemented using <xref:Microsoft.Quantum.Preparation.PrepareArbitraryState>.</span></span>
<span data-ttu-id="44494-165">Un esempio che prevede la simulazione del modello Hubbard può essere trovato come [ :::no-loc(Q#)::: esempio](https://github.com/microsoft/Quantum/tree/main/samples/simulation/hubbard).</span><span class="sxs-lookup"><span data-stu-id="44494-165">An example that involves simulating the Hubbard model can be found as a [:::no-loc(Q#)::: sample](https://github.com/microsoft/Quantum/tree/main/samples/simulation/hubbard).</span></span>

<span data-ttu-id="44494-166">La specifica manuale di questi passaggi per i problemi di chimica arbitraria richiede molto lavoro, evitando l'uso della libreria di chimica.</span><span class="sxs-lookup"><span data-stu-id="44494-166">Manually specifying these steps for arbitrary chemistry problems would require much effort, which is avoided using the chemistry library.</span></span>
<span data-ttu-id="44494-167">Analogamente all'algoritmo di simulazione Trotter-Suzuki precedente, `JordanWignerEncodingData` viene passato alla funzione convenience `QubitizationOracle` che restituisce l'operatore Walk, oltre ad altri parametri richiesti per la relativa esecuzione.</span><span class="sxs-lookup"><span data-stu-id="44494-167">Similarly to the Trotter–Suzuki simulation algorithm above, the `JordanWignerEncodingData` is passed to the convenience function `QubitizationOracle` that returns the walk-operator, in addition to other parameters required for its run.</span></span>

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/oneNorm`, where oneNorm is the sum of absolute values of all probabilities in state prepared by `Prepare`.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  QubitizationOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single step of the quantum walk.
using(qubits = Qubit[nQubits]){

    // Apply single step of quantum walk.
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

<span data-ttu-id="44494-168">In particolare, l'implementazione <xref:Microsoft.Quantum.Chemistry.JordanWigner.QubitizationOracle> è applicabile a hamiltonians arbitrario specificati come una combinazione lineare di stringhe Pauli.</span><span class="sxs-lookup"><span data-stu-id="44494-168">Importantly, the implementation <xref:Microsoft.Quantum.Chemistry.JordanWigner.QubitizationOracle> is applicable to arbitrary Hamiltonians specified as a linear combination of Pauli strings.</span></span>
<span data-ttu-id="44494-169">Una versione ottimizzata per le simulazioni di chimica viene richiamata usando <xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedQubitizationOracle> .</span><span class="sxs-lookup"><span data-stu-id="44494-169">A version optimized for chemistry simulations is invoked using <xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedQubitizationOracle>.</span></span>
<span data-ttu-id="44494-170">Questa versione è ottimizzata per ridurre al minimo il numero di controlli T usando le tecniche descritte in [codifica di spettri elettronici nei circuiti quantistici con complessità T lineare](https://arxiv.org/abs/1805.03662).</span><span class="sxs-lookup"><span data-stu-id="44494-170">This version is optimized to minimize the number of T gates using techniques discussed in [Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity](https://arxiv.org/abs/1805.03662).</span></span>
