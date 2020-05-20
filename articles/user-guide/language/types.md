---
title: Tipi in Q#
description: 'Informazioni sui diversi tipi usati nel linguaggio di programmazione Q #.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
ms.openlocfilehash: 4a551ee90a0abb6e42953cf04c7f5a8ca3573f26
ms.sourcegitcommit: 682a4a5f5dd23ca58a4addf62aea4086bb308552
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609142"
---
# <a name="types-in-q"></a>Tipi in Q#

In questa pagina viene illustrato il modello di tipo Q # e viene descritta la sintassi per specificare e utilizzare i tipi.
Nella pagina successiva, [espressioni di tipo](xref:microsoft.quantum.guide.expressions), viene illustrato in dettaglio come creare e utilizzare espressioni di questi tipi.

Si noti che Q # è un linguaggio *fortemente tipizzato* , in modo che l'utilizzo accurato di questi tipi possa aiutare il compilatore a fornire garanzie complesse sui programmi Q # in fase di compilazione.
Per garantire le migliori garanzie possibili, le conversioni tra i tipi in Q # devono essere esplicite usando chiamate a funzioni che esprimono tale conversione. Una serie di funzioni di questo tipo viene fornita come parte dello <xref:microsoft.quantum.convert> spazio dei nomi.
I cast ai tipi compatibili, invece, si verificano in modo implicito. 

Q # fornisce entrambi i tipi primitivi, che possono essere usati direttamente e diversi modi per produrre nuovi tipi da altri tipi.
Ognuno viene descritto nella parte restante di questa sezione.

## <a name="primitive-types"></a>Tipi primitivi

Il linguaggio Q # offre diversi *tipi primitivi*, da cui è possibile costruire altri tipi:

- Il `Int` tipo rappresenta un intero con segno a 64 bit, ad esempio: `2` , `107` , `-5` .
- Il `BigInt` tipo rappresenta un intero con segno di dimensione arbitraria, ad esempio, `2L` `107L` , `-5L` .
   Questo tipo è basato su .NET<xref:System.Numerics.BigInteger>
   tipo.
- Il `Double` tipo rappresenta un numero a virgola mobile a precisione doppia, ad esempio `0.0` :, `-1.3` , `4e-7` .
- Il `Bool` tipo rappresenta un valore booleano che può essere `true` o `false` .
- Il `Range` tipo rappresenta una sequenza di numeri interi, identificati da `start..step..stop` , in cui la denotazione del passaggio è facoltativa. 
   `start .. stop`Corrisponde a `start..1..stop` e, ad esempio, `1..2..7` rappresenta la sequenza $ \{ 1, 3, 5, 7 \} $.
- Il `String` tipo è una sequenza di caratteri Unicode che è opaca per l'utente dopo la creazione.
  Questo tipo viene usato per segnalare i messaggi a un host classico nel caso di un evento di errore o di diagnostica.
- Il `Unit` tipo è il tipo che consente un solo valore `()` . 
  Questo tipo viene usato per indicare che la funzione o l'operazione Q # non restituisce alcuna informazione. 
- Il `Qubit` tipo rappresenta un bit Quantum o qubit.
   `Qubit`i sono opachi per l'utente; l'unica operazione possibile, ad eccezione del passaggio a un'altra operazione, consiste nel testare l'identità (uguaglianza).
   Infine, le azioni su `Qubit` s vengono implementate chiamando istruzioni intrinseche su un processore quantico (o una simulazione).
- Il `Pauli` tipo rappresenta uno dei quattro operatori Pauli a qubit singola.
   Questo tipo viene utilizzato per indicare l'operazione di base per le rotazioni e per specificare la misura osservabile.
   Si tratta di un tipo enumerato che dispone di quattro valori possibili: `PauliI` , `PauliX` , `PauliY` e `PauliZ` , che sono costanti di tipo `Pauli` .
- Il `Result` tipo rappresenta il risultato di una misura.
   Si tratta di un tipo enumerato con due valori possibili: `One` e `Zero` , che sono costanti di tipo `Result` .
   `Zero`indica che è stato misurato il autovalore + 1; `One`indica il autovalore-1.

Le costanti,,,,,, `true` `false` `PauliI` `PauliX` `PauliY` `PauliZ` `One` e `Zero` sono tutti simboli riservati in Q #.

## <a name="array-types"></a>Tipi di matrice

Dato qualsiasi tipo Q # valido `'T` , esiste un tipo che rappresenta una matrice di valori di tipo `'T` .
Questo tipo di matrice è rappresentato come `'T[]` , ad esempio `Qubit[]` o `Int[][]` .
Ad esempio, viene indicata una raccolta di numeri interi `Int[]` , mentre una matrice di matrici di `(Bool, Pauli)` valori è indicata `(Bool, Pauli)[][]` .

Nel secondo esempio si noti che questo rappresenta una matrice di matrici potenzialmente irregolare e non una matrice bidimensionale rettangolare.
Q # non fornisce il supporto per le matrici multidimensionali rettangolari.

È possibile scrivere un valore di matrice nel codice sorgente Q # usando le parentesi quadre intorno agli elementi di una matrice, come in `[PauliI, PauliX, PauliY, PauliZ]` .
Il tipo di un valore letterale di matrice è determinato dal tipo di base comune di tutti gli elementi nella matrice. 

> [!WARNING]
> Gli elementi di una matrice non possono essere modificati dopo la creazione della matrice.
> Per costruire una matrice modificata è possibile utilizzare le [istruzioni Update-and-reassign](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) e/o le [espressioni di copia e aggiornamento](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) .

In alternativa, è possibile creare una matrice dalle relative dimensioni usando la `new` parola chiave:

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

In entrambi i casi, una volta costruita una matrice, la funzione Core `Length` può essere usata per ottenere il numero di elementi come `Int` .
Le matrici possono essere sottoposte a indicizzazione usando parentesi quadre, con indici con tipo `Int` o tipo `Range` , per ottenere singoli elementi o nuove matrici contenenti un subset degli elementi di una matrice.
Gli indici delle matrici sono in base zero:

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a>Tipi di tupla

Dato zero o più tipi diversi `T0` ,,... `T1` , `Tn` , è possibile indicare un nuovo *tipo di tupla* come `(T0, T1, ..., Tn)` .
I tipi utilizzati per costruire un nuovo tipo di tupla possono essere Tuple, come in `(Int, (Qubit, Qubit))` .
Tale annidamento è sempre finito, tuttavia, in quanto i tipi di tupla non possono in alcun caso contenere se stessi.

I valori del nuovo tipo di tupla sono Tuple costituite da sequenze di valori di ogni tipo nella tupla.
Ad esempio, `(3, false)` è una tupla il cui tipo è il tipo di tupla `(Int, Bool)` .
È possibile creare matrici di tuple, Tuple di matrici, Tuple di sottotuple e così via.

A partire da Q # 0,3, `Unit` è il nome del *tipo* della tupla vuota `()` . viene usato per il *valore*della tupla vuota.

Le istanze di tupla non sono modificabili.
Q # non fornisce un meccanismo per modificare il contenuto di una tupla una volta creata.

Le tuple sono un concetto potente usato in Q # per raccogliere i valori in un unico valore, semplificando il passaggio.
In particolare, usando la notazione di tupla, possiamo esprimere che ogni operazione e Callable accetta esattamente un input e restituisce esattamente un output.

### <a name="singleton-tuple-equivalence"></a>Equivalenza della tupla singleton

È possibile creare una tupla Singleton (elemento singolo), `('T1)` , ad esempio `(5)` o `([1,2,3])` .
Tuttavia, Q # considera una tupla singleton come completamente equivalente a un valore del tipo racchiuso.
Ovvero, non esiste alcuna differenza tra `5` e `(5)` , o tra `5` e `(((5)))` o tra `(5, (6))` e `(5, 6)` .
È altrettanto valido scrivere `(5)+3` come per scrivere `5+3` e entrambe le espressioni restituiranno `8` .

Questa equivalenza si applica a tutti gli scopi, incluse le assegnazioni e le espressioni.
Dato qualsiasi espressione, la stessa espressione racchiusa tra parentesi è un'espressione dello stesso tipo.
Ad esempio, `(7)` è un' `Int` espressione, `([1,2,3])` è un'espressione di tipo matrice di `Int` s e `((1,2))` è un'espressione con tipo `(Int, Int)` .

In particolare, ciò significa che un'operazione o una funzione la cui tupla di input o il tipo di tupla di output ha un campo può essere considerato come accettare un singolo argomento o restituire un singolo valore.

Si fa riferimento a questa proprietà come _equivalenza della tupla singleton_.


## <a name="user-defined-types"></a>Tipi definiti dall'utente

Una dichiarazione del tipo definito dall'utente è costituita dalla parola chiave `newtype` , seguita dal nome del tipo definito dall'utente, da `=` , da una specifica del tipo valida e da un punto e virgola di terminazione.

Ad esempio:

```qsharp
newtype PairOfInts = (Int, Int);
```

Ogni file di origine Q # può dichiarare un numero qualsiasi di tipi definiti dall'utente.
I nomi dei tipi devono essere univoci all'interno di uno spazio dei nomi e non possono entrare in conflitto con i nomi di funzione e

I tipi definiti dall'utente sono distinti anche se i tipi di base sono identici.
In particolare, non viene eseguita alcuna conversione automatica tra i valori di due tipi definiti dall'utente, anche se i tipi sottostanti sono identici.

### <a name="named-vs-anonymous-items"></a>Elementi denominati e anonimi

Un file Q # può definire un nuovo tipo denominato contenente un singolo valore di qualsiasi tipo valido.
Per qualsiasi tipo di tupla `T` , è possibile dichiarare un nuovo tipo definito dall'utente che è un sottotipo di `T` con l' `newtype` istruzione.
Nello @"microsoft.quantum.math" spazio dei nomi, ad esempio, i numeri complessi sono definiti come tipo definito dall'utente:

```qsharp
newtype Complex = (Double, Double);
```
Questa istruzione crea un nuovo tipo con due elementi anonimi di tipo `Double` .   

A parte gli elementi anonimi, i tipi definiti dall'utente supportano anche *gli elementi denominati* a partire da Q # versione 0,7 o successiva. Ad esempio, avremmo potuto denominare gli elementi `Re` per il Double che rappresenta la parte reale di un numero complesso e `Im` per la parte immaginaria: 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
La denominazione di un elemento in un tipo definito dall'utente non implica che tutti gli elementi devono essere denominati. sono supportate tutte le combinazioni di elementi denominati e senza nome. Inoltre, gli elementi interni possono anche essere denominati.
Il tipo `Nested` come definito di seguito, ad esempio, ha un tipo sottostante `(Double, (Int, String))` , di cui solo l'elemento di tipo `Int` è denominato e tutti gli altri elementi sono anonimi. 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

Gli elementi denominati hanno il vantaggio di poter accedere direttamente tramite l' *operatore di accesso* `::` . 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

Oltre a fornire alias brevi per i tipi di tupla potenzialmente complessi, un vantaggio significativo della definizione di tali tipi è che possono documentare lo scopo di un determinato valore.
Tornando all'esempio di `Complex` , è possibile definire anche le coordinate polari 2D come tipo definito dall'utente:

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

Anche se entrambi `Complex` `Polar` i tipi e hanno entrambi un tipo sottostante `(Double, Double)` , i due tipi sono completamente incompatibili in Q #, riducendo al minimo il rischio di chiamare accidentalmente una funzione matematica complessa con coordinate polari e viceversa.
In questo modo, i tipi definiti dall'utente hanno un ruolo simile a quello dei record in F #, ad esempio. 


#### <a name="access-anonymous-items-with-the-unwrap-operator"></a>Accedere a elementi anonimi con l'operatore Unwrap

Per accedere agli elementi anonimi, è necessario innanzitutto estrarre il valore di cui è stato eseguito il wrapped utilizzando l'operatore di suffisso `!` .
L'operatore "Unwrap", `!` , consente di estrarre il valore contenuto in un tipo definito dall'utente.
Il tipo di un'espressione "Unwrap" è il tipo sottostante del tipo definito dall'utente. 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

L'operatore Unwrap Annulla il wrapping di un solo livello di wrapping.
È possibile utilizzare più operatori Unwrap per accedere a un valore con wrapping multiplo.

Ad esempio:

```qsharp
newtype WrappedInt = Int;
newtype DoublyWrappedInt = WrappedInt;

...
    let x = DoublyWrappedInt(WrappedInt(6));
    let y = x!;       // y is WrappedInt(6)
    let z = x!!;      // z is 6
    let a = x + 5;    // This is an error, a DoublyWrappedInt isn't an Int
    let b = x! + 5;   // Also an error
    let c = x!! + 5;  // This is valid, c will be 11
...
```

Altre informazioni sull'operatore unwrap sono disponibili in [espressioni di tipo in Q #](xref:microsoft.quantum.guide.expressions).

### <a name="creating-values-of-user-defined-types"></a>Creazione di valori di tipi definiti dall'utente

I valori di un tipo definito dall'utente possono essere creati chiamando il costruttore del tipo corrispondente:

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

In alternativa, è possibile creare nuovi valori da quelli esistenti usando [le espressioni di copia e aggiornamento](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions). Analogamente alle matrici, tali espressioni copiano tutti i valori degli elementi dell'espressione originale, ad eccezione degli elementi denominati specificati. Per questi valori, i valori vengono impostati su quelli definiti sul lato destro dell'espressione. Tutti gli altri costrutti di linguaggio, come ad esempio le [istruzioni Update-and-reassign](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), disponibili per gli elementi della matrice sono disponibili per gli elementi denominati anche nei tipi definiti dall'utente.

```qsharp
newtype ComplexArray = (Count : Int, Data : Complex[]);

function AsComplexArray (data : Double[]) : ComplexArray {

    mutable res = ComplexArray(0, new Complex[0]);
    for (item in data) {
        set res w/= Data <- res::Data + [Complex(item, 0.)]; // update-and-reassign statement
    }
    return res w/ Count <- Length(res::Data); // returning a copy-and-update expression
}
```

I tipi definiti dall'utente possono essere usati ovunque sia possibile usare qualsiasi altro tipo.
In particolare, è possibile definire una matrice di un tipo definito dall'utente e includere un tipo definito dall'utente come elemento di un tipo di tupla.

Si noti che non è possibile creare strutture di tipo ricorsivo.
Ovvero, il tipo che definisce un tipo definito dall'utente non può essere un tipo di tupla che include un elemento del tipo definito dall'utente.
Più in generale, i tipi definiti dall'utente potrebbero non avere dipendenze cicliche tra loro, quindi il set di definizioni di tipi seguente non è valido:

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```


## <a name="operation-and-function-types"></a>Tipi di operazioni e funzioni

Il tipo di base per qualsiasi chiamata chiamabile viene scritto come `('Tinput => 'Tresult)` o `('Tinput -> 'Tresult)` , dove sia `'Tinput` che `'Tresult` sono tipi.
Questi sono detti *firma* dell'oggetto chiamabile.

Tutti i chiamanti Q # sono considerati come input e restituiscono un singolo valore come output.
Sia i valori di input che quelli di output possono essere Tuple.
Chiamabili senza risultato restituito `Unit` .
Le chiamabili senza input accettano la tupla vuota come input.

> [!NOTE]
> Il primo form, con `=>` , viene usato per le operazioni; la seconda forma, con `->` , per le funzioni.
> Ad esempio, `((Qubit, Pauli) => Result)` rappresenta la firma per una possibile operazione di misurazione a qubit singola.
I tipi di *funzione* sono completamente specificati dalla relativa firma.
Ad esempio, una funzione che calcola il seno di un angolo avrebbe il tipo `(Double -> Double)` .

*Le operazioni*---ma non funzioni---hanno determinate caratteristiche aggiuntive espresse come parte del tipo di operazione. Tali caratteristiche includono informazioni sul *funtori* supportato dall'operazione.
Se, ad esempio, l'esecuzione dell'operazione può essere condizionata allo stato di altri qubits, deve supportare il `Controlled` functor; se l'operazione ha un inverso, deve supportare il `Adjoint` functor. Funtori e le operazioni sono descritte in dettaglio in [operazioni e funzioni in Q #](xref:microsoft.quantum.guide.operationsfunctions), ma in questo articolo viene illustrato semplicemente come questa modifica la firma dell'operazione.

Per richiedere il supporto per `Controlled` e/o `Adjoint` functor in un tipo di operazione, è necessario aggiungere un'annotazione che indichi le caratteristiche corrispondenti.
Un'annotazione `is Ctl` , ad esempio `(Qubit => Unit is Ctl)` , indica che l'operazione è controllabile---ovvero che l'esecuzione è condizionata allo stato di un altro qubit o qubits. Analogamente, `is Adj` indica che l'operazione ha un oggetto adiacente o semplicemente può essere "invertita" in modo che in seguito l'applicazione di un'operazione e quindi il relativo contiguo a uno stato lasci lo stato invariato. 

Se si vuole richiedere che un'operazione di quel tipo supporti sia il `Adjoint` `Controlled` functor che lo si può esprimere come `(Qubit => Unit is Adj + Ctl)` . L'operazione di Pauli incorporata, ad esempio, <xref:microsoft.quantum.intrinsic.x> è di tipo `(Qubit => Unit is Adj + Ctl)` . 

Un tipo di operazione che non supporta alcun funtori viene specificato solo dal tipo di input e di output, senza alcuna annotazione aggiuntiva.

### <a name="type-parameterized-functions-and-operations"></a>Funzioni e operazioni con parametri di tipo

I tipi chiamabili possono contenere parametri di tipo.
I parametri di tipo sono indicati da un simbolo preceduto da una virgoletta singola; ad esempio, `'A` è un parametro di tipo valido.
Informazioni dettagliate sulla definizione di chiamabili con parametri di tipo sono disponibili nelle [operazioni e funzioni nella pagina Q #](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) .

Un parametro di tipo può essere visualizzato più di una volta in un'unica firma.
Ad esempio, una funzione che applica un'altra funzione a ogni elemento di una matrice e restituisce i risultati raccolti avrebbe la firma `(('A[], 'A->'A) -> 'A[])` .
Analogamente, una funzione che restituisce la composizione di due operazioni potrebbe avere la firma `((('A=>'B), ('B=>'C)) -> ('A=>'C))` .

Quando si richiama un oggetto chiamabile con parametri di tipo, tutti gli argomenti che hanno lo stesso parametro di tipo devono essere dello stesso tipo.

Q # non fornisce un meccanismo per vincolare i possibili tipi che possono essere sostituiti per un parametro di tipo.

## <a name="whats-next"></a>Operazioni successive
Ora che sono stati visualizzati tutti i tipi che includono il linguaggio Q #, è possibile passare a [espressioni di tipo in q #](xref:microsoft.quantum.guide.expressions) per vedere come creare e modificare espressioni di questi diversi tipi.


