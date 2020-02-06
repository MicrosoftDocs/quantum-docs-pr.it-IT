---
title: 'Ulteriori-tecniche di Q # | Microsoft Docs'
description: 'Ulteriori tecniche-Q #'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.going-further
ms.openlocfilehash: 41713827a93d2cc97e198fa4ad377012c846cf8b
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036237"
---
# <a name="going-further"></a>Più avanti #

Ora che si è appreso come scrivere programmi Quantum interessanti in Q #, questa sezione approfondisce ulteriormente introducendo alcuni argomenti più avanzati che dovrebbero risultare utili.


## <a name="generic-operations-and-functions"></a>Operazioni e funzioni generiche ##

> [!TIP]
> Questa sezione presuppone una certa familiarità con i [Generics C#in ](https://docs.microsoft.com/dotnet/csharp/programming-guide/generics/introduction-to-generics), i [ F#generics in ](https://docs.microsoft.com/dotnet/fsharp/language-reference/generics/), [ C++ i modelli](https://docs.microsoft.com/cpp/cpp/templates-cpp)o approcci simili alla metaprogrammazione in altri linguaggi.

Molte funzioni e operazioni che è possibile definire non si basano molto sui tipi di input, ma usano solo i tipi in modo implicito tramite un'altra funzione o un'altra operazione.
Si consideri, ad esempio, il concetto di *mappa* comune a molti linguaggi funzionali; Data una funzione $f (x) $ e una raccolta di valori $\{x_1, x_2, \dots, x_n\}$, map restituisce una nuova raccolta $\{f (X_1), f (x_2), \dots, f (x_n)\}$.
Per implementarlo in Q #, è possibile sfruttare le funzioni che sono la prima classe.
Viene ora illustrato un esempio rapido di `Map`, usando ★ come segnaposto, mentre è possibile individuare i tipi necessari.

```qsharp
function Map(fn : (★ -> ★), values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Nota Questa funzione è molto simile indipendentemente dai tipi effettivi sostituiti.
Un mapping da Integer a Paulis, ad esempio, ha un aspetto molto simile a quello di una mappa dai numeri a virgola mobile a stringhe:

```qsharp
function MapIntsToPaulis(fn : (Int -> Pauli), values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : (Double -> String), values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

In linea di principio, è possibile scrivere una versione di `Map` per ogni coppia di tipi che si verificano, ma in questo caso è stata introdotta una serie di problemi.
Se, ad esempio, si trova un bug in `Map`, è necessario assicurarsi che la correzione venga applicata in modo uniforme in tutte le versioni di `Map`.
Inoltre, se si costruisce una nuova tupla o un tipo definito dall'utente, è ora necessario costruire anche un nuovo `Map` per procedere con il nuovo tipo.
Sebbene si tratti di un numero ridotto di funzioni di questo tipo, quando si raccolgono più funzioni dello stesso tipo di `Map`, il costo dell'introduzione di nuovi tipi diventa ingiustificatamente grande in ordine piuttosto breve.

Gran parte di questa difficoltà, tuttavia, dal momento che non è stato fornito al compilatore le informazioni necessarie per riconoscere il modo in cui le diverse versioni di `Map` sono correlate.
In realtà, si vuole che il compilatore tratti `Map` come un tipo di funzione matematica dai *tipi* q # alle funzioni q #.
Questa nozione viene formalizzata consentendo a funzioni e operazioni di avere *parametri di tipo*, nonché i parametri di tupla ordinari.
Negli esempi precedenti si desidera considerare `Map` come avere parametri di tipo `Int, Pauli` nel primo caso e `Double, String` nel secondo caso.
Nella maggior parte dei casi, questi parametri di tipo possono essere usati come se fossero tipi normali: si usano valori di parametri di tipo per creare matrici e tuple, chiamare funzioni e operazioni e assegnare a variabili ordinarie o modificabili.

> [!NOTE]
> Il caso più estremo della dipendenza indiretta è quello di qubits, in cui un programma Q # non può basarsi direttamente sulla struttura del tipo di `Qubit`, ma **deve** passare tali tipi ad altre operazioni e funzioni.

Tornando all'esempio precedente, si noterà che è necessario `Map` disporre di parametri di tipo, uno per rappresentare l'input per `fn` e uno per rappresentare l'output da `fn`.
In Q # questa operazione viene scritta aggiungendo parentesi angolari (`<>`, non i Brake $ \braket{}$!) dopo il nome di una funzione o di un'operazione nella relativa dichiarazione e elencando ogni parametro di tipo.
Il nome di ogni parametro di tipo deve iniziare con un segno di `'`, a indicare che si tratta di un parametro di tipo e non di un tipo ordinario (noto anche come tipo *concreto* ).
Per `Map`, scriviamo quindi:

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Si noti che la definizione di `Map<'Input, 'Output>` ha un aspetto molto simile a quello delle versioni precedenti.
L'unica differenza consiste nel fatto che il compilatore è stato informato in modo esplicito che `Map` non dipende direttamente da quali `'Input` e `'Output` sono, ma funziona per i due tipi usando indirettamente tramite `fn`.
Una volta definito `Map<'Input, 'Output>` in questo modo, è possibile chiamarlo come se fosse una funzione ordinaria:

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> La scrittura di funzioni e funzioni generiche è un'unica posizione in cui "tuple-in tuple-out" è un modo utile per considerare le funzioni e le operazioni Q #.
> Poiché ogni funzione accetta esattamente un input e restituisce esattamente un output, un input di tipo `'T -> 'U` corrisponde a *qualsiasi* funzione Q #.
> Analogamente, qualsiasi operazione può essere passata a un input di tipo `'T => 'U`.

Come secondo esempio, si consideri la necessità di scrivere una funzione che restituisce la composizione di altre due funzioni:

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

In questo caso, è necessario specificare esattamente quali `A`, `B`e `C` sono, di conseguenza la limitazione dell'utilità della nuova funzione `Compose`.
Dopotutto, `Compose` dipende solo da `A`, `B`e `C` *tramite* `innerFn` e `outerFn`.
In alternativa, è possibile aggiungere parametri di tipo a `Compose` che indichino che funziona per *qualsiasi* `A`, `B`e `C`, purché questi parametri corrispondano a quelli previsti da `innerFn` e `outerFn`:

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

Le librerie standard Q # forniscono una serie di operazioni e funzioni con parametri di tipo per semplificare l'espressione del flusso di controllo di ordine superiore.
Questi argomenti sono illustrati più avanti nella [Guida alla libreria standard Q #](xref:microsoft.quantum.libraries.standard.intro).

## <a name="borrowing-qubits"></a>Prestito di qubits ##

Il meccanismo di prestito consente l'allocazione di qubits che può essere usata come spazio scratch durante un calcolo. Questi qubits in genere non sono in uno stato pulito, ovvero non vengono necessariamente inizializzati in uno stato noto, ad esempio $ \ket{0}$. Si parla anche di qubits "Dirty", perché il loro stato è sconosciuto e può anche essere correlato ad altre parti della memoria del computer Quantum. Tra i casi d'uso noti dei qubits Dirty sono implementazioni di controlli CNOT multicontrollati che richiedono solo pochi qubits e implementazioni di incrementatori.

In Canon sono disponibili esempi che usano la parola chiave `borrowing`, ad esempio la funzione `MultiControlledXBorrow` definita di seguito.
Se `controls` indica il qubits di controllo che deve essere aggiunto a un'operazione di `X`, in questa implementazione viene aggiunto un valore complessivo di `Length(controls)-2` molti ancillas Dirty.

```qsharp
operation MultiControlledXBorrow ( controls : Qubit[] , target : Qubit ) : Unit
is Adj + Ctl {

    body (...) {
        ... // skipping some case handling here
        let numberOfDirtyQubits = numberOfControls - 2;
        borrowing( dirtyQubits = Qubit[ numberOfDirtyQubits ] ) {

            let allQubits = [ target ] + dirtyQubits + controls;
            let lastDirtyQubit = numberOfDirtyQubits;
            let totalNumberOfQubits = Length(allQubits);

            let outerOperation1 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 1, 1, 0, numberOfDirtyQubits , _ );
            
            let innerOperation = 
                CCNOTByIndex(
                    totalNumberOfQubits - 1, totalNumberOfQubits - 2, lastDirtyQubit, _ );
            
            WithA(outerOperation1, innerOperation, allQubits);
            
            let outerOperation2 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 2, 2, 1, numberOfDirtyQubits - 1 , _ );
            
            WithA(outerOperation2, innerOperation, allQubits);
        }
    }

    controlled(extraControls, ...) {
        MultiControlledXBorrow( extraControls + controls, target );
    }
}
```

Si noti che l'uso estensivo di `With` combinatore---nel formato applicabile per le operazioni che supportano contigut, ad esempio `WithA`---è stato creato in questo esempio, che è uno stile di programmazione valido, come l'aggiunta di un controllo alle strutture che coinvolgono `With` solo la propagazione del controllo all'operazione interna. Si noti inoltre che qui, oltre all'`body` dell'operazione è stata fornita in modo esplicito un'implementazione del corpo `controlled` dell'operazione anziché ricorrere a un'istruzione `controlled auto`. Il motivo è che la struttura del circuito illustra come aggiungere facilmente ulteriori controlli, che risulta vantaggioso rispetto all'aggiunta di un controllo a ogni singolo controllo nella `body`. 

È istruttivo confrontare questo codice con un'altra funzione Canon `MultiControlledXClean` che raggiunga lo stesso obiettivo dell'implementazione di un'operazione di `X` controllata da Multiply, che usa diversi qubits puliti usando il meccanismo di `using`. 
