---
title: Contributi della documentazione a Microsoft QDK
description: Informazioni su come fornire contenuti concettuali o API al set di documentazione Microsoft Quantum.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: contributor-guide
uid: microsoft.quantum.contributing.docs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8602705d2dd071e822e2ff58a9a44cd0684f77f1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857366"
---
# <a name="improving-documentation"></a>Miglioramento della documentazione

La documentazione per Quantum Development Kit assume diverse forme, in modo che le informazioni siano immediatamente disponibili per gli sviluppatori di Quantum.

Seguendo i principi di [docs come codice](https://www.writethedocs.org/guide/docs-as-code/), tutta la documentazione del kit di sviluppo quantum viene formattata come codice e viene gestita con git nello stesso modo del codice sorgente usato per compilare Quantum Development Kit.
Nella maggior parte dei casi, la documentazione di supporto del codice è costituita da diverse forme di [Markdown](https://daringfireball.net/projects/markdown/), un linguaggio per la scrittura di testo formattato in modo RTF in un formato di testo semplice e facile da usare nella riga di comando, negli IDE e con il controllo del codice sorgente.
La libreria [MathJax](https://www.mathjax.org/) viene adottata in modo analogo per consentire la formattazione della matematica nella documentazione mediante la lingua lattica, come descritto più avanti.


Detto questo, ogni forma di documentazione può variare leggermente nei dettagli:

- La **documentazione concettuale** è costituita da un set di articoli pubblicati in https://docs.microsoft.com/quantum e che descrivono tutti gli elementi, dalle nozioni di base del quantum computing alle specifiche tecniche per i formati di interscambio. Questi articoli sono scritti in [Markdown (DFM) DocFX](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html), una variante Markdown usata per la creazione di set di documentazione avanzati.
- Il **riferimento API** è un set di pagine per ogni Q# funzione, operazione e tipo definito dall'utente, pubblicato in https://docs.microsoft.com/qsharp/api/ . Queste pagine documentano gli input e le operazioni per ogni chiamabile, insieme ad esempi e collegamenti ad altre informazioni. Il riferimento all'API viene estratto automaticamente da piccoli documenti DFM nel Q# codice sorgente come parte di ogni versione.
- I file **Leggimi <!----> . MD** inclusi in ogni esempio e Kata descrivono come usare tale esempio o Kata, il suo contenuto e il modo in cui è correlato al resto del kit di sviluppo Quantum. Questi file vengono scritti usando [GitHub Flavored Markdown (GFM)](https://github.github.com/gfm/), un'alternativa più semplice a DFM che è popolare per il fissaggio della documentazione direttamente ai repository di codice.

## <a name="contributing-to-the-conceptual-documentation"></a>Contributo alla documentazione concettuale

Per contribuire a un miglioramento della documentazione concettuale o README, inizia con una richiesta pull su [**MicrosoftDocs/Quantum-docs-PR**](https://github.com/MicrosoftDocs/quantum-docs-pr/
), [**Microsoft/Quantum**](https://github.com/Microsoft/Quantum)o [**Microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas), come appropriato.
Di seguito vengono descritte altre informazioni sulle richieste pull, ma per il momento è opportuno tenere presente quanto segue per migliorare la documentazione:

- I lettori arrivano alla documentazione di Quantum Development Kit da una vasta gamma di sfondi. Tutti gli studenti di alta scuola che desiderano apprendere qualcosa di nuovo e entusiasmante fino a docenti di possesso che eseguono la ricerca di quantum computing dovrebbero essere in grado di leggere la documentazione. Nella misura in cui è possibile, non presupporre una conoscenza approfondita della parte dei lettori, perché potrebbero semplicemente iniziare. È molto utile se è possibile fornire descrizioni chiare e accessibili oppure può fornire collegamenti ad altre risorse per ulteriori informazioni.
- I set di documentazione non sono disposti come libri o documenti, in quanto i lettori arriveranno a quello che potrebbe sembrare il "medio". I motori di ricerca, ad esempio, potrebbero non suggerire l'indice oppure è possibile che sia stato inviato un collegamento da un amico che tenta di aiutarli. Provare a aiutare il lettore fornendo sempre un contesto chiaro, insieme ai collegamenti laddove appropriato.
- Alcuni lettori troveranno le definizioni e le istruzioni astratte più utili, mentre gli altri lettori funzionano meglio Estrapolando da esempi concreti. Fornire sia il caso generale che gli esempi specifici possono aiutare entrambi i lettori a sfruttare al meglio la programmazione quantistica.
- In particolare, se è stato scritto anche il codice documentato, è possibile che le cose risultino ovvie al lettore. Non esiste un modo univoco per programmare, quindi, indipendentemente dal livello di intelligenza o esperienza di un lettore, non è possibile indovinare quali modelli di progettazione sono stati trovati più utili per esprimere le proprie idee nel codice. Per chiarire il modo in cui un lettore può prevedere di usare il codice può contribuire a fornire tale contesto.
- Molti membri della community di programmazione quantistica sono ricercatori accademici e sono riconosciuti principalmente attraverso le citazioni per i contributi della community. Oltre a aiutare i lettori a trovare materiali aggiuntivi, assicurarsi di citare correttamente gli output accademici, ad esempio documenti, colloqui, post di Blog e strumenti software, per aiutare i collaboratori accademici a lavorare al meglio per migliorare la community.
- La community di programmazione quantistica è una community ampia e straordinariamente diversificata. L'uso di prosostantivi con sesso in esempi di terze persone (ad esempio, "Se un utente..., loro...") può funzionare da escludere anziché includere. La conoscenza dei nomi delle persone in citazioni e collegamenti e l'inclusione corretta di caratteri non ASCII possono soddisfare la diversità della community visualizzando i relativi membri. Analogamente, molte parole della lingua inglese vengono spesso utilizzate in modo odioso, in modo che il loro utilizzo nella documentazione tecnica possa causare danni sia ai singoli lettori che alla community.

### <a name="referencing-sample-code-from-conceptual-articles"></a>Riferimento a codice di esempio da articoli concettuali

Per includere il codice dal [repository degli esempi](https://github.com/Microsoft/Quantum), è possibile usare uno speciale DocFX-Flavored comando markdown:

```markdown
:::code language="qsharp" source="~/quantum/samples/algorithms/chsh-game/Game.qs" range="4-8":::
```

Questo comando importerà le righe da 4 a 8 del [ `Game.qs` file dall' `chsh-game` esempio](https://github.com/microsoft/Quantum/blob/main/samples/algorithms/chsh-game/Game.qs), contrassegnando tali righe come Q# codice allo scopo di evidenziare la sintassi.
Con questo comando è possibile evitare di duplicare il codice tra gli articoli concettuali e il repository degli esempi, in modo che il codice di esempio nella documentazione sia sempre il più aggiornato possibile.

### <a name="contributing-image-files"></a>Aggiunta di contributi ai file di immagine

**Importante**: per fare in modo che le immagini vengano renderizzate correttamente in modalità scura è necessario evitare lucidi.

- Per i file con estensione jpg. non è necessario eseguire alcuna operazione perché il formato jpg non supporta elementi trasparenti.
- Per i file con estensione png, è necessario aggiungere uno sfondo bianco o modificare il valore del canale alfa in **100**. Il modo più semplice per eseguire questa operazione in Windows consiste nell'aprire il file in **Paint** e salvarlo, sovrascrivendo il file originale.
- Per i file con estensione SVG è necessario aggiungere un rettangolo bianco nel livello più basso. Questa operazione può essere eseguita con **Inkscape**:
  1. Aprire il file con estensione SVG.
  1. Selezionare lo strumento creatore quadrato e tracciare un rettangolo bianco nella parte superiore della figura originale.
  1. Selezionare lo strumento **selezionare e trasformare gli oggetti** facendo clic sulla freccia scura o premendo **F1**.
  1. Quando il rettangolo è selezionato, fare clic sull'elemento della barra degli strumenti **in basso a selezione (fine)**.
  1. Modificare il rettangolo con il mouse o i tasti di direzione.

## <a name="contributing-to-the-api-references"></a>Aggiunta di un contributo ai riferimenti alle API

Per contribuire a migliorare i riferimenti alle API, è più utile aprire una richiesta pull direttamente sul codice in corso di documentazione.
Ogni funzione, operazione o tipo definito dall'utente supporta un commento sulla documentazione (indicato con `///` anziché `//` ).
Quando si compila ogni versione di Quantum Development Kit, questi commenti vengono usati per generare il riferimento all'API in https://docs.microsoft.com/qsharp/api/ , inclusi i dettagli sugli input e gli output di ogni callable, i presupposti per ogni chiamata ed esempi di come usarli.

> [!IMPORTANT]
> Assicurarsi di non modificare manualmente la documentazione dell'API generata, perché i file vengono sovrascritti con ogni nuova versione.
> Il contributo alla community viene valorizzato e si desidera assicurarsi che le modifiche continuino a consentire agli utenti di rilasciare dopo il rilascio.

Si consideri, ad esempio, la funzione `ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)` .
Un commento relativo alla documentazione dovrebbe consentire a un utente di imparare a interpretare `bits` e `oracle` e a cosa serve la funzione.
Ognuna di queste diverse informazioni può essere fornita al Q# compilatore da una sezione Markdown denominata in modo specifico nel commento della documentazione.
Per l'esempio di `ControlledOnBitString` , è possibile scrivere qualcosa di simile al seguente:

```qsharp
 /// # Summary
 /// Returns a unitary operation that applies an oracle on the target register if the 
 /// control register state corresponds to a specified bit mask.
 ///
 /// # Description
 /// The output of this function is an operation that can be represented by a
 /// unitary transformation $U$ such that
 /// \begin{align}
 ///     U \ket{b_0 b_1 \cdots b_{n - 1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_{n-1}} \otimes
 ///     \begin{cases}
 ///         V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_{n - 1}) = \texttt{bits} \\\\
 ///         \ket{\psi} & \textrm{otherwise}
 ///     \end{cases},
 /// \end{align}
 /// where $V$ is a unitary transformation that represents the action of the
 /// `oracle` operation.
 ///
 /// # Input
 /// ## bits
 /// The bit string to control the given unitary operation on.
 /// ## oracle
 /// The unitary operation to be applied on the target register.
 ///
 /// # Output
 /// A unitary operation that applies `oracle` on the target register if the control 
 /// register state corresponds to the bit mask `bits`.
 ///
 /// # Remarks
 /// The length of `bits` and `controlRegister` must be equal.
 ///
 /// Given a Boolean array `bits` and a unitary operation `oracle`, the output of this function
 /// is an operation that performs the following steps:
 /// * apply an `X` operation to each qubit of the control register that corresponds to `false` 
 /// element of the `bits`;
 /// * apply `Controlled oracle` to the control and target registers;
 /// * apply an `X` operation to each qubit of the control register that corresponds to `false` 
 /// element of the `bits` again to return the control register to the original state.
 ///
 /// The output of the `Controlled` functor is a special case of `ControlledOnBitString` where `bits` is equal to `[true, ..., true]`.
 ///
 /// # Example
 /// The following code snippets are equivalent:
 /// ```qsharp
 /// (ControlledOnBitString(bits, oracle))(controlRegister, targetRegister);
 /// ```
 /// and
 /// ```qsharp
 /// within {
 ///     ApplyPauliFromBitString(PauliX, false, bits, controlRegister);
 /// } apply {
 ///     Controlled oracle(controlRegister, targetRegister);
 /// }
 /// ```
 ///
 /// The following code prepares a state $\frac{1}{2}(\ket{00} - \ket{01} + \ket{10} + \ket{11})$:
 /// ```qsharp
 /// using (register = Qubit[2]) {
 ///     ApplyToEach(H, register);
 ///     (ControlledOnBitString([false], Z))(register[0..0], register[1]);
 /// }
 /// ```
 function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
 {
     return ControlledOnBitStringImpl(bits, oracle, _, _);
 }
```

È possibile visualizzare la versione di cui è stato eseguito il rendering del codice precedente nella [documentazione dell'API per la `ControlledOnBitString` funzione](xref:Microsoft.Quantum.Canon.ControlledOnBitString).

Oltre alla pratica generale della scrittura della documentazione, per la scrittura di commenti sulla documentazione dell'API è utile tenere presenti alcuni aspetti:

- Il formato di ogni commento della documentazione deve corrispondere a quello Q# previsto dal compilatore per visualizzare correttamente la documentazione. Alcune sezioni, ad esempio, `/// # Remarks` consentono contenuto a mano libera, mentre le sezioni come la `/// # See Also` sezione sono più restrittive.
- Un lettore può leggere la documentazione dell'API nel sito di riferimento dell'API principale, nel riepilogo per ogni spazio dei nomi o anche all'interno dell'IDE usando le informazioni sul passaggio del mouse. Assicurandosi che `/// # Summary` non sia più lungo di una frase, il lettore può determinare rapidamente se è necessario leggere ulteriori informazioni o cercare altrove e aiuta a eseguire rapidamente l'analisi tramite riepiloghi dello spazio dei nomi.
- La documentazione potrebbe essere molto più lunga del codice, ma è accettabile. Anche una piccola parte di codice può avere effetti imprevisti per gli utenti che non conoscono il contesto in cui tale codice esiste. Fornendo esempi concreti e spiegazioni chiare, è possibile aiutare gli utenti a sfruttare al meglio il codice disponibile.

<!-- ## LaTeX Formatting ##

**TODO** -->
