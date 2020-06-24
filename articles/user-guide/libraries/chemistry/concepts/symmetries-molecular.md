---
title: Simmetrie di integrali molecolari
description: "Informazioni sull'uso del tipo Q # OrbitalIntegral per enumerare le simmetrie molecolari."
author: nathanwiebe2
ms.author: nawiebe
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.symmetries
ms.openlocfilehash: b7e7b79af17af544c4a784eff08500498afc9f67
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274732"
---
# <a name="symmetries-of-molecular-integrals"></a>Simmetrie di integrali molecolari

La simmetria intrinseca dell'Hamiltoniana di Coulomb, che è l'Hamiltoniana fornita nei [modelli Quantum per i sistemi elettronici](xref:microsoft.quantum.chemistry.concepts.quantummodels), che descrive gli elettroni che interagiscono elettricamente tra loro e con i nuclei, conduce a diverse simmetrie che possono essere sfruttate per comprimere i termini nell'Hamiltoniana.
In generale, se non vengono apportate altre ipotesi sulle funzioni di base $ \ psi_j $, abbiamo solo \begin{Equation} h_ {PQRS} = h_ {qpsr}, \tag{★} \label{EQ: hpqrs} \end{Equation}, che può essere visualizzato immediatamente dagli integrali nei [modelli quantistici per i sistemi elettronici](xref:microsoft.quantum.chemistry.concepts.quantummodels) quando si nota che i loro valori rimangono identici se $p, q $ e $r, s $ sono intercambiabili da anti-commutation.

Se si presuppone che le orbite di rotazione siano di valore reale (così come per le basi orbitali di Gauss), è necessario che \begin{Equation} h_ {PQRS} = h_ {qpsr} = h_ {srqp} = h_ {rspq} = h_ {rqps} = h_ {psrq} = h_ {SPQR} = h_ {QRsP} ★ {.\tag} \label{EQ: hpqrsreal} \end{Equation} in base a tali presupposti, è possibile usare le simmetrie precedenti per ridurre i dati necessari per archiviare gli elementi della matrice dell'Hamiltoniana per un fattore di $8 $; Sebbene in questo modo, l'importazione dei dati in modo coerente risulta leggermente più complessa.
Fortunatamente, la libreria di simulazione hamiltoniana include subroutine che possono essere usate per importare file integrali da [liqui $ | \rangle $](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/) o direttamente da [nwchem](http://www.nwchem-sw.org/index.php/Main_Page).

Gli integrali orbitali molecolari, ad esempio i \_ termini $h {PQ} $ e $h \_ {PQRS} $, come questi sono rappresentati usando il `OrbitalIntegral` tipo, che fornisce una serie di funzioni utili per esprimere questa simmetria.
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

Oltre a enumerare tutti gli integrali orbitali numericamente identici, un elenco di tutti gli indici orbitali presenti nell'Hamiltoniana rappresentata da un `OrbitalIntegral` può essere generato come indicato di seguito.
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

Anziché creare un'Hamiltoniana fermioniche aggiungendo `FermionTerm` s, è possibile aggiungere automaticamente tutti i termini corrispondenti a ogni integrale orbitale.
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
