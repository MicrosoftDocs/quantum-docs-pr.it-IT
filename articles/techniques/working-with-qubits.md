---
title: Utilizzo di qubits | Microsoft Docs
description: Uso di qubits
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.qubits
ms.openlocfilehash: d1a8ccc9423a9a04e12bc98e3783790232b2f5d8
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183472"
---
# <a name="working-with-qubits"></a>Uso di qubits #

Avendo visto una serie di diverse parti del linguaggio Q #, è possibile passare al suo interno e vedere come usare qubits.

## <a name="allocating-qubits"></a>Allocazione di qubits ##

Per prima cosa, per ottenere un qubit che è possibile usare in Q #, viene *allocato* qubits in un blocco `using`:

```qsharp
using (register = Qubit[5]) {
    // Do stuff...
}
```

Tutti i qubits allocati in questo modo iniziano con lo stato $ \ket{0}$; Nell'esempio precedente `register` si trova quindi nello stato $ \ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.
Alla fine del blocco `using`, qualsiasi qubits allocato da tale blocco viene immediatamente deallocato e non può essere usato ulteriormente.

> [!WARNING]
> I computer di destinazione si aspettano che qubits si trovino nello stato $ \ket{0}$ immediatamente prima della deallocazione, in modo che possano essere riutilizzati e offerti ad altri blocchi `using` per l'allocazione.
> Quando possibile, usare le operazioni unitarie per restituire i qubits allocati a $ \ket{0}$.
> Se necessario, è possibile utilizzare l'operazione @"microsoft.quantum.intrinsic.reset" per misurare un qubit e utilizzare tale risultato per garantire che il valore di qubit misurato venga restituito a $ \ket{0}$. Una misura di questo tipo eliminerà eventuali problemi con i restanti qubits e può quindi influisca sul calcolo. 

## <a name="intrinsic-operations"></a>Operazioni intrinseche ##

Una volta allocato, un qubit può quindi essere passato a funzioni e operazioni.
In un certo senso, questo è tutto ciò che può fare un programma Q # con un qubit, in quanto le azioni che è possibile eseguire sono tutte definite come operazioni.
Queste operazioni verranno visualizzate in modo più dettagliato nelle [operazioni e funzioni intrinseche](xref:microsoft.quantum.libraries.standard.prelude), ma per il momento si menzioneranno alcune operazioni utili che possono essere usate per interagire con qubits.

In primo luogo, gli operatori di Pauli Single-qubit $X $, $Y $ e $Z $ sono rappresentati in Q # dalle operazioni intrinseche `X`, `Y`e `Z`, ognuno dei quali ha un tipo `(Qubit => Unit is Adj + Ctl)`.
Come descritto in [operazioni e funzioni intrinseche](xref:microsoft.quantum.libraries.standard.prelude), è possibile pensare a $X $ e quindi di `X` come operazione di capovolgimento di bit o non di controllo.
In questo modo è possibile preparare gli Stati del form $ \ket{s_0 s_1 \dots S_n} $ per una stringa di bit classica $s $:

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

operation Example() : Unit {

    using (register = Qubit[8]) {
        PrepareBitString(
            [true, true, false, false, true, false, false, true],
            register
        );
        // At this point, register now has the state |11001001〉.
    }
}
```

> [!TIP]
> In un secondo momento, verrà illustrato come scrivere questa operazione in modo più compatto che non richiede il controllo di flusso manuale.

È inoltre possibile preparare gli Stati, ad esempio $ \ket{+} = \left (\ket{0} + \ket{1}\right)/\sqrt{2}$ e $ \ket{-} = \left (\ket{0}-\ket{1}\right)/\sqrt{2}$ utilizzando la trasformazione Hadamard $H $ , rappresentato in Q # dall'operazione intrinseca `H : (Qubit => Unit is Adj + Ctl)`:

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

## <a name="measurements"></a>Measurements (Misure) ##

Utilizzando l'operazione di `Measure`, ovvero un'operazione intrinseca non unitaria incorporata, è possibile estrarre le informazioni classiche da un oggetto di tipo `Qubit` e assegnare un valore classico come risultato, che ha un tipo riservato `Result`, a indicare che il risultato è no. più uno stato quantum. L'input per `Measure` è un asse di Pauli nella sfera Bloch, rappresentato da un oggetto di tipo `Pauli` (ad esempio, per `PauliX`di istanza) e da un oggetto di tipo `Qubit`. 

Un esempio semplice è l'operazione seguente che crea un qubit nello stato $ \ket{0}$, quindi applica una ``H`` Gate di Hadamard e quindi misura il risultato in base `PauliZ`. 

```qsharp
operation MeasurementOneQubit () : Result {

    // The following using block creates a fresh qubit and initializes it 
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby creating the 
        // state 1/sqrt(2)(|0〉+|1〉). 
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

Un esempio leggermente più complesso è fornito dall'operazione seguente che restituisce il valore booleano `true` se tutti i qubits in un registro di tipo `Qubit[]` sono nello stato zero, se misurato in base a Pauli specificato e `false` in caso contrario. 

```qsharp
operation AllMeasurementsZero (qs : Qubit[], pauli : Pauli) : Bool {

    mutable value = true;
    for (q in qs) {
        if ( Measure([pauli], [q]) == One ) {
            set value = false;
        }
    }
    return value;
}
```

Il linguaggio Q # consente le dipendenze del flusso di controllo classico sui risultati di misurazione di qubits. Questo consente a sua volta di implementare potenti gadget probabilistici che possono ridurre il costo computazionale per l'implementazione di unitaries. Ad esempio, è facile implementare la cosiddetta *ripetizione fino al successo* in Q #, ovvero circuiti probabilistici che hanno un costo basso *previsto* in termini di controllo elementare, ma per il quale il costo effettivo dipende da un'esecuzione effettiva e da un vero e proprio interfoliazione di diversi rami possibili. 

Per semplificare i modelli di ripetizione fino alla riuscita (UR), Q # supporta il costrutto
```qsharp
repeat {
    statementBlock1 
}
until (expression)
fixup {
    statementBlock2
}
```
dove `statementBlock1` e `statementBlock2` sono zero o più istruzioni Q # e `expression` qualsiasi espressione valida che restituisca un valore di tipo `Bool`. In un caso di utilizzo tipico, il circuito seguente implementa una rotazione intorno a un asse irrazionale di $ (I + 2i Z)/\sqrt{5}$ nella sfera Bloch. Questa operazione viene eseguita usando un modello di ur noto: 

```qsharp
operation RUScircuit (qubit : Qubit) : Unit {

    using(ancillas = Qubit[2]) {
        ApplyToEachA(H, ancillas);
        mutable finished = false;
        repeat {
            Controlled X(ancillas, qubit);
            S(qubit);
            Controlled X(ancillas, qubit);
            Z(qubit);
        }
        until(finished)
        fixup {
            if AllMeasurementsZero(ancillas, Xpauli) {
                set finished = true;
            }
        }
    }
}
```

Questo esempio illustra l'uso di una variabile modificabile `finished` che rientra nell'ambito dell'intero ciclo di ripetizione fino alla correzione e che viene inizializzato prima del ciclo e aggiornato nel passaggio di correzione.

Infine, viene illustrato un esempio di modello ur per preparare uno stato quantico $ \frac{1}{\sqrt{3}} \left (\sqrt{2}\ket{0}+ \ket{1}\right) $, a partire dallo stato $ \ket{+} $. Vedere anche l' [esempio di unit test fornito con la libreria standard](https://github.com/Microsoft/Quantum/blob/master/Samples/src/UnitTesting/RepeatUntilSuccessCircuits.qs): 

```qsharp
operation RepeatUntilSuccessStatePreparation( target : Qubit ) : Unit {

    using( ancilla = Qubit() ) {
        H(ancilla);
        repeat {
            // We expect target and ancilla qubit to be in |+⟩ state.
            AssertProb( 
                [PauliX], [target], Zero, 1.0, 
                "target qubit should be in the |+⟩ state", 1e-10 );
            AssertProb( 
                [PauliX], [ancilla], Zero, 1.0,
                "ancilla qubit should be in the |+⟩ state", 1e-10 );
                
            Adjoint T(ancilla);
            CNOT(target, ancilla);
            T(ancilla);

            // The probability of measuring |+⟩ state on ancilla is 3/4.
            AssertProb( 
                [PauliX], [ancilla], Zero, 3. / 4., 
                "Error: the probability to measure |+⟩ in the first 
                ancilla must be 3/4",
                1e-10);

            // If we get measurement outcome Zero, we prepare the required state 
            let outcome = Measure([PauliX], [ancilla]);
        }
        until( outcome == Zero )
        fixup {
            // Bring ancilla and target back to |+⟩ state
            if( outcome == One ) {
                Z(ancilla);
                X(target);
                H(target);
            }
        }
        // Return ancilla back to Zero state
        H(ancilla);
    }
}
```
 
Le caratteristiche programmatiche più importanti illustrate in questa operazione sono un `fixup` più complesso del ciclo che prevede operazioni Quantum e l'uso di istruzioni `AssertProb` per verificare la probabilità di misurare lo stato del quantum in determinati punti specificati nel programma. Per ulteriori informazioni sulle istruzioni `Assert` e `AssertProb`, vedere anche [test e debug](xref:microsoft.quantum.techniques.testing-and-debugging) . 
