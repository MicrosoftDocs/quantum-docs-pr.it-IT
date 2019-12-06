---
title: Simulazione di Dynamics hamiltoniana | Microsoft Docs
description: Simulazione di documenti concettuali di Dynamics hamiltoniana
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.simulationalgorithms
ms.openlocfilehash: 4d1924386eadb427e8f53bc0a177453a341f185f
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74864458"
---
# <a name="simulating-hamiltonian-dynamics"></a>Simulazione di Dynamics hamiltoniana

Una volta che l'hamiltoniana è stata espressa come una somma di operatori elementari, le dinamiche possono essere compilate in operazioni Gate fondamentali usando una serie di tecniche ben note.
Tre approcci efficienti includono le formule Trotter – Suzuki, le combinazioni lineari di unitaries e qubitization.
Questi tre approcci vengono illustrati di seguito e vengono forniti esempi concreti Q # di come implementare questi metodi usando la libreria di simulazione hamiltoniana.


## <a name="trottersuzuki-formulas"></a>Trotter-formule Suzuki
L'idea dietro le formule Trotter – Suzuki è semplice: esprimere l'Hamiltoniana come una somma di facile simulazione di hamiltonians e quindi approssimare l'evoluzione totale come una sequenza di queste evoluzioni più semplici.
In particolare, consentire a $H = \ sum_ {j = 1} ^ m H_j $ be the hamiltoniana.
Quindi, $ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \ prod_ {j = 1} ^ m e ^ {-iH_j t} + O (m ^ 2 t ^ 2), $ $, vale a dire che, se $t \ll $1, l'errore in questa approssimazione diventa irrilevante.
Si noti che se $e ^ {-i H t} $ era un esponenziale normale, l'errore in questa approssimazione non sarebbe $O (m ^ 2 t ^ 2) $: sarebbe zero.
Questo errore si verifica perché $e ^ {-iHt} $ è un operatore esponenziale e, di conseguenza, si verifica un errore durante l'utilizzo di questa formula a causa del fatto che i $H _j $ terms non vengono commutati,*ad esempio*$H _J H_k \ne H_k H_j $ in generale.

Se $t $ è di grandi dimensioni, le formule Trotter-Suzuki possono comunque essere usate per simulare la dinamica in modo accurato suddividendo il valore in una sequenza di brevi passaggi temporali.
Consentire $r $ sia il numero di passaggi eseguiti nell'evoluzione del tempo.
Quindi, è necessario che $ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \left (\ prod_ {j = 1} ^ m e ^ {-iH_j t/r} \ Right) ^ r + O (m ^ 2 t ^ 2/r), $ $, che implica che se $r $ Scales come $m ^ 2 t ^ 2/\ Epsilon $, l'errore può essere eseguito al massimo $ \epsilon $ per qualsiasi $ \epsilon > 0 $.

È possibile creare approssimazioni più accurate creando una sequenza di operatori esponenziali in modo che i termini di errore vengano annullati.
La formula più semplice, la formula Trotter simmetrica o la suddivisione Strang, assume il formato $ $ U_1 (t) = \ prod_ {j = 1} ^ m e ^ {-iH_j t/2} \ prod_ {j = m} ^ 1 e ^ {-iH_j t} = e ^ {-iHt} + O (m ^ 3 t ^ 3), $ $, che può essere reso inferiore a $ \epsilon $ per qualsiasi $ \epsilon > 0 $ scegliendo $r $ per la scalabilità come $m ^ {3/2} t ^ {3/2}/\sqrt {\ Epsilon} $.

È possibile costruire formule Trotter anche di ordine superiore basate su $U _1 $.
Il più semplice è la formula del quarto ordine seguente: introdotta originariamente da Suzuki: $ $ U_2 (t) = U_1 ^ 2 (s_1t) U_1 ([1-4s_1] t) U_1 ^ 2 (s_1 t) = e ^ {-iHt} + O (m ^ 5T ^ 5), $ $ where $s _1 = (4-4 ^ {1/3}) ^{-1}$.
In generale, le formule arbitrariamente più ordinate possono essere costruite in modo analogo; Tuttavia, i costi sostenuti dall'utilizzo di integratori più complessi spesso superano i vantaggi oltre il quarto ordine per la maggior parte dei problemi pratici.

Per far funzionare le strategie precedenti, è necessario disporre di un metodo per simulare un'ampia classe di $e ^ {-iH_j t} $.
La famiglia più semplice di hamiltonians e probabilmente più utile, che potremmo usare qui, sono gli operatori di Pauli.
Gli operatori di Pauli possono essere facilmente simulati perché possono essere diagonali usando le operazioni di Clifford, ovvero le porte standard nel quantum computing.
Inoltre, una volta che sono state spostate in diagonale, è possibile trovare gli autovalori calcolando la parità di qubits su cui agiscono.

Ad esempio, $ $ e ^ {-iX\otimes X t} = (H\otimes H) e ^ {-iZ\otimes Z t} (H\otimes H), $ $ where $ $ e ^ {-i Z \otimes Z t} = \begin{Bmatrix} e ^ {-it} & 0 & 0 & 0 \\\
        0 & e ^ {i t} & 0 & 0 \\\
        0 & 0 & e ^ {it} & 0 \\\
        0 & 0 & 0 & e ^ {-it} \end{Bmatrix}.
$ $ Here, $e ^ {-iHt} \ket{00} = e ^ {it} \ket{00}$ e $e ^ {-iHt} \ket{01} = e ^ {-it} \ket{01}$, che può essere visto direttamente come conseguenza del fatto che la parità di $0 $ è $0 $, mentre la parità della stringa di bit $1 $ è $1 $.

Gli esponenziali degli operatori di Pauli possono essere implementati direttamente in Q # usando l'operazione <xref:microsoft.quantum.primitive.exp>:
```qsharp
    using(qubits = Qubit[2]){
        let pauliString = [PauliX, PauliX];
        let evolutionTime = 1.0;

        // This applies e^{- i X \otimes X t} to qubits 0 and 1.
        Exp(pauliString, - evolutionTime, qubits);
    }
```

Per fermioniche hamiltonians, la [scomposizione Giordania-Wigner](xref:microsoft.quantum.chemistry.concepts.jordanwigner) esegue la mappatura dell'Hamiltoniana in una somma di operatori Pauli.
Questo significa che l'approccio precedente può essere facilmente adattato alla simulazione della chimica.
Anziché eseguire manualmente il loop su tutti i termini di Pauli nella rappresentazione Giordania-Wigner, di seguito è riportato un esempio semplice di come l'esecuzione di tale simulazione all'interno della chimica.
Il punto di partenza è una [codifica Giordania-Wigner](xref:microsoft.quantum.chemistry.concepts.jordanwigner) dell'Hamiltoniana fermioniche, espressa nel codice come un'istanza della classe `JordanWignerEncoding`.

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

    // We now convert this representation into a format consumable by Q#.
    var qSharpData = jordanWignerEncoding.ToQSharpFormat();
```

Questo formato della rappresentazione Giordania-Wigner che può essere utilizzato dagli algoritmi di simulazione Q # è un tipo definito dall'utente `JordanWignerEncodingData`.
All'interno di Q # questo formato viene passato a una funzione di praticità `TrotterStepOracle` che restituisce un'evoluzione del tempo di operatore approssimativo usando il Trotter, Suzuki Integrator, oltre ad altri parametri necessari per l'esecuzione.

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

In particolare, questa implementazione applica alcune ottimizzazioni illustrate nella [simulazione della struttura elettronica hamiltonians usando i computer Quantum](https://arxiv.org/abs/1001.3855) e [migliorando gli algoritmi quantistici per la chimica quantistica](https://arxiv.org/abs/1403.1539) per ridurre al minimo il numero di rotazioni singole qubit necessarie, nonché ridurre gli errori di simulazione.

## <a name="qubitization"></a>Qubitization

Qubitization è un approccio alternativo alla simulazione che usa le idee dei percorsi quantistici per simulare la dinamica quantistica.
Mentre qubitization richiede più qubits delle formule Trotter, il metodo promette la scalabilità ottimale con il tempo di evoluzione e la tolleranza di errore.
Per questi motivi, è diventato un metodo favorito per simulare in generale la dinamica Hamiltoniana e per risolvere il problema di struttura elettronica in particolare.

A livello generale, qubitization esegue questa operazione tramite i passaggi seguenti.
Per prima cosa, lasciare $H = \ sum_j h_j H_j $ per Unity e Hermitiane $H _J $ e $h _J \ge $0.
Eseguendo una coppia di riflessioni, qubitization implementa un operatore equivalente a $ $W = e ^ {\pm i \cos ^{-1}(H/| h | _1)}, $ $ where $ | H | _1 = \ sum_j | h_j | $.
Il passaggio successivo consiste nel trasformare gli autovalori dell'operatore Walk da $e ^ {i\pm \cos ^{-1}(E_k/| h | _1)} $, dove $E _k $ sono gli autovalori di $H $ a $e ^ {-iE_k t} $.
Questa operazione può essere eseguita usando un'ampia gamma di metodi di trasformazione del valore singolare Quantum, inclusa l' [elaborazione del segnale Quantum](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501).

In alternativa, se si desiderano solo quantità statiche (ad esempio, l'energia dello stato di base dell'Hamiltoniana), è sufficiente applicare la [stima della fase](xref:microsoft.quantum.libraries.characterization) direttamente a $W $ per stimare l'energia dello stato di base dal risultato prendendo il coseno del risultato.
Questa operazione è significativa perché consente di eseguire la trasformazione spettrale in modo classico anziché utilizzare un metodo di trasformazione di valori singolari Quantum.

A un livello più dettagliato, l'implementazione di qubitization richiede due subroutine che forniscono le interfacce per l'hamiltoniana.
A differenza dei metodi Trotter – Suzuki, queste subroutine sono quantum non classico e la loro implementazione richiederà l'uso di logaritmicamente più qubits che sarebbero necessari per una simulazione basata su Trotter.

La prima subroutine quantistica utilizzata da qubitization viene chiamata $ \operatorname{Select} $ ed è stata promessa di produrre \begin{Equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}, \end{Equation} in cui si presuppone che ogni $H _j $ sia Hermitiane e unitario.
Sebbene possa sembrare restrittivo, tenere presente che gli operatori di Pauli sono Hermitiane e Unity, quindi le applicazioni come la simulazione della chimica quantistica rientrano naturalmente in questo Framework.
L'operazione $ \operatorname{Select} $, probabilmente sorprendentemente, è in realtà un'operazione di Reflection.
Questa situazione si verifica dal fatto che $ \operatorname{Select} ^ 2 \ KET {j} \ket{\psi} = \ket{j} \ket{\psi} $ poiché ogni $H _j $ è unitario e Hermitiane e pertanto dispone di autovalori $ \pm $1.

La seconda subroutine è chiamata $ \operatorname{Prepare} $.
Mentre l'operazione Select consente di accedere in modo coerente a ognuno dei termini hamiltoniana $H _j $ la subroutine Prep fornisce un metodo per accedere ai coefficienti $h _j $, \begin{Equation} \operatorname{Prepare}\ket{0} = \ sum_j \sqrt{\frac{h_j} {| H | _1}} \ket{j}.
\end{Equation} quindi, usando un controllo della fase di moltiplicazione controllata, si noterà che $ $ \Lambda\ket{0}^ {\otimes n} = \begin{cases} \-\ket{x} & \Text{If} x = 0 \\\
        \ket{x} & \Text{otherwise} \end{Cases}.
$$

L'operazione $ \operatorname{Prepare} $ non viene utilizzata direttamente in qubitization, bensì viene utilizzata per implementare una reflection sullo stato che $ \operatorname{Prepare} $ crea $ $ \begin{align} R &amp; = 1-2 \ operatorName {prepare} \ket{0}\bra{0} \operatorname{Prepare} ^{-1} \\\\ &amp; = \operatorname{Prepare} \Lambda \operatorname{Prepare} ^{-1}.
\end{align} $ $

L'operatore Walk, $W $, può essere espresso in termini di $ \operatorname{Select} $ e $R $ Operations come $ $ W = \operatorname{Select} R, $ $, che può essere visualizzato di nuovo per implementare un operatore equivalente (fino a un isometria) a $e ^ {\pm i \cos ^{-1}(H/| h | _1)} $.

Queste subroutine sono facili da configurare in Q #.
Si consideri ad esempio la semplice hamiltoniana qubit trasversale Ising in cui $H = X_1 + X_2 + Z_1 Z_2 $.
In questo caso, il codice Q # che implementa l'operazione $ \operatorname{Select} $ viene richiamato da <xref:microsoft.quantum.canon.multiplexoperations>, mentre l'operazione $ \operatorname{Prepare} $ può essere implementata usando <xref:microsoft.quantum.preparation.preparearbitrarystate>.
Un esempio che prevede la simulazione del modello Hubbard può essere trovato come [esempio Q #](https://github.com/microsoft/Quantum/tree/master/samples/simulation/hubbard).

La specifica manuale di questi passaggi per i problemi di chimica arbitraria richiede molto lavoro, evitando l'uso della libreria di chimica.
Analogamente all'algoritmo di simulazione Trotter-Suzuki precedente, il `JordanWignerEncodingData` viene passato alla funzione convenience `QubitizationOracle` che restituisce l'operatore Walk, oltre ad altri parametri necessari per l'esecuzione.

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

È importante che l'implementazione <xref:microsoft.quantum.chemistry.jordanwigner.qubitizationoracle> sia applicabile a hamiltonians arbitrario specificati come una combinazione lineare di stringhe Pauli.
Una versione ottimizzata per le simulazioni di chimica viene richiamata usando <xref:microsoft.quantum.chemistry.jordanwigner.optimizedqubitizationoracle>.
Questa versione è ottimizzata per ridurre al minimo il numero di controlli T usando le tecniche descritte in [codifica di spettri elettronici nei circuiti quantistici con complessità T lineare](https://arxiv.org/abs/1805.03662).
