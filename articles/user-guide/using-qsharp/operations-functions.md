---
title: 'Operazioni e funzioni in Q #'
description: Come definire e chiamare operazioni e funzioni, nonché le specializzazioni delle operazioni controllate e contigue.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
ms.openlocfilehash: 6cfc1b14d86e86a1cbf0109d5e81dfe50c3a80bf
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630224"
---
# <a name="operations-and-functions-in-q"></a>Operazioni e funzioni in Q #

## <a name="defining-new-operations"></a>Definizione di nuove operazioni

Le operazioni sono il nucleo di Q #.
Una volta dichiarate, possono essere chiamate da applicazioni .NET classiche, ad esempio usando un simulatore o altre operazioni all'interno di Q #.
Ogni operazione definita in Q # può quindi chiamare un numero qualsiasi di altre operazioni, incluse le operazioni intrinseche predefinite definite dal linguaggio. Il modo specifico in cui vengono definite queste operazioni intrinseche dipende dal computer di destinazione.
Quando viene compilata, ogni operazione viene rappresentata come tipo di classe .NET che può essere fornita ai computer di destinazione.

Ogni file di origine Q # può definire un numero qualsiasi di operazioni.
I nomi delle operazioni devono essere univoci all'interno di uno spazio dei nomi e non possono entrare in conflitto con i nomi di tipo o

Una dichiarazione di operazione è costituita dalla parola chiave `operation` , seguita dal simbolo che rappresenta il nome dell'operazione, una tupla di identificatori tipizzati che definisce gli argomenti per l'operazione, due punti `:` , un'annotazione di tipo che descrive il tipo di risultato dell'operazione, facoltativamente un'annotazione con le caratteristiche dell'operazione, una parentesi graffa aperta `{` , il corpo della dichiarazione dell'operazione e una `}`

Ogni operazione accetta un input, produce un output e specifica l'implementazione per una o più specializzazioni delle operazioni.
Le specializzazioni possibili e le relative modalità di definizione/chiamata sono descritte in dettaglio più avanti.
Per il momento, si consideri l'operazione seguente, che definisce solo una specializzazione del corpo predefinita e accetta un solo qubit come input, quindi chiama l'operazione incorporata <xref:microsoft.quantum.intrinsic.x> su tale input:

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

La parola chiave `operation` inizia la definizione dell'operazione ed è seguita dal nome; in questo caso, `BitFlip` .
Successivamente, il tipo di input viene definito come `Qubit` , insieme a un nome `target` per fare riferimento all'input all'interno della nuova operazione.
Analogamente, `Unit` definisce che l'output dell'operazione è vuoto.
Viene usato in modo analogo a `void` in C# e altri linguaggi imperativi ed è equivalente a `unit` in F # e altri linguaggi funzionali.

Le operazioni possono inoltre restituire tipi più interessanti rispetto a `Unit` .
Ad esempio, l' <xref:microsoft.quantum.intrinsic.m> operazione restituisce un output di tipo `Result` , che rappresenta l'esecuzione di una misurazione. È possibile passare l'output da un'operazione a un'altra operazione o usarlo con la `let` parola chiave per definire una nuova variabile.

Questo consente la rappresentazione di calcoli classici che interagiscono con le operazioni Quantum a un livello basso, ad esempio nella [codifica superdensa](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding):

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

> [!NOTE]
> Ogni operazione in Q # accetta esattamente un input e restituisce esattamente un output.
> Più input e output vengono quindi rappresentati utilizzando *Tuple*, che raccolgono più valori in un singolo valore.
> In modo informale, diciamo che Q # è un linguaggio "tuple-in-out".
> Seguendo questo concetto, `()` deve quindi essere letto come tupla "vuota", che ha il tipo `Unit` .


## <a name="controlled-and-adjoint-operations"></a>Operazioni controllate e adiacenti

Se un'operazione implementa una trasformazione unitaria, come nel caso di molte operazioni in Q #, è possibile definire il modo in cui l'operazione agisce quando *adjointed* o *controllato*. Una specializzazione *contigua* di un'operazione specifica il modo in cui il "inverso" dell'operazione agisce, mentre una specializzazione *controllata* specifica il modo in cui un'operazione agisce quando l'applicazione è condizionata allo stato di un particolare registro Quantum.

Gli elementi adiacenti delle operazioni Quantum sono cruciali per molti aspetti del quantum computing. Più avanti, nella sezione [coniugazioni](#conjugations) , si troverà una situazione di questo tipo, descritta insieme a una tecnica di programmazione Q # utile.

La versione controllata di un'operazione è una nuova operazione che applica efficacemente l'operazione di base solo se tutti i qubits di controllo si trovano in uno stato specificato.
Se il controllo qubits si trova in una posizione sovraposizionata, l'operazione di base viene applicata in modo coerente alla parte appropriata della superposizione.
In questo modo, le operazioni controllate vengono spesso usate per generare il groviglio.

Naturalmente è possibile che esista anche una specializzazione *contigua controllata* , specificando l'applicazione controllata di un'operazione contigua.

> [!NOTE]
> Se $U $ è la trasformazione unitaria implementata da un'operazione `U` , `Adjoint U` rappresenta la trasformazione unitaria $U ^ \dagger $, che è la trasforma coniugale complessa.
> Se successivamente si applica un'operazione e il relativo contiguo a uno stato lascia lo stato invariato, come illustrato dal fatto che $UU ^ \dagger = U ^ \dagger U = \ID $, la matrice di identità.
> La rappresentazione unitaria di un'operazione controllata è leggermente più sfumata, ma è possibile trovare altre informazioni sui [concetti di quantum computing: più qubits](xref:microsoft.quantum.concepts.multiple-qubits).

La sezione seguente descrive come chiamare queste varie specializzazioni nel codice Q #.
Di seguito viene illustrato in dettaglio come definire le operazioni per supportarle.

### <a name="calling-operation-specializations"></a>Specializzazioni delle operazioni di chiamata

Un *functor* in Q # è una factory che definisce una nuova operazione da un'altra operazione.
I due funtori standard in Q # sono `Adjoint` e `Controlled` .

Funtori hanno accesso all'implementazione dell'operazione di base quando si definisce l'implementazione della nuova operazione.
Funtori può quindi eseguire funzioni più complesse rispetto alle funzioni di livello superiore tradizionali. Funtori non dispone di una rappresentazione nel sistema di tipi Q #. Attualmente non è possibile associarli a una variabile o passarli come argomenti. 

Un functor viene usato applicando l'oggetto a un'operazione, restituendo una nuova operazione.
Ad esempio, l'operazione risultante dall'applicazione del `Adjoint` functore all' `Y` operazione viene scritta come `Adjoint Y` .
La nuova operazione può quindi essere richiamata come qualsiasi altra operazione.
Per eseguire un'operazione per supportare l'applicazione di `Adjoint` e/o `Controlled` funtori, il tipo restituito deve necessariamente essere `Unit` . 

#### <a name="adjoint-functor"></a>`Adjoint`funtore

Applica quindi `Adjoint Y(q1)` il functor adiacente all' `Y` operazione per generare una nuova operazione e applica tale nuova operazione a `q1` .
La nuova operazione ha la stessa firma e il tipo dell'operazione di base `Y` .
In particolare, la nuova operazione consente inoltre `Adjoint` e consentirà `Controlled` solo se è stata eseguita l'operazione di base.
Il functor contiguo è il proprio inverso; ovvero `Adjoint Adjoint Op` è sempre uguale a `Op` .

#### <a name="controlled-functor"></a>`Controlled`funtore

Analogamente, `Controlled X(controls, target)` applica il functor controllato all' `X` operazione per generare una nuova operazione e applica tale nuova operazione a `controls` e `target` .

> [!NOTE]
> In Q # le versioni controllate accettano sempre una matrice di qubits di controllo e lo stato specificato è sempre per tutti i qubits di controllo nello stato computazionale ( `PauliZ` ) `One` , $ \ket {1} $.
> Il controllo basato su altri Stati può essere ottenuto applicando l'operazione unitaria appropriata al controllo qubits prima dell'operazione controllata, quindi applicando gli inversi dell'operazione unitaria dopo l'operazione controllata.
> Se, ad esempio, si applica un'operazione `X` a un controllo qubit prima e dopo un'operazione controllata, l'operazione Controlla lo `Zero` stato ($ \ket {0} $) per tale qubit; l'applicazione di un' `H` operazione prima e dopo controlla lo stato `PauliX` `One` , ovvero-1 autovalore di Pauli X, $ \ket {-} \mathrel{: =} (\ket {0} -\ket {1} )/\sqrt {2} $ anziché lo `PauliZ` `One` stato.

Data un'espressione di operazione, è possibile formare una nuova espressione di operazione usando il `Controlled` functor.
La firma della nuova operazione si basa sulla firma dell'operazione originale.
Il tipo di risultato è lo stesso, ma il tipo di input è una tupla con due tuple con una matrice qubit che include i qubit del controllo come primo elemento e gli argomenti dell'operazione originale come secondo elemento.
La nuova operazione supporta `Controlled` e supporterà solo se è `Adjoint` stata eseguita l'operazione originale.

Se l'operazione originale ha accettato un solo argomento, l'equivalenza della tupla singleton entrerà in gioco qui.
Ad esempio, `Controlled X` è la versione controllata dell' `X` operazione. 
`X`il tipo è `(Qubit => Unit is Adj + Ctl)` , quindi `Controlled X` è di tipo, a `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` causa dell'equivalenza della tupla singleton, equivale a `((Qubit[], Qubit) => Unit is Adj + Ctl)` .

Se l'operazione di base ha assunto diversi argomenti, ricordarsi di racchiudere tra parentesi gli argomenti corrispondenti della versione controllata dell'operazione per convertirli in una tupla.
Ad esempio, `Controlled Rz` è la versione controllata dell' `Rz` operazione. 
`Rz`dispone del tipo `((Double, Qubit) => Unit is Adj + Ctl)` , pertanto `Controlled Rz` è di tipo `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` .
Quindi, `Controlled Rz(controls, (0.1, target))` sarebbe una chiamata valida di `Controlled Rz` (si notino le parentesi `0.1, target` ).

Un altro esempio `CNOT(control, target)` può essere implementato come `Controlled X([control], target)` . Se una destinazione deve essere controllata da 2 Control qubits (CCNOT), è possibile usare l' `Controlled X([control1, control2], target)` istruzione.

#### `Controlled Adjoint` 

Il `Controlled` e il `Adjoint` funtori commute, quindi non esiste alcuna differenza tra l'applicazione di `Controlled Adjoint Op` o `Adjoint Controlled Op` .


## <a name="defining-controlled-and-adjoint-implementations"></a>Definizione di implementazioni controllate e adiacenti

Nei primi esempi di dichiarazione di operazione precedenti, le operazioni `BitFlip` e `DecodeSuperdense` sono state definite rispettivamente con le firme `(Qubit => Unit)` e `((Qubit, Qubit) => (Result, Result))` .
Come `DecodeSuperdense` include le misurazioni, non è un'operazione unitaria e pertanto non è possibile che esistano specializzazioni controllate e non contigue (richiamare il requisito correlato restituito da tale operazione `Unit` ).
Tuttavia, poiché `BitFlip` esegue semplicemente l'operazione unitaria <xref:microsoft.quantum.intrinsic.x> , è possibile che sia stata definita con entrambe le specializzazioni.

In questo articolo viene illustrato in dettaglio come includere l'esistenza di specializzazioni nelle dichiarazioni di operazione Q #, offrendo quindi la possibilità di chiamare insieme a `Adjoint` e/o `Controlled` funtori.
Di [seguito](#circumstances-for-validly-defining-specializations)vengono descritte alcune situazioni in cui è valido o non è valido per dichiarare determinate specializzazioni.

Le caratteristiche dell'operazione definiscono i tipi di funtori che possono essere applicati all'operazione dichiarata e l'effetto che hanno. L'esistenza di queste specializzazioni può essere dichiarata come parte della firma dell'operazione, in particolare tramite un'annotazione con le caratteristiche dell'operazione, ovvero `is Adj` , `is Ctl` o `is Adj + Ctl` .
L'implementazione effettiva di ogni specializzazione può essere definita in modo *implicito* o *esplicito* .

### <a name="implicitly-specifying-implementations"></a>Specifica delle implementazioni in modo implicito

In questo caso, il corpo della dichiarazione dell'operazione è costituito esclusivamente dall'implementazione predefinita. Ad esempio:

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```
In questo caso, l'implementazione corrispondente per ogni specializzazione dichiarata in modo implicito viene generata automaticamente dal compilatore, da eseguire se `Adjoint` `Controlled` vengono usati o funtori.

Pertanto, una chiamata di `Adjoint PrepareEntangledPair` provocherebbe il compilatore che implementa il contiguo di `CNOT` e quindi il contiguo di `H` .
Queste singole operazioni sono entrambe autocontigue, pertanto l'operazione risultante `Adjoint PrepareEntangledPair` sarebbe semplicemente costituita dall'applicazione `CNOT(here, there)` e quindi da `H(here)` .
È quindi possibile usarlo per scrivere l' `DecodeSuperdense` esempio precedente in modo più compatto, usando il contiguo di `PrepareEntangledPair` per trasformare lo stato incastrato di nuovo in una coppia non impigliata di qubits:

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

L'annotazione con le caratteristiche dell'operazione nella dichiarazione è utile per garantire che il compilatore generi automaticamente altre specializzazioni in base all'implementazione predefinita. 

Quando si progettano operazioni da usare con funtori, è necessario considerare alcune importanti limitazioni.
In modo più critico, le specializzazioni per un'operazione che usa il valore di output di qualsiasi altra operazione *non possono* essere generate automaticamente dal compilatore, perché è ambiguo come riordinare le istruzioni in tale operazione per ottenere lo stesso effetto.

Pertanto, è spesso utile specificare in modo esplicito le varie implementazioni.

### <a name="explicitly-specifying-implementations"></a>Specifica delle implementazioni in modo esplicito

Nel caso in cui l'implementazione non possa essere generata dal compilatore, può essere specificata in modo esplicito. Tali dichiarazioni di specializzazione esplicita possono essere costituite da una *direttiva di generazione* adatta o da un'implementazione definita dall'utente.
Qui viene fornita la gamma completa di possibilità, con esempi seguenti.


#### <a name="explicit-specialization-declarations"></a>Dichiarazioni di specializzazione esplicite

Le operazioni Q # possono contenere le seguenti dichiarazioni di specializzazione esplicite:

- La `body` specializzazione specifica l'implementazione dell'operazione senza funtori applicata.
- La `adjoint` specializzazione specifica l'implementazione dell'operazione con il `Adjoint` functor applicato.
- La `controlled` specializzazione specifica l'implementazione dell'operazione con il `Controlled` functor applicato.
- La `controlled adjoint` specializzazione specifica l'implementazione dell'operazione con `Adjoint` e `Controlled` funtori applicati.
  Questa specializzazione può anche essere denominata `adjoint controlled` , dal momento che i due funtori del commutatore.


Una specializzazione di operazione è costituita dal tag di specializzazione, ad esempio `body` , o e `adjoint` così via, seguito da uno dei seguenti elementi:

- Dichiarazione esplicita, come descritto di seguito.
- *Direttiva* che indica al compilatore *come* generare la specializzazione, una tra le seguenti:
  - `intrinsic`, che indica che la specializzazione viene fornita dal computer di destinazione.
  - `distribute`, che può essere usato con le `controlled` `controlled adjoint` specializzazioni e.
    Se usato con `controlled` , indica che il compilatore deve calcolare la specializzazione applicando `Controlled` a tutte le operazioni nell'oggetto `body` .
    Se usato con `controlled adjoint` , indica che il compilatore deve calcolare la specializzazione applicando `Controlled` a tutte le operazioni nella `adjoint` specializzazione.
  - `invert`, che indica che il compilatore deve calcolare la `adjoint` specializzazione invertendo l'oggetto `body` , ad esempio invertendo l'ordine delle operazioni e applicando il contiguo a ognuno di essi.
    Se usato con `adjoint controlled` , indica che il compilatore deve calcolare la specializzazione invertendo la `controlled` specializzazione.
  - `self`, per indicare che la specializzazione contigua è uguale alla `body` specializzazione.
    Questo è valido per le `adjoint` `adjoint controlled` specializzazioni e.
    Per `adjoint controlled` , `self` implica che la `adjoint controlled` specializzazione corrisponde alla `controlled` specializzazione.
  - `auto`, per indicare che il compilatore deve selezionare una direttiva appropriata da applicare.
    `auto`non può essere usato per la `body` specializzazione.

Tutte le direttive e richiedono un punto e virgola `auto` di chiusura `;` .
La `auto` direttiva viene risolta nella direttiva di generazione seguente se viene fornita una dichiarazione esplicita di `body` :

- La `adjoint` specializzazione viene generata in base alla direttiva `invert` .
- La `controlled` specializzazione viene generata in base alla direttiva `distribute` .
- La `adjoint controlled` specializzazione viene generata in base alla direttiva `invert` se viene fornita una dichiarazione esplicita per `controlled` , ma non una per `adjoint` e `distribute` in caso contrario.

> [!TIP]   
> Se un'operazione è autonoma, specificare in modo esplicito la specializzazione contigua o controllata tramite la direttiva `self` di generazione per consentire al compilatore di utilizzare tali informazioni a scopo di ottimizzazione.

Una dichiarazione di specializzazione contenente un'implementazione definita dall'utente è costituita da una tupla di argomenti seguita da un blocco di istruzioni con il codice Q # che implementa la specializzazione.
Nell'elenco di argomenti, `...` viene usato per rappresentare gli argomenti dichiarati per l'intera operazione.
Per `body` e `adjoint` , l'elenco di argomenti deve essere sempre `(...)` ; per `controlled` e `adjoint controlled` , l'elenco di argomenti deve essere un simbolo che rappresenta la matrice di qubits del controllo, seguito da `...` , racchiuso tra parentesi, ad esempio `(controls,...)` .

### <a name="examples"></a>Esempi

Una dichiarazione di operazione potrebbe essere semplice come la seguente, che definisce l'operazione di Pauli X primitiva:

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```
Si noti che il contiguo dell'operazione di Pauli X viene definito con la direttiva, `self` perché per definizione `X` è il proprio inverso.

Il codice `PrepareEntangledPair` riportato sopra, ad esempio, è equivalente al codice riportato di seguito contenente dichiarazioni di specializzazione esplicite: 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
La parola chiave `auto` indica che il compilatore deve determinare come generare l'implementazione della specializzazione.

#### <a name="user-defined-specialization-implementation"></a>Implementazione della specializzazione definita dall'utente

Se il compilatore non è in grado di generare automaticamente l'implementazione per una determinata specializzazione o se è possibile fornire un'implementazione più efficiente, l'implementazione può anche essere definita manualmente.

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user-defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
Nell'esempio precedente, `adjoint invert;` indica che la specializzazione contigua deve essere generata invertendo l'implementazione del corpo e `controlled adjoint invert;` indica che la specializzazione contigua controllata deve essere generata invertendo l'implementazione specificata della specializzazione controllata.

Se una o più specializzazioni oltre al corpo predefinito devono essere dichiarate in modo esplicito, l'implementazione del corpo predefinito deve essere racchiusa anche in una dichiarazione di specializzazione adatta:

```qsharp
operation CountOnes(qubits: Qubit[]) : Int {

    body (...) // default body specialization
    {
        mutable n = 0;
        for (qubit in qubits) {
            set n += M(q) == One ? 1 | 0;
        }
        return n;
    }

    ...
```

### <a name="circumstances-for-validly-defining-specializations"></a>Circostanze per la definizione valida delle specializzazioni

#### <a name="operation-declarations-with-adjointcontrolled"></a>Dichiarazioni di operazione con contiguo/controllato

È lecito specificare un'operazione senza versioni contigue o controllate. Ad esempio, le operazioni di misurazione non hanno nessuno, perché non sono invertibili o controllabili.

Un'operazione supporta `Adjoint` e/o `Controlled` funtori se la relativa dichiarazione contiene una dichiarazione implicita o esplicita delle rispettive specializzazioni.

Una specializzazione annullata o controllata dichiarata in modo esplicito implica l'esistenza di una specializzazione contigua/controllata. 

Per un'operazione il cui corpo contiene cicli di ripetizione fino al completamento, istruzioni set, misure, istruzioni return o chiamate ad altre operazioni che non supportano il `Adjoint` functor, la generazione automatica di una specializzazione contigua che segue la `invert` `auto` direttiva o non è possibile.

Per un'operazione il cui corpo contiene chiamate ad altre operazioni che non supportano il `Controlled` functor, non è possibile generare automaticamente una specializzazione controllata che segue la `distribute` `auto` direttiva o.

#### <a name="controlled-adjoint"></a>Contiguo controllato

La versione controllata contigua di un'operazione specifica il modo in cui viene implementata una versione controllata da Quantum del contiguo dell'operazione.
È lecito specificare un'operazione senza una versione controllata contigua. ad esempio, le operazioni di misurazione non hanno una versione controllata contigua, perché non sono controllabili né invertibili.

Una specializzazione contigua controllata per un'operazione deve esistere solo se sono presenti sia una specializzazione contigua che una specializzazione controllata. In tal caso, viene dedotta l'esistenza della specializzazione contigua controllata e una specializzazione appropriata viene generata dal compilatore se nessuna implementazione è stata definita in modo esplicito. 

Per un'operazione il cui corpo contiene chiamate ad altre operazioni che non dispongono di una versione controllata contigua, la generazione automatica di una specializzazione contigua che segue la `invert` `distribute` direttiva, o `auto` non è possibile.


### <a name="type-compatibility"></a>Compatibilità tra tipi

Un'operazione con funtori aggiuntivi supportata può essere usata ovunque un'operazione con un numero di funtori inferiore ma è prevista la stessa firma.
Ad esempio, un'operazione di tipo `(Qubit => Unit is Adj)` può essere utilizzata ovunque sia prevista un'operazione di tipo `(Qubit => Unit)` .

Q # è *covariante* rispetto ai tipi restituiti richiamabili: un oggetto chiamabile che restituisce un tipo `'A` è compatibile con un oggetto chiamabile con lo stesso tipo di input e un tipo di risultato `'A` compatibile con.

Q # è *controvariante* rispetto ai tipi di input: un oggetto chiamabile che accetta un tipo `'A` come input è compatibile con un oggetto chiamabile con lo stesso tipo di risultato e un tipo di input compatibile con `'A` .

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

- La funzione `ConjugateInvertWith` può essere richiamata con un `inner` argomento di `Invert` o `ApplyUnitary` .
- La funzione `ConjugateUnitaryWith` può essere richiamata con un `inner` argomento di `ApplyUnitary` , ma non `Invert` .
- Un valore di tipo `(Qubit[] => Unit is Adj + Ctl)` può essere restituito da `ConjugateInvertWith` .

> [!IMPORTANT]
> Q # 0,3 ha introdotto una differenza significativa nel comportamento dei tipi definiti dall'utente.

I tipi definiti dall'utente vengono considerati come una versione di cui è stato eseguito il wrapped del tipo sottostante, anziché come sottotipo.
Ciò significa che un valore di un tipo definito dall'utente non può essere utilizzato quando è previsto un valore del tipo sottostante.


### <a name="conjugations"></a>Coniugazioni

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

A partire dalla versione 0,9, è supportata un'istruzione di coniugazione che implementa la trasformazione precedente. Utilizzando tale istruzione, `ApplyWith` è possibile implementare l'operazione nel modo seguente:

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

La trasformazione inversa per le istruzioni definite nel blocco interno viene generata automaticamente dal compilatore ed eseguita al termine del blocco Apply.
Poiché le variabili modificabili usate come parte del blocco all'interno non possono essere riassociati nel blocco Apply, la trasformazione generata è sicuramente l'elemento contiguo del calcolo nel blocco all'interno. 


## <a name="defining-new-functions"></a>Definizione di nuove funzioni

Le funzioni sono puramente deterministiche, ovvero routine classiche in Q #, diverse dalle operazioni in quanto non possono avere effetti oltre il calcolo di un valore di output.
In particolare, le funzioni non possono chiamare operazioni; agire, allocare o prendere in prestito qubits; numeri casuali di esempio; o altrimenti dipendono dallo stato oltre il valore di input per una funzione.
Di conseguenza, le funzioni Q # sono *pure*, in quanto eseguono sempre il mapping degli stessi valori di input agli stessi valori di output.
Ciò consente al compilatore Q # di riordinare in modo sicuro come e quando le funzioni vengono chiamate quando si generano specializzazioni delle operazioni.

Ogni file di origine Q # può definire un numero qualsiasi di funzioni.
I nomi di funzione devono essere univoci all'interno di uno spazio dei nomi e non possono entrare in conflitto con i nomi di operazione o

La definizione di una funzione funziona in modo analogo alla definizione di un'operazione, ad eccezione del fatto che non è possibile definire alcuna specializzazioni contigua o controllata per una funzione.
Ad esempio:

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```

oppure 

```qsharp
function DotProduct(a : Double[], b : Double[]) : Double {
    if (Length(a) != Length(b)) {
        fail "Arrays are not compatible";
    }

    mutable accum = 0.0;
    for (i in 0..Length(a)-1) {
        set accum += a[i] * b[i];
    }
    return accum;
}
```

### <a name="classical-logic-in-functions--good"></a>Logica classica nelle funzioni = = corretta

Quando è possibile eseguire questa operazione, è utile scrivere la logica classica in termini di funzioni anziché di operazioni, in modo che possa essere usata più facilmente all'interno di operazioni.
Se ad esempio è stata scritta la `Square` dichiarazione precedente come *operazione*, il compilatore non sarebbe stato in grado di garantire che la chiamata con lo stesso input produrrebbe sempre gli stessi output.

Per sottolineare la differenza tra funzioni e operazioni, prendere in considerazione il problema di campionamento classico di un numero casuale da un'operazione Q #:

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

Ogni volta che `U` viene chiamato, avrà un'azione diversa su `target` .
In particolare, il compilatore non è in grado di garantire che se è stata aggiunta una `adjoint auto` dichiarazione di specializzazione a `U` , `U(target); Adjoint U(target);` funge da identità, ovvero come no-op.
In questo modo si viola la definizione del contiguo che è stato osservato in [vettori e matrici](xref:microsoft.quantum.concepts.vectors), in modo che la possibilità di generare automaticamente una specializzazione contigua in un'operazione in cui è stata chiamata l'operazione <xref:microsoft.quantum.math.randomreal> interrompa le garanzie fornite dal compilatore. <xref:microsoft.quantum.math.randomreal> è un'operazione per la quale non esiste alcuna versione contigua o controllata.

D'altra parte, consentire le chiamate di funzione come `Square` è sicuro, in quanto è possibile garantire che il compilatore debba solo conservare l'input per garantire la `Square` stabilità dell'output.
In questo modo, l'isolamento della logica classica più possibile in funzioni semplifica il riutilizzo di tale logica in altre funzioni e operazioni.


## <a name="generic-type-parameterized-callables"></a>Chiamabili generici (con parametri di tipo)

Molte funzioni e operazioni che è possibile definire non si basano molto sui tipi di input, ma usano solo i tipi in modo implicito tramite un'altra funzione o un'altra operazione.
Si consideri, ad esempio, il concetto di *mappa* comune a molti linguaggi funzionali; Data una funzione $f (x) $ e una raccolta di valori $ \{ X_1, x_2, \dots, x_n \} $, map restituisce una nuova raccolta $ \{ f (X_1), f (x_2), \dots, f (x_n) \} $.
Per implementarlo in Q #, è possibile sfruttare le funzioni che sono la prima classe.
Viene ora illustrato un esempio rapido di `Map` utilizzo di ★ come segnaposto, mentre è possibile individuare i tipi necessari.

```qsharp
function Map(fn : (★ -> ★), values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Nota Questa funzione è molto simile indipendentemente dai tipi effettivi sostituiti.
Un mapping da Integer a Paulis, ad esempio, ha un aspetto molto simile a quello di una mappa dai numeri a virgola mobile a stringhe:

```qsharp
function MapIntsToPaulis(fn : (Int -> Pauli), values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : (Double -> String), values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

In linea di principio, è possibile scrivere una versione di `Map` per ogni coppia di tipi incontrata, ma in questo caso è stata introdotta una serie di problemi.
Se ad esempio si rileva un bug in `Map` , è necessario assicurarsi che la correzione venga applicata in modo uniforme in tutte le versioni di `Map` .
Inoltre, se si costruisce una nuova tupla o un tipo definito dall'utente, ora è necessario creare anche un nuovo oggetto `Map` da usare con il nuovo tipo.
Sebbene si tratti di un numero ridotto di funzioni di questo tipo, quando si raccolgono più funzioni con lo stesso formato di `Map` , il costo dell'introduzione di nuovi tipi diventa ingiustificatamente grande nell'ordine piuttosto breve.

Gran parte di questa difficoltà, tuttavia, dal momento che non è stato fornito il compilatore, le informazioni necessarie per riconoscere il modo in cui sono correlate le diverse versioni di `Map` .
In realtà, il compilatore si vuole trattare `Map` come un tipo di funzione matematica dai *tipi* q # alle funzioni q #.

Questa nozione viene formalizzata consentendo a funzioni e operazioni di avere *parametri di tipo*, nonché i parametri di tupla ordinari.
Negli esempi precedenti si desidera considerare `Map` come avere parametri di tipo `Int, Pauli` nel primo caso e `Double, String` nel secondo caso.
Nella maggior parte dei casi, questi parametri di tipo possono essere usati come se fossero tipi normali: si usano valori di parametri di tipo per creare matrici e tuple, chiamare funzioni e operazioni e assegnare a variabili ordinarie o modificabili.

> [!NOTE]
> Il caso più estremo della dipendenza indiretta è quello di qubits, in cui un programma Q # non può basarsi direttamente sulla struttura del `Qubit` tipo, ma **deve** passare tali tipi ad altre operazioni e funzioni.

Tornando all'esempio precedente, è possibile vedere che è necessario `Map` disporre di parametri di tipo, uno per rappresentare l'input `fn` e uno per rappresentare l'output da `fn` .
In Q # questo viene scritto aggiungendo parentesi angolari (ovvero `<>` , non i Brake $ \braket {} $!) dopo il nome di una funzione o di un'operazione nella relativa dichiarazione e elencando ogni parametro di tipo.
Il nome di ogni parametro di tipo deve iniziare con un segno di indicizzazione `'` , a indicare che si tratta di un parametro di tipo e non di un tipo ordinario (noto anche come tipo *concreto* ).
Per `Map` , scriviamo quindi:

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Si noti che la definizione di `Map<'Input, 'Output>` ha un aspetto molto simile a quello delle versioni precedenti.
L'unica differenza consiste nel fatto che il compilatore è stato informato in modo esplicito che `Map` non dipende direttamente da quali `'Input` e `'Output` sono, ma funziona per due tipi utilizzandoli indirettamente tramite `fn` .
Una volta definito `Map<'Input, 'Output>` in questo modo, è possibile chiamarlo come se fosse una funzione ordinaria:

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> La scrittura di funzioni e funzioni generiche è un'unica posizione in cui "tuple-in tuple-out" è un modo utile per considerare le funzioni e le operazioni Q #.
> Poiché ogni funzione accetta esattamente un input e restituisce esattamente un output, un input di tipo `'T -> 'U` corrisponde a *qualsiasi* funzione Q #.
> Analogamente, qualsiasi operazione può essere passata a un input di tipo `'T => 'U` .

Come secondo esempio, si consideri la necessità di scrivere una funzione che restituisce la composizione di altre due funzioni:

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

In questo caso, è necessario specificare esattamente cosa `A` , `B` e `C` sono, di conseguenza la limitazione dell'utilità della nuova `Compose` funzione.
Dopo tutto, `Compose` dipende solo da `A` , `B` e `C` *tramite* `innerFn` e `outerFn` .
In alternativa, è possibile aggiungere parametri di tipo a `Compose` che indicano che funziona per *qualsiasi* `A` , `B` e `C` , purché questi parametri corrispondano a quelli previsti da `innerFn` e `outerFn` :

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

Le librerie standard Q # forniscono una serie di operazioni e funzioni con parametri di tipo per semplificare l'espressione del flusso di controllo di ordine superiore.
Questi argomenti sono illustrati più avanti nella [Guida alla libreria standard Q #](xref:microsoft.quantum.libraries.standard.intro).


## <a name="callables-as-first-class-values"></a>Chiamabili come valori di prima classe

Una tecnica critica per ragionare sul flusso di controllo e la logica classica con funzioni anziché operazioni consiste nell'usare le operazioni e le funzioni in Q # sono di *prima classe*.
Ovvero ciascuno dei quali è il linguaggio di propria scelta.
Ad esempio, di seguito è riportato un codice Q # perfettamente valido, se poco indiretto:

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

Il valore della variabile `ourH` nel frammento di codice precedente è quindi l'operazione <xref:microsoft.quantum.intrinsic.h> , in modo che sia possibile chiamare tale valore come qualsiasi altra operazione.
In questo modo è possibile scrivere operazioni che accettano operazioni come parte dell'input, formando concetti di flusso di controllo di ordine superiore.
Si supponga, ad esempio, di voler "quadrare" un'operazione applicando due volte lo stesso qubit di destinazione.

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a>Restituzione di operazioni da una funzione

Si evidenzia che è anche possibile restituire le operazioni come parte degli output, in modo da poter isolare alcuni tipi di logica condizionale classica come una funzione classica che restituisce una descrizione di un programma Quantum sotto forma di operazione.
Come esempio semplice, si consideri l'esempio di Teleporting, in cui la parte che riceve un messaggio classico a due bit deve usare il messaggio per decodificare i qubit nello stato di teleporte appropriato.
È possibile scrivere questo risultato in termini di funzione che accetta i due bit classici e restituisce l'operazione di decodifica corretta.

```qsharp
function TeleporationDecoderForMessage(hereBit : Result, thereBit : Result)
: (Qubit => Unit is Adj + Ctl) {

    if (hereBit == Zero && thereBit == Zero) {
        return I;
    } elif (hereBit == One && thereBit == Zero) {
        return X;
    } elif (hereBit == Zero && thereBit == One) {
        return Z;
    } else {
        return Y;
    }
}
```

Questa nuova funzione è effettivamente una funzione, in quanto se viene chiamata con gli stessi valori di `hereBit` e `thereBit` , viene sempre restituita la stessa operazione.
Pertanto, il decodificatore può essere eseguito in modo sicuro all'interno di operazioni senza dover ragionare sul modo in cui la logica di decodifica interagisce con le definizioni delle diverse specializzazioni delle operazioni.
Ovvero è stata isolata la logica classica all'interno di una funzione, garantendo al compilatore che la chiamata di funzione possa essere riordinata con impuneità purché l'input venga mantenuto.


## <a name="partial-application"></a>Applicazione parziale

È possibile eseguire molte altre operazioni con funzioni che restituiscono operazioni usando un' *applicazione parziale*, in cui è possibile fornire una o più parti dell'input a una funzione o a un'operazione senza chiamarla effettivamente. Ad esempio, richiamando l' `ApplyTwice` esempio precedente, è possibile indicare che non si vuole specificare, immediatamente, a quale qubit deve essere applicata l'operazione di input:

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

In questo caso, la variabile locale `twiceOp` contiene l'operazione parzialmente applicata `ApplyTwice(op, _)` , in cui le parti dell'input che non sono state ancora specificate sono indicate `_` da.
Quando si chiama effettivamente `twiceOp` nella riga successiva, viene passato come input all'operazione parzialmente applicata tutte le parti rimanenti dell'input per l'operazione originale.
Pertanto, il frammento di codice precedente è effettivamente identico alla chiamata `ApplyTwice(op, target)` diretta, salvo per il fatto che è stata introdotta una nuova variabile locale che consente di ritardare la chiamata fornendo alcune parti dell'input.

Poiché un'operazione che è stata applicata parzialmente non viene effettivamente chiamata fino a quando non è stato fornito l'intero input, è possibile applicare parzialmente in modo sicuro le operazioni anche dalle funzioni.

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

In linea di base, la logica classica in `SquareOperation` potrebbe essere stata molto più complessa, ma è ancora isolata dal resto di un'operazione garantita dal fatto che il compilatore possa offrire informazioni sulle funzioni.
Questo approccio verrà usato in tutta la libreria standard Q # per esprimere il flusso di controllo classico in modo da poter essere usato facilmente nei programmi Quantum.


## <a name="recursion"></a>Ricorsione

D # i chiamabili possono essere ricorsivi direttamente o indirettamente.
Ovvero, un'operazione o una funzione può chiamare se stessa oppure può chiamare un altro oggetto chiamabile che chiama direttamente o indirettamente l'operazione chiamabile.

Sono tuttavia disponibili due commenti importanti sull'utilizzo della ricorsione:

- L'uso della ricorsione nelle operazioni potrebbe interferire con determinate ottimizzazioni.
  Questo può avere un notevole effetto sul tempo di esecuzione dell'algoritmo.
- Quando si esegue su un dispositivo Quantum effettivo, lo spazio dello stack può essere limitato e pertanto la ricorsione profonda può causare un errore di Runtime.
  In particolare, il compilatore e il runtime Q # non identificano e ottimizzano la ricorsione Tail.

## <a name="next-steps"></a>Passaggi successivi

Informazioni sulle [variabili](xref:microsoft.quantum.guide.variables) in Q #.