---
title: 'Variabili in Q #'
description: Descrizione riempimento
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.variables
ms.openlocfilehash: 407b4ff3570816eb7bdc323a5c5b77dac2d951af
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430901"
---
# <a name="variables-in-q"></a>Variabili in Q #

Q # distingue tra simboli modificabili e non modificabili o "Variables", che sono associati o assegnati a espressioni.
In generale, l'uso di simboli non modificabili è consigliato perché consente al compilatore di eseguire altre ottimizzazioni.

Il lato sinistro di un'associazione è costituito da una tupla di simboli e dalla parte destra di un'espressione.

## <a name="immutable-variables"></a>Variabili non modificabili

Un valore di qualsiasi tipo in Q # può essere assegnato a una variabile per il riutilizzo all'interno di un'operazione o funzione tramite la `let` parola chiave.

Un'associazione non modificabile è costituita dalla parola chiave `let` , seguita da un simbolo o da una tupla di simboli, un segno di uguale `=` , un'espressione a cui associare i simboli e un punto e virgola di terminazione.

Ad esempio:

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

Questa operazione assegna una matrice specifica di operatori Pauli al nome della variabile (o "symbol"), `measurementOperator` .

> [!NOTE]
> Non è stato necessario specificare in modo esplicito il tipo della nuova variabile, poiché l'espressione sul lato destro dell' `let` istruzione non è ambigua e il tipo viene dedotto dal compilatore. 

Le variabili definite utilizzando `let` non sono *modificabili*, ovvero una volta definito, non possono più essere modificate in alcun modo.
Questo consente diverse ottimizzazioni utili, inclusa l'ottimizzazione della logica classica che agisce sulle variabili da riordinare per l'applicazione della `Adjoint` variante di un'operazione.

## <a name="mutable-variables"></a>Variabili modificabili

In alternativa alla creazione di una variabile con `let` , la `mutable` parola chiave creerà una variabile modificabile che *può* essere riassociata dopo che è stata creata inizialmente con la `set` parola chiave.

I simboli dichiarati e associati come parte di un' `mutable` istruzione possono essere riassociati a un valore diverso in un secondo momento nel codice. Se un simbolo viene riassociato in un secondo momento nel codice, il relativo tipo non viene modificato e il nuovo valore associato deve essere compatibile con quel tipo.

### <a name="rebinding-of-mutable-symbols"></a>Riassociazione di simboli modificabili

Una variabile modificabile può essere riassociata usando un' `set` istruzione.
Tale riassociazione è costituita dalla parola chiave `set` , seguita da un simbolo o da una tupla di simboli, un segno di uguale `=` , un'espressione per riassociare i simboli a e un punto e virgola di terminazione.

Di seguito vengono forniti alcuni esempi possibili di tecniche di riassociazione delle istruzioni

### <a name="apply-and-reassign-statements"></a>Istruzioni Apply-and-reassign

Un particolare tipo di `set` istruzione a cui si fa riferimento come istruzione *Apply-and-reassign* fornisce un modo pratico per la concatenazione se il lato destro è costituito dall'applicazione di un operatore binario e il risultato deve essere riassociato all'argomento a sinistra per l'operatore. Ad esempio,
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
incrementa il valore del contatore `counter` in ogni iterazione del `for` ciclo. Il codice precedente è equivalente a 
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```

Sono disponibili istruzioni simili per tutti gli operatori binari in cui il tipo della parte sinistra corrisponde al tipo di espressione. In questo modo, ad esempio, viene fornito un modo pratico per accumulare i valori.

Ad esempio, supponendo che `qubits` sia un regsiter di qubits:
```qsharp
mutable results = new Result[0];   // results is an empty array of type Result[]
for (q in qubits) {
    set results += [M(q)];         // concatenate the outcome from measuring q to the existing array
    // ...
}
...                                // results contains the measurement outcomes from the whole register
```

### <a name="update-and-reassign-statements"></a>Istruzioni Update e reassign

Esiste una concatenazione simile per le [espressioni di copia e aggiornamento](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) sul lato destro.
Per *gli elementi denominati* nei tipi definiti dall'utente e per *gli elementi della matrice*sono disponibili *le istruzioni Update e reassign* corrispondenti.  

```qsharp
newtype Complex = (Re : Double, Im : Double);

function ComplexSum(reals : Double[], ims : Double[]) : Complex[] {
    mutable res = Complex(0.,0.);

    for (r in reals) {
        set res w/= Re <- res::Re + r; // update-and-reassign statement
    }
    for (i in ims) {
        set res w/= Im <- res::Im + i; // update-and-reassign statement
    }
    return res;
}
```

Nel caso di matrici, [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) nelle librerie standard sono disponibili gli strumenti necessari per molte esigenze comuni di inizializzazione e manipolazione degli array, evitando così di dover aggiornare gli elementi della matrice in primo luogo. 

Le istruzioni Update-and-reassign forniscono un'alternativa se necessario:

```qsharp
operation GenerateRandomInts(max : Int, nSamples : Int) : Int[] {
    mutable samples = new Double[0];
    for (i in 1 .. nSamples) {
        set samples += [RandomInt(max)];
    }
    return samples;
}

operation SampleUniformDistrbution(nSamples : Int, nSteps : Int) : Double[] {
    let normalization = 1. / IntAsDouble(nSteps);
    mutable samples = GenerateRandomInts(nSteps, nSamples);
    
    for (i in IndexRange(samples) {
        let value = IntAsDouble(samples[i]);
        set samples w/= i <- normalization * value; // update-and-reassign statement
    }
}

```

Utilizzando gli strumenti di libreria per le matrici disponibili in [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) , è possibile, ad esempio, definire con facilità una funzione che restituisce una matrice di Paulis in cui Pauli at index `i` accetta il valore specificato e tutte le altre voci sono l'identità.

Di seguito sono riportate due definizioni di una funzione di questo tipo, il secondo sfruttando gli strumenti a disposizione.

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];             // initialize pauliArray of given length
    for (index in 0 .. length - 1) {                    // iterate over the integers in the length range
        set pauliArray w/= index <-                     // change the value at index to input pauli or PauliI
            index == location ? pauli | PauliI;         // cond. expression evaluating to pauli or PauliI dep. on whether index==location
    }    
    return pauliArray;
}
```

Anziché scorrere ogni indice nella matrice e impostarlo in modo condizionale su `PauliI` o, è `Pauli` invece possibile utilizzare `ConstantArray` da [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) per creare una matrice di `PauliI` e quindi restituire semplicemente un'espressione di copia e aggiornamento in cui è stato modificato il valore specifico in corrispondenza dell'indice `location` :

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

## <a name="tuple-deconstruction"></a>Decostruzione di Tuple

Oltre a assegnare una singola variabile, le `let` `mutable` parole chiave e---o in realtà qualsiasi altro costrutto di binding, ad esempio `set` (descritto di seguito)---consente anche di decomprimere il contenuto di un [tipo di tupla](xref:microsoft.quantum.guide.types#tuple-types).
Un'assegnazione di questo form è detta *decostruzione* degli elementi di tale tupla.

Se il lato destro dell'associazione è una tupla, la tupla può essere decostruita al momento dell'assegnazione.
Tali decostruzioni possono coinvolgere Tuple nidificate e qualsiasi decostruzione completa o parziale è valida purché la forma della tupla sulla parte destra sia compatibile con la forma della tupla di simboli.

Ad esempio:

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

## <a name="binding-scopes"></a>Ambiti di associazione

In generale, le associazioni di simboli non rientrano nell'ambito e diventano inattive alla fine del blocco di istruzioni in cui si verificano.
Sono previste due eccezioni a questa regola:

- Il binding della variabile del ciclo di un `for` ciclo è nell'ambito per il corpo del ciclo for, ma non dopo la fine del ciclo.
- Tutte e tre le parti di un `repeat` / `until` ciclo (il corpo, il test e la correzione) vengono trattate come un singolo ambito, quindi i simboli associati nel corpo sono disponibili nel test e nella correzione.

Per entrambi i tipi di cicli, ognuno passa attraverso il ciclo viene eseguito nel proprio ambito, quindi le associazioni da un passaggio precedente non sono disponibili in un passaggio successivo.
I dettagli su questi cicli sono disponibili nel [flusso di controllo](xref:microsoft.quantum.guide.controlflow).

Le associazioni di simboli dei blocchi esterni vengono ereditate da blocchi interni.
Un simbolo può essere associato una sola volta per blocco; non è consentito definire un simbolo con lo stesso nome di un altro simbolo incluso nell'ambito (Nessuna ombreggiatura).
Le sequenze seguenti sarebbero valide:

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

e

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
} else {
    ...
    let n = 8;
    ...             // n is 8
}
...                 // n is not bound to a value
```

Ma non è valido:

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

come:

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="whats-next"></a>Operazioni successive
Informazioni sull' [uso di qubits](xref:microsoft.quantum.guide.qubits) in Q #.