---
title: Simmetrie di integrali molecolari | Microsoft Docs
description: Documentazione concettuale sulle simmetrie di integrali molecolari
author: nathanwiebe2
ms.author: nawiebe
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.symmetries
ms.openlocfilehash: 041d600bc8d65e7d67f5fe7d61a69426fb42ffbc
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442389"
---
# <a name="symmetries-of-molecular-integrals"></a>Simmetrie di integrali molecolari

La simmetria intrinseca dell'Hamiltoniana di Coulomb, che è l'Hamiltoniana fornita nei [modelli Quantum per i sistemi elettronici](xref:microsoft.quantum.chemistry.concepts.quantummodels), che descrive gli elettroni che interagiscono elettricamente tra loro e con i nuclei, porta a una serie di simmetrie che possono essere sfruttato per comprimere i termini nell'Hamiltoniana.
In generale, se non sono state apportate altre ipotesi sulle funzioni di base $ \psi_j $, abbiamo solo \begin{Equation} h {PQRS} = h {qpsr}, \tag{★} \label{EQ: hpqrs} \end{Equation}, che possono essere visualizzate immediatamente dagli integrali nei [modelli Quantum per Sistemi elettronici](xref:microsoft.quantum.chemistry.concepts.quantummodels) quando si nota che i loro valori rimangono identici se $p, q $ e $r, s $ sono intercambiabili da anti-commutation.

Se si presuppone che gli orbitali di rotazione siano di valore reale (come avviene per le basi orbitali di Gauss), è necessario che \begin{Equation} h {PQRS} = h {qpsr} = h {srqp} ★ = h {rspq} = h {rqps} = h {psrq} = h {SPQR} = h {QRsP} .\tag {\label{EQ} hpqrsreal: \end{} equazione} dato questo presupposto, è possibile usare le simmetrie precedenti per ridurre i dati necessari per archiviare gli elementi della matrice dell'Hamiltoniana per un fattore di $8 $; Sebbene in questo modo, l'importazione dei dati in modo coerente risulta leggermente più complessa.
Fortunatamente, la libreria di simulazione hamiltoniana include subroutine che possono essere usate per importare file integrali da [liqui $ | \rangle $](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/) o direttamente da [nwchem](http://www.nwchem-sw.org/index.php/Main_Page).

Integrali orbitali molecolari (ad esempio, i $h\_{PQ} $ e $h\_{PQRS} $ termini), ad esempio, sono rappresentati usando il tipo di `OrbitalIntegral`, che fornisce una serie di funzioni utili per esprimere questa simmetria.
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

Oltre a enumerare tutti gli integrali orbitali numericamente identici, è possibile generare un elenco di tutti gli indici Orbit-Orbital contenuti nell'Hamiltoniana rappresentata da un `OrbitalIntegral` come indicato di seguito.
```csharp
    // Create a `OrbitalIntegral` instance to store a two-electron molecular
    // orbital integral data.
    var twoElectronIntegral = new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123);

    // This enumerates all spin-orbital indices of the `FermionTerm`s in the 
    // Hamiltonian represented by this integral -- this is an array of array 
    // of `SpinOrbital` instances.
    var twoElectronSpinOrbitalIndices = twoElectronIntegral.EnumerateSpinOrbitals();
```
## <a name="constructing-fermionic-hamiltonians-from-molecular-integrals"></a>Costruzione di fermioniche hamiltonians da integrali molecolari

Anziché creare un'Hamiltoniana fermioniche aggiungendo `FermionTerm`s, è possibile aggiungere automaticamente tutti i termini corrispondenti a ogni integrale orbitale.
Il codice seguente, ad esempio, enumera automaticamente tutte le simmetrie permutative e ordina i termini in ordine canonico: 
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
