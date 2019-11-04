---
title: Simmetrie di integrali molecolari | Microsoft Docs
description: Documentazione concettuale sulle simmetrie di integrali molecolari
keywords: Non aggiungere o modificare parole chiave senza consultare il proprio champ SEO.
author: nathanwiebe2
ms.author: nawiebe
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.symmetries
ms.openlocfilehash: d539b6339a937c7ab9049e7b50d7852272c25deb
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73185580"
---
## <a name="symmetries-of-molecular-integrals"></a><span data-ttu-id="1df2a-104">Simmetrie di integrali molecolari</span><span class="sxs-lookup"><span data-stu-id="1df2a-104">Symmetries of Molecular Integrals</span></span>

<span data-ttu-id="1df2a-105">La simmetria intrinseca dell'Hamiltoniana di Coulomb, che è l'Hamiltoniana fornita nei [modelli Quantum per i sistemi elettronici](xref:microsoft.quantum.chemistry.concepts.quantummodels), che descrive gli elettroni che interagiscono elettricamente tra loro e con i nuclei, porta a una serie di simmetrie che possono essere sfruttato per comprimere i termini nell'Hamiltoniana.</span><span class="sxs-lookup"><span data-stu-id="1df2a-105">The inherent symmetry of the Coulomb Hamiltonian, which is the Hamiltonian given in [Quantum Models for Electronic Systems](xref:microsoft.quantum.chemistry.concepts.quantummodels), that describes electrons interacting electrically with each other and with the nuclei, leads to a number of symmetries that can be exploited to compress the terms in the Hamiltonian.</span></span>
<span data-ttu-id="1df2a-106">In generale, se non sono state apportate altre ipotesi sulle funzioni di base $ \psi_j $, abbiamo solo \begin{Equation} h {PQRS} = h {qpsr}, \tag{★} \label{EQ: hpqrs} \end{Equation}, che possono essere visualizzate immediatamente dagli integrali nei [modelli Quantum per Sistemi elettronici](xref:microsoft.quantum.chemistry.concepts.quantummodels) quando si nota che i loro valori rimangono identici se $p, q $ e $r, s $ sono intercambiabili da anti-commutation.</span><span class="sxs-lookup"><span data-stu-id="1df2a-106">In general if no further assumptions are made about the basis functions $\psi_j$ then we only have that \begin{equation} h_{pqrs}= h_{qpsr},\tag{★}\label{eq:hpqrs} \end{equation} which can be immediately seen from the integrals in [Quantum Models for Electronic Systems](xref:microsoft.quantum.chemistry.concepts.quantummodels) upon noting that their values remain identical if $p,q$ and $r,s$ are interchanged from anti-commutation.</span></span>

<span data-ttu-id="1df2a-107">Se si presuppone che gli orbitali di rotazione siano di valore reale (come avviene per le basi orbitali di Gauss), è necessario che \begin{Equation} h {PQRS} = h {qpsr} = h {srqp} ★ = h {rspq} = h {rqps} = h {psrq} = h {SPQR} = h {QRsP} .\tag {\label{EQ} hpqrsreal: \end{} equazione} dato questo presupposto, è possibile usare le simmetrie precedenti per ridurre i dati necessari per archiviare gli elementi della matrice dell'Hamiltoniana per un fattore di $8 $; Sebbene in questo modo, l'importazione dei dati in modo coerente risulta leggermente più complessa.</span><span class="sxs-lookup"><span data-stu-id="1df2a-107">If we assume that the spin-orbitals are real-valued (as they are for Gaussian orbital bases) then we further have that \begin{equation} h_{pqrs} = h_{qpsr} = h_{srqp} = h_{rspq}=h_{rqps}=h_{psrq}=h_{spqr}=h_{qrsp}.\tag{★}\label{eq:hpqrsreal} \end{equation} Given such assumptions hold, we can use the above symmetries to reduce the data needed to store the matrix elements of the Hamiltonian by a factor of $8$; although doing so makes importing data in a consistent way slightly more challenging.</span></span>
<span data-ttu-id="1df2a-108">Fortunatamente, la libreria di simulazione hamiltoniana include subroutine che possono essere usate per importare file integrali da [liqui $ | \rangle $](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/) o direttamente da [nwchem](http://www.nwchem-sw.org/index.php/Main_Page).</span><span class="sxs-lookup"><span data-stu-id="1df2a-108">Fortunately the Hamiltonian simulation library has subroutines that can be used to import integral files from either [LIQUI$|\rangle$](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/) or directly from [NWChem](http://www.nwchem-sw.org/index.php/Main_Page).</span></span>

<span data-ttu-id="1df2a-109">Integrali orbitali molecolari (ad esempio, i $h\_{PQ} $ e $h\_{PQRS} $ termini), ad esempio, sono rappresentati usando il tipo di `OrbitalIntegral`, che fornisce una serie di funzioni utili per esprimere questa simmetria.</span><span class="sxs-lookup"><span data-stu-id="1df2a-109">Molecular orbital integrals (i.e. the $h\_{pq}$ and $h\_{pqrs}$ terms) such as these are represented using the `OrbitalIntegral` type, which provides a number of helpful functions to express this symmetry.</span></span>
```csharp
    // Load the namespace containing orbital integral objects.
    using Microsoft.Quantum.Chemistry.OrbitalIntegrals;

    // Create a `OrbitalIntegral` instance to store a one-electron molecular 
    // orbital integral data.
    var oneElectronOrbitalIndices = new[] { 0, 1 };
    var oneElectronCoefficient = 1.0;
    var oneElectronIntegral = new OrbitalIntegral(oneElectronOrbitalIndices, oneElectronCoefficient);

    // This enumerates all one-electron integrals with the same coefficient --
    // an array of equivalent `OrbitalIntegral` instances is generated. In this
    // case, there are two elements.
    var oneElectronIntegrals = oneElectronIntegral.EnumerateOrbitalSymmetries();

    // Create a `OrbitalIntegral` instance to store a two-electron molecular orbital integral data.
    var twoElectronOrbitalIndices = new[] { 0, 1, 2, 3 };
    var twoElectronCoefficient = 0.123;
    var twoElectronIntegral = new OrbitalIntegral(twoElectronOrbitalIndices, twoElectronCoefficient);

    // This enumerates all two-electron integrals with the same coefficient -- 
    // an array of equivalent `OrbitalIntegral` instances is generated. In 
    // this case, there are 8 elements.
    var twoElectronIntegrals = twoElectronIntegral.EnumerateOrbitalSymmetries();
```

<span data-ttu-id="1df2a-110">Oltre a enumerare tutti gli integrali orbitali numericamente identici, è possibile generare un elenco di tutti gli indici Orbit-Orbital contenuti nell'Hamiltoniana rappresentata da un `OrbitalIntegral` come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="1df2a-110">In addition to enumerating over all orbital integrals that are numerically identical, a list of all spin-orbital indices contained in the Hamiltonian represented by an `OrbitalIntegral` may be generated as follows.</span></span>
```csharp
    // Create a `OrbitalIntegral` instance to store a two-electron molecular
    // orbital integral data.
    var twoElectronIntegral = new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123);

    // This enumerates all spin-orbital indices of the `FermionTerm`s in the 
    // Hamiltonian represented by this integral -- this is an array of array 
    // of `SpinOrbital` instances.
    var twoElectronSpinOrbitalIndices = twoElectronIntegral.EnumerateSpinOrbitals();
```
## <a name="constructing-fermionic-hamiltonians-from-molecular-integrals"></a><span data-ttu-id="1df2a-111">Costruzione di fermioniche hamiltonians da integrali molecolari</span><span class="sxs-lookup"><span data-stu-id="1df2a-111">Constructing Fermionic Hamiltonians from Molecular Integrals</span></span>

<span data-ttu-id="1df2a-112">Anziché creare un'Hamiltoniana fermioniche aggiungendo `FermionTerm`s, è possibile aggiungere automaticamente tutti i termini corrispondenti a ogni integrale orbitale.</span><span class="sxs-lookup"><span data-stu-id="1df2a-112">Rather than constructing a Fermionic Hamiltonian by adding `FermionTerm`s, all terms corresponding to each orbital integral may be added automatically.</span></span>
<span data-ttu-id="1df2a-113">Il codice seguente, ad esempio, enumera automaticamente tutte le simmetrie permutative e ordina i termini in ordine canonico:</span><span class="sxs-lookup"><span data-stu-id="1df2a-113">For example, the following code automatically enumerates over all permutational symmetries and orders the terms in canonical order:</span></span> 
```csharp
    // Load the namespace containing fermion objects. This
    // example also uses LINQ queries.
    using Microsoft.Quantum.Chemistry.Fermion;
    using System.Linq;

    // Create a `OrbitalIntegral` instance to store a two-electron molecular 
    // orbital integral data.
    var orbitalIntegral = new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123);

    // Create an `OrbitalIntegralHamiltonian` instance to store the orbital integral
    // terms
    var orbitalIntegralHamiltonian = new OrbitalIntegralHamiltonian();
    orbitalIntegralHamiltonian.Add(orbitalIntegral);

    // Convert the orbital integral representation to a fermion
    // representation. This also requires choosing a convention for 
    // mapping spin orbital indices to integer indices.
    var fermionHamiltonian = orbitalIntegralHamiltonian.ToFermionHamiltonian(IndexConvention.UpDown);

    // Alternatively, one can add orbital integrals directly to a fermion Hamiltonian
    // as follows. This automatically enumerates over all symmetries, and then
    // orders the `HermitianFermionTerm` instances in canonical order. We will need to
    // choose an indexing convention as well.
    fermionHamiltonian.AddRange(orbitalIntegral
        .ToHermitianFermionTerms(0, IndexConvention.UpDown)
        .Select(o => (o.Item1, o.Item2.ToDoubleCoeff())));
```
