---
title: Caricamento di un operatore hamiltoniano da un file
description: Informazioni su come generare automaticamente un'Hamiltoniana di grandi dimensioni con lo schema Broombridge.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.loadhamiltonian
no-loc:
- Q#
- $$v
ms.openlocfilehash: 57e25bf55009797b01695cef0f3d29b94662ccc0
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869240"
---
# <a name="loading-a-hamiltonian-from-file"></a>Caricamento di un operatore hamiltoniano da un file
In precedenza, abbiamo creato hamiltonians aggiungendo singoli termini. Sebbene si tratti di un problema per piccoli esempi, la chimica quantistica su larga scala richiede hamiltonians con milioni o miliardi di termini. Tali hamiltonians, generati da pacchetti di chimica come NWChem, sono troppo grandi per essere importati manualmente. In questo esempio viene illustrato come un' `FermionHamiltonian` istanza può essere generata automaticamente da una molecola rappresentata dallo [schema Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge). Come riferimento, è possibile esaminare l' `LithiumHydrideGUI` esempio specificato o l' `RunSimulation` esempio. Il supporto limitato è disponibile anche per l'importazione dal formato utilizzato da [LIQUi |>](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/).

Prendiamo in considerazione l'esempio della molecola azoto, disponibile nella `IntegralData/YAML` cartella del repository Samples. Il metodo per il caricamento dello `Broombridge` schema è semplice.

```csharp
// This is the name of the file we want to load
var filename = @"n2_1_00Re_sto3g.nw.out.yaml";
// This is the directory containing the file
var root = @"IntegralData\YAML";

// This deserializes a Broombridge file, given its filename.
var broombridge = Broombridge.Deserializers.DeserializeBroombridge($@"{root}\{filename}");

// Note that the deserializer returns a list of `ProblemDescription` instances 
// as the file might describe multiple Hamiltonians. In this example, there is 
// only one Hamiltonian. So we use `.First()`, which selects the first element of the list.
var problem = broombridge.ProblemDescriptions.First();

// This extracts the `OrbitalIntegralHamiltonian` from Broombridge format,
// then converts it to a fermion Hamiltonian, then to a Jordan-Wigner
// representation.
var orbitalIntegralHamiltonian = problem.OrbitalIntegralHamiltonian;
var fermionHamiltonian = orbitalIntegralHamiltonian.ToFermionHamiltonian(IndexConvention.UpDown);
var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(Pauli.QubitEncoding.JordanWigner);
```

Lo schema Broombridge contiene anche suggerimenti per lo stato iniziale da preparare. Le etichette, ad esempio `"|G⟩"` o `"|E1⟩"` , per questi Stati possono essere visualizzate controllando il file. Per preparare questi stati iniziali, il `qSharpData` utilizzato dagli Q# algoritmi quantum viene ottenuto in modo analogo alla [sezione precedente](xref:microsoft.quantum.chemistry.examples.energyestimate), ma con un parametro aggiuntivo che seleziona lo stato iniziale desiderato. Ad esempio,
```csharp
// The desired initial state, assuming that a description of it is present in the
// Broombridge schema.
var state = "|E1>";
var wavefunction = problem.Wavefunctions[state].ToIndexing(IndexConvention.UpDown);

// This creates the qSharpData consumable by the Q# chemistry library algorithms.
var qSharpHamiltonianData = jordanWignerEncoding.ToQSharpFormat();
var qSharpWavefunctionData = wavefunction.ToQSharpFormat();
var qSharpData = QSharpFormat.Convert.ToQSharpFormat(qSharpHamiltonianData, qSharpWavefunctionData);
```

Tutti i passaggi precedenti possono essere abbreviati usando i metodi pratici indicati di seguito.
```csharp
// This is the name of the file we want to load
var filename = "...";

// This deserializes a Broombridge file, given its filename.
var broombridge = Broombridge.Deserializers.DeserializeBroombridge(filename);

// Note that the deserializer returns a list of `ProblemDescription` instances 
// as the file might describe multiple Hamiltonians. In this example, there is 
// only one Hamiltonian. So we use `.Single()`, which selects the only element of the list.
var problem = broombridge.ProblemDescriptions.Single();

// This is a data structure representing the Jordan-Wigner encoding 
// of the Hamiltonian that we may pass to a Q# algorithm.
// If no state is specified, the Hartree-Fock state is used by default.
var qSharpData = problem.ToQSharpFormat("|E1>");
```

È anche possibile caricare un'Hamiltoniana da LIQUi |> formato, usando una sintassi molto simile. 

```csharp
// This is the name of the file we want to load
var filename = @"fe2s2_sto3g.dat"; // This is Ferrodoxin.
// This is the directory containing the file
var root = @"IntegralData\Liquid";

// Deserialize the LiQuiD format.
var problem = LiQuiD.Deserialize($@"{root}\{filename}").First();

// This is a data structure representing the Jordan-Wigner encoding 
// of the Hamiltonian that we may pass to a Q# algorithm.
var qSharpData = problem.ToQSharpFormat();
```

Seguendo questo processo da qualsiasi istanza di Broombridge o da qualsiasi passaggio intermedio, è possibile eseguire algoritmi quantistici come la stima della fase quantistica sul problema di struttura elettronica specificato.
