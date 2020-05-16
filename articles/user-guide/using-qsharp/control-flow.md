---
title: 'Flusso di controllo in Q #'
description: Cicli, condizionali e così via
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
ms.openlocfilehash: c534e016fcb8b50e66c11ca29c253ba0512acc6e
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430952"
---
# <a name="control-flow-in-q"></a>Flusso di controllo in Q #

All'interno di un'operazione o di una funzione, ogni istruzione viene eseguita in ordine, in modo analogo ai linguaggi classici imperativi più comuni.
Questo flusso di controllo può tuttavia essere modificato in tre modi distinti:

- `if`istruzioni
- `for`cicli
- `repeat`-`until`cicli

Il secondo argomento è rinviato a quanto [segue](#repeat-until-success-loop).
I `if` `for` costrutti del flusso di controllo e, tuttavia, procedono in un senso familiare alla maggior parte dei linguaggi di programmazione classici.

In particolare, `for` `if` è possibile utilizzare cicli e istruzioni anche in operazioni per le quali le specializzazioni vengono generate automaticamente. In tal caso, l'oggetto adiacente di un `for` ciclo inverte la direzione e accetta il contiguo di ogni iterazione.
Segue il principio "Shoes-and-Socks": se si vuole annullare la messa a punto dei calzini e quindi delle scarpe, è necessario annullare le calzature e quindi annullare l'inserimento dei calzini.
Si tratta di un approccio decisamente meno efficace per provare a riportare i calzini quando si indossano ancora le scarpe.

## <a name="if-else-if-else"></a>Se, else-if, else

L' `if` istruzione supporta l'esecuzione condizionale.
È costituito dalla parola chiave, da una `if` parentesi aperta, da un' `(` espressione booleana, da una parentesi di chiusura `)` e da un blocco di istruzioni (il blocco _then_ ).
Questo può essere seguito da un numero qualsiasi di clausole else-if, ciascuna delle quali è costituita dalla parola chiave, da una `elif` parentesi aperta, da un' `(` espressione booleana, da una parentesi di chiusura `)` e da un blocco di istruzioni (il blocco _else-if_ ).
Infine, l'istruzione può terminare facoltativamente con una clausola else, che è costituita dalla parola chiave `else` seguita da un altro blocco Statement (il blocco _else_ ).

La `if` condizione viene valutata e, se è true, il blocco then viene eseguito.
Se la condizione è false, viene valutata la prima condizione else-if; Se è true, il blocco else-if viene eseguito.
In caso contrario, viene testato il secondo blocco else-if, quindi il terzo e così via fino a quando non viene rilevata una clausola con una condizione true o non sono presenti altre clausole else-if.
Se la condizione if originale e tutte le clausole else-if restituiscono false, il blocco Else viene eseguito se ne è stato fornito uno.

Si noti che qualsiasi blocco eseguito viene eseguito nel proprio ambito.
Le associazioni eseguite all'interno di `if` un `elif` blocco, o `else` non sono visibili dopo la relativa fine.

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

## <a name="for-loop"></a>Ciclo For

L' `for` istruzione supporta l'iterazione su un intervallo di interi o su una matrice.
L'istruzione è costituita dalla parola chiave, da una `for` parentesi aperta `(` , seguita da un simbolo o da una tupla di simboli, dalla parola chiave `in` , da un'espressione di tipo `Range` o matrice, da una parentesi di chiusura `)` e da un blocco di istruzioni.

Il blocco di istruzioni (il corpo del ciclo) viene eseguito ripetutamente con i simboli definiti (le variabili del ciclo) associati a ogni valore nell'intervallo o nella matrice.
Si noti che se l'espressione di intervallo restituisce un intervallo o una matrice vuota, il corpo non verrà eseguito affatto.
L'espressione viene valutata completamente prima dell'immissione del ciclo e non verrà modificata durante l'esecuzione del ciclo.

La variabile del ciclo è associata a ogni ingresso al corpo del ciclo e non è associata alla fine del corpo.
In particolare, la variabile di ciclo non è associata dopo il completamento del ciclo for.
L'associazione dei simboli dichiarati non è modificabile e segue le stesse regole di altre associazioni variabili. 

Per alcuni esempi, supponendo che `qubits` sia un registro di qubits (ad esempio, di tipo `Qubit[]` ), 

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
Si noti che alla fine è stato utilizzato l'operatore Binary-Shift-Left Binary, `<<<` , i cui dettagli sono reperibili in [espressioni numeriche](xref:microsoft.quantum.guide.expressions#numeric-expressions)


## <a name="repeat-until-success-loop"></a>Ciclo repeat-until-Success

Il linguaggio Q # consente a un flusso di controllo classico di dipendere dai risultati della misurazione di qubits.
Questa funzionalità consente, a sua volta, di implementare potenti gadget probabilistici che possono ridurre il costo computazionale per l'implementazione di unitaries.
Ad esempio, è facile implementare i cosiddetti modelli di *ripetizione fino al successo* (UR) in Q #.
Questi modelli di ur sono programmi probabilistici che hanno un basso costo *previsto* in termini di attività di controllo elementari, ma per il quale il costo effettivo dipende da un'esecuzione effettiva e da un effettivo interfoliazione delle diverse branche possibili.

Per semplificare i modelli di ripetizione fino alla riuscita (UR), Q # supporta i costrutti

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
Se la condizione è true, l'istruzione viene completata; in caso contrario, la correzione viene eseguita e l'istruzione viene eseguita di nuovo a partire dal corpo del ciclo.

Tutte e tre le parti di un ciclo repeat/until (il corpo, il test e la correzione) vengono considerate come un singolo ambito *per ogni ripetizione*, quindi i simboli associati al corpo sono disponibili nel test e nella correzione.
Il completamento dell'esecuzione della correzione termina tuttavia l'ambito dell'istruzione, in modo che le associazioni di simboli effettuate durante il corpo o la correzione non siano disponibili nelle ripetizioni successive.

Inoltre, l' `fixup` istruzione è spesso utile ma non sempre necessaria.
Nei casi in cui non è necessario, il costrutto
```qsharp
repeat {
    // do stuff
}
until (expression);
```
è anche un modello ur valido.

Nella parte inferiore della pagina vengono presentati alcuni [esempi di cicli ur](#repeat-until-success-examples).

> [!TIP]   
> Evitare l'utilizzo di cicli repeat-until-Success all'interno di funzioni. La funzionalità corrispondente viene fornita dai cicli while nelle funzioni. 

## <a name="while-loop"></a>Ciclo while

I modelli repeat-until-Success hanno una connotazione molto specifica del quantum. Sono ampiamente usati in particolari classi di algoritmi quantistici, di conseguenza il costrutto di linguaggio dedicato in Q #. Tuttavia, i cicli che si interrompono in base a una condizione e la cui lunghezza di esecuzione risultano pertanto sconosciuti in fase di compilazione devono essere gestiti con particolare attenzione in un runtime Quantum. Il loro utilizzo all'interno delle funzioni non è problematico, dal momento che contengono solo codice che verrà eseguito su hardware convenzionale (non Quantum). 

Q # supporta pertanto l'utilizzo dei cicli while solo all'interno di funzioni. Un' `while` istruzione è costituita dalla parola chiave, da una `while` parentesi aperta, da una `(` condizione (ovvero un'espressione booleana), da una parentesi di chiusura `)` e da un blocco di istruzioni.
Il blocco di istruzioni (il corpo del ciclo) viene eseguito finché la condizione restituisce `true` .

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```


## <a name="return-statement"></a>Istruzione Return

L'istruzione return termina l'esecuzione di un'operazione o di una funzione e restituisce un valore al chiamante.
È costituito dalla parola chiave `return` , seguita da un'espressione del tipo appropriato e da un punto e virgola di terminazione.

Un oggetto chiamabile che restituisce una tupla vuota, `()` , non richiede un'istruzione return.
Se si desidera una prima uscita, è `return ()` possibile utilizzare in questo caso.
Le Callable che restituiscono qualsiasi altro tipo richiedono un'istruzione return finale.

Non esiste un numero massimo di istruzioni return all'interno di un'operazione.
Il compilatore può generare un avviso se le istruzioni seguono un'istruzione return all'interno di un blocco.

Ad esempio,
```qsharp
return 1;
```
oppure
```qsharp
return ();
```
oppure
```qsharp
return (results, qubits);
```

## <a name="fail-statement"></a>Istruzione Fail

L'istruzione Fail termina l'esecuzione di un'operazione e restituisce un valore di errore al chiamante.
È costituito dalla parola chiave `fail` , seguita da una stringa e da un punto e virgola di terminazione.
La stringa viene restituita al driver classico come messaggio di errore.

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

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a>Modello ur per la rotazione di una singola qubit su un asse irrazionale 

In un caso di utilizzo tipico, l'operazione Q # seguente implementa una rotazione intorno a un asse irrazionale di $ (I + 2i Z)/\sqrt {5} $ sulla sfera Bloch. Questa operazione viene eseguita usando un modello di ur noto:

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

### <a name="rus-loop-with-mutable-variable-in-scope"></a>Ciclo ur con variabile modificabile nell'ambito

Questo esempio illustra l'uso di una variabile modificabile `finished` che rientra nell'ambito dell'intero ciclo di ripetizione fino alla correzione e che viene inizializzata prima del ciclo e aggiornata nel passaggio di correzione.

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

### <a name="rus-without-fixup"></a>UR senza`fixup`

Il codice seguente, ad esempio, è un circuito probabilistico che implementa un gate di rotazione importante $V _3 = (\boldone + 2 i Z)/\sqrt {5} $ usando le attività `H` di controllo e `T` .
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

Infine, viene illustrato un esempio di modello ur per preparare uno stato quantico $ \frac {1} {\sqrt {3} } \left (\sqrt {2} \ket {0} + \ket {1} \right) $, a partire dallo stato $ \ket{+} $.
Vedere anche l' [esempio di unit test fornito con la libreria standard](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertProb(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertProb(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertProb(
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

Le caratteristiche programmatiche più importanti illustrate in questa operazione sono una parte più complessa `fixup` del ciclo, che include le operazioni Quantum e l'utilizzo di `AssertProb` istruzioni per verificare la probabilità di misurare lo stato del quantum in determinati punti specificati del programma.
Per ulteriori informazioni sulle operazioni e, vedere anche [test e debug](xref:microsoft.quantum.guide.testingdebugging) [`Assert`](xref:microsoft.quantum.intrinsic.assert) [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) .


## <a name="whats-next"></a>Operazioni successive
Informazioni sul [test e il debug](xref:microsoft.quantum.guide.testingdebugging) in Q #.