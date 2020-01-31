---
title: 'Istruzioni Q # | Microsoft Docs'
description: 'Istruzioni Q #'
author: QuantumWriter
uid: microsoft.quantum.language.statements
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 9157cf3336ce0894816dbfbaf13ce0e712a6b096
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821066"
---
# <a name="statements-and-other-constructs"></a>Istruzioni e altri costrutti

## <a name="comments"></a>Commenti

I commenti iniziano con due barre, `//`e continuano fino alla fine della riga.
Un commento può essere visualizzato in qualsiasi punto di un file di origine Q #.

### <a name="documentation-comments"></a>Commenti sulla documentazione

I commenti che iniziano con tre barre, `///`, vengono trattati in modo speciale dal compilatore quando vengono visualizzati immediatamente prima di uno spazio dei nomi, un'operazione, una specializzazione, una funzione o una definizione di tipo.
In tal caso, il contenuto viene considerato come documentazione per il tipo definito chiamabile o definito dall'utente, come per altri linguaggi .NET.

All'interno `///` commenti, il testo da visualizzare come parte della documentazione dell'API è formattato come [Markdown](https://daringfireball.net/projects/markdown/syntax), con diverse parti della documentazione indicate da intestazioni con nome specifico.
Come estensione di Markdown, è possibile includere riferimenti incrociati a operazioni, funzioni e tipi definiti dall'utente in Q # usando il `@"<ref target>"`, in cui `<ref target>` viene sostituito dal nome completo dell'oggetto di codice a cui si fa riferimento.
Facoltativamente, un motore di documentazione può supportare anche estensioni Markdown aggiuntive.

Ad esempio:

```qsharp
/// # Summary
/// Given an operation and a target for that operation,
/// applies the given operation twice.
///
/// # Input
/// ## op
/// The operation to be applied.
/// ## target
/// The target to which the operation is to be applied.
///
/// # Type Parameters
/// ## 'T
/// The type expected by the given operation as its input.
///
/// # Example
/// ```Q#
/// // Should be equivalent to the identity.
/// ApplyTwice(H, qubit);
/// ```
///
/// # See Also
/// - Microsoft.Quantum.Intrinsic.H
operation ApplyTwice<'T>(op : ('T => Unit), target : 'T) : Unit {
    op(target);
    op(target);
}
```

I nomi seguenti sono riconosciuti come intestazioni di commento della documentazione.

- **Riepilogo**: breve riepilogo del comportamento di una funzione o di un'operazione o dello scopo di un tipo. Il primo paragrafo del riepilogo viene usato per le informazioni sul passaggio del mouse. Dovrebbe essere testo normale.
- **Descrizione**: Descrizione del comportamento di una funzione o di un'operazione o dello scopo di un tipo. Il riepilogo e la descrizione vengono concatenati per formare il file di documentazione generato per la funzione, l'operazione o il tipo.
  La descrizione può contenere simboli e equazioni inline in formato LaTeX.
- **Input**: Descrizione della tupla di input per un'operazione o una funzione.
  Può contenere sottosezioni Markdown aggiuntive che indicano ogni singolo elemento della tupla di input.
- **Output**: Descrizione della tupla restituita da un'operazione o da una funzione.
- **Parametri di tipo**: una sezione vuota contenente una sottosezione aggiuntiva per ogni parametro di tipo generico.
- **Esempio**: un breve esempio dell'operazione, della funzione o del tipo in uso.
- **Note**: prosa Miscellanea che descrive alcuni aspetti dell'operazione, della funzione o del tipo.
- **Vedere anche**: elenco di nomi completi che indicano funzioni correlate, operazioni o tipi definiti dall'utente.
- **Riferimenti**: un elenco di riferimenti e citazioni per l'elemento da documentare.

## <a name="namespaces"></a>Spazi dei nomi

Ogni operazione Q #, funzione e tipo definito dall'utente viene definita all'interno di uno spazio dei nomi.
Q # segue le stesse regole per la denominazione degli altri linguaggi .NET.
Tuttavia, Q # non supporta riferimenti relativi agli spazi dei nomi.
Ovvero, se lo spazio dei nomi `a.b` è stato aperto, un riferimento a un nome di operazione `c.d` non verrà risolto in un'operazione con nome completo `a.b.c.d`.

All'interno di un blocco dello spazio dei nomi, è possibile usare la direttiva `open` per importare tutti i tipi e chiamabili dichiarati in un determinato spazio dei nomi e farvi riferimento in base al nome non qualificato. Facoltativamente, è possibile definire un nome breve per lo spazio dei nomi aperto in modo che tutti gli elementi di tale spazio dei nomi possano (e devono) essere qualificati dal nome breve definito. La direttiva `open` si applica all'intero blocco dello spazio dei nomi all'interno di un file.

Il nome completo di un tipo o di una chiamabile definito in un altro spazio dei nomi non aperto nello spazio dei nomi corrente deve essere usato come riferimento.
Ad esempio, è necessario fare riferimento a un'operazione denominata `Op` nello spazio dei nomi `X.Y` mediante il nome completo `X.Y.Op`, a meno che lo spazio dei nomi `X.Y` non sia stato aperto in precedenza nel blocco corrente. Come indicato in precedenza, anche se lo spazio dei nomi `X` è stato aperto, non è possibile fare riferimento all'operazione come `Y.Op`.
Se nel file e nello spazio dei nomi è stato definito un nome breve `Z` per `X.Y`, `Op` necessario denominarlo `Z.Op`. 

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace
}
```

In genere è preferibile includere uno spazio dei nomi utilizzando una direttiva `open`.
L'utilizzo di un nome completo è obbligatorio se due spazi dei nomi definiscono costrutti con lo stesso nome e l'origine corrente utilizza costrutti di entrambi.

## <a name="formatting"></a>Formattazione

La maggior parte delle istruzioni e le direttive Q # terminano con un punto e virgola di terminazione `;`.
Le istruzioni e le dichiarazioni, ad esempio `for` e `operation` che terminano con un blocco di istruzioni, non richiedono un punto e virgola di terminazione.
Ogni descrizione dell'istruzione indica se il punto e virgola di terminazione è obbligatorio.

Le istruzioni, come espressioni, dichiarazioni e direttive, possono essere suddivise in più righe.
Evitare di avere più istruzioni su una sola riga.

## <a name="statement-blocks"></a>Blocchi di istruzioni

Le istruzioni Q # sono raggruppate in blocchi di istruzioni.
Un blocco di istruzioni inizia con un `{` di apertura e termina con una `}`di chiusura.

Un blocco di istruzioni racchiuso in modo lessicale all'interno di un altro blocco viene considerato un sottoblocco del blocco contenitore; gli elementi e i sottoblocchi sono denominati anche blocchi esterni e interni.

## <a name="symbol-binding-and-assignment"></a>Associazione di simboli e assegnazione

Q # distingue tra simboli modificabili e non modificabili.
In generale, l'uso di simboli non modificabili è consigliato perché consente al compilatore di eseguire altre ottimizzazioni.

Il lato sinistro dell'associazione è costituito da una tupla di simboli e dalla parte destra di un'espressione.

Poiché tutti i tipi Q # sono tipi di valore, con il qubits che prende un ruolo speciale in modo formale, una "copia" viene creata quando un valore è associato a un simbolo o quando un simbolo viene riassociato. Ovvero, il comportamento di Q # è identico a quello in cui è stata creata una copia durante l'assegnazione. Questo in particolare include anche matrici. Naturalmente, in pratica, solo le parti pertinenti vengono effettivamente ricreate in base alle esigenze. 

### <a name="tuple-deconstruction"></a>Decostruzione di Tuple

Se il lato destro dell'associazione è una tupla, la tupla può essere decostruita al momento dell'assegnazione.
Tali decostruzioni possono coinvolgere Tuple nidificate e qualsiasi decostruzione completa o parziale è valida purché la forma della tupla sulla parte destra sia compatibile con la forma della tupla di simboli.
La decostruzione di tuple può essere utilizzata in particolare quando il lato destro del `=` è un'espressione con valori di tupla.

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

### <a name="immutable-symbols"></a>Simboli non modificabili

I simboli non modificabili vengono associati utilizzando l'istruzione `let`.
Questo è approssimativamente equivalente alla dichiarazione di variabile e all'inizializzazione in C#linguaggi come, ad eccezione del fatto che i simboli Q #, una volta associati, non possono essere modificati; le associazioni `let` non sono modificabili.

Un'associazione non modificabile è costituita dalla parola chiave `let`, seguita da un simbolo o da una tupla di simboli, un segno di uguale `=`, un'espressione a cui associare i simboli e un punto e virgola di terminazione.
Il tipo dei simboli associati viene dedotto in base all'espressione sul lato destro.

### <a name="mutable-symbols"></a>Simboli modificabili

I simboli modificabili vengono definiti e inizializzati utilizzando l'istruzione `mutable`.
I simboli dichiarati e associati come parte di un'istruzione `mutable` possono essere riassociati a un valore diverso in un secondo momento nel codice. 

Un'istruzione di associazione modificabile è costituita dalla parola chiave `mutable`, seguita da un simbolo o da una tupla di simboli, un segno di uguale `=`, un'espressione a cui associare i simboli e un punto e virgola di terminazione.
Il tipo dei simboli associati viene dedotto in base all'espressione sul lato destro. Se un simbolo viene riassociato in un secondo momento nel codice, il relativo tipo non viene modificato e il valore associato deve essere compatibile con tale tipo.

### <a name="rebinding-of-mutable-symbols"></a>Riassociazione di simboli modificabili

Una variabile modificabile può essere riassociata usando un'istruzione `set`.
Tale riassociazione è costituita dalla parola chiave `set`, seguita da un simbolo o da una tupla di simboli, un segno di uguale `=`, un'espressione per riassociare i simboli a e un punto e virgola di terminazione.
Il valore deve essere compatibile con i tipi dei simboli a cui è associata.

#### <a name="apply-and-reassign-statement"></a>Istruzione Apply-and-reassign

Un particolare tipo di set-Statement a cui si fa riferimento come istruzione Apply-and-reassign fornisce un modo pratico per la concatenazione se il lato destro è costituito dall'applicazione di un operatore binario e il risultato deve essere riassociato all'argomento a sinistra per l'operatore. Ad esempio,
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
incrementa il valore del contatore `counter` in ogni iterazione del ciclo di `for`. Il codice precedente è equivalente a 
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```
Sono disponibili istruzioni simili per tutti gli operatori binari in cui il tipo della parte sinistra corrisponde al tipo di espressione. In questo modo, ad esempio, viene fornito un modo pratico per accumulare i valori:
```qsharp
mutable results = new Result[0];
for (qubit in qubits) {
    set results += [M(q)];
    // ...
}
```
#### <a name="update-and-reassign-statement"></a>Istruzione Update-and-reassign

Esiste una concatenazione simile per le espressioni di copia e aggiornamento sul lato destro. Per gli elementi denominati nei tipi definiti dall'utente e per gli elementi della matrice sono disponibili le istruzioni Update e reassign corrispondenti.  

```qsharp
newtype Complex = (Re : Double, Im : Double);

function ElementwisePlus(reals : Double[], ims : Double[]) : Complex[] {
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

Nel caso di matrici, le librerie standard contengono gli strumenti necessari per molte esigenze comuni di inizializzazione e manipolazione degli array, evitando così di dover aggiornare gli elementi della matrice in primo luogo. Le istruzioni Update-and-reassign forniscono un'alternativa se necessario:

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

> [!TIP]   
> Evitare l'uso non necessario di istruzioni Update e reassign usando gli strumenti disponibili in <xref:microsoft.quantum.arrays>.

Funzione
```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];
    for (index in 0 .. length - 1) {
        set pauliArray w/= index <- 
            index == location ? pauli | PauliI;
    }    
    return pauliArray;
}
```
ad esempio, può essere semplicemente semplificato usando la funzione `ConstantArray` in `Microsoft.Quantum.Arrays`e restituendo un'espressione di copia e aggiornamento:

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

### <a name="binding-scopes"></a>Ambiti di associazione

In generale, le associazioni di simboli non rientrano nell'ambito e diventano inattive alla fine del blocco di istruzioni in cui si verificano.
Sono previste due eccezioni a questa regola:

- Il binding della variabile del ciclo di un ciclo di `for` è nell'ambito del corpo del ciclo for, ma non dopo la fine del ciclo.
- Tutte e tre le parti di un `repeat`/ciclo `until` (il corpo, il test e la correzione) vengono considerati come un singolo ambito, quindi i simboli associati nel corpo sono disponibili nel test e nella correzione.

Per entrambi i tipi di cicli, ognuno passa attraverso il ciclo viene eseguito nel proprio ambito, quindi le associazioni da un passaggio precedente non sono disponibili in un passaggio successivo.

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

## <a name="control-flow"></a>Flusso di controllo

### <a name="for-loop"></a>Ciclo For

L'istruzione `for` supporta l'iterazione su un intervallo di interi o su una matrice.
L'istruzione è costituita dalla parola chiave `for`, da una parentesi di apertura `(`, seguita da un simbolo o da una tupla di simboli, dalla parola chiave `in`, da un'espressione di tipo `Range` o matrice, da una parentesi di chiusura `)`e da un blocco di istruzioni.

Il blocco di istruzioni (il corpo del ciclo) viene eseguito ripetutamente con i simboli definiti (le variabili del ciclo) associati a ogni valore nell'intervallo o nella matrice.
Si noti che se l'espressione di intervallo restituisce un intervallo o una matrice vuota, il corpo non verrà eseguito affatto.
L'espressione viene valutata completamente prima dell'immissione del ciclo e non verrà modificata durante l'esecuzione del ciclo.

L'associazione dei simboli dichiarati non è modificabile e segue le stesse regole di altre associazioni variabili. In particolare, è possibile Destruct, ad esempio, gli elementi di matrice per un'iterazione su una matrice al momento dell'assegnazione alle variabili del ciclo.

Ad esempio,

```qsharp
// ...
for (qubit in qubits) { // qubits contains a Qubit[]
    H(qubit);
}

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {
    set results w/= index <- (index, M(qubits[index]));
}

mutable accumulated = 0;
for ((index, measured) in results) {
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```

La variabile del ciclo è associata a ogni ingresso al corpo del ciclo e non è associata alla fine del corpo.
In particolare, la variabile di ciclo non è associata dopo il completamento del ciclo for.

### <a name="repeat-until-success-loop"></a>Ciclo repeat-until-Success

L'istruzione `repeat` supporta il modello quantum "repeat until Success".
È costituito dalla parola chiave `repeat`, seguita da un blocco di istruzioni (Body del _ciclo_ ), dalla parola chiave `until`, da un'espressione booleana e da un punto e virgola di terminazione o dalla parola chiave `fixup` seguito da un altro blocco di istruzioni (la _correzione_).
Il corpo del ciclo, la condizione e la correzione sono tutti considerati come un singolo ambito, quindi i simboli associati al corpo sono disponibili nella condizione e nella correzione.

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

Il corpo del ciclo viene eseguito, quindi la condizione viene valutata.
Se la condizione è true, l'istruzione viene completata; in caso contrario, la correzione viene eseguita e l'istruzione viene eseguita di nuovo a partire dal corpo del ciclo.
Si noti che il completamento dell'esecuzione della correzione termina l'ambito dell'istruzione, in modo che le associazioni di simboli effettuate durante il corpo o la correzione non siano disponibili nelle ripetizioni successive.

Il codice seguente, ad esempio, è un circuito probabilistico che implementa un controllo di rotazione importante $V _3 = (\boldone + 2 i Z)/\sqrt{5}$ usando i cancelli Hadamard e T.
Il ciclo termina in $ \frac{8}{5}$ ripetizioni in media.
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

> [!TIP]   
> Evitare l'utilizzo di cicli repeat-until-Success all'interno di funzioni. La funzionalità corrispondente viene fornita dai cicli while nelle funzioni. 

### <a name="while-loop"></a>Ciclo while

I modelli repeat-until-Success hanno una connotazione molto specifica del quantum. Sono ampiamente usati in particolari classi di algoritmi quantistici, di conseguenza il costrutto di linguaggio dedicato in Q #. Tuttavia, i cicli che si interrompono in base a una condizione e la cui lunghezza di esecuzione risultano pertanto sconosciuti in fase di compilazione devono essere gestiti con particolare attenzione in un runtime Quantum. Il loro utilizzo all'interno delle funzioni non è problematico, dal momento che contengono solo codice che verrà eseguito su hardware convenzionale (non Quantum). 

Q # supporta pertanto l'utilizzo dei cicli while solo all'interno di funzioni. Un'istruzione `while` è costituita dalla parola chiave `while`, da una parentesi di apertura `(`, da una condizione (ovvero un'espressione booleana), da una parentesi di chiusura `)`e da un blocco di istruzioni.
Il blocco di istruzioni (il corpo del ciclo) viene eseguito finché la condizione restituisce `true`.

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

### <a name="conditional-statement"></a>Istruzione condizionale

L'istruzione `if` supporta l'esecuzione condizionale.
È costituito dalla parola chiave `if`, da una parentesi di apertura `(`, da un'espressione booleana, da una parentesi di chiusura `)`e da un blocco di istruzioni (il blocco _then_ ).
Questo può essere seguito da un numero qualsiasi di clausole else-if, ciascuna delle quali è costituita dalla parola chiave `elif`, da una parentesi di apertura `(`, da un'espressione booleana, da una parentesi di chiusura `)`e da un blocco di istruzioni (il blocco _else-if_ ).
Infine, l'istruzione può terminare facoltativamente con una clausola else, che è costituita dalla parola chiave `else` seguita da un altro blocco Statement (il blocco _else_ ).
La condizione viene valutata e, se è true, il blocco then viene eseguito.
Se la condizione è false, viene valutata la prima condizione else-if; Se è true, il blocco else-if viene eseguito.
In caso contrario, viene testato il secondo blocco else-if, quindi il terzo e così via fino a quando non viene rilevata una clausola con una condizione true o non sono presenti altre clausole else-if.
Se la condizione if originale e tutte le clausole else-if restituiscono false, il blocco Else viene eseguito se ne è stato fornito uno.

Si noti che qualsiasi blocco eseguito viene eseguito nel proprio ambito.
Le associazioni eseguite all'interno di un blocco then, else-if o else non sono visibili dopo la fine dell'istruzione if.

Ad esempio,

```qsharp
if (result == One) {
    X(target);
} 
```

Oppure

```qsharp
if (i == 1) {
    X(target);
} elif (i == 2) {
    Y(target);
} else {
    Z(target);
}
```

### <a name="return"></a>Return

L'istruzione return termina l'esecuzione di un'operazione o di una funzione e restituisce un valore al chiamante.
È costituito dalla parola chiave `return`, seguita da un'espressione del tipo appropriato e da un punto e virgola di terminazione.

Oggetto chiamabile che restituisce una tupla vuota, `()`, non richiede un'istruzione return.
Se si desidera una prima uscita, in questo caso `return ()` possibile utilizzare.
Le Callable che restituiscono qualsiasi altro tipo richiedono un'istruzione return finale.

Non esiste un numero massimo di istruzioni return all'interno di un'operazione.
Il compilatore può generare un avviso se le istruzioni seguono un'istruzione return all'interno di un blocco.

Ad esempio,

```qsharp
return 1;
```

Oppure

```qsharp
return ();
```

Oppure

```qsharp
return (results, qubits);
```

### <a name="fail"></a>Esito negativo

L'istruzione Fail termina l'esecuzione di un'operazione e restituisce un valore di errore al chiamante.
È costituito dalla parola chiave `fail`, seguita da una stringa e da un punto e virgola di terminazione.
La stringa viene restituita al driver classico come messaggio di errore.

Non esiste alcuna restrizione sul numero di istruzioni fail in un'operazione.
Il compilatore può generare un avviso se le istruzioni seguono un'istruzione Fail all'interno di un blocco.

Ad esempio,

```qsharp
fail $"Impossible state reached";
```

Oppure

```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="qubit-management"></a>Gestione qubit

Si noti che nessuna di queste istruzioni è consentita all'interno del corpo di una funzione.
Sono valide solo all'interno delle operazioni.

### <a name="clean-qubits"></a>Pulisci qubits

L'istruzione `using` viene utilizzata per acquisire nuovi qubits da utilizzare durante un blocco di istruzioni.
L'inizializzazione di qubits è garantita per lo stato `Zero` computazionale.
Il qubits deve trovarsi nello stato del `Zero` computazionale alla fine del blocco di istruzioni; i simulatori sono invitati a applicare questa operazione.

L'istruzione è costituita dalla parola chiave `using`, seguita da una parentesi di apertura `(`, da un'associazione, da una parentesi di chiusura `)`e dal blocco di istruzioni in cui qubits sarà disponibile.
Il binding segue lo stesso modello delle istruzioni `let`: un singolo simbolo o una tupla di simboli, seguito da un segno di uguale `=`e da un singolo valore o da una tupla corrispondente di inizializzatori.
Gli inizializzatori sono disponibili per un singolo qubit, indicato come `Qubit()`, o una matrice di qubits, indicata da `Qubit[`, un'espressione `Int` e `]`.

Ad esempio,

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

### <a name="borrowed-qubits"></a>Qubits preso in prestito

L'istruzione `borrowing` viene utilizzata per ottenere qubits per l'utilizzo temporaneo. L'istruzione è costituita dalla parola chiave `borrowing`, seguita da una parentesi di apertura `(`, da un'associazione, da una parentesi di chiusura `)`e dal blocco di istruzioni in cui qubits sarà disponibile.
L'associazione segue lo stesso modello e le stesse regole di un'istruzione `using`.

Ad esempio,

```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

I qubits presi in prestito sono in uno stato sconosciuto e non rientrano nell'ambito alla fine del blocco di istruzioni.
Il mutuatario si impegna a lasciare il qubits nello stesso stato in cui si trovavano quando sono state prese in prestito, ovvero il proprio stato all'inizio e alla fine del blocco di istruzioni deve essere lo stesso.
Questo stato in particolare non è necessariamente uno stato classico, in modo che nella maggior parte dei casi gli ambiti in prestito non contengano misurazioni. 

Per un esempio di uso di Svore in prestito, vedere [*factoring using 2n + 2 qubits with Toffoli Modular based Moltiplication*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler e qubit 2017).

Quando si prendono in prestito qubits, il sistema tenterà innanzitutto di compilare la richiesta da qubits in uso, ma non è possibile accedervi durante il corpo dell'istruzione `borrowing`.
Se il qubits non è sufficiente, verrà allocato il nuovo qubits per completare la richiesta.

## <a name="conjugations"></a>Coniugazioni

A differenza dei bit classici, il rilascio della memoria quantistica è leggermente più coinvolto, perché la reimpostazione cieca di qubits può avere effetti indesiderati sul calcolo rimanente se il qubits è ancora stato impigliato. Questa operazione può essere evitata eseguendo correttamente i calcoli eseguiti prima di rilasciare la memoria. Un modello comune in quantum computing è quindi il seguente: 

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

: nuovo: a partire dalla versione 0,9, è supportata un'istruzione di coniugazione che implementa la trasformazione sopra. Utilizzando tale istruzione, l'operazione `ApplyWith` può essere implementata nel modo seguente:

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
Tale istruzione di coniugazione, ovviamente, diventa molto più utile se la trasformazione esterna e interna non è immediatamente disponibile come operazione, ma è più semplice da descrivere da un blocco composto da diverse istruzioni. 

La trasformazione inversa per le istruzioni definite nel blocco interno viene generata automaticamente dal compilatore ed eseguita al termine del blocco Apply. Poiché le variabili modificabili usate come parte del blocco all'interno non possono essere riassociati nel blocco Apply, la trasformazione generata è sicuramente l'elemento contiguo del calcolo nel blocco all'interno. 

## <a name="expression-evaluation-statements"></a>Istruzioni di valutazione delle espressioni

Qualsiasi espressione di chiamata di tipo `Unit` può essere utilizzata come un'istruzione.
Questa operazione viene utilizzata principalmente quando si chiamano le operazioni su qubits che restituiscono `Unit` perché lo scopo dell'istruzione è modificare lo stato quantum implicito.
Le istruzioni di valutazione dell'espressione richiedono un punto e virgola di terminazione.

Ad esempio,

```qsharp
X(q);
CNOT(control, target);
Adjoint T(q);
```
