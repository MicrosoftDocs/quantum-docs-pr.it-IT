---
title: Funzioni d'onda correlate
description: Informazioni sulle correlazioni dinamiche e non dinamiche in d'onda usando la libreria Microsoft Quantum Chemistry.
author: guanghaolow
ms.author: gulow@microsoft.com
ms.date: 05/28/2019
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.multireference
ms.openlocfilehash: 005ef86382ca72969b06a4206cab01f3845718e2
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275916"
---
# <a name="correlated-wavefunctions"></a>Funzioni d'onda correlate

Per molti sistemi, in particolare quelli che si avvicinano alla geometria di equilibrio, [Hartree – Fock](xref:microsoft.quantum.chemistry.concepts.hartreefock) Theory fornisce una descrizione qualitativa delle proprietà molecolari tramite uno stato di riferimento con un solo determinante. Tuttavia, per ottenere un'accuratezza quantitativa, è necessario considerare anche gli effetti di correlazione. 

In questo contesto è importante dinstinguish tra correlazioni dinamiche e non dinamiche.
Le correlazioni dinamiche derivano dalla tendenza degli elettroni a distinguersi, ad esempio a causa della repulsione interelettronica. Questo effetto può essere modellato considerando le eccitazioni di elettroni dallo stato di riferimento. Le correlazioni non dinamiche si verificano quando il zero è dominato da due o più configurazioni in ordine zero, anche per ottenere solo una descrizione qualitativa del sistema.
Questa operazione richiede una superposizione dei fattori determinanti ed è un esempio di zero a più riferimenti.

La libreria di chimica fornisce un modo per specificare un zero di ordine zero per il problema di più riferimenti come una superposizione dei fattori determinanti. Questo approccio, che viene chiamato d'onda multireference di tipo sparse, è efficace quando solo pochi componenti sono sufficienti per specificare la superposizione. La libreria fornisce anche un metodo per includere le correlazioni dinamiche sopra un riferimento a un singolo determinante tramite l'unità di aggregazione del cluster unitario unitario generalizzato. Inoltre, costruisce anche circuiti Quantum che generano questi stati in un computer Quantum. Questi Stati possono essere specificati nello [schema Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)e forniscono anche la funzionalità per specificare manualmente questi stati tramite la libreria di chimica.

## <a name="sparse-multi-reference-wavefunction"></a>Zero a più riferimenti sparse
Uno stato a più riferimenti $ \ket{\ psi_ {\rm {MCSCF}}} $ può essere specificato in modo esplicito come combinazione lineare di $N $-Electron Slater determininants.
\begin{align} \ket{\ psi_ {\rm {MCSCF}}} \propto \ sum_ {i_1 < i_2 < \cdots < i_N} \ lambda_ {i_1, i_2, \cdots, i_N} a ^ \ dagger_ {i_1} a ^ \ dagger_ {i_2} \cdots a ^ \ dagger_ {i_N} \ket {0} .
\end{align} ad esempio, lo stato $ \propto (0.1 a ^ \ dagger_1a ^ \ dagger_2a ^ \ dagger_6-0,2 a ^ \ dagger_2a ^ \ dagger_1a ^ \ dagger_5) \ket {0} $ può essere specificato nella libreria di chimica come indicato di seguito.
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
Questa rappresentazione esplicita dei componenti di superposizione è efficace quando è necessario specificare solo alcuni componenti. Si consiglia di evitare di utilizzare questa rappresentazione quando sono necessari molti componenti per acquisire accuratamente lo stato desiderato. Il motivo è il costo del controllo del circuito quantistico che prepara questo stato in un computer Quantum, che scala almeno in modo lineare con il numero di componenti di superposizione e al massimo quadratico con la regola unica delle ampiezze della superposizione.

## <a name="unitary-coupled-cluster-wavefunction"></a>Unitario abbinato-cluster zero
È anche possibile specificare un Unity-cluster zero $ \ket{\ psi_ {\rm {UCC}}} $ usando la libreria di farmacie. In questa situazione è presente uno stato di riferimento con un solo determinante, ad \ket{\ psi_ {\rm{SCF}}} $. I componenti del zero del cluster unitario abbinato vengono quindi specificati in modo implicito tramite un operatore unitario che agisce su uno stato di riferimento.
Questo operatore unitario viene comunemente scritto come $e ^ {T-T ^ \dagger} $, dove $T-T ^ \dagger $ è l'operatore cluster anti-Hermitiane. Quindi \begin{align} \ket{\ psi_ {\rm {UCC}}} = e ^ {T-T ^ \dagger}\ket{\ psi_ {\rm{SCF}}}.
\end{align}

È anche comune suddividere l'operatore cluster $T = T_1 + T_2 + \cdots $ in parti, dove ogni parte $T _j $ contiene $j termini $-Body. In teoria dei cluster abbinati, l'operatore del cluster a corpo singolo (Single) ha il formato \begin{align} T_1 = \ sum_ {PQ} T ^ {p} _ {q} a ^ \ dagger_p a_q, \end{align}

e l'operatore cluster a due corpo (Double) ha il formato \begin{align} T_2 = \ sum_ {PQRS} T ^ {PQ} _ {RS} a ^ \ dagger_p a ^ \ dagger_q a_r a_s.
\end{align}

Sono possibili termini di ordine superiore (triple, quadruple e così via), ma non supportati attualmente dalla libreria di chimica.

Ad esempio, Let $ \ket{\ psi_ {\rm{SCF}}} = a ^ \ dagger_1 a ^ \ dagger_2 \ket {0} $ e let $T = 0,123 a ^ \ dagger_0 A_1 + 0,456 a ^ \ dagger_0a ^ \ dagger_3 A_1 A_2-0,789 a ^ \ dagger_3a ^ \ dagger_2 A_1 A_0 $. Viene quindi creata un'istanza di questo stato nella libreria di chimica come indicato di seguito.
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

Il convervation di selezione può essere reso esplicito specificando invece gli `SpinOrbital` indici invece degli indici Integer. Ad esempio, Let $ \ket{\ psi_ {\rm{SCF}}} = a ^ \ dagger_ {1, \uparrow} a ^ \ dagger_ {2, \downarrow}\ket {0} $ e let $T = 0,123 a ^ \ dagger_ {0, \uparrow} A_ {1, \uparrow} + 0,456 a ^ \ dagger_ {0, \uparrow} a ^ \ dagger_ {3, \downarrow} A_ {1, \uparrow} A_ {2, \downarrow}-0,789 a ^ \ dagger_ {3, \uparrow} a ^ \ dagger_ {2, \uparrow} A_ {1, \uparrow} A_ {0, \uparrow} $ be spin convserving. Viene quindi creata un'istanza di questo stato nella libreria di chimica come indicato di seguito.
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

Viene inoltre fornita una funzione di praticità che enumera tutti gli operatori di cluster che si Conversano alla rotazione che annientano solo le orbite di rotazione occupate e si eccita solo per gli orbitali di rotazione non occupate.
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
