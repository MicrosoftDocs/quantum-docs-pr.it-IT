---
title: Tipi in Q#
description: Informazioni sui diversi tipi usati nel linguaggio di Q# programmazione.
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
no-loc:
- Q#
- $$v
ms.openlocfilehash: 349138984387cc564cca18ea09c7bf161524b0b6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691611"
---
# <a name="types-in-no-locq"></a>Tipi in Q#

Questo articolo descrive il Q# modello di tipo e la sintassi per specificare e usare i tipi. Per informazioni dettagliate su come creare e usare espressioni di questi tipi, vedere [espressioni di tipo](xref:microsoft.quantum.guide.expressions).

Si noti che Q# è un linguaggio *fortemente tipizzato* , in modo che l'utilizzo accurato di questi tipi possa aiutare il compilatore a fornire garanzie complesse sui Q# programmi in fase di compilazione.
Per garantire le migliori garanzie possibili, le conversioni tra i tipi in Q# devono essere esplicite mediante chiamate a funzioni che esprimono tale conversione. 
Q# fornisce una varietà di funzioni di questo tipo come parte dello <xref:Microsoft.Quantum.Convert> spazio dei nomi.
I cast ai tipi compatibili, d'altra parte, si verificano in modo implicito. 

Q# fornisce entrambi i tipi primitivi, che vengono usati direttamente e diversi modi per produrre nuovi tipi da altri tipi.
Ognuno viene descritto nella parte restante di questo articolo.

## <a name="primitive-types"></a>Tipi primitivi

Il Q# linguaggio fornisce i *tipi primitivi* seguenti, che possono essere usati direttamente nei Q# programmi. È anche possibile usare questi tipi primitivi per costruire nuovi tipi.

- Il `Int` tipo rappresenta un intero con segno a 64 bit, ad esempio,,, `2` `107` `-5` .
- Il `BigInt` tipo rappresenta un intero con segno di dimensione arbitraria, ad esempio,, `2L` `107L` `-5L` .
   Questo tipo è basato su .NET <xref:System.Numerics.BigInteger>
   tipo.

- Il `Double` tipo rappresenta un numero a virgola mobile a precisione doppia, ad esempio,, `0.0` `-1.3` `4e-7` .
- Il `Bool` tipo rappresenta un valore booleano di `true` o `false` .
- Il `Range` tipo rappresenta una sequenza di numeri interi, identificati da `start..step..stop` , in cui la denotazione del passaggio è facoltativa. 
   Ad esempio, `start .. stop` corrisponde a `start..1..stop` e `1..2..7` rappresenta la sequenza $ \{ 1, 3, 5, 7 \} $.
- Il `String` tipo è una sequenza di caratteri Unicode che è opaca per l'utente dopo la creazione.
  Usare il `string` tipo per segnalare i messaggi a un host classico nel caso di un evento di errore o di diagnostica.
- Il `Unit` tipo può avere un solo valore, `()` . 
  Utilizzare questo tipo per indicare che una Q# funzione o un'operazione non restituisce alcuna informazione. 
- Il `Qubit` tipo rappresenta un bit Quantum o qubit.
   `Qubit`i sono opachi per l'utente. L'unica operazione possibile, ad eccezione del passaggio a un'altra operazione, consiste nel testare l'identità (uguaglianza).
   Infine, si implementano le azioni su `Qubit` s chiamando istruzioni intrinseche su un processore Quantum (o un simulatore Quantum).
- Il `Pauli` tipo rappresenta uno dei quattro operatori Pauli a qubit singola.
   Utilizzare questo tipo per indicare l'operazione di base per le rotazioni e per specificare la misura osservabile.
   Si tratta di un tipo enumerato che dispone di quattro valori possibili: `PauliI` , `PauliX` , `PauliY` e `PauliZ` , che sono costanti di tipo `Pauli` .
- Il `Result` tipo rappresenta il risultato di una misura.
   Si tratta di un tipo enumerato con due valori possibili: `One` e `Zero` , che sono costanti di tipo `Result` .
   `Zero` indica che è stato misurato il autovalore + 1; `One` indica che è stato misurato-1 autovalore.

Le costanti,,,,,, `true` `false` `PauliI` `PauliX` `PauliY` `PauliZ` `One` e `Zero` sono tutti simboli riservati in Q# .

## <a name="array-types"></a>Tipi di matrici

* Per qualsiasi Q# tipo valido, esiste un tipo che rappresenta una matrice di valori di quel tipo.
    Ad esempio, `Qubit[]` e `(Bool, Pauli)[]` rappresentano matrici di `Qubit` valori e `(Bool, Pauli)` valori di tupla.

* È anche valida una matrice di matrici. Espandendo l'esempio precedente, viene indicata una matrice di `(Bool, Pauli)` matrici `(Bool, Pauli)[][]` .

> [!NOTE] 
> Questo esempio, `(Bool, Pauli)[][]` , rappresenta una matrice di matrici potenzialmente irregolare e non una matrice bidimensionale rettangolare. Q# non supporta matrici multidimensionali rettangolari.

* È possibile scrivere un valore di matrice nel Q# codice sorgente usando le parentesi quadre intorno agli elementi di una matrice, come in `[PauliI, PauliX, PauliY, PauliZ]` .
Il tipo di base comune di tutti gli elementi nella matrice determina il tipo di un valore letterale di matrice. Di conseguenza, la costruzione di una matrice con elementi che non dispongono di un tipo di base comune genera un errore.  
Per un esempio, vedere [matrici di chiamabili](xref:microsoft.quantum.guide.expressions#arrays-of-callables).

    > [!WARNING]
    > Una volta creati, gli elementi di una matrice non possono essere modificati.
    > Per costruire una matrice modificata, usare [le istruzioni Update-and-reassign](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) oppure [le espressioni di copia e aggiornamento](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).

* In alternativa, è possibile creare una matrice dalle relative dimensioni usando la `new` parola chiave:

    ```qsharp
    let zeros = new Int[13];
    // you can also use new for creating empty arrays:
    let emptyRegister = new Qubit[0];
    ```

* Usare la funzione Core `Length` per ottenere il numero di elementi da una matrice come `Int` .
* Le matrici possono essere sottoposte a indicizzazione per ottenere singoli elementi o nuove matrici contenenti un subset degli elementi di una matrice.
Gli indici delle matrici sono in base zero e devono essere di tipo `Int` o di tipo `Range` :

    ```qsharp
    let arr = [10, 11, 36, 49];
    let ten = arr[0]; // 10
    let odds = arr[1..2..4]; // [11, 49]
    ```

## <a name="tuple-types"></a>Tipi di tupla

Le tuple sono un concetto potente usato Q# per raccogliere i valori in un unico valore, rendendolo più semplice da passare.
In particolare, usando la notazione di tupla, è possibile esprimere che ogni operazione e Callable accetta esattamente un input e restituisce esattamente un output.

* Dato zero o più tipi diversi `T0` ,,... `T1` , `Tn` , è possibile indicare un nuovo  *tipo di tupla* come `(T0, T1, ..., Tn)` .
I tipi utilizzati per costruire un nuovo tipo di tupla possono essere Tuple, come in `(Int, (Qubit, Qubit))` .
Tale annidamento è sempre finito, tuttavia, in quanto i tipi di tupla non possono in alcun caso contenere se stessi.

* I valori del nuovo tipo di tupla sono Tuple costituite da sequenze di valori di ogni tipo nella tupla.
Ad esempio, `(3, false)` è una tupla il cui tipo è il tipo di tupla `(Int, Bool)` .
È possibile creare matrici di tuple, Tuple di matrici, Tuple di sottotuple e così via.

* A partire da Q# 0,3, `Unit` è il nome del *tipo* della tupla vuota `()` . viene usato per il *valore* della tupla vuota.

* Le istanze di tupla non sono modificabili.
Q# non fornisce un meccanismo per modificare il contenuto di una tupla una volta creata.



### <a name="singleton-tuple-equivalence"></a>Equivalenza della tupla singleton

È possibile creare una tupla Singleton (elemento singolo) `('T1)` , ad esempio `(5)` o `([1,2,3])` .
Tuttavia, Q# tratta una tupla singleton come equivalente a un valore del tipo racchiuso.
Ovvero, non esiste alcuna differenza tra `5` e `(5)` , o tra `5` e `(((5)))` o tra `(5, (6))` e `(5, 6)` .
È altrettanto valido scrivere `(5)+3` così come è scrivere `5+3` . entrambe le espressioni restituiscono `8` .

Questa equivalenza si applica a tutti gli scopi, incluse le assegnazioni e le espressioni.
Dato qualsiasi espressione, la stessa espressione racchiusa tra parentesi è un'espressione dello stesso tipo.
Ad esempio, `(7)` è un'espressione di tipo `Int` , `([1,2,3])` è un'espressione di tipo `Int[]` e `((1,2))` è un'espressione di tipo `(Int, Int)` .

In particolare, ciò significa che è possibile visualizzare un'operazione o una funzione il cui tipo di tupla di input o di tupla di output ha un campo che accetta un singolo argomento o restituisce un singolo valore.

Si fa riferimento a questa proprietà come _equivalenza della tupla singleton_ .


## <a name="user-defined-types"></a>Tipi definiti dall'utente

Una dichiarazione del tipo definito dall'utente è costituita dalla parola chiave `newtype` , seguita dal nome del tipo definito dall'utente, da `=` , da una specifica del tipo valida e da un punto e virgola di terminazione.

Ad esempio:

```qsharp
newtype PairOfInts = (Int, Int);
```
    
* Ogni Q# file di origine può dichiarare un numero qualsiasi di tipi definiti dall'utente.
* I nomi dei tipi devono essere univoci all'interno di uno spazio dei nomi e non possono entrare in conflitto con i nomi di funzione e
* I tipi definiti dall'utente sono distinti, anche se i tipi di base sono identici.
In particolare, non viene eseguita alcuna conversione automatica tra i valori di due tipi definiti dall'utente, anche se i tipi sottostanti sono identici.

### <a name="named-vs-anonymous-items"></a>Elementi denominati e anonimi

Un Q# file può definire un nuovo tipo denominato contenente un singolo valore di qualsiasi tipo valido.
Per qualsiasi tipo di tupla `T` , è possibile dichiarare un nuovo tipo definito dall'utente che è un sottotipo di `T` con l' `newtype` istruzione.
Nello @"microsoft.quantum.math" spazio dei nomi, ad esempio, i numeri complessi sono definiti come tipo definito dall'utente:

```qsharp
newtype Complex = (Double, Double);
```
Questa istruzione crea un nuovo tipo con due elementi anonimi di tipo `Double` .   

A parte gli elementi anonimi, i tipi definiti dall'utente supportano anche *gli elementi denominati* a partire dalla Q# versione 0,7 o successiva. È ad esempio possibile denominare gli elementi per `Real` il valore Double che rappresenta la parte reale di un numero complesso e `Imag` per la parte immaginaria: 

```qsharp
newtype Complex = (Real : Double, Imag : Double);
```
La denominazione di un elemento in un tipo definito dall'utente non implica che tutti gli elementi devono essere denominati. sono supportate tutte le combinazioni di elementi denominati e senza nome. Inoltre, gli elementi interni possono anche essere denominati.
Il tipo `Nested` , come definito di seguito, ad esempio, ha un tipo sottostante `(Double, (Int, String))` , di cui solo l'elemento di tipo `Int` è denominato e tutti gli altri elementi sono anonimi. 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

Gli elementi denominati hanno il vantaggio di poter accedere direttamente tramite l' *operatore di accesso* `::` . 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Real + c2::Real, c1::Imag + c2::Imag);
}
```

Oltre a fornire alias brevi per i tipi di tupla potenzialmente complessi, un vantaggio significativo della definizione di tali tipi è che possono documentare lo scopo di un determinato valore.
Tornando all'esempio di `Complex` , è possibile che sia stata definita anche una coordinata polare rappresentazione come tipo definito dall'utente:

```qsharp
newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```

Anche se entrambi `Complex` `ComplexPolar` i tipi e hanno entrambi un tipo sottostante `(Double, Double)` , i due tipi sono completamente incompatibili in Q# , riducendo al minimo il rischio di chiamare accidentalmente una funzione matematica complessa con coordinate polari e viceversa.

#### <a name="access-anonymous-items-with-the-unwrap-operator"></a>Accedere a elementi anonimi con l'operatore Unwrap

Per accedere agli elementi anonimi, estrarre innanzitutto il valore di cui è stato eseguito il wrapped usando l'operatore Postfix `!` .
Con l'operatore "Unwrap", `!` è possibile estrarre il valore contenuto in un tipo definito dall'utente.
Il tipo di un'espressione "Unwrap" è il tipo sottostante del tipo definito dall'utente. 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

Un singolo operatore Unwrap Annulla il wrapping di un livello di wrapping. Usare più operatori Unwrap per accedere a un valore con wrapping multiplo.

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

Per ulteriori informazioni sull'operatore Unwrap, vedere [espressioni di tipo in Q# ](xref:microsoft.quantum.guide.expressions).

### <a name="creating-values-of-user-defined-types"></a>Creazione di valori di tipi definiti dall'utente

Creare valori di un tipo definito dall'utente chiamando il costruttore del tipo corrispondente:

```qsharp
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

In alternativa, è possibile creare nuovi valori da quelli esistenti usando [le espressioni di copia e aggiornamento](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions). Analogamente a quanto avviene con le matrici, le espressioni di copia e aggiornamento copiano tutti i valori degli elementi dell'espressione originale, ad eccezione degli elementi denominati specificati. Per queste eccezioni, i valori di questi elementi sono i valori definiti sul lato destro dell'espressione. Tutti gli altri costrutti di linguaggio disponibili per gli elementi della matrice, ad esempio le [istruzioni Update e reassign](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), esistono anche per gli elementi denominati nei tipi definiti dall'utente.

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

* È possibile usare i tipi definiti dall'utente in qualsiasi punto in cui si usano altri tipi.
In particolare, è possibile definire una matrice di un tipo definito dall'utente e includere un tipo definito dall'utente come elemento di un tipo di tupla.

* Non è possibile creare strutture di tipo ricorsivo.
Ovvero, il tipo che definisce un tipo definito dall'utente non può essere un tipo di tupla che include un elemento del tipo definito dall'utente.
Più in generale, i tipi definiti dall'utente potrebbero non avere dipendenze cicliche tra loro, quindi il set di definizioni di tipo seguente non è valido:

    ```qsharp
    newtype TypeA = (Int, TypeB);
    newtype TypeB = (Double, TypeC);
    newtype TypeC = (TypeA, Range);
    ```


## <a name="operation-and-function-types"></a>Tipi di operazioni e funzioni

Dati i tipi `'Tinput` e `'Tresult` :

* `('Tinput => 'Tresult)` è il tipo di base per qualsiasi *operazione* , ad esempio `((Qubit, Pauli) => Result)` .
* `('Tinput -> 'Tresult)` è il tipo di base per qualsiasi *funzione* , ad esempio `(Int -> Int)` . 

Questi sono detti *firma* dell'oggetto chiamabile.

* Tutte le Q# Callable accettano un singolo valore come input e restituiscono un singolo valore come output.
* È possibile utilizzare le tuple per i valori di input e di output.
* Chiamabili senza risultato, restituiscono `Unit` .
* Le chiamabili senza input accettano la tupla vuota come input.

### <a name="functors"></a>Funtori

I tipi di *funzione* sono completamente specificati dalla relativa firma. Ad esempio, una funzione che calcola il seno di un angolo avrebbe il tipo `(Double -> Double)` . 

*Le operazioni* hanno determinate caratteristiche aggiuntive espresse come parte del tipo di operazione. Tali caratteristiche includono le informazioni sul *funtori* supportato dall'operazione.
Se, ad esempio, l'esecuzione dell'operazione si basa sullo stato di altri qubits, deve supportare il `Controlled` functor; se l'operazione ha un inverso, deve supportare il `Adjoint` functor.

> [!NOTE]
> Questo articolo illustra solo il modo in cui funtori modifica la firma dell'operazione. Per ulteriori informazioni su funtori e sulle operazioni, vedere [operazioni e funzioni Q# in ](xref:microsoft.quantum.guide.operationsfunctions). 

Per richiedere il supporto per `Controlled` e/o `Adjoint` functor in un tipo di operazione, è necessario aggiungere un'annotazione che indichi le caratteristiche corrispondenti.
L'annotazione `is Ctl` , ad esempio, `(Qubit => Unit is Ctl)` indica che l'operazione è controllabile. Ovvero, la relativa esecuzione si basa sullo stato di un altro qubit o qubits. Analogamente, l'annotazione `is Adj` indica che l'operazione ha un contiguo, ovvero può essere "invertito" in modo che l'applicazione successiva di un'operazione e quindi il relativo contiguo a uno stato lasci lo stato invariato. 

Se si vuole richiedere che un'operazione di quel tipo supporti sia il `Adjoint` `Controlled` functor che l'espressione `(Qubit => Unit is Adj + Ctl)` . L'operazione di Pauli incorporata, ad esempio, <xref:Microsoft.Quantum.Intrinsic.X> è di tipo `(Qubit => Unit is Adj + Ctl)` . 

Un tipo di operazione che non supporta alcun funtori viene specificato solo dal tipo di input e di output, senza alcuna annotazione aggiuntiva.

### <a name="type-parameterized-functions-and-operations"></a>Funzioni e operazioni Type-Parameterized

I tipi chiamabili possono contenere *parametri di tipo* .
Usare un simbolo preceduto da una virgoletta singola per indicare un parametro di tipo; ad esempio, `'A` è un parametro di tipo valido.
Per ulteriori informazioni e dettagli su come definire le funzioni chiamabili con parametri di tipo, vedere [operazioni e Q# funzioni in ](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables).

Un parametro di tipo può essere visualizzato più di una volta in un'unica firma.
Ad esempio, una funzione che applica un'altra funzione a ogni elemento di una matrice e restituisce la firma dei risultati raccolti `(('A[], 'A->'A) -> 'A[])` .
Analogamente, una funzione che restituisce la composizione di due operazioni dispone della firma `((('A=>'B), ('B=>'C)) -> ('A=>'C))` .

Quando si richiama un oggetto chiamabile con parametri di tipo, tutti gli argomenti che hanno lo stesso parametro di tipo devono essere dello stesso tipo.

Q# non fornisce un meccanismo per vincolare i possibili tipi che possono essere sostituiti da un utente per un parametro di tipo.

## <a name="next-steps"></a>Passaggi successivi

Ora che sono stati visualizzati tutti i tipi che includono il Q# linguaggio, vedere [espressioni di tipo in Q# ](xref:microsoft.quantum.guide.expressions) per informazioni su come creare e modificare le espressioni di questi diversi tipi.
