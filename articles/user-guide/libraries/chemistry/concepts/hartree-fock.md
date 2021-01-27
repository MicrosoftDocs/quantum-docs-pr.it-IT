---
title: Teoria Hartree-Fock
description: Informazioni sulla teoria Hartree – Fock, un modo semplice per costruire lo stato iniziale per i sistemi quantistici.
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: conceptual
uid: microsoft.quantum.chemistry.concepts.hartreefock
no-loc:
- Q#
- $$v
ms.openlocfilehash: 48d6bc4face90046271dd8705188a92daafad98a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854099"
---
# <a name="hartreefock-theory"></a>Hartree – teoria di Fock

Probabilmente la quantità più importante nella simulazione della chimica quantistica è lo stato di base, ovvero la autovettore di energia minima della matrice hamiltoniana.
Ciò è dovuto al fatto che per la maggior parte delle molecole in quantità di temperatura della stanza, ad esempio i tassi di reazione, sono dominate da differenze di energia gratuite tra gli Stati del quantum che descrivono l'inizio e la fine di un passaggio in un percorso di reazione e la temperatura della stanza, ad esempio lo stato
Mentre lo stato di base è in genere troppo difficile da apprendere (anche con un computer Quantum) perché si tratta di una distribuzione su un numero esponenzialmente elevato di configurazioni.
Possono essere apprese quantità come l'energia dello stato di base.
Se ad esempio $ \ket{\psi} $ è uno stato quantum puro, \begin{Equation} E = \bra{\psi} \hat{H} \ket{\psi} \end{Equation} fornisce l'energia media del sistema in tale stato.
Lo stato di base è quindi lo stato che fornisce il valore più piccolo. Di conseguenza, la scelta di uno stato che sia il più vicino possibile al vero stato è estremamente importante per stimare l'energia direttamente (come avviene in eigensolvers varianti) o attraverso la stima della fase.

Hartree: la teoria Fock fornisce un modo semplice per costruire lo stato iniziale per i sistemi quantistici. Produce una singola approssimazione del valore del valore di Slater per lo stato di base di un sistema quantico. A tal fine, trova una rotazione nello spazio di Fock che riduce al minimo l'energia dello stato di base. In particolare, per un sistema di $N $ Electrons, il metodo esegue la rotazione \begin{Equation} \ prod_ {j = 0} ^ {N-1} a ^ \ dagger_j \ket {0} \mapsto \ prod_ {j = 0} ^ {n-1} e ^ {u} a ^ \ dagger_j e ^ {-u} \ket {0} \defeq\ prod_ {j = 0} ^ {N-1} \widetilde{a} ^ \ dagger_j \ket {0} , \end{Equation} con un anti-Hermitiane (ad esempio $u =-u ^ \dagger $) Matrix $u = \ Sum_ {PQ} U_ {PQ} a ^ \ dagger_p a_q $. Si noti che la matrice $u $ rappresenta le rotazioni orbitali e $ \widetilde{a} ^ \ dagger_j $ e $ \widetilde{a} _j $ rappresentano gli operatori di creazione e annientamento per gli elettroni che occupano le orbite molecolari di Hartree – Fock.


Matrix $u $ viene quindi ottimizzato per ridurre al minimo l'energia prevista $ \bra {0} \ prod_ {j = 0} ^ {n-1} \widetilde{a} \_ j H \Prod \_ {k = 0} ^ {n-1} \widetilde{a} ^ \ dagger_k \ket {0} $. Sebbene tali problemi di ottimizzazione possano essere genericamente complessi, in pratica l'algoritmo Hartree-Fock tende a convergere rapidamente a una soluzione quasi ottimale al problema di ottimizzazione, soprattutto per le molecole della shell chiusa nelle geometrie di equilibrio. È possibile specificare questi stati come un'istanza dell' `FermionWavefunction` oggetto. Ad esempio, viene creata un'istanza dello stato $a ^ \ dagger_ {1} a ^ \ dagger_ {2} a ^ \ dagger_ {6} \ket {0} $ nella libreria di chimica, come indicato di seguito.
```csharp
// Create a list of integer indices of the creation operators
var indices = new[] { 1, 2, 6 };

// Convert the list of indices to a `FermionWavefunction` object.
// In this case, the indices are integers, so we use the `int`
// type specialization.
var wavefunction = new FermionWavefunction<int>(indices);
```
È anche possibile indicizzare le funzioni Wave con gli `SpinOrbital` indici e quindi convertire questi indici in numeri interi come indicato di seguito.
```csharp
// Create a list of spin orbital indices of the creation operators
var indices = new[] { (0, Spin.d), (1,Spin.u), (3, Spin.u) };

// Convert the list of indices to a `FermionWavefunction` object.
var wavefunctionSpinOrbital = new FermionWavefunction<SpinOrbital>(indices.ToSpinOrbitals());

// Convert a wavefunction indexed by spin orbitals to
// one indexed by integers
var wavefunctionInt = wavefunctionSpinOrbital.ToIndexing(IndexConvention.UpDown);
```

La caratteristica più eclatante della teoria Hartree – Fock è che produce uno stato quantico che non ha alcun groviglio tra gli elettroni.
Ciò significa che spesso fornisce una descrizione qualitativa adatta delle proprietà dei sistemi molecolari. 

Lo stato Hartree-Fock può anche essere ricostruito da un `FermionHamiltonian`  come indicato di seguito.
```csharp
// We initialize a fermion Hamiltonian.
var fermionHamiltonian = new FermionHamiltonian();

// Create a Hartree-Fock state from the Hamiltonian 
// with, say, `4` occupied spin orbitals.
var wavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons: 4);
```

Tuttavia, ottenendo risultati accurati, soprattutto per i sistemi fortemente correlati, richiedono gli Stati Quantum che vanno oltre la teoria Hartree – Fock.
