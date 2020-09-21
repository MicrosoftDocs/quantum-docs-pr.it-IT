---
title: Variabili in Q#
description: Informazioni su come usare variabili diverse in Q#
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.variables
no-loc:
- Q#
- $$v
ms.openlocfilehash: bb87f36d3c9b7df195f64e85151e833d494ea945
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835877"
---
# <a name="variables-in-no-locq"></a>Variabili in Q#

Q# consente di distinguere tra simboli modificabili e non modificabili oppure *variabili*, associate/assegnate a espressioni.
In generale, l'uso di simboli non modificabili è consigliato perché consente al compilatore di eseguire altre ottimizzazioni.

Il lato sinistro di un'associazione è costituito da una tupla di simboli e dal lato destro di un'espressione.

## <a name="immutable-variables"></a>Variabili non modificabili

È possibile assegnare un valore di qualsiasi tipo in Q# a una variabile per riutilizzarlo all'interno di un'operazione o funzione tramite la `let` parola chiave. 

Un'associazione non modificabile è costituita dalla parola chiave `let` , seguita da un simbolo o da una tupla di simboli, un segno di uguale `=` , un'espressione a cui associare i simboli e un punto e virgola di terminazione.

Ad esempio:

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

Questa operazione assegna una matrice specifica di operatori Pauli al nome della variabile (o "symbol"), `measurementOperator` .

> [!NOTE]
> Nell'esempio precedente non è necessario specificare in modo esplicito il tipo della nuova variabile, poiché l'espressione sul lato destro dell' `let` istruzione non è ambigua e il compilatore deduce il tipo corretto. 

Le variabili definite usando non `let` sono *modificabili*, ovvero una volta definita, non è più possibile modificarla in alcun modo.
Questo consente diverse ottimizzazioni utili, inclusa l'ottimizzazione della logica classica che agisce sulle variabili da riordinare per l'applicazione della `Adjoint` variante di un'operazione.

## <a name="mutable-variables"></a>Variabili modificabili

In alternativa alla creazione di una variabile con `let` , la `mutable` parola chiave crea una variabile modificabile che *può* essere riassociata dopo che è stata creata inizialmente con la `set` parola chiave.

È possibile riassociare i simboli dichiarati e associati come parte di un' `mutable` istruzione a un valore diverso in un secondo momento nel codice. Se un simbolo viene riassociato in un secondo momento nel codice, il relativo tipo non viene modificato e il nuovo valore associato deve essere compatibile con tale tipo.

### <a name="rebinding-of-mutable-symbols"></a>Riassociazione di simboli modificabili

È possibile riassociare una variabile modificabile usando un' `set` istruzione.
Tale riassociazione è costituita dalla parola chiave `set` , seguita da un simbolo o da una tupla di simboli, un segno di uguale `=` , un'espressione per riassociare i simboli a e un punto e virgola di terminazione.

Di seguito sono riportati alcuni esempi di tecniche di riassociazione delle istruzioni.

#### <a name="apply-and-reassign-statements"></a>Istruzioni Apply-and-reassign

Un particolare tipo di `set` istruzione, l'istruzione *Apply-and-reassign* , fornisce un modo pratico per la concatenazione se il lato destro è costituito dall'applicazione di un operatore binario e il risultato deve essere riassociato all'argomento a sinistra per l'operatore. Ad esempio,

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

Sono disponibili istruzioni simili per tutti gli operatori binari in cui il tipo della parte sinistra corrisponde al tipo di espressione. Queste istruzioni costituiscono un modo pratico per accumulare i valori.

Si supponga, ad esempio, che `qubits` sia un registro di qubits:
```qsharp
mutable results = new Result[0];   // results is an empty array of type Result[]
for (q in qubits) {
    set results += [M(q)];         // concatenate the outcome from measuring q to the existing array
    // ...
}
...                                // results contains the measurement outcomes from the whole register
```

#### <a name="update-and-reassign-statements"></a>Istruzioni Update e reassign

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

Nel caso di matrici, [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) nella Q# libreria standard sono disponibili gli strumenti necessari per molte esigenze comuni di inizializzazione e manipolazione degli array e, di conseguenza, evita di dover aggiornare gli elementi della matrice in primo luogo. 

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

Utilizzando gli strumenti di libreria per le matrici disponibili in [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) , è possibile, ad esempio, definire facilmente una funzione che restituisce una matrice di `Pauli` tipi in cui l'elemento in corrispondenza dell'indice `i` accetta un `Pauli` valore specificato e tutte le altre voci sono l'identità ( `PauliI` ).

Di seguito sono riportate due definizioni di una funzione di questo tipo, il secondo sfruttando gli strumenti a disposizione.

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];             // initialize pauliArray of given length
    for (index in 0 .. length - 1) {                    // iterate over the integers in the length range
        set pauliArray w/= index <-                     // change the value at index to input pauli or PauliI
            index == location ? pauli | PauliI;         // cond. expression evaluating to pauli if index==location and PauliI if not
    }    
    return pauliArray;
}
```

Anziché scorrere ogni indice nella matrice e impostarlo in modo condizionale su `PauliI` o sul dato `pauli` , è invece possibile utilizzare `ConstantArray` da [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) per creare una matrice di `PauliI` tipi e quindi restituire semplicemente un'espressione di copia e aggiornamento in cui è stato modificato il valore specifico in corrispondenza dell'indice `location` :

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

## <a name="tuple-deconstruction"></a>Decostruzione di Tuple

Oltre ad assegnare una singola variabile, è possibile usare le `let` `mutable` parole chiave e o qualsiasi altro costrutto di associazione, ad esempio `set` -per decomprimere il contenuto di un [tipo di tupla](xref:microsoft.quantum.guide.types#tuple-types).
Un'assegnazione di questo form è detta *decostruzione* degli elementi di tale tupla.

Se il lato destro dell'associazione è una tupla, è possibile decostruire tale tupla al momento dell'assegnazione.
Tali decostruzioni possono coinvolgere Tuple nidificate e qualsiasi decostruzione completa o parziale è valida purché la forma della tupla sul lato destro sia compatibile con la forma della tupla di simboli.

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
- Tutte e tre le parti di un `repeat` / `until` ciclo (il corpo, il test e la correzione) fungono da singolo ambito, quindi i simboli associati al corpo sono disponibili nel test e nella correzione.

Per entrambi i tipi di cicli, ognuno passa attraverso il ciclo viene eseguito nel proprio ambito, quindi le associazioni da un passaggio precedente non sono disponibili in un passaggio successivo.
Per altre informazioni su questi cicli, vedere [flusso di controllo](xref:microsoft.quantum.guide.controlflow).

I blocchi interni ereditano associazioni di simboli da blocchi esterni.
È possibile associare un simbolo una sola volta per ogni blocco; non è consentito definire un simbolo con lo stesso nome di un altro simbolo incluso nell'ambito (Nessuna ombreggiatura).
Le sequenze seguenti sono valide:

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

## <a name="next-steps"></a>Passaggi successivi

Informazioni sull' [uso di qubits](xref:microsoft.quantum.guide.qubits) in Q# .