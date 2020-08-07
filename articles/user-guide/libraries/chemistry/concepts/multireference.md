---
title: Funzioni d'onda correlate
description: Informazioni sulle correlazioni dinamiche e non dinamiche in d'onda usando la libreria Microsoft Quantum Chemistry.
author: guanghaolow
ms.author: gulow@microsoft.com
ms.date: 05/28/2019
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.multireference
no-loc:
- Q#
- $$v
ms.openlocfilehash: 0066d676205901d4f2d41538684f9ba57407eb82
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869563"
---
# <a name="correlated-wavefunctions"></a><span data-ttu-id="6d4ff-103">Funzioni d'onda correlate</span><span class="sxs-lookup"><span data-stu-id="6d4ff-103">Correlated wavefunctions</span></span>

<span data-ttu-id="6d4ff-104">Per molti sistemi, in particolare quelli che si avvicinano alla geometria di equilibrio, [Hartree – Fock](xref:microsoft.quantum.chemistry.concepts.hartreefock) Theory fornisce una descrizione qualitativa delle proprietà molecolari tramite uno stato di riferimento con un solo determinante.</span><span class="sxs-lookup"><span data-stu-id="6d4ff-104">For many systems, particularly those near the equilibrium geometry, [Hartree–Fock](xref:microsoft.quantum.chemistry.concepts.hartreefock) theory provides a qualitative description of molecular properties through a single-determinant reference state.</span></span> <span data-ttu-id="6d4ff-105">Tuttavia, per ottenere un'accuratezza quantitativa, è necessario considerare anche gli effetti di correlazione.</span><span class="sxs-lookup"><span data-stu-id="6d4ff-105">However, in order to achieve quantitative accuracy, one must also consider correlation effects.</span></span> 

<span data-ttu-id="6d4ff-106">In questo contesto è importante dinstinguish tra correlazioni dinamiche e non dinamiche.</span><span class="sxs-lookup"><span data-stu-id="6d4ff-106">In this context, it is important to dinstinguish between dynamic and non-dynamic correlations.</span></span>
<span data-ttu-id="6d4ff-107">Le correlazioni dinamiche derivano dalla tendenza degli elettroni a distinguersi, ad esempio a causa della repulsione interelettronica.</span><span class="sxs-lookup"><span data-stu-id="6d4ff-107">Dynamical correlations arise from the tendency of electrons to stay apart, such as due to interelectronic repulsion.</span></span> <span data-ttu-id="6d4ff-108">Questo effetto può essere modellato considerando le eccitazioni di elettroni dallo stato di riferimento.</span><span class="sxs-lookup"><span data-stu-id="6d4ff-108">This effect can be modelled by considering excitations of electrons out of the reference state.</span></span> <span data-ttu-id="6d4ff-109">Le correlazioni non dinamiche si verificano quando il zero è dominato da due o più configurazioni in ordine zero, anche per ottenere solo una descrizione qualitativa del sistema.</span><span class="sxs-lookup"><span data-stu-id="6d4ff-109">Non-dynamic correlations arise when the wavefunction is dominated by two or more configurations at zeroth order, even to achieve only a qualitative description of the system.</span></span>
<span data-ttu-id="6d4ff-110">Questa operazione richiede una superposizione dei fattori determinanti ed è un esempio di zero a più riferimenti.</span><span class="sxs-lookup"><span data-stu-id="6d4ff-110">This necessitates a superposition of determinants and is an example of a multireference wavefunction.</span></span>

<span data-ttu-id="6d4ff-111">La libreria di chimica fornisce un modo per specificare un zero di ordine zero per il problema di più riferimenti come una superposizione dei fattori determinanti.</span><span class="sxs-lookup"><span data-stu-id="6d4ff-111">The chemistry library provides a way to specify a zeroth order wavefunction for the multireference problem as a superposition of determinants.</span></span> <span data-ttu-id="6d4ff-112">Questo approccio, che viene chiamato d'onda multireference di tipo sparse, è efficace quando solo pochi componenti sono sufficienti per specificare la superposizione.</span><span class="sxs-lookup"><span data-stu-id="6d4ff-112">This approach, which we call sparse multireference wavefunctions, is effective when only a few components suffice to specify the superposition.</span></span> <span data-ttu-id="6d4ff-113">La libreria fornisce anche un metodo per includere le correlazioni dinamiche sopra un riferimento a un singolo determinante tramite l'unità di aggregazione del cluster unitario unitario generalizzato.</span><span class="sxs-lookup"><span data-stu-id="6d4ff-113">The library also provides a method to include dynamic correlations on top of a single-determinant reference via the generalized unitary coupled-cluster ansatz.</span></span> <span data-ttu-id="6d4ff-114">Inoltre, costruisce anche circuiti Quantum che generano questi stati in un computer Quantum.</span><span class="sxs-lookup"><span data-stu-id="6d4ff-114">Furthermore, it also constructs quantum circuits that generate these states on a quantum computer.</span></span> <span data-ttu-id="6d4ff-115">Questi Stati possono essere specificati nello [schema Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)e forniscono anche la funzionalità per specificare manualmente questi stati tramite la libreria di chimica.</span><span class="sxs-lookup"><span data-stu-id="6d4ff-115">These states may be specified in the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), and we also provide the functionality to manually specify these states through the chemistry library.</span></span>

## <a name="sparse-multi-reference-wavefunction"></a><span data-ttu-id="6d4ff-116">Zero a più riferimenti sparse</span><span class="sxs-lookup"><span data-stu-id="6d4ff-116">Sparse multi-reference wavefunction</span></span>
<span data-ttu-id="6d4ff-117">Uno stato a più riferimenti $ \ket{\ psi_ {\rm {MCSCF}}} $ può essere specificato in modo esplicito come combinazione lineare di $N $-Electron Slater determininants.</span><span class="sxs-lookup"><span data-stu-id="6d4ff-117">A multi-reference state $\ket{\psi_{\rm {MCSCF}}}$ may be specified explicitly as a linear combination of $N$-electron Slater determininants.</span></span>
<span data-ttu-id="6d4ff-118">\begin{align} \ket{\ psi_ {\rm {MCSCF}}} \propto \ sum_ {i_1 < i_2 < \cdots < i_N} \ lambda_ {i_1, i_2, \cdots, i_N} a ^ \ dagger_ {i_1} a ^ \ dagger_ {i_2} \cdots a ^ \ dagger_ {i_N} \ket {0} .</span><span class="sxs-lookup"><span data-stu-id="6d4ff-118">\begin{align} \ket{\psi_{\rm {MCSCF}}} \propto \sum_{i_1 < i_2 < \cdots < i_N} \lambda_{i_1,i_2,\cdots,i_N} a^\dagger_{i_1}a^\dagger_{i_2}\cdots a^\dagger_{i_N}\ket{0}.</span></span>
<span data-ttu-id="6d4ff-119">\end{align} ad esempio, lo stato $ \propto (0.1 a ^ \ dagger_1a ^ \ dagger_2a ^ \ dagger_6-0,2 a ^ \ dagger_2a ^ \ dagger_1a ^ \ dagger_5) \ket {0} $ può essere specificato nella libreria di chimica come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="6d4ff-119">\end{align} For example, the state $\propto(0.1 a^\dagger_1a^\dagger_2a^\dagger_6 - 0.2 a^\dagger_2a^\dagger_1a^\dagger_5)\ket{0}$ may be specified in the chemistry library as follows.</span></span>
```csharp
// Create a list of tuples where the first item of each 
// tuple are indices to the creation operators acting on the
// vacuum state, and the second item is the coefficient
// of that basis state.
var superposition = new[] {
    (new[] {1, 2, 6}, 0.1),
    (new[] {2, 1, 5}, -0.2) };

// Create a fermion wavefunction object that represents the superposition.
var wavefunction = new FermionWavefunction<int>(superposition);
```
<span data-ttu-id="6d4ff-120">Questa rappresentazione esplicita dei componenti di superposizione è efficace quando è necessario specificare solo alcuni componenti.</span><span class="sxs-lookup"><span data-stu-id="6d4ff-120">This explicit representation of the superposition components is effective when only a few components need to be specified.</span></span> <span data-ttu-id="6d4ff-121">Si consiglia di evitare di utilizzare questa rappresentazione quando sono necessari molti componenti per acquisire accuratamente lo stato desiderato.</span><span class="sxs-lookup"><span data-stu-id="6d4ff-121">One should avoid using this representation when many components are required to accurately capture the desired state.</span></span> <span data-ttu-id="6d4ff-122">Il motivo è il costo del controllo del circuito quantistico che prepara questo stato in un computer Quantum, che scala almeno in modo lineare con il numero di componenti di superposizione e al massimo quadratico con la regola unica delle ampiezze della superposizione.</span><span class="sxs-lookup"><span data-stu-id="6d4ff-122">The reason for this is the gate cost of quantum circuit that prepares this state on a quantum computer, which scales at least linearly with the number of superposition components, and at most quadratically with the one-norm of the superposition amplitudes.</span></span>

## <a name="unitary-coupled-cluster-wavefunction"></a><span data-ttu-id="6d4ff-123">Unitario abbinato-cluster zero</span><span class="sxs-lookup"><span data-stu-id="6d4ff-123">Unitary coupled-cluster wavefunction</span></span>
<span data-ttu-id="6d4ff-124">È anche possibile specificare un Unity-cluster zero $ \ket{\ psi_ {\rm {UCC}}} $ usando la libreria di farmacie.</span><span class="sxs-lookup"><span data-stu-id="6d4ff-124">It is also possible to specify a unitary coupled-cluster wavefunction $\ket{\psi_{\rm {UCC}}}$ using the chemistery library.</span></span> <span data-ttu-id="6d4ff-125">In questa situazione è presente uno stato di riferimento con un solo determinante, ad \ket{\ psi_ {\rm{SCF}}} $.</span><span class="sxs-lookup"><span data-stu-id="6d4ff-125">In this situation, we have a single-determinant reference state, say, $\ket{\psi_{\rm{SCF}}}$.</span></span> <span data-ttu-id="6d4ff-126">I componenti del zero del cluster unitario abbinato vengono quindi specificati in modo implicito tramite un operatore unitario che agisce su uno stato di riferimento.</span><span class="sxs-lookup"><span data-stu-id="6d4ff-126">The components of the unitary coupled-cluster wavefunction are then specified implicity through a unitary operator acting on a reference state.</span></span>
<span data-ttu-id="6d4ff-127">Questo operatore unitario viene comunemente scritto come $e ^ {T-T ^ \dagger} $, dove $T-T ^ \dagger $ è l'operatore cluster anti-Hermitiane.</span><span class="sxs-lookup"><span data-stu-id="6d4ff-127">This unitary operator is commonly written as $e^{T-T^\dagger}$, where $T-T^\dagger$ is the anti-Hermitian cluster operator.</span></span> <span data-ttu-id="6d4ff-128">Quindi \begin{align} \ket{\ psi_ {\rm {UCC}}} = e ^ {T-T ^ \dagger}\ket{\ psi_ {\rm{SCF}}}.</span><span class="sxs-lookup"><span data-stu-id="6d4ff-128">Thus \begin{align} \ket{\psi_{\rm {UCC}}} = e^{T-T^\dagger}\ket{\psi_{\rm{SCF}}}.</span></span>
<span data-ttu-id="6d4ff-129">\end{align}</span><span class="sxs-lookup"><span data-stu-id="6d4ff-129">\end{align}</span></span>

<span data-ttu-id="6d4ff-130">È anche comune suddividere l'operatore cluster $T = T_1 + T_2 + \cdots $ in parti, dove ogni parte $T _j $ contiene $j termini $-Body.</span><span class="sxs-lookup"><span data-stu-id="6d4ff-130">It is also common to split the cluster operator $T = T_1 + T_2 + \cdots$ into parts, where each part $T_j$ contains $j$-body terms.</span></span> <span data-ttu-id="6d4ff-131">In teoria dei cluster abbinati, l'operatore del cluster a corpo singolo (Single) ha il formato \begin{align} T_1 = \ sum_ {PQ} T ^ {p} _ {q} a ^ \ dagger_p a_q, \end{align}</span><span class="sxs-lookup"><span data-stu-id="6d4ff-131">In generalized coupled-cluster theory, the one-body cluster operator (singles) is of the form \begin{align} T_1 = \sum_{pq}t^{p}_{q} a^\dagger_p a_q, \end{align}</span></span>

<span data-ttu-id="6d4ff-132">e l'operatore cluster a due corpo (Double) ha il formato \begin{align} T_2 = \ sum_ {PQRS} T ^ {PQ} _ {RS} a ^ \ dagger_p a ^ \ dagger_q a_r a_s.</span><span class="sxs-lookup"><span data-stu-id="6d4ff-132">and two-body cluster operator (doubles) is of the form \begin{align} T_2 = \sum_{pqrs}t^{pq}_{rs} a^\dagger_p a^\dagger_q a_r a_s.</span></span>
<span data-ttu-id="6d4ff-133">\end{align}</span><span class="sxs-lookup"><span data-stu-id="6d4ff-133">\end{align}</span></span>

<span data-ttu-id="6d4ff-134">Sono possibili termini di ordine superiore (triple, quadruple e così via), ma non supportati attualmente dalla libreria di chimica.</span><span class="sxs-lookup"><span data-stu-id="6d4ff-134">Higher-order terms (triples, quadruples, etc.) are possible, but not currently supported by the chemistry library.</span></span>

<span data-ttu-id="6d4ff-135">Ad esempio, Let $ \ket{\ psi_ {\rm{SCF}}} = a ^ \ dagger_1 a ^ \ dagger_2 \ket {0} $ e let $T = 0,123 a ^ \ dagger_0 A_1 + 0,456 a ^ \ dagger_0a ^ \ dagger_3 A_1 A_2-0,789 a ^ \ dagger_3a ^ \ dagger_2 A_1 A_0 $.</span><span class="sxs-lookup"><span data-stu-id="6d4ff-135">For example, let $\ket{\psi_{\rm{SCF}}} = a^\dagger_1 a^\dagger_2\ket{0}$, and let $T= 0.123 a^\dagger_0 a_1 + 0.456 a^\dagger_0a^\dagger_3 a_1 a_2 - 0.789 a^\dagger_3a^\dagger_2 a_1 a_0$.</span></span> <span data-ttu-id="6d4ff-136">Viene quindi creata un'istanza di questo stato nella libreria di chimica come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="6d4ff-136">Then this state is instantiated in the chemistry library as follows.</span></span>
```csharp
// Create a list of indices of the creation operators
// for the single-reference state
var reference = new[] { 1, 2 };

// Create a list describing the cluster operator
// The first half of each list of integers will be
// associated with the creation operators, and
// the second half with the annihilation operators.
var clusterOperator = new[]
{
    (new [] {0, 1}, 0.123),
    (new [] {0, 3, 1, 2}, 0.456),
    (new [] {3, 2, 1, 0}, 0.789)
};

// Create a fermion wavefunction object that represents the 
// unitary coupled-cluster wavefunction. It is assumed implicity
// that the exponent of the unitary coupled-cluster operator
// is the cluster operator minus its Hermitian conjugate.
var wavefunction = new FermionWavefunction<int>(reference, clusterOperator);
```

<span data-ttu-id="6d4ff-137">Il convervation di selezione può essere reso esplicito specificando invece gli `SpinOrbital` indici invece degli indici Integer.</span><span class="sxs-lookup"><span data-stu-id="6d4ff-137">Spin convervation may be made explicit by instead specifying `SpinOrbital` indices instead of integer indices.</span></span> <span data-ttu-id="6d4ff-138">Ad esempio, Let $ \ket{\ psi_ {\rm{SCF}}} = a ^ \ dagger_ {1, \uparrow} a ^ \ dagger_ {2, \downarrow}\ket {0} $ e let $T = 0,123 a ^ \ dagger_ {0, \uparrow} A_ {1, \uparrow} + 0,456 a ^ \ dagger_ {0, \uparrow} a ^ \ dagger_ {3, \downarrow} A_ {1, \uparrow} A_ {2, \downarrow}-0,789 a ^ \ dagger_ {3, \uparrow} a ^ \ dagger_ {2, \uparrow} A_ {1, \uparrow} A_ {0, \uparrow} $ be spin convserving.</span><span class="sxs-lookup"><span data-stu-id="6d4ff-138">For example, let $\ket{\psi_{\rm{SCF}}} = a^\dagger_{1,\uparrow} a^\dagger_{2, \downarrow}\ket{0}$, and let $T= 0.123 a^\dagger_{0, \uparrow} a_{1, \uparrow} + 0.456 a^\dagger_{0, \uparrow} a^\dagger_{3, \downarrow} a_{1, \uparrow} a_{2, \downarrow} - 0.789 a^\dagger_{3,\uparrow} a^\dagger_{2,\uparrow} a_{1,\uparrow} a_{0, \uparrow}$ be spin convserving.</span></span> <span data-ttu-id="6d4ff-139">Viene quindi creata un'istanza di questo stato nella libreria di chimica come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="6d4ff-139">Then this state is instantiated in the chemistry library as follows.</span></span>
```csharp
// Create a list of indices of the creation operators
// for the single-reference state
var reference = new[] { (1, Spin.u), (2, Spin.d) }.ToSpinOrbitals();

// Create a list describing the cluster operator
// The first half of each list of integers will be
// associated with the creation operators, and
// the second half with the annihilation operators.
var clusterOperator = new[]
{
    (new [] {(0, Spin.u), (1, Spin.u)}, 0.123),
    (new [] {(0, Spin.u), (3, Spin.d), (1, Spin.u), (2, Spin.d)}, 0.456),
    (new [] {(3, Spin.u), (2, Spin.u), (1, Spin.u), (0, Spin.u)}, 0.789)
}.Select(o => (o.Item1.ToSpinOrbitals(), o.Item2);

// Create a fermion wavefunction object that represents the 
// unitary coupled-cluster wavefunction. It is assumed implicity
// that the exponent of the unitary coupled-cluster operator
// is the cluster operator minus its Hermitian conjugate.
var wavefunctionSpinOrbital = new FermionWavefunction<SpinOrbital>(reference, clusterOperator);

// Convert the wavefunction indexed by spin-orbitals to one indexed
// by integers
var wavefunctionInteger = wavefunctionSpinOrbital.ToIndexing(IndexConvention.UpDown);
```

<span data-ttu-id="6d4ff-140">Viene inoltre fornita una funzione di praticità che enumera tutti gli operatori di cluster che si Conversano alla rotazione che annientano solo le orbite di rotazione occupate e si eccita solo per gli orbitali di rotazione non occupate.</span><span class="sxs-lookup"><span data-stu-id="6d4ff-140">We also provide a convenience function that enumerates over all spin-conversing cluster operators that annihilate only occupied spin-orbitals and excite to only unoccupied spin-orbitals.</span></span>
```csharp
// Create a list of indices of the creation operators
// for the single-reference state
var reference = new[] { (1, Spin.u), (2, Spin.d) }.ToSpinOrbitals();

// Generate all spin-conversing excitations from spin-orbitals 
// occupied by the reference state to virtual orbitals.
var generatedExcitations = reference.CreateAllUCCSDSingletExcitations(nOrbitals: 3).Excitations;

// This is the list of expected spin-consvering excitations
var expectedExcitations = new[]
{
    new []{ (0, Spin.u), (1,Spin.u)},
    new []{ (2, Spin.u), (1,Spin.u)},
    new []{ (0, Spin.d), (2,Spin.d)},
    new []{ (1, Spin.d), (2,Spin.d)},
    new []{ (0, Spin.u), (0, Spin.d), (2, Spin.d), (1,Spin.u)},
    new []{ (0, Spin.u), (1, Spin.d), (2, Spin.d), (1,Spin.u)},
    new []{ (0, Spin.d), (2, Spin.u), (2, Spin.d), (1,Spin.u)},
    new []{ (1, Spin.d), (2, Spin.u), (2, Spin.d), (1,Spin.u)}
}.Select(o => new IndexOrderedSequence<SpinOrbital>(o.ToLadderSequence()));

// The following two assertions are true, and verify that the generated 
// excitations exactly match the expected excitations.
var bool0 = generatedExcitations.Keys.All(expectedExcitations.Contains);
var bool1 = generatedExcitations.Count() == expectedExcitations.Count();
```
