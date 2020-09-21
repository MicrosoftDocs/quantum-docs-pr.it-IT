---
title: Flusso di controllo in Q#
description: Cicli, condizionali e così via
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
no-loc:
- Q#
- $$v
ms.openlocfilehash: 547c57cab67443e8b487bf817eb79fc922b43cdc
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833516"
---
# <a name="control-flow-in-no-locq"></a>Flusso di controllo in Q#

All'interno di un'operazione o di una funzione, ogni istruzione viene eseguita in ordine, in modo analogo ad altri linguaggi classici imperativi comuni.
Tuttavia, è possibile modificare il flusso di controllo in tre modi distinti:

* `if` istruzioni
* `for` cicli
* `repeat-until-success` cicli
* coniugazioni ( `apply-within` istruzioni)

I `if` `for` costrutti del flusso di controllo e procedono in un senso familiare alla maggior parte dei linguaggi di programmazione classici. [`Repeat-until-success`](#repeat-until-success-loop) i cicli e le [coniugazioni](#conjugations) sono descritti più avanti in questo articolo.

In particolare, `for` `if` è possibile usare cicli e istruzioni in operazioni per le quali le [specializzazioni](xref:microsoft.quantum.guide.operationsfunctions) vengono generate automaticamente. In questo scenario, il contiguo di un `for` ciclo inverte la direzione e accetta il contiguo di ogni iterazione.
Questa azione segue il principio "Shoes-and-Socks": se si vuole annullare la messa a punto dei calzini e quindi delle scarpe, è necessario annullare le calzature e quindi annullare l'inserimento sui calzini. 

## <a name="if-else-if-else"></a>Se, else-if, else

L' `if` istruzione supporta l'elaborazione condizionale.
È costituito dalla parola chiave `if` , da un'espressione booleana tra parentesi e da un blocco di istruzioni (il blocco _then_ ).
Facoltativamente, è possibile seguire qualsiasi numero di clausole else-if, ciascuna delle quali è costituita dalla parola chiave `elif` , da un'espressione booleana tra parentesi e da un blocco di istruzioni (il blocco _else-if_ ).
Infine, l'istruzione può terminare facoltativamente con una clausola else, che è costituita dalla parola chiave `else` seguita da un altro blocco Statement (il blocco _else_ ).

La `if` condizione viene valutata e, se è *true*, il blocco *then* viene eseguito.
Se la condizione è *false*, viene valutata la prima condizione else-if; Se è true, viene eseguito il blocco *else-if* .
In caso contrario, il secondo blocco Else-If restituisce, quindi il terzo e così via fino a quando non viene rilevata una clausola con una condizione true o non sono presenti altre clausole else-if.
Se la condizione originale *if* e tutte le clausole else-if restituiscono *false*, viene eseguito il blocco *else* , se specificato.

Si noti che qualunque blocco viene eseguito, viene eseguito all'interno del proprio ambito.
Le associazioni eseguite all'interno di `if` un `elif` blocco, o `else` non sono visibili al termine del blocco.

Ad esempio,

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
oppure
```qsharp
if (i == 1) {
    X(target);
    let n = 1;
} elif (i == 2) {
    Y(target);
    let m = n + 1; // would cause an error, because n is no longer bound
} else {
    Z(target);
}
```

## <a name="for-loop"></a>Ciclo for

L' `for` istruzione supporta l'iterazione su un intervallo di interi o una matrice.
L'istruzione è costituita dalla parola chiave `for` , seguita da un simbolo o da una tupla di simboli, la parola chiave `in` e un'espressione di tipo `Range` o matrice, tutte racchiuse tra parentesi e un blocco di istruzioni.

Il blocco di istruzioni (il corpo del ciclo) viene eseguito ripetutamente, con il simbolo definito (la variabile del ciclo) associato a ogni valore nell'intervallo o nella matrice.
Si noti che se l'espressione di intervallo restituisce un intervallo o una matrice vuota, il corpo non viene eseguito.
L'espressione viene valutata completamente prima dell'immissione del ciclo e non cambia mentre il ciclo è in esecuzione.

La variabile di ciclo viene associata a ogni ingresso al corpo del ciclo e non è associata alla fine del corpo.
La variabile di ciclo non è associata dopo il completamento del ciclo for.
Il binding della variabile del ciclo non è modificabile e segue le stesse regole di altre associazioni variabili. 

In questi esempi, `qubits` è un registro di qubits (ad esempio, di tipo `Qubit[]` ), 

```qsharp
// ...
for (qubit in qubits) {  // iterate over each qubit value in the array qubits
    H(qubit);
}
// 'qubit' is no longer bound

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {  // iterates over the integers in the Range 0 .. (Length(qubits) - 1)
    set results w/= index <- (index, M(qubits[index])); // measure each qubit, updates the tuple value in the results array that at index 
}

mutable accumulated = 0;
for ((index, measured) in results) { // iterates over the tuple values in results
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```

Si noti che alla fine è stato usato l'operatore binario di spostamento a sinistra aritmetico `<<<` . Per altre informazioni, vedere [espressioni numeriche](xref:microsoft.quantum.guide.expressions#numeric-expressions).

## <a name="repeat-until-success-loop"></a>Ciclo repeat-until-Success

Il Q# linguaggio consente a un flusso di controllo classico di dipendere dai risultati della misurazione di qubits.
Questa funzionalità consente, a sua volta, di implementare potenti gadget probabilistici che possono ridurre il costo computazionale per l'implementazione di unitaries.
Esempi di questo sono i modelli di *ripetizione fino alla riuscita* (UR) in Q# .
Questi modelli di ur sono programmi probabilistici che hanno un costo basso *previsto* in termini di controlli elementari; il costo sostenuto dipende dall'esecuzione effettiva e dall'interfoliazione di più Branch possibili.

Per semplificare i modelli di ripetizione fino al completamento (UR), Q# supporta i costrutti

```qsharp
repeat {
    // do stuff
}
until (expression)
fixup {
    // do other stuff
}
```

dove `expression` è qualsiasi espressione valida che restituisce un valore di tipo `Bool` .
Il corpo del ciclo viene eseguito, quindi la condizione viene valutata.
Se la condizione è true, l'istruzione viene completata; in caso contrario, la correzione viene eseguita e l'istruzione viene eseguita nuovamente, a partire dal corpo del ciclo.

Tutte e tre le parti di un ciclo UR (il corpo, il test e la correzione) vengono trattate come un singolo ambito *per ogni ripetizione*, quindi i simboli associati al corpo sono disponibili sia nel test che nella correzione.
Tuttavia, il completamento dell'esecuzione della correzione termina l'ambito dell'istruzione, in modo che le associazioni di simboli effettuate durante il corpo o la correzione non siano disponibili nelle ripetizioni successive.

Inoltre, l' `fixup` istruzione è spesso utile ma non sempre necessaria.
Nei casi in cui non è necessario, il costrutto

```qsharp
repeat {
    // do stuff
}
until (expression);
```

è anche un modello ur valido.

Per altri esempi e dettagli, vedere [esempi di ripetizione fino al](#repeat-until-success-examples) completamento in questo articolo.

> [!TIP]   
> Evitare l'utilizzo di cicli repeat-until-Success all'interno di funzioni. Usare i cicli *while* per fornire la funzionalità corrispondente all'interno di funzioni. 

## <a name="while-loop"></a>Ciclo while

I modelli repeat-until-Success hanno una connotazione molto specifica del quantum. Sono ampiamente usati in particolari classi di algoritmi quantistici, quindi il costrutto di linguaggio dedicato in Q# . Tuttavia, i cicli che si interrompono in base a una condizione e la cui lunghezza di esecuzione è sconosciuta in fase di compilazione, vengono gestiti con particolare attenzione in un runtime Quantum. Tuttavia, l'uso all'interno delle funzioni non è problematico perché questi cicli contengono solo codice eseguito su hardware convenzionale (non Quantum). 

Q#, pertanto, supporta l'utilizzo di cicli while solo all'interno di funzioni.
Un' `while` istruzione è costituita dalla parola chiave `while` , da un'espressione booleana tra parentesi e da un blocco di istruzioni.
Il blocco di istruzioni (il corpo del ciclo) viene eseguito fino a quando la condizione restituisce `true` .

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

## <a name="conjugations"></a>Coniugazioni

A differenza dei bit classici, il rilascio della memoria quantistica è leggermente più coinvolto, perché la reimpostazione cieca di qubits può avere effetti indesiderati sul calcolo rimanente se il qubits è ancora stato impigliato. Questi effetti possono essere evitati eseguendo correttamente l'operazione di calcolo prima di rilasciare la memoria. Un modello comune in quantum computing è quindi il seguente: 

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    outerOperation(target);
    innerOperation(target);
    Adjoint outerOperation(target);
}
```

Q# supporta un'istruzione di coniugazione che implementa la trasformazione precedente. Utilizzando tale istruzione, `ApplyWith` è possibile implementare l'operazione nel modo seguente:

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    within{ 
        outerOperation(target);
    }
    apply {
        innerOperation(target);
    }
}
```
Una tale istruzione di coniugazione diventa utile se le trasformazioni esterne e interne non sono immediatamente disponibili come operazioni, ma sono più convenienti da descrivere da un blocco composto da diverse istruzioni. 

La trasformazione inversa per le istruzioni definite nel blocco interno viene generata automaticamente dal compilatore e viene eseguita al termine del blocco Apply.
Poiché le variabili modificabili usate come parte del blocco all'interno non possono essere riassociati nel blocco Apply, la trasformazione generata è sicuramente l'elemento contiguo del calcolo nel blocco all'interno. 

## <a name="return-statement"></a>Istruzione Return

L'istruzione return termina l'esecuzione di un'operazione o di una funzione e restituisce un valore al chiamante.
È costituito dalla parola chiave `return` , seguita da un'espressione del tipo appropriato e da un punto e virgola di terminazione.

Ad esempio,
```qsharp
return 1;
```
oppure
```qsharp
return (results, qubits);
```

* Un oggetto chiamabile che restituisce una tupla vuota, `()` , non richiede un'istruzione return.
* Per specificare una prima uscita dall'operazione o dalla funzione, usare `return ();` .
Le Callable che restituiscono qualsiasi altro tipo richiedono un'istruzione return finale.
* Non esiste un numero massimo di istruzioni return all'interno di un'operazione.
Il compilatore può generare un avviso se le istruzioni seguono un'istruzione return all'interno di un blocco.

   
## <a name="fail-statement"></a>Istruzione Fail

L'istruzione Fail termina l'esecuzione di un'operazione e restituisce un valore di errore al chiamante.
È costituito dalla parola chiave `fail` , seguita da una stringa e da un punto e virgola di terminazione.
L'istruzione restituisce la stringa al driver classico come messaggio di errore.

Non esiste alcuna restrizione sul numero di istruzioni fail in un'operazione.
Il compilatore può generare un avviso se le istruzioni seguono un'istruzione Fail all'interno di un blocco.

Ad esempio,

```qsharp
fail $"Impossible state reached";
```
oppure, usando [stringhe interpolate](xref:microsoft.quantum.guide.expressions#interpolated-strings),
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a>Esempi di ripetizione fino al completamento

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a>Modello ur per la rotazione a qubit singolo su un asse irrazionale 

In un caso di utilizzo tipico, l' Q# operazione seguente implementa una rotazione intorno a un asse irrazionale di $ (I + 2i Z)/\sqrt {5} $ sulla sfera Bloch. L'implementazione usa un modello di ur noto:

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

### <a name="rus-loop-with-a-mutable-variable-in-scope"></a>Ciclo ur con una variabile modificabile nell'ambito

Questo esempio illustra l'uso di una variabile modificabile, `finished` , che rientra nell'ambito dell'intero ciclo di ripetizione fino alla correzione e che viene inizializzato prima del ciclo e aggiornato nel passaggio di correzione.

```qsharp
mutable iter = 1;
repeat {
    ProbabilisticCircuit(qubits);
    let success = ComputeSuccessIndicator(qubits);
}
until (success || iter > maxIter)
fixup {
    iter += 1;
    ComputeCorrection(qubits);
}
```

### <a name="rus-without-fixup"></a>UR senza `fixup`

Questo esempio mostra un ciclo UR senza il passaggio di correzione. Il codice è un circuito probabilistico che implementa un gate di rotazione importante $V _3 = (\boldone + 2 i Z)/\sqrt {5} $ usando le attività `H` di controllo e `T` .
Il ciclo termina in media le ripetizioni di $ \frac {8} {5} $.
Per informazioni dettagliate, vedere [*repeat-until-Success: scomposizione non deterministica di single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Papini e Svore, 2014).

```qsharp
using (qubit = Qubit()) {
    repeat {
        H(qubit);
        T(qubit);
        CNOT(target, qubit);
        H(qubit);
        Adjoint T(qubit);
        H(qubit);
        T(qubit);
        H(qubit);
        CNOT(target, qubit);
        T(qubit);
        Z(target);
        H(qubit);
        let result = M(qubit);
    } until (result == Zero);
}
```

### <a name="rus-to-prepare-a-quantum-state"></a>UR per preparare uno stato quantico

Infine, di seguito è riportato un esempio di modello ur per preparare uno stato quantico $ \frac {1} {\sqrt {3} } \left (\sqrt {2} \ket {0} + \ket {1} \right) $, a partire dallo stato $ \ket{+} $.

Le funzionalità a livello di codice indicate in questa operazione sono:

* Parte più complessa `fixup` del ciclo, che implica operazioni Quantum. 
* Utilizzo di `AssertMeasurementProbability` istruzioni per verificare la probabilità di misurare lo stato del quantum in determinati punti specificati del programma.

Per ulteriori informazioni sulle [`AssertMeasurement`](xref:microsoft.quantum.diagnostics.assertmeasurement) operazioni e [`AssertMeasurementProbability`](xref:microsoft.quantum.diagnostics.assertmeasurementprobability) , vedere [testing and Debugging](xref:microsoft.quantum.guide.testingdebugging).

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertMeasurementProbability(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertMeasurementProbability(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertMeasurementProbability(
                [PauliX], [auxiliary], Zero, 3. / 4.,
                "Error: the probability to measure |+> in the first
                auxiliary must be 3/4",
                1e-10);

            // If we get the measurement outcome Zero, we prepare the
            // required state.
            let outcome = Measure([PauliX], [auxiliary]);
        }
        until (outcome == Zero)
        fixup {
            // Bring the auxiliary and target qubits back to |+> state.
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

Per ulteriori informazioni, vedere [l'esempio di unit test fornito con la libreria standard](https://github.com/microsoft/Quantum/blob/main/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):

## <a name="next-steps"></a>Passaggi successivi

Informazioni sul [test e il debug](xref:microsoft.quantum.guide.testingdebugging) in Q# .
