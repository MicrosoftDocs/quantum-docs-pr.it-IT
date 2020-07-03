---
title: Uso dei qubit
description: Descrizione riempimento
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
ms.openlocfilehash: 1655d18ab9d8638ad356e6fb90994b5c1fd76a25
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2020
ms.locfileid: "85885300"
---
# <a name="working-with-qubits"></a>Uso dei qubit

Qubits sono l'oggetto fondamentale delle informazioni in quantum computing. Per un'introduzione generale a qubits, vedere [informazioni sul quantum computing](xref:microsoft.quantum.overview.understanding)e approfondimento sulla relativa rappresentazione matematica, vedere [qubit](xref:microsoft.quantum.concepts.qubit). 

Questo articolo illustra come usare e usare qubits in un programma Q #. 

> [!IMPORTANT]
>Nessuna delle istruzioni descritte in questo articolo è valida all'interno del corpo di una funzione. Sono valide solo all'interno delle operazioni.

## <a name="allocating-qubits"></a>Allocazione di qubits

Poiché i qubits fisici rappresentano una risorsa preziosa in un computer Quantum, parte del processo del compilatore consiste nel verificare che vengano usati nel modo più efficiente possibile.
Di conseguenza, è necessario indicare a Q # di *allocare* qubits per l'uso in un blocco di istruzioni specifico.
È possibile allocare qubits come singolo qubit o come matrice di qubits, noto come *Registro*. 

### <a name="clean-qubits"></a>Pulisci qubits

Utilizzare l' `using` istruzione per allocare nuovi qubits da utilizzare durante un blocco di istruzioni.

L'istruzione è costituita dalla parola chiave `using` , seguita da un'associazione racchiusa tra parentesi `( )` e dal blocco di istruzioni all'interno del quale sono disponibili i qubits.
Il binding segue lo stesso modello delle `let` istruzioni, ovvero un singolo simbolo o una tupla di simboli, seguito da un segno di uguale `=` e da un singolo valore o da una tupla corrispondente di *inizializzatori*.

Gli inizializzatori sono disponibili per un singolo qubit, indicato come `Qubit()` o una matrice di qubits, `Qubit[n]` , dove `n` è un' `Int` espressione.
Ad esempio:

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```

Tutti i qubits allocati in questo modo iniziano con lo stato $ \ket {0} $. Nell'esempio precedente, quindi, `auxiliary` è un singolo qubit nello stato $ \ket {0} $ e `register` si trova nello stato Five-qubit $ \ket {00000} = \ket \otimes {0} {0} \ket \otimes \cdots \otimes \ket {0} $.
Alla fine del `using` blocco, qualsiasi qubits allocato dal blocco viene immediatamente deallocato e non può essere usato ulteriormente.

> [!WARNING]
> I computer di destinazione possono riutilizzare qubits deallocati e offrirli ad altri `using` blocchi per l'allocazione. Di conseguenza, il computer di destinazione prevede che qubits si trovino nello stato $ \ket {0} $ immediatamente prima della deallocazione.
> Quando possibile, usare le operazioni unitarie per restituire qualsiasi qubits allocato a $ \ket {0} $.
> Se necessario, è possibile usare l' @"microsoft.quantum.intrinsic.reset" operazione, che restituisce il valore di qubit a $ \ket {0} $ misurando ed eseguendo in modo condizionale un'operazione in base al risultato. Tale misurazione elimina qualsiasi groviglio con i restanti qubits e può quindi influisca sul calcolo.


### <a name="borrowed-qubits"></a>Qubits preso in prestito

Usare l' `borrowing` istruzione per allocare qubits per l'uso temporaneo, che non devono essere in uno stato specifico.

Durante un calcolo, è possibile usare qubits in prestito come spazio scratch.
Questi qubits in genere non sono in uno stato pulito, ovvero non vengono necessariamente inizializzati in uno stato noto, ad esempio $ \ket {0} $.
Queste sono spesso denominate qubits "Dirty" perché il loro stato è sconosciuto e può anche essere aggrovigliato con altre parti della memoria del computer Quantum.

L'associazione segue lo stesso modello e le stesse regole dell' `using` istruzione.
Ad esempio:
```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```
I qubits presi in prestito sono in uno stato sconosciuto e non rientrano nell'ambito alla fine del blocco di istruzioni.
Il mutuatario si impegna a lasciare il qubits nello stesso stato in cui si trovava al momento del prestito; ovvero, il loro stato all'inizio e alla fine del blocco di istruzioni deve essere lo stesso.
Poiché questo stato non è necessariamente uno stato classico, nella maggior parte dei casi gli ambiti in prestito non devono contenere misurazioni. 

Quando si prende in prestito qubits, il sistema tenta innanzitutto di compilare la richiesta da qubits in uso, ma non è possibile accedervi durante il corpo dell' `borrowing` istruzione.
Se il qubits non è sufficiente, viene allocato il nuovo qubits per completare la richiesta.

Tra i casi d'uso noti dei qubits Dirty sono implementazioni di controlli CNOT multicontrollati che richiedono solo pochi qubits e implementazioni di incrementatori.
Per un esempio di uso in Q #, vedere l' [esempio relativo a borrowing qubits](#borrowing-qubits-example) in questo articolo o il [*factoring della carta che usa 2n + 2 qubits con moltiplicazione modulare basata su Toffoli*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler e Svore 2017) per un algoritmo che usa qubits in prestito.

## <a name="intrinsic-operations"></a>Operazioni intrinseche

Una volta allocato, è possibile passare un qubit a funzioni e operazioni.
In un certo senso, questo è tutto ciò che può fare un programma Q # con un qubit, in quanto le azioni che è possibile eseguire sono tutte definite come operazioni.

Questo articolo illustra alcune utili operazioni Q # che è possibile usare per interagire con qubits.
Per informazioni più dettagliate su queste e altre, vedere [operazioni e funzioni intrinseche](xref:microsoft.quantum.libraries.standard.prelude). 

In primo luogo, gli operatori di Pauli Single-qubit $X $, $Y $ e $Z $ sono rappresentati in Q # dalle operazioni intrinseche [`X`](xref:microsoft.quantum.intrinsic.x) , [`Y`](xref:microsoft.quantum.intrinsic.y) e [`Z`](xref:microsoft.quantum.intrinsic.z) , ognuno dei quali è di tipo `(Qubit => Unit is Adj + Ctl)` .

Come descritto in [operazioni e funzioni intrinseche](xref:microsoft.quantum.libraries.standard.prelude), si pensi a $X $ e quindi a `X` un'operazione di capovolgimento di bit o non di controllo.
È possibile usare l' `X` operazione per preparare gli Stati nel formato $ \ket{s_0 s_1 \dots S_n} $ per una stringa di bit classica $s $:

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
        // Remember to reset the qubits before deallocation:
        ResetAll(register);
    }
}
```

> [!TIP]
> In un secondo momento, verrà illustrato come scrivere questa operazione in modo più compatto che non richiede un flusso di controllo manuale.

È inoltre possibile preparare Stati quali $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ e $ \ket {-} = \left (\ket {0} -\ket {1} \right)/\sqrt $ utilizzando {2} la trasformazione Hadamard $H $, che è rappresentata in Q # dall'operazione intrinseca [`H`](xref:microsoft.quantum.intrinsic.h) (anche di tipo (qubit => unità è ADJ + CTL)'):

```qsharp
operation PreparePlusMinusState(bitstring : Bool[], register : Qubit[]) : Unit {
    // First, get a computational basis state of the form
    // |s_0 s_1 ... s_n〉 by using PrepareBitString in the earlier example.
    PrepareBitString(bitstring, register);
    // Next, use that |+〉 = H|0〉 and |-〉 = H|1〉 to
    // prepare the desired state.
    for (idxQubit in IndexRange(register)) {
        H(register[idxQubit]);
    }
}
```

## <a name="measurements"></a>Misurazioni

Le misurazioni dei singoli qubits possono essere eseguite in basi diverse, ciascuna rappresentata da un asse di Pauli nella [sfera Bloch](xref:microsoft.quantum.glossary#bloch-sphere).
La base *computazionale* si riferisce alla `PauliZ` base ed è la base più comune utilizzata per la misurazione.

### <a name="measure-a-single-qubit-in-the-pauliz-basis"></a>Misurare un singolo qubit di `PauliZ` base

Usare l' [`M`](xref:microsoft.quantum.intrinsic.m) operazione, che è un'operazione intrinseca non unitaria incorporata, per misurare un singolo qubit di `PauliZ` base e assegnare un valore classico al risultato.
`M`dispone di un tipo restituito riservato, `Result` , che può assumere solo valori `Zero` o `One` corrispondenti agli stati misurati $ \ket {0} $ o $ \ket {1} $, a indicare che il risultato non è più uno stato quantum.

Un esempio semplice è l'operazione seguente, che alloca un qubit nello stato $ \ket {0} $, quindi applica un'operazione Hadamard `H` e misura il risultato in `PauliZ` base a.

```qsharp
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // Apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, return the result of the measurement.
        return result;
    }
}
```

### <a name="measure-one-or-more-qubits-in-specific-bases"></a>Misurare uno o più qubits in basi specifiche

Per misurare una matrice di uno o più qubits in basi specifiche, è possibile usare l' [`Measure`](xref:microsoft.quantum.intrinsic.measure) operazione.

Gli input per `Measure` sono una matrice di `Pauli` tipi (ad esempio, `[PauliX, PauliZ, PauliZ]` ) e una matrice di qubits.

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

Si noti che questo esempio viene ancora eseguito solo `Measure` su singoli qubits uno alla volta, ma è possibile estendere l'operazione in misurazioni congiunte su più qubits.

## <a name="borrowing-qubits-example"></a>Esempio di qubits in prestito

Sono disponibili esempi nella canonica che usano la `borrowing` parola chiave, ad esempio la funzione seguente `MultiControlledXBorrow` . Se `controls` denota il qubits di controllo da aggiungere a un' `X` operazione, il numero di [ancillas](xref:microsoft.quantum.glossary#ancilla) Dirty aggiunto da questa implementazione è `Length(controls)-2` .

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

Si noti che in questo esempio è stato usato l'uso estensivo di `With` Combinator, nel formato applicabile per le operazioni che supportano il tipo adiacente, ad esempio `WithA` .
Si tratta di uno stile di programmazione efficace, perché l'aggiunta del controllo alle strutture che coinvolgono `With` propaga il controllo solo all'operazione interna.
Si noti inoltre che, oltre all'oggetto `body` dell'operazione, un'implementazione del `controlled` corpo dell'operazione è stata fornita in modo esplicito, anziché ricorrere a un' `controlled auto` istruzione.
Questo è il motivo per cui, a causa della struttura del circuito, è facile aggiungere altri controlli, il che risulta vantaggioso rispetto all'aggiunta di un controllo a ogni gate in `body` . 

È istruttivo confrontare questo codice con un'altra funzione Canon, `MultiControlledXClean` ottenendo allo stesso tempo lo stesso obiettivo di implementare un'operazione a controllo multiplo, `X` che usa diversi qubits puliti usando il `using` meccanismo. 

## <a name="next-steps"></a>Passaggi successivi

Informazioni sul [flusso di controllo](xref:microsoft.quantum.guide.controlflow) in Q #.