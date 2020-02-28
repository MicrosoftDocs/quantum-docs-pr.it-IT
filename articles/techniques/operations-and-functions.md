---
title: 'Operazioni e funzioni Q #'
description: 'Informazioni sulle operazioni e sulle funzioni di Q # e su come vengono applicate in un programma Quantum.'
uid: microsoft.quantum.techniques.opsandfunctions
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 43f0cf2da192a607e514d0c7de57a9bdd067faf7
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907665"
---
# <a name="q-operations-and-functions"></a>Operazioni e funzioni Q #

I programmi Q # sono costituiti da una o più *operazioni* che descrivono gli effetti collaterali delle operazioni Quantum possono avere sui dati quantistici e una o più *funzioni* che consentono modifiche ai dati classici. Diversamente dalle operazioni, le funzioni vengono usate per descrivere il comportamento puramente classico e non hanno effetti oltre al calcolo dei valori di output classici.

Ogni operazione definita in Q # può quindi chiamare un numero qualsiasi di altre operazioni, incluse le operazioni intrinseche predefinite definite dal linguaggio. Il modo specifico in cui vengono definite queste operazioni intrinseche dipende dal computer di destinazione. Quando viene compilata, ogni operazione viene rappresentata come tipo di classe .NET che può essere fornita ai computer di destinazione.

## <a name="defining-new-operations"></a>Definizione di nuove operazioni

Come descritto in precedenza, il blocco predefinito più elementare di un programma Quantum scritto in Q # è un' *operazione*che può essere chiamata da applicazioni .NET classiche, ad esempio usando un simulatore o altre operazioni all'interno di q #.
Ogni operazione accetta un input, produce un output e specifica l'implementazione per una o più specializzazioni delle operazioni.
Ad esempio, l'operazione seguente definisce solo una specializzazione del corpo predefinita e accetta un solo qubit come input, quindi chiama l'operazione incorporata `X` su tale input:

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

La parola chiave `operation` inizia la definizione dell'operazione ed è seguita dal nome; `BitFlip`.
Successivamente, il tipo di input viene definito come `Qubit`, insieme a un nome `target` per fare riferimento all'input all'interno della nuova operazione.
Analogamente, il `Unit` definisce che l'output dell'operazione è vuoto.
Viene usato in modo analogo a C# `void` in e altri linguaggi imperativi ed è equivalente F# a `unit` in e altri linguaggi funzionali.

> [!NOTE]
> Questo aspetto verrà esaminato in dettaglio più avanti, ma ogni operazione in Q # accetta esattamente un input e restituisce esattamente un output.
> Più input e output vengono quindi rappresentati utilizzando *Tuple*, che raccolgono più valori in un singolo valore.
> In modo informale, diciamo che Q # è un linguaggio "tuple-in-out".
> Seguendo questo concetto, `()` deve quindi essere letto come tupla "vuota", che ha il tipo `Unit`.

All'interno della nuova operazione, l'implementazione può essere specificata direttamente nella dichiarazione se è necessario specificare in modo esplicito solo l'implementazione della specializzazione del corpo predefinita. Inoltre, è possibile definire le implementazioni di, ad esempio, una o più operazioni di `functor`, come elaborato di seguito. Nell'esempio precedente, l'unica istruzione consiste nel chiamare l'operazione Q # incorporata <xref:microsoft.quantum.intrinsic.x>.

Le operazioni possono inoltre restituire tipi più interessanti rispetto a `Unit`.
Ad esempio, l'operazione <xref:microsoft.quantum.intrinsic.m> restituisce un output di tipo `Result`, che rappresenta l'esecuzione di una misurazione. È possibile passare l'output di un'operazione a un'altra operazione oppure utilizzarlo con la parola chiave `let` per definire una nuova variabile.
<!-- Link to UID for superdense conceptual and example documentation. -->
Questo consente la rappresentazione di calcoli classici che interagiscono con le operazioni Quantum a un livello basso, ad esempio nella codifica superdensa:

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```
### <a name="functors-adjoint-and-controlled"></a>Funtori, contigut e controllato
Se un'operazione implementa una trasformazione unitaria, è possibile definire il modo in cui l'operazione agisce quando *adjointed* o *controllata*. Una specializzazione contigua di un'operazione specifica il modo in cui agisce quando viene eseguita in ordine inverso, mentre una specializzazione controllata specifica il modo in cui un'operazione viene applicata quando viene applicato condizionato allo stato di un registro quantico.
L'esistenza di queste specializzazioni può essere dichiarata come parte della firma dell'operazione: `is Adj + Ctl` nell'esempio seguente. L'implementazione corrispondente per ogni specializzazione dichiarata in modo implicito viene quindi generata dal compilatore. 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

> [!NOTE]
> Molte operazioni in Q # rappresentano i cancelli unitari.
> Se $U $ è il controllo unitario rappresentato da un'operazione `U`, `Adjoint U` rappresenta il controllo dell'unità $U ^ \dagger $.

Nel caso in cui l'implementazione non possa essere generata dal compilatore, può essere specificata in modo esplicito. Tali dichiarazioni di specializzazione esplicita possono essere costituite da una direttiva di generazione adatta o da un'implementazione definita dall'utente. Il codice nell'`PrepareEntangledPair` precedente, ad esempio, equivale al codice riportato di seguito contenente dichiarazioni di specializzazione esplicite: 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
La parola chiave `auto` indica che il compilatore deve determinare come generare l'implementazione della specializzazione.
Se il compilatore non è in grado di generare automaticamente l'implementazione per una determinata specializzazione o se è possibile fornire un'implementazione più efficiente, l'implementazione può anche essere definita manualmente.

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
Nell'esempio precedente, `adjoint invert;` indica che la specializzazione contigua deve essere generata invertendo l'implementazione del corpo e `controlled adjoint invert;` indica che la specializzazione contigua controllata deve essere generata invertendo l'implementazione specificata della specializzazione controllata.

In un [flusso di controllo di ordine superiore](xref:microsoft.quantum.concepts.control-flow)si vedranno altri esempi.

Per chiamare una specializzazione di un'operazione, usare le parole chiave `Adjoint` o `Controlled`.
Ad esempio, l'esempio di codifica di superdense sopra riportato può essere scritto in modo più compatto usando il `PrepareEntangledPair` contiguo per trasformare lo stato inserito di nuovo in una coppia non impigliata di qubits:

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

Quando si progettano operazioni da usare con funtori, è necessario considerare alcune importanti limitazioni.
In modo più critico, le specializzazioni per un'operazione che usa il valore di output di qualsiasi altra operazione non possono essere generate automaticamente dal compilatore, perché è ambiguo come riordinare le istruzioni in tale operazione per ottenere lo stesso effetto.


## <a name="defining-new-functions"></a>Definizione di nuove funzioni

Q # consente inoltre di definire *funzioni*, che sono distinte dalle operazioni in quanto non possono avere effetti oltre il calcolo di un valore di output.
In particolare, le funzioni non possono chiamare operazioni, agire su qubits, numeri casuali di esempio o in altro modo dipendono dallo stato oltre il valore di input per una funzione.
Di conseguenza, le funzioni Q # sono *pure*, in quanto eseguono sempre il mapping degli stessi valori di input agli stessi valori di output.
Ciò consente al compilatore Q # di riordinare in modo sicuro come e quando le funzioni vengono chiamate quando si generano specializzazioni delle operazioni.

La definizione di una funzione funziona in modo analogo alla definizione di un'operazione, ad eccezione del fatto che non è possibile definire alcuna specializzazioni contigua o controllata per una funzione.
Ad esempio:

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```
Quando è possibile eseguire questa operazione, è utile scrivere la logica classica in termini di funzioni anziché di operazioni, in modo che possa essere usata più facilmente all'interno di operazioni.
Se, ad esempio, è stato scritto `Square` come operazione, il compilatore non sarebbe stato in grado di garantire che la chiamata con lo stesso input produrrebbe sempre gli stessi output.

Per sottolineare la differenza tra funzioni e operazioni, prendere in considerazione il problema di campionamento classico di un numero casuale da un'operazione Q #:

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

Ogni volta che viene chiamato `U`, avrà un'azione diversa su `target`.
In particolare, il compilatore non può garantire che se è stato aggiunto un `adjoint auto` dichiarazione di specializzazione per `U`, `U(target); Adjoint U(target);` funge da identità, ovvero come no-op.
In questo modo si viola la definizione del contiguo che abbiamo visto in [vettori e matrici](xref:microsoft.quantum.concepts.vectors), in modo da consentire a di generare automaticamente una specializzazione contigua in un'operazione in cui è stata chiamata l'operazione <xref:microsoft.quantum.math.randomreal> comporterebbe la violazione delle garanzie fornite dal compilatore. <xref:microsoft.quantum.math.randomreal> è un'operazione per la quale non esiste alcuna versione contigua o controllata.

D'altra parte, consentire le chiamate di funzione, ad esempio `Square` è sicuro, in quanto è possibile garantire che il compilatore debba solo mantenere l'input per `Square` per mantenere stabile l'output.
In questo modo, l'isolamento della logica classica più possibile in funzioni semplifica il riutilizzo di tale logica in altre funzioni e operazioni.

## <a name="control-flow"></a>Flusso di controllo

All'interno di un'operazione o di una funzione, ogni istruzione viene eseguita in ordine, in modo analogo ai linguaggi classici imperativi più comuni.
Questo flusso di controllo può tuttavia essere modificato in tre modi distinti:

- Istruzioni `if`
- Cicli di `for`
- `repeat`-cicli `until`

Si rinvia la discussione di quest'ultima fino a quando non si discute la [ripetizione fino al completamento dei circuiti (UR)](xref:microsoft.quantum.techniques.qubits#measurements) .
I costrutti del flusso di controllo `if` e `for`, tuttavia, procedono in un senso familiare alla maggior parte dei linguaggi di programmazione classici.
In particolare, un'istruzione `if` può assumere una condizione, può essere seguita da una o più istruzioni `elif` e può terminare con un `else`:

```qsharp
if (pauli == PauliX) {
    X(qubit);
} elif (pauli == PauliY) {
    Y(qubit);
} elif (pauli == PauliZ) {
    Z(qubit);
} else {
    fail "Cannot use PauliI here.";
}
```

Analogamente, i cicli di `for` indicano l'iterazione su un intervallo di numeri interi o sugli elementi di una matrice:

```qsharp
for (idxQubit in 0..nQubits - 1) {
    // Do something to idxQubit...
}
```

In particolare, è possibile usare i cicli di `for` e le istruzioni `if` anche nelle operazioni per le quali le specializzazioni vengono generate automaticamente. In tal caso, il contiguo di un ciclo di `for` inverte la direzione e accetta il contiguo di ogni iterazione.
Segue il principio "Shoes-and-Socks": se si vuole annullare la messa a punto dei calzini e quindi delle scarpe, è necessario annullare le calzature e quindi annullare l'inserimento dei calzini.
Si tratta di un approccio decisamente meno efficace per provare a riportare i calzini quando si indossano ancora le scarpe.

## <a name="operations-and-functions-as-first-class-values"></a>Operazioni e funzioni come valori di prima classe

Una tecnica critica per ragionare sul flusso di controllo e la logica classica con funzioni anziché operazioni consiste nell'usare le operazioni e le funzioni in Q # sono di *prima classe*.
Ovvero ciascuno dei quali è il linguaggio di propria scelta.
Ad esempio, di seguito è riportato un codice Q # perfettamente valido, se poco indiretto:

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

Il valore della variabile `ourH` nel frammento di codice precedente è quindi l'operazione <xref:microsoft.quantum.intrinsic.h>, in modo che sia possibile chiamare tale valore come qualsiasi altra operazione.
In questo modo è possibile scrivere operazioni che accettano operazioni come parte dell'input, formando concetti di flusso di controllo di ordine superiore.
Si supponga, ad esempio, di voler "quadrare" un'operazione applicando due volte lo stesso qubit di destinazione.

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

In questo esempio, la freccia `=>` visualizzata nel tipo `(Qubit => Unit)` indica che il campo di input `op` è un'operazione che accetta come input il tipo `Qubit` e produce una tupla vuota come output.
Vengono inoltre specificate le caratteristiche del tipo di operazione, che contengono le informazioni su quali funtori sono supportate.
Un'operazione di tipo `(Qubit => Unit)` non supporta né il `Adjoint` né il functore `Controlled`. Se si vuole indicare che un'operazione di tale tipo deve supportare, ad esempio, il `Adjoint` functor, è necessario dichiararlo come adjointable. Questa operazione viene eseguita utilizzando l'annotazione `is Adj` al tipo. Analogamente, `(Qubit => Unit is Ctl)` indica che un'operazione di tale tipo supporta il functor `Controlled`. Questa operazione verrà ulteriormente esaminata quando si discutono i [tipi in Q #](xref:microsoft.quantum.language.type-model) più in generale.

Per il momento, viene evidenziato che è anche possibile restituire le operazioni come parte degli output, in modo da poter isolare alcuni tipi di logica condizionale classica come una funzione classica che restituisce una descrizione di un programma Quantum sotto forma di operazione.
Come esempio semplice, si consideri l'esempio di Teleporting, in cui la parte che riceve un messaggio classico a due bit deve usare il messaggio per decodificare i qubit nello stato di teleporte appropriato.
È possibile scrivere questo risultato in termini di funzione che accetta i due bit classici e restituisce l'operazione di decodifica corretta.

```qsharp
function TeleporationDecoderForMessage(hereBit : Result, thereBit : Result)
: (Qubit => Unit is Adj + Ctl) {

    if (hereBit == Zero && thereBit == Zero) {
        return I;
    } elif (hereBit == One && thereBit == Zero) {
        return X;
    } elif (hereBit == Zero && thereBit == One) {
        return Z;
    } else {
        return Y;
    }
}
```

Questa nuova funzione è effettivamente una funzione, in quanto se viene chiamata con gli stessi valori di `hereBit` e `thereBit`, verrà sempre restituita la stessa operazione.
Pertanto, il decodificatore può essere eseguito in modo sicuro all'interno di operazioni senza dover ragionare sul modo in cui la logica di decodifica interagisce con le definizioni delle diverse specializzazioni delle operazioni.
Ovvero è stata isolata la logica classica all'interno di una funzione, garantendo al compilatore che la chiamata di funzione possa essere riordinata con impuneità purché l'input venga mantenuto.

È anche possibile considerare le funzioni come valori di prima classe, come si vedrà in modo più dettagliato quando si discutono [le operazioni e i tipi di funzione](#operations-and-functions-as-first-class-values).

## <a name="partially-applying-operations-and-functions"></a>Applicazione parziale di operazioni e funzioni

È possibile eseguire molte altre operazioni con funzioni che restituiscono operazioni usando un' *applicazione parziale*, in cui è possibile fornire una o più parti dell'input a una funzione o a un'operazione senza chiamarla effettivamente. Ad esempio, richiamando il `ApplyTwice` esempio precedente, è possibile indicare che non si vuole specificare, immediatamente, a quale qubit deve essere applicata l'operazione di input:

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

In questo caso, la variabile locale `twiceOp` contiene l'operazione parzialmente applicata `ApplyTwice(op, _)`, in cui le parti dell'input che non sono state ancora specificate sono indicate da `_`.
Quando si chiama effettivamente `twiceOp` nella riga successiva, viene passato come input all'operazione parzialmente applicata tutte le parti rimanenti dell'input per l'operazione originale.
Di conseguenza, il frammento di codice precedente è effettivamente identico a avere chiamato `ApplyTwice(op, target)` direttamente, salvo per il fatto che è stata introdotta una nuova variabile locale che ci permette di ritardare la chiamata, fornendo alcune parti dell'input.

Poiché un'operazione che è stata applicata parzialmente non viene effettivamente chiamata fino a quando non è stato fornito l'intero input, è possibile applicare parzialmente in modo sicuro le operazioni anche dalle funzioni.

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

In linea di base, la logica classica all'interno di `SquareOperation` potrebbe essere stata molto più complessa, ma è ancora isolata dal resto di un'operazione garantita dal fatto che il compilatore possa offrire informazioni sulle funzioni.
Questo approccio verrà usato in tutta la libreria standard Q # per esprimere il flusso di controllo classico in modo da poter essere usato facilmente nei programmi Quantum.
