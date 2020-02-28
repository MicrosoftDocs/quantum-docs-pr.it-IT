---
title: Contributi della documentazione a Microsoft QDK
description: Informazioni su come fornire contenuti concettuali o API al set di documentazione Microsoft Quantum.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.docs
ms.openlocfilehash: d244a7841b4093031d6225230a6cbefb22cc6a39
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904894"
---
# <a name="improving-documentation"></a><span data-ttu-id="f1dcb-103">Miglioramento della documentazione</span><span class="sxs-lookup"><span data-stu-id="f1dcb-103">Improving Documentation</span></span> #

<span data-ttu-id="f1dcb-104">La documentazione per Quantum Development Kit assume diverse forme, in modo che le informazioni siano immediatamente disponibili per gli sviluppatori di Quantum.</span><span class="sxs-lookup"><span data-stu-id="f1dcb-104">The documentation for the Quantum Development Kit takes on several different forms, such that information is readily available to quantum developers.</span></span>

<span data-ttu-id="f1dcb-105">Seguendo i principi di [docs come codice](https://www.writethedocs.org/guide/docs-as-code/), tutta la documentazione del kit di sviluppo quantum viene formattata come codice e viene gestita con git nello stesso modo del codice sorgente usato per compilare Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="f1dcb-105">Following the principles of [Docs as Code](https://www.writethedocs.org/guide/docs-as-code/), all Quantum Development Kit documentation is formatted as code and is managed using Git in the same way as the source code that is used to build the Quantum Development Kit.</span></span>
<span data-ttu-id="f1dcb-106">Nella maggior parte dei casi, la documentazione di supporto del codice è costituita da diverse forme di [Markdown](https://daringfireball.net/projects/markdown/), un linguaggio per la scrittura di testo formattato in modo RTF in un formato di testo semplice e facile da usare nella riga di comando, negli IDE e con il controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="f1dcb-106">For the most part, the code backing documentation consists of various forms of [Markdown](https://daringfireball.net/projects/markdown/), a language for writing out richly formatted text in a plain text format that's easy to use at the command line, in IDEs, and with source control.</span></span>
<span data-ttu-id="f1dcb-107">La libreria [MathJax](https://www.mathjax.org/) viene adottata in modo analogo per consentire la formattazione della matematica nella documentazione mediante la lingua lattica, come descritto più avanti.</span><span class="sxs-lookup"><span data-stu-id="f1dcb-107">We similarly adopt the [MathJax](https://www.mathjax.org/) library to allow for formatting mathematics in documentation using the LaTeX language, as detailed further below.</span></span>


<span data-ttu-id="f1dcb-108">Detto questo, ogni forma di documentazione può variare leggermente nei dettagli:</span><span class="sxs-lookup"><span data-stu-id="f1dcb-108">That said, each form of documentation does vary somewhat in the details:</span></span>

- <span data-ttu-id="f1dcb-109">La **documentazione concettuale** è costituita da un set di articoli pubblicati per la https://docs.microsoft.com/quantume che descrivono tutti gli elementi, dalle nozioni di base del quantum computing alle specifiche tecniche per i formati di interscambio.</span><span class="sxs-lookup"><span data-stu-id="f1dcb-109">The **conceptual documentation** consists of a set of articles that are published to https://docs.microsoft.com/quantum, and that describe everything from the basics of quantum computing to the technical specifications for interchange formats.</span></span> <span data-ttu-id="f1dcb-110">Questi articoli sono scritti in [Markdown (DFM) DocFX](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html), una variante Markdown usata per la creazione di set di documentazione avanzati.</span><span class="sxs-lookup"><span data-stu-id="f1dcb-110">These articles are written in [DocFX-Flavored Markdown (DFM)](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html), a Markdown variant used for creating rich documentation sets.</span></span>
- <span data-ttu-id="f1dcb-111">Il **riferimento all'API** è un set di pagine per ogni funzione Q #, operazione e tipo definito dall'utente, pubblicata in https://docs.microsoft.com/qsharp/api/.</span><span class="sxs-lookup"><span data-stu-id="f1dcb-111">The **API reference** is a set of pages for each Q# function, operation, and user-defined type, published to https://docs.microsoft.com/qsharp/api/.</span></span> <span data-ttu-id="f1dcb-112">Queste pagine documentano gli input e le operazioni per ogni chiamabile, insieme ad esempi e collegamenti ad altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="f1dcb-112">These pages document the inputs and operations to each callable, along with examples and links to more information.</span></span> <span data-ttu-id="f1dcb-113">Il riferimento all'API viene estratto automaticamente da piccoli documenti DFM nel codice sorgente Q # come parte di ogni versione.</span><span class="sxs-lookup"><span data-stu-id="f1dcb-113">The API reference is automatically extracted from small DFM documents in Q# source code as a part of each release.</span></span>
- <span data-ttu-id="f1dcb-114">Il file Leggimi<!---->i file con **estensione MD** inclusi in ogni esempio e Kata descrivono come usare tale esempio o Kata, cosa copre e come si riferisce al resto del kit di sviluppo Quantum.</span><span class="sxs-lookup"><span data-stu-id="f1dcb-114">The **README<!---->.md** files included with each sample and kata describe how to use that sample or kata is used, what it covers, and how it relates to the rest of the Quantum Development Kit.</span></span> <span data-ttu-id="f1dcb-115">Questi file vengono scritti usando [GitHub Flavored Markdown (GFM)](https://github.github.com/gfm/), un'alternativa più semplice a DFM che è popolare per il fissaggio della documentazione direttamente ai repository di codice.</span><span class="sxs-lookup"><span data-stu-id="f1dcb-115">These files are written using [GitHub Flavored Markdown (GFM)](https://github.github.com/gfm/), a more lightweight alternative to DFM that's popular for attaching documentation directly to code repositories.</span></span>

## <a name="contributing-to-the-conceptual-documentation"></a><span data-ttu-id="f1dcb-116">Contributo alla documentazione concettuale</span><span class="sxs-lookup"><span data-stu-id="f1dcb-116">Contributing to the Conceptual Documentation</span></span> ##

<span data-ttu-id="f1dcb-117">Per contribuire a un miglioramento della documentazione concettuale o README, inizia con una richiesta pull su [**MicrosoftDocs/Quantum-docs-PR**](https://github.com/MicrosoftDocs/quantum-docs-pr/
), [**Microsoft/Quantum**](https://github.com/Microsoft/Quantum)o [**Microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas), come appropriato.</span><span class="sxs-lookup"><span data-stu-id="f1dcb-117">To contribute an improvement to the conceptual or README documentation, then, starts with a pull request onto either [**MicrosoftDocs/quantum-docs-pr**](https://github.com/MicrosoftDocs/quantum-docs-pr/
), [**Microsoft/Quantum**](https://github.com/Microsoft/Quantum), or [**Microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas), as is appropriate.</span></span>
<span data-ttu-id="f1dcb-118">Di seguito vengono descritte altre informazioni sulle richieste pull, ma per il momento è opportuno tenere presente quanto segue per migliorare la documentazione:</span><span class="sxs-lookup"><span data-stu-id="f1dcb-118">We'll describe more about pull requests below, but for now there's a few things that are good to keep in mind as you improve documentation:</span></span>

- <span data-ttu-id="f1dcb-119">I lettori arrivano alla documentazione di Quantum Development Kit da una vasta gamma di sfondi.</span><span class="sxs-lookup"><span data-stu-id="f1dcb-119">Readers come to the Quantum Development Kit documentation from a very wide range of backgrounds.</span></span> <span data-ttu-id="f1dcb-120">Tutti gli studenti di alta scuola che desiderano apprendere qualcosa di nuovo e entusiasmante fino a docenti di possesso che eseguono la ricerca di quantum computing dovrebbero essere in grado di leggere la documentazione.</span><span class="sxs-lookup"><span data-stu-id="f1dcb-120">Everyone from high school students looking to learn something new and exciting through to tenured faculty performing quantum computing research should be able to get something out of reading the documentation.</span></span> <span data-ttu-id="f1dcb-121">Nella misura in cui è possibile, non presupporre una conoscenza approfondita della parte dei lettori, perché potrebbero semplicemente iniziare. È molto utile se è possibile fornire descrizioni chiare e accessibili oppure può fornire collegamenti ad altre risorse per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="f1dcb-121">To the extent that's possible, please don't assume extensive knowledge on the part of your readers, as they may just be starting out. It's most helpful if you can provide clear and accessible descriptions, or can provide links to other resources for more information.</span></span>
- <span data-ttu-id="f1dcb-122">I set di documentazione non sono disposti come libri o documenti, in quanto i lettori arriveranno a quello che potrebbe sembrare il "medio".</span><span class="sxs-lookup"><span data-stu-id="f1dcb-122">Documentation sets aren't laid out like books or papers, in that readers will arrive in what might seem like the "middle."</span></span> <span data-ttu-id="f1dcb-123">I motori di ricerca, ad esempio, potrebbero non suggerire l'indice oppure è possibile che sia stato inviato un collegamento da un amico che tenta di aiutarli. Provare a aiutare il lettore fornendo sempre un contesto chiaro, insieme ai collegamenti laddove appropriato.</span><span class="sxs-lookup"><span data-stu-id="f1dcb-123">For example, search engines might not suggest the index, or they might have been sent a link by a friend trying to help them out. Try to help your reader by always providing a clear context, along with links where appropriate.</span></span>
- <span data-ttu-id="f1dcb-124">Alcuni lettori troveranno le definizioni e le istruzioni astratte più utili, mentre gli altri lettori funzionano meglio Estrapolando da esempi concreti.</span><span class="sxs-lookup"><span data-stu-id="f1dcb-124">Some readers will find abstract statements and definitions most helpful, while other readers work best by extrapolating from concrete examples.</span></span> <span data-ttu-id="f1dcb-125">Fornire sia il caso generale che gli esempi specifici possono aiutare entrambi i lettori a sfruttare al meglio la programmazione quantistica.</span><span class="sxs-lookup"><span data-stu-id="f1dcb-125">Providing both the general case and specific examples can help both readers get the most out of quantum programming.</span></span>
- <span data-ttu-id="f1dcb-126">In particolare, se è stato scritto anche il codice documentato, è possibile che le cose risultino ovvie al lettore.</span><span class="sxs-lookup"><span data-stu-id="f1dcb-126">Especially if you also wrote the code being documented, things may be obvious to you that are not at all obvious to your reader.</span></span> <span data-ttu-id="f1dcb-127">Non esiste un modo univoco per programmare, quindi, indipendentemente dal livello di intelligenza o esperienza di un lettore, non è possibile indovinare quali modelli di progettazione sono stati trovati più utili per esprimere le proprie idee nel codice.</span><span class="sxs-lookup"><span data-stu-id="f1dcb-127">There's no one unique best way to program, so no matter how clever or experienced a reader might be, they can't guess at what design patterns you found the most helpful to express your ideas in code.</span></span> <span data-ttu-id="f1dcb-128">Per chiarire il modo in cui un lettore può prevedere di usare il codice può contribuire a fornire tale contesto.</span><span class="sxs-lookup"><span data-stu-id="f1dcb-128">Being clear about how a reader can expect to make use of your code can help provide that context.</span></span>
- <span data-ttu-id="f1dcb-129">Molti membri della community di programmazione quantistica sono ricercatori accademici e sono riconosciuti principalmente attraverso le citazioni per i contributi della community.</span><span class="sxs-lookup"><span data-stu-id="f1dcb-129">Many members of the quantum programming community are academic researchers, and are recognized mainly through citations for their contributions to the community.</span></span> <span data-ttu-id="f1dcb-130">Oltre a aiutare i lettori a trovare materiali aggiuntivi, assicurarsi di citare correttamente gli output accademici, ad esempio documenti, colloqui, post di Blog e strumenti software, per aiutare i collaboratori accademici a lavorare al meglio per migliorare la community.</span><span class="sxs-lookup"><span data-stu-id="f1dcb-130">In addition to helping readers find additional materials, making sure to properly cite academic outputs such as papers, talks, blog posts, and software tools can help academic contributors to keep doing their best work to improve the community.</span></span>
- <span data-ttu-id="f1dcb-131">La community di programmazione quantistica è una community ampia e straordinariamente diversificata.</span><span class="sxs-lookup"><span data-stu-id="f1dcb-131">The quantum programming community is a broad and wonderfully diverse community.</span></span> <span data-ttu-id="f1dcb-132">L'uso di pronomi con sesso in esempi di terze persone (ad esempio, "Se un utente..., he he...") può lavorare per escludere anziché includere.</span><span class="sxs-lookup"><span data-stu-id="f1dcb-132">The use of gendered pronouns in third-person examples (e.g.: "if a user ..., he will ...") can work to exclude rather than include.</span></span> <span data-ttu-id="f1dcb-133">La conoscenza dei nomi delle persone in citazioni e collegamenti e l'inclusione corretta di caratteri non ASCII possono soddisfare la diversità della community visualizzando i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="f1dcb-133">Being cognizant of people's names in citations and links, and of the correct inclusion of non-ASCII characters can serve the diversity of the community by showing respect to its members.</span></span> <span data-ttu-id="f1dcb-134">Analogamente, molte parole della lingua inglese vengono spesso utilizzate in modo odioso, in modo che il loro utilizzo nella documentazione tecnica possa causare danni sia ai singoli lettori che alla community.</span><span class="sxs-lookup"><span data-stu-id="f1dcb-134">Similarly, many words in the English language are often used in a hateful manner, such that their use in technical documentation can cause harm both to individual readers and to the community at large.</span></span>

## <a name="contributing-to-the-api-references"></a><span data-ttu-id="f1dcb-135">Aggiunta di un contributo ai riferimenti alle API</span><span class="sxs-lookup"><span data-stu-id="f1dcb-135">Contributing to the API References</span></span> ##

<span data-ttu-id="f1dcb-136">Per contribuire a migliorare i riferimenti alle API, è più utile aprire una richiesta pull direttamente sul codice in corso di documentazione.</span><span class="sxs-lookup"><span data-stu-id="f1dcb-136">To contribute an improvement to the API references, it's most helpful to open a pull request directly on the code being documented.</span></span>
<span data-ttu-id="f1dcb-137">Ogni funzione, operazione o tipo definito dall'utente supporta un commento sulla documentazione (indicato con `///` anziché `//`).</span><span class="sxs-lookup"><span data-stu-id="f1dcb-137">Each function, operation, or user-defined type supports a documentation comment (denoted with `///` instead of `//`).</span></span>
<span data-ttu-id="f1dcb-138">Quando si compila ogni versione di Quantum Development Kit, questi commenti vengono usati per generare il riferimento all'API in https://docs.microsoft.com/qsharp/api/, inclusi i dettagli relativi agli input e agli output di ogni callable, i presupposti per ogni chiamata ed esempi di come usarli.</span><span class="sxs-lookup"><span data-stu-id="f1dcb-138">When we compile each release of the Quantum Development Kit, these comments are used to generate the API reference at https://docs.microsoft.com/qsharp/api/, including details about the inputs to and outputs from each callable, the assumptions each callable makes, and examples of how to use them.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f1dcb-139">Assicurarsi di non modificare manualmente la documentazione dell'API generata, perché i file vengono sovrascritti con ogni nuova versione.</span><span class="sxs-lookup"><span data-stu-id="f1dcb-139">Please make sure to not manually edit the generated API documentation, as these files are overwritten with each new release.</span></span>
> <span data-ttu-id="f1dcb-140">Il contributo alla community viene valorizzato e si desidera assicurarsi che le modifiche continuino a consentire agli utenti di rilasciare dopo il rilascio.</span><span class="sxs-lookup"><span data-stu-id="f1dcb-140">We value your contribution to the community, and want to make sure that your changes continue to help users release after release.</span></span>

<span data-ttu-id="f1dcb-141">Si consideri, ad esempio, la funzione `ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="f1dcb-141">For example, consider the function `ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="f1dcb-142">Un commento relativo alla documentazione dovrebbe aiutare un utente a imparare a interpretare `bits` e `oracle` e a cosa serve la funzione.</span><span class="sxs-lookup"><span data-stu-id="f1dcb-142">A documentation comment should help a user learn how to interpret `bits` and `oracle` and what the function is for.</span></span>
<span data-ttu-id="f1dcb-143">Ognuna di queste diverse informazioni può essere fornita al compilatore Q # da una sezione Markdown denominata in modo specifico nel commento della documentazione.</span><span class="sxs-lookup"><span data-stu-id="f1dcb-143">Each of these different pieces of information can be provided to the Q# compiler by a specially named Markdown section in the documentation comment.</span></span>
<span data-ttu-id="f1dcb-144">Per l'esempio di `ControlledOnBitString`, è possibile scrivere qualcosa di simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="f1dcb-144">For the example of `ControlledOnBitString`, we might write something like the following:</span></span>

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
<span data-ttu-id="f1dcb-145">È possibile visualizzare la versione di cui è stato eseguito il rendering del codice precedente nella [documentazione dell'API per la funzione `ControlledOnBitString`](xref:microsoft.quantum.canon.controlledonbitstring).</span><span class="sxs-lookup"><span data-stu-id="f1dcb-145">You can see the rendered version of the code above in the [API documentation for the `ControlledOnBitString` function](xref:microsoft.quantum.canon.controlledonbitstring).</span></span>

<span data-ttu-id="f1dcb-146">Oltre alla pratica generale della scrittura della documentazione, per la scrittura di commenti sulla documentazione dell'API è utile tenere presenti alcuni aspetti:</span><span class="sxs-lookup"><span data-stu-id="f1dcb-146">In addition to the general practice of documentation writing, in writing API documentation comments it helps to keep a few things in mind:</span></span>

- <span data-ttu-id="f1dcb-147">Il formato di ogni commento sulla documentazione deve corrispondere a quello previsto dal compilatore Q # per visualizzare correttamente la documentazione.</span><span class="sxs-lookup"><span data-stu-id="f1dcb-147">The format of each documentation comment has to match what the Q# compiler expects for your documentation to appear correctly.</span></span> <span data-ttu-id="f1dcb-148">Alcune sezioni, ad esempio `/// # Remarks` consentono contenuto a mano libera, mentre le sezioni come `/// # See Also` sezione sono più restrittive.</span><span class="sxs-lookup"><span data-stu-id="f1dcb-148">Some sections, such as `/// # Remarks` allow for freeform content, while sections such as `/// # See Also` section are more restrictive.</span></span>
- <span data-ttu-id="f1dcb-149">Un lettore può leggere la documentazione dell'API nel sito di riferimento dell'API principale, nel riepilogo per ogni spazio dei nomi o anche all'interno dell'IDE usando le informazioni sul passaggio del mouse.</span><span class="sxs-lookup"><span data-stu-id="f1dcb-149">A reader may read your API documentation on the main API reference site, on the summary for each namespace, or even from within their IDE through the use of hover information.</span></span> <span data-ttu-id="f1dcb-150">Assicurandosi che il `/// # Summary` non sia più lungo di una frase, consente al lettore di determinare rapidamente se è necessario leggere ulteriormente o cercare altrove e può aiutare a eseguire rapidamente l'analisi tramite riepiloghi dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="f1dcb-150">Making sure that `/// # Summary` isn't longer than about a sentence helps your reader quickly sort out whether they need to read further or look elsewhere, and can help in quickly scanning through namespace summaries.</span></span>
- <span data-ttu-id="f1dcb-151">La documentazione potrebbe essere molto più lunga del codice, ma è accettabile.</span><span class="sxs-lookup"><span data-stu-id="f1dcb-151">Your documentation may well wind up being much longer than the code itself, but that's OK!</span></span> <span data-ttu-id="f1dcb-152">Anche una piccola parte di codice può avere effetti imprevisti per gli utenti che non conoscono il contesto in cui tale codice esiste.</span><span class="sxs-lookup"><span data-stu-id="f1dcb-152">Even a small piece of code can have unexpected effects to users that don't know the context in which that code exists.</span></span> <span data-ttu-id="f1dcb-153">Fornendo esempi concreti e spiegazioni chiare, è possibile aiutare gli utenti a sfruttare al meglio il codice disponibile.</span><span class="sxs-lookup"><span data-stu-id="f1dcb-153">By providing concrete examples and clear explanations, you can help users make the best use of the code that's available to them.</span></span>

<!-- ## LaTeX Formatting ##

**TODO** -->
