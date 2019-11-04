---
title: Seconda quantizzazione | Microsoft Docs
description: Seconda documentazione concettuale di quantizzazione
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.secondquantization
ms.openlocfilehash: b3cc7eb8139d2df6e02de371ccf7a423e58ea76d
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2019
ms.locfileid: "73210399"
---
# <a name="second-quantization"></a><span data-ttu-id="06768-103">Seconda quantizzazione</span><span class="sxs-lookup"><span data-stu-id="06768-103">Second Quantization</span></span>

<span data-ttu-id="06768-104">La seconda quantizzazione analizza il problema della struttura elettronica tramite un'altra lente.</span><span class="sxs-lookup"><span data-stu-id="06768-104">Second quantization looks at the problem of electronic structure through a different lens.</span></span>
<span data-ttu-id="06768-105">Anziché assegnare ogni $N _E $ elettroni a uno stato specifico (o orbitale), la seconda quantizzazione tiene traccia di ogni Orbital e archivia se è presente un elettrone presente in ognuno di essi e allo stesso tempo garantisce automaticamente le proprietà di simmetria del funzione Wave corrispondente.</span><span class="sxs-lookup"><span data-stu-id="06768-105">Rather than assigning each of the $N_e$ electrons to a specific state (or orbital), second quantization tracks each orbital and stores whether there is an electron present in each of them and at the same time automatically ensures symmetry properties of the corresponding wave function.</span></span>
<span data-ttu-id="06768-106">Questo è importante perché consente di specificare i modelli di chimica quantistica senza doversi preoccupare dell'anti-symmetrizing lo stato di input (come richiesto per fermioni) e anche perché la seconda quantizzazione consente la simulazione di tali modelli usando un quantum ridotto computer.</span><span class="sxs-lookup"><span data-stu-id="06768-106">This is important because it allows quantum chemistry models to be specified without having to worry about anti-symmetrizing the input state (as is required for fermions) and also because second quantization allows such models to be simulated using small quantum computers.</span></span>

<span data-ttu-id="06768-107">Come esempio della seconda quantizzazione in azione, supponiamo che $ \psi_0\cdots \psi_{N-1} $ sia un set ortonormale di orbitali spaziali.</span><span class="sxs-lookup"><span data-stu-id="06768-107">As an example of second quantization in action, let's assume that $\psi_0\cdots \psi_{N-1}$ are an orthonormal set of spatial orbitals.</span></span>
<span data-ttu-id="06768-108">Queste orbite vengono scelte per rappresentare il sistema nel modo più accurato possibile nel set di base limitato considerato.</span><span class="sxs-lookup"><span data-stu-id="06768-108">These orbitals are chosen to represent the system as accurately as possible within the finite basis set considered.</span></span>
<span data-ttu-id="06768-109">Un esempio comune di tali orbite sono gli orbitali atomici che formano un eigenbasis per l'Atom idrogeno.</span><span class="sxs-lookup"><span data-stu-id="06768-109">A common example of such orbitals are atomic orbitals which form an eigenbasis for the hydrogen atom.</span></span>
<span data-ttu-id="06768-110">Poiché gli elettroni hanno due stati di rotazione, due elettroni possono essere stipati in ogni orbita spaziale.</span><span class="sxs-lookup"><span data-stu-id="06768-110">Because electrons have two spin states, two electrons can be crammed into each such spatial orbital.</span></span>
<span data-ttu-id="06768-111">Ovvero, gli Stati di base validi sono nel formato $ \psi_{0, \uparrow}, \ldots, \psi_{N-1, \uparrow}, \psi_{0, \downarrow}, \ldots, \psi_{N-1, \downarrow} $ where $ \uparrow $ e $ \downarrow $ sono etichette che specificano i due autostati del grado di rotazione di libertà.</span><span class="sxs-lookup"><span data-stu-id="06768-111">That is to say, the valid basis states are of the form $\psi_{0,\uparrow},\ldots,\psi_{N-1,\uparrow}, \psi_{0,\downarrow},\ldots,\psi_{N-1,\downarrow}$ where $\uparrow$ and $\downarrow$ are labels that specify the two eigenstates of the spin degree of freedom.</span></span>
<span data-ttu-id="06768-112">Questo indice combinato di $ (j, \sigma) $ per $ \sigma \in \{\uparrow, \downarrow\}$ è denominato "orbitale", perché archivia sia il grado di libertà spaziale che quello di rotazione.</span><span class="sxs-lookup"><span data-stu-id="06768-112">This combined index of $(j,\sigma)$ for $\sigma \in \{\uparrow,\downarrow\}$ is called a spin-orbital because it stores both the spatial as well as the spin degree of freedom.</span></span>
<span data-ttu-id="06768-113">Nella libreria di chimica, gli orbitali di rotazione vengono archiviati in una struttura di dati `SpinOrbital` e vengono creati come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="06768-113">In the chemistry library, spin-orbitals are stored in a `SpinOrbital` data structure, and are created as follows.</span></span>

```csharp
    // First, we load the namespace containing spin-orbital objects.
    using Microsoft.Quantum.Chemistry.OrbitalIntegrals;

    // First, we assign an orbital index, say `5`. Note that we use 0-indexing,
    // so this is the 6th orbital.
    var orbitalIdx = 5;

    // Second, we assign a spin index, say `Spin.u` for spin up or `Spin.d` for spin down.
    var spin = Spin.d;

    // the spin-orbital (5, ↓) is then
    var spinOrbital = new SpinOrbital(orbitalIdx, spin);

    // A tuple `(int, Spin)` is also implicitly recognized as a spin-orbital.
    (int, Spin) tuple = (orbitalIdx, spin);

    // We explicitly specify the type of `spinOrbital1` to demonstrate
    // the implicit cast to `SpinOrbital`.
    SpinOrbital spinOrbital1 = tuple;
```

<span data-ttu-id="06768-114">Ciò significa che è possibile considerare formalmente la base sia per la parte rotativa che per quella spaziale della funzione Wave come $ \psi_{0} \cdots \psi_{2N-1} $ dove ogni indici è ora un'enumerazione di $ (j, \sigma) $.</span><span class="sxs-lookup"><span data-stu-id="06768-114">This means that we can formally think of the basis for both the spin and spatial part of the wave function as $\psi_{0} \cdots \psi_{2N-1}$ where each of the indices now is an enumeration of a $(j,\sigma)$.</span></span>
<span data-ttu-id="06768-115">Una possibile enumerazione è $g (j, \sigma) = j + N\sigma ' $.</span><span class="sxs-lookup"><span data-stu-id="06768-115">One possible enumeration is $g(j,\sigma) = j+N\sigma'$.</span></span>
<span data-ttu-id="06768-116">Un'altra possibile enumerazione è $h (j, \sigma) = 2 \* j + \sigma $.</span><span class="sxs-lookup"><span data-stu-id="06768-116">Another possible enumeration is $h(j,\sigma) = 2\*j + \sigma$.</span></span>
<span data-ttu-id="06768-117">La libreria Quantum Chemistry può usare tali convenzioni ed è possibile creare un'istanza degli orbitali di rotazione in una codifica di questo tipo come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="06768-117">The quantum chemistry library can use these conventions, and the spin-orbitals in such an encoding can be instantiated as follows.</span></span>

```csharp
    // Let us use the spin orbital created in the previous snippet.
   var spinOrbital = new SpinOrbital(5, Spin.d);

   // Let us set the total number of orbitals to be say, `7`.
   var nOrbitals = 7;

    // This converts a spin-orbital index to a unique integer, in this case `12`,
    // using the formula `g(j,σ)`.
    var integerIndexHalfUp = spinOrbital.ToInt(IndexConvention.HalfUp);

    // This converts a spin-orbital index to a unique integer, in this case `11`,
    // using the formula `h(j,σ)`.
    var integerIndexUpDown = spinOrbital.ToInt(IndexConvention.UpDown);

    // The default conversion uses the formula `h(j,σ)`, in this case `11`.
    var integerIndexDefault = spinOrbital.ToInt();
```

<span data-ttu-id="06768-118">Per i sistemi fermioniche, il principio di esclusione di Pauli impedisce che più elettroni siano presenti nello stesso momento.</span><span class="sxs-lookup"><span data-stu-id="06768-118">For fermionic systems, the Pauli exclusion principle prevents more than one electron from being present in any spin-orbital at the same time.</span></span>
<span data-ttu-id="06768-119">Ciò significa che è possibile scrivere i due stati legali per $ \psi_1 $ come \begin{Equation} \psi_1 \rightarrow \begin{cases} \ket{0}_1 & \Text{if $ \psi_1 $ non è occupato,} </span><span class="sxs-lookup"><span data-stu-id="06768-119">This means that we can write the two legal states for $\psi_1$ as \begin{equation} \psi_1 \rightarrow \begin{cases} \ket{0}_1 & \text{if $\psi_1$ is not occupied,} </span></span>\\\
<span data-ttu-id="06768-120">\ket{1}_1 & \Text{if $ \psi_1 $ occupata.}</span><span class="sxs-lookup"><span data-stu-id="06768-120">\ket{1}_1 & \text{if $\psi_1$ is occupied.}</span></span> <span data-ttu-id="06768-121">\end{Cases} \end{Equation} questa codifica è ideale per i computer Quantum perché significa che è possibile archiviare l'occupazione elettronica come singolo bit di Quantum.</span><span class="sxs-lookup"><span data-stu-id="06768-121">\end{cases} \end{equation} This encoding is great for quantum computers because it means that we can store the electronic occupation as a single quantum bit.</span></span>

<span data-ttu-id="06768-122">Gli Stati di occupazione per le orbite $2N $ rotazioni possono essere archiviati in modo analogo in $2N $ qubits.</span><span class="sxs-lookup"><span data-stu-id="06768-122">The occupation states for the $2N$ spin orbitals can similarly be stored in $2N$ qubits.</span></span>
<span data-ttu-id="06768-123">Ad esempio, se $N = $2, lo stato $ $ \ket{0} \ket{1} \ket{1} \ket{0}, $ $</span><span class="sxs-lookup"><span data-stu-id="06768-123">As an example, if $N=2$ then the state $$ \ket{0} \ket{1} \ket{1} \ket{0}, $$</span></span>

<span data-ttu-id="06768-124">corrisponderebbe alle orbite di rotazione $1 $ e $2 $ occupate con il resto vuoto.</span><span class="sxs-lookup"><span data-stu-id="06768-124">would correspond to spin orbitals $1$ and $2$ being occupied with the remainder empty.</span></span>
<span data-ttu-id="06768-125">Allo stesso modo, lo stato $ $ \ket{0} \equiv \ket{0} _{0} \cdots \ket{0}_ {N-1}, $ $</span><span class="sxs-lookup"><span data-stu-id="06768-125">Similarly, the state $$ \ket{0} \equiv \ket{0}_{0} \cdots \ket{0}_{N-1}, $$</span></span>

<span data-ttu-id="06768-126">non ha elettroni ed è noto come "stato di vuoto".</span><span class="sxs-lookup"><span data-stu-id="06768-126">has no electrons and is known as the 'vacuum state'.</span></span>

<span data-ttu-id="06768-127">Uno splendido effetto collaterale della seconda quantizzazione consiste nel fatto che non è più necessario tenere traccia in modo esplicito dell'anti-simmetria dello stato del quantum.</span><span class="sxs-lookup"><span data-stu-id="06768-127">A beautiful side-effect of second quantization is that we no longer have to explicitly keep track of the anti-symmetry of the quantum state.</span></span>
<span data-ttu-id="06768-128">Questo è dovuto al fatto che, come si vedrà, l'anti-simmetria dello stato rappresenta se stessa tramite le regole anti-commutazione degli operatori che creano ed eliminano le occupazioni elettroniche di un orbitale di rotazione.</span><span class="sxs-lookup"><span data-stu-id="06768-128">This is because, as we will see, the anti-symmetry of the state represents itself instead through the anti-commutation rules of the operators that create and destroy electronic occupations of a spin orbital.</span></span>

## <a name="fermionic-operators"></a><span data-ttu-id="06768-129">Operatori fermioniche</span><span class="sxs-lookup"><span data-stu-id="06768-129">Fermionic operators</span></span>

<span data-ttu-id="06768-130">I due operatori fondamentali che agiscono sui vettori di base quantizzati secondo sono noti come operatori di creazione e annientamento.</span><span class="sxs-lookup"><span data-stu-id="06768-130">The two fundamental operators that act on the second-quantized basis vectors are known as creation and annihilation operators.</span></span>
<span data-ttu-id="06768-131">Questi operatori inseriscono o distruggono gli elettroni in una posizione specifica.</span><span class="sxs-lookup"><span data-stu-id="06768-131">These operators insert or destroy electrons at a particular location.</span></span>
<span data-ttu-id="06768-132">Questi sono indicati $a ^ \dagger_j $ e $a _J $ rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="06768-132">These are denoted $a^\dagger_j$ and $a_j$ respectively.</span></span>

<span data-ttu-id="06768-133">Ad esempio, \begin{align} a ^ \dagger_1 \ket{0}_1 = \ket{1}_1, \quad a ^ \dagger_1 \ket{1}_1 = 0, \quad A_1 \ket{0}_1 = 0, \quad A_1 \ket{1}_1 = \ket{0}_1.</span><span class="sxs-lookup"><span data-stu-id="06768-133">For example, \begin{align} a^\dagger_1 \ket{0}_1 = \ket{1}_1,\quad a^\dagger_1 \ket{1}_1 = 0,\quad a_1 \ket{0}_1 = 0,\quad a_1 \ket{1}_1 = \ket{0}_1.</span></span>
<span data-ttu-id="06768-134">\end{align} si noti che qui $a ^ \dagger_1 \ket{1}_1 = 0 $ e $a _1 \ket{0}_1 $ restituiscono il vettore zero not $ \ket{0}_1 $.</span><span class="sxs-lookup"><span data-stu-id="06768-134">\end{align} Note that here $a^\dagger_1 \ket{1}_1=0$ and $a_1 \ket{0}_1$ yield the zero-vector not $\ket{0}_1$.</span></span>
<span data-ttu-id="06768-135">Tali operatori non sono pertanto né Hermitiane né Unity.</span><span class="sxs-lookup"><span data-stu-id="06768-135">Such operators are therefore neither Hermitian nor unitary.</span></span>
<span data-ttu-id="06768-136">Sono rappresentati gli operatori di creazione e annientamento generali usando il tipo di <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1>.</span><span class="sxs-lookup"><span data-stu-id="06768-136">We represent general creation and annihilation operators using the <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1> type.</span></span>
<span data-ttu-id="06768-137">Ad esempio, un singolo operatore di creazione viene rappresentato come segue.</span><span class="sxs-lookup"><span data-stu-id="06768-137">For instance, a single creation operator is represented as follow.</span></span>

```csharp
    // We load the namespace containing ladder operator objects.
    using Microsoft.Quantum.Chemistry.LadderOperators;

    // Let us use the spin orbital created in the previous snippet.
    var spinOrbitalInteger = new SpinOrbital(5, Spin.d).ToInt();

    // We specify either a creation or annihilation operator using 
    // the enumerable type `RaisingLowering.u` or `RaisingLowering.d`
    // respectively;
    var creationEnum = RaisingLowering.u;

    // The type representing a creation operator is then initialized 
    // as follows. Here, we index these operators with integers.
    // Hence we initialize the generic ladder operator with an
    // integer index type.
    var ladderOperator0 = new LadderOperator<int>(creationEnum, spinOrbitalInteger);

    // An alternate constructor for a LadderOperator instead uses
    // a tuple.
    var ladderOperator1 = new LadderOperator<int>((creationEnum, spinOrbitalInteger));
```

<span data-ttu-id="06768-138">Con tali operatori è inoltre possibile esprimere $ $ \ket{0} \ket{1} \ket{1} \ket{0} = a ^ \dagger_1 a ^ \dagger_2 \ket{0}^ {\otimes 4}.</span><span class="sxs-lookup"><span data-stu-id="06768-138">Also using such operators we can express $$ \ket{0} \ket{1} \ket{1} \ket{0} = a^\dagger_1 a^\dagger_2 \ket{0}^{\otimes 4}.</span></span>
<span data-ttu-id="06768-139">$ $ Questa sequenza di operatori viene costruita all'interno della libreria di simulazione hamiltoniana C# usando codice simile al caso orbitario a rotazione singola considerato sopra sopra:</span><span class="sxs-lookup"><span data-stu-id="06768-139">$$ This sequence of operators would be constructed within the Hamiltonian simulation library using C# code that is similar to the single-spin orbital case considered above above:</span></span>
```csharp
    // We load the namespace containing fermion-related objects.
    using Microsoft.Quantum.Chemistry.Fermion;

    // Let us initialize an array of tuples representing the
    // desired sequence of creation operators.
    var indices = new[] { (RaisingLowering.u, 1), (RaisingLowering.u, 2) };

    // We can convert this array of tuples to a sequence of ladder
    // operators using the `ToLadderSequence()` methods.
    var ladderSequences = indices.ToLadderSequence();

    // Sequences of ladder operators are quite general. For instance,
    // they could be bosonic operators, instead of fermionic operators.
    // We specialize them by constructing a `FermionTerm` representing 
    // a fermion creation operator on the index `2` followed by `1`.
    var fermionTerm = new FermionTerm(ladderSequences);
```

<span data-ttu-id="06768-140">Per un sistema di $k $ fermioni, nella seconda quantizzazione l'azione dell'operatore di creazione $a ^ \dagger_i $ viene fornita da $ $ a ^ \dagger_i \ket{n_1, N_2, \ldots, 0_i, \ldots, n_k} = (-1) ^ {S_i} \ket{n_1, N_2, \ldots, 1_I , \ldots, n_k}, $ $ e $ $ a ^ \dagger_i \ket{n_1, N_2, \ldots, 1_I, \ldots, n_k} = 0, $ $ where $S _i = \sum_{j < i} a ^ \dagger_j a_j $ misura il numero totale di fermioni che si trovano nello stato di una singola particella e che hanno un indice $j < i $.</span><span class="sxs-lookup"><span data-stu-id="06768-140">For a system of $k$ Fermions, in second quantization the action of the creation operator $a^\dagger_i$ is given by $$ a^\dagger_i \ket{n_1, n_2, \ldots, 0_i, \ldots, n_k } = (-1)^{S_i} \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k}, $$ and $$ a^\dagger_i \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k } = 0, $$ where $S_i = \sum_{j<i} a^\dagger_j a_j$ measures the total number of Fermions that are in the state of a single particle and that have an index $j < i$.</span></span>

<span data-ttu-id="06768-141">Un terzo operatore viene spesso utilizzato anche nelle rappresentazioni quantizzate secondo.</span><span class="sxs-lookup"><span data-stu-id="06768-141">A third operator is also often used in second quantized representations.</span></span>
<span data-ttu-id="06768-142">Questo operatore è noto come operatore Number ed è definito da \begin{Equation} n_i = a ^ \dagger_i A_I.</span><span class="sxs-lookup"><span data-stu-id="06768-142">This operator is known as the number operator and is defined by \begin{equation} n_i = a^\dagger_i a_i.</span></span>
<span data-ttu-id="06768-143">\end{Equation} questo operatore conta l'occupazione di un determinato Orbital di rotazione, ovvero \begin{align} n_i \ket{0}_i & = 0 \ NoNumber</span><span class="sxs-lookup"><span data-stu-id="06768-143">\end{equation} This operator counts the occupation of a given spin orbital, which is to say \begin{align} n_i \ket{0}_i &= 0\nonumber</span></span>\\\
<span data-ttu-id="06768-144">n_i \ket{1}_i & = \ket{1}_i.</span><span class="sxs-lookup"><span data-stu-id="06768-144">n_i \ket{1}_i &= \ket{1}_i.</span></span>
<span data-ttu-id="06768-145">\end{align} simile a quello riportato sopra `FermionTerm` esempi, questo operatore Number viene costruito come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="06768-145">\end{align} Similar to the above `FermionTerm` examples, this number operator is constructed as follows.</span></span>
```csharp
    // Let us use a new method to compactly create a sequence of ladder
    // operators. Note that we have ommitted specifying whether the 
    // operators are raising or lowering. In this case, the first half
    // will be raising operators, and the second half will be lowering 
    // operators.
    var indices = new[] { 1, 1 }.ToLadderSequence();

    // We now construct a `FermionTerm` representing an annihilation operator
    // on the index 1 followed by the creation operator on the index 1.
    var fermionTerm0 = new FermionTerm(indices);
```

<span data-ttu-id="06768-146">Una sottigliezza emerge tuttavia quando si usano gli operatori di creazione o annientamento nei sistemi fermioniche.</span><span class="sxs-lookup"><span data-stu-id="06768-146">A subtlety emerges though when using creation or annihilation operators in fermionic systems.</span></span>
<span data-ttu-id="06768-147">È necessario che qualsiasi stato quantum valido sia anti-simmetrico in scambio di etichette.</span><span class="sxs-lookup"><span data-stu-id="06768-147">We require that any valid quantum state is anti-symmetric under exchange of labels.</span></span>
<span data-ttu-id="06768-148">Ciò significa che $ $ a ^ \dagger_2 a ^ \dagger_1 \ket{0} =-a ^ \dagger_1 a ^ \dagger_2 \ket{0}.</span><span class="sxs-lookup"><span data-stu-id="06768-148">This means that $$ a^\dagger_2 a^\dagger_1 \ket{0} = -a^\dagger_1 a^\dagger_2 \ket{0}.</span></span>
<span data-ttu-id="06768-149">Gli operatori $ $ di questo tipo sono detti "anti-commute" e, in generale, per qualsiasi $i, j $ abbiamo \begin{align} a ^ \dagger_i a ^ \dagger_j =-(1-\delta_{i, j}) a ^ \dagger_j a ^ \dagger_i, \quad a ^ \dagger_i a_j = \delta_{i, j}-a_j a ^ \dagger_i.</span><span class="sxs-lookup"><span data-stu-id="06768-149">$$ Such operators are said to 'anti-commute' and in general for any $i, j$ we have that \begin{align} a^\dagger_i a^\dagger_j  = -(1-\delta_{i,j})a^\dagger_j a^\dagger_i,\quad a^\dagger_i a_j =\delta_{i,j} - a_j a^\dagger_i.</span></span>
<span data-ttu-id="06768-150">\end{align} quindi le due istanze di <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> seguenti sono considerate inequivalenti</span><span class="sxs-lookup"><span data-stu-id="06768-150">\end{align} Thus the following two <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> instances are considered inequivalent</span></span>
```csharp
    // Let us initialize an array of tuples representing the
    // desired sequence of creation operators.
    var indices = new[] { (RaisingLowering.u, 1), (RaisingLowering.u, 2) };

    // We now construct a `LadderSequence` representing a creation operator
    // on the index 1 followed by 2, then a term with the reverse ordering.
    var laddderSeqeunce = indices.ToLadderSequence();
    var laddderSeqeunceReversed = indices.Reverse().ToLadderSequence();

    // The following Boolean is `false`.
    var equal = laddderSeqeunce == laddderSeqeunceReversed;
```

<span data-ttu-id="06768-151">Il requisito che ognuno degli operatori di creazione antipermuta significa che l'utilizzo di una seconda rappresentazione quantizzata consente di ovviare alle problematiche poste dall'anti-simmetria di fermioni.</span><span class="sxs-lookup"><span data-stu-id="06768-151">The requirement that each of the creation operators anti-commute means that using a second quantized representation does obviate the challenges faced by the anti-symmetry of Fermions.</span></span>
<span data-ttu-id="06768-152">Al contrario, la sfida riemerge nella definizione degli operatori di creazione.</span><span class="sxs-lookup"><span data-stu-id="06768-152">Instead the challenge re-emerges in our definition of the creation operators.</span></span> 

<span data-ttu-id="06768-153">Utilizzando le regole di anti-commutazione, alcune istanze `LadderSequence` corrispondono effettivamente alla stessa sequenza di operatori fermioniche, a volte fino a un segno meno.</span><span class="sxs-lookup"><span data-stu-id="06768-153">Using the anti-commutation rules, some `LadderSequence` instances actually correspond to the same sequence of fermionic operators, sometimes up to a minus sign.</span></span>
<span data-ttu-id="06768-154">Si consideri, ad esempio, l'Hamiltoniana $a _0 ^ \dagger A_1 ^ \dagger A_1 A_0 =-A_1 ^ \dagger A_0 ^ \dagger A_1 A_0 $.</span><span class="sxs-lookup"><span data-stu-id="06768-154">For instance, consider the Hamiltonian $a_0^\dagger a_1^\dagger a_1 a_0 = - a_1^\dagger a_0^\dagger a_1 a_0$.</span></span>
<span data-ttu-id="06768-155">Questo consente di definire un ordinamento canonico per ogni `FermionTerm`.</span><span class="sxs-lookup"><span data-stu-id="06768-155">This motivates us to define a canonical ordering for every `FermionTerm`.</span></span>
<span data-ttu-id="06768-156">Qualsiasi `FermionTerm` viene inserita automaticamente nell'ordine canonico come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="06768-156">Any `FermionTerm` is automatically put into canonical order as follows.</span></span>
```csharp
    // We now construct two `FermionTerms` that are equivalent with respect to
    // anti-commutation up to a sign change.
    var fermionTerm0 = new FermionTerm(new[] { 0, 1, 1, 0 }.ToLadderSequence());
    var fermionTerm1 = new FermionTerm(new[] { 1, 0, 1, 0 }.ToLadderSequence());

    // The following Boolean is `true`.
    var sequenceEqual = fermionTerm0 == fermionTerm1;

    // The change in sign is not compared above, but is an internally tracked
    // property of `FermionTerm`.
    int sign0 = fermionTerm0.Coefficient;
    var sign1 = fermionTerm1.Coefficient;

    // The following Boolean is `false`.
    var signEqual = sign0 == sign1;
```

## <a name="second-quantized-fermionic-hamiltonian"></a><span data-ttu-id="06768-157">Hamiltoniana fermioniche secondo-quantizzato</span><span class="sxs-lookup"><span data-stu-id="06768-157">Second-Quantized Fermionic Hamiltonian</span></span>

<span data-ttu-id="06768-158">È probabilmente sorprendente che l'Hamiltoniana nei [modelli quantistici per i sistemi elettronici](xref:microsoft.quantum.chemistry.concepts.quantummodels) possa essere scritta in termini di operatori di creazione e annientamento.</span><span class="sxs-lookup"><span data-stu-id="06768-158">It is perhaps unsurprising that the Hamiltonian in [Quantum Models for Electronic Systems](xref:microsoft.quantum.chemistry.concepts.quantummodels) can be written in terms of creation and annihilation operators.</span></span>
<span data-ttu-id="06768-159">In particolare, se $ \psi\_j $ sono le orbite di rotazione che formano la base</span><span class="sxs-lookup"><span data-stu-id="06768-159">In particular, if $\psi\_j$ are the spin orbitals that form the basis then</span></span>

<span data-ttu-id="06768-160">\begin{Equation} \hat{H} = \sum\_{PQ} h\_{PQ} a ^ \dagger\_p a\_q + \frac{1}{2}\sum\_{PQRS} h\_{PQRS} a ^ \dagger\_p a ^ \dagger\_q a\_ra\_s + h\_{\textrm NUC}, \label{EQ: totalha} \end{Equation} dove $h\_{\textrm NUC} $ è l'energia nucleare, ovvero una costante sotto l'approssimazione di Oppenheimer,</span><span class="sxs-lookup"><span data-stu-id="06768-160">\begin{equation} \hat{H} = \sum\_{pq} h\_{pq}a^\dagger\_p a\_q + \frac{1}{2}\sum\_{pqrs} h\_{pqrs}a^\dagger\_p a^\dagger\_q a\_ra\_s +h\_{\textrm nuc},\label{eq:totalHam} \end{equation} where $h\_{\textrm nuc}$ is the nuclear energy (which is a constant under the Born-Oppenheimer approximation) and</span></span>

<span data-ttu-id="06768-161">\begin{align} h\_{PQ} & = \int\_{-\infty} ^ \infty \psi ^\*\_p (x\_1) \left (-\frac{\nabla ^ 2}{2} + V (x\_1) \right) \psi\_q (x\_1) \mathrm{d} ^ 3x @no__ t_9_ 1, \end{align}</span><span class="sxs-lookup"><span data-stu-id="06768-161">\begin{align} h\_{pq} &= \int\_{-\infty}^\infty \psi^\*\_p(x\_1) \left(-\frac{\nabla^2}{2} +V(x\_1)\right)  \psi\_q(x\_1)\mathrm{d}^3x\_1, \end{align}</span></span>

<span data-ttu-id="06768-162">dove $V (x) $ è il potenziale campo medio e</span><span class="sxs-lookup"><span data-stu-id="06768-162">where $V(x)$ is the mean-field potential, and</span></span>

<span data-ttu-id="06768-163">\begin{align} h\_{PQRS} & = \int\_{-\infty} ^ \infty \int\_{-\infty} ^ \infty\psi\_p ^\*(x\_1) \psi\_q ^\*(x\_2) \left (\frac{1}{| X_1-x_2 |} \ Right) \psi\_r (x\_2) \psi\_s (x\_1) \mathrm{d} ^ 3x\_1 \ mathrm {d} ^ 3x\_2. \ label {EQ: integralis} \end{align}</span><span class="sxs-lookup"><span data-stu-id="06768-163">\begin{align} h\_{pqrs} &= \int\_{-\infty}^\infty \int\_{-\infty}^\infty\psi\_p^\*(x\_1)\psi\_q^\*(x\_2) \left(\frac{1}{|x_1-x_2|} \right)\psi\_r(x\_2)\psi\_s(x\_1)\mathrm{d}^3x\_1\mathrm{d}^3x\_2.\label{eq:integrals} \end{align}</span></span>

<span data-ttu-id="06768-164">I termini $h\_{PQ} $ vengono indicati come integrali a un elettrone, perché tutti questi termini coinvolgono solo elettroni singoli e, allo stesso modo, $h\_{PQRS} $ sono integrali a due elettroni.</span><span class="sxs-lookup"><span data-stu-id="06768-164">The terms $h\_{pq}$ are refered to as one-electron integrals because all such terms only involve single electrons and likewise $h\_{pqrs}$ are the two-electron integrals.</span></span>
<span data-ttu-id="06768-165">Sono detti integrali perché il calcolo dei valori di questi coefficienti richiede un integrale.</span><span class="sxs-lookup"><span data-stu-id="06768-165">They are called integrals because computing the values of these coefficients requires an integral.</span></span>
<span data-ttu-id="06768-166">I termini di un elettrone descrivono l'energia cinetica dei singoli elettroni e le loro interazioni con i campi elettrici dei nuclei.</span><span class="sxs-lookup"><span data-stu-id="06768-166">The one electron terms describe the kinetic energy of the individual electrons and their interactions with the electric fields of the nuclei.</span></span>
<span data-ttu-id="06768-167">Gli integrali a due elettroni d'altra parte descrivono le interazioni tra gli elettroni.</span><span class="sxs-lookup"><span data-stu-id="06768-167">The two-electron integrals on the other hand describe the interactions between the electrons.</span></span>

<span data-ttu-id="06768-168">Un'intuizione del significato di questi termini può essere ricavata dagli operatori di creazione e annientamento che comprendono ognuno di essi.</span><span class="sxs-lookup"><span data-stu-id="06768-168">An intuition for what these terms mean can be gleaned from the creation and annihilation operators that comprise each of them.</span></span>
<span data-ttu-id="06768-169">Ad esempio, $h _ {PQ} a ^ \dagger_p a_q $ descrive il salto degli elettroni da Orbital spin $q $ a spin Orbital $p $.</span><span class="sxs-lookup"><span data-stu-id="06768-169">For example, $h_{pq}a^\dagger_p a_q$ describes the electron hopping from spin orbital $q$ to spin orbital $p$.</span></span>
<span data-ttu-id="06768-170">Analogamente, il termine $h _ {PQRS} a ^ \dagger_p a ^ \dagger_q a_r a_s $ (per Distinct $p, q, r, s $) descrive due elettroni negli orbitali della rotazione $r $ e $s $ scattering tra loro e che terminano con le orbite di rotazione $p $ e $q $.</span><span class="sxs-lookup"><span data-stu-id="06768-170">Similarly, the term $h_{pqrs} a^\dagger_p a^\dagger_q a_r a_s$ (for distinct $p,q,r,s$) describes two electrons in spin orbitals $r$ and $s$ scattering off of each other and ending up in spin orbitals $p$ and $q$.</span></span>
<span data-ttu-id="06768-171">Se $r = q $ e $p = s $, $h _ {PRRP} a ^ \dagger_p a ^ \dagger_r a_r A_p = h {PRRP} n_P n_r $ fornisce la penalizzazione energetica associata ai due elettroni che si avvicinano tra loro, ma non descrive un processo dinamico.</span><span class="sxs-lookup"><span data-stu-id="06768-171">If $r=q$ and $p=s$ then $h_{prrp} a^\dagger_p a^\dagger_r a_r a_p = h_{prrp} n_p n_r$ gives the energy penalty associated with the two electrons being near each other, but does not describe a dynamical process.</span></span>

<span data-ttu-id="06768-172">Questi hamiltonians possono essere rappresentati usando la classe `FermionHamiltonian`, che è essenzialmente un elenco contenente tutte le istanze di `FermionTerm` desiderate.</span><span class="sxs-lookup"><span data-stu-id="06768-172">We may represent such Hamiltonians using the `FermionHamiltonian` class, which is essentially a list containing all the desired `FermionTerm` instances.</span></span>
<span data-ttu-id="06768-173">Poiché hamiltonians sono Hermitiane per definizione, i termini vengono indicizzati usando il tipo più specializzato `HermitianFermionTerm` che usa anche la simmetria Hermitiane per verificare se i termini sono equivalenti.</span><span class="sxs-lookup"><span data-stu-id="06768-173">As Hamiltonians are Hermitian by definition, we index terms using the more specialized type `HermitianFermionTerm` that also uses Hermitian symmetry when checking whether terms are equivalent.</span></span>

<span data-ttu-id="06768-174">Si consentirà di creare alcuni esempi esemplificativi.</span><span class="sxs-lookup"><span data-stu-id="06768-174">Let us construct a few illustrative examples.</span></span>
<span data-ttu-id="06768-175">Prendere in considerazione l'Hamiltoniana $ \hat{H} = A_0 ^ \dagger A_1 + A_1 ^ \dagger A_0 $.</span><span class="sxs-lookup"><span data-stu-id="06768-175">Consider the Hamiltonian $\hat{H} = a_0^\dagger a_1 + a_1^\dagger a_0$.</span></span>
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the terms to be added.
    var fermionTerm0 = new FermionTerm(new[] { 1, 0 }.ToLadderSequence());
    var fermionTerm1 = new FermionTerm(new[] { 0, 1 }.ToLadderSequence());

    // These fermion terms are not equal. The following Boolean is `false`.
    var sequenceEqual = fermionTerm0 == fermionTerm1;

    // However, these terms are equal under Hermitian symmetry.
    // We also take the opportunity to demonstrate equivalent constructors
    // for hermitian fermion terms
    var hermitianFermionTerm0 = new HermitianFermionTerm(fermionTerm0);
    var hermitianFermionTerm1 = new HermitianFermionTerm(new[] { 0, 1 });

    // These Hermitian fermion terms are equal. The following Boolean is `true`.
    var hermitianSequenceEqual = hermitianFermionTerm0 == hermitianFermionTerm1;

    // We add the terms to the Hamiltonian with the appropriate coefficient.
    // Note that these terms are identical.
    hamiltonian.Add(hermitianFermionTerm0, 1.0);
    hamiltonian.Add(hermitianFermionTerm1, 1.0);
```
<span data-ttu-id="06768-176">È possibile semplificare questa costruzione usando il fatto che gli operatori hamiltoniana sono operatori Hermitiane.</span><span class="sxs-lookup"><span data-stu-id="06768-176">We may simplify this construction using the fact that Hamiltonian operators are Hermitian operators.</span></span>
<span data-ttu-id="06768-177">Quando si aggiungono termini a hamiltoniana usando `Add`, si presuppone che tutti i termini non hermitiane, ad esempio `fermionTerm0`, siano abbinati al relativo coniugato Hermitiane.</span><span class="sxs-lookup"><span data-stu-id="06768-177">When adding terms to the Hamiltonian using `Add`, any non-Hermitian term such as `fermionTerm0` is assumed to be paired with its Hermitian conjugate.</span></span>
<span data-ttu-id="06768-178">Quindi il frammento di codice seguente rappresenta anche la stessa hamiltoniana:</span><span class="sxs-lookup"><span data-stu-id="06768-178">Thus the following snippet also represents the same Hamiltonian:</span></span>
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the term to be added -- note the doubled coefficient.
    hamiltonian.Add(new HermitianFermionTerm(new[] { 1, 0 }), 2.0);
```

<span data-ttu-id="06768-179">Se si usano le regole di anti-commutazione, alcune `FermionTerm` istanze nell'Hamiltoniana corrispondono in realtà alla stessa sequenza di operatori fermioniche, a volte fino a un segno meno.</span><span class="sxs-lookup"><span data-stu-id="06768-179">Using the anti-commutation rules, some `FermionTerm` instances in the Hamiltonian actually correspond to the same sequence of fermionic operators, sometimes up to a minus sign.</span></span>
<span data-ttu-id="06768-180">Si consideri, ad esempio, l'Hamiltoniana $H = A_0 ^ \dagger A_1 ^ \dagger A_1 A_0-A_1 ^ \dagger A_0 ^ \dagger A_1 A_0 = 2a_0 ^ \dagger A_1 ^ \dagger A_1 A_0 $, ovvero una somma dei termini costruiti sopra.</span><span class="sxs-lookup"><span data-stu-id="06768-180">For instance, consider the Hamiltonian $H=a_0^\dagger a_1^\dagger a_1 a_0 - a_1^\dagger a_0^\dagger a_1 a_0 =2a_0^\dagger a_1^\dagger a_1 a_0$, which is a sum of terms constructed above.</span></span>
<span data-ttu-id="06768-181">Potrebbe non essere sempre chiaro all'utente che si tratta di termini equivalenti, quindi possono essere aggiunti all'Hamiltoniana separatamente.</span><span class="sxs-lookup"><span data-stu-id="06768-181">It may not always be clear to the user that these are equivalent terms, and so they may be added to the Hamiltonian separately.</span></span>
<span data-ttu-id="06768-182">In alternativa, è possibile che si desideri modificare i termini già esistenti nell'Hamiltoniana.</span><span class="sxs-lookup"><span data-stu-id="06768-182">Alternatively, one may be interested in modifying already-existing terms in the Hamiltonian.</span></span>
<span data-ttu-id="06768-183">In questi casi, è possibile combinare termini equivalenti, come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="06768-183">In these cases, we may combine equivalent terms as follows.</span></span>
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We now create two Hermitian fermion terms that are equivalent with respect to
    // anti-commutation and Hermitian symmetry.
    var terms = new[] {
        (new[] { 0, 1, 1, 0 }, 1.0),
        (new[] { 1, 0, 1, 0 }, 1.0) }
    .Select(o => (new HermitianFermionTerm(o.Item1.ToLadderSequence()), o.Item2.ToDoubleCoeff()));

    // Now add `terms` to the Hamiltonian.
    hamiltonian.AddRange(terms);

    // There is only one unique term. `nTerms == 1` is `true`.
    var nTerms = hamiltonian.CountTerms();
```
<span data-ttu-id="06768-184">Combinando i coefficienti dei termini equivalenti, viene ridotto il numero totale di termini nell'Hamiltoniana.</span><span class="sxs-lookup"><span data-stu-id="06768-184">By combining coefficients of equivalent terms, we reduce the total number of terms in the Hamiltonian.</span></span>
<span data-ttu-id="06768-185">In un secondo momento, questo riduce il numero di controlli Quantum necessari per simulare l'hamiltoniana.</span><span class="sxs-lookup"><span data-stu-id="06768-185">Later on, this reduces the number of quantum gates required to simulate the Hamiltonian.</span></span>

### <a name="internal-representation"></a><span data-ttu-id="06768-186">Rappresentazione interna</span><span class="sxs-lookup"><span data-stu-id="06768-186">Internal Representation</span></span>

<span data-ttu-id="06768-187">Un'Hamiltoniana fermioniche con interazioni di uno e due corpi viene rappresentata in una notazione di secondo-quantizzata come</span><span class="sxs-lookup"><span data-stu-id="06768-187">A fermionic Hamiltonian with one- and two-body interactions is represented in second-quantized notation as</span></span>

<span data-ttu-id="06768-188">$ $ \begin{align} H = \sum\_{PQ} h\_{PQ} a ^ \dagger\_{p} a\_{q} + \frac{1}{2}\sum\_{PQRS} h\_{PQRS} a ^ \dagger\_{p} a ^ \dagger\_{q} a @no__ t_10_ {r} a\_{s}.</span><span class="sxs-lookup"><span data-stu-id="06768-188">$$ \begin{align} H=\sum\_{pq}h\_{pq}a^\dagger\_{p}a\_{q}+\frac{1}{2}\sum\_{pqrs}h\_{pqrs}a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}.</span></span>
<span data-ttu-id="06768-189">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="06768-189">\end{align} $$</span></span>

<span data-ttu-id="06768-190">In questa notazione sono presenti al massimo $N ^ 2 + N ^ 4 $ coefficienti.</span><span class="sxs-lookup"><span data-stu-id="06768-190">In this notation, there are at most $N^2+N^4$ coefficients.</span></span>
<span data-ttu-id="06768-191">Tuttavia, molti di questi coefficienti possono essere raccolti in quanto corrispondono allo stesso operatore.</span><span class="sxs-lookup"><span data-stu-id="06768-191">However, many of these coefficients may be collected as they correspond to the same operator.</span></span>
<span data-ttu-id="06768-192">Ad esempio, nel caso in cui $p, q, r, s $ siano indici distinti, è possibile usare le regole di anti-commutazione per mostrare che: $ $ a ^ \dagger\_{p} a ^ \dagger\_{q} a\_{r} a\_{s} =-a ^ \dagger\_{q} a ^ \dagger\_{ p} a\_{r} a\_{s} =-a ^ \dagger\_{p} a ^ \dagger\_{q} a\_{s} a\_{r} = a ^ \dagger\_{q} a ^ \dagger\_{p} a\_{s} a\_{r}.</span><span class="sxs-lookup"><span data-stu-id="06768-192">For instance, in the case where $p,q,r,s$ are distinct indices, we may use the anti-commutation rules to show that: $$ a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s} = -a^\dagger\_{q}a^\dagger\_{p}a\_{r}a\_{s} = -a^\dagger\_{p}a^\dagger\_{q}a\_{s}a\_{r} = a^\dagger\_{q}a^\dagger\_{p}a\_{s}a\_{r}.</span></span>
$$

<span data-ttu-id="06768-193">Inoltre, come $H $ è hermitiane, ogni operatore fermioniche non hermitiane, ad esempio $h\_{PQRS} a ^ \dagger\_{p} a ^ \dagger\_{q} a\_{r} a\_{s} $, ha un coniugato Hermitiane presente anche in $H $.</span><span class="sxs-lookup"><span data-stu-id="06768-193">Furthermore, as $H$ is Hermitian, every non-Hermitian fermionic operator, say $h\_{pqrs}a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}$, has a Hermitian conjugate that is also found in $H$.</span></span> <span data-ttu-id="06768-194">Per indicizzare in modo univoco i gruppi di termini caratterizzati da queste simmetrie, viene definito un ordinamento canonico sugli indici $ (i\_1, \cdots, i\_n, j\_1, \cdots, j\_m) $ di qualsiasi sequenza di $n + m $ fermioniche Operators $a ^ \dagger\_{i\_1} \cdots a ^ \dagger\_{i\_n} a\_{j\_1} \cdots a\_{j\_m} $as segue:</span><span class="sxs-lookup"><span data-stu-id="06768-194">In order to uniquely index groups of terms characterized by these symmetries, we define a canonical ordering on the indices $(i\_1,\cdots,i\_n,j\_1,\cdots,j\_m)$ of any sequence of $n+m$ fermionic operators $a^\dagger\_{i\_1}\cdots a^\dagger\_{i\_n}a\_{j\_1}\cdots a\_{j\_m}$as follows:</span></span>
-   <span data-ttu-id="06768-195">Tutti gli operatori di creazione $a ^ \dagger\_{i\_\cdot} $ vengono posizionati prima di tutti gli operatori di annientamento $a\_{j\_\cdot} $.</span><span class="sxs-lookup"><span data-stu-id="06768-195">All creation operators $a^\dagger\_{i\_\cdot}$ are placed before all annihilation operators $a\_{j\_\cdot}$.</span></span>
-   <span data-ttu-id="06768-196">Tutti gli indici degli operatori di creazione sono ordinati in ordine crescente, ovvero $i\_1 < i\_2 < \cdots < i\_n $.</span><span class="sxs-lookup"><span data-stu-id="06768-196">All creation operator indices are sorted in ascending order, that is $i\_1< i\_2< \cdots < i\_n$.</span></span>
-   <span data-ttu-id="06768-197">Tutti gli indici degli operatori di annientamento sono ordinati in ordine decrescente, ovvero $j\_1 > j\_2 \cdots > j\_m $.</span><span class="sxs-lookup"><span data-stu-id="06768-197">All annihilation operator indices are sorted in descending order, that is $j\_1> j\_2 \cdots > j\_m$.</span></span>
-   <span data-ttu-id="06768-198">L'indice più a sinistra è minore o uguale all'indice più a destra, ovvero $i\_1 \ le j\_m $.</span><span class="sxs-lookup"><span data-stu-id="06768-198">The left-most index is less than or equal to the right-most index, that is $i\_1\le j\_m$.</span></span>

<span data-ttu-id="06768-199">Identifichiamo questo set di indici ordinati in modo canonico come $ $ \begin{align} (i\_1, \cdots, i\_n, j\_1, \cdots, j\_m) \in S\_{n, m}.</span><span class="sxs-lookup"><span data-stu-id="06768-199">Let us identify this set of canonically ordered indices as $$ \begin{align} (i\_1,\cdots,i\_n,j\_1,\cdots,j\_m) \in S\_{n,m}.</span></span>
<span data-ttu-id="06768-200">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="06768-200">\end{align} $$</span></span>

<span data-ttu-id="06768-201">Con questo ordinamento canonico, l'Hamiltoniana fermioniche può essere espressa come $ $ \begin{align} H = \sum\_{(p, q) \in S\_{1,1}} H '\_{PQ} \frac{a ^ \dagger\_{p} a\_{q} + a ^ \dagger\_{q} a\_{ p}}{2}+ \sum\_{(p, q, r, s) \in S\_{2,2}} h '\_{PQRS} \frac{a ^ \dagger\_{p} a ^ \dagger\_{q} a\_{r} a\_{s} + a ^ \dagger\_{s} a ^ \ Dagger\_{r} a\_{q} a\_{p}}{2}, \end{align} $ $ con i integrali a uno e due elettroni appropriati, $h "\_{PQ} $ e $h"\_{PQRS} $ rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="06768-201">With this canonical ordering, the fermionic Hamiltonian may be expressed as $$ \begin{align} H=\sum\_{(p,q)\in S\_{1,1}}h'\_{pq}\frac{a^\dagger\_{p}a\_{q}+a^\dagger\_{q}a\_{p}}{2}+\sum\_{(p,q,r,s)\in S\_{2,2}}h'\_{pqrs}\frac{a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}+a^\dagger\_{s}a^\dagger\_{r}a\_{q}a\_{p}}{2}, \end{align} $$ with suitably adapted one- and two-electron integrals $h'\_{pq}$ and $h'\_{pqrs}$, respectively.</span></span>

