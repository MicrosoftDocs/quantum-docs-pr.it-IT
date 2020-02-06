---
title: Seconda quantizzazione | Microsoft Docs
description: Seconda documentazione concettuale di quantizzazione
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.secondquantization
ms.openlocfilehash: 4b7b5a6be6d0c1f3520128609e6b9fa83e5460d5
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036424"
---
# <a name="second-quantization"></a>Seconda quantizzazione

La seconda quantizzazione analizza il problema della struttura elettronica tramite un'altra lente.
Anziché assegnare ogni $N _e $ elettroni a uno stato specifico (o orbitale), la seconda quantizzazione tiene traccia di ogni Orbital e archivia se è presente un elettrone presente in ognuno di essi e allo stesso tempo garantisce automaticamente le proprietà di simmetria del funzione Wave corrispondente.
Questo è importante perché consente di specificare i modelli di chimica quantistica senza doversi preoccupare dell'anti-symmetrizing lo stato di input (come richiesto per fermioni) e anche perché la seconda quantizzazione consente la simulazione di tali modelli usando un quantum ridotto computer.

Come esempio della seconda quantizzazione in azione, supponiamo che $ \ psi_0 \cdots \ psi_ {N-1} $ siano un set ortonormale di orbitali spaziali.
Queste orbite vengono scelte per rappresentare il sistema nel modo più accurato possibile nel set di base limitato considerato.
Un esempio comune di tali orbite sono gli orbitali atomici che formano un eigenbasis per l'Atom idrogeno.
Poiché gli elettroni hanno due stati di rotazione, due elettroni possono essere stipati in ogni orbita spaziale.
Ciò significa che gli Stati di base validi sono nel formato $ \ psi_ {0, \uparrow}, \ldots, \ psi_ {N-1, \uparrow}, \ psi_ {0, \downarrow}, \ldots, \ psi_ {N-1, \downarrow} $ where $ \uparrow $ e $ \downarrow $ sono etichette che specificano i due autostati del grado di rotazione libertà.
Questo indice combinato di $ (j, \sigma) $ per $ \sigma \in \{\uparrow, \downarrow\}$ è denominato "orbitale", perché archivia sia il grado di libertà spaziale che quello di rotazione.
Nella libreria di chimica, gli orbitali di rotazione vengono archiviati in una struttura di dati `SpinOrbital` e vengono creati come indicato di seguito.

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

Ciò significa che è possibile considerare formalmente la base sia per la parte di rotazione che per quella spaziale della funzione Wave come $ \ psi_{0} \cdots \ psi_ {2N-1} $ dove ogni indici ora è un'enumerazione di $ (j, \sigma) $.
Una possibile enumerazione è $g (j, \sigma) = j + N\sigma ' $.
Un'altra possibile enumerazione è $h (j, \sigma) = 2 * j + \sigma $.
La libreria Quantum Chemistry può usare tali convenzioni ed è possibile creare un'istanza degli orbitali di rotazione in una codifica di questo tipo come indicato di seguito.

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

Per i sistemi fermioniche, il principio di esclusione di Pauli impedisce che più elettroni siano presenti nello stesso momento.
Ciò significa che è possibile scrivere i due stati legali per $ \ psi_1 $ As \begin{Equation} \ psi_1 \rightarrow \begin{cases} \ket{0}_1 & \Text{if $ \ psi_1 $ non è occupato,} \\\
\ket{1}_1 & \Text{if $ \ psi_1 $ occupata.} \end{Cases} \end{Equation} questa codifica è ideale per i computer Quantum perché significa che è possibile archiviare l'occupazione elettronica come singolo bit di Quantum.

Gli Stati di occupazione per le orbite $2N $ rotazioni possono essere archiviati in modo analogo in $2N $ qubits.
Ad esempio, se $N = $2, lo stato $ $ \ket{0} \ket{1} \ket{1} \ket{0}, $ $

corrisponderebbe alle orbite di rotazione $1 $ e $2 $ occupate con il resto vuoto.
Allo stesso modo, lo stato $ $ \ket{0} \equiv \ket{0} _{0} \cdots \ket{0}_ {N-1}, $ $

non ha elettroni ed è noto come "stato di vuoto".

Uno splendido effetto collaterale della seconda quantizzazione consiste nel fatto che non è più necessario tenere traccia in modo esplicito dell'anti-simmetria dello stato del quantum.
Questo è dovuto al fatto che, come si vedrà, l'anti-simmetria dello stato rappresenta se stessa tramite le regole anti-commutazione degli operatori che creano ed eliminano le occupazioni elettroniche di un orbitale di rotazione.

## <a name="fermionic-operators"></a>Operatori fermioniche

I due operatori fondamentali che agiscono sui vettori di base quantizzati secondo sono noti come operatori di creazione e annientamento.
Questi operatori inseriscono o distruggono gli elettroni in una posizione specifica.
Questi sono indicati $a ^ \ dagger_j $ e $a _j $ rispettivamente.

Ad esempio, \begin{align} a ^ \ dagger_1 \ket{0}_1 = \ket{1}_1, \quad a ^ \ dagger_1 \ket{1}_1 = 0, \quad a_1 \ket{0}_1 = 0, \quad a_1 \ket{1}_1 = \ket{0}_1.
\end{align} si noti che qui $a ^ \ dagger_1 \ket{1}_1 = 0 $ e $a _1 \ket{0}_1 $ restituiscono il vettore zero not $ \ket{0}_1 $.
Tali operatori non sono pertanto né Hermitiane né Unity.
Sono rappresentati gli operatori di creazione e annientamento generali usando il tipo di <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1>.
Ad esempio, un singolo operatore di creazione viene rappresentato come segue.

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

Con tali operatori è inoltre possibile esprimere $ $ \ket{0} \ket{1} \ket{1} \ket{0} = a ^ \ dagger_1 a ^ \ dagger_2 \ket{0}^ {\otimes 4}.
$ $ Questa sequenza di operatori viene costruita all'interno della libreria di simulazione hamiltoniana C# usando codice simile al caso orbitario a rotazione singola considerato sopra sopra:
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

Per un sistema di $k $ fermioni, nella seconda quantizzazione l'azione dell'operatore di creazione $a ^ \ dagger_i $ viene fornita da $ $ a ^ \ dagger_i \ket{n_1, n_2, \ldots, 0_i, \ldots, n_k} = (-1) ^ {S_i} \ket{n_1, n_2, \ldots, 1_i , \ldots, n_k}, $ $ e $ $ a ^ \ dagger_i \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k} = 0, $ $ where $S _i = \ sum_ {j < i} a ^ \ dagger_j a_j $ misura il numero totale di fermioni che si trovano nello stato di una singola particella e che hanno un indice $j < i $.

Un terzo operatore viene spesso utilizzato anche nelle rappresentazioni quantizzate secondo.
Questo operatore è noto come operatore Number ed è definito da \begin{Equation} n_i = a ^ \ dagger_i a_i.
\end{Equation} questo operatore conta l'occupazione di un determinato Orbital di rotazione, ovvero \begin{align} n_i \ket{0}_i & = 0 \ NoNumber\\\
n_i \ket{1}_i & = \ket{1}_i.
\end{align} simile a quello riportato sopra `FermionTerm` esempi, questo operatore Number viene costruito come indicato di seguito.
```csharp
    // Let us use a new method to compactly create a sequence of ladder
    // operators. Note that we have omitted specifying whether the 
    // operators are raising or lowering. In this case, the first half
    // will be raising operators, and the second half will be lowering 
    // operators.
    var indices = new[] { 1, 1 }.ToLadderSequence();

    // We now construct a `FermionTerm` representing an annihilation operator
    // on the index 1 followed by the creation operator on the index 1.
    var fermionTerm0 = new FermionTerm(indices);
```

Una sottigliezza emerge tuttavia quando si usano gli operatori di creazione o annientamento nei sistemi fermioniche.
È necessario che qualsiasi stato quantum valido sia anti-simmetrico in scambio di etichette.
Ciò significa che $ $ a ^ \ dagger_2 a ^ \ dagger_1 \ket{0} =-a ^ \ dagger_1 a ^ \ dagger_2 \ket{0}.
Gli operatori $ $ di questo tipo sono detti "anti-commute" e, in generale, per qualsiasi $i, j $ abbiamo \begin{align} a ^ \ dagger_i a ^ \ dagger_j =-(1-\ delta_ {i, j}) a ^ \ dagger_j a ^ \ dagger_i, \quad a ^ \ dagger_i a_j = \ delta_ {i, j}-a_j a ^ \ dagger_i.
\end{align} quindi le due istanze di <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> seguenti sono considerate inequivalenti
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

Il requisito che ognuno degli operatori di creazione antipermuta significa che l'utilizzo di una seconda rappresentazione quantizzata consente di ovviare alle problematiche poste dall'anti-simmetria di fermioni.
Al contrario, la sfida riemerge nella definizione degli operatori di creazione. 

Utilizzando le regole di anti-commutazione, alcune istanze `LadderSequence` corrispondono effettivamente alla stessa sequenza di operatori fermioniche, a volte fino a un segno meno.
Si consideri, ad esempio, l'Hamiltoniana $a _0 ^ \dagger a_1 ^ \dagger a_1 a_0 =-a_1 ^ \dagger a_0 ^ \dagger A_1 a_0 $.
Questo consente di definire un ordinamento canonico per ogni `FermionTerm`.
Qualsiasi `FermionTerm` viene inserita automaticamente nell'ordine canonico come indicato di seguito.
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

## <a name="second-quantized-fermionic-hamiltonian"></a>Hamiltoniana fermioniche secondo-quantizzato

È probabilmente sorprendente che l'Hamiltoniana nei [modelli quantistici per i sistemi elettronici](xref:microsoft.quantum.chemistry.concepts.quantummodels) possa essere scritta in termini di operatori di creazione e annientamento.
In particolare, se $ \psi\_j $ sono le orbite di rotazione che formano la base

\begin{Equation} \hat{H} = \sum\_{PQ} h\_{PQ} a ^ \dagger\_p a\_q + \frac{1}{2}\sum\_{PQRS} H\_{PQRS} a ^ \dagger\_p a ^ \dagger\_q a\_ra\_s + H\_{\textrm NUC}, \label{EQ: totalha} \end{Equation} in cui $h\_{\textrm NUC} $ è l'energia nucleare, ovvero una costante sotto l'approssimazione di Oppenheimer, e

\begin{align} h\_{PQ} & = \int\_{-\infty} ^ \infty \psi ^\*\_p (x\_1) \left (-\frac{\nabla ^ 2}{2} + V (x\_1) \right) \psi\_q (x\_1) \mathrm{d} ^ 3x\_1, \end{align}

dove $V (x) $ è il potenziale campo medio e

\begin{align} h\_{PQRS} & = \int\_{-\infty} ^ \infty \int\_{-\infty} ^ \infty\psi\_p ^\*(x\_1) \psi\_q ^\*(x\_2) \left (\frac{1}{| x_1-x_2 |} \right) \psi\_r (x\_2) \psi\_s (x\_1) \mathrm{d} ^ 3x\_1 \ mathrm {d} ^ 3x\_2. \ etichetta {EQ : integrali} \end{align}

I termini $h\_{PQ} $ sono definiti integrali a un elettrone, perché tutti questi termini coinvolgono solo elettroni singoli e, allo stesso modo, $h\_{PQRS} $ sono integrali a due elettroni.
Sono detti integrali perché il calcolo dei valori di questi coefficienti richiede un integrale.
I termini di un elettrone descrivono l'energia cinetica dei singoli elettroni e le loro interazioni con i campi elettrici dei nuclei.
Gli integrali a due elettroni d'altra parte descrivono le interazioni tra gli elettroni.

Un'intuizione del significato di questi termini può essere ricavata dagli operatori di creazione e annientamento che comprendono ognuno di essi.
Ad esempio, $h _ {PQ} a ^ \ dagger_p a_q $ descrive il salto degli elettroni dall'orbitale di rotazione $q $ a spin Orbital $p $.
In modo analogo, il termine $h _ {PQRS} a ^ \ dagger_p a ^ \ dagger_q a_r a_s $ (per Distinct $p, q, r, s $) descrive due elettroni negli orbitali di rotazione $r $ e $s $ scattering tra loro e che terminano con gli orbitali di rotazione $p $ e $q $.
Se $r = q $ e $p = s $, $h _ {PRRP} a ^ \ dagger_p a ^ \ dagger_r a_r a_p = h_ {PRRP} n_p n_r $ fornisce la penalità di energia associata ai due elettroni che si avvicinano tra loro, ma non descrive un processo dinamico.

Questi hamiltonians possono essere rappresentati usando la classe `FermionHamiltonian`, che è essenzialmente un elenco contenente tutte le istanze di `FermionTerm` desiderate.
Poiché hamiltonians sono Hermitiane per definizione, i termini vengono indicizzati usando il tipo più specializzato `HermitianFermionTerm` che usa anche la simmetria Hermitiane per verificare se i termini sono equivalenti.

Si consentirà di creare alcuni esempi esemplificativi.
Si consideri l'Hamiltoniana $ \hat{H} = a_0 ^ \dagger a_1 + a_1 ^ \dagger a_0 $.
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
È possibile semplificare questa costruzione usando il fatto che gli operatori hamiltoniana sono operatori Hermitiane.
Quando si aggiungono termini a hamiltoniana usando `Add`, si presuppone che tutti i termini non hermitiane, ad esempio `fermionTerm0`, siano abbinati al relativo coniugato Hermitiane.
Quindi il frammento di codice seguente rappresenta anche la stessa hamiltoniana:
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the term to be added -- note the doubled coefficient.
    hamiltonian.Add(new HermitianFermionTerm(new[] { 1, 0 }), 2.0);
```

Se si usano le regole di anti-commutazione, alcune `FermionTerm` istanze nell'Hamiltoniana corrispondono in realtà alla stessa sequenza di operatori fermioniche, a volte fino a un segno meno.
Si consideri, ad esempio, l'Hamiltoniana $H = a_0 ^ \dagger a_1 ^ \dagger a_1 a_0-a_1 ^ \dagger a_0 ^ \dagger a_1 a_0 = 2a_0 ^ \dagger a_1 ^ \dagger a_1 a_0 $, ovvero una somma dei termini costruiti sopra.
Potrebbe non essere sempre chiaro all'utente che si tratta di termini equivalenti, quindi possono essere aggiunti all'Hamiltoniana separatamente.
In alternativa, è possibile che si desideri modificare i termini già esistenti nell'Hamiltoniana.
In questi casi, è possibile combinare termini equivalenti, come indicato di seguito.
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
Combinando i coefficienti dei termini equivalenti, viene ridotto il numero totale di termini nell'Hamiltoniana.
In un secondo momento, questo riduce il numero di controlli Quantum necessari per simulare l'hamiltoniana.

### <a name="internal-representation"></a>Rappresentazione interna

Un'Hamiltoniana fermioniche con interazioni di uno e due corpi viene rappresentata in una notazione di secondo-quantizzata come

$ $ \begin{align} H = \sum\_{PQ} h\_{PQ} a ^ \dagger\_{p} a\_{q} + \frac{1}{2}\sum\_{PQRS} h\_{PQRS} a ^ \dagger\_{p} a ^ \dagger\_{q} a\_{r} a\_{s}.
\end{align} $ $

In questa notazione sono presenti al massimo $N ^ 2 + N ^ 4 $ coefficienti.
Tuttavia, molti di questi coefficienti possono essere raccolti in quanto corrispondono allo stesso operatore.
Ad esempio, nel caso in cui $p, q, r, s $ sono indici distinti, è possibile usare le regole di anti-commutazione per mostrare che: $ $ a ^ \dagger\_{p} a ^ \dagger\_{q} a\_{r} a\_{s} =-a ^ \dagger\_{q} a ^ \dagger\_{p} a\_{r} a\_{s} =-a ^ \dagger\_{p} a ^ \dagger\_{q} a\_{s} a\_{r} = a ^ \dagger\_{q} a ^ \dagger\_{p} a\_{s} a\_{r}.
$$

Inoltre, come $H $ è hermitiane, ogni operatore fermioniche non hermitiane, ad esempio $h\_{PQRS} a ^ \dagger\_{p} a ^ \dagger\_{q} a\_{r} a\_{s} $, ha un coniugato Hermitiane presente anche in $H $. Per indicizzare in modo univoco i gruppi di termini caratterizzati da queste simmetrie, viene definito un ordinamento canonico sugli indici $ (i\_1, \cdots, i\_n, j\_1, \cdots, j\_m) $ di qualsiasi sequenza di $n + m $ fermioniche Operators $a ^ \dagger\_{i\_1} \cdots a ^ \dagger\_{i\_n} a\_{j\_1} \cdots a\_{j\_m} $as segue :
-   Tutti gli operatori di creazione $a ^ \dagger\_{i\_\cdot} $ vengono posizionati prima di tutti gli operatori di annientamento $a\_{j\_\cdot} $.
-   Tutti gli indici degli operatori di creazione sono ordinati in ordine crescente, ovvero $i\_1 < i\_2 < \cdots < i\_n $.
-   Tutti gli indici degli operatori di annientamento sono ordinati in ordine decrescente, ovvero $j\_1 > j\_2 \cdots > j\_m $.
-   L'indice più a sinistra è minore o uguale all'indice più a destra, ovvero $i\_1 \ le j\_m $.

Identifichiamo questo set di indici ordinati in modo canonico come $ $ \begin{align} (i\_1, \cdots, i\_n, j\_1, \cdots, j\_m) \in S\_{n, m}.
\end{align} $ $

Con questo ordinamento canonico, l'Hamiltoniana fermioniche può essere espressa come $ $ \begin{align} H = \sum\_{(p, q) \in S\_{1,1}} H '\_{PQ} \frac{a ^ \dagger\_{p} a\_{q} + a ^ \dagger\_{q} a\_{p}}{2}+ \sum\_{(p, d, r, s) \in S\_{2,2}} H '\_{PQRS} \frac{a ^ \dagger\_{p} a ^ \dagger\_{q} a\_{r} a\_{s} + a ^ \dagger\_{S} a ^ \ Dagger\_{r} a\_{q} a\_{p}}{2}, \end{align} $ $ con i integrali a uno e due elettroni appropriati, $h "\_{PQ} $ e $h"\_{PQRS} $ rispettivamente.

