---
title: 'Guida di stile di Microsoft Q #'
description: 'Informazioni sulle convenzioni di denominazione, input, documentazione e formattazione per le librerie e i programmi Q #.'
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.style
ms.openlocfilehash: f8e398b5c9932a5079222fed7ad20e54de814eb8
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274796"
---
# <a name="q-style-guide"></a>Guida di stile Q # #
## <a name="general-conventions"></a>Convenzioni generali ##

Le convenzioni suggerite in questa guida hanno lo scopo di semplificare la lettura e la comprensione dei programmi e delle librerie scritte in Q #.

## <a name="guidance"></a>Indicazioni

È consigliabile:

- Non ignorare mai una convenzione, a meno che non lo si stia intenzionalmente per fornire codice più leggibile e comprensibile per gli utenti.

## <a name="naming-conventions"></a>Convenzioni di denominazione ##

Nell'offerta del quantum Development Kit, ci impegniamo per i nomi di funzione e di operazione che aiutano gli sviluppatori di Quantum a scrivere programmi facili da leggere e che riducono al minimo le sorprese.
Una parte importante di questo è che quando si scelgono i nomi di funzioni, operazioni e tipi, viene stabilito il *vocabolario* usato dai programmatori per esprimere i concetti quantistici; con le nostre scelte, Microsoft li aiuta o li ostacola nel tentativo di comunicare chiaramente.
In questo modo si ha la responsabilità di assicurarsi che i nomi introdotti offrano una maggiore chiarezza piuttosto che l'oscurità.
In questa sezione viene illustrato in dettaglio il modo in cui viene rispettato questo impegno in termini di linee guida esplicite che consentono di sfruttare al meglio la community di sviluppo Q #.

### <a name="operations-and-functions"></a>Operazioni e funzioni ###

Una delle prime cose che un nome deve stabilire è se un simbolo specificato rappresenta una funzione o un'operazione.
La differenza tra funzioni e operazioni è fondamentale per comprendere il comportamento di un blocco di codice.
Per comunicare la distinzione tra funzioni e operazioni per gli utenti, si fa affidamento su tale operazione per i modelli Q #, usando gli effetti collaterali.
Ovvero, un'operazione *esegue* un'operazione.

Al contrario, le funzioni descrivono le relazioni matematiche tra i dati.
L'espressione `Sin(PI() / 2.0)` *è* `1.0` e non implica nulla sullo stato di un programma o del relativo qubits.

Riepilogando, le operazioni eseguono attività mentre le funzioni.
Questa distinzione suggerisce che le operazioni vengono denominate come verbi e funzioni come sostantivi.

> [!NOTE]
> Quando viene dichiarato un tipo definito dall'utente, una nuova funzione che costruisce istanze di quel tipo viene definita in modo implicito nello stesso momento.
> Da tale prospettiva, i tipi definiti dall'utente devono essere denominati come sostantivi, in modo che sia il tipo stesso che la funzione del costruttore abbiano nomi coerenti.

Se ragionevole, assicurarsi che i nomi delle operazioni inizino con verbi che indicano chiaramente l'effetto ottenuto dall'operazione.
Ad esempio:

- `MeasureInteger`
- `EstimateEnergy`
- `SampleInt`

Un caso che merita una menzione speciale è quando un'operazione accetta un'altra operazione come input e la chiama.
In questi casi, l'azione eseguita dall'operazione di input non è chiara quando viene definita l'operazione esterna, in modo che il verbo destro non sia immediatamente chiaro.
È consigliabile usare il verbo `Apply` , come in `ApplyIf` , `ApplyToEach` e `ApplyToFirst` .
Altri verbi possono essere utili anche in questo caso, come in `IterateThroughCartesianPower` .

| Verbo | Effetto previsto |
| ---- | ------ |
| Applica | Viene chiamata un'operazione fornita come input |
| Assert | Un'ipotesi sul risultato di una possibile misurazione quantistica viene controllata da un simulatore |
| Estimate | Viene restituito un valore classico che rappresenta una stima disegnata da una o più misurazioni |
| Measure | Viene eseguita una misurazione quantistica e il risultato viene restituito all'utente |
| Preparazione | Un registro specificato di qubits viene inizializzato in uno stato specifico |
| Esempio | Un valore classico viene restituito in modo casuale da una distribuzione |

Per le funzioni, è consigliabile evitare l'uso di verbi a favore dei sostantivi comuni (vedere le linee guida sui sostantivi appropriati sotto) o sugli aggettivi:

- `ConstantArray`
- `Head`
- `LookupFunction`

In particolare, in quasi tutti i casi, è consigliabile usare participi precedenti, laddove appropriato, per indicare che un nome di funzione è fortemente connesso a un'azione o a un effetto collaterale in un'altra posizione in un programma Quantum.
Ad esempio, `ControlledOnInt` Usa il formato participio della parte del verbo "Control" per indicare che la funzione funge da aggettivo per modificare il relativo argomento.
Questo nome presenta il vantaggio aggiuntivo di abbinare la semantica del `Controlled` functore incorporato, come illustrato più avanti.
Analogamente, è possibile usare i _sostantivi di Agent_ per costruire nomi di funzioni e UDT da nomi di operazione, come nel caso del nome `Encoder` di un tipo definito dall'utente che è fortemente associato a `Encode` .

# <a name="guidance"></a>[Indicazioni](#tab/guidance)

È consigliabile:

- Usare i verbi per i nomi delle operazioni.
- Utilizzare sostantivi o aggettivi per i nomi di funzione.
- Usare i sostantivi per i tipi e gli attributi definiti dall'utente.
- Per tutti i nomi chiamabili, usare `CamelCase` in una preferenza avanzata per `pascalCase` , `snake_case` o `ANGRY_CASE` . In particolare, assicurarsi che i nomi richiamabili inizino con lettere maiuscole.
- Per tutte le variabili locali, utilizzare `pascalCase` in una preferenza sicura per `CamelCase` , `snake_case` o `ANGRY_CASE` . In particolare, assicurarsi che le variabili locali inizino con lettere minuscole.
- Evitare l'utilizzo di caratteri di sottolineatura `_` nei nomi di funzione e di operazione, dove sono necessari livelli aggiuntivi di gerarchia, utilizzare gli spazi dei nomi e gli alias degli spazi dei nomi.

# <a name="examples"></a>[esempi](#tab/examples)

|   | Nome | Descrizione |
|---|------|-------------|
| ☑ | `operation ReflectAboutStart` | Cancellazione dell'utilizzo di un verbo ("Reflect") per indicare l'effetto dell'operazione. |
| ☒ | <s>`operation XRotation`</s> | L'uso della frase nominale suggerisce la funzione, anziché l'operazione. |
| ☒ | <s>`operation search_oracle`</s> | Uso della `snake_case` notazione Q # in contrasto. |
| ☒ | <s>`operation Search_Oracle`</s> | L'uso di caratteri di sottolineatura interni al nome dell'operazione è in funzione della notazione Q #. |
| ☑ | `function StatePreparationOracle` | L'uso della frase nominale suggerisce che la funzione restituisce un'operazione. |
| ☑ | `function EqualityFact` | Uso chiaro del sostantivo ("fact") per indicare che si tratta di una funzione, mentre l'aggettivo. |
| ☒ | <s>`function GetRotationAngles`</s> | L'uso del verbo ("Get") suggerisce che si tratta di un'operazione. |
| ☑ | `newtype GeneratorTerm` | L'uso della frase nominale indica chiaramente il risultato della chiamata al costruttore del tipo definito dall'utente. |
| ☒ | <s>`@Attribute() newtype RunOnce()`</s> | L'uso della frase verbo suggerisce che il costruttore del tipo definito dall'utente è un'operazione. |
| ☑ | `@Attribute() newtype Deprecated(Reason : String)` | L'uso di sintagma sostantivo comunica l'uso dell'attributo. |

***

### <a name="shorthand-and-abbreviations"></a>Abbreviazione e abbreviazioni ###

Il Consiglio precedente, tuttavia, è costituito da molte forme di abbreviazione che vedono un uso comune e dilagante in quantum computing.
Si consiglia di usare l'abbreviazione esistente e comune in cui è presente, in particolare per le operazioni intrinseche al funzionamento di un computer di destinazione.
Si sceglie, ad esempio, il nome `X` anziché `ApplyX` , `Rz` anziché `RotateAboutZ` .
Quando si utilizza tale sintassi, i nomi delle operazioni devono essere tutti in maiuscolo, ad esempio: `MAJ` .

È necessario prestare attenzione quando si applica questa convenzione nel caso degli acronimi usati comunemente e acronimi, ad esempio "QFT" per "Quantum Fourier Transform".
Si consiglia di seguire le convenzioni .NET generali per l'uso di acronimi e acronimi nei nomi completi, che prevedono che:

- gli acronimi di due lettere e acronimi sono denominati in lettere maiuscole `BE` , ad esempio per "big-endian".
- tutti gli acronimi più lunghi e acronimi sono denominati in `CamelCase` (ad esempio, `Qft` per "Quantum Fourier Transform")

Pertanto, un'operazione che implementa QFT può essere chiamata `QFT` come abbreviata o scritta come `ApplyQft` .

Per le operazioni e le funzioni di uso più comune, può essere utile fornire un nome abbreviato come _alias_ per una forma più lunga:

```qsharp
operation CCNOT(control0 : Qubit, control1 : Qubit, target : Qubit)
is Adj + Ctl {
    Controlled X([control0, control1], target);
}
```

# <a name="guidance"></a>[Indicazioni](#tab/guidance)

È consigliabile:

- Prendere in considerazione nomi abbreviati comunemente accettati e ampiamente usati quando appropriato.
- Usare maiuscole per la sintassi abbreviata.
- Usare i caratteri maiuscoli per gli acronimi Short (Two-Letter) e acronimi.
- Usare `CamelCase` per gli acronimi più lunghi (tre o più lettere) e acronimi.

# <a name="examples"></a>[esempi](#tab/examples)

|   | Nome | Descrizione |
|---|------|-------------|
| ☑ | `X` | Abbreviazione ben riconosciuta per "applicare una $X $ Transformation" |
| ☑ | `CNOT` | Abbreviazione ben riconosciuta per "controllato-NOT" |
| ☒ | <s>`Cnot`</s> | La sintassi abbreviata non dovrebbe essere in `CamelCase` . |
| ☑ | `ApplyQft` | L'iniziale comune "QFT" viene visualizzato come parte di un nome di tipo esteso. |
| ☑ | `QFT` | Il valore iniziale comune "QFT" viene visualizzato come parte di un nome abbreviato. |



***


### <a name="proper-nouns-in-names"></a>Sostantivi appropriati nei nomi ###

Nella fisica è comune denominare gli elementi dopo la prima persona a pubblicarli, la maggior parte dei non fisici non ha familiarità con i nomi di tutti gli utenti e tutta la cronologia.
Basandosi troppo sulle convenzioni di denominazione della fisica, può quindi costituire un ostacolo sostanziale alla voce, in quanto gli utenti di altri background devono apprendere un numero elevato di nomi apparentemente opachi per poter utilizzare le operazioni e i concetti comuni.
<!-- An important part of the task of reducing confusion is to make code more accessible.
Especially in a field such as quantum computing that is rich with domain expertise, we must at all times be cognizant of the demands we place on that expertise as we design quantum software.
In naming code symbols, one way that this cognizance expresses itself is as an awareness of the convention from physics of adopting as the names of algorithms and operations the names of their original publishers.
While we must maintain the history and intellectual provenance of concepts in quantum computing, demanding that all users be versed in this history to use even the most basic of functions and operations places a barrier to entry that is in most cases severe enough to even present an ethical compromise. -->
Pertanto, si consiglia di adottare tutti i sostantivi comuni che descrivono un concetto con una preferenza forte ai sostantivi appropriati che descrivono la cronologia delle pubblicazioni di un concetto.
Come esempio specifico, le operazioni di scambio e doppia controllo non sono spesso chiamate "Fredkin" e "Toffoli" in letteratura accademica, ma sono identificate in Q # principalmente come `CSWAP` e `CCNOT` .
In entrambi i casi, i commenti relativi alla documentazione dell'API forniscono nomi sinonimi in base a sostantivi appropriati, insieme a tutte le citazioni appropriate.

Questa preferenza è particolarmente importante, dato che l'utilizzo dei sostantivi appropriati sarà sempre necessario: Q # segue le tradizioni impostate da molti linguaggi classici, ad esempio, e fa riferimento ai `Bool` tipi in riferimento alla logica booleana, che è a sua volta denominata in onore di George Boole.
Alcuni concetti di quantum vengono denominati in modo simile, incluso il `Pauli` tipo incorporato nel linguaggio Q #.
Riducendo al minimo l'utilizzo dei sostantivi appropriati in cui tale utilizzo non è essenziale, viene ridotto l'effetto in cui i sostantivi appropriati non possono essere ragionevolmente evitati.

# <a name="guidance"></a>[Indicazioni](#tab/guidance) 

È consigliabile:

- Evitare l'uso di sostantivi appropriati nei nomi.

# <a name="examples"></a>[esempi](#tab/examples)

***

### <a name="type-conversions"></a>Conversione di tipi ###

Poiché Q # è un linguaggio fortemente tipizzato in modo statico, un valore di un tipo può essere usato solo come valore di un altro tipo usando una chiamata esplicita a una funzione di conversione del tipo.
Si tratta di un contrasto rispetto ai linguaggi che consentono di modificare i tipi in modo implicito, ad esempio promozione del tipo, o tramite cast.
Di conseguenza, le funzioni di conversione dei tipi svolgono un ruolo importante nello sviluppo di una libreria Q # e comprendono una delle decisioni più comunemente rilevate per la denominazione.
Si noti, tuttavia, che poiché le conversioni di tipi sono sempre _deterministiche_, possono essere scritte come funzioni e quindi rientrare nei consigli precedenti.
In particolare, è consigliabile che le funzioni di conversione dei tipi non vengano mai denominate come verbi (ad esempio: `ConvertToX` ) o frasi preposizionali avverbio ( `ToX` ), ma devono essere denominate come frasi preposizionali aggettivali che indicano i tipi di origine e destinazione ( `XAsY` ).
Quando si elencano i tipi di matrici nei nomi delle funzioni di conversione del tipo, è consigliabile usare `Arr` la sintassi
Escludendo circostanze eccezionali, è consigliabile che tutte le funzioni di conversione del tipo vengano denominate utilizzando in `As` modo che possano essere identificate rapidamente.

# <a name="guidance"></a>[Indicazioni](#tab/guidance)

È consigliabile:

- Se una funzione converte un valore di tipo `X` in un valore di tipo `Y` , utilizzare il nome `AsY` o `XAsY` .

# <a name="examples"></a>[esempi](#tab/examples)

|   | Nome | Descrizione |
|---|------|-------------|
| ☒ | <s>`ToDouble`</s> | La preposizione "to" restituisce una frase verbo, che indica un'operazione e non una funzione. |
| ☒ | <s>`AsDouble`</s> | Il tipo di input non è chiaro dal nome della funzione. |
| ☒ | <s>`PauliArrFromBoolArr`</s> | I tipi di input e di output vengono visualizzati nell'ordine errato. |
| ☑ | `ResultArrAsBoolArr` | I tipi di input e di output sono entrambi chiari. |

***

### <a name="private-or-internal-names"></a>Nomi privati o interni ###

In molti casi, un nome è destinato esclusivamente all'uso interno a una libreria o a un progetto e non è una parte garantita dell'API offerta da una libreria.
È utile indicare chiaramente che questa situazione si verifica quando si denominano funzioni e operazioni in modo che le dipendenze accidentali sul codice solo interno siano rese evidenti.
Se un'operazione o una funzione non è destinata all'uso diretto, ma deve essere usata da un oggetto chiamabile corrispondente che agisce da applicazione parziale, provare a usare un nome che inizia con la `internal` parola chiave per l'oggetto chiamabile che viene applicato parzialmente.

# <a name="guidance"></a>[Indicazioni](#tab/guidance)

È consigliabile:

- Quando una funzione, un'operazione o un tipo definito dall'utente non fa parte dell'API pubblica per una libreria o un programma Q #, assicurarsi che sia contrassegnato come interno inserendo la `internal` parola chiave prima della `function` dichiarazione, `operation` o `newtype` .

# <a name="examples"></a>[esempi](#tab/examples)

|   | Nome | Descrizione |
|---|------|-------------|
| ☒ | <s>`operation _ApplyDecomposedOperation`</s> | Non usare un carattere di sottolineatura `_` per indicare che questa operazione è solo per uso interno. |
| ☑ | `internal operation ApplyDecomposedOperation` | La `internal` parola chiave all'inizio indica chiaramente che questa operazione è solo per uso interno. |

***
### <a name="variants"></a>Varianti ###

Anche se questa limitazione potrebbe non essere permanente nelle versioni future di Q #, è attualmente il caso che ci siano spesso gruppi di operazioni o funzioni correlate che si distinguono con i quali funtori gli input supportano o con i tipi concreti dei relativi argomenti.
Questi gruppi possono essere distinti usando lo stesso nome radice, seguito da una o due lettere che indicano la relativa variante.

| Suffisso | Significato |
|--------|---------|
| `A` | Input previsto per il supporto`Adjoint` |
| `C` | Input previsto per il supporto`Controlled` |
| `CA` | Input previsto per il supporto di `Controlled` e`Adjoint` |
| `I` | Input o input di tipo`Int` |
| `D` | Input o input di tipo`Double` |
| `L` | Input o input di tipo`BigInt` |

# <a name="guidance"></a>[Indicazioni](#tab/guidance)

È consigliabile:

- Se una funzione o un'operazione non è correlata a funzioni o operazioni simili da parte del supporto di tipi e functor degli input, non usare un suffisso.
- Se una funzione o un'operazione è correlata a funzioni o operazioni analoghe con i tipi e il supporto del functore degli input, usare i suffissi come nella tabella precedente per distinguere le varianti.

# <a name="examples"></a>[esempi](#tab/examples)

***

### <a name="arguments-and-variables"></a>Argomenti e variabili ###

Uno degli obiettivi principali del codice Q # per una funzione o un'operazione è per facilitarne la lettura e la comprensione.
Analogamente, i nomi degli input e degli argomenti di tipo devono comunicare come una funzione o un argomento verrà usato una volta specificati.


# <a name="guidance"></a>[Indicazioni](#tab/guidance)

È consigliabile:

- Per tutti i nomi di variabile e di input, utilizzare `pascalCase` in una preferenza forte per `CamelCase` , `snake_case` o `ANGRY_CASE` .
- I nomi di input devono essere descrittivi; evitare uno o due nomi di lettere laddove possibile.
- Le operazioni e le funzioni che accettano esattamente un argomento di tipo devono indicare tale argomento di tipo da `T` quando il suo ruolo è ovvio.
- Se una funzione o un'operazione accetta più argomenti di tipo o se il ruolo di un solo argomento di tipo non è ovvio, provare a usare una parola maiuscola breve preceduta da `T` (ad esempio: `TOutput` ) per ogni tipo.
- Non includere nomi di tipi in argomenti e nomi di variabili; Queste informazioni possono e devono essere fornite dall'ambiente di sviluppo.
- Indica i tipi scalari in base ai relativi nomi letterali ( `flagQubit` ) e ai tipi di matrice in base al plurale ( `measResults` ).
  Per le matrici di qubits in particolare, è consigliabile denominare tali tipi in base a `Register` cui il nome fa riferimento a una sequenza di qubits strettamente correlati in qualche modo.
- Le variabili usate come indici nelle matrici devono iniziare con `idx` e devono essere singolari (ad esempio, `things[idxThing]` ).
  In particolare, è consigliabile evitare di utilizzare nomi di variabili a lettera singola come indici. si consiglia `idx` di utilizzare almeno.
- Le variabili usate per contenere lunghezze di matrici devono iniziare con `n` e devono essere plurali (ad esempio, `nThings` ).

# <a name="examples"></a>[esempi](#tab/examples)

***

### <a name="user-defined-type-named-items"></a>Elementi denominati di tipo definito dall'utente ###

Gli elementi denominati in tipi definiti dall'utente devono essere denominati come `CamelCase` , anche in input per costruttori UDT.
Questo consente di separare chiaramente gli elementi denominati dai riferimenti alle variabili con ambito locale quando si usa la notazione della funzione di accesso (ad esempio, `callable::Apply` ) o la notazione di copia e aggiornamento ( `set arr w/= Data <- newData` ).

# <a name="guidance"></a>[Indicazioni](#tab/guidance)

È consigliabile:

- Gli elementi denominati nei costruttori UDT devono essere denominati come `CamelCase` , ovvero devono iniziare con una lettera maiuscola iniziale.
- Gli elementi denominati che risolvono le operazioni devono essere denominati come fasi del verbo.
- Gli elementi denominati che non vengono risolti in operazioni devono essere denominati frasi sostantive.
- Per i tipi definiti dall'utente che incapsulano le operazioni, è necessario definire un singolo elemento denominato denominato `Apply` .

# <a name="examples"></a>[esempi](#tab/examples)

|   | Frammento di codice | Descrizione |
|---|---------|-------------|
| ☑ | `newtype Oracle = (Apply : Qubit[] => Unit is Adj + Ctl)` | Il nome `Apply` è una `CamelCase` frase del verbo formattata, che suggerisce che l'elemento denominato è un'operazione. |
| ☒ | <s>`newtype Oracle = (apply : Qubit[] => Unit is Adj + Ctl) `</s> | Gli elementi denominati devono iniziare con una lettera maiuscola iniziale. |
| ☒ | <s>`newtype Collection = (Length : Int, Get : Int -> (Qubit => Unit)) `</s> | Gli elementi denominati che si risolvono in funzioni devono essere denominati come frasi sostantive, non come frasi verbo. |

***

## <a name="input-conventions"></a>Convenzioni di input ##

Quando uno sviluppatore chiama un'operazione o una funzione, i vari input per tale operazione o funzione devono essere specificati in un ordine particolare, aumentando il carico cognitivo che uno sviluppatore deve affrontare per poter usare una libreria.
In particolare, l'attività di ricordare gli ordini di input è spesso una distrazione dall'attività a disposizione: programmazione di un'implementazione di un algoritmo Quantum.
Sebbene il supporto avanzato dell'IDE possa mitigare questo problema in larga misura, una buona progettazione e aderenza alle convenzioni comuni può anche aiutare a ridurre al minimo il carico cognitivo imposto da un'API.

Laddove possibile, può essere utile ridurre il numero di input previsti da un'operazione o una funzione, in modo che il ruolo di ogni input sia più immediato per gli sviluppatori che chiamano tale operazione o funzione e per gli sviluppatori che leggono il codice in un secondo momento.
Soprattutto quando non è possibile o ragionevole ridurre il numero di argomenti a un'operazione o a una funzione, è importante avere un ordinamento coerente che riduca al minimo la sorpresa che un utente deve affrontare durante la stima dell'ordine degli input.

Si consiglia di usare le convenzioni di ordinamento di input che in gran parte derivano dal pensare a un'applicazione parziale come generalizzazione di currying f (x, y) ≡ f (x) (y).
Pertanto, l'applicazione parziale dei primi argomenti dovrebbe dare come risultato un oggetto chiamabile che risulta utile in un proprio momento, ogni volta che è ragionevole.
In base a questo principio, prendere in considerazione l'uso dell'ordine degli argomenti seguente:

- Argomenti classici non richiamabili, ad esempio angoli, vettori di potenza e così via.
- Argomenti chiamabili (funzioni e argomenti).
  Se entrambe le funzioni e le operazioni vengono considerate come argomenti, provare a inserire le operazioni dopo le funzioni.
- Le raccolte su cui si basano gli argomenti richiamabili sono simili a `Map` , `Iter` , `Enumerate` e `Fold` .
- Argomenti qubit usati come controlli.
- Argomenti qubit usati come destinazioni.

Si consideri un'operazione `ApplyPhaseEstimationIteration` da usare nella stima della fase che accetta un angolo e un Oracle, passa l'angolo a `Rz` modificato da una matrice di fattori di scalabilità diversi e quindi controlla le applicazioni di Oracle.
Gli input verranno ordinati in modo analogo al `ApplyPhaseEstimationIteration` seguente:

```qsharp
operation ApplyPhaseEstimationIteration(
    angle : Double,
    callable : (Qubit => () is Ctl),
    scaleFactors : Double[],
    controlQubit : Qubit,
    targetQubits : Qubit[]
)
: Unit
...
```
Come caso speciale di riduzione delle sorprese, alcune funzioni e operazioni simulano il comportamento dei funtori predefiniti `Adjoint` e `Controlled` .
Ad esempio, `ControlledOnInt<'T>` è di tipo `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)` , che `ControlledOnInt<Qubit[]>(5, _)` agisce come il `Controlled` functor, ma nella condizione in cui il registro di controllo rappresenta lo stato $ \ket {5} = \ket {101} $.
Uno sviluppatore prevede pertanto che gli input `ControlledOnInt` inserino l'ultimo oggetto chiamabile trasformato e che l'operazione risultante accetta come input `(Qubit[], 'T)` ---lo stesso ordine seguito dall'output del `Controlled` functore.

# <a name="guidance"></a>[Indicazioni](#tab/guidance)

È consigliabile:

- Usare gli ordini di input coerenti con l'uso dell'applicazione parziale.
- Usare gli ordini di input coerenti con funtori predefiniti.
- Inserire tutti gli input classici prima di qualsiasi input Quantum.

# <a name="examples"></a>[esempi](#tab/examples)

***

## <a name="documentation-conventions"></a>Convenzioni della documentazione ##

Il linguaggio Q # consente di allegare la documentazione a operazioni, funzioni e tipi definiti dall'utente tramite l'utilizzo di commenti di documentazione specificamente formattati.
Indicato da tre barre ( `///` ), questi commenti di documentazione sono documenti Markdown di piccole dimensioni [DocFX](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) che possono essere usati per descrivere lo scopo di ogni operazione, funzione e tipo definito dall'utente, quali sono gli input previsti e così via.
Il compilatore fornito con Quantum Development Kit estrae questi commenti e li usa per semplificare la documentazione del set di elementi in https://docs.microsoft.com/quantum .
Analogamente, il server di linguaggio fornito con Quantum Development Kit usa questi commenti per fornire assistenza agli utenti quando passano il mouse sui simboli nel codice Q #.
L'uso di commenti di documentazione può consentire agli utenti di dare senso al codice fornendo un riferimento utile per i dettagli che non sono facilmente espressi con le altre convenzioni di questo documento.

<div class="nextstepaction">
    [Documentazione di riferimento sulla sintassi di commenti](xref:microsoft.quantum.guide.filestructure#documentation-comments)
</div>

Per usare efficacemente questa funzionalità per aiutare gli utenti, è consigliabile tenere presenti alcuni aspetti quando si scrivono i commenti della documentazione.

# <a name="guidance"></a>[Indicazioni](#tab/guidance)

È consigliabile:

- Ogni funzione pubblica, operazione e tipo definito dall'utente deve essere immediatamente preceduta da un commento della documentazione.
- Come minimo, ogni commento alla documentazione deve includere le sezioni seguenti:
    - Riepilogo
    - Input
    - Output (se applicabile)
- Assicurarsi che tutti i riepiloghi siano due frasi o meno. Se è necessario più spazio, fornire una `# Description` sezione immediatamente successiva `# Summary` con i dettagli completi.
- Se ragionevole, non includere la matematica nei riepiloghi, perché non tutti i client supportano la notazione TeX nei riepiloghi. Si noti che durante la scrittura di documenti in prosa (ad esempio, TeX o Markdown), può essere preferibile usare lunghezze di riga più lunghe.
- Fornire tutte le espressioni matematiche rilevanti nella `# Description` sezione.
- Quando si descrivono gli input, non ripetere i tipi di ogni input in quanto questi possono essere dedotti dal compilatore e rischiano di introdurre incoerenza.
- Fornire esempi appropriati, ognuno nella propria `# Example` sezione.
- Descrivere brevemente ogni esempio prima di elencare il codice.
- Citare tutte le pubblicazioni accademiche rilevanti, ad esempio documenti, procedure, post di Blog e implementazioni alternative, in una `# References` sezione come elenco puntato dei collegamenti.
- Assicurarsi che, ove possibile, tutti i collegamenti di citazione siano identificatori permanenti e non modificabili (DOI o numeri arXiv con versione).
- Quando un'operazione o una funzione è correlata ad altre operazioni o funzioni in base alle varianti di functor, elencare altre varianti come punti elenco nella `# See Also` sezione.
- Lasciare una riga di commento vuota tra le sezioni di livello 1 ( `/// #` ), ma non lasciare una riga vuota tra le sezioni di livello 2 ( `/// ##` ).

# <a name="examples"></a>[esempi](#tab/examples)

#### <a name=""></a>☑ ####

```
/// # Summary
/// Applies a rotation about the X-axis by a given angle.
///
///
/// # Description
/// This operation rotates a single qubit by the unitary operation
/// \begin{align}
///     R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2}.
/// \end{align}
///
/// # Input
/// ## theta
/// Angle about which the qubit is to be rotated.
/// ## qubit
/// Qubit to which the gate should be applied.
///
/// # Remarks
/// Equivalent to:
/// ```qsharp
/// R(PauliX, theta, qubit);
/// ```
///
/// # See Also
/// - Ry
/// - Rz
operation Rx(theta : Double, qubit : Qubit) : Unit
is Adj + Ctl {
    body (...) { R(PauliX, theta, qubit); }
    adjoint (...) { R(PauliX, -theta, qubit); }
}
```

***

## <a name="formatting-conventions"></a>Convenzioni di formattazione ##

Oltre ai suggerimenti precedenti, è utile rendere il codice più leggibile possibile per l'utilizzo di regole di formattazione coerenti.
Tali regole di formattazione per natura tendono a essere arbitrarie e in modo forte fino a essere estetiche personali.
Tuttavia, si consiglia di mantenere un set coerente di convenzioni di formattazione all'interno di un gruppo di collaboratori e soprattutto per progetti Q # di grandi dimensioni, ad esempio Quantum Development Kit.
Queste regole possono essere applicate automaticamente usando lo strumento di formattazione integrato con il compilatore Q #.

# <a name="guidance"></a>[Indicazioni](#tab/guidance) 

È consigliabile:

- Usare quattro spazi anziché le schede per la portabilità.
  Ad esempio, in VS Code:
  ```json
    "editor.insertSpaces": true,
    "editor.tabSize": 4
  ```
- Ritorno a capo riga a 79 caratteri, ove ragionevole.
- Usare spazi intorno agli operatori binari.
- Usare spazi su entrambi i lati dei due punti usati per le annotazioni del tipo.
- Usare uno spazio singolo dopo le virgole usate nei valori letterali di matrice e di tupla (ad esempio, in input per funzioni e operazioni).
- Non usare spazi dopo i nomi di funzione, operazione o UDT o dopo le `@` dichiarazioni di attributo in.
- Ogni dichiarazione di attributo deve trovarsi su una riga a se stante.

# <a name="examples"></a>[esempi](#tab/examples)

|   | Frammento di codice | Descrizione |
|---|---------|-------------|
| ☒ | <s>`2+3`</s> | Usare spazi intorno agli operatori binari. |
| ☒ | <s>`target:Qubit`</s> | Usare spazi intorno ai due punti dell'annotazione del tipo. |
| ☑ | `Example(a, b, c)` | Gli elementi nella tupla di input sono spaziati correttamente per migliorare la leggibilità. |
| ☒ | <s>`Example (a, b, c)`</s> | Gli spazi devono essere eliminati dopo i nomi della funzione, dell'operazione o del tipo definito dall'utente. |

***
