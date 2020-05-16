---
title: 'Espressioni di tipo in Q #'
description: 'Informazioni su come specificare, fare riferimento e combinare costanti, variabili, operatori, operazioni e funzioni come espressioni in Q #.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
ms.openlocfilehash: 93432cef9711b6780192cd59e92b09647a264b5c
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431207"
---
# <a name="type-expressions-in-q"></a>Espressioni di tipo in Q #

## <a name="numeric-expressions"></a>Espressioni numeriche

Le espressioni numeriche sono espressioni di tipo `Int` , `BigInt` o `Double` .
Ovvero sono numeri interi o a virgola mobile.

`Int`i valori letterali in Q # vengono scritti semplicemente come una sequenza di cifre.
Gli Integer esadecimali e binari sono supportati rispettivamente con un `0x` `0b` prefisso e.

`BigInt`i valori letterali in Q # vengono scritti con un `l` `L` suffisso o finale.
I Big Integer esadecimali sono supportati con un prefisso "0x".
Di conseguenza, di seguito sono riportati tutti gli utilizzi validi dei `BigInt` valori letterali:

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

`Double`i valori letterali in Q # sono numeri a virgola mobile scritti con cifre decimali.
Possono essere scritti con un separatore decimale, `.` e/o una parte esponenziale indicata con "e" o "e" (dopo il quale sono validi solo un possibile segno negativo e cifre decimali).
I valori letterali validi sono i seguenti `Double` : `0.0` , `1.2e5` , `1e-5` .

Data un'espressione di matrice di qualsiasi tipo di elemento, un' `Int` espressione può essere formata usando la [`Length`](xref:microsoft.quantum.core.length) funzione predefinita, con l'espressione di matrice racchiusa tra parentesi, `(` e `)` .
Ad esempio, se `a` è associato a una matrice, `Length(a)` è un'espressione Integer.
Se `b` è una matrice di matrici di numeri interi, `Int[][]` , `Length(b)` è il numero di sottomatrici in `b` e `Length(b[1])` è il numero di numeri interi nella seconda sottomatrice di `b` .

Date due espressioni numeriche dello stesso tipo, gli operatori binari `+` , `-` , `*` e `/` possono essere usati per formare una nuova espressione numerica.
Il tipo della nuova espressione sarà uguale ai tipi delle espressioni costituenti.

Date due espressioni Integer, l'operatore binario `^` (Power) può essere usato per formare una nuova espressione Integer.
Analogamente, `^` può essere usato con due espressioni doppie per formare una nuova espressione doppia.
Infine, `^` può essere usato con un Big Integer a sinistra e un numero intero a destra per formare una nuova espressione di tipo Integer grande.
In questo caso, il secondo parametro deve adattarsi a 32 bit; in caso contrario, verrà generato un errore di Runtime.

Date due espressioni Integer o Big Integer, è possibile formare una nuova espressione Integer o Big Integer usando gli `%` operatori (modulo), `&&&` (and bit per bit), `|||` (OR bit per bit) o `^^^` (XOR bit per bit).

Data un'espressione Integer o Big Integer a sinistra e un'espressione Integer a destra, `<<<` `>>>` per creare una nuova espressione con lo stesso tipo dell'espressione a sinistra, è possibile usare gli operatori (spostamento aritmetico a sinistra) o (spostamento a destra aritmetico).

Il secondo parametro (l'importo dello spostamento) per l'operazione di spostamento deve essere maggiore o uguale a zero; il comportamento per gli importi di spostamento negativi non è definito.
L'importo dello spostamento per entrambe le operazioni di spostamento deve rientrare anche in 32 bit; in caso contrario, verrà generato un errore di Runtime.
Se il numero da spostare è un numero intero, l'importo dello spostamento viene interpretato, `mod 64` ovvero uno spostamento di 1 e uno spostamento di 65 hanno lo stesso effetto.

Per i valori integer e Big Integer, i turni sono aritmetici.
Se si sposta un valore negativo, a sinistra o a destra, viene generato un numero negativo.
Ovvero, lo spostamento di un passaggio verso sinistra o a destra è esattamente uguale alla moltiplicazione o alla divisione per 2, rispettivamente.

La divisione Integer e il modulo Integer seguono lo stesso comportamento per i numeri negativi in C#.
Ovvero, `a % b` avrà sempre lo stesso segno di `a` e `b * (a / b) + a % b` sarà sempre uguale `a` .
Ad esempio:

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 5 | 2 | 2 | 1
 5 | -2 | -2 | 1
 -5 | 2 | -2 | -1
 -5 | -2 | 2 | -1

La divisione e il modulo di Big Integer funzionano allo stesso modo.

Data un'espressione numerica, una nuova espressione può essere formata usando l' `-` operatore unario.
La nuova espressione sarà dello stesso tipo dell'espressione costituente.

Dato qualsiasi espressione Integer o Big Integer, è possibile formare una nuova espressione dello stesso tipo utilizzando l' `~~~` operatore unario (complemento bit per bit).

## <a name="boolean-expressions"></a>Espressioni booleane

I due `Bool` valori letterali sono `true` e `false` .

Date due espressioni dello stesso tipo primitivo, gli `==` `!=` operatori binari e possono essere usati per costruire un' `Bool` espressione.
L'espressione sarà true se le due espressioni sono uguali e false in caso contrario.

I valori dei tipi definiti dall'utente non possono essere confrontati, ma è possibile confrontare solo i valori di cui non è stato eseguito il wrapper. Ad esempio, usando l'operatore "Unwrap" `!` (illustrato in dettaglio nei [tipi in Q #](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

Il confronto di uguaglianza per `Qubit` i valori è uguaglianza di identità, ovvero se le due espressioni identificano lo stesso qubit.
Lo stato dei due qubits non viene confrontato, accessibile, misurato o modificato da questo confronto.

Il confronto di uguaglianza per `Double` i valori può essere fuorviante a causa degli effetti dell'arrotondamento.
Ad esempio, `49.0 * (1.0/49.0) != 1.0` .

Date due espressioni numeriche, gli operatori binari `>` , `<` , `>=` e `<=` possono essere usati per costruire una nuova espressione booleana che è true se la prima espressione è rispettivamente maggiore di, minore di, maggiore o uguale a o minore o uguale alla seconda espressione.

Date due espressioni booleane, gli `and` `or` operatori binari e possono essere usati per costruire una nuova espressione booleana che è true se entrambe le espressioni (resp. both o entrambe) sono true.

Dato qualsiasi espressione booleana, l' `not` operatore unario può essere usato per costruire una nuova espressione booleana che è true se l'espressione costituente è false.

## <a name="string-expressions"></a>Espressioni stringa

Q # consente di usare le stringhe nell' `fail` istruzione (illustrate in [flusso di controllo](xref:microsoft.quantum.guide.controlflow#fail-statement)) e nella [`Message`](xref:microsoft.quantum.intrinsic.message) funzione standard.
Il comportamento specifico di quest'ultimo dipende dal simulatore usato, ma in genere scrive un messaggio nella console host quando viene chiamato durante un programma Q #.

Le stringhe in Q # sono valori letterali o stringhe interpolate.

I valori letterali stringa sono simili a valori letterali stringa semplici nella maggior parte dei linguaggi: una sequenza di caratteri Unicode racchiusi tra virgolette doppie, `"` .
All'interno di una stringa, il carattere barra rovesciata `\` può essere utilizzato per eseguire l'escape di un carattere virgolette doppie e per inserire una nuova riga come `\n` , un ritorno a capo come `\r` e una tabulazione come `\t` .
Ad esempio:

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a>Stringhe interpolate

La sintassi Q # per l'interpolazione di stringhe è un subset della sintassi C#, ma vengono riepilogati i punti chiave che riguardano Q #.
Le distinzioni principali sono illustrate di seguito.

Per identificare un valore letterale stringa come stringa interpolata, anteporre a questa il simbolo `$`.
Non è possibile avere spazi vuoti tra `$` e `"` che avvia un valore letterale stringa.

Di seguito è riportato un esempio di base [`Message`](xref:microsoft.quantum.intrinsic.message) che usa la funzione per scrivere il risultato di una misurazione nella console, insieme ad altre espressioni Q #.

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```
In una stringa interpolata può essere presente qualsiasi espressione Q # valida.

Altre informazioni sulla sintassi di C# sono disponibili in [*stringhe interpolate*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).
La differenza più importante è che Q # non supporta le stringhe interpolate Verbatim (a più righe).
Le espressioni all'interno di una stringa interpolata seguono la sintassi Q #, non la sintassi C#.

## <a name="range-expressions"></a>Espressioni di intervallo

Date le tre `Int` espressioni `start` , `step` , e `stop` , `start .. step .. stop` è un'espressione di intervallo il cui primo elemento è `start` , il secondo elemento è `start+step` , il terzo elemento è `start+step+step` e così via, fino a quando non `stop` viene passato.
Un intervallo può essere vuoto se, ad esempio, `step` è positivo e `stop < start` .
L'ultimo elemento dell'intervallo sarà `stop` se la differenza tra `start` e `stop` è un multiplo integrale di `step` , ovvero l'intervallo è incluso a entrambe le estremità.

Date due `Int` espressioni qualsiasi `start` e `stop` , `start .. stop` è un'espressione di intervallo uguale a `start .. 1 .. stop` .
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

Un valore letterale di tupla è una sequenza di espressioni di elemento del tipo appropriato, separate da virgole, racchiuse tra `(` e `)` .
Ad esempio, `(1, One)` è un' `(Int, Result)` espressione.

Ad eccezione dei valori letterali, le uniche espressioni di tupla sono simboli associati a valori di tupla, elementi di matrice di matrici di tuple e chiamate chiamabili che restituiscono Tuple.

## <a name="user-defined-type-expressions"></a>Espressioni di tipo definito dall'utente

Un valore letterale di un tipo definito dall'utente è costituito dal nome del tipo seguito da un valore letterale di tupla del tipo di tupla di base del tipo.
Se, ad esempio, `IntPair` è un tipo definito dall'utente basato su `(Int, Int)` , `IntPair(2, 3)` sarà un valore letterale valido di tale tipo.

Ad eccezione dei valori letterali, le uniche espressioni di un tipo definito dall'utente sono i simboli associati a valori di quel tipo, gli elementi di matrice delle matrici di quel tipo e le chiamate richiamabili che restituiscono quel tipo.

## <a name="unwrap-expressions"></a>Espressioni Unwrap

In Q # l'operatore Unwrap è un punto esclamativo finale `!` .
Se, ad esempio, `IntPair` è un tipo definito dall'utente con tipo sottostante `(Int, Int)` ed `s` è una variabile con valore `IntPair(2, 3)` , `s!` sarà `(2, 3)` .

Per i tipi definiti dall'utente definiti in termini di altri tipi definiti dall'utente. l'operatore Unwrap può essere ripetuto; ad esempio, `s!!` indica il valore con doppia incapsulamento di `s` .
Se, pertanto, `WrappedPair` è un tipo definito dall'utente con tipo sottostante `IntPair` e `t` è una variabile con valore `WrappedPair(IntPair(1,2))` , `t!!` sarà `(1,2)` .

L' `!` operatore ha una precedenza più alta rispetto a tutti gli altri operatori diversi da `[]` per l'indicizzazione e il sezionamento di matrici.
`!`e si `[]` associano in modo posizionale, ovvero `a[i]![3]` devono essere lette come `((a[i])!)[3]` : prendere il `i` ' esimo elemento di, annullare il `a` wrapping e quindi ottenere il terzo elemento del valore di cui non è stato eseguito il wrapping (che deve essere una matrice).

La precedenza dell' `!` operatore ha un effetto che potrebbe non essere ovvio.
Se una funzione o un'operazione restituisce un valore che viene quindi sottoposto a wrapping, la funzione o la chiamata dell'operazione deve essere racchiusa tra parentesi in modo che la tupla dell'argomento venga associata alla chiamata anziché all'annullamento del wrapping.
Ad esempio:

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a>Espressioni di matrice

Un valore letterale di matrice è una sequenza di una o più espressioni di elementi, separate da virgole, racchiuse tra `[` e `]` .
Tutti gli elementi devono essere compatibili con lo stesso tipo.


Date due matrici dello stesso tipo, l' `+` operatore binario può essere usato per formare una nuova matrice che rappresenta la concatenazione delle due matrici.
Ad esempio, `[1,2,3] + [4,5,6]` è `[1,2,3,4,5,6]` .

### <a name="array-creation"></a>Creazione di matrici

Dato un tipo e un' `Int` espressione, l' `new` operatore può essere usato per allocare una nuova matrice della dimensione specificata.
Ad esempio, `new Int[i + 1]` alloca una nuova `Int` matrice con `i + 1` gli elementi.

Gli elementi di una nuova matrice vengono inizializzati su un valore predefinito dipendente dal tipo.
Nella maggior parte dei casi si tratta di una variante di zero.

Per qubits e callable, che sono riferimenti a entità, non esiste un valore predefinito ragionevole.
Pertanto, per questi tipi, il valore predefinito è un riferimento non valido che non può essere utilizzato senza causare un errore di Runtime.
Questa operazione è simile a un riferimento null in linguaggi come C# o Java.
Le matrici contenenti qubits o Callable devono essere inizializzate correttamente con valori non predefiniti prima che i relativi elementi possano essere usati in modo sicuro. È possibile trovare routine di inizializzazione appropriate in <xref:microsoft.quantum.arrays> .

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

I tipi di tupla sono elemento per elemento inizializzato.


### <a name="array-elements"></a>Elementi di matrice

Data un'espressione di matrice e un' `Int` espressione, è possibile che venga creata una nuova espressione usando l' `[` `]` operatore di elemento della matrice e.
La nuova espressione sarà dello stesso tipo del tipo di elemento della matrice.
Ad esempio, se `a` è associato a una matrice di `Double` , `a[4]` è un' `Double` espressione.

Se l'espressione di matrice non è un identificatore semplice, deve essere racchiusa tra parentesi per selezionare un elemento.
Se, ad esempio, `a` e `b` sono entrambe matrici di `Int` , un elemento della concatenazione verrebbe espresso come:

```qsharp
(a + b)[13]
```

Tutte le matrici in Q # sono in base zero.
Ovvero il primo elemento di una matrice `a` è sempre `a[0]` .


### <a name="array-slices"></a>Sezioni di matrici

Data un'espressione di matrice e un' `Range` espressione, è possibile che venga creata una nuova espressione usando l' `[` operatore e la `]` sezione di matrici.
La nuova espressione sarà dello stesso tipo della matrice e conterrà gli elementi della matrice indicizzati dagli elementi dell'oggetto `Range` , nell'ordine definito da `Range` .
Ad esempio, se `a` è associato a una matrice di `Double` , `a[3..-1..0]` è un' `Double[]` espressione che contiene i primi quattro elementi di, `a` ma in ordine inverso come appaiono in `a` .

Se `Range` è vuoto, la sezione della matrice risultante avrà una lunghezza pari a zero.

Come per fare riferimento a elementi della matrice, se l'espressione di matrice non è un identificatore semplice, deve essere racchiusa tra parentesi per sezionare.
Se `a` e `b` sono entrambe matrici di `Int` , una sezione della concatenazione verrebbe espressa come:

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a>Valori di inizio/fine dedotti

A partire dalla versione 0,8, sono supportate le espressioni contestuali per il sezionamento dell'intervallo. In particolare, i valori iniziale e finale dell'intervallo possono essere omessi nel contesto di un'espressione di sezionamento dell'intervallo. In tal caso, il compilatore applicherà le regole seguenti per dedurre i delimitatori previsti per l'intervallo. 

Ad esempio, se il valore iniziale dell'intervallo viene omesso, il valore di inizio derivato 
- è zero se non è specificato alcun passaggio oppure il passaggio specificato è positivo e 
- lunghezza della matrice sezionata meno uno se il passaggio specificato è negativo. 

Se il valore finale dell'intervallo viene omesso, il valore di fine derivato 
- lunghezza della matrice sezionata meno uno se non si specifica alcun passaggio oppure il passaggio specificato è positivo e 
- è zero se il passaggio specificato è negativo. 

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

Poiché tutti i tipi Q # sono tipi di valore, con qubits che assumono un ruolo particolare, formalmente una "copia" viene creata quando un valore è associato a un simbolo o quando un simbolo viene riassociato. Ovvero, il comportamento di Q # è identico a quello in cui è stata creata una copia durante l'assegnazione.
Naturalmente, in pratica, solo le parti pertinenti vengono effettivamente ricreate in base alle esigenze. 

Questo in particolare include anche matrici.
In particolare, non è possibile aggiornare gli elementi della matrice. Per modificare una matrice esistente, è necessario sfruttare un meccanismo di *copia e aggiornamento* .

È possibile creare nuove matrici da quelle esistenti tramite espressioni di *copia e aggiornamento* .
Un'espressione di copia e aggiornamento è un'espressione nel formato `expression1 w/ expression2 <- expression3` , dove `expression1` deve essere di tipo `T[]` per un certo tipo `T` .
Il secondo `expression2` definisce gli indici degli elementi da modificare rispetto alla matrice in `expression1` e deve essere di tipo `Int` o di tipo `Range` .
Se `expression2` è di tipo `Int` , `expression3` deve essere di tipo `T` . Se `expression2` è di tipo `Range` , `expression3` deve essere di tipo `T[]` .

Un'espressione di copia e aggiornamento `arr w/ idx <- value` costruisce una nuova matrice con tutti gli elementi impostati sull'elemento corrispondente in `arr` , ad eccezione degli elementi in `idx` , che sono impostati su uno o più elementi in `value` . Se, ad esempio, `arr` contiene una matrice `[0,1,2,3]` , 
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

Si noti che altre informazioni sui tipi richiamabili sono disponibili di seguito, nonché nella pagina successiva, [operazioni e funzioni in Q #](xref:microsoft.quantum.guide.operationsfunctions).

Se il tipo di elemento comune è un'operazione o un tipo di funzione, tutti gli elementi devono avere gli stessi tipi di input e di output.
Il tipo di elemento della matrice supporterà qualsiasi funtori supportato da tutti gli elementi.
Se, ad esempio `Op1` ,, `Op2` e `Op3` sono tutti `Qubit[] => Unit` , ma `Op1` supporta, supporta e supporta `Adjoint` `Op2` `Controlled` `Op3` entrambi:

- `[Op1, Op2]`è una matrice di `(Qubit[] => Unit)` operazioni.
- `[Op1, Op3]`è una matrice di `(Qubit[] => Unit is Adj)` operazioni.
- `[Op2, Op3]`è una matrice di `(Qubit[] => Unit is Ctl)` operazioni.

I valori letterali di matrice vuoti, `[]` , non sono consentiti.
In alternativa, `new ★[0]` se si usa, dove `★` è come segnaposto per un tipo adatto, consente a di creare la matrice desiderata di lunghezza zero.


## <a name="conditional-expressions"></a>Espressioni condizionali

Date due altre espressioni dello stesso tipo e di un'espressione booleana, l'espressione condizionale può essere formata usando il punto interrogativo `?` e la barra verticale `|` .
Ad esempio, `a==b ? c | d` .
In questo esempio, il valore dell'espressione condizionale sarà `c` se `a==b` è true e `d` se è false.

### <a name="conditional-expressions-with-callables"></a>Espressioni condizionali con Callable

Le due espressioni possono restituire operazioni con gli stessi input e output ma supportano funtori diversi.
In questo caso, il tipo dell'espressione condizionale è un'operazione con gli input e gli output che supportano qualsiasi funtori supportato da entrambe le espressioni.
Se, ad esempio `Op1` ,, `Op2` e `Op3` sono tutti `Qubit[]=>Unit` , ma `Op1` supporta, supporta e supporta `Adjoint` `Op2` `Controlled` `Op3` entrambi:

- `flag ? Op1 | Op2`è un' `(Qubit[] => Unit)` operazione.
- `flag ? Op1 | Op3`è un' `(Qubit[] => Unit is Adj)` operazione.
- `flag ? Op2 | Op3`è un' `(Qubit[] => Unit is Ctl)` operazione.

Se una delle due espressioni di risultato possibili include una funzione o una chiamata a un'operazione, la chiamata verrà eseguita solo se il risultato è quello che sarà il valore della chiamata.
Nel caso, ad esempio, `a==b ? C(qs) | D(qs)` se `a==b` è true, l' `C` operazione verrà richiamata e se è false verrà `D` richiamato solo.
Questa operazione è simile a un cortocircuito in altri linguaggi.

## <a name="callable-expressions"></a>Espressioni richiamabili

Un valore letterale chiamabile è il nome di un'operazione o di una funzione definita nell'ambito di compilazione.
Ad esempio, `X` è un valore letterale di operazione che fa riferimento all'operazione della libreria standard `X` e `Message` è un valore letterale di funzione che fa riferimento alla funzione della libreria standard `Message` .

Se un'operazione supporta il `Adjoint` functor, `Adjoint op` è un'espressione dell'operazione.
Analogamente, se l'operazione supporta il `Controlled` functor, `Controlled op` è un'espressione dell'operazione.
I tipi di queste espressioni vengono specificati durante le [specializzazioni delle operazioni di chiamata](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).

Funtori ( `Adjoint` e `Controlled` ) vengono associati in modo più accurato rispetto a tutti gli altri operatori, ad eccezione dell'operatore Unwrap `!` e dell'indicizzazione della matrice con []'.
Pertanto, di seguito sono riportate tutte le informazioni legali, supponendo che le operazioni supportino i funtori utilizzati:

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a>Espressioni chiamabili con parametri di tipo

Un valore letterale chiamabile può essere usato come valore, ad esempio per assegnare a una variabile o per passare a un altro oggetto chiamabile.
In questo caso, se l'oggetto chiamabile dispone di [parametri di tipo](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), questi devono essere forniti come parte del valore chiamabile.
Un valore chiamabile non può avere parametri di tipo non specificati.

Ad esempio, se `Fun` è una funzione con firma `'T1->Unit` :

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a>Espressioni di chiamata chiamabili

Data un'espressione chiamabile (operazione o funzione) e un'espressione di tupla del tipo di input della firma richiamabile, un'espressione di chiamata può essere formata aggiungendo l'espressione di tupla all'espressione chiamabile.
Il tipo dell'espressione di chiamata è il tipo di output della firma richiamabile.

Se, ad esempio, `Op` è un'operazione con firma `((Int, Qubit) => Double)` , `Op(3, qubit1)` è un'espressione di tipo `Double` .
Analogamente, se `Sin` è una funzione con firma `(Double -> Double)` , `Sin(0.1)` è un'espressione di tipo `Double` .
Infine, se `Builder` è una funzione con firma `(Int -> (Int -> Int))` , `Builder(3)` è una funzione da a int.

Per richiamare il risultato di un'espressione con valori richiamabili è necessaria una coppia aggiuntiva di parentesi intorno all'espressione chiamabile.
Pertanto, per richiamare il risultato della chiamata `Builder` dal paragrafo precedente, la sintassi corretta è la seguente:

```qsharp
(Builder(3))(2)
```

Quando si richiama un oggetto chiamabile con [parametri di tipo](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) , i parametri di tipo effettivi possono essere specificati tra parentesi angolari `<` e `>` dopo l'espressione chiamabile.
Questa operazione non è in genere necessaria perché il compilatore Q # dedurrà i tipi effettivi.
Tuttavia, è *necessario per* l' [applicazione parziale](xref:microsoft.quantum.guide.operationsfunctions#partial-application) se un argomento con parametri di tipo non è specificato.
A volte può essere utile anche quando si passano operazioni con diversi supporti functor a un oggetto chiamabile.

Ad esempio, se `Func` ha `('T1, 'T2, 'T1) -> 'T2` la firma `Op1` e `Op2` hanno `(Qubit[] => Unit is Adj)` la firma e `Op3` ha `(Qubit[] => Unit)` la firma, da richiamare `Func` con `Op1` come primo argomento, `Op2` come secondo e `Op3` come terzo:

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

La specifica del tipo è obbligatoria perché `Op3` e `Op1` hanno tipi diversi, pertanto il compilatore lo considererà ambiguo senza la specifica.


## <a name="operator-precedence"></a>Ordine di precedenza degli operatori

Tutti gli operatori binari sono associativi a destra, ad eccezione di `^` .

Le parentesi quadre `[` e, `]` per l'indicizzazione e l'indicizzazione della matrice, vengono associate prima di qualsiasi operatore.

Funtori `Adjoint` e `Controlled` Bind dopo l'indicizzazione della matrice ma prima di tutti gli altri operatori.

Anche le parentesi per la chiamata di operazioni e funzioni vengono associate prima di qualsiasi operatore, ma dopo l'indicizzazione della matrice e funtori.

Operatori in ordine di precedenza, dal più alto al più basso:

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
`w/` `<-` | Ternario | Copia e aggiornamento | vedere [espressioni di copia e aggiornamento](#copy-and-update-expressions)

## <a name="whats-next"></a>Operazioni successive
Ora che è possibile usare le espressioni in Q #, è possibile passare alle [operazioni e alle funzioni in q #](xref:microsoft.quantum.guide.operationsfunctions) per informazioni su come definire e chiamare operazioni e funzioni.
