---
title: 'Controlli di flusso nel libararies standard Q #'
description: 'Informazioni sulle funzioni e sulle operazioni di controllo del flusso nella libreria Microsoft Q # standard.'
author: QuantumWriter
uid: microsoft.quantum.concepts.control-flow
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: b41b3edd7a3e3ac13dbda106a869f4cba8183600
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907172"
---
# <a name="higher-order-control-flow"></a>Flusso di controllo di ordine superiore #

Uno dei ruoli principali della libreria standard è quello di semplificare l'espressione di idee algoritmiche di alto livello come [programmi Quantum](https://en.wikipedia.org/wiki/Quantum_programming).
In questo modo, il canone Q # offre un'ampia gamma di costrutti di controllo di flusso diversi, ognuno implementato usando un'applicazione parziale di funzioni e operazioni.
Passando immediatamente ad esempio, si consideri il caso in cui si vuole creare una "CNOT Ladder" in un registro:

```qsharp
let nQubits = Length(register);
CNOT(register[0], register[1]);
CNOT(register[1], register[2]);
// ...
CNOT(register[nQubits - 2], register[nQubits - 1]);
```

È possibile esprimere questo modello usando i cicli di iterazione e `for`:

```qsharp
for (idxQubit in 0..nQubits - 2) {
    CNOT(register[idxQubit], register[idxQubit + 1]);
}
```

Espressa in termini di <xref:microsoft.quantum.canon.applytoeachca> e funzioni di manipolazione di matrici come <xref:microsoft.quantum.arrays.zip>, tuttavia, questo è molto più breve e più facile da leggere:

```qsharp
ApplyToEachCA(CNOT, Zip(register[0..nQubits - 2], register[1..nQubits - 1]));
```

Nella parte restante di questa sezione vengono forniti alcuni esempi di come usare le varie operazioni e funzioni di controllo di flusso fornite dal canonico per esprimere in modo compatto i programmi Quantum.

## <a name="applying-operations-and-functions-over-arrays-and-ranges"></a>Applicazione di operazioni e funzioni su matrici e intervalli ##

Una delle astrazioni principali fornite da Canon è quella di iterazione.
Si consideri, ad esempio, un elemento unitario nel formato $U \otimes U \otimes \cdots \otimes U $ per un singolo qubit unitario $U $.
In Q # è possibile usare <xref:microsoft.quantum.arrays.indexrange> per rappresentare questo come un ciclo di `for` su un registro:

```qsharp
/// # Summary
/// Applies $H$ to all qubits in a register.
operation ApplyHadamardToAll(
    register : Qubit[])
: Unit is Adj + Ctl {
    for (qubit in register) {
        H(qubit);
    }
}
```

È quindi possibile usare questa nuova operazione come `HAll(register)` per applicare $H \otimes H \otimes \cdots \otimes H $.

Si tratta tuttavia di un'operazione complessa, in particolare in un algoritmo di dimensioni maggiori.
Questo approccio è inoltre specializzato per l'operazione specifica che si vuole applicare a ogni qubit.
È possibile utilizzare il fatto che le operazioni siano di prima classe per esprimere questo concetto algoritmico in modo più esplicito:

```qsharp
ApplyToEachCA(H, register);
```

Il suffisso `CA` indica che la chiamata a `ApplyToEach` è a sua volta adjointable e controllabile.
Pertanto, se `U` supporta `Adjoint` e `Controlled`, le righe seguenti sono equivalenti:

```qsharp
Adjoint ApplyToEachCA(U, register);
ApplyToEachCA(Adjoint U, register);
```

In particolare, ciò significa che le chiamate a `ApplyToEachCA` possono comparire in operazioni per le quali viene generata automaticamente una specializzazione contigua.
Analogamente, <xref:microsoft.quantum.canon.applytoeachindex> è utile per rappresentare i modelli del form `U(0, targets[0]); U(1, targets[1]); ...`e offre versioni per ogni combinazione di funtori supportata dal relativo input.

> [!TIP]
> `ApplyToEach` è parametrizzato con parametri di tipo in modo che possa essere utilizzato con operazioni che accettano input diversi da `Qubit`.
> Si supponga, ad esempio, che `codeBlocks` sia una matrice di <xref:microsoft.quantum.errorcorrection.logicalregister> valori che devono essere ripristinati.
> Quindi `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` applicherà il codice di correzione degli errori `code` e la funzione di ripristino `recoveryFn` a ogni blocco in modo indipendente.
> Questo vale anche per gli input classici: `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` applica una rotazione di $ \Pi/$2 circa $X $ seguito da una rotazione di $pi/$3 su $Y $.

Il canone Q # fornisce anche il supporto per modelli di enumerazione classici noti alla programmazione funzionale.
Ad esempio, <xref:microsoft.quantum.arrays.fold> implementa il pattern $f (f (f (s\_{\Text{Initial}}, x\_0), x\_1), \dots) $ per ridurre una funzione in un elenco.
Questo modello può essere utilizzato per implementare somme, prodotti, minima, Maxima e altre funzioni di questo tipo:

```qsharp
open Microsoft.Quantum.Arrays;
function Plus(a : Int, b : Int) : Int { return a + b; }
function Sum(xs : Int[]) {
    return Fold(Sum, 0, xs);
}
```

Analogamente, è possibile usare funzioni come <xref:microsoft.quantum.arrays.mapped> e <xref:microsoft.quantum.arrays.mappedbyindex> per esprimere i concetti di programmazione funzionale in Q #.

## <a name="composing-operations-and-functions"></a>Composizione di operazioni e funzioni ##

I costrutti del flusso di controllo offerti dalla Canon accettano operazioni e funzioni come input, in modo che sia utile poter comporre diverse operazioni o funzioni in un singolo chiamabile.
Ad esempio, il modello $UVU ^ {\dagger} $ è molto comune nella programmazione quantistica, in modo che il canone fornisca l'operazione <xref:microsoft.quantum.canon.applywith> come un'astrazione per questo modello.
Questa astrazione consente anche un Compliation più efficiente nei circuiti, perché `Controlled` agire sulla sequenza `U(qubit); V(qubit); Adjoint U(qubit);` non deve agire su ogni `U`.
Per verificarlo, consentire a $c (U) $ di essere l'unitario che rappresenta `Controlled U([control], target)` e lasciare che $c (V) $ venga definito nello stesso modo.
Quindi, per uno stato arbitrario $ \ket{\psi} $, \begin{align} c (U) c (V) c (U) ^ \dagger \ket{1} \otimes \ket{\psi} & = \ket{1} \otimes (UVU ^ {\dagger} \ket{\psi}) \\\\ & = (\boldone \otimes U) (c (V)) (\boldone \otimes U ^ \dagger) \ket{1} \otimes \ket{\psi}.
\end{align} in base alla definizione di `Controlled`.
D'altra parte, \begin{align} c (U) c (V) c (U) ^ \dagger \ket{0} \otimes \ket{\psi} & = \ket{0} \otimes \ket{\psi} \\\\ & = \ket{0} \otimes (UU ^ \dagger \ket{\psi}) \\\\ & = (\boldone \otimes U) (c (V)) (\boldone \otimes U ^ \dagger) \ket{0} \otimes \ket{\psi}.
\end{align} per linearità, possiamo concludere che è possibile fattorizzare $U $ out in questo modo per tutti gli Stati di input.
Ovvero $c (UVU ^ \dagger) = U c (V) U ^ \dagger $.
Poiché le operazioni di controllo possono risultare costose in generale, l'uso di varianti controllate come `WithC` e `WithCA` può ridurre il numero di funtori di controllo che devono essere applicati.

> [!NOTE]
> Un'altra conseguenza del factoring di $U $ è che non è necessario neanche capire come applicare il `Controlled` functor a `U`.
> `ApplyWithCA` ha pertanto una firma più debole rispetto a quanto previsto:
> ```qsharp
> ApplyWithCA<'T> : (('T => Unit is Adj),
>     ('T => Unit is Adj + Ctl), 'T) => Unit
> ```

Analogamente, <xref:microsoft.quantum.canon.bound> genera operazioni che applicano a sua volta una sequenza di altre operazioni.
Ad esempio, gli elementi seguenti sono equivalenti:

```qsharp
H(qubit); X(qubit);
Bound([H, X], qubit);
```

La combinazione con i modelli di iterazione può rendere questa operazione particolarmente utile:

```qsharp
// Bracket the quantum Fourier transform with $XH$ on each qubit.
ApplyWith(ApplyToEach(Bound([H, X]), _), QFT, _);
```

### <a name="time-ordered-composition"></a>Composizione Time-ordered ###

Possiamo continuare a usare il controllo di flusso in termini di funzioni di applicazione e classiche parziali ed è possibile modellare concetti quantistici anche piuttosto sofisticati in termini di controllo di flusso classico.
Questa analogia viene resa precisa dal riconoscimento che gli operatori unitari corrispondono esattamente agli effetti collaterali delle operazioni di chiamata, in modo che qualsiasi scomposizione di operatori unitari in termini di altri operatori unitari corrisponda alla costruzione di una particolare sequenza di chiamata per subroutine classiche che emettono istruzioni per agire come operatori unitari specifici.
In questa visualizzazione, `Bound` è esattamente la rappresentazione del prodotto Matrix, dal momento che `Bound([A, B])(target)` è equivalente a `A(target); B(target);`, che a sua volta è la sequenza chiamante corrispondente a $BA $.

Un esempio più sofisticato è l' [espansione Trotter-Suzuki](https://arxiv.org/abs/math-ph/0506007v1).
Come illustrato nella sezione relativa alla rappresentazione dinamica del generatore di [strutture di dati](xref:microsoft.quantum.libraries.data-structures), l'espansione Trotter-Suzuki fornisce un modo particolarmente utile per esprimere esponenziali matrici.
Ad esempio, l'applicazione dell'espansione con l'ordine più basso produce che per tutti gli operatori $A $ e $B $ tale che $A = A ^ \dagger $ e $B = B ^ \dagger $, \begin{align} \tag{★} \label{EQ: Trotter-Suzuki-0} \exp (i [A + B] t) = \ lim_ {n\to\infty} \left (\exp (i A t/n) \exp (i B t/n) \right) ^ n.
\end{align} colloquialmente, questo afferma che è possibile evolvere approssimativamente uno stato in $A + B $, in alternativa in $A $ e $B $ alone.
Se l'evoluzione viene rappresentata in $A $ da un'operazione `A : (Double, Qubit[]) => Unit` applicabile $e ^ {i t A} $, la rappresentazione dell'espansione Trotter – Suzuki in termini di ridisposizione delle sequenze di chiamata diventa chiara.
In concreto, data un'operazione `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` in modo che `A = U(0, _, _)` e `B = U(1, _, _)`, è possibile definire una nuova operazione che rappresenta l'integrale di `U` al momento $t $ generando sequenze nel form

```qsharp
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
// ...
```

A questo punto, è ora possibile ragionare sull'espansione Trotter-Suzuki *senza riferimento ai meccanismi Quantum*.
L'espansione è effettivamente un modello di iterazione molto particolare motivato da $ \eqref{EQ: Trotter-Suzuki-0} $.
Questo modello di iterazione viene implementato da <xref:microsoft.quantum.canon.decomposeintotimestepsca>:

```qsharp
// The 2 indicates how many terms we need to decompose,
// while the 1 indicates that we are using the
// first-order Trotter–Suzuki decomposoition.
DecomposeIntoTimeStepsCA((2, U), 1);
```

La firma di `DecomposeIntoTimeStepsCA` segue un modello comune in Q #, in cui le raccolte di cui è possibile eseguire il backup in base a matrici o a un elemento che calcola gli elementi in tempo reale sono rappresentate da tuple i cui primi elementi sono `Int` valori che ne indicano le lunghezze.

## <a name="putting-it-together-controlling-operations"></a>Inserimento insieme: controllo delle operazioni ##

Infine, la Canon si basa sul `Controlled` functor fornendo modi aggiuntivi per condizionare le operazioni quantistiche.
Si tratta di una situazione comune, soprattutto in aritmetica quantistica, per condizionare le operazioni su stati di base computazionali diversi da $ \ket{0\cdots 0} $.
Utilizzando le operazioni e le funzioni di controllo introdotte in precedenza, è possibile utilizzare più condizioni di Quantum generali in un'unica istruzione.
Passiamo ora a come <xref:microsoft.quantum.canon.controlledonbitstring> (parametri di tipo sans), quindi suddividiamo le parti una alla volta.
La prima cosa da fare è definire un'operazione che esegue effettivamente il pesante carico di implementazione del controllo sugli stati di base di calcolo arbitrari.
Questa operazione, tuttavia, non viene chiamata direttamente, quindi si aggiunge `_` all'inizio del nome per indicare che si tratta di un'implementazione di un altro costrutto altrove.

```qsharp
operation _ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl),
    controlRegister : Qubit[],
    targetRegister: Qubit[])
: Unit is Adj + Ctl
```

Si noti che si accetta una stringa di bit, rappresentata come matrice di `Bool`, che verrà usata per specificare il condizionamento che si vuole applicare all'operazione `oracle` fornita.
Poiché questa operazione esegue effettivamente direttamente l'applicazione, è necessario anche prendere i registri di controllo e di destinazione, entrambi rappresentati come `Qubit[]`.

Si noti quindi che il controllo sullo stato di base di calcolo $ \ket{\vec{s}} = \ket{s\_0 s\_1 \dots s\_{n-1}} $ per una stringa di bit $ \vec{s} $ può essere realizzato trasformando $ \ket{\vec{s}} $ in $ \ket{0\cdots 0} $.
In particolare, $ \ket{\vec{s}} = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} \ket{0\cdots 0} $.
Poiché $X ^ {\dagger} = X $, significa che $ \ket{0\dots 0} = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} \ket{\vec{s}} $.
È quindi possibile applicare $P = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} $, applicare `Controlled oracle`e trasformare nuovamente in $ \vec{s} $.
Questa costruzione è esattamente `ApplyWith`, quindi scriviamo il corpo della nuova operazione di conseguenza:

```qsharp
{
    ApplyWithCA(
        ApplyPauliFromBitString(PauliX, false, bits, _),
        (Controlled oracle)(_, targetRegister),
        controlRegister
    );
}
```

In questo esempio è stato usato <xref:microsoft.quantum.canon.applypaulifrombitstring> per applicare $P $, applicando parzialmente la destinazione per l'uso con `ApplyWith`.
Si noti, tuttavia, che è necessario trasformare il registro di *controllo* nel modulo desiderato, in modo da applicare parzialmente l'operazione interna `(Controlled oracle)` sulla *destinazione*.
In questo modo si lascia `ApplyWith` agire per racchiudere il registro di controllo con $P $, esattamente come si desidera.

A questo punto, è possibile eseguire questa operazione, ma in qualche modo non è in grado di soddisfare la nuova operazione, ad esempio l'applicazione del `Controlled` functor.
In questo modo, si termina la definizione del nuovo concetto di flusso di controllo scrivendo una funzione che accetta l'oggetto Oracle da controllare e che restituisce una nuova operazione.
In questo modo, la nuova funzione ha un aspetto molto simile a `Controlled`, illustrando che è possibile definire facilmente nuovi costrutti di flusso di controllo con Q # e la Canon insieme:

```qsharp
function ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl))
: ((Qubit[], Qubit[]) => Unit is Adj + Ctl) {
    return _ControlledOnBitString(bits, oracle, _, _);
}
```
