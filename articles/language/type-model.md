---
title: 'Tipi di dati Q #'
description: "Informazioni sui diversi tipi usati nel linguaggio di programmazione Q #, inclusi tipi incorporati, matrici, Tuple, operazioni, funzioni e tipi definiti dall'utente."
author: QuantumWriter
uid: microsoft.quantum.language.type-model
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 1fc4c0b3fed9277c7f9f3ac421330df03c1b30e4
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904656"
---
# <a name="the-type-model"></a>Modello di tipo

In questa sezione viene illustrato il modello di tipo Q # e viene descritta la sintassi per specificare e utilizzare i tipi.
Si noti che Q # è un linguaggio *fortemente tipizzato* , in modo che l'utilizzo accurato di questi tipi possa aiutare il compilatore a fornire garanzie complesse sui programmi Q # in fase di compilazione.

Per garantire le migliori garanzie possibili, le conversioni tra i tipi in Q # devono essere esplicite usando chiamate a funzioni che esprimono tale conversione. Una serie di funzioni di questo tipo viene fornita come parte dello spazio dei nomi <xref:microsoft.quantum.convert>.
I cast ai tipi compatibili, invece, si verificano in modo implicito. 

Q # fornisce entrambi i tipi primitivi, che possono essere usati direttamente e diversi modi per produrre nuovi tipi da altri tipi.
Ognuno viene descritto nella parte restante di questa sezione.

## <a name="primitive-types"></a>Tipi primitivi

Il linguaggio Q # offre diversi *tipi primitivi*, da cui è possibile costruire altri tipi:

- Il tipo di `Int` rappresenta un intero con segno a 64 bit, ad esempio: `2`, `107``-5`.
- Il tipo di `BigInt` rappresenta un intero con segno di dimensione arbitraria, ad esempio `2L`, `107L``-5L`.
   Questo tipo è basato su .NET <xref:System.Numerics.BigInteger>
   tipo.
- Il tipo di `Double` rappresenta un numero a virgola mobile a precisione doppia, ad esempio `0.0`, `-1.3``4e-7`.
- Il tipo di `Bool` rappresenta un valore booleano che può essere `true` o `false`.
- Il tipo di `Qubit` rappresenta un bit Quantum o qubit.
   `Qubit`s sono opachi per l'utente; l'unica operazione possibile, ad eccezione del passaggio a un'altra operazione, consiste nel testare l'identità (uguaglianza).
   Infine, le azioni su `Qubit`s vengono implementate chiamando istruzioni intrinseche su un processore quantico (o una simulazione).
- Il tipo di `Pauli` rappresenta uno dei quattro operatori Pauli a qubit singola.
   Questo tipo viene utilizzato per indicare l'operazione di base per le rotazioni e per specificare la misura osservabile.
   Si tratta di un tipo enumerato che dispone di quattro valori possibili: `PauliI`, `PauliX`, `PauliY`e `PauliZ`, che sono costanti di tipo `Pauli`.
- Il tipo di `Result` rappresenta il risultato di una misura.
   Si tratta di un tipo enumerato con due valori possibili: `One` e `Zero`, che sono costanti di tipo `Result`.
   `Zero` indica che è stato misurato il autovalore + 1; `One` indica il autovalore-1.
- Il tipo di `Range` rappresenta una sequenza di numeri interi, indicata da `start..step..stop`, in cui il passaggio indica che il passaggio è options. 
   `start .. stop` corrisponde a `start..1..stop`e, ad esempio, `1..2..7` rappresenta la sequenza $\{1, 3, 5, 7\}$.
- Il tipo di `String` è una sequenza di caratteri Unicode che è opaca per l'utente dopo la creazione.
  Questo tipo viene usato per segnalare i messaggi a un host classico nel caso di un evento di errore o di diagnostica.
- Il tipo di `Unit` è il tipo che consente un solo valore `()`. 
  Questo tipo viene usato per indicare che la funzione o l'operazione Q # non restituisce alcuna informazione. 

Le costanti `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`e `Zero` sono tutti simboli riservati in Q #.

## <a name="array-types"></a>Tipi di matrice

Dato qualsiasi `'T`di tipo Q # valido, esiste un tipo che rappresenta una matrice di valori di tipo `'T`.
Questo tipo di matrice è rappresentato come `'T[]`; ad esempio, `Qubit[]` o `Int[][]`.
Una raccolta di numeri interi, ad esempio, è indicata `Int[]`, mentre una matrice di matrici di valori `(Bool, Pauli)` è indicata `(Bool, Pauli)[][]`.

Nel secondo esempio si noti che questo rappresenta una matrice di matrici potenzialmente irregolare e non una matrice bidimensionale rettangolare.
Q # non fornisce il supporto per le matrici multidimensionali rettangolari.

È possibile scrivere un valore di matrice nel codice sorgente Q # usando le parentesi quadre attorno agli elementi di una matrice, come in `[PauliI, PauliX, PauliY, PauliZ]`.
Il tipo di un valore letterale di matrice è determinato dal tipo di base comune di tutti gli elementi nella matrice. 

> [!WARNING]
> Gli elementi di una matrice non possono essere modificati dopo la creazione della matrice.
> Per costruire una matrice modificata è possibile utilizzare le istruzioni Update-and-reassign e/o le espressioni di copia e aggiornamento.

In alternativa, è possibile creare una matrice dalle relative dimensioni usando la parola chiave `new`:

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

In entrambi i casi, una volta costruita una matrice, è possibile usare la funzione Core `Length` per ottenere il numero di elementi come `Int`.
Le matrici possono essere sottoposte a indicizzazione usando parentesi quadre, con indici di tipo `Int` o tipo `Range`, per ottenere singoli elementi o nuove matrici contenenti un subset degli elementi di una matrice.
Gli indici delle matrici sono in base zero:

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a>Tipi di tupla

Dato zero o più tipi diversi `T0`, `T1`,... `Tn`, è possibile indicare un nuovo tipo di *tupla* come `(T0, T1, ..., Tn)`.
I tipi utilizzati per costruire un nuovo tipo di tupla possono essere Tuple, come in `(Int, (Qubit, Qubit))`.
Tale annidamento è sempre finito, tuttavia, in quanto i tipi di tupla non possono in alcun caso contenere se stessi.

I valori del nuovo tipo di tupla sono Tuple costituite da sequenze di valori di ogni tipo nella tupla.
Ad esempio, `(3, false)` è una tupla il cui tipo è il tipo di tupla `(Int, Bool)`.
È possibile creare matrici di tuple, Tuple di matrici, Tuple di sottotuple e così via.

A partire da Q # 0,3, `Unit` è il nome del *tipo* della tupla vuota; `()` viene usato per il *valore*della tupla vuota.

Le istanze di tupla non sono modificabili.
Q # non fornisce un meccanismo per modificare il contenuto di una tupla una volta creata.

Le tuple sono un concetto potente usato in Q # per raccogliere i valori in un unico valore, semplificando il passaggio.
In particolare, usando la notazione di tupla, possiamo esprimere che ogni operazione e Callable accetta esattamente un input e restituisce esattamente un output.

### <a name="singleton-tuple-equivalence"></a>Equivalenza della tupla singleton

È possibile creare una tupla (a elemento singolo) singleton, `('T1)`, ad esempio `(5)` o `([1,2,3])`.
Tuttavia, Q # considera una tupla singleton come completamente equivalente a un valore del tipo racchiuso.
Ovvero, non esiste alcuna differenza tra `5` e `(5)`o tra `5` e `(((5)))`oppure tra `(5, (6))` e `(5, 6)`.

Questa equivalenza si applica a tutti gli scopi, incluse le assegnazioni e le espressioni.
È altrettanto valido scrivere `(5)+3` come per scrivere `5+3`ed entrambe le espressioni restituiranno `8`.
In particolare, ciò significa che un'operazione o una funzione la cui tupla di input o il tipo di tupla di output ha un campo può essere considerato come accettare un singolo argomento o restituire un singolo valore.

Si fa riferimento a questa proprietà come _equivalenza della tupla singleton_.

## <a name="user-defined-types"></a>Tipi definiti dall'utente

Un file Q # può definire un nuovo tipo denominato contenente un singolo valore di qualsiasi tipo valido.
Per qualsiasi tipo di tupla `T`, è possibile dichiarare un nuovo tipo definito dall'utente che è un sottotipo di `T` con l'istruzione `newtype`.
Nello spazio dei nomi @"microsoft.quantum.math", ad esempio, i numeri complessi sono definiti come tipo definito dall'utente:

```qsharp
newtype Complex = (Double, Double);
```

Questa istruzione crea un nuovo tipo con due elementi anonimi di tipo `Double`.   
A parte gli elementi anonimi, i tipi definiti dall'utente supportano anche gli elementi denominati a partire da Q # versione 0,7 o successiva. Ad esempio, avremmo potuto denominare gli elementi `Re` per il valore Double che rappresenta la parte reale di un numero complesso e `Im` per la parte immaginaria: 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
La denominazione di un elemento in un tipo definito dall'utente non implica che tutti gli elementi devono essere denominati. è supportata qualsiasi combinazione di elementi denominati e non denominati. Inoltre, gli elementi interni possono essere denominati.
Il tipo `Nested` come definito di seguito, ad esempio, ha un tipo sottostante `(Double, (Int, String))`, di cui solo l'elemento di tipo `Int` è denominato e tutti gli altri elementi sono anonimi. 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```
Gli elementi denominati hanno il vantaggio di poter accedere direttamente tramite l'operatore di accesso `::`. 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

Per accedere agli elementi anonimi, è necessario innanzitutto estrarre il valore di cui è stato eseguito il wrapped utilizzando l'operatore di suffisso `!`.
L'operatore "Unwrap", `!`, consente di estrarre il valore contenuto in un tipo definito dall'utente.
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

Per altri dettagli, vedere la sezione relativa alla [precedenza degli operatori](xref:microsoft.quantum.language.expressions#operator-precedence) e delle [espressioni Unwrap](xref:microsoft.quantum.language.expressions#unwrap-expressions) .

I valori di un tipo definito dall'utente possono essere creati chiamando il costruttore del tipo corrispondente:

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

In alternativa, è possibile creare nuovi valori da quelli esistenti usando [le espressioni di copia e aggiornamento](xref:microsoft.quantum.language.expressions#copy-and-update-expressions). Analogamente alle matrici, tali espressioni copiano tutti i valori degli elementi dell'espressione originale, ad eccezione degli elementi denominati specificati. Per questi valori, i valori vengono impostati su quelli definiti sul lato destro dell'espressione. Tutti gli altri costrutti di linguaggio, come ad esempio le [istruzioni Update-and-reassign](xref:microsoft.quantum.language.statements#update-and-reassign-statement), disponibili per gli elementi della matrice esistono anche per gli elementi denominati nei tipi definiti dall'utente.

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

Non è possibile creare strutture di tipo ricorsivo.
Ovvero, il tipo che definisce un tipo definito dall'utente non può essere un tipo di tupla che include un elemento del tipo definito dall'utente.
Più in generale, i tipi definiti dall'utente potrebbero non avere dipendenze cicliche tra loro, quindi il set di definizioni di tipi seguente non è valido:

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```

Oltre a fornire alias brevi per i tipi di tupla potenzialmente complessi, un vantaggio significativo della definizione di tali tipi è che possono documentare lo scopo di un determinato valore.
Tornando all'esempio di `Complex`, è possibile definire anche le coordinate polari 2D come tipo definito dall'utente:

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

Anche se sia `Complex` che `Polar` hanno entrambi un tipo sottostante `(Double, Double)`, i due tipi sono completamente incompatibili in Q #, riducendo al minimo il rischio di chiamare accidentalmente una funzione matematica complessa con coordinate polari e viceversa.
In questo modo, i tipi definiti dall'utente hanno un ruolo simile a quello F# dei record in, ad esempio. 


## <a name="operation-and-function-types"></a>Tipi di operazioni e funzioni

Un' _operazione_ Q # è una subroutine Quantum.
vale a dire una routine chiamabile che contiene operazioni quantistiche.

Una _funzione_ Q # è una subroutine classica usata all'interno di un algoritmo Quantum.
Può contenere codice classico, ma nessuna operazione quantistica.
In particolare, le funzioni non possono allocare o prendere in prestito qubits, né possono chiamare operazioni.
È tuttavia possibile passare le operazioni o qubits per l'elaborazione.
Le funzioni sono quindi completamente deterministiche, nel senso che la chiamata con gli stessi argomenti genererà sempre lo stesso risultato. 

Insieme, le operazioni e le funzioni vengono chiamate _Callable_.  È possibile vedere alcuni [esempi](#examples) di questi esempi.

Tutti i chiamanti Q # sono considerati come input e restituiscono un singolo valore come output.
Sia i valori di input che quelli di output possono essere Tuple.
Chiamabili senza risultato restituito `Unit`.
Le chiamabili senza input accettano la tupla vuota come input.

Il tipo di base per qualsiasi chiamata chiamabile viene scritto come `('Tinput => 'Tresult)` o `('Tinput -> 'Tresult)`, in cui sia `'Tinput` che `'Tresult` sono tipi.
Il primo form, con `=>`, viene usato per le operazioni; secondo form, con `->`, per le funzioni.
Ad esempio, `((Qubit, Pauli) => Result)` rappresenta la firma per una possibile operazione di misurazione a qubit singola.

I tipi di funzione sono completamente specificati dalla relativa firma.
Ad esempio, una funzione che calcola il seno di un angolo avrà il tipo `(Double -> Double)`.

Le operazioni, ma non le funzioni, hanno determinate _caratteristiche_ aggiuntive espresse come parte del tipo di operazione. Tali caratteristiche includono informazioni sul funtori supportato dall'operazione.
Funtori sono metaoperazioni che generano una specializzazione di un'operazione di base. vedere [funtori](#functors), di seguito.

I tipi di operazione sono specificati dal tipo di input, dal tipo di output e dalle relative caratteristiche.    
Per richiedere il supporto per il `Controlled` e/o l'`Adjoint` functore in un tipo di operazione, è necessario aggiungere un'annotazione che indichi le caratteristiche corrispondenti.
Un'annotazione `is Ctl` ad esempio indica che l'operazione è controllabile. Se si vuole richiedere che un'operazione di quel tipo supporti sia il `Adjoint` che il functore di `Controlled`, è possibile esprimere questo tipo di `(Qubit => Unit is Adj + Ctl)`. Le caratteristiche dell'operazione utilizzate `Adj` e `Ctl` in modo rigoroso sono due set predefiniti di etichette, in cui ogni etichetta indica determinate caratteristiche dell'operazione, ad esempio il supporto per un particolare functore.
Di conseguenza, `+` viene usato per indicare l'Unione di questi due set e viene usato `*` per indicare l'intersezione, ovvero le etichette comuni a entrambi i set.  

Ad esempio, l'operazione di `X` di Pauli è di tipo `(Qubit => Unit is Adj + Ctl)`.
Un tipo di operazione che non supporta alcun funtori viene specificato solo dal tipo di input e di output, senza alcuna annotazione aggiuntiva.


### <a name="type-parameterized-functions-and-operations"></a>Funzioni e operazioni con parametri di tipo

I tipi chiamabili possono contenere parametri di tipo.
I parametri di tipo sono indicati da un simbolo preceduto da una virgoletta singola; ad esempio, `'A` è un parametro di tipo valido.

Un parametro di tipo può essere visualizzato più di una volta in un'unica firma.
Ad esempio, una funzione che applica un'altra funzione a ogni elemento di una matrice e restituisce i risultati raccolti avrebbe la firma `(('A[], 'A->'A) -> 'A[])`.
Analogamente, una funzione che restituisce la composizione di due operazioni potrebbe avere la firma `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.

Quando si richiama un oggetto chiamabile con parametri di tipo, tutti gli argomenti che hanno lo stesso parametro di tipo devono essere dello stesso tipo.

Q # non fornisce un meccanismo per vincolare i possibili tipi che possono essere sostituiti per un parametro di tipo.

### <a name="type-compatibility"></a>Compatibilità tra tipi

Un'operazione con funtori aggiuntivi supportata può essere usata ovunque un'operazione con un numero di funtori inferiore ma è prevista la stessa firma.
Ad esempio, un'operazione di tipo `(Qubit => Unit is Adj)` può essere utilizzata ovunque sia prevista un'operazione di tipo `(Qubit => Unit)`.

Q # è covariante rispetto ai tipi restituiti richiamabili: un chiamabile che restituisce un tipo `'A` è compatibile con un oggetto chiamabile con lo stesso tipo di input e un tipo di risultato con cui `'A` è compatibile.

Q # è controvariante rispetto ai tipi di input: un oggetto chiamabile che accetta un tipo `'A` come input è compatibile con un oggetto chiamabile con lo stesso tipo di risultato e un tipo di input compatibile con `'A`.

Ovvero, date le seguenti definizioni:

```qsharp
operation Invert(qubits : Qubit[]) : Unit 
is Adj {...} 

operation ApplyUnitary(qubits : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertWith(
    inner : (Qubit[] => Unit is Adj),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith(
    inner : (Qubit[] => Unit is Adj + Ctl),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

sono soddisfatte le condizioni seguenti:

- Il `ConjugateInvertWith` di funzione può essere richiamato con un argomento `inner` di `Invert` o `ApplyUnitary`.
- Il `ConjugateUnitaryWith` di funzione può essere richiamato con un argomento `inner` di `ApplyUnitary`, ma non `Invert`.
- Da `ConjugateInvertWith`può essere restituito un valore di tipo `(Qubit[] => Unit is Adj + Ctl)`.

> [!IMPORTANT]
> Q # 0,3 introduce una differenza significativa nel comportamento dei tipi definiti dall'utente.

I tipi definiti dall'utente vengono considerati come una versione di cui è stato eseguito il wrapped del tipo sottostante, anziché come sottotipo.
Ciò significa che un valore di un tipo definito dall'utente non può essere utilizzato quando è previsto un valore del tipo sottostante.

### <a name="functors"></a>Funtori

Un functor in Q # è una factory che definisce una nuova operazione da un'altra operazione.
Funtori hanno accesso all'implementazione dell'operazione di base quando si definisce l'implementazione della nuova operazione.
Funtori può quindi eseguire funzioni più complesse rispetto alle funzioni di livello superiore tradizionali.

Funtori non dispone di una rappresentazione nel sistema di tipi Q #. Attualmente non è possibile associarli a una variabile o passarli come argomenti. 

Un functor viene usato applicando l'oggetto a un'operazione, restituendo una nuova operazione.
Ad esempio, l'operazione risultante dall'applicazione del `Adjoint` functore all'operazione `Y` viene scritta come `Adjoint Y`.
La nuova operazione può quindi essere richiamata come qualsiasi altra operazione.
Pertanto, `Adjoint Y(q1)` applica il functor adiacente all'operazione `Y` per generare una nuova operazione e applica tale nuova operazione al `q1`.

Allo stesso modo, `Controlled X(controls, target)` applica il functor controllato all'operazione `X` per generare una nuova operazione e applica tale nuova operazione a `controls` e `target`.

I due funtori standard in Q # sono `Adjoint` e `Controlled`.

#### <a name="adjoint"></a>Adjoint

In quantum computing, il contiguo di un'operazione è la trasportazione complessa del coniugato dell'operazione.
Per le operazioni che implementano un operatore unitario, l'elemento contiguo è l'inverso dell'operazione.
Per un'operazione semplice che richiama solo una sequenza di altre operazioni Unite su un set di qubits, l'elemento contiguo può essere calcolato applicando gli elementi adiacenti delle sottooperazioni nello stesso qubits, nella sequenza inversa.

Data un'espressione di operazione, è possibile formare una nuova espressione di operazione usando il `Adjoint` functor.
Ad esempio, `Adjoint QFT` definisce il contiguo dell'operazione di `QFT`.
La nuova operazione ha la stessa firma e il tipo dell'operazione di base.
In particolare, la nuova operazione consente anche `Adjoint`e consentirà `Controlled` solo se è stata eseguita l'operazione di base.

Il functor contiguo è il proprio inverso; ovvero, `Adjoint Adjoint Op` è sempre uguale `Op`.

#### <a name="controlled"></a>Controllato

La versione controllata di un'operazione è una nuova operazione che applica efficacemente l'operazione di base solo se tutti i qubits di controllo si trovano in uno stato specificato.
Se il controllo qubits si trova in una posizione sovraposizionata, l'operazione di base viene applicata in modo coerente alla parte appropriata della superposizione.
In questo modo, le operazioni controllate vengono spesso usate per generare il groviglio.

In Q #, le versioni controllate accettano sempre una matrice di qubits di controllo e lo stato specificato è sempre per tutti i qubits del controllo in modo che siano nello stato del `One` computazionale (`PauliZ`), $ \ket{1}$.
Il controllo basato su altri Stati può essere ottenuto applicando l'operazione unitaria appropriata al controllo qubits prima dell'operazione controllata, quindi applicando gli inversi dell'operazione unitaria dopo l'operazione controllata.
Se ad esempio si applica un'operazione `X` a un controllo qubit prima e dopo un'operazione controllata, l'operazione verrà controllata sullo stato `Zero` ($ \ket{0}$) per tale qubit; l'applicazione di un'operazione di `H` prima e dopo controllerà lo stato di `One` `PauliX`, ovvero-1 autovalore di Pauli X, $ \ket{-} \mathrel{: =} (\ket{0}-\ket{1})/\sqrt{2}$ anziché lo stato `PauliZ` `One`.

Data un'espressione di operazione, è possibile formare una nuova espressione di operazione usando il `Controlled` functor.
La firma della nuova operazione si basa sulla firma dell'operazione originale.
Il tipo di risultato è lo stesso, ma il tipo di input è una tupla con due tuple con una matrice qubit che include i qubit del controllo come primo elemento e gli argomenti dell'operazione originale come secondo elemento.
La nuova operazione supporta `Controlled`e supporterà `Adjoint` solo se l'operazione originale è stata eseguita.

Se l'operazione originale ha accettato un solo argomento, l'equivalenza della tupla singleton entrerà in gioco qui.
Ad esempio, `Controlled X` è la versione controllata dell'operazione di `X`.
`X` è di tipo `(Qubit => Unit is Adj + Ctl)`, quindi `Controlled X` è di tipo `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; a causa dell'equivalenza della tupla singleton, questo è lo stesso `((Qubit[], Qubit) => Unit is Adj + Ctl)`.

Se l'operazione di base ha assunto diversi argomenti, ricordarsi di racchiudere tra parentesi gli argomenti corrispondenti della versione controllata dell'operazione per convertirli in una tupla.
Ad esempio, `Controlled Rz` è la versione controllata dell'operazione di `Rz`.
`Rz` è di tipo `((Double, Qubit) => Unit is Adj + Ctl)`, quindi `Controlled Rz` ha il tipo `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.
Pertanto, `Controlled Rz(controls, (0.1, target))` sarebbe una chiamata valida di `Controlled Rz` (si notino le parentesi intorno `0.1, target`).

Come altro esempio, `CNOT(control, target)` può essere implementato come `Controlled X([control], target)`. Se una destinazione deve essere controllata da 2 Control qubits (CCNOT), è possibile usare `Controlled X([control1, control2], target)` istruzione.

### <a name="examples"></a>Esempi

Questo esempio di operazione Q # deriva dall'esempio di [misurazione](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/measurement) . All'interno delle operazioni, è possibile allocare qubits e usare operazioni Quantum su tali qubits, ad esempio `H` e `X`:

```qsharp
/// # Summary
/// Prepares a state and measures it in the Pauli-Z basis.
operation MeasureOneQubit() : Result {
        mutable result = Zero;

        using (qubit = Qubit()) { // Allocate a qubit
            H(qubit);               // Use a quantum operation on that qubit
            set result = M(qubit);      // Measure the qubit
            if (result == One) {    // Reset the qubit so that it can be released
                X(qubit);
            }

            return result;
        }
 }
```

Questo esempio di una funzione deriva dall'esempio [PhaseEstimation](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation) . Contiene codice puramente classico. Si può notare che, a differenza dell'esempio precedente, non vengono allocati qubits e non vengono usate operazioni Quantum.

```qsharp
/// # Summary
/// Given two arrays, returns a new array that is the pointwise product
/// of each of the given arrays.
function PointwiseProduct(left : Double[], right : Double[]) : Double[] {
    mutable product = new Double[Length(left)];

    for (idxElement in IndexRange(left)) {
        set product w/= idxElement <- left[idxElement] * right[idxElement];
    }
    return product;
}
```

È anche possibile passare una funzione qubits per l'elaborazione, come in questo esempio dell'esempio [ReversibleLogicSynthesis](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/reversible-logic-synthesis) . Qubits vengono passati alla funzione e usati per l'elaborazione, anche se in nessun momento gli Stati qubit sono stati modificati.

```qsharp
/// # Summary
/// Translate MCT masks into multiple-controlled Toffoli gates (with single
/// targets).
function GateMasksToToffoliGates(
    qubits : Qubit[], 
    masks : MCMTMask[]) 
: MCTGate[] {

    mutable result = new MCTGate[0];
    let n = Length(qubits);

    for (i in 0 .. Length(masks) - 1) {
        let (controls, targets) = (masks[i])!;
        let controlBits = IntegerBits(controls, n);
        let targetBits = IntegerBits(targets, n);
        let cQubits = Subarray(controlBits, qubits);
        let tQubits = Subarray(targetBits, qubits);

        for (target in tQubits) {
            set result += [MCTGate(cQubits, target)];
        }
    }

    return result;
}
```
