---
title: 'Espressioni di tipo in Q #'
description: 'Informazioni su come specificare, fare riferimento e combinare costanti, variabili, operatori, operazioni e funzioni come espressioni in Q #.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
ms.openlocfilehash: 1821df6a3a51a62b44f3ccd96b127577c5db990a
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415389"
---
# <a name="type-expressions-in-q"></a>Espressioni di tipo in Q #

## <a name="numeric-expressions"></a>Espressioni numeriche

Le espressioni numeriche sono espressioni di tipo `Int` , `BigInt` o `Double` .
Ovvero sono numeri interi o a virgola mobile.

`Int`i valori letterali in Q # vengono scritti come una sequenza di cifre.
Gli Integer esadecimali e binari sono supportati e scritti rispettivamente con un `0x` `0b` prefisso e.

`BigInt`i valori letterali in Q # hanno un `l` `L` suffisso o finale.
I Big Integer esadecimali sono supportati e scritti con un prefisso "0x".
Di conseguenza, di seguito sono riportati tutti gli utilizzi validi dei `BigInt` valori letterali:

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

`Double`i valori letterali in Q # sono numeri a virgola mobile scritti con cifre decimali.
Possono essere scritti con o senza un separatore decimale, `.` o una parte esponenziale indicata con "e" o "e" (dopo il quale sono validi solo un possibile segno negativo e cifre decimali).
I valori letterali validi sono i seguenti `Double` : `0.0` , `1.2e5` , `1e-5` .

Data un'espressione di matrice di qualsiasi tipo di elemento, è possibile formare un' `Int` espressione usando la [`Length`](xref:microsoft.quantum.core.length) funzione predefinita, con l'espressione di matrice racchiusa tra parentesi.
Se, ad esempio, `a` è associato a una matrice, `Length(a)` sarà un'espressione Integer.
Se `b` è una matrice di matrici di numeri interi, `Int[][]` , `Length(b)` è il numero di sottomatrici in `b` e `Length(b[1])` è il numero di numeri interi nella seconda sottomatrice di `b` .

Date due espressioni numeriche dello stesso tipo, gli operatori binari `+` , `-` , `*` e `/` possono essere usati per formare una nuova espressione numerica.
Il tipo della nuova espressione corrisponde ai tipi delle espressioni costituenti.

Date due espressioni Integer, usare l'operatore binario `^` (Power) per formare una nuova espressione Integer.
Analogamente, è anche possibile usare `^` con due espressioni doppie per formare una nuova espressione doppia.
Infine, è possibile usare `^` con un Big Integer a sinistra e un numero intero a destra per formare una nuova espressione di tipo Integer grande.
In questo caso, il secondo parametro deve adattarsi a 32 bit; in caso contrario, viene generato un errore di Runtime.

Date due espressioni Integer o Big Integer, formano una nuova espressione Integer o Big Integer usando gli `%` operatori (modulo), `&&&` (and bit per bit), `|||` (OR bit per bit) o `^^^` (XOR bit per bit).

Data un'espressione Integer o Big Integer a sinistra e un'espressione Integer a destra, usare gli `<<<` operatori (spostamento aritmetico a sinistra) o `>>>` (spostamento a destra aritmetico) per creare una nuova espressione con lo stesso tipo dell'espressione di sinistra.

Il secondo parametro (l'importo dello spostamento) per l'operazione di spostamento deve essere maggiore o uguale a zero; il comportamento per gli importi di spostamento negativi non è definito.
L'importo dello spostamento per entrambe le operazioni di spostamento deve rientrare anche in 32 bit; in caso contrario, viene generato un errore di Runtime.
Se il numero spostato è un numero intero, l'importo dello spostamento viene interpretato, `mod 64` ovvero uno spostamento di 1 e uno spostamento di 65 hanno lo stesso effetto.

Per i valori integer e Big Integer, i turni sono aritmetici.
Se si sposta un valore negativo, viene restituito un numero negativo, a sinistra o a destra.
Ovvero, lo spostamento di un passaggio verso sinistra o a destra è uguale alla moltiplicazione o alla divisione per 2, rispettivamente.

La divisione Integer e il modulo Integer seguono lo stesso comportamento per i numeri negativi in C#.
Ovvero, `a % b` ha sempre lo stesso segno di `a` ed è `b * (a / b) + a % b` sempre uguale a `a` .
Ad esempio:

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 5 | 2 | 2 | 1
 5 | -2 | -2 | 1
 -5 | 2 | -2 | -1
 -5 | -2 | 2 | -1

Le operazioni di divisione e modulo di tipo Big Integer funzionano allo stesso modo.

Dato qualsiasi espressione numerica, è possibile creare una nuova espressione usando l' `-` operatore unario.
La nuova espressione è dello stesso tipo dell'espressione costituente.

Dato qualsiasi espressione Integer o Big Integer, è possibile creare una nuova espressione dello stesso tipo utilizzando l' `~~~` operatore unario (complemento bit per bit).

## <a name="boolean-expressions"></a>Espressioni booleane

I due `Bool` valori letterali sono `true` e `false` .

Date due espressioni dello stesso tipo primitivo, gli `==` `!=` operatori binari e possono essere usati per costruire un' `Bool` espressione.
L'espressione è true se le due espressioni sono uguali e false in caso contrario.

I valori dei tipi definiti dall'utente non possono essere confrontati, ma è possibile confrontare solo i valori di cui non è stato eseguito il wrapper. Ad esempio, usando l'operatore "Unwrap" `!` (illustrato in dettaglio nei [tipi in Q #](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

Il confronto di uguaglianza per `Qubit` i valori è uguaglianza di identità, ovvero se le due espressioni identificano lo stesso qubit.
Gli Stati dei due qubits non vengono confrontati, accessibili, misurati o modificati da questo confronto.

Il confronto di uguaglianza per `Double` i valori può essere fuorviante a causa degli effetti dell'arrotondamento.
Ad esempio: `49.0 * (1.0/49.0) != 1.0`.

Date due espressioni numeriche, gli operatori binari `>` , `<` , `>=` e `<=` possono essere usati per costruire una nuova espressione booleana che è true se la prima espressione è rispettivamente maggiore di, minore di, maggiore o uguale a o minore o uguale alla seconda espressione.

Date due espressioni booleane, usare l' `and` operatore binario per costruire una nuova espressione booleana che è true se entrambe le espressioni sono true. Analogamente, l'utilizzo dell' `or` operatore crea un'espressione che è true se una delle due espressioni è true.

Dato qualsiasi espressione booleana, l' `not` operatore unario può essere usato per costruire una nuova espressione booleana che è true se l'espressione costituente è false.

## <a name="string-expressions"></a>Espressioni stringa

Q # consente di usare le stringhe nell' `fail` istruzione (spiegate in [flusso di controllo](xref:microsoft.quantum.guide.controlflow#fail-statement)) e nella [`Message`](xref:microsoft.quantum.intrinsic.message) funzione standard. Il comportamento specifico di quest'ultimo dipende dal simulatore usato, ma in genere scrive un messaggio nella console host quando viene chiamato durante un programma Q #.

Le stringhe in Q # sono valori letterali o stringhe interpolate.

I valori letterali stringa sono simili a valori letterali stringa semplici nella maggior parte dei linguaggi, ovvero una sequenza di caratteri Unicode racchiusi tra virgolette doppie `" "` .
All'interno di una stringa, usare il carattere barra rovesciata `\` per eseguire l'escape di un carattere di virgolette doppie ( `\"` ) o per inserire una nuova riga ( `\n` ), un ritorno a capo ( `\r` ) o una tabulazione ( `\t` ).
Ad esempio:

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a>Stringhe interpolate

La sintassi Q # per l'interpolazione di stringhe è un subset della sintassi C#. Di seguito sono riportati i punti chiave relativi a Q #:

* Per identificare un valore letterale stringa come stringa interpolata, anteporre a questa il simbolo `$`. Non può essere presente alcuno spazio vuoto tra `$` e `"` che avvia un valore letterale stringa.

* Di seguito è riportato un esempio di base [`Message`](xref:microsoft.quantum.intrinsic.message) che usa la funzione per scrivere il risultato di una misurazione nella console, insieme ad altre espressioni Q #.

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```

* In una stringa interpolata può essere presente qualsiasi espressione Q # valida.

* Le espressioni all'interno di una stringa interpolata seguono la sintassi Q #, non la sintassi C#. La differenza più importante è che Q # non supporta le stringhe interpolate Verbatim (a più righe).

Per altri dettagli sulla sintassi di C#, vedere [*stringhe interpolate*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).

## <a name="range-expressions"></a>Espressioni di intervallo

Date le tre `Int` espressioni `start` , `step` , e `stop` , l'espressione `start .. step .. stop` è un'espressione di intervallo il cui primo elemento è, il secondo elemento è, il `start` `start+step` terzo elemento è `start+step+step` e così via, fino a quando non viene superato `stop` .
Un intervallo può essere vuoto se, ad esempio, `step` è positivo e `stop < start` .

L'intervallo è incluso a entrambe le estremità. Ovvero, se la differenza tra `start` e `stop` è un multiplo Integer di `step` , l'ultimo elemento dell'intervallo sarà `stop` .

Date due `Int` espressioni qualsiasi `start` e `stop` , l'espressione `start .. stop` è un'espressione di intervallo uguale a `start .. 1 .. stop` .
Si noti che il valore implicito `step` è + 1 anche se `stop` è minore di `start` ; in tal caso, l'intervallo è vuoto.

Alcuni intervalli di esempio sono:

- `1..3`è l'intervallo 1, 2, 3.
- `2..2..5`è l'intervallo 2, 4.
- `2..2..6`è l'intervallo 2, 4, 6.
- `6..-2..2`è l'intervallo 6, 4, 2.
- `2..1`intervallo vuoto.
- `2..6..7`è l'intervallo 2.
- `2..2..1`intervallo vuoto.
- `1..-1..2`intervallo vuoto.

## <a name="qubit-expressions"></a>Espressioni qubit

Le uniche `Qubit` espressioni sono simboli associati a `Qubit` valori o elementi di matrice di `Qubit` matrici.
Nessun `Qubit` valore letterale.

## <a name="pauli-expressions"></a>Espressioni di Pauli

I quattro `Pauli` valori, `PauliI` , `PauliX` , `PauliY` e `PauliZ` , sono tutte espressioni valide `Pauli` .

A parte questo, le uniche `Pauli` espressioni sono i simboli associati a `Pauli` valori o elementi di matrice di `Pauli` matrici.

## <a name="result-expressions"></a>Espressioni risultato

I due `Result` valori, `One` e `Zero` , sono `Result` espressioni valide.

A parte questo, le uniche `Result` espressioni sono i simboli associati a `Result` valori o elementi di matrice di `Result` matrici.
In particolare, si noti che `One` non è uguale al numero intero `1` e non esiste alcuna conversione diretta tra di essi.
Lo stesso vale per `Zero` e `0` .

## <a name="tuple-expressions"></a>Espressioni di tupla

Un valore letterale di tupla è una sequenza di espressioni di elemento del tipo appropriato, separate da virgole, racchiuse tra parentesi.
Ad esempio, `(1, One)` è un' `(Int, Result)` espressione.

Ad eccezione dei valori letterali, le uniche espressioni di tupla sono simboli associati a valori di tupla, elementi di matrice di matrici di tuple e chiamate chiamabili che restituiscono Tuple.

## <a name="user-defined-type-expressions"></a>Espressioni di tipo definito dall'utente

Un valore letterale di un tipo definito dall'utente è costituito dal nome del tipo seguito da un valore letterale di tupla del tipo di tupla di base del tipo.
Se, ad esempio, `IntPair` è un tipo definito dall'utente basato su `(Int, Int)` , `IntPair(2, 3)` è un valore letterale valido di tale tipo.

Ad eccezione dei valori letterali, le uniche espressioni di un tipo definito dall'utente sono i simboli associati a valori di quel tipo, gli elementi di matrice delle matrici di quel tipo e le chiamate richiamabili che restituiscono quel tipo.

## <a name="unwrap-expressions"></a>Espressioni Unwrap

In Q # l'operatore Unwrap è un punto esclamativo finale `!` .
Se, ad esempio, `IntPair` è un tipo definito dall'utente con il tipo sottostante `(Int, Int)` ed `s` è una variabile con valore `IntPair(2, 3)` , `s!` sarà `(2, 3)` .

Per i tipi definiti dall'utente definiti in termini di altri tipi definiti dall'utente, è possibile ripetere l'operatore Unwrap. Ad esempio, `s!!` indica il valore con doppia incapsulamento di `s` .
Se, pertanto, `WrappedPair` è un tipo definito dall'utente con tipo sottostante `IntPair` e `t` è una variabile con valore `WrappedPair(IntPair(1,2))` , `t!!` è `(1,2)` .

L' `!` operatore ha una precedenza più alta rispetto a tutti gli altri operatori diversi da `[]` per l'indicizzazione e il sezionamento di matrici.
`!`e si `[]` associano in modo posizionale, ovvero `a[i]![3]` viene letto come `((a[i])!)[3]` : prendere l' `i` elemento th di, annullare il `a` wrapping e quindi ottenere il terzo elemento del valore di cui non è stato eseguito il wrapping (che deve essere una matrice).

La precedenza dell' `!` operatore ha un effetto che potrebbe non essere ovvio.
Se una funzione o un'operazione restituisce un valore che viene quindi sottoposto a wrapping, la funzione o la chiamata dell'operazione deve essere racchiusa tra parentesi in modo che la tupla dell'argomento venga associata alla chiamata anziché all'annullamento del wrapping.
Ad esempio:

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a>Espressioni di matrice

Un valore letterale di matrice è una sequenza di una o più espressioni di elementi, separate da virgole, racchiuse tra parentesi quadre `[]` .
Tutti gli elementi devono essere compatibili con lo stesso tipo.

Date due matrici dello stesso tipo, usare l' `+` operatore binario per formare una nuova matrice che corrisponde alla concatenazione delle due matrici.
Ad esempio, `[1,2,3] + [4,5,6]` = `[1,2,3,4,5,6]`.

### <a name="array-creation"></a>Creazione di matrici

Dato un tipo e un' `Int` espressione, usare l' `new` operatore per allocare una nuova matrice della dimensione specificata.
Ad esempio, `new Int[i + 1]` alloca una nuova `Int` matrice con `i + 1` gli elementi.

I valori letterali di matrice vuoti, ad esempio `[]` , non sono consentiti.
È invece possibile creare una matrice di lunghezza zero usando `new T[0]` , dove `T` è un segnaposto per un tipo appropriato.

Gli elementi di una nuova matrice vengono inizializzati su un valore predefinito dipendente dal tipo.
Nella maggior parte dei casi, si tratta di una variante di zero.

Per qubits e callable, che sono riferimenti a entità, non esiste un valore predefinito ragionevole.
Pertanto, per questi tipi, il valore predefinito è un riferimento non valido che non è possibile utilizzare senza causare un errore di runtime, simile a un riferimento null in linguaggi come C# o Java.
Prima di poter usare i relativi elementi in modo sicuro, è necessario inizializzare le matrici contenenti qubits o Callable con valori non predefiniti. Per le routine di inizializzazione appropriate, vedere <xref:microsoft.quantum.arrays> .

I valori predefiniti per ogni tipo sono:

Type | Predefinito
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | _Qubit non valido_
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | Intervallo vuoto,`1..1..0`
 `Callable` | _chiamabile non valido_
 `Array['T]` | `'T[0]`

I tipi di tupla inizializzano elemento per elemento.


### <a name="array-elements"></a>Elementi di matrice

Data un'espressione di matrice e un' `Int` espressione, formano una nuova espressione usando l'operatore di elemento della matrice `[]` .
La nuova espressione è dello stesso tipo del tipo di elemento della matrice.
Ad esempio, se `a` è associato a una matrice di tipo `Double` , `a[4]` è un' `Double` espressione.

Se l'espressione di matrice non è un identificatore semplice, è necessario racchiuderla tra parentesi per selezionare un elemento.
Se, ad esempio, `a` e `b` sono entrambe matrici di tipo `Int` , un elemento della concatenazione viene espresso come:

```qsharp
(a + b)[13]
```

Tutte le matrici in Q # sono in base zero.
Ovvero il primo elemento di una matrice `a` è sempre `a[0]` .


### <a name="array-slices"></a>Sezioni di matrici

Data un'espressione di matrice e un' `Range` espressione, formano una nuova espressione usando l'operatore di sezionamento della matrice `[ ]` .
La nuova espressione è dello stesso tipo della matrice e contiene gli elementi della matrice indicizzati dagli elementi dell'oggetto `Range` , nell'ordine definito da `Range` .
Se, ad esempio, `a` è associato a una matrice di tipo `Double` , `a[3..-1..0]` è un' `Double[]` espressione che contiene i primi quattro elementi di, `a` ma in ordine inverso come appaiono in `a` .

Se `Range` è vuoto, la sezione della matrice risultante è di lunghezza zero.

Come per fare riferimento agli elementi della matrice, se l'espressione di matrice non è un identificatore semplice, è necessario racchiuderla tra parentesi per sezionarla.
Se, ad esempio, `a` e `b` sono entrambe matrici di tipo `Int` , una sezione della concatenazione viene espressa come:

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a>Valori di inizio/fine dedotti

A partire dalla [versione 0,8](xref:microsoft.quantum.relnotes), sono supportate le espressioni contestuali per il sezionamento dell'intervallo. In particolare, è possibile omettere i valori di inizio e di fine dell'intervallo nel contesto di un'espressione di sezionamento dell'intervallo. In tal caso, il compilatore applica le regole seguenti per dedurre i delimitatori previsti per l'intervallo:

* Se il valore *iniziale* dell'intervallo viene omesso, il valore di inizio derivato
  * è zero se non è specificato alcun passaggio oppure il passaggio specificato è positivo.  
  * lunghezza della matrice sezionata meno uno se il passaggio specificato è negativo.

* Se il valore *finale* dell'intervallo viene omesso, il valore di fine derivato
  * lunghezza della matrice sezionata meno uno se non viene specificato alcun passaggio oppure il passaggio specificato è positivo.
  * è zero se il passaggio specificato è negativo.

Ad esempio:

```qsharp
let arr = [1,2,3,4,5,6];
let slice1  = arr[3...];      // slice1 is [4,5,6];
let slice2  = arr[0..2...];   // slice2 is [1,3,5];
let slice3  = arr[...2];      // slice3 is [1,2,3];
let slice4  = arr[...2..3];   // slice4 is [1,3];
let slice5  = arr[...2...];   // slice5 is [1,3,5];
let slice7  = arr[4..-2...];  // slice7 is [5,3,1];
let slice8  = arr[...-1..3];  // slice8 is [6,5,4];
let slice9  = arr[...-1...];  // slice9 is [6,5,4,3,2,1];
let slice10 = arr[...];       // slice10 is [1,2,3,4,5,6];
```

### <a name="copy-and-update-expressions"></a>Espressioni di copia e aggiornamento

Poiché tutti i tipi Q # sono tipi valore (con qubits che accetta un ruolo particolare), viene creata formalmente una "copia" quando un valore è associato a un simbolo o quando un simbolo viene riassociato. Ovvero, il comportamento di Q # è identico a quello in cui è stata creata una copia utilizzando un operatore di assegnazione. 

Naturalmente, in pratica, solo le parti rilevanti vengono ricreate in base alle esigenze. Ciò influiscono sulla modalità di copia delle matrici perché non è possibile aggiornare gli elementi della matrice. Per modificare una matrice esistente, è necessario sfruttare un meccanismo di *copia e aggiornamento* .

È possibile creare una nuova matrice da una matrice esistente tramite espressioni di *copia e aggiornamento* , che usano gli operatori `w/` e `<-` .
Un'espressione di copia e aggiornamento è un'espressione nel formato, in `expression1 w/ expression2 <- expression3` cui

* `expression1`deve essere `T[]` di tipo per un tipo `T` .
* `expression2`definisce gli indici nella matrice specificata in `expression1` da modificare. `expression2`deve essere di tipo `Int` o `Range` .
* `expression3`valore o valori utilizzati per aggiornare gli elementi in, in `expression1` base agli indici specificati in `expression2` . Se `expression2` è `Int` di tipo, `expression3` deve essere di tipo `T` . Se `expression2` è `Range` di tipo, `expression3` deve essere di tipo `T[]` .

L'espressione Copy-and-Update, ad esempio, `arr w/ idx <- value` costruisce una nuova matrice con tutti gli elementi impostati sugli elementi corrispondenti in `arr` , ad eccezione degli elementi specificati da `idx` , che viene impostato sul valore/i in `value` . 

Dato che `arr` contiene la matrice `[0,1,2,3]` , 

- `arr w/ 0 <- 10`è la matrice `[10,1,2,3]` .
- `arr w/ 2 <- 10`è la matrice `[0,1,10,3]` .
- `arr w/ 0..2..3 <- [10,12]`è la matrice `[10,1,12,3]` .

#### <a name="copy-and-update-expressions-for-named-items"></a>Espressioni di copia e aggiornamento per gli elementi denominati

Sono presenti espressioni simili per gli elementi denominati in tipi definiti dall'utente. 

Si consideri ad esempio il tipo 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
Se `c` contiene il valore di tipo `Complex(1., -1.)` , `c w/ Re <- 0.` è un'espressione di tipo `Complex` che restituisce `Complex(0., -1.)` .

### <a name="jagged-arrays"></a>Matrici irregolari

Una matrice di matrici, talvolta denominata "matrice di matrici", è una matrice i cui elementi sono matrici.
Gli elementi di una matrice irregolare possono avere dimensioni diverse.
Nell'esempio seguente viene illustrato come dichiarare e inizializzare una matrice di matrici che rappresenta una tabella di moltiplicazione.

```qsharp
let N = 4;
mutable multiplicationTable = new Int[][N];
for (i in 1..N) {
    mutable row = new Int[i];
    for (j in 1..i) {
        set row w/= j-1 <- i * j;
    }
    set multiplicationTable w/= i-1 <- row;
}
```

### <a name="arrays-of-callables"></a>Matrici di chiamabili 

È anche possibile creare una matrice di chiamabili.

* Se il tipo di elemento comune è un'operazione o un tipo di funzione, tutti gli elementi devono avere gli stessi tipi di input e di output.
* Il tipo di elemento della matrice supporta qualsiasi [funtori](xref:microsoft.quantum.guide.operationsfunctions) supportato da tutti gli elementi.
Ad esempio, se `Op1` , `Op2` e `Op3` sono tutte `Qubit[] => Unit` operazioni, ma supporta, supporta `Op1` e supporta `Adjoint` `Op2` `Controlled` `Op3` entrambi:
  * `[Op1, Op2]`è una matrice di `(Qubit[] => Unit)` operazioni.
  * `[Op1, Op3]`è una matrice di `(Qubit[] => Unit is Adj)` operazioni.
  * `[Op2, Op3]`è una matrice di `(Qubit[] => Unit is Ctl)` operazioni.

Tuttavia, mentre le operazioni `(Qubit[] => Unit is Adj)` e `(Qubit[] => Unit is Ctl)` hanno il tipo di base comune di `(Qubit[] => Unit)` , le *matrici* di queste operazioni non condividono un tipo di base comune.

Al momento, ad esempio, `[[Op1], [Op2]]` genera un errore perché tenta di creare una matrice dei due tipi di matrice incompatibili `(Qubit[] => Unit is Adj)[]` e `(Qubit[] => Unit is Ctl)[]` .

Per altre informazioni sulle richiamabili, vedere [espressioni richiamabili](#callable-expressions) in questa pagina o [operazioni e funzioni in Q #](xref:microsoft.quantum.guide.operationsfunctions).

## <a name="conditional-expressions"></a>Espressioni condizionali

Date due espressioni dello stesso tipo e di un'espressione booleana, formano un'espressione condizionale usando il punto interrogativo, `?` e la barra verticale `|` . Dato `a==b ? c | d` , il valore dell'espressione condizionale è `c` se `a==b` è true e `d` se è false.

### <a name="conditional-expressions-with-callables"></a>Espressioni condizionali con Callable

Le espressioni condizionali possono restituire operazioni con gli stessi input e output ma supportano funtori diversi. In questo caso, il tipo dell'espressione condizionale è un'operazione con input e output che supportano qualsiasi funtori supportato da entrambe le espressioni.
Se, ad esempio `Op1` ,, `Op2` e `Op3` sono tutti `Qubit[]=>Unit` , ma `Op1` supporta, supporta e supporta `Adjoint` `Op2` `Controlled` `Op3` entrambi:

- `flag ? Op1 | Op2`è un' `(Qubit[] => Unit)` operazione.
- `flag ? Op1 | Op3`è un' `(Qubit[] => Unit is Adj)` operazione.
- `flag ? Op2 | Op3`è un' `(Qubit[] => Unit is Ctl)` operazione.

Se una delle due espressioni di risultato possibili include una funzione o una chiamata a un'operazione, la chiamata viene eseguita solo se il risultato è quello che corrisponde al valore della chiamata. Nel caso, ad esempio, `a==b ? C(qs) | D(qs)` se `a==b` è true, `C` viene richiamata l'operazione e se è false, `D` viene richiamata solo l'operazione. Questo approccio è simile a *un cortocircuito in altri* linguaggi.

## <a name="callable-expressions"></a>Espressioni richiamabili

Un valore letterale chiamabile è il nome di un'operazione o di una funzione definita nell'ambito di compilazione. Ad esempio, `X` è un valore letterale di operazione che fa riferimento all'operazione della libreria standard `X` e `Message` è un valore letterale di funzione che fa riferimento alla funzione della libreria standard `Message` .

Se un'operazione supporta il `Adjoint` functor, `Adjoint op` è un'espressione dell'operazione.
Analogamente, se l'operazione supporta il `Controlled` functor, `Controlled op` è un'espressione dell'operazione.
Per ulteriori informazioni sui tipi di queste espressioni, vedere la pagina relativa alle [specializzazioni delle operazioni di chiamata](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).

Funtori ( `Adjoint` e `Controlled` ) vengono associati in modo più accurato rispetto a tutti gli altri operatori, ad eccezione dell'operatore Unwrap `!` e dell'indicizzazione della matrice con `[ ]` .
Pertanto, tutti i seguenti sono validi, presupponendo che le operazioni supportino i funtori utilizzati:

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a>Espressioni chiamabili con parametri di tipo

È possibile usare un valore letterale chiamabile come valore, ad esempio, per assegnarlo a una variabile o passarlo a un altro oggetto chiamabile. In questo caso, se l'oggetto chiamabile dispone di [parametri di tipo](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), è necessario fornire i parametri come parte del valore chiamabile.

Un valore chiamabile non può avere parametri di tipo non specificati. Ad esempio, se `Fun` è una funzione con la firma `'T1->Unit` :

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomeOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a>Espressioni di chiamata chiamabili

Data un'espressione chiamabile (operazione o funzione) e un'espressione di tupla del tipo di input della firma richiamabile, è possibile formare un' *espressione di chiamata* aggiungendo l'espressione di tupla all'espressione chiamabile.
Il tipo dell'espressione di chiamata è il tipo di output della firma richiamabile.

Se, ad esempio, `Op` è un'operazione con la firma `((Int, Qubit) => Double)` , `Op(3, qubit1)` è un'espressione di tipo `Double` .
Analogamente, se `Sin` è una funzione con la firma `(Double -> Double)` , `Sin(0.1)` è un'espressione di tipo `Double` .
Infine, se `Builder` è una funzione con la firma `(Int -> (Int -> Int))` , `Builder(3)` è una funzione da `Int` a `Int` .

Per richiamare il risultato di un'espressione con valori richiamabili è necessaria una coppia aggiuntiva di parentesi intorno all'espressione chiamabile.
Pertanto, per richiamare il risultato della chiamata `Builder` dal paragrafo precedente, la sintassi corretta è la seguente:

```qsharp
(Builder(3))(2)
```

Quando si richiama un oggetto chiamabile con [parametri di tipo](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) , è possibile specificare i parametri di tipo effettivi tra parentesi acute `< >` dopo l'espressione chiamabile.
Questa azione non è in genere necessaria perché il compilatore Q # deduce i tipi effettivi.
Tuttavia, è *necessario per* l' [applicazione parziale](xref:microsoft.quantum.guide.operationsfunctions#partial-application) se un argomento con parametri di tipo non è specificato.
È utile anche quando si passano operazioni con diversi supporti di un functor a un oggetto chiamabile.

Ad esempio, se `Func` ha `('T1, 'T2, 'T1) -> 'T2` la firma `Op1` e `Op2` hanno `(Qubit[] => Unit is Adj)` la firma e `Op3` ha `(Qubit[] => Unit)` la firma, per richiamare `Func` con `Op1` come primo argomento, `Op2` come secondo e `Op3` come terzo:

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

La specifica del tipo è obbligatoria perché `Op3` e `Op1` hanno tipi diversi, pertanto il compilatore lo considererà ambiguo senza la specifica.


## <a name="operator-precedence"></a>Ordine di precedenza degli operatori

* Tutti gli operatori binari sono associativi a destra, ad eccezione di `^` .

* Le parentesi quadre, `[ ]` , per il sezionamento e l'indicizzazione della matrice, vengono associate prima di qualsiasi operatore.

* Funtori `Adjoint` e `Controlled` Bind dopo l'indicizzazione della matrice ma prima di tutti gli altri operatori.

* Anche le parentesi per la chiamata di operazioni e funzioni vengono associate prima di qualsiasi operatore, ma dopo l'indicizzazione della matrice e funtori.

Operatori Q # in ordine di precedenza, dal più alto al più basso:

Operatore | Grado | Descrizione | Tipi di operando
---------|----------|---------|---------------
 finali`!` | Unaria | Unwrap | Qualsiasi tipo definito dall'utente
 `-`, `~~~`, `not` | Unaria | Valore numerico negativo, complemento bit per bit, negazione logica | `Int`, `BigInt` o `Double` per `-` , `Int` o `BigInt` per `~~~` , `Bool` per`not`
 `^` | Binary | Potenza intera | `Int`o `BigInt` per la base, `Int` per l'esponente
 `/`, `*`, `%` | Binary | Divisione, moltiplicazione, modulo Integer | `Int`, `BigInt` oppure `Double` per `/` e `*` `Int` o `BigInt` per`%`
 `+`, `-` | Binary | Aggiunta o concatenazione di stringhe e matrici, sottrazione | `Int``BigInt`o `Double` , inoltre, `String` o qualsiasi tipo di matrice per`+`
 `<<<`, `>>>` | Binary | Spostamento a sinistra, spostamento a destra | `Int` o `BigInt`
 `<`, `<=`, `>`, `>=` | Binary | Confronti minore di, minore di o uguale a, maggiore di, maggiore di o uguale a | `Int``BigInt`o`Double`
 `==`, `!=` | Binary | confronti uguali, non uguali | qualsiasi tipo primitivo
 `&&&` | Binary | AND bit per bit | `Int` o `BigInt`
 `^^^` | Binary | XOR bit per bit | `Int` o `BigInt`
 <code>\|\|\|</code> | Binary | OR bit per bit | `Int` o `BigInt`
 `and` | Binary | AND logico | `Bool`
 `or` | Binary | OR logico | `Bool`
 `..` | Binario/ternario | Operatore Range | `Int`
 `?` `|` | Ternario | Condizionale | `Bool`per il lato sinistro
`w/` `<-` | Ternario | Copia e aggiornamento | Vedere [espressioni di copia e aggiornamento](#copy-and-update-expressions)

## <a name="next-steps"></a>Passaggi successivi

Ora che è possibile usare le espressioni in Q #, passare a [operazioni e funzioni in q #](xref:microsoft.quantum.guide.operationsfunctions) per informazioni su come definire e chiamare operazioni e funzioni.
