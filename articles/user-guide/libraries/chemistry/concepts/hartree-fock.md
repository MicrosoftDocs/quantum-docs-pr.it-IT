---
title: Teoria Hartree-Fock
description: Informazioni sulla teoria Hartree – Fock, un modo semplice per costruire lo stato iniziale per i sistemi quantistici.
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.hartreefock
ms.openlocfilehash: 6fa63cbe13fe98565ffb42b56f3ade86720cedb3
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275952"
---
# <a name="hartreefock-theory"></a><span data-ttu-id="9815a-103">Hartree – teoria di Fock</span><span class="sxs-lookup"><span data-stu-id="9815a-103">Hartree–Fock Theory</span></span>

<span data-ttu-id="9815a-104">Probabilmente la quantità più importante nella simulazione della chimica quantistica è lo stato di base, ovvero la autovettore di energia minima della matrice hamiltoniana.</span><span class="sxs-lookup"><span data-stu-id="9815a-104">Perhaps the most important quantity in quantum chemistry simulation is the ground state, which is the minimum energy eigenvector of the Hamiltonian matrix.</span></span>
<span data-ttu-id="9815a-105">Ciò è dovuto al fatto che per la maggior parte delle molecole in quantità di temperatura della stanza, ad esempio i tassi di reazione, sono dominate da differenze di energia gratuite tra gli Stati del quantum che descrivono l'inizio e la fine di un passaggio in un percorso di reazione e la temperatura della stanza, ad esempio lo stato</span><span class="sxs-lookup"><span data-stu-id="9815a-105">This is because for most molecules at room temperature quantities such as reaction rates are dominated by free energy differences between quantum states that describe the beginning and end of a step in a reaction pathway and at room temperature such intermediate state are usually ground states.</span></span>
<span data-ttu-id="9815a-106">Mentre lo stato di base è in genere troppo difficile da apprendere (anche con un computer Quantum) perché si tratta di una distribuzione su un numero esponenzialmente elevato di configurazioni.</span><span class="sxs-lookup"><span data-stu-id="9815a-106">While the ground state is typically too hard to learn (even with a quantum computer) because it is a distribution over an exponentially large number of configurations.</span></span>
<span data-ttu-id="9815a-107">Possono essere apprese quantità come l'energia dello stato di base.</span><span class="sxs-lookup"><span data-stu-id="9815a-107">Quantities such as ground state energy can be learned.</span></span>
<span data-ttu-id="9815a-108">Se ad esempio $ \ket{\psi} $ è uno stato quantum puro, \begin{Equation} E = \bra{\psi} \hat{H} \ket{\psi} \end{Equation} fornisce l'energia media del sistema in tale stato.</span><span class="sxs-lookup"><span data-stu-id="9815a-108">For example, if $\ket{\psi}$ is any pure quantum state then \begin{equation} E = \bra{ \psi } \hat{H} \ket{\psi} \end{equation} gives the mean energy that the system has in that state.</span></span>
<span data-ttu-id="9815a-109">Lo stato di base è quindi lo stato che fornisce il valore più piccolo.</span><span class="sxs-lookup"><span data-stu-id="9815a-109">The ground state then is the state that gives the smallest such value.</span></span> <span data-ttu-id="9815a-110">Di conseguenza, la scelta di uno stato che sia il più vicino possibile al vero stato è estremamente importante per stimare l'energia direttamente (come avviene in eigensolvers varianti) o attraverso la stima della fase.</span><span class="sxs-lookup"><span data-stu-id="9815a-110">As a result, choosing a state that is as close as possible to the true ground state is vitally important for estimating the energy either directly (as is done in variational eigensolvers) or through phase estimation.</span></span>

<span data-ttu-id="9815a-111">Hartree: la teoria Fock fornisce un modo semplice per costruire lo stato iniziale per i sistemi quantistici.</span><span class="sxs-lookup"><span data-stu-id="9815a-111">Hartree–Fock theory gives a simple way to construct the initial state for quantum systems.</span></span> <span data-ttu-id="9815a-112">Produce una singola approssimazione del valore del valore di Slater per lo stato di base di un sistema quantico.</span><span class="sxs-lookup"><span data-stu-id="9815a-112">It yields a single Slater-determinant approximation to the ground state of a quantum system.</span></span> <span data-ttu-id="9815a-113">A tal fine, trova una rotazione nello spazio di Fock che riduce al minimo l'energia dello stato di base.</span><span class="sxs-lookup"><span data-stu-id="9815a-113">To that end, it finds a rotation within Fock-space that minimizes the ground state energy.</span></span> <span data-ttu-id="9815a-114">In particolare, per un sistema di $N $ Electrons, il metodo esegue la rotazione \begin{Equation} \ prod_ {j = 0} ^ {N-1} a ^ \ dagger_j \ket {0} \mapsto \ prod_ {j = 0} ^ {n-1} e ^ {u} a ^ \ dagger_j e ^ {-u} \ket {0} \defeq\ prod_ {j = 0} ^ {N-1} \widetilde{a} ^ \ dagger_j \ket {0} , \end{Equation} con un anti-Hermitiane (ad esempio $u =-u ^ \dagger $) Matrix $u = \ Sum_ {PQ} U_ {PQ} a ^ \ dagger_p a_q $.</span><span class="sxs-lookup"><span data-stu-id="9815a-114">In particular, for a system of $N$ electrons the method performs the rotation \begin{equation} \prod_{j=0}^{N-1} a^\dagger_j \ket{0} \mapsto \prod_{j=0}^{N-1} e^{u} a^\dagger_j e^{-u} \ket{0}\defeq\prod_{j=0}^{N-1}  \widetilde{a}^\dagger_j  \ket{0}, \end{equation} with an anti-Hermitian (i.e. $u= -u^\dagger$) matrix $u = \sum_{pq} u_{pq} a^\dagger_p a_q$.</span></span> <span data-ttu-id="9815a-115">Si noti che la matrice $u $ rappresenta le rotazioni orbitali e $ \widetilde{a} ^ \ dagger_j $ e $ \widetilde{a} _j $ rappresentano gli operatori di creazione e annientamento per gli elettroni che occupano le orbite molecolari di Hartree – Fock.</span><span class="sxs-lookup"><span data-stu-id="9815a-115">It should be noted that the matrix $u$ represents the orbital rotations and $\widetilde{a}^\dagger_j$ and $\widetilde{a}_j$ represent creation and annihilation operators for electrons occupying Hartree–Fock molecular spin-orbitals.</span></span>


<span data-ttu-id="9815a-116">Matrix $u $ viene quindi ottimizzato per ridurre al minimo l'energia prevista $ \bra {0} \ prod_ {j = 0} ^ {n-1} \widetilde{a} \_ j H \Prod \_ {k = 0} ^ {n-1} \widetilde{a} ^ \ dagger_k \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="9815a-116">The matrix $u$ is then optimized to minimize the expected energy $\bra{0} \prod_{j=0}^{N-1}  \widetilde{a}\_j  H \prod\_{k=0}^{N-1}  \widetilde{a}^\dagger_k\ket{0}$.</span></span> <span data-ttu-id="9815a-117">Sebbene tali problemi di ottimizzazione possano essere genericamente complessi, in pratica l'algoritmo Hartree-Fock tende a convergere rapidamente a una soluzione quasi ottimale al problema di ottimizzazione, soprattutto per le molecole della shell chiusa nelle geometrie di equilibrio.</span><span class="sxs-lookup"><span data-stu-id="9815a-117">While such optimization problems may be generically hard, in practice the Hartree–Fock algorithm tends to rapidly converge to a near-optimal solution to the optimization problem, especially for closed-shell molecules in the equilibrium geometries.</span></span> <span data-ttu-id="9815a-118">È possibile specificare questi stati come un'istanza dell' `FermionWavefunction` oggetto.</span><span class="sxs-lookup"><span data-stu-id="9815a-118">We may specify these states as an instance of the `FermionWavefunction` object.</span></span> <span data-ttu-id="9815a-119">Ad esempio, viene creata un'istanza dello stato $a ^ \ dagger_ {1} a ^ \ dagger_ {2} a ^ \ dagger_ {6} \ket {0} $ nella libreria di chimica, come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="9815a-119">For instance, the state $a^\dagger_{1}a^\dagger_{2}a^\dagger_{6}\ket{0}$ is instantiated in the chemistry library as follows.</span></span>
```csharp
// Create a list of integer indices of the creation operators
var indices = new[] { 1, 2, 6 };

// Convert the list of indices to a `FermionWavefunction` object.
// In this case, the indices are integers, so we use the `int`
// type specialization.
var wavefunction = new FermionWavefunction<int>(indices);
```
<span data-ttu-id="9815a-120">È anche possibile indicizzare le funzioni Wave con gli `SpinOrbital` indici e quindi convertire questi indici in numeri interi come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="9815a-120">It is also possible to index wave functions with `SpinOrbital` indices, and then convert these indices to integers as follows.</span></span>
```csharp
// Create a list of spin orbital indices of the creation operators
var indices = new[] { (0, Spin.d), (1,Spin.u), (3, Spin.u) };

// Convert the list of indices to a `FermionWavefunction` object.
var wavefunctionSpinOrbital = new FermionWavefunction<SpinOrbital>(indices.ToSpinOrbitals());

// Convert a wavefunction indexed by spin orbitals to
// one indexed by integers
var wavefunctionInt = wavefunctionSpinOrbital.ToIndexing(IndexConvention.UpDown);
```

<span data-ttu-id="9815a-121">La caratteristica più eclatante della teoria Hartree – Fock è che produce uno stato quantico che non ha alcun groviglio tra gli elettroni.</span><span class="sxs-lookup"><span data-stu-id="9815a-121">The most striking feature about Hartree–Fock theory is that it yields a quantum state that has no entanglement between the electrons.</span></span>
<span data-ttu-id="9815a-122">Ciò significa che spesso fornisce una descrizione qualitativa adatta delle proprietà dei sistemi molecolari.</span><span class="sxs-lookup"><span data-stu-id="9815a-122">This means that it often provides a suitable qualitative description of properties of molecular systems.</span></span> 

<span data-ttu-id="9815a-123">Lo stato Hartree-Fock può anche essere ricostruito da un `FermionHamiltonian` come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="9815a-123">The Hartree-Fock state may also be reconstructed from a `FermionHamiltonian`  as follows.</span></span>
```csharp
// We initialize a fermion Hamiltonian.
var fermionHamiltonian = new FermionHamiltonian();

// Create a Hartree-Fock state from the Hamiltonian 
// with, say, `4` occupied spin orbitals.
var wavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons: 4);
```

<span data-ttu-id="9815a-124">Tuttavia, ottenendo risultati accurati, soprattutto per i sistemi fortemente correlati, richiedono gli Stati Quantum che vanno oltre la teoria Hartree – Fock.</span><span class="sxs-lookup"><span data-stu-id="9815a-124">However, obtaining accurate results, especially for strongly correlated systems, necessitate quantum states that go beyond Hartree–Fock theory.</span></span>
