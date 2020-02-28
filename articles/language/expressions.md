---
title: 'Espressioni Q #'
description: 'Informazioni su come specificare, fare riferimento e combinare costanti, variabili, operatori, operazioni e funzioni come espressioni in Q #.'
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.expressions
ms.openlocfilehash: fbde873f220d737db17f889d00be33541e3eb59b
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907410"
---
# <a name="expressions"></a>Espressioni

## <a name="grouping"></a>Raggruppamento

Dato qualsiasi espressione, la stessa espressione racchiusa tra parentesi è un'espressione dello stesso tipo.
Ad esempio, `(7)` è un'espressione `Int`, `([1,2,3])` è un'espressione di tipo matrice di `Int`s e `((1,2))` è un'espressione con tipo `(Int, Int)`.

L'equivalenza tra i valori semplici e le tuple a elemento singolo descritte nel [modello di tipo](xref:microsoft.quantum.language.type-model#tuple-types) consente di rimuovere l'ambiguità tra `(6)` come gruppo e `(6)` come tupla con un solo elemento.

## <a name="symbols"></a>Simboli

Il nome di un simbolo associato o assegnato a un valore di tipo `'T` è un'espressione di tipo `'T`.
Ad esempio, se il simbolo `count` viene associato al valore integer `5`, `count` è un'espressione Integer.

## <a name="numeric-expressions"></a>Espressioni numeriche

Le espressioni numeriche sono espressioni di tipo `Int`, `BigInt`o `Double`.
Ovvero sono numeri interi o a virgola mobile.

`Int` valori letterali in Q # sono identici a valori letterali integer in, ad eccezione del C#fatto che non è necessario (o consentito) la "l" o "l" finale.
Gli Integer esadecimali e binari sono supportati rispettivamente con un prefisso "0x" e "0B".

`BigInt` valori letterali in Q # sono identici alle stringhe di grandi dimensioni di tipo integer in .NET, con una "l" o "L" finale.
I Big Integer esadecimali sono supportati con un prefisso "0x".
Di conseguenza, di seguito sono riportati tutti gli utilizzi validi dei valori letterali `BigInt`:

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

`Double` valori letterali in Q # sono identici a valori letterali doppi in, ad eccezione del C#fatto che nessun carattere "d" o "d" finale è obbligatorio (o consentito).

Data un'espressione di matrice di qualsiasi tipo di elemento, è possibile creare un'espressione `Int` usando la funzione incorporata `Length`, con l'espressione di matrice racchiusa tra parentesi, `(` e `)`.
Se ad esempio `a` è associato a una matrice, `Length(a)` è un'espressione Integer.
Se `b` è una matrice di matrici di numeri interi, `Int[][]`, `Length(b)` è il numero di sottomatrici in `b`e `Length(b[1])` è il numero di numeri interi nella seconda matrice secondaria in `b`.

Date due espressioni numeriche dello stesso tipo, è possibile usare gli operatori binari `+`, `-`, `*`e `/` per formare una nuova espressione numerica.
Il tipo della nuova espressione sarà uguale ai tipi delle espressioni costituenti.

Date due espressioni Integer, l'operatore binario `^` (Power) può essere usato per formare una nuova espressione Integer.
Analogamente, è possibile usare `^` con due espressioni doppie per formare una nuova espressione doppia.
Infine, `^` possibile usare con un numero intero grande a sinistra e un numero intero a destra per formare una nuova espressione di tipo Integer grande.
In questo caso, il secondo parametro deve adattarsi a 32 bit; in caso contrario, verrà generato un errore di Runtime.

Date due espressioni Integer o Big Integer, è possibile che venga creata una nuova espressione Integer o Big Integer usando gli operatori `%` (modulo), `&&&` (AND bit per bit), `|||` (OR bit per bit) o `^^^` (XOR bit per bit).

Dato un Integer o un'espressione di tipo Integer a sinistra e un'espressione Integer a destra, è possibile usare gli operatori `<<<` (scorrimento a sinistra aritmetico) o `>>>` (di spostamento a destra aritmetico) per creare una nuova espressione con lo stesso tipo dell'espressione di sinistra.

Il secondo parametro (l'importo dello spostamento) per l'operazione di spostamento deve essere maggiore o uguale a zero; il comportamento per gli importi di spostamento negativi non è definito.
L'importo dello spostamento per entrambe le operazioni di spostamento deve rientrare anche in 32 bit; in caso contrario, verrà generato un errore di Runtime.
Se il numero da spostare è un numero intero, l'importo dello spostamento viene interpretato `mod 64`; ovvero uno spostamento di 1 e uno spostamento di 65 hanno lo stesso effetto.

Per i valori integer e Big Integer, i turni sono aritmetici.
Se si sposta un valore negativo, a sinistra o a destra, viene generato un numero negativo.
Ovvero, lo spostamento di un passaggio verso sinistra o a destra è esattamente uguale alla moltiplicazione o alla divisione per 2, rispettivamente.

La divisione Integer e il modulo Integer seguono lo stesso comportamento per i C#numeri negativi di.
Ovvero `a % b` avrà sempre lo stesso segno di `a`e `b * (a / b) + a % b` sarà sempre uguale `a`.
Ad esempio,

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 5 | 2 | 2 | 1
 5 | -2 | -2 | 1
 -5 | 2 | -2 | -1
 -5 | -2 | 2 | -1

La divisione e il modulo di Big Integer funzionano allo stesso modo.

Data un'espressione numerica, una nuova espressione può essere formata utilizzando l'operatore unario `-`.
La nuova espressione sarà dello stesso tipo dell'espressione costituente.

Dato qualsiasi espressione Integer o Big Integer, è possibile formare una nuova espressione dello stesso tipo utilizzando l'operatore unario `~~~` (complemento bit per bit).

## <a name="boolean-expressions"></a>Espressioni booleane

I due `Bool` valori letterali sono `true` e `false`.

Date due espressioni dello stesso tipo primitivo, è possibile usare gli operatori binari `==` e `!=` per costruire un'espressione di `Bool`.
L'espressione sarà true se le due espressioni sono uguali e false in caso contrario.

I valori dei tipi definiti dall'utente non possono essere confrontati, ma è possibile confrontare solo i valori di cui non è stato eseguito il wrapper. Ad esempio, usando l'operatore "Unwrap" `!` (illustrato nella [pagina del modello Q # type](xref:microsoft.quantum.language.type-model#user-defined-types)),

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

Il confronto di uguaglianza per i valori `Qubit` è uguaglianza di identità; ovvero se le due espressioni identificano lo stesso qubit.
Lo stato dei due qubits non viene confrontato, accessibile, misurato o modificato da questo confronto.

Il confronto di uguaglianza per i valori `Double` può essere fuorviante a causa degli effetti dell'arrotondamento.
Ad esempio, `49.0 * (1.0/49.0) != 1.0`.

Date due espressioni numeriche, è possibile usare gli operatori binari `>`, `<`, `>=`e `<=` per costruire una nuova espressione booleana che è true se la prima espressione è rispettivamente maggiore di, minore di, maggiore o uguale a o minore o uguale alla seconda espressione.

Date due espressioni booleane, è possibile usare gli operatori binari `and` e `or` per costruire una nuova espressione booleana che è true se entrambe le espressioni (risp. both o Both) sono true.

Dato qualsiasi espressione booleana, è possibile usare l'operatore unario `not` per costruire una nuova espressione booleana che è true se l'espressione costituente è false.

## <a name="string-expressions"></a>Espressioni stringa

Q # consente l'uso di stringhe nell'istruzione `fail` e nella funzione `Log` standard.

Le stringhe in Q # sono valori letterali o stringhe interpolate.
I valori letterali stringa sono simili a valori letterali stringa semplici nella maggior parte dei linguaggi: una sequenza di caratteri Unicode racchiusi tra virgolette doppie, `"`.
All'interno di una stringa, è possibile usare il carattere di barra rovesciata `\` per eseguire l'escape di un carattere virgolette doppie e inserire una nuova riga come `\n`, un ritorno a capo come `\r`e una scheda come `\t`.
Ad esempio:

```qsharp
"\"Hello world!\", she said.\n"
```

La sintassi Q # per l' C# interpolazione di stringhe è un subset della sintassi 7,0; Q # non supporta le stringhe interpolate Verbatim (a più righe).
Per la C# sintassi, vedere [*stringhe interpolate*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) .

Le espressioni all'interno di una stringa interpolata seguono la sintassi C# Q #, non la sintassi.
In una stringa interpolata può essere presente qualsiasi espressione Q # valida.

## <a name="qubit-expressions"></a>Espressioni qubit

Le uniche espressioni `Qubit` sono simboli associati a valori `Qubit` o elementi di matrice di `Qubit` matrici.
Nessun valore letterale `Qubit`.

## <a name="pauli-expressions"></a>Espressioni di Pauli

I quattro valori `Pauli`, `PauliI`, `PauliX`, `PauliY`e `PauliZ`sono tutte espressioni di `Pauli` valide.

A parte questo, le uniche espressioni `Pauli` sono simboli associati a valori `Pauli` o elementi di matrice di `Pauli` matrici.

## <a name="result-expressions"></a>Espressioni risultato

I due valori `Result`, `One` e `Zero`, sono espressioni `Result` valide.

A parte questo, le uniche espressioni `Result` sono simboli associati a valori `Result` o elementi di matrice di `Result` matrici.
In particolare, si noti che `One` non corrisponde al `1`Integer e non esiste alcuna conversione diretta tra di essi.
Lo stesso vale per `Zero` e `0`.

## <a name="range-expressions"></a>Espressioni di intervallo

Date le tre espressioni `Int` `start`, `step`e `stop``start .. step .. stop` è un'espressione di intervallo il cui primo elemento è `start`, il secondo elemento è `start+step`, il terzo elemento è `start+step+step`e così via, fino a quando non viene passato `stop`.
Un intervallo può essere vuoto se, ad esempio, `step` è positivo e `stop < start`.
L'ultimo elemento dell'intervallo verrà `stop` se la differenza tra `start` e `stop` è un multiplo integrale di `step`; ovvero, l'intervallo è incluso a entrambe le estremità.

Date due espressioni `Int` `start` e `stop`, `start .. stop` è un'espressione di intervallo uguale a `start .. 1 .. stop`.
Si noti che il `step` implicito è + 1 anche se `stop` è minore di `start`; in tal caso, l'intervallo è vuoto.

Alcuni intervalli di esempio sono:

- `1..3` è l'intervallo 1, 2, 3.
- `2..2..5` è l'intervallo 2, 4.
- `2..2..6` è l'intervallo 2, 4, 6.
- `6..-2..2` è l'intervallo 6, 4, 2.
- `2..1` è l'intervallo vuoto.
- `2..6..7` è l'intervallo 2.
- `2..2..1` è l'intervallo vuoto.
- `1..-1..2` è l'intervallo vuoto.

## <a name="callable-expressions"></a>Espressioni richiamabili

Un valore letterale chiamabile è il nome di un'operazione o di una funzione definita nell'ambito di compilazione.
Ad esempio, `X` è un valore letterale dell'operazione che fa riferimento all'operazione di `X` della libreria standard e `Message` è un valore letterale di funzione che fa riferimento alla funzione di `Message` della libreria standard.

Se un'operazione supporta il `Adjoint` functor, `Adjoint op` è un'espressione dell'operazione.
Analogamente, se l'operazione supporta il `Controlled` functor, `Controlled op` è un'espressione Operation.
I tipi di queste espressioni sono specificati in [funtori](xref:microsoft.quantum.language.type-model#functors).

Funtori (`Adjoint` e `Controlled`) si associano in modo più accurato a tutti gli altri operatori, ad eccezione dell'operatore Unwrap `!` e dell'indicizzazione della matrice con `[]`.
Pertanto, di seguito sono riportate tutte le informazioni legali, supponendo che le operazioni supportino i funtori utilizzati:

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

Un valore letterale chiamabile può essere usato come valore, ad esempio per assegnare a una variabile o per passare a un altro oggetto chiamabile.
In questo caso, se l'oggetto chiamabile dispone di parametri di tipo, questi devono essere forniti come parte del valore chiamabile.
Un valore chiamabile non può avere parametri di tipo non specificati.

Ad esempio, se `Fun` è una funzione con `'T1->Unit`di firma:

```qsharp
let f = Fun<Int>;            // f is Int->Unit.
SomeOtherFun(Fun<Double>);   // A Double->Unit is passed to SomOtherFun.
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a>Espressioni di chiamata chiamabili

Data un'espressione chiamabile (operazione o funzione) e un'espressione di tupla del tipo di input della firma richiamabile, un'espressione di chiamata può essere formata aggiungendo l'espressione di tupla all'espressione chiamabile.
Il tipo dell'espressione di chiamata è il tipo di output della firma richiamabile.

Se ad esempio `Op` è un'operazione con `((Int, Qubit) => Double)`di firma, `Op(3, qubit1)` è un'espressione di tipo `Double`.
Analogamente, se `Sin` è una funzione con `(Double -> Double)`di firma, `Sin(0.1)` è un'espressione di tipo `Double`.
Infine, se `Builder` è una funzione con `(Int -> (Int -> Int))`di firma, `Builder(3)` è una funzione da a int.

Per richiamare il risultato di un'espressione con valori richiamabili è necessaria una coppia aggiuntiva di parentesi intorno all'espressione chiamabile.
Pertanto, per richiamare il risultato della chiamata di `Builder` dal paragrafo precedente, la sintassi corretta è la seguente:

```qsharp
(Builder(3))(2)
```

Quando si richiama un oggetto chiamabile con parametri di tipo, i parametri di tipo effettivi possono essere specificati tra parentesi angolari `<` e `>` dopo l'espressione chiamabile.
Questa operazione non è in genere necessaria perché il compilatore Q # dedurrà i tipi effettivi.
È necessario per l'applicazione parziale (vedere di seguito) se non è specificato un argomento con parametri di tipo.
A volte può essere utile anche quando si passano operazioni con diversi supporti functor a un oggetto chiamabile.

Ad esempio, se `Func` ha `('T1, 'T2, 'T1) -> 'T2`di firma, `Op1` e `Op2` hanno la firma `(Qubit[] => Unit is Adj)`e `Op3` ha la firma `(Qubit[] => Unit)`, per richiamare `Func` con `Op1` come primo argomento, `Op2` come secondo e `Op3` come terzo:

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

La specifica del tipo è necessaria perché `Op3` e `Op1` hanno tipi diversi, pertanto il compilatore lo considererà ambiguo senza la specifica.

### <a name="partial-application"></a>Applicazione parziale

Data un'espressione chiamabile, è possibile creare un nuovo oggetto chiamabile fornendo un subset degli argomenti all'oggetto chiamabile.
Questa operazione è denominata _applicazione parziale_.

In Q # un oggetto chiamabile parzialmente applicato viene espresso scrivendo un'espressione di chiamata normale, ma usando un carattere di sottolineatura `_`per gli argomenti non specificati.
Il richiamabile risultante ha lo stesso tipo di risultato di base Callable e le stesse specializzazioni per le operazioni.
Il tipo di input dell'applicazione parziale è semplicemente il tipo originale con gli argomenti specificati rimossi.

Se una variabile modificabile viene passata come argomento specificato durante la creazione di un'applicazione parziale, viene usato il valore corrente della variabile.
Se successivamente si modifica il valore della variabile, l'applicazione parziale non avrà alcun effetto.

Ad esempio, se `Op` dispone di tipo `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`:

- `Op(5,(_,_))` è di tipo `(((Qubit,Qubit), Double) => Unit is Adj)`e pertanto ha `Op(5,_)`.
- il tipo di `Op(_,(_,1.0))` è `((Int, (Qubit,Qubit)) => Unit is Adj)`.
- il tipo di `Op(_,((q1,q2),_))` è `((Int,Double) => Unit is Adj)`.
   Si noti che qui è stata applicata l'equivalenza della tupla singleton.

Se il richiamabile parzialmente applicato dispone di parametri di tipo che non possono essere dedotti dal compilatore, è necessario che siano specificati nel sito di chiamata.
L'applicazione parziale non può avere parametri di tipo non specificati.

Ad esempio, se `Op` dispone di tipo `(('T1, Qubit, 'T1) => Unit : Adjoint)`:

```qsharp
let f1 = Op<Int>(_, qb, _); // f1 has type ((Int,Int) => Unit is Adj)
let f2 = Op(5, qb, _);      // f2 has type (Int => Unit is Adj)
let f3 = Op(_,qb, _);       // f3 generates a compilation error
```

### <a name="recursion"></a>Ricorsione

D # i chiamabili possono essere ricorsivi direttamente o indirettamente.
Ovvero, un'operazione o una funzione può chiamare se stessa oppure può chiamare un altro oggetto chiamabile che chiama direttamente o indirettamente l'operazione chiamabile.

Sono tuttavia disponibili due commenti importanti sull'utilizzo della ricorsione:

- L'uso della ricorsione nelle operazioni potrebbe interferire con determinate ottimizzazioni.
  Questo può avere un notevole effetto sul tempo di esecuzione dell'algoritmo.
- Quando si esegue su un dispositivo Quantum effettivo, lo spazio dello stack può essere limitato e pertanto la ricorsione profonda può causare un errore di Runtime.
  In particolare, il compilatore e il runtime Q # non identificano e ottimizzano la ricorsione Tail.

## <a name="tuple-expressions"></a>Espressioni di tupla

Un valore letterale di tupla è una sequenza di espressioni di elemento del tipo appropriato, separate da virgole, racchiuse tra `(` e `)`.
Ad esempio, `(1, One)` è un'espressione `(Int, Result)`.

Ad eccezione dei valori letterali, le uniche espressioni di tupla sono simboli associati a valori di tupla, elementi di matrice di matrici di tuple e chiamate chiamabili che restituiscono Tuple.

## <a name="user-defined-type-expressions"></a>Espressioni di tipo definito dall'utente

Un valore letterale di un tipo definito dall'utente è costituito dal nome del tipo seguito da un valore letterale di tupla del tipo di tupla di base del tipo.
Se ad esempio `IntPair` è un tipo definito dall'utente basato su `(Int, Int)`, `IntPair(2,3)` sarebbe un valore letterale valido di quel tipo.

Ad eccezione dei valori letterali, le uniche espressioni di un tipo definito dall'utente sono i simboli associati a valori di quel tipo, gli elementi di matrice delle matrici di quel tipo e le chiamate richiamabili che restituiscono quel tipo.

## <a name="unwrap-expressions"></a>Espressioni Unwrap

In Q # l'operatore Unwrap è un punto esclamativo finale `!`.
Se, ad esempio, `IntPair` è un tipo definito dall'utente con tipo sottostante `(Int, Int)`e `s` è una variabile con valore `IntPair(2,3)`, `s!` verrebbe `(2,3)`.

Per i tipi definiti dall'utente definiti in termini di altri tipi definiti dall'utente. l'operatore Unwrap può essere ripetuto; ad esempio, `s!!` indica il valore con doppia incapsulamento di `s`.
Pertanto, se `WrappedPair` è un tipo definito dall'utente con il tipo sottostante `IntPair`e `t` è una variabile con valore `WrappedPair(IntPair(1,2))`, `t!!` verrebbe `(1,2)`.

L'operatore `!` ha precedenza maggiore rispetto a tutti gli altri operatori diversi da `[]` per l'indicizzazione e il sezionamento di matrici.
`!` e `[]` eseguire l'associazione posizionale; Ciò significa che `a[i]![3]` deve essere letto come `((a[i])!)[3]`: prendere il `i`"esimo elemento di `a`, annullare il wrapping e quindi ottenere il terzo elemento del valore di cui non è stato eseguito il wrapping (che deve essere una matrice).

La precedenza dell'operatore `!` ha un effetto che potrebbe non essere ovvio.
Se una funzione o un'operazione restituisce un valore che viene quindi sottoposto a wrapping, la funzione o la chiamata dell'operazione deve essere racchiusa tra parentesi in modo che la tupla dell'argomento venga associata alla chiamata anziché all'annullamento del wrapping.
Ad esempio,

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a>Espressioni di matrice

Un valore letterale di matrice è una sequenza di una o più espressioni di elemento, separate da virgole, racchiuse tra `[` e `]`.
Tutti gli elementi devono essere compatibili con lo stesso tipo.

Se il tipo di elemento comune è un'operazione o un tipo di funzione, tutti gli elementi devono avere gli stessi tipi di input e di output.
Il tipo di elemento della matrice supporterà qualsiasi funtori supportato da tutti gli elementi.
Ad esempio, se `Op1`, `Op2`e `Op3` sono tutti `Qubit[] => Unit`, ma `Op1` supporta `Adjoint`, `Op2` supporta `Controlled`e `Op3` supporta entrambi:

- `[Op1, Op2]` è una matrice di operazioni `(Qubit[] => Unit)`.
- `[Op1, Op3]` è una matrice di operazioni `(Qubit[] => Unit is Adj)`.
- `[Op2, Op3]` è una matrice di operazioni `(Qubit[] => Unit is Ctl)`.

I valori letterali di matrice vuoti, `[]`, non sono consentiti.
Utilizzando invece `new ★[0]`, dove `★` è come segnaposto per un tipo adatto, consente a di creare la matrice desiderata di lunghezza zero.

Date due matrici dello stesso tipo, è possibile usare l'operatore Binary `+` per formare una nuova matrice che rappresenta la concatenazione delle due matrici.
Ad esempio, `[1,2,3] + [4,5,6]` è `[1,2,3,4,5,6]`.

### <a name="array-creation"></a>Creazione di matrici

Dato un tipo e un'espressione `Int`, l'operatore `new` può essere usato per allocare una nuova matrice della dimensione specificata.
Ad esempio, `new Int[i+1]` alloca una nuova matrice di `Int` con `i+1` elementi.

Gli elementi di una nuova matrice vengono inizializzati su un valore predefinito dipendente dal tipo.
Nella maggior parte dei casi si tratta di una variante di zero.

Per qubits e callable, che sono riferimenti a entità, non esiste un valore predefinito ragionevole.
Pertanto, per questi tipi, il valore predefinito è un riferimento non valido che non può essere utilizzato senza causare un errore di Runtime.
Questa operazione è simile a un riferimento null in linguaggi come C# o Java.
Le matrici contenenti qubits o Callable devono essere inizializzate correttamente con valori non predefiniti prima che i relativi elementi possano essere usati in modo sicuro. È possibile trovare routine di inizializzazione appropriate in <xref:microsoft.quantum.arrays>.

I valori predefiniti per ogni tipo sono:

Type | Default
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | _Qubit non valido_
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | Intervallo vuoto, `1..1..0`
 `Callable` | _chiamabile non valido_
 `Array['T]` | `'T[0]`

I tipi di tupla sono elemento per elemento inizializzato.


### <a name="jagged-arrays"></a>Matrici irregolari

Una matrice di matrici, talvolta denominata "matrice di matrici", è una matrice i cui elementi sono matrici. Gli elementi di una matrice irregolare possono avere dimensioni diverse. Nell'esempio seguente viene illustrato come dichiarare e inizializzare una matrice di matrici che rappresenta una tabella di moltiplicazione.

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


### <a name="array-slices"></a>Sezioni di matrici

Data un'espressione di matrice e un'espressione `Range`, è possibile che venga creata una nuova espressione utilizzando l'operatore di sezionamento di `[` e `]`.
La nuova espressione sarà dello stesso tipo della matrice e conterrà gli elementi della matrice indicizzati dagli elementi del `Range`, nell'ordine definito dall'`Range`.
Se, ad esempio, `a` è associato a una matrice di `Double`s, `a[3..-1..0]` è un'espressione `Double[]` che contiene i primi quattro elementi di `a` ma nell'ordine inverso come appaiono in `a`.

Se la `Range` è vuota, la sezione della matrice risultante avrà una lunghezza pari a zero.

Se l'espressione di matrice non è un identificatore semplice, deve essere racchiusa tra parentesi per eseguire il sezionamento.
Ad esempio, se `a` e `b` sono entrambe matrici di `Int`s, una sezione della concatenazione verrebbe espressa come:

```qsharp
(a+b)[1..2..7]
```

Tutte le matrici in Q # sono in base zero.
Ovvero il primo elemento di una matrice `a` è sempre `a[0]`.

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

## <a name="array-element-expressions"></a>Espressioni di elementi di matrice

Data un'espressione di matrice e un'espressione `Int`, è possibile che venga creata una nuova espressione usando l'operatore `[` e `]` elemento Array.
La nuova espressione sarà dello stesso tipo del tipo di elemento della matrice.
Se ad esempio `a` è associato a una matrice di `Double`s, `a[4]` è un'espressione `Double`.

Se l'espressione di matrice non è un identificatore semplice, deve essere racchiusa tra parentesi per selezionare un elemento.
Ad esempio, se `a` e `b` sono entrambe matrici di `Int`s, un elemento dalla concatenazione verrebbe espresso come:

```qsharp
(a+b)[13]
```

Tutte le matrici in Q # sono in base zero.
Ovvero il primo elemento di una matrice `a` è sempre `a[0]`.


## <a name="copy-and-update-expressions"></a>Espressioni di copia e aggiornamento

È possibile creare nuove matrici da quelle esistenti tramite espressioni di copia e aggiornamento.
Un'espressione di copia e aggiornamento è un'espressione nel formato `expression1 w/ expression2 <- expression3`, dove `expression1` deve essere di tipo `T[]` per alcuni tipi `T`. Il secondo `expression2` definisce gli indici degli elementi da modificare rispetto alla matrice in `expression1` e deve essere di tipo `Int` o di tipo `Range`. Se `expression2` è di tipo `Int`, `expression3` deve essere di tipo `T`. Se `expression2` è di tipo `Range`, `expression3` deve essere di tipo `T[]`.

Un'espressione di copia e aggiornamento `arr w/ idx <- value` crea una nuova matrice con tutti gli elementi impostati sull'elemento corrispondente in `arr`, ad eccezione degli elementi in `idx`, che vengono impostati su uno o più elementi in `value`. Se, ad esempio, `arr` contiene una matrice `[0,1,2,3]`, 
- `arr w/ 0 <- 10` è l'`[10,1,2,3]`di matrici.
- `arr w/ 2 <- 10` è l'`[0,1,10,3]`di matrici.
- `arr w/ 0..2..3 <- [10,12]` è l'`[10,1,12,3]`di matrici.

Sono presenti espressioni simili per gli elementi denominati in tipi definiti dall'utente. Si consideri ad esempio il tipo 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
Se `c` contiene il valore di tipo `Complex(1.,-1.)`, `c w/ Re <- 0.` è un'espressione di tipo `Complex` che restituisce `Complex(0.,-1.)`.

## <a name="conditional-expressions"></a>Espressioni condizionali

Date due altre espressioni dello stesso tipo e di un'espressione booleana, l'espressione condizionale può essere formata usando il punto interrogativo `?` e la barra verticale `|`.
Ad esempio, `a==b ? c | d`.
In questo esempio, il valore dell'espressione condizionale verrà `c` se `a==b` è true e `d` se è false.

Le due espressioni possono restituire operazioni con gli stessi input e output ma supportano funtori diversi.
In questo caso, il tipo dell'espressione condizionale è un'operazione con gli input e gli output che supportano qualsiasi funtori supportato da entrambe le espressioni.
Ad esempio, se `Op1`, `Op2`e `Op3` sono tutti `Qubit[]=>Unit`, ma `Op1` supporta `Adjoint`, `Op2` supporta `Controlled`e `Op3` supporta entrambi:

- `flag ? Op1 | Op2` è un'operazione di `(Qubit[] => Unit)`.
- `flag ? Op1 | Op3` è un'operazione di `(Qubit[] => Unit is Adj)`.
- `flag ? Op2 | Op3` è un'operazione di `(Qubit[] => Unit is Ctl)`.

Se una delle due espressioni di risultato possibili include una funzione o una chiamata a un'operazione, la chiamata verrà eseguita solo se il risultato è quello che sarà il valore della chiamata.
Ad esempio, nel caso `a==b ? C(qs) | D(qs)`, se `a==b` è true, l'operazione di `C` verrà richiamata e se è false, verrà richiamato solo `D`.
Questa operazione è simile a un cortocircuito in altri linguaggi.


## <a name="operator-precedence"></a>Precedenza tra gli operatori

Tutti gli operatori binari sono associativi a destra, ad eccezione di `^`.

Le parentesi quadre, `[` e `]`, per l'indicizzazione e l'indicizzazione della matrice, vengono associate prima di qualsiasi operatore.

Funtori `Adjoint` e `Controlled` eseguire l'associazione dopo l'indicizzazione della matrice, ma prima di tutti gli altri operatori.

Anche le parentesi per la chiamata di operazioni e funzioni vengono associate prima di qualsiasi operatore, ma dopo l'indicizzazione della matrice e funtori.

Operatori in ordine di precedenza, dal più alto al più basso:

Operatore | Grado | Descrizione | Tipi di operando
---------|----------|---------|---------------
 `!` finali | Unaria | Unwrap | Qualsiasi tipo definito dall'utente
 `-`, `~~~`, `not` | Unaria | Valore numerico negativo, complemento bit per bit, negazione logica | `Int`, `BigInt` o `Double` per `-`, `Int` o `BigInt` per `~~~`, `Bool` per `not`
 `^` | Binary | Potenza intera | `Int` o `BigInt` per la base, `Int` per l'esponente
 `/`, `*`, `%` | Binary | Divisione, moltiplicazione, modulo Integer | `Int`, `BigInt` o `Double` per `/` e `*`, `Int` o `BigInt` per `%`
 `+`, `-` | Binary | Aggiunta o concatenazione di stringhe e matrici, sottrazione | `Int`, `BigInt` o `Double`, `String` o qualsiasi tipo di matrice per `+`
 `<<<`, `>>>` | Binary | Spostamento a sinistra, spostamento a destra | `Int` o `BigInt`
 `<`, `<=`, `>`, `>=` | Binary | Confronti minore di, minore di o uguale a, maggiore di, maggiore di o uguale a | `Int`, `BigInt` o `Double`
 `==`, `!=` | Binary | confronti uguali, non uguali | qualsiasi tipo primitivo
 `&&&` | Binary | AND bit per bit | `Int` o `BigInt`
 `^^^` | Binary | XOR bit per bit | `Int` o `BigInt`
 <code>\|\|\|</code> | Binary | OR bit per bit | `Int` o `BigInt`
 `and` | Binary | AND logico | `Bool`
 `or` | Binary | OR logico | `Bool`
 `..` | Binario/ternario | Operatore Range | `Int`
 `?` `|` | Ternario | Condizionali | `Bool` per il lato sinistro
`w/` `<-` | Ternario | Copia e aggiornamento | vedere [espressioni di copia e aggiornamento](#copy-and-update-expressions)
