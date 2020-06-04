---
title: Uso dei qubit
description: Descrizione riempimento
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
ms.openlocfilehash: 0deb0729a88c49798f32a22a943b935d383c570b
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327544"
---
# <a name="working-with-qubits"></a>Uso dei qubit

Avendo visto una serie di diverse parti del linguaggio Q #, è possibile passare al suo interno e vedere come usare qubits.

Si noti che nessuna di queste istruzioni è consentita all'interno del corpo di una funzione.
Sono valide solo all'interno delle operazioni.

## <a name="allocating-qubits"></a>Allocazione di qubits

### <a name="clean-qubits"></a>Pulisci qubits

L' `using` istruzione viene utilizzata per *allocare* nuovi qubits da utilizzare durante un blocco di istruzioni.

L'istruzione è costituita dalla parola chiave `using` , seguita da una parentesi aperta `(` , un'associazione, una parentesi di chiusura `)` e il blocco di istruzioni all'interno del quale sarà disponibile qubits.
Il binding segue lo stesso modello delle `let` istruzioni, ovvero un singolo simbolo o una tupla di simboli, seguito da un segno di uguale `=` e da un singolo valore o da una tupla corrispondente di *inizializzatori*.

Gli inizializzatori sono disponibili per un singolo qubit, indicato come `Qubit()` o una matrice di qubits, `Qubit[n]` , dove `n` è un' `Int` espressione.
Ad esempio,

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```

Tutti i qubits allocati in questo modo iniziano con lo stato $ \ket {0} $. nell'esempio precedente, `register` è quindi nello stato $ \ket = \ket \otimes \ket \otimes \cdots \otimes {00000} {0} {0} \ket {0} $.
Alla fine del `using` blocco, qualsiasi qubits allocato dal blocco viene immediatamente deallocato e non può essere usato ulteriormente.

> [!WARNING]
> I computer di destinazione si aspettano che qubits si trovino nello stato $ \ket {0} $ immediatamente prima della deallocazione, in modo che possano essere riutilizzati e offerti ad altri `using` blocchi per l'allocazione.
> Quando possibile, usare le operazioni unitarie per restituire qualsiasi qubits allocato a $ \ket {0} $.
> Se necessario, l' @"microsoft.quantum.intrinsic.reset" operazione può essere usata per misurare un qubit e per usare il risultato della misurazione per garantire che il qubit misurato venga restituito a $ \ket {0} $. Una misura di questo tipo eliminerà eventuali problemi con i restanti qubits e può quindi influisca sul calcolo.


### <a name="borrowed-qubits"></a>Qubits preso in prestito

L' `borrowing` istruzione viene usata per rendere qubits disponibili per l'uso temporaneo, che non devono essere in uno stato specifico.

Il meccanismo di prestito consente l'allocazione di qubits che può essere usata come spazio scratch durante un calcolo.
Questi qubits in genere non sono in uno stato pulito, ovvero non vengono necessariamente inizializzati in uno stato noto, ad esempio $ \ket {0} $.
Queste sono spesso denominate qubits "Dirty" perché il loro stato è sconosciuto e può anche essere aggrovigliato con altre parti della memoria del computer Quantum.

L'associazione segue lo stesso modello e le stesse regole di un' `using` istruzione.
Ad esempio,
```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```
I qubits presi in prestito sono in uno stato sconosciuto e non rientrano nell'ambito alla fine del blocco di istruzioni.
Il mutuatario si impegna a lasciare il qubits nello stesso stato in cui si trovavano quando sono state prese in prestito, ovvero il proprio stato all'inizio e alla fine del blocco di istruzioni deve essere lo stesso.
Questo stato in particolare non è necessariamente uno stato classico, in modo che nella maggior parte dei casi gli ambiti in prestito non contengano misurazioni. 

Quando si prendono in prestito qubits, il sistema tenterà innanzitutto di compilare la richiesta da qubits in uso, ma non è possibile accedervi durante il corpo dell' `borrowing` istruzione.
Se il qubits non è sufficiente, verrà allocato il nuovo qubits per completare la richiesta.


Tra i casi d'uso noti dei qubits Dirty sono implementazioni di controlli CNOT multicontrollati che richiedono solo pochi qubits e implementazioni di incrementatori.
Vedere l' [esempio di qubits in prestito](#borrowing-qubits-example) seguente per vedere un esempio di uso in Q # o il factoring della carta con la funzionalità di [*qubits 2n + 2 con moltiplicazione modulare basata su Toffoli*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler e Svore 2017) per un algoritmo che utilizza qubits in prestito.


## <a name="intrinsic-operations"></a>Operazioni intrinseche

Una volta allocato, un qubit può quindi essere passato a funzioni e operazioni.
In un certo senso, questo è tutto ciò che può fare un programma Q # con un qubit, in quanto le azioni che è possibile eseguire sono tutte definite come operazioni.
Queste operazioni verranno visualizzate in modo più dettagliato nelle [operazioni e funzioni intrinseche](xref:microsoft.quantum.libraries.standard.prelude), ma per il momento si menzioneranno alcune operazioni utili che possono essere usate per interagire con qubits.

In primo luogo, gli operatori di Pauli Single-qubit $X $, $Y $ e $Z $ sono rappresentati in Q # dalle operazioni intrinseche `X` , `Y` e `Z` , ognuno dei quali è di tipo `(Qubit => Unit is Adj + Ctl)` .
Come descritto in [operazioni e funzioni intrinseche](xref:microsoft.quantum.libraries.standard.prelude), è possibile pensare a $X $ e, di conseguenza, `X` come operazione di capovolgimento di bit o non di controllo.
L' `X` operazione consente di preparare gli Stati del form $ \ket{s_0 s_1 \dots S_n} $ per una stringa di bit classica $s $:

```qsharp
operation PrepareBitString(bitstring : Bool[], register : Qubit[]) : Unit
is Adj + Ctl {
    let nQubits = Length(register);
    for (idxQubit in 0..nQubits - 1) {
        if (bitstring[idxQubit]) {
            X(register[idxQubit]);
        }
    }
}

operation RunExample() : Unit {
    using (register = Qubit[8]) {
        PrepareBitString(
            [true, true, false, false, true, false, false, true],
            register
        );
        // At this point, register now has the state |11001001〉.
        // Resetting the qubits will allow us to deallocate them properly.
        ResetAll(register);
    }
}
```

> [!TIP]
> In un secondo momento, verrà illustrato come scrivere questa operazione in modo più compatto che non richiede il controllo di flusso manuale.

È anche possibile preparare gli Stati, ad esempio $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ e $ \ket {-} = \left (\ket {0} -\ket {1} \right)/\sqrt {2} $ usando la trasformazione Hadamard $H $, rappresentata in Q # dall'operazione intrinseca `H : (Qubit => Unit is Adj + Ctl)` :

```qsharp
operation PreparePlusMinusState(bitstring : Bool[], register : Qubit[]) : Unit {
    // First, get a computational basis state of the form
    // |s_0 s_1 ... s_n〉 by using PrepareBitString, above.
    PrepareBitString(bitstring, register);
    // Next, we use that |+〉 = H|0〉 and |-〉 = H|1〉 to
    // prepare the state we want.
    for (idxQubit in IndexRange(register)) {
        H(register[idxQubit]);
    }
}
```

## <a name="measurements"></a>Misurazioni

Utilizzando l' `Measure` operazione, che è un'operazione intrinseca non unitaria incorporata, è possibile estrarre le informazioni classiche da un oggetto di tipo `Qubit` e assegnare un valore classico come risultato, che ha un tipo riservato `Result` , che indica che il risultato non è più uno stato quantum.
L'input per `Measure` è un asse di Pauli sulla sfera Bloch, rappresentato da un valore di tipo `Pauli` (ad esempio `PauliX` ) e un valore di tipo `Qubit` .

Un esempio semplice è l'operazione seguente, che alloca un qubit nello stato $ \ket {0} $, quindi applica un'operazione Hadamard `H` e misura il risultato in `PauliZ` base a.

```qsharp
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now we measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // we reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, we return the result of the measurement.
        return result;
    }
}
```

Un esempio leggermente più complesso viene fornito dalla seguente operazione, che restituisce il valore booleano `true` se tutti qubits in un registro di tipo `Qubit[]` si trovano nello stato zero se misurato in base a Pauli specificato e che restituisce in `false` caso contrario.

```qsharp
operation MeasureIfAllQubitsAreZero(qubits : Qubit[], pauli : Pauli) : Bool {
    mutable value = true;
    for (qubit in qubits) {
        if (Measure([pauli], [qubit]) == One) {
            set value = false;
        }
    }
    return value;
}
```

## <a name="borrowing-qubits-example"></a>Esempio di qubits in prestito

In Canon sono disponibili esempi che usano la `borrowing` parola chiave, ad esempio la funzione `MultiControlledXBorrow` definita di seguito.
Se `controls` denota il qubits di controllo che deve essere aggiunto a un' `X` operazione, viene aggiunta una quantità complessiva di `Length(controls)-2` ancillas Dirty da questa implementazione.

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

Si noti che l'utilizzo estensivo del `With` combinatore---nel formato applicabile per le operazioni che supportano contigut, ad esempio `WithA` ---è stato creato in questo esempio.
Si tratta di uno stile di programmazione efficace, perché l'aggiunta del controllo alle strutture che coinvolgono `With` propaga il controllo solo all'operazione interna.
Si noti inoltre che qui, oltre alla `body` dell'operazione, un'implementazione del `controlled` corpo dell'operazione è stata fornita in modo esplicito, anziché ricorrere a un' `controlled auto` istruzione.
Il motivo è che la struttura del circuito illustra come aggiungere facilmente ulteriori controlli, che risulta vantaggioso rispetto all'aggiunta di un controllo a ogni singolo controllo nella `body` . 

È istruttivo confrontare questo codice con un'altra funzione Canon, `MultiControlledXClean` ottenendo allo stesso tempo lo stesso obiettivo di implementare un'operazione a controllo multiplo, `X` che usa diversi qubits puliti usando il `using` meccanismo. 

## <a name="next-steps"></a>Passaggi successivi

Informazioni sul [flusso di controllo](xref:microsoft.quantum.guide.controlflow) in Q #.