---
title: Uso di qubits
description: 'Uso delle tecniche qubits-Q #'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.qubits
ms.openlocfilehash: dc6db93dadc37534aece9624fe516125d919f8cd
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76819995"
---
# <a name="working-with-qubits"></a>Uso di qubits

Avendo visto una serie di diverse parti del linguaggio Q #, è possibile passare al suo interno e vedere come usare qubits.

## <a name="allocating-qubits"></a>Allocazione di qubits

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

## <a name="intrinsic-operations"></a>Operazioni intrinseche

Una volta allocato, un qubit può quindi essere passato a funzioni e operazioni.
In un certo senso, questo è tutto ciò che può fare un programma Q # con un qubit, in quanto le azioni che è possibile eseguire sono tutte definite come operazioni.
Queste operazioni verranno visualizzate in modo più dettagliato nelle [operazioni e funzioni intrinseche](xref:microsoft.quantum.libraries.standard.prelude), ma per il momento si menzioneranno alcune operazioni utili che possono essere usate per interagire con qubits.

In primo luogo, gli operatori di Pauli Single-qubit $X $, $Y $ e $Z $ sono rappresentati in Q # dalle operazioni intrinseche `X`, `Y`e `Z`, ognuno dei quali ha un tipo `(Qubit => Unit is Adj + Ctl)`.
Come descritto in [operazioni e funzioni intrinseche](xref:microsoft.quantum.libraries.standard.prelude), è possibile pensare a $X $ e quindi di `X` come operazione di capovolgimento di bit o non di controllo.
L'operazione di `X` consente di preparare gli Stati nel formato $ \ket{s_0 s_1 \dots s_n} $ per una stringa di bit classica $s $:

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

È inoltre possibile preparare gli Stati, ad esempio $ \ket{+} = \left (\ket{0} + \ket{1}\right)/\sqrt{2}$ e $ \ket{-} = \left (\ket{0}-\ket{1}\right)/\sqrt{2}$ utilizzando la trasformazione Hadamard $H $, che è rappresentata in Q # dall'operazione intrinseca `H : (Qubit => Unit is Adj + Ctl)`:

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

Utilizzando l'operazione di `Measure`, che è un'operazione intrinseca non unitaria incorporata, è possibile estrarre le informazioni classiche da un oggetto di tipo `Qubit` e assegnare un valore classico come risultato, che ha un tipo riservato `Result`, a indicare che il risultato non è più uno stato quantum.
L'input per `Measure` è un asse di Pauli nella sfera Bloch, rappresentato da un valore di tipo `Pauli` (ad esempio `PauliX`) e un valore di tipo `Qubit`.

Un esempio semplice è l'operazione seguente, che alloca un qubit nello stato $ \ket{0}$, quindi applica un'operazione Hadamard `H` e misura il risultato nella `PauliZ` base.

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

Un esempio leggermente più complesso viene fornito dalla seguente operazione, che restituisce il valore booleano `true` se tutti i qubits in un registro di tipo `Qubit[]` sono nello stato zero se misurato in base a Pauli specificato e che restituisce `false` in caso contrario.

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

Il linguaggio Q # consente a un flusso di controllo classico di dipendere dai risultati della misurazione di qubits.
Questa funzionalità consente, a sua volta, di implementare potenti gadget probabilistici che possono ridurre il costo computazionale per l'implementazione di unitaries.
Ad esempio, è facile implementare i cosiddetti modelli di *ripetizione fino al successo* (UR) in Q #.
Questi modelli di ur sono programmi probabilistici che hanno un basso costo *previsto* in termini di attività di controllo elementari, ma per il quale il costo effettivo dipende da un'esecuzione effettiva e da un effettivo interfoliazione delle diverse branche possibili.

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

dove `statementBlock1` e `statementBlock2` sono zero o più istruzioni Q # e `expression` qualsiasi espressione valida che restituisca un valore di tipo `Bool`.
In un caso di utilizzo tipico, l'operazione Q # seguente implementa una rotazione intorno a un asse irrazionale di $ (I + 2i Z)/\sqrt{5}$ nella sfera Bloch. Questa operazione viene eseguita usando un modello di ur noto:

```qsharp
operation ApplyVRotationUsingRUS(qubit : Qubit) : Unit {
    using (controls = Qubit[2]) {
        ApplyToEachA(H, controls);
        mutable finished = false;
        repeat {
            Controlled X(controls, qubit);
            S(qubit);
            Controlled X(controls, qubit);
            Z(qubit);
        }
        until (finished)
        fixup {
            if (MeasureIfAllQubitsAreZero(controls, PauliX)) {
                set finished = true;
            }
        }
    }
}
```

Questo esempio illustra l'uso di una variabile modificabile `finished` che rientra nell'ambito dell'intero ciclo di ripetizione fino alla correzione e che viene inizializzato prima del ciclo e aggiornato nel passaggio di correzione.

Infine, viene illustrato un esempio di modello ur per preparare uno stato quantico $ \frac{1}{\sqrt{3}} \left (\sqrt{2}\ket{0}+ \ket{1}\right) $, a partire dallo stato $ \ket{+} $.
Vedere anche l' [esempio di unit test fornito con la libreria standard](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+⟩ state.
            AssertProb(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+⟩ state", 1e-10 );
            AssertProb(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+⟩ state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+⟩ state on the auxiliary qubit
            // is 3/4.
            AssertProb(
                [PauliX], [auxiliary], Zero, 3. / 4.,
                "Error: the probability to measure |+⟩ in the first
                auxiliary must be 3/4",
                1e-10);

            // If we get the measurement outcome Zero, we prepare the
            // required state.
            let outcome = Measure([PauliX], [auxiliary]);
        }
        until (outcome == Zero)
        fixup {
            // Bring the auxiliary and target qubits back to |+⟩ state.
            if (outcome == One) {
                Z(auxiliary);
                X(target);
                H(target);
            }
        }
        // Return the auxiliary qubit back to the Zero state.
        H(auxiliary);
    }
}
```

Le caratteristiche programmatiche più importanti illustrate in questa operazione sono un `fixup` più complesso del ciclo, che implica operazioni Quantum e l'utilizzo di istruzioni `AssertProb` per verificare la probabilità di misurare lo stato del quantum in determinati punti specificati del programma.
Per ulteriori informazioni sulle operazioni di [`Assert`](xref:microsoft.quantum.intrinsic.assert) e [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) , vedere anche [test e debug](xref:microsoft.quantum.techniques.testing-and-debugging) .
