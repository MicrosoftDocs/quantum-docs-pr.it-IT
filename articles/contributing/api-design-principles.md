---
title: "Principi di progettazione dell'API Q #"
description: "Principi di progettazione dell'API Q #"
author: cgranade
ms.author: chgranad
ms.date: 3/9/2020
ms.topic: article
uid: microsoft.quantum.contributing.api-design
ms.openlocfilehash: 03c32331f8988181ec6fedcfc207d752b4a880b2
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/10/2020
ms.locfileid: "79024203"
---
# <a name="q-api-design-principles"></a>Principi di progettazione dell'API Q #

## <a name="introduction"></a>Introduzione

In quanto linguaggio e piattaforma, Q # consente agli utenti di scrivere, eseguire, comprendere ed esplorare le applicazioni Quantum.
Per consentire agli utenti di progettare librerie Q #, seguiamo un set di principi di progettazione dell'API per guidare i nostri progetti e per rendere disponibili librerie utilizzabili per la community di sviluppo Quantum.
Questo articolo elenca questi principi e fornisce esempi per guidarne l'applicazione durante la progettazione di API Q #.

> [!TIP]
> Si tratta di un documento piuttosto dettagliato che consente di semplificare lo sviluppo di librerie e i contributi di librerie approfondite.
> Probabilmente è molto utile se si scrivono librerie personalizzate in Q # o se si contribuiscono a ottenere funzionalità di maggiori dimensioni nel [repository delle librerie Q #](https://github.com/microsoft/QuantumLibraries).
>
> D'altra parte, se si desidera apprendere come contribuire più in generale al quantum Development Kit, è consigliabile iniziare con la [Guida ai contributi](xref:microsoft.quantum.contributing).
> Per informazioni più generali su come si consiglia di formattare il codice Q #, potrebbe essere interessante consultare la [Guida di stile](xref:microsoft.quantum.contributing.style).

## <a name="general-principles"></a>Principi generali

**Principio chiave:** Esporre le API che attivano le applicazioni Quantum.

- ✅ **scegliere** i nomi delle operazioni e delle funzioni che riflettono la struttura di alto livello di algoritmi e applicazioni.
- ⛔️ **non** esporre API incentrate principalmente sui dettagli di implementazione di basso livello.

**Principio chiave:** Avviare ogni progettazione di API con casi d'uso di esempio per garantire che le API siano intuitive da usare.

- ✅ **assicurarsi** che ogni componente di un'API pubblica disponga di un caso d'uso corrispondente, anziché provare a progettare per tutti i possibili utilizzi dall'inizio.
    In modo diverso, non introdurre API pubbliche nel caso in cui siano utili, ma assicurarsi che ogni parte di un'API abbia un esempio *concreto* in cui sarà utile.

  *Esempi:*
  - @"microsoft.quantum.canon.applytoeachca" può essere usato come `ApplyToEachCA(H, _)` per preparare i registri in uno stato di superposizione uniforme, un'attività comune in molti algoritmi quantistici. La stessa operazione può essere utilizzata anche per molte altre attività di preparazione, valori numerici e algoritmi basati su Oracle.

- ✅ **sono** disponibili Brainstorm e workshop sui nuovi progetti API per verificare che siano intuitivi e soddisfino i casi di utilizzo proposti.

  *Esempi:*
  - Esaminare il codice Q\# corrente per vedere come le nuove progettazioni API possono semplificare e chiarire le implementazioni esistenti.
  - Esaminare le progettazioni dell'API proposte con i rappresentanti dei gruppi di destinatari primari.

**Principio chiave:** Progettare API per supportare e incoraggiare codice leggibile.

- ✅ **assicurarsi** che il codice sia leggibile da esperti di dominio e non esperti.
- ✅ **DO** concentrare l'attenzione sugli effetti di ogni operazione e funzione all'interno dell'algoritmo di alto livello, usando la documentazione per approfondire i dettagli di implementazione in base alle esigenze.
- ✅ **seguire** la Guida di [stile comune Q\#](xref:microsoft.quantum.contributing.style) quando applicabile.

**Principio chiave:** Progettare le API in modo che siano stabili e forniscano compatibilità con le edizioni.

- ✅ deprecare normalmente le **API obsolete** quando sono necessarie modifiche di rilievo.

- ✅ **forniscono** le operazioni "shim" e le funzioni che consentono il corretto funzionamento del codice utente esistente durante la deprecazione.

  *Esempi:*
  - Quando si rinomina un'operazione denominata `EstimateExpectation` `EstimateAverage`, introdurre una nuova operazione denominata `EstimateExpectation` che chiama l'operazione originale con il nuovo nome, in modo che il codice esistente possa continuare a funzionare correttamente.

- ✅ **utilizzare** l'attributo @"microsoft.quantum.core.deprecated" per comunicare le deprecazioni all'utente.

- ✅ quando si rinomina un'operazione o una funzione **, specificare** il nuovo nome come input di stringa per `@Deprecated`.

- ⛔️ **non** rimuovere le funzioni o le operazioni esistenti senza un periodo di deprecazione di almeno sei mesi per le versioni di anteprima o almeno due anni per le versioni supportate.

## <a name="functions-and-operations"></a>Funzioni e operazioni

**Principio chiave:** assicurarsi che ogni funzione e operazione abbia un solo scopo ben definito all'interno dell'API.

- ⛔️ **non** esporre funzioni e operazioni che eseguono più attività non correlate.

**Principio chiave:** le funzioni e le operazioni di progettazione sono riutilizzabili come possibile e per prevedere le esigenze future.

- ✅ **le** funzioni e le operazioni di progettazione per comporre correttamente con altre funzioni e operazioni, sia nella stessa API che nelle librerie precedentemente esistenti.

  *Esempi:*
  - L'operazione @"microsoft.quantum.canon.delay" esegue presupposti minimi sull'input e può quindi essere usata per ritardare le applicazioni di entrambe le operazioni nella libreria standard Q # o in base a quanto definito dagli utenti.
    <!-- TODO: define bad example. -->

- ✅ **esporre** la logica classica puramente deterministica come funzioni anziché operazioni.

  *Esempi:*
  - Una subroutine che consente di eseguire la scrittura in modo deterministico dei quadrati dell'input a virgola mobile e deve quindi essere esposta all'utente come `Squared : Double -> Double` anziché come operazione `Square : Double => Double`. Questo consente la chiamata della subroutine in più posizioni, ad esempio all'interno di altre funzioni, e fornisce informazioni di ottimizzazione utili al compilatore che possono influire sulle prestazioni e sulle ottimizzazioni.
  - `ForEach<'TInput, 'TOutput>('TInput => 'TOutput, 'TInput[]) => 'TOutput[]` e `Mapped<'TInput, 'TOutput>('TInput -> 'TOutput, 'TInput[]) -> 'TOutput[]` differiscono dalle garanzie effettuate per quanto riguarda il determinismo; entrambi sono utili in circostanze diverse.
  - Le routine API che trasformano l'applicazione delle operazioni Quantum possono spesso essere eseguite in modo deterministico e pertanto possono essere rese disponibili come funzioni come `CControlled<'T>(op : 'T => Unit) => ((Bool, 'T) => Unit)`.

- ✅ **DO** generalizzare il tipo di input quanto più ragionevole per ogni funzione e operazione, usando i parametri di tipo in base alle esigenze.

  *Esempi:*
  - il tipo di `ApplyToEach` è `<'T>(('T => Unit), 'T[]) => Unit` anziché il tipo specifico dell'applicazione più comune, `((Qubit => Unit), Qubit[]) => Unit`.

> [!TIP]
> È importante prevedere le esigenze future, ma è importante anche risolvere problemi concreti per gli utenti.
> Agendo su questo principio chiave, in questo modo è sempre necessario prestare particolare attenzione e bilanciamento per evitare di sviluppare API "solo nel caso".

**Principio chiave:** scegliere i tipi di input e di output per le funzioni e le operazioni stimabili e che comunicano lo scopo di un oggetto chiamabile.

- ✅ **utilizzare** i tipi di tupla per raggruppare in modo logico gli input e gli output che sono significativi solo se considerati insieme. In questi casi è consigliabile utilizzare un tipo definito dall'utente.

  *Esempi:*
  - Una funzione per l'output del valore minimo locale di un'altra funzione potrebbe dover prendere i limiti di un intervallo di ricerca come input, in modo che `LocalMinima(fn : (Double -> Double), (left : Double, right : Double)) : Double` possa essere una firma appropriata.
  - Un'operazione per stimare un derivato di un classificatore di Machine Learning usando la tecnica di spostamento dei parametri potrebbe dover usare i vettori di parametri spostati e non spostati come input. In questo caso, un input simile a `(unshifted : Double[], shifted : Double[])` potrebbe essere appropriato.

- ✅ **ordinare** gli elementi nelle Tuple di input e output in modo coerente tra funzioni e operazioni diverse.

  *Esempi:*
  - Se si considerano due o funzioni o operazioni che accettano un angolo di rotazione e un qubit di destinazione come input, assicurarsi che siano ordinati allo stesso modo in ogni tupla di input. Ovvero preferiscono `ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl` e `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)` `ApplyRotation(target : Qubit, angle : Double) : Unit is Adj + Ctl` e `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)`.

**Principio chiave:** le funzioni e le operazioni di progettazione funzionano bene con le funzionalità del linguaggio Q\# come l'applicazione parziale.

- ✅ **ordinare** gli elementi delle tuple di input in modo che gli input applicati più comunemente si verifichino per primi, ad esempio, in modo che l'applicazione parziale agisca in modo analogo al currying.

  *Esempi:*
  - Un'operazione `ApplyRotation` che accetta un numero a virgola mobile e un qubit come input può spesso essere applicata parzialmente con l'input a virgola mobile per l'uso con operazioni che prevedono un input di tipo `Qubit => Unit`. Quindi, una firma di `operation ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl`
      funzionerebbe in modo più coerente con l'applicazione parziale.
  - In genere, questo materiale sussidiario significa inserire tutti i dati classici prima di tutti qubits nelle Tuple di input, ma usare un giudizio valido ed esaminare il modo in cui l'API viene chiamata in pratica.

## <a name="user-defined-types"></a>Tipi definiti dall'utente

**Principio chiave:** usare i tipi definiti dall'utente per rendere le API più espressive e convenienti da usare.

- ✅ **DO** introducono nuovi tipi definiti dall'utente per fornire un'abbreviazione utile per i tipi lunghi e/o complessi.

  *Esempi:*
  - Nei casi in cui un tipo di operazione con tre input di matrice qubit viene comunemente usato come input o restituito come output, fornendo un tipo definito dall'utente, ad esempio `newtype TimeDependentBlockEncoding = ((Qubit[], Qubit[], Qubit[]) => Unit is Adj + Ctl)`
      consente di fornire un'utile abbreviazione.

- ✅ **DO** introducono nuovi tipi definiti dall'utente per indicare che un determinato tipo di base deve essere utilizzato solo in un senso molto particolare.

  *Esempi:*
  - Un'operazione che deve essere interpretata in modo specifico come operazione che codifica i dati classici in un registro quantum può essere appropriata per l'etichetta con un tipo definito dall'utente `newtype InputEncoder = (Apply : (Qubit[] => Unit))`.

- ✅ **DO** introducono nuovi tipi definiti dall'utente con elementi denominati che consentono l'estendibilità futura (ad esempio, una struttura dei risultati che può contenere altri elementi denominati in futuro).

  *Esempi:*
  - Quando un'operazione `TrainModel` espone un numero elevato di opzioni di configurazione, l'esposizione di queste opzioni come nuovo UDT `TrainingOptions` e la fornitura di una nuova funzione `DefaultTrainingOptions : Unit -> TrainingOptions` consente agli utenti di eseguire l'override di elementi denominati specifici nei valori UDT TrainingOptions, consentendo allo stesso tempo agli sviluppatori di librerie di aggiungere nuovi elementi UDT nel modo appropriato.

- ✅ **dichiarare** gli elementi denominati per i nuovi tipi definiti dall'utente in modo da richiedere agli utenti di comprendere la decostruzione corretta della tupla.

  *Esempi:*
  - Quando si rappresenta un numero complesso nella relativa scomposizione polare, preferire `newtype ComplexPolar = (Magnitude: Double, Argument: Double)` `newtype ComplexPolar = (Double, Double)`.

**Principio chiave:** usare i tipi definiti dall'utente in modo da ridurre il carico cognitivo e non richiedere all'utente di apprendere concetti e nomenclatura aggiuntivi.

- ⛔️ **non** introducono tipi definiti dall'utente che richiedono l'uso frequente dell'operatore Unwrap (`!`) o che richiedono in genere più livelli di annullamento del wrapping. Le strategie di mitigazione possibili includono:

  - Quando si espone un tipo definito dall'utente con un singolo elemento, è consigliabile definire un nome per l'elemento. Si consideri, ad esempio, `newtype Encoder = (Apply : (Qubit[] => Unit is Adj + Ctl))` preferenza a `newtype Encoder = (Qubit[] => Unit is Adj + Ctl)`.

  - Assicurandosi che altre funzioni e operazioni possano accettare direttamente le istanze del tipo definito dall'utente "Wrapped".

- ⛔️ **non** introducono nuovi tipi definiti dall'utente che duplicano i tipi incorporati senza fornire un'espressività aggiuntiva.

  *Esempi:*
  - Un tipo definito dall'utente `newtype QubitRegister = Qubit[]` non fornisce espressività aggiuntiva rispetto `Qubit[]`ed è quindi più difficile da usare senza alcun vantaggio distinguibile.
  - Un tipo definito dall'utente `newtype LittleEndian = Qubit[]` documenta il modo in cui deve essere usato e interpretato il registro sottostante e quindi fornisce un'espressività aggiuntiva sul relativo tipo di base.

- ⛔️ **non** introducono funzioni di accesso a meno che non sia strettamente necessario;   in questo caso, è consigliabile preferire gli elementi denominati.

  *Esempi:*
  - Quando si introduce un tipo definito dall'utente `newtype Complex = (Double, Double)`, è preferibile modificare la definizione per `newtype Complex = (Real : Double, Imag : Double)` all'introduzione di funzioni `GetReal : Complex -> Double` e `GetImag : Complex -> Double`.

## <a name="namespaces-and-organization"></a>Spazi dei nomi e organizzazione

**Principio chiave:** scegliere i nomi degli spazi dei nomi stimabili e che comunicano chiaramente lo scopo di funzioni, operazioni e tipi definiti dall'utente in ogni spazio dei nomi.

- ✅ gli spazi dei nomi **vengono** denominati come `Publisher.Product.DomainArea`.

  *Esempi:*
  - Le funzioni, le operazioni e i tipi definiti dall'utente pubblicati da Microsoft nell'ambito della funzionalità di simulazione quantistica del quantum Development Kit vengono inseriti nello spazio dei nomi `Microsoft.Quantum.Simulation`.
  - `Microsoft.Quantum.Math` rappresenta uno spazio dei nomi pubblicato da Microsoft come parte del quantum Development Kit relativo all'area del dominio matematico.

- ✅ **DO** inseriscono operazioni, funzioni e tipi definiti dall'utente utilizzati per funzionalità specifiche in uno spazio dei nomi in cui viene descritta tale funzionalità, anche quando tale funzionalità viene utilizzata in domini problematici diversi.

  *Esempi:*
  - Le API di preparazione dello stato pubblicate da Microsoft come parte del quantum Development Kit verrebbero inserite in `Microsoft.Quantum.Preparation`.
  - Le API di simulazione quantistica pubblicate da Microsoft come parte del quantum Development Kit verrebbero inserite in `Microsoft.Quantum.Simulation`.

- ✅ inseriscono operazioni, funzioni e tipi definiti dall'utente utilizzati solo all'interno di domini specifici in spazi dei nomi che **ne** indicano il dominio di utilità. Se necessario, utilizzare i sottospazi dei nomi per indicare le attività mirate all'interno di ogni spazio dei nomi specifico del dominio.

  *Esempi:*
  - La libreria Quantum Machine Learning pubblicata da Microsoft si trova in gran parte nello spazio dei nomi @"microsoft.quantum.machinelearning", ma i set di impostazioni di esempio vengono forniti dallo spazio dei nomi @"microsoft.quantum.machinelearning.datasets".
  - Le API di chimica quantistica pubblicate da Microsoft come parte del quantum Development Kit devono essere inserite in `Microsoft.Quantum.Chemistry`. Le funzionalità specifiche dell'implementazione della scomposizione Giordania--Wigner possono essere inserite in `Microsoft.Quantum.Chemistry.JordanWigner`, in modo che l'interfaccia primaria per l'area del dominio di chimica quantistica non sia interessata dalle implementazioni.

**Principio chiave:** Usare insieme gli spazi dei nomi e i modificatori di accesso per essere intenzionali sulla superficie dell'API esposta agli utenti e per nascondere i dettagli interni correlati all'implementazione e al test delle API.

- ✅ ogni volta che è ragionevole **, inserire tutte** le funzioni e le operazioni necessarie per implementare un'API nello stesso spazio dei nomi dell'API implementata, ma contrassegnata con le parole chiave "private" o "Internal" per indicare che non fanno parte della superficie dell'API pubblica per una raccolta. Usare un nome che inizia con un carattere di sottolineatura (`_`) per distinguere visivamente le operazioni e le operazioni private e interne dalle funzioni chiamabili pubbliche.

  *Esempi:*
  - Il nome dell'operazione `_Features` indica una funzione privata per uno spazio dei nomi e un assembly specificati e deve essere accompagnata dalla parola chiave `internal`.

- ✅ nel raro caso in cui sia necessario un set completo di funzioni o funzioni private per implementare l'API per un determinato spazio dei **nomi,** inserirle in un nuovo spazio dei nomi che corrisponde allo spazio dei nomi implementato e che termina con `.Private`.

- ✅ **eseguire** tutti gli unit test in spazi dei nomi che corrispondono allo spazio dei nomi sottoposto a test e che terminano con `.Tests`.

## <a name="naming-conventions-and-vocabulary"></a>Convenzioni di denominazione e vocabolario

**Principio chiave:** Scegli i nomi e la terminologia che sono chiari, accessibili e leggibili in una vasta gamma di destinatari, inclusi sia i novizi quantistici che gli esperti.

- ⛔️ **non** usare nomi di identificatori discriminatori o esclusioni, né la terminologia nei commenti della documentazione dell'API.

- ✅ **usare** i commenti relativi alla documentazione API per fornire contesto, esempi e riferimenti pertinenti, soprattutto per concetti più complessi.

- ⛔️ **non** usano nomi di identificatore inutilmente esoterici o che richiedono una conoscenza significativa degli algoritmi Quantum da leggere.

  *Esempi:*
  - Preferisce "iterazione di amplificazione dell'ampiezza" a "iterazione Grover".

- ✅ **DO** scelgono le operazioni e i nomi di funzione che comunicano chiaramente l'effetto previsto di un oggetto chiamabile e non la relativa implementazione. Si noti che l'implementazione può e deve essere

  *Esempi:*
  - Preferisco "stima sovrapposizione" a "Hadamard test", perché quest'ultimo comunica come viene implementato il primo.

- ✅ **usare** parole in modo coerente in tutte le API di Q\#:

  - **Verbi**

    - **Assert**: verificare che un presupposto sullo stato di un computer di destinazione e del relativo qubits contenga, possibilmente usando risorse non fisiche. Le operazioni che usano questo verbo devono essere sempre rimovibili in modo sicuro senza influire sulla funzionalità delle librerie e dei programmi eseguibili. Si noti che, a differenza dei fatti, le asserzioni possono in genere dipendere dallo stato esterno, ad esempio lo stato di un registro qubit, l'ambiente di esecuzione o così via. Poiché la dipendenza dallo stato esterno è un tipo di effetto collaterale, le asserzioni devono essere esposte come operazioni anziché come funzioni.

    - **Stima**: utilizzando una o più misurazioni eventualmente ripetute, stimare una quantità classica dai risultati della misurazione.

      *Esempi:*
      - @"microsoft.quantum.characterization.estimatefrequency"
      - @"microsoft.quantum.characterization.estimateoverlapbetweenstates"

    - **Preparazione**: applicare un'operazione Quantum o una sequenza di operazioni a uno o più qubits si presuppone che si avvii in uno stato iniziale specifico (in genere $ \ket{00\cdots 0} $), causando lo stato di tali qubits per evolversi a uno stato finale desiderato. In generale, l'uso di stati diversi dallo stato di avvio specificato **può** comportare una trasformazione unitaria non definita, ma **deve** comunque mantenere che un'operazione e la relativa annullata "Annulla" e applichino un no-op.

      *Esempi:*
      - @"microsoft.quantum.preparation.preparearbitrarystate"
      - @"microsoft.quantum.preparation.prepareuniformsuperposition"

    - **Measure**: applicare un'operazione Quantum o una sequenza di operazioni a uno o più qubits, leggendo il backup dei dati classici.

      *Esempi:*
      - @"microsoft.quantum.intrinsic.measure"
      - @"microsoft.quantum.arithmetic.measurefxp"
      - @"microsoft.quantum.arithmetic.measureinteger"

    - **Apply**: applicare un'operazione Quantum o una sequenza di operazioni a uno o più qubits, causando la modifica dello stato di tali qubits in modo coerente. Questo verbo è il verbo più generale nella nomenclatura Q\# e **non deve essere** usato quando un verbo più specifico è più direttamente pertinente.

  - **Sostantivi**:

    - **Fact**: condizione booleana che dipende solo dagli input e non dallo stato di un computer di destinazione, dal relativo ambiente o dallo stato del qubits del computer. Al contrario di un'asserzione, un fatto è sensibile solo ai *valori* forniti al fatto. Ad esempio:

      *Esempi:*
      - @"microsoft.quantum.diagnostics.equalityfacti": rappresenta un fatto di uguaglianza per due input Integer; i numeri interi specificati come input sono uguali tra loro o non sono, indipendentemente da qualsiasi altro stato del programma.

    - **Opzioni:** Tipo definito dall'utente che contiene più elementi denominati che possono fungere da "argomenti facoltativi" per una funzione o un'operazione. Ad esempio:

      *Esempi:*
      - Il tipo definito dall'utente @"microsoft.quantum.machinelearning.trainingoptions" include gli elementi denominati per la velocità di apprendimento, le dimensioni minibatch e altri parametri configurabili per la formazione ML.

  - **Aggettivi**:

    - ⛔️ **nuovo**: questo aggettivo **non deve** essere usato, come per evitare confusione con l'utilizzo come verbo in molti linguaggi di programmazione, ad esempio C++, C#, Java, typescript, PowerShell.

  - **Preposizioni:** In alcuni casi, è possibile usare le preposizioni per eliminare ulteriormente le ambiguità o chiarire i ruoli di sostantivi e verbi nei nomi delle funzioni e delle operazioni. È necessario prestare attenzione a tale scopo, tuttavia, in modo sporadico e coerente.

    - **Come:** Indica che l'input e l'output di una funzione rappresentano le stesse informazioni, ma che l'output rappresenta le informazioni **come** una *X* anziché la rappresentazione originale. Questa operazione è particolarmente comune per le funzioni di conversione dei tipi.

      *Esempi:*
      - `IntAsDouble(2)` indica che l'input (`2`) e l'output (`2.0`) rappresentano in modo qualitativo le stesse informazioni, ma utilizzano diversi tipi di dati Q\# a tale scopo.

    - **Da:** Per garantire la coerenza, questa preposizione **non deve** essere utilizzata per indicare funzioni di conversione del tipo o altri casi **in** cui è appropriato.

    - ⛔️ **:** questa preposizione **non deve** essere utilizzata per evitare confusione con l'utilizzo come verbo in molti linguaggi di programmazione.
