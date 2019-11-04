---
title: 'Guida di stile Q # | Microsoft Docs'
description: 'Guida di stile Q #'
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.style
ms.openlocfilehash: 4050e2ee9e516aed7a8ba1398792562926808ee0
ms.sourcegitcommit: c93fea5980d1d46fbda1e7c7153831b9337134bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73463316"
---
# <a name="q-style-guide"></a><span data-ttu-id="3fb5a-103">Guida di stile Q #</span><span class="sxs-lookup"><span data-stu-id="3fb5a-103">Q# Style Guide</span></span> #
## <a name="general-conventions"></a><span data-ttu-id="3fb5a-104">Convenzioni generali</span><span class="sxs-lookup"><span data-stu-id="3fb5a-104">General Conventions</span></span> ##

<span data-ttu-id="3fb5a-105">Le convenzioni suggerite in questa guida hanno lo scopo di semplificare la lettura e la comprensione dei programmi e delle librerie scritte in Q #.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-105">The conventions suggested in this guide are intended to help make programs and libraries written in Q# easier to read and understand.</span></span>

## <a name="guidance"></a><span data-ttu-id="3fb5a-106">Guida</span><span class="sxs-lookup"><span data-stu-id="3fb5a-106">Guidance</span></span>

<span data-ttu-id="3fb5a-107">È consigliabile:</span><span class="sxs-lookup"><span data-stu-id="3fb5a-107">We suggest:</span></span>

- <span data-ttu-id="3fb5a-108">Non ignorare mai una convenzione, a meno che non lo si stia intenzionalmente per fornire codice più leggibile e comprensibile per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-108">Never disregard a convention unless you’re doing so intentionally in order to provide more readable and understandable code for your users.</span></span>

## <a name="naming-conventions"></a><span data-ttu-id="3fb5a-109">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="3fb5a-109">Naming Conventions</span></span> ##

<span data-ttu-id="3fb5a-110">Nell'offerta del quantum Development Kit, ci impegniamo per i nomi di funzione e di operazione che aiutano gli sviluppatori di Quantum a scrivere programmi facili da leggere e che riducono al minimo le sorprese.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-110">In offering the Quantum Development Kit, we strive for function and operation names that help quantum developers write programs that are easy to read and that minimize surprise.</span></span>
<span data-ttu-id="3fb5a-111">Una parte importante di questo è che quando si scelgono i nomi di funzioni, operazioni e tipi, viene stabilito il *vocabolario* usato dai programmatori per esprimere i concetti quantistici; con le nostre scelte, Microsoft li aiuta o li ostacola nel tentativo di comunicare chiaramente.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-111">An important part of that is that when we choose names for functions, operations, and types, we are establishing the *vocabulary* that programmers use to express quantum concepts; with our choices, we either help or hinder them in their effort to clearly communicate.</span></span>
<span data-ttu-id="3fb5a-112">In questo modo si ha la responsabilità di assicurarsi che i nomi introdotti offrano una maggiore chiarezza piuttosto che l'oscurità.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-112">This places a responsibility on us to make sure that the names we introduce offer clarity rather than obscurity.</span></span>
<span data-ttu-id="3fb5a-113">In questa sezione viene illustrato in dettaglio il modo in cui viene rispettato questo impegno in termini di linee guida esplicite che consentono di sfruttare al meglio la community di sviluppo Q #.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-113">In this section, we detail how we meet this obligation in terms of explicit guidance that helps us do the best by the Q# development community.</span></span>

### <a name="operations-and-functions"></a><span data-ttu-id="3fb5a-114">Operazioni e funzioni</span><span class="sxs-lookup"><span data-stu-id="3fb5a-114">Operations and Functions</span></span> ###

<span data-ttu-id="3fb5a-115">Una delle prime cose che un nome deve stabilire è se un simbolo specificato rappresenta una funzione o un'operazione.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-115">One of the first things that a name should establish is whether a given symbol represents a function or an operation.</span></span>
<span data-ttu-id="3fb5a-116">La differenza tra funzioni e operazioni è fondamentale per comprendere il comportamento di un blocco di codice.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-116">The difference between functions and operations is critical to understanding how a block of code behaves.</span></span>
<span data-ttu-id="3fb5a-117">Per comunicare la distinzione tra funzioni e operazioni per gli utenti, si fa affidamento su tale operazione per i modelli Q #, usando gli effetti collaterali.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-117">To communicate the distinction between functions and operations to users, we rely on that Q# models quantum operations through the use of side effects.</span></span>
<span data-ttu-id="3fb5a-118">Ovvero, un'operazione *esegue* un'operazione.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-118">That is, an operation *does* something.</span></span>

<span data-ttu-id="3fb5a-119">Al contrario, le funzioni descrivono le relazioni matematiche tra i dati.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-119">By contrast, functions describe the mathematical relationships between data.</span></span>
<span data-ttu-id="3fb5a-120">L'espressione `Sin(PI() / 2.0)` *è* `1.0`e non implica nulla sullo stato di un programma o della relativa qubits.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-120">The expression `Sin(PI() / 2.0)` *is* `1.0`, and implies nothing about the state of a program or its qubits.</span></span>

<span data-ttu-id="3fb5a-121">Riepilogando, le operazioni eseguono attività mentre le funzioni.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-121">Summarizing, operations do things while functions are things.</span></span>
<span data-ttu-id="3fb5a-122">Questa distinzione suggerisce che le operazioni vengono denominate come verbi e funzioni come sostantivi.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-122">This distinction suggests that we name operations as verbs and functions as nouns.</span></span>

> [!NOTE]
> <span data-ttu-id="3fb5a-123">Quando viene dichiarato un tipo definito dall'utente, una nuova funzione che costruisce istanze di quel tipo viene definita in modo implicito nello stesso momento.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-123">When a user-defined type is declared, a new function that constructs instances of that type is implicitly defined at the same time.</span></span>
> <span data-ttu-id="3fb5a-124">Da tale prospettiva, i tipi definiti dall'utente devono essere denominati come sostantivi, in modo che sia il tipo stesso che la funzione del costruttore abbiano nomi coerenti.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-124">From that perspective, user-defined types should be named as nouns so that both the type itself and the constructor function have consistent names.</span></span>

<span data-ttu-id="3fb5a-125">Se ragionevole, assicurarsi che i nomi delle operazioni inizino con verbi che indicano chiaramente l'effetto ottenuto dall'operazione.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-125">Where reasonable, ensure that operation names begin with verbs that clearly indicate the effect taken by the operation.</span></span>
<span data-ttu-id="3fb5a-126">ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3fb5a-126">For example:</span></span>

- `MeasureInteger`
- `EstimateEnergy`
- `SampleInt`

<span data-ttu-id="3fb5a-127">Un caso che merita una menzione speciale è quando un'operazione accetta un'altra operazione come input e la chiama.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-127">One case that deserves special mention is when an operation takes another operation as input and calls it.</span></span>
<span data-ttu-id="3fb5a-128">In questi casi, l'azione eseguita dall'operazione di input non è chiara quando viene definita l'operazione esterna, in modo che il verbo destro non sia immediatamente chiaro.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-128">In such cases, the action taken by the input operation is not clear when the outer operation is defined, such that the right verb is not immediately clear.</span></span>
<span data-ttu-id="3fb5a-129">È consigliabile usare il verbo `Apply`, come in `ApplyIf`, `ApplyToEach`e `ApplyToFirst`.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-129">We recommend the verb `Apply`, as in `ApplyIf`, `ApplyToEach`, and `ApplyToFirst`.</span></span>
<span data-ttu-id="3fb5a-130">Anche altri verbi possono essere utili in questo caso, come in `IterateThroughCartesianPower`.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-130">Other verbs may be useful in this case as well, as in `IterateThroughCartesianPower`.</span></span>

| <span data-ttu-id="3fb5a-131">Verbo</span><span class="sxs-lookup"><span data-stu-id="3fb5a-131">Verb</span></span> | <span data-ttu-id="3fb5a-132">Effetto previsto</span><span class="sxs-lookup"><span data-stu-id="3fb5a-132">Expected Effect</span></span> |
| ---- | ------ |
| <span data-ttu-id="3fb5a-133">Richiesta</span><span class="sxs-lookup"><span data-stu-id="3fb5a-133">Apply</span></span> | <span data-ttu-id="3fb5a-134">Viene chiamata un'operazione fornita come input</span><span class="sxs-lookup"><span data-stu-id="3fb5a-134">An operation provided as input is called</span></span> |
| <span data-ttu-id="3fb5a-135">Assert</span><span class="sxs-lookup"><span data-stu-id="3fb5a-135">Assert</span></span> | <span data-ttu-id="3fb5a-136">Un'ipotesi sul risultato di una possibile misurazione quantistica viene controllata da un simulatore</span><span class="sxs-lookup"><span data-stu-id="3fb5a-136">A hypothesis about the outcome of a possible quantum measurement is checked by a simulator</span></span> |
| <span data-ttu-id="3fb5a-137">Estimate</span><span class="sxs-lookup"><span data-stu-id="3fb5a-137">Estimate</span></span> | <span data-ttu-id="3fb5a-138">Viene restituito un valore classico che rappresenta una stima disegnata da una o più misurazioni</span><span class="sxs-lookup"><span data-stu-id="3fb5a-138">A classical value is returned, representing an estimate drawn from one or more measurements</span></span> |
| <span data-ttu-id="3fb5a-139">Measure</span><span class="sxs-lookup"><span data-stu-id="3fb5a-139">Measure</span></span> | <span data-ttu-id="3fb5a-140">Viene eseguita una misurazione quantistica e il risultato viene restituito all'utente</span><span class="sxs-lookup"><span data-stu-id="3fb5a-140">A quantum measurement is performed, and its result is returned to the user</span></span> |
| <span data-ttu-id="3fb5a-141">Prepara</span><span class="sxs-lookup"><span data-stu-id="3fb5a-141">Prepare</span></span> | <span data-ttu-id="3fb5a-142">Un registro specificato di qubits viene inizializzato in uno stato specifico</span><span class="sxs-lookup"><span data-stu-id="3fb5a-142">A given register of qubits is initialized into a particular state</span></span> |
| <span data-ttu-id="3fb5a-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="3fb5a-143">Sample</span></span> | <span data-ttu-id="3fb5a-144">Un valore classico viene restituito in modo casuale da una distribuzione</span><span class="sxs-lookup"><span data-stu-id="3fb5a-144">A classical value is returned at random from some distribution</span></span> |

<span data-ttu-id="3fb5a-145">Per le funzioni, è consigliabile evitare l'uso di verbi a favore dei sostantivi comuni (vedere le linee guida sui sostantivi appropriati sotto) o sugli aggettivi:</span><span class="sxs-lookup"><span data-stu-id="3fb5a-145">For functions, we suggest avoiding the use of verbs in favor of common nouns (see guidance on proper nouns below) or adjectives:</span></span>

- `ConstantArray`
- `Head`
- `LookupFunction`

<span data-ttu-id="3fb5a-146">In particolare, in quasi tutti i casi, è consigliabile usare participi precedenti, laddove appropriato, per indicare che un nome di funzione è fortemente connesso a un'azione o a un effetto collaterale in un'altra posizione in un programma Quantum.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-146">In particular, in almost all cases, we suggest using past participles where appropriate to indicate that a function name is strongly connected to an action or side effect elsewhere in a quantum program.</span></span>
<span data-ttu-id="3fb5a-147">Ad esempio, `ControlledOnInt` usa il formato participio della parte del verbo "Control" per indicare che la funzione funge da aggettivo per modificare il relativo argomento.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-147">For example,  `ControlledOnInt` uses the part participle form of the verb "control" to indicate that the function acts as an adjective to modify its argument.</span></span>
<span data-ttu-id="3fb5a-148">Questo nome presenta il vantaggio aggiuntivo di abbinare la semantica del `Controlled` functore incorporato, come illustrato più avanti.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-148">This name has the additional benefit of matching the semantics of the built-in `Controlled` functor, as discussed further below.</span></span>
<span data-ttu-id="3fb5a-149">Analogamente, è possibile usare i _sostantivi di Agent_ per costruire nomi di funzioni e UDT da nomi di operazione, come nel caso del nome `Encoder` per un tipo definito dall'utente che è strettamente associato al `Encode`.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-149">Similarly, _agent nouns_ can be used to construct function and UDT names from operation names, as in the case of the name `Encoder` for a UDT that is strongly associated with `Encode`.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="3fb5a-150">Materiale sussidiario</span><span class="sxs-lookup"><span data-stu-id="3fb5a-150">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="3fb5a-151">È consigliabile:</span><span class="sxs-lookup"><span data-stu-id="3fb5a-151">We suggest:</span></span>

- <span data-ttu-id="3fb5a-152">Usare i verbi per i nomi delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-152">Use verbs for operation names.</span></span>
- <span data-ttu-id="3fb5a-153">Utilizzare sostantivi o aggettivi per i nomi di funzione.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-153">Use nouns or adjectives for function names.</span></span>
- <span data-ttu-id="3fb5a-154">Usare i sostantivi per i tipi e gli attributi definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-154">Use nouns for user-defined types and attributes.</span></span>
- <span data-ttu-id="3fb5a-155">Per tutti i nomi chiamabili, usare `CamelCase` in una preferenza sicura per `pascalCase`, `snake_case`o `ANGRY_CASE`.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-155">For all callable names, use `CamelCase` in strong preference to `pascalCase`, `snake_case`, or `ANGRY_CASE`.</span></span> <span data-ttu-id="3fb5a-156">In particolare, assicurarsi che i nomi richiamabili inizino con lettere maiuscole.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-156">In particular, ensure that callable names start with uppercase letters.</span></span>
- <span data-ttu-id="3fb5a-157">Per tutte le variabili locali, utilizzare `pascalCase` di preferenza forte per `CamelCase`, `snake_case`o `ANGRY_CASE`.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-157">For all local variables, use `pascalCase` in strong preference to `CamelCase`, `snake_case`, or `ANGRY_CASE`.</span></span> <span data-ttu-id="3fb5a-158">In particolare, assicurarsi che le variabili locali inizino con lettere minuscole.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-158">In particular, ensure that local variables start with lowercase letters.</span></span>
- <span data-ttu-id="3fb5a-159">Evitare l'uso di caratteri di sottolineatura `_` nei nomi delle funzioni e delle operazioni; laddove sono necessari livelli aggiuntivi di gerarchia, usare gli spazi dei nomi e gli alias degli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-159">Avoid the use of underscores `_` in function and operation names; where additional levels of hierarchy are needed, use namespaces and namespace aliases.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="3fb5a-160">esempi</span><span class="sxs-lookup"><span data-stu-id="3fb5a-160">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="3fb5a-161">name</span><span class="sxs-lookup"><span data-stu-id="3fb5a-161">Name</span></span> | <span data-ttu-id="3fb5a-162">Description</span><span class="sxs-lookup"><span data-stu-id="3fb5a-162">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="3fb5a-163">☑</span><span class="sxs-lookup"><span data-stu-id="3fb5a-163">☑</span></span> | `operation ReflectAboutStart` | <span data-ttu-id="3fb5a-164">Cancellazione dell'utilizzo di un verbo ("Reflect") per indicare l'effetto dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-164">Clear use of a verb ("reflect") to indicate the effect of the operation.</span></span> |
| <span data-ttu-id="3fb5a-165">☒</span><span class="sxs-lookup"><span data-stu-id="3fb5a-165">☒</span></span> | <s>`operation XRotation`</s> | <span data-ttu-id="3fb5a-166">L'uso della frase nominale suggerisce la funzione, anziché l'operazione.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-166">Use of noun phrase suggests function, rather than operation.</span></span> |
| <span data-ttu-id="3fb5a-167">☒</span><span class="sxs-lookup"><span data-stu-id="3fb5a-167">☒</span></span> | <s>`operation search_oracle`</s> | <span data-ttu-id="3fb5a-168">L'uso di `snake_case` in contrasto con la notazione Q #.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-168">Use of `snake_case` contravenes Q# notation.</span></span> |
| <span data-ttu-id="3fb5a-169">☒</span><span class="sxs-lookup"><span data-stu-id="3fb5a-169">☒</span></span> | <s>`operation Search_Oracle`</s> | <span data-ttu-id="3fb5a-170">L'uso di caratteri di sottolineatura interni al nome dell'operazione è in funzione della notazione Q #.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-170">Use of underscores internal to operation name contravenes Q# notation.</span></span> |
| <span data-ttu-id="3fb5a-171">☑</span><span class="sxs-lookup"><span data-stu-id="3fb5a-171">☑</span></span> | `function StatePreparationOracle` | <span data-ttu-id="3fb5a-172">L'uso della frase nominale suggerisce che la funzione restituisce un'operazione.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-172">Use of noun phrase suggests that the function returns an operation.</span></span> |
| <span data-ttu-id="3fb5a-173">☑</span><span class="sxs-lookup"><span data-stu-id="3fb5a-173">☑</span></span> | `function EqualityFact` | <span data-ttu-id="3fb5a-174">Uso chiaro del sostantivo ("fact") per indicare che si tratta di una funzione, mentre l'aggettivo.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-174">Clear use of noun ("fact") to indicate that this is a function, while the adjective.</span></span> |
| <span data-ttu-id="3fb5a-175">☒</span><span class="sxs-lookup"><span data-stu-id="3fb5a-175">☒</span></span> | <s>`function GetRotationAngles`</s> | <span data-ttu-id="3fb5a-176">L'uso del verbo ("Get") suggerisce che si tratta di un'operazione.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-176">Use of verb ("get") suggests that this is an operation.</span></span> |
| <span data-ttu-id="3fb5a-177">☑</span><span class="sxs-lookup"><span data-stu-id="3fb5a-177">☑</span></span> | `newtype GeneratorTerm` | <span data-ttu-id="3fb5a-178">L'uso della frase nominale indica chiaramente il risultato della chiamata al costruttore del tipo definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-178">Use of noun phrase clearly refers to the result of calling the UDT constructor.</span></span> |
| <span data-ttu-id="3fb5a-179">☒</span><span class="sxs-lookup"><span data-stu-id="3fb5a-179">☒</span></span> | <s>`@Attribute() newtype RunOnce()`</s> | <span data-ttu-id="3fb5a-180">L'uso della frase verbo suggerisce che il costruttore del tipo definito dall'utente è un'operazione.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-180">Use of verb phrase suggests that the UDT constructor is an operation.</span></span> |
| <span data-ttu-id="3fb5a-181">☑</span><span class="sxs-lookup"><span data-stu-id="3fb5a-181">☑</span></span> | `@Attribute() newtype Deprecated(Reason : String)` | <span data-ttu-id="3fb5a-182">L'uso di sintagma sostantivo comunica l'uso dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-182">Use of noun phrase communicates the use of the attribute.</span></span> |

***

### <a name="shorthand-and-abbreviations"></a><span data-ttu-id="3fb5a-183">Abbreviazione e abbreviazioni</span><span class="sxs-lookup"><span data-stu-id="3fb5a-183">Shorthand and Abbreviations</span></span> ###

<span data-ttu-id="3fb5a-184">Il Consiglio precedente, tuttavia, è costituito da molte forme di abbreviazione che vedono un uso comune e dilagante in quantum computing.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-184">The above advice notwithstanding, there are many forms of shorthand that see common and pervasive use in quantum computing.</span></span>
<span data-ttu-id="3fb5a-185">Si consiglia di usare l'abbreviazione esistente e comune in cui è presente, in particolare per le operazioni intrinseche al funzionamento di un computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-185">We suggest using existing and common shorthand where it exists, especially for operations that are intrinsic to the operation of a target machine.</span></span>
<span data-ttu-id="3fb5a-186">Si sceglie, ad esempio, il nome `X` anziché `ApplyX`e `Rz` anziché `RotateAboutZ`.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-186">For example, we choose the name `X` instead of `ApplyX`, and `Rz` instead of `RotateAboutZ`.</span></span>
<span data-ttu-id="3fb5a-187">Quando si utilizza tale sintassi, i nomi delle operazioni devono essere tutti in maiuscolo, ad esempio `MAJ`.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-187">When using such shorthand, operation names should be all uppercase (e.g.: `MAJ`).</span></span>

<span data-ttu-id="3fb5a-188">È necessario prestare attenzione quando si applica questa convenzione nel caso degli acronimi usati comunemente e acronimi, ad esempio "QFT" per "Quantum Fourier Transform".</span><span class="sxs-lookup"><span data-stu-id="3fb5a-188">Some care is required when applying this convention in the case of commonly used acronyms and initialisms such as "QFT" for "quantum Fourier transform."</span></span>
<span data-ttu-id="3fb5a-189">Si consiglia di seguire le convenzioni .NET generali per l'uso di acronimi e acronimi nei nomi completi, che prevedono che:</span><span class="sxs-lookup"><span data-stu-id="3fb5a-189">We suggest following general .NET conventions for the use of acronyms and initialisms in full names, which prescribe that:</span></span>

- <span data-ttu-id="3fb5a-190">gli acronimi di due lettere e acronimi sono denominati in lettere maiuscole, ad esempio `BE` per "big-endian",</span><span class="sxs-lookup"><span data-stu-id="3fb5a-190">two-letter acronyms and initialisms are named in upper case (e.g.: `BE` for "big-endian"),</span></span>
- <span data-ttu-id="3fb5a-191">tutti gli acronimi e acronimi più lunghi sono denominati in `CamelCase`, ad esempio `Qft` per "Quantum Fourier Transform".</span><span class="sxs-lookup"><span data-stu-id="3fb5a-191">all longer acronyms and initialisms are named in `CamelCase` (e.g.: `Qft` for "quantum Fourier transform")</span></span>

<span data-ttu-id="3fb5a-192">Pertanto, un'operazione che implementa QFT può essere chiamata `QFT` come sintassi abbreviata o scritta come `ApplyQft`.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-192">Thus, an operation implementing the QFT could either be called `QFT` as shorthand, or written out as `ApplyQft`.</span></span>

<span data-ttu-id="3fb5a-193">Per le operazioni e le funzioni di uso più comune, può essere utile fornire un nome abbreviato come _alias_ per una forma più lunga:</span><span class="sxs-lookup"><span data-stu-id="3fb5a-193">For particularly commonly used operations and functions, it may be desirable to provide a shorthand name as an _alias_ for a longer form:</span></span>

```qsharp
operation CCNOT(control0 : Qubit, control1 : Qubit, target : Qubit)
is Adj + Ctl {
    Controlled X([control0, control1], target);
}
```

# <a name="guidancetabguidance"></a>[<span data-ttu-id="3fb5a-194">Materiale sussidiario</span><span class="sxs-lookup"><span data-stu-id="3fb5a-194">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="3fb5a-195">È consigliabile:</span><span class="sxs-lookup"><span data-stu-id="3fb5a-195">We suggest:</span></span>

- <span data-ttu-id="3fb5a-196">Prendere in considerazione nomi abbreviati comunemente accettati e ampiamente usati quando appropriato.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-196">Consider commonly accepted and widely used shorthand names when appropriate.</span></span>
- <span data-ttu-id="3fb5a-197">Usare maiuscole per la sintassi abbreviata.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-197">Use uppercase for shorthand.</span></span>
- <span data-ttu-id="3fb5a-198">Usare i caratteri maiuscoli per gli acronimi Short (Two-Letter) e acronimi.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-198">Use uppercase for short (two-letter) acronyms and initialisms.</span></span>
- <span data-ttu-id="3fb5a-199">Usare `CamelCase` per gli acronimi più lunghi (tre o più lettere) e acronimi.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-199">Use `CamelCase` for longer (three or more letter) acronyms and initialisms.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="3fb5a-200">esempi</span><span class="sxs-lookup"><span data-stu-id="3fb5a-200">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="3fb5a-201">name</span><span class="sxs-lookup"><span data-stu-id="3fb5a-201">Name</span></span> | <span data-ttu-id="3fb5a-202">Description</span><span class="sxs-lookup"><span data-stu-id="3fb5a-202">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="3fb5a-203">☑</span><span class="sxs-lookup"><span data-stu-id="3fb5a-203">☑</span></span> | `X` | <span data-ttu-id="3fb5a-204">Abbreviazione ben riconosciuta per "applicare una $X $ Transformation"</span><span class="sxs-lookup"><span data-stu-id="3fb5a-204">Well-understood shorthand for "apply an $X$ transformation"</span></span> |
| <span data-ttu-id="3fb5a-205">☑</span><span class="sxs-lookup"><span data-stu-id="3fb5a-205">☑</span></span> | `CNOT` | <span data-ttu-id="3fb5a-206">Abbreviazione ben riconosciuta per "controllato-NOT"</span><span class="sxs-lookup"><span data-stu-id="3fb5a-206">Well-understood shorthand for "controlled-NOT"</span></span> |
| <span data-ttu-id="3fb5a-207">☒</span><span class="sxs-lookup"><span data-stu-id="3fb5a-207">☒</span></span> | <s>`Cnot`</s> | <span data-ttu-id="3fb5a-208">La sintassi abbreviata non dovrebbe essere in `CamelCase`.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-208">Shorthand should not be in `CamelCase`.</span></span> |
| <span data-ttu-id="3fb5a-209">☑</span><span class="sxs-lookup"><span data-stu-id="3fb5a-209">☑</span></span> | `ApplyQft` | <span data-ttu-id="3fb5a-210">L'iniziale comune "QFT" viene visualizzato come parte di un nome di tipo esteso.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-210">Common initialism "QFT" appears as a part of a long-form name.</span></span> |
| <span data-ttu-id="3fb5a-211">☑</span><span class="sxs-lookup"><span data-stu-id="3fb5a-211">☑</span></span> | `QFT` | <span data-ttu-id="3fb5a-212">Il valore iniziale comune "QFT" viene visualizzato come parte di un nome abbreviato.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-212">Common initialism "QFT" appears as a part of a shorthand name.</span></span> |



***


### <a name="proper-nouns-in-names"></a><span data-ttu-id="3fb5a-213">Sostantivi appropriati nei nomi</span><span class="sxs-lookup"><span data-stu-id="3fb5a-213">Proper Nouns in Names</span></span> ###

<span data-ttu-id="3fb5a-214">Nella fisica è comune denominare gli elementi dopo la prima persona a pubblicarli, la maggior parte dei non fisici non ha familiarità con i nomi di tutti gli utenti e tutta la cronologia.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-214">While in physics it is common to name things after the first person to publish about them, most non-physicists aren’t familiar with everyone’s names and all of the history.</span></span>
<span data-ttu-id="3fb5a-215">Basandosi troppo sulle convenzioni di denominazione della fisica, può quindi costituire un ostacolo sostanziale alla voce, in quanto gli utenti di altri background devono apprendere un numero elevato di nomi apparentemente opachi per poter utilizzare le operazioni e i concetti comuni.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-215">Relying too heavily on naming conventions from physics can thus put up a substantial barrier to entry, as users from other backgrounds must learn a large number of seemingly opaque names in order to use common operations and concepts.</span></span>
<!-- An important part of the task of reducing confusion is to make code more accessible.
Especially in a field such as quantum computing that is rich with domain expertise, we must at all times be cognizant of the demands we place on that expertise as we design quantum software.
In naming code symbols, one way that this cognizance expresses itself is as an awareness of the convention from physics of adopting as the names of algorithms and operations the names of their original publishers.
While we must maintain the history and intellectual provenance of concepts in quantum computing, demanding that all users be versed in this history to use even the most basic of functions and operations places a barrier to entry that is in most cases severe enough to even present an ethical compromise. -->
<span data-ttu-id="3fb5a-216">Pertanto, si consiglia di adottare tutti i sostantivi comuni che descrivono un concetto con una preferenza forte ai sostantivi appropriati che descrivono la cronologia delle pubblicazioni di un concetto.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-216">Thus, we recommend that wherever reasonable, common nouns that describe a concept be adopted in strong preference to proper nouns that describe the publication history of a concept.</span></span>
<span data-ttu-id="3fb5a-217">Come un particolare esempio, le operazioni di scambio e doppia controllo singolarmente controllate sono spesso denominate "Fredkin" e "Toffoli" in letteratura accademica, ma sono identificate in Q # principalmente come `CSWAP` e `CCNOT`.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-217">As a particular example, the singly controlled SWAP and doubly controlled NOT operations are often called the "Fredkin" and "Toffoli" operations in academic literature, but are identified in Q# primarily as `CSWAP` and `CCNOT`.</span></span>
<span data-ttu-id="3fb5a-218">In entrambi i casi, i commenti relativi alla documentazione dell'API forniscono nomi sinonimi in base a sostantivi appropriati, insieme a tutte le citazioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-218">In both cases, the API documentation comments provide synonymous names based on proper nouns, along with all appropriate citations.</span></span>

<span data-ttu-id="3fb5a-219">Questa preferenza è particolarmente importante, dato che l'uso dei sostantivi appropriati sarà sempre necessario: Q # segue la tradizione impostata da molti linguaggi classici, ad esempio, e fa riferimento a `Bool` tipi in riferimento alla logica booleana, che è a sua volta denominata in onore di George Boole.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-219">This preference is especially important given that some usage of proper nouns will always be necessary — Q# follows the tradition set by many classical languages, for instance, and refers to `Bool` types in reference to Boolean logic, which is in turn named in honor of George Boole.</span></span>
<span data-ttu-id="3fb5a-220">Alcuni concetti di quantum vengono denominati in modo simile, incluso il tipo `Pauli` incorporato nel linguaggio Q #.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-220">A few quantum concepts similarly are named in a similar fashion, including the `Pauli` type built-in to the Q# language.</span></span>
<span data-ttu-id="3fb5a-221">Riducendo al minimo l'utilizzo dei sostantivi appropriati in cui tale utilizzo non è essenziale, viene ridotto l'effetto in cui i sostantivi appropriati non possono essere ragionevolmente evitati.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-221">By minimizing the usage of proper nouns where such usage is not essential, we reduce the impact where proper nouns cannot be reasonably avoided.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="3fb5a-222">Materiale sussidiario</span><span class="sxs-lookup"><span data-stu-id="3fb5a-222">Guidance</span></span>](#tab/guidance) 

<span data-ttu-id="3fb5a-223">È consigliabile:</span><span class="sxs-lookup"><span data-stu-id="3fb5a-223">We suggest:</span></span>

- <span data-ttu-id="3fb5a-224">Evitare l'uso di sostantivi appropriati nei nomi.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-224">Avoid the use of proper nouns in names.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="3fb5a-225">esempi</span><span class="sxs-lookup"><span data-stu-id="3fb5a-225">Examples</span></span>](#tab/examples)

***

### <a name="type-conversions"></a><span data-ttu-id="3fb5a-226">Conversioni di tipi</span><span class="sxs-lookup"><span data-stu-id="3fb5a-226">Type Conversions</span></span> ###

<span data-ttu-id="3fb5a-227">Poiché Q # è un linguaggio fortemente tipizzato in modo statico, un valore di un tipo può essere usato solo come valore di un altro tipo usando una chiamata esplicita a una funzione di conversione del tipo.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-227">Since Q# is a strongly and staticly typed language, a value of one type can only be used as a value of another type by using an explicit call to a type conversion function.</span></span>
<span data-ttu-id="3fb5a-228">Si tratta di un contrasto rispetto ai linguaggi che consentono di modificare i tipi in modo implicito, ad esempio promozione del tipo, o tramite cast.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-228">This is in contrast to languages which allow for values to change types implicitly (e.g.: type promotion), or through casting.</span></span>
<span data-ttu-id="3fb5a-229">Di conseguenza, le funzioni di conversione dei tipi svolgono un ruolo importante nello sviluppo di una libreria Q # e comprendono una delle decisioni più comunemente rilevate per la denominazione.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-229">As a result, type conversion functions play an important role in Q# library development, and comprise one of the more commonly encountered decisions about naming.</span></span>
<span data-ttu-id="3fb5a-230">Si noti, tuttavia, che poiché le conversioni di tipi sono sempre _deterministiche_, possono essere scritte come funzioni e quindi rientrare nei consigli precedenti.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-230">We note, however, that since type conversions are always _deterministic_, they can be written as functions and thus fall under the advice above.</span></span>
<span data-ttu-id="3fb5a-231">In particolare, è consigliabile che le funzioni di conversione dei tipi non vengano mai denominate come verbi (ad esempio, `ConvertToX`) o frasi preposizionali avverbi (`ToX`), ma devono essere denominate come frasi preposizionali aggettivali che indicano i tipi di origine e destinazione (`XAsY`).</span><span class="sxs-lookup"><span data-stu-id="3fb5a-231">In particular, we suggest that type conversion functions should never be named as verbs (e.g.: `ConvertToX`) or adverb prepositional phrases (`ToX`), but should be named as adjective prepositional phrases that indicate the source and destination types (`XAsY`).</span></span>
<span data-ttu-id="3fb5a-232">Quando si elencano i tipi di matrici nei nomi delle funzioni di conversione del tipo, è consigliabile `Arr`abbreviazione.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-232">When listing array types in type conversion function names, we recommend the shorthand `Arr`.</span></span>
<span data-ttu-id="3fb5a-233">Salvo circostanze eccezionali, è consigliabile denominare tutte le funzioni di conversione del tipo utilizzando `As` in modo che possano essere identificate rapidamente.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-233">Barring exceptional circumstances, we recommend that all type conversion functions be named using `As` so that they can be quickly identified.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="3fb5a-234">Materiale sussidiario</span><span class="sxs-lookup"><span data-stu-id="3fb5a-234">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="3fb5a-235">È consigliabile:</span><span class="sxs-lookup"><span data-stu-id="3fb5a-235">We suggest:</span></span>

- <span data-ttu-id="3fb5a-236">Se una funzione converte un valore di tipo `X` in un valore di tipo `Y`, utilizzare il nome `AsY` o `XAsY`.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-236">If a function converts a value of type `X` to a value of type `Y`, use either the name `AsY` or `XAsY`.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="3fb5a-237">esempi</span><span class="sxs-lookup"><span data-stu-id="3fb5a-237">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="3fb5a-238">name</span><span class="sxs-lookup"><span data-stu-id="3fb5a-238">Name</span></span> | <span data-ttu-id="3fb5a-239">Description</span><span class="sxs-lookup"><span data-stu-id="3fb5a-239">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="3fb5a-240">☒</span><span class="sxs-lookup"><span data-stu-id="3fb5a-240">☒</span></span> | <s>`ToDouble`</s> | <span data-ttu-id="3fb5a-241">La preposizione "to" restituisce una frase verbo, che indica un'operazione e non una funzione.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-241">The preposition "to" results in a verb phrase, indicating an operation and not a function.</span></span> |
| <span data-ttu-id="3fb5a-242">☒</span><span class="sxs-lookup"><span data-stu-id="3fb5a-242">☒</span></span> | <s>`AsDouble`</s> | <span data-ttu-id="3fb5a-243">Il tipo di input non è chiaro dal nome della funzione.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-243">The input type is not clear from the function name.</span></span> |
| <span data-ttu-id="3fb5a-244">☒</span><span class="sxs-lookup"><span data-stu-id="3fb5a-244">☒</span></span> | <s>`PauliArrFromBoolArr`</s> | <span data-ttu-id="3fb5a-245">I tipi di input e di output vengono visualizzati nell'ordine errato.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-245">The input and output types appear in the wrong order.</span></span> |
| <span data-ttu-id="3fb5a-246">☑</span><span class="sxs-lookup"><span data-stu-id="3fb5a-246">☑</span></span> | `ResultArrAsBoolArr` | <span data-ttu-id="3fb5a-247">I tipi di input e di output sono entrambi chiari.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-247">Both the input types and output types are clear.</span></span> |

***

### <a name="private-or-internal-names"></a><span data-ttu-id="3fb5a-248">Nomi privati o interni</span><span class="sxs-lookup"><span data-stu-id="3fb5a-248">Private or Internal Names</span></span> ###

<span data-ttu-id="3fb5a-249">In molti casi, un nome è destinato esclusivamente all'uso interno a una libreria o a un progetto e non è una parte garantita dell'API offerta da una libreria.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-249">In many cases, a name is intended strictly for use internal to a library or project, and is not a guaranteed part of the API offered by a library.</span></span>
<span data-ttu-id="3fb5a-250">È utile indicare chiaramente che questa situazione si verifica quando si denominano funzioni e operazioni in modo che le dipendenze accidentali sul codice solo interno siano rese evidenti.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-250">It is helpful to clearly indicate that this is the case when naming functions and operations so that accidental dependencies on internal-only code are made obvious.</span></span>
<span data-ttu-id="3fb5a-251">Se un'operazione o una funzione non è destinata all'uso diretto, ma deve essere usata da un oggetto chiamabile corrispondente che agisce da applicazione parziale, provare a usare un nome che inizia con `_` per il richiamabile che viene applicato parzialmente.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-251">If an operation or function is not intended for direct use, but rather should be used by a matching callable which acts by partial application, consider using a name starting with `_` for the callable that is partially applied.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="3fb5a-252">Materiale sussidiario</span><span class="sxs-lookup"><span data-stu-id="3fb5a-252">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="3fb5a-253">È consigliabile:</span><span class="sxs-lookup"><span data-stu-id="3fb5a-253">We suggest:</span></span>

- <span data-ttu-id="3fb5a-254">Quando una funzione, un'operazione o un tipo definito dall'utente non fa parte dell'API pubblica per una libreria o un programma Q #, verificare che il nome inizi con un carattere di sottolineatura iniziale (`_`).</span><span class="sxs-lookup"><span data-stu-id="3fb5a-254">When a function, operation, or user-defined type is not a part of the public API for a Q# library or program, ensure that its name begins with a leading underscore (`_`).</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="3fb5a-255">esempi</span><span class="sxs-lookup"><span data-stu-id="3fb5a-255">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="3fb5a-256">name</span><span class="sxs-lookup"><span data-stu-id="3fb5a-256">Name</span></span> | <span data-ttu-id="3fb5a-257">Description</span><span class="sxs-lookup"><span data-stu-id="3fb5a-257">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="3fb5a-258">☒</span><span class="sxs-lookup"><span data-stu-id="3fb5a-258">☒</span></span> | <s>`ApplyDecomposedOperation_`</s> | <span data-ttu-id="3fb5a-259">Il carattere di sottolineatura `_` non deve essere visualizzato alla fine del nome.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-259">The underscore `_` should not appear at the end of the name.</span></span> |
| <span data-ttu-id="3fb5a-260">☑</span><span class="sxs-lookup"><span data-stu-id="3fb5a-260">☑</span></span> | `_ApplyDecomposedOperation` | <span data-ttu-id="3fb5a-261">Il carattere di sottolineatura `_` all'inizio indica chiaramente che questa operazione è solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-261">The underscore `_` at the beginning clearly indicates that this operation is for internal use only.</span></span> |

***

### <a name="variants"></a><span data-ttu-id="3fb5a-262">Varianti</span><span class="sxs-lookup"><span data-stu-id="3fb5a-262">Variants</span></span> ###

<span data-ttu-id="3fb5a-263">Anche se questa limitazione potrebbe non essere permanente nelle versioni future di Q #, è attualmente il caso che ci siano spesso gruppi di operazioni o funzioni correlate che si distinguono con i quali funtori gli input supportano o con i tipi concreti dei relativi argomenti.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-263">Though this limitation may not persist in future versions of Q#, it is presently the case that there will often be groups of related operations or functions that are distinguished by which functors their inputs support, or by the concrete types of their arguments.</span></span>
<span data-ttu-id="3fb5a-264">Questi gruppi possono essere distinti usando lo stesso nome radice, seguito da una o due lettere che indicano la relativa variante.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-264">These groups can be distinguished by using the same root name, followed by one or two letters that indicate its variant.</span></span>

| <span data-ttu-id="3fb5a-265">Suffisso</span><span class="sxs-lookup"><span data-stu-id="3fb5a-265">Suffix</span></span> | <span data-ttu-id="3fb5a-266">Significato</span><span class="sxs-lookup"><span data-stu-id="3fb5a-266">Meaning</span></span> |
|--------|---------|
| `A` | <span data-ttu-id="3fb5a-267">Input previsto per supportare `Adjoint`</span><span class="sxs-lookup"><span data-stu-id="3fb5a-267">Input expected to support `Adjoint`</span></span> |
| `C` | <span data-ttu-id="3fb5a-268">Input previsto per supportare `Controlled`</span><span class="sxs-lookup"><span data-stu-id="3fb5a-268">Input expected to support `Controlled`</span></span> |
| `CA` | <span data-ttu-id="3fb5a-269">Input previsto per supportare `Controlled` e `Adjoint`</span><span class="sxs-lookup"><span data-stu-id="3fb5a-269">Input expected to support `Controlled` and `Adjoint`</span></span> |
| `I` | <span data-ttu-id="3fb5a-270">Gli input o gli input sono di tipo `Int`</span><span class="sxs-lookup"><span data-stu-id="3fb5a-270">Input or inputs are of type `Int`</span></span> |
| `D` | <span data-ttu-id="3fb5a-271">Gli input o gli input sono di tipo `Double`</span><span class="sxs-lookup"><span data-stu-id="3fb5a-271">Input or inputs are of type `Double`</span></span> |
| `L` | <span data-ttu-id="3fb5a-272">Gli input o gli input sono di tipo `BigInt`</span><span class="sxs-lookup"><span data-stu-id="3fb5a-272">Input or inputs are of type `BigInt`</span></span> |

# <a name="guidancetabguidance"></a>[<span data-ttu-id="3fb5a-273">Materiale sussidiario</span><span class="sxs-lookup"><span data-stu-id="3fb5a-273">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="3fb5a-274">È consigliabile:</span><span class="sxs-lookup"><span data-stu-id="3fb5a-274">We suggest:</span></span>

- <span data-ttu-id="3fb5a-275">Se una funzione o un'operazione non è correlata a funzioni o operazioni simili da parte del supporto di tipi e functor degli input, non usare un suffisso.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-275">If a function or operation is not related to any similar functions or operations by the types and functor support of their inputs, do not use a suffix.</span></span>
- <span data-ttu-id="3fb5a-276">Se una funzione o un'operazione è correlata a funzioni o operazioni analoghe con i tipi e il supporto del functore degli input, usare i suffissi come nella tabella precedente per distinguere le varianti.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-276">If a function or operation is related to any similar functions or operations by the types and functor support of their inputs, use suffixes as in the table above to distinguish variants.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="3fb5a-277">esempi</span><span class="sxs-lookup"><span data-stu-id="3fb5a-277">Examples</span></span>](#tab/examples)

***

### <a name="arguments-and-variables"></a><span data-ttu-id="3fb5a-278">Argomenti e variabili</span><span class="sxs-lookup"><span data-stu-id="3fb5a-278">Arguments and Variables</span></span> ###

<span data-ttu-id="3fb5a-279">Uno degli obiettivi principali del codice Q # per una funzione o un'operazione è per facilitarne la lettura e la comprensione.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-279">A key goal of the Q# code for a function or operation is for it to be easily read and understood.</span></span>
<span data-ttu-id="3fb5a-280">Analogamente, i nomi degli input e degli argomenti di tipo devono comunicare come una funzione o un argomento verrà usato una volta specificati.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-280">Similarly, the names of inputs and type arguments should communicate how a function or argument will be used once provided.</span></span>


# <a name="guidancetabguidance"></a>[<span data-ttu-id="3fb5a-281">Materiale sussidiario</span><span class="sxs-lookup"><span data-stu-id="3fb5a-281">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="3fb5a-282">È consigliabile:</span><span class="sxs-lookup"><span data-stu-id="3fb5a-282">We suggest:</span></span>

- <span data-ttu-id="3fb5a-283">Per tutti i nomi di variabile e di input, usare `pascalCase` in una preferenza sicura per `CamelCase`, `snake_case`o `ANGRY_CASE`.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-283">For all variable and input names, use `pascalCase` in strong preference to `CamelCase`, `snake_case`, or `ANGRY_CASE`.</span></span>
- <span data-ttu-id="3fb5a-284">I nomi di input devono essere descrittivi; evitare uno o due nomi di lettere laddove possibile.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-284">Input names should be descriptive; avoid one or two letter names where possible.</span></span>
- <span data-ttu-id="3fb5a-285">Le operazioni e le funzioni che accettano esattamente un argomento di tipo devono indicare tale argomento di tipo per `T` quando il suo ruolo è ovvio.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-285">Operations and functions accepting exactly one type argument should denote that type argument by `T` when its role is obvious.</span></span>
- <span data-ttu-id="3fb5a-286">Se una funzione o un'operazione accetta più argomenti di tipo o se il ruolo di un solo argomento di tipo non è ovvio, provare a usare una parola maiuscola breve preceduta da `T` (ad esempio, `TOutput`) per ogni tipo.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-286">If a function or operation takes multiple type arguments, or if the role of a single type argument is not obvious, consider using a short capitalized word prefaced by `T` (e.g.: `TOutput`) for each type.</span></span>
- <span data-ttu-id="3fb5a-287">Non includere nomi di tipi in argomenti e nomi di variabili; Queste informazioni possono e devono essere fornite dall'ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-287">Do not include type names in argument and variable names; this information can and should be provided by your development environment.</span></span>
- <span data-ttu-id="3fb5a-288">Indica i tipi scalari in base ai nomi letterali (`flagQubit`) e ai tipi di matrice in base al plurale (`measResults`).</span><span class="sxs-lookup"><span data-stu-id="3fb5a-288">Denote scalar types by their literal names (`flagQubit`), and array types by a plural (`measResults`).</span></span>
  <span data-ttu-id="3fb5a-289">Per le matrici di qubits in particolare, provare a denotare tali tipi per `Register` in cui il nome fa riferimento a una sequenza di qubits strettamente correlati in qualche modo.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-289">For arrays of qubits in particular, consider denoting such types by `Register` where the name refers to a sequence of qubits that are closely related in some way.</span></span>
- <span data-ttu-id="3fb5a-290">Le variabili usate come indici nelle matrici devono iniziare con `idx` e devono essere singolari (ad esempio: `things[idxThing]`).</span><span class="sxs-lookup"><span data-stu-id="3fb5a-290">Variables used as indices into arrays should begin with `idx` and should be singular (e.g.: `things[idxThing]`).</span></span>
  <span data-ttu-id="3fb5a-291">In particolare, è consigliabile evitare di utilizzare nomi di variabili a lettera singola come indici. prendere in considerazione l'uso di `idx` come minimo.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-291">In particular, strongly avoid using single-letter variable names as indices; consider using `idx` at a minimum.</span></span>
- <span data-ttu-id="3fb5a-292">Le variabili usate per contenere lunghezze di matrici devono iniziare con `n` e devono essere plurali, ad esempio: `nThings`.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-292">Variables used to hold lengths of arrays should begin with `n` and should be pluralized (e.g.: `nThings`).</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="3fb5a-293">esempi</span><span class="sxs-lookup"><span data-stu-id="3fb5a-293">Examples</span></span>](#tab/examples)

***

### <a name="user-defined-type-named-items"></a><span data-ttu-id="3fb5a-294">Elementi denominati di tipo definito dall'utente</span><span class="sxs-lookup"><span data-stu-id="3fb5a-294">User Defined Type Named Items</span></span> ###

<span data-ttu-id="3fb5a-295">Gli elementi denominati in tipi definiti dall'utente devono essere denominati come `CamelCase`, anche in input per costruttori UDT.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-295">Named items in user-defined types should be named as `CamelCase`, even in input to UDT constructors.</span></span>
<span data-ttu-id="3fb5a-296">Questo consente di separare chiaramente gli elementi denominati dai riferimenti alle variabili con ambito locale quando si usa la notazione della funzione di accesso (ad esempio, `callable::Apply`) o la notazione di copia e aggiornamento (`set arr w/= Data <- newData`).</span><span class="sxs-lookup"><span data-stu-id="3fb5a-296">This helps in order to clearly separate named items from references to locally scoped variables when using accessor notation (e.g.: `callable::Apply`) or copy-and-update notation (`set arr w/= Data <- newData`).</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="3fb5a-297">Materiale sussidiario</span><span class="sxs-lookup"><span data-stu-id="3fb5a-297">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="3fb5a-298">È consigliabile:</span><span class="sxs-lookup"><span data-stu-id="3fb5a-298">We suggest:</span></span>

- <span data-ttu-id="3fb5a-299">Gli elementi denominati nei costruttori UDT devono essere denominati come `CamelCase`; ovvero, devono iniziare con un carattere maiuscolo iniziale.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-299">Named items in UDT constructors should be named as `CamelCase`; that is, they should begin with an initial uppercase.</span></span>
- <span data-ttu-id="3fb5a-300">Gli elementi denominati che risolvono le operazioni devono essere denominati come fasi del verbo.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-300">Named items that resolve to operations should be named as verb phases.</span></span>
- <span data-ttu-id="3fb5a-301">Gli elementi denominati che non vengono risolti in operazioni devono essere denominati frasi sostantive.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-301">Named items that do not resolve to operations should be named as noun phrases.</span></span>
- <span data-ttu-id="3fb5a-302">Per i tipi definiti dall'utente che incapsulano le operazioni, è necessario definire un singolo elemento denominato denominato `Apply`.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-302">For UDTs that wrap operations, a single named item called `Apply` should be defined.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="3fb5a-303">esempi</span><span class="sxs-lookup"><span data-stu-id="3fb5a-303">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="3fb5a-304">Frammento</span><span class="sxs-lookup"><span data-stu-id="3fb5a-304">Snippet</span></span> | <span data-ttu-id="3fb5a-305">Description</span><span class="sxs-lookup"><span data-stu-id="3fb5a-305">Description</span></span> |
|---|---------|-------------|
| <span data-ttu-id="3fb5a-306">☑</span><span class="sxs-lookup"><span data-stu-id="3fb5a-306">☑</span></span> | `newtype Oracle = (Apply : Qubit[] => Unit is Adj + Ctl)` | <span data-ttu-id="3fb5a-307">Il nome `Apply` è una frase verbo in formato `CamelCase`, che suggerisce che l'elemento denominato è un'operazione.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-307">The name `Apply` is a `CamelCase`-formatted verb phrase, suggesting that the named item is an operation.</span></span> |
| <span data-ttu-id="3fb5a-308">☒</span><span class="sxs-lookup"><span data-stu-id="3fb5a-308">☒</span></span> | <s>`newtype Oracle = (apply : Qubit[] => Unit is Adj + Ctl) `</s> | <span data-ttu-id="3fb5a-309">Gli elementi denominati devono iniziare con una lettera maiuscola iniziale.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-309">Named items should begin with an initial uppercase letter.</span></span> |
| <span data-ttu-id="3fb5a-310">☒</span><span class="sxs-lookup"><span data-stu-id="3fb5a-310">☒</span></span> | <s>`newtype Collection = (Length : Int, Get : Int -> (Qubit => Unit)) `</s> | <span data-ttu-id="3fb5a-311">Gli elementi denominati che si risolvono in funzioni devono essere denominati come frasi sostantive, non come frasi verbo.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-311">Named items which resolve to functions should be named as noun phrases, not as verb phrases.</span></span> |

***

## <a name="input-conventions"></a><span data-ttu-id="3fb5a-312">Convenzioni di input</span><span class="sxs-lookup"><span data-stu-id="3fb5a-312">Input Conventions</span></span> ##

<span data-ttu-id="3fb5a-313">Quando uno sviluppatore chiama un'operazione o una funzione, i vari input per tale operazione o funzione devono essere specificati in un ordine particolare, aumentando il carico cognitivo che uno sviluppatore deve affrontare per poter usare una libreria.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-313">When a developer calls into an operation or function, the various inputs to that operation or function must be specified in a particular order, increasing the cognitive load that a developer faces in order to make use of a library.</span></span>
<span data-ttu-id="3fb5a-314">In particolare, l'attività di ricordare gli ordini di input è spesso una distrazione dall'attività a disposizione: programmazione di un'implementazione di un algoritmo Quantum.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-314">In particular, the task of remembering input orderings is often a distraction from the task at hand: programming an implementation of a quantum algorithm.</span></span>
<span data-ttu-id="3fb5a-315">Sebbene il supporto avanzato dell'IDE possa mitigare questo problema in larga misura, una buona progettazione e aderenza alle convenzioni comuni può anche aiutare a ridurre al minimo il carico cognitivo imposto da un'API.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-315">Though rich IDE support can mitigate this to a large extent, good design and adherence to common conventions can also help to minimize the cognitive load imposed by an API.</span></span>

<span data-ttu-id="3fb5a-316">Laddove possibile, può essere utile ridurre il numero di input previsti da un'operazione o una funzione, in modo che il ruolo di ogni input sia più immediato per gli sviluppatori che chiamano tale operazione o funzione e per gli sviluppatori che leggono il codice in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-316">Where possible, it can be helpful to reduce the number of inputs expected by an operation or function, so that the role of each input is more immediately obvious both to developers calling into that operation or function, and to developers reading that code later.</span></span>
<span data-ttu-id="3fb5a-317">Soprattutto quando non è possibile o ragionevole ridurre il numero di argomenti a un'operazione o a una funzione, è importante avere un ordinamento coerente che riduca al minimo la sorpresa che un utente deve affrontare durante la stima dell'ordine degli input.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-317">Especially when it is not possible or reasonable to reduce the number of arguments to an operation or function, it is important to have a consistent ordering that minimizes the surprise that a user faces when predicting the order of inputs.</span></span>

<span data-ttu-id="3fb5a-318">Si consiglia di usare le convenzioni di ordinamento di input che in gran parte derivano dal pensare a un'applicazione parziale come generalizzazione di currying f (x, y) ≡ f (x) (y).</span><span class="sxs-lookup"><span data-stu-id="3fb5a-318">We recommend an input ordering conventions that largely derives from thinking of partial application as a generalization of currying 𝑓(𝑥, 𝑦) ≡ 𝑓(𝑥)(𝑦).</span></span>
<span data-ttu-id="3fb5a-319">Pertanto, l'applicazione parziale dei primi argomenti dovrebbe dare come risultato un oggetto chiamabile che risulta utile in un proprio momento, ogni volta che è ragionevole.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-319">Thus, partially applying the first arguments should result in a callable that is useful in its own right whenever that is reasonable.</span></span>
<span data-ttu-id="3fb5a-320">In base a questo principio, prendere in considerazione l'uso dell'ordine degli argomenti seguente:</span><span class="sxs-lookup"><span data-stu-id="3fb5a-320">Following this principle, consider using the following order of arguments:</span></span>

- <span data-ttu-id="3fb5a-321">Argomenti classici non richiamabili, ad esempio angoli, vettori di potenza e così via.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-321">Classical non-callable arguments such as angles, vectors of powers, etc.</span></span>
- <span data-ttu-id="3fb5a-322">Argomenti chiamabili (funzioni e argomenti).</span><span class="sxs-lookup"><span data-stu-id="3fb5a-322">Callable arguments (functions and arguments).</span></span>
  <span data-ttu-id="3fb5a-323">Se entrambe le funzioni e le operazioni vengono considerate come argomenti, provare a inserire le operazioni dopo le funzioni.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-323">If both functions and operations are taken as arguments, consider placing operations after functions.</span></span>
- <span data-ttu-id="3fb5a-324">Le raccolte su cui si basano gli argomenti richiamabili sono simili per `Map`, `Iter`, `Enumerate`e `Fold`.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-324">Collections acted upon by callable arguments in a similar way to `Map`, `Iter`, `Enumerate`, and `Fold`.</span></span>
- <span data-ttu-id="3fb5a-325">Argomenti qubit usati come controlli.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-325">Qubit arguments used as controls.</span></span>
- <span data-ttu-id="3fb5a-326">Argomenti qubit usati come destinazioni.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-326">Qubit arguments used as targets.</span></span>

<span data-ttu-id="3fb5a-327">Si consideri un'operazione `ApplyPhaseEstimationIteration` per l'utilizzo nella stima della fase che accetta un angolo e un Oracle, passa l'angolo a `Rz` modificato da una matrice di fattori di scala diversi e quindi controlla le applicazioni di Oracle.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-327">Consider an operation `ApplyPhaseEstimationIteration` for use in phase estimation that takes an angle and an oracle, passes the angle to `Rz` modified by an array of different scaling factors, and then controls applications of the oracle.</span></span>
<span data-ttu-id="3fb5a-328">Gli input verranno ordinati in modo da `ApplyPhaseEstimationIteration` nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="3fb5a-328">We would order the inputs to `ApplyPhaseEstimationIteration` in the following fashion:</span></span>

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
<span data-ttu-id="3fb5a-329">Come caso speciale di riduzione delle sorprese, alcune funzioni e operazioni simulano il comportamento del funtori incorporato `Adjoint` e `Controlled`.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-329">As a special case of minimizing surprise, some functions and operations mimic the behavior of the built-in functors `Adjoint` and `Controlled`.</span></span>
<span data-ttu-id="3fb5a-330">Ad esempio, `ControlledOnInt<'T>` dispone di tipo `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)`, in modo che `ControlledOnInt<Qubit[]>(5, _)` funga da `Controlled` functor, ma sulla condizione che il registro di controllo rappresenti lo stato $ \ket{5} = \ket{101}$.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-330">For instance, `ControlledOnInt<'T>` has type `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)`, such that `ControlledOnInt<Qubit[]>(5, _)` acts like the `Controlled` functor, but on the condition that the control register represents the state $\ket{5} = \ket{101}$.</span></span>
<span data-ttu-id="3fb5a-331">Uno sviluppatore prevede pertanto che gli input per `ControlledOnInt` inserire l'ultimo oggetto chiamabile trasformato e che l'operazione risultante accetta come input `(Qubit[], 'T)`---lo stesso ordine seguito dall'output del `Controlled` functor.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-331">Thus, a developer expects that the inputs to `ControlledOnInt` place the callable being transformed last, and that the resulting operation takes as its input `(Qubit[], 'T)` --- the same order as followed by the output of the `Controlled` functor.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="3fb5a-332">Materiale sussidiario</span><span class="sxs-lookup"><span data-stu-id="3fb5a-332">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="3fb5a-333">È consigliabile:</span><span class="sxs-lookup"><span data-stu-id="3fb5a-333">We suggest:</span></span>

- <span data-ttu-id="3fb5a-334">Usare gli ordini di input coerenti con l'uso dell'applicazione parziale.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-334">Use input orderings consistent with the use of partial application.</span></span>
- <span data-ttu-id="3fb5a-335">Usare gli ordini di input coerenti con funtori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-335">Use input orderings consistent with built-in functors.</span></span>
- <span data-ttu-id="3fb5a-336">Inserire tutti gli input classici prima di qualsiasi input Quantum.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-336">Place all classical inputs before any quantum inputs.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="3fb5a-337">esempi</span><span class="sxs-lookup"><span data-stu-id="3fb5a-337">Examples</span></span>](#tab/examples)

***

## <a name="documentation-conventions"></a><span data-ttu-id="3fb5a-338">Convenzioni della documentazione</span><span class="sxs-lookup"><span data-stu-id="3fb5a-338">Documentation Conventions</span></span> ##

<span data-ttu-id="3fb5a-339">Il linguaggio Q # consente di allegare la documentazione a operazioni, funzioni e tipi definiti dall'utente tramite l'utilizzo di commenti di documentazione specificamente formattati.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-339">The Q# language allows for attaching documentation to operations, functions, and user-defined types through the use of specially formatted documentation comments.</span></span>
<span data-ttu-id="3fb5a-340">Indicato da tre barre (`///`), questi commenti di documentazione sono documenti Markdown di piccole dimensioni [DocFX](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) che possono essere usati per descrivere lo scopo di ogni operazione, funzione e tipo definito dall'utente, quali input si aspettano ciascuno e così via.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-340">Denoted by triple-slashes (`///`), these documentation comments are small [DocFX-flavored Markdown](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) documents that can be used to describing the purpose of each operation, function, and user-defined type, what inputs each expects, and so forth.</span></span>
<span data-ttu-id="3fb5a-341">Il compilatore fornito con Quantum Development Kit estrae questi commenti e li usa per semplificare la documentazione del set di elementi in https://docs.microsoft.com/quantum.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-341">The compiler provided with the Quantum Development Kit extracts these comments and uses them to help typeset documentation similar to that at https://docs.microsoft.com/quantum.</span></span>
<span data-ttu-id="3fb5a-342">Analogamente, il server di linguaggio fornito con Quantum Development Kit usa questi commenti per fornire assistenza agli utenti quando passano il mouse sui simboli nel codice Q #.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-342">Similarly, the language server provided with the Quantum Development Kit uses these comments to provide help to users when they hover over symbols in their Q# code.</span></span>
<span data-ttu-id="3fb5a-343">L'uso di commenti di documentazione può consentire agli utenti di dare senso al codice fornendo un riferimento utile per i dettagli che non sono facilmente espressi con le altre convenzioni di questo documento.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-343">Making use of documentation comments can thus help users to make sense of code by providing a useful reference for details that are not easily expressed using the other conventions in this document.</span></span>

<div class="nextstepaction"><span data-ttu-id="3fb5a-344">
    [Documentazione di riferimento](xref:microsoft.quantum.language.statements#documentation-comments) per la sintassi di commento
</span><span class="sxs-lookup"><span data-stu-id="3fb5a-344">
    [Documentation comment syntax reference](xref:microsoft.quantum.language.statements#documentation-comments)
</span></span></div>

<span data-ttu-id="3fb5a-345">Per usare efficacemente questa funzionalità per aiutare gli utenti, è consigliabile tenere presenti alcuni aspetti quando si scrivono i commenti della documentazione.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-345">In order to effectively use this functionality to help users, we recommend keeping a few things in mind as you write documentation comments.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="3fb5a-346">Materiale sussidiario</span><span class="sxs-lookup"><span data-stu-id="3fb5a-346">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="3fb5a-347">È consigliabile:</span><span class="sxs-lookup"><span data-stu-id="3fb5a-347">We suggest:</span></span>

- <span data-ttu-id="3fb5a-348">Ogni funzione pubblica, operazione e tipo definito dall'utente deve essere immediatamente preceduta da un commento della documentazione.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-348">Each public function, operation, and user-defined type should be immediately preceded by a documentation comment.</span></span>
- <span data-ttu-id="3fb5a-349">Come minimo, ogni commento alla documentazione deve includere le sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3fb5a-349">At a minimum, each documentation comment should include the following sections:</span></span>
    - <span data-ttu-id="3fb5a-350">Summary</span><span class="sxs-lookup"><span data-stu-id="3fb5a-350">Summary</span></span>
    - <span data-ttu-id="3fb5a-351">Input</span><span class="sxs-lookup"><span data-stu-id="3fb5a-351">Input</span></span>
    - <span data-ttu-id="3fb5a-352">Output (se applicabile)</span><span class="sxs-lookup"><span data-stu-id="3fb5a-352">Output (if applicable)</span></span>
- <span data-ttu-id="3fb5a-353">Assicurarsi che tutti i riepiloghi siano due frasi o meno.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-353">Ensure that all summaries are two sentences or less.</span></span> <span data-ttu-id="3fb5a-354">Se è necessario più spazio, fornire una sezione `# Description` immediatamente dopo `# Summary` con i dettagli completi.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-354">If more room is needed, provide a `# Description` section immediately following `# Summary` with complete details.</span></span>
- <span data-ttu-id="3fb5a-355">Se ragionevole, non includere la matematica nei riepiloghi, perché non tutti i client supportano la notazione TeX nei riepiloghi.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-355">Where reasonable, do not include math in summaries, as not all clients support TeX notation in summaries.</span></span> <span data-ttu-id="3fb5a-356">Si noti che durante la scrittura di documenti in prosa (ad esempio, TeX o Markdown), può essere preferibile usare lunghezze di riga più lunghe.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-356">Note that when writing prose documents (e.g. TeX or Markdown), it may be preferable to use longer line lengths.</span></span>
- <span data-ttu-id="3fb5a-357">Fornire tutte le espressioni matematiche rilevanti nella sezione `# Description`.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-357">Provide all relevant mathematical expressions in the `# Description` section.</span></span>
- <span data-ttu-id="3fb5a-358">Quando si descrivono gli input, non ripetere i tipi di ogni input in quanto questi possono essere dedotti dal compilatore e rischiano di introdurre incoerenza.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-358">When describing inputs, do not repeat the types of each input as these can be inferred by the compiler and risk introducing inconsistency.</span></span>
- <span data-ttu-id="3fb5a-359">Fornire esempi appropriati, ognuno nella propria sezione `# Example`.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-359">Provide examples as appropriate, each in their own `# Example` section.</span></span>
- <span data-ttu-id="3fb5a-360">Descrivere brevemente ogni esempio prima di elencare il codice.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-360">Briefly describe each example before listing code.</span></span>
- <span data-ttu-id="3fb5a-361">Citare tutte le pubblicazioni accademiche rilevanti, ad esempio documenti, procedure, post di Blog e implementazioni alternative, in una `# References` sezione come elenco puntato dei collegamenti.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-361">Cite all relevant academic publications (e.g.: papers, proceedings, blog posts, and alternative implementations) in a `# References` section as a bulleted list of links.</span></span>
- <span data-ttu-id="3fb5a-362">Assicurarsi che, ove possibile, tutti i collegamenti di citazione siano identificatori permanenti e non modificabili (DOI o numeri arXiv con versione).</span><span class="sxs-lookup"><span data-stu-id="3fb5a-362">Ensure that, where possible, all citation links are to permanent and immutable identifiers (DOIs or versioned arXiv numbers).</span></span>
- <span data-ttu-id="3fb5a-363">Quando un'operazione o una funzione è correlata ad altre operazioni o funzioni in base alle varianti di functor, elencare altre varianti come punti elenco nella sezione `# See Also`.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-363">When an operation or function is related to other operations or functions by functor variants, list other variants as bullets in the `# See Also` section.</span></span>
- <span data-ttu-id="3fb5a-364">Lasciare una riga di commento vuota tra le sezioni di livello 1 (`/// #`), ma non lasciare una riga vuota tra le sezioni di livello 2 (`/// ##`).</span><span class="sxs-lookup"><span data-stu-id="3fb5a-364">Leave a blank comment line between level-1 (`/// #`) sections, but do not leave a blank line between level-2 (`/// ##`) sections.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="3fb5a-365">esempi</span><span class="sxs-lookup"><span data-stu-id="3fb5a-365">Examples</span></span>](#tab/examples)

#### <a name=""></a><span data-ttu-id="3fb5a-366">☑</span><span class="sxs-lookup"><span data-stu-id="3fb5a-366">☑</span></span> ####

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

## <a name="formatting-conventions"></a><span data-ttu-id="3fb5a-367">Convenzioni di formattazione</span><span class="sxs-lookup"><span data-stu-id="3fb5a-367">Formatting Conventions</span></span> ##

<span data-ttu-id="3fb5a-368">Oltre ai suggerimenti precedenti, è utile rendere il codice più leggibile possibile per l'utilizzo di regole di formattazione coerenti.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-368">In addition to the preceding suggestions, it is helpful to help make code as legible as possible to use consistent formatting rules.</span></span>
<span data-ttu-id="3fb5a-369">Tali regole di formattazione per natura tendono a essere arbitrarie e in modo forte fino a essere estetiche personali.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-369">Such formatting rules by nature tend to be somewhat arbitrary and strongly up to personal aesthetics.</span></span>
<span data-ttu-id="3fb5a-370">Tuttavia, si consiglia di mantenere un set coerente di convenzioni di formattazione all'interno di un gruppo di collaboratori e soprattutto per progetti Q # di grandi dimensioni, ad esempio Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-370">Nonetheless, we recommend maintaining a consistent set of formatting conventions within a group of collaborators, and especially for large Q# projects such as the Quantum Development Kit itself.</span></span>
<span data-ttu-id="3fb5a-371">Queste regole possono essere applicate automaticamente usando lo strumento di formattazione integrato con il compilatore Q #.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-371">These rules can be automatically applied by using the formatting tool integrated with the Q# compiler.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="3fb5a-372">Materiale sussidiario</span><span class="sxs-lookup"><span data-stu-id="3fb5a-372">Guidance</span></span>](#tab/guidance) 

<span data-ttu-id="3fb5a-373">È consigliabile:</span><span class="sxs-lookup"><span data-stu-id="3fb5a-373">We suggest:</span></span>

- <span data-ttu-id="3fb5a-374">Usare quattro spazi anziché le schede per la portabilità.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-374">Use four spaces instead of tabs for portability.</span></span>
  <span data-ttu-id="3fb5a-375">Ad esempio, in VS Code:</span><span class="sxs-lookup"><span data-stu-id="3fb5a-375">For instance, in VS Code:</span></span>
  ```json
    "editor.insertSpaces": true,
    "editor.tabSize": 4
  ```
- <span data-ttu-id="3fb5a-376">Ritorno a capo riga a 79 caratteri, ove ragionevole.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-376">Line wrap at 79 characters where reasonable.</span></span>
- <span data-ttu-id="3fb5a-377">Usare spazi intorno agli operatori binari.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-377">Use spaces around binary operators.</span></span>
- <span data-ttu-id="3fb5a-378">Usare spazi su entrambi i lati dei due punti usati per le annotazioni del tipo.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-378">Use spaces on either side of colons used for type annotations.</span></span>
- <span data-ttu-id="3fb5a-379">Usare uno spazio singolo dopo le virgole usate nei valori letterali di matrice e di tupla (ad esempio, in input per funzioni e operazioni).</span><span class="sxs-lookup"><span data-stu-id="3fb5a-379">Use a single space after commas used in array and tuple literals (e.g.: in inputs to functions and operations).</span></span>
- <span data-ttu-id="3fb5a-380">Non usare spazi dopo i nomi di funzione, operazione o UDT o dopo il `@` nelle dichiarazioni di attributo.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-380">Do not use spaces after function, operation, or UDT names, or after the `@` in attribute declarations.</span></span>
- <span data-ttu-id="3fb5a-381">Ogni dichiarazione di attributo deve trovarsi su una riga a se stante.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-381">Each attribute declaration should be on its own line.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="3fb5a-382">esempi</span><span class="sxs-lookup"><span data-stu-id="3fb5a-382">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="3fb5a-383">Frammento</span><span class="sxs-lookup"><span data-stu-id="3fb5a-383">Snippet</span></span> | <span data-ttu-id="3fb5a-384">Description</span><span class="sxs-lookup"><span data-stu-id="3fb5a-384">Description</span></span> |
|---|---------|-------------|
| <span data-ttu-id="3fb5a-385">☒</span><span class="sxs-lookup"><span data-stu-id="3fb5a-385">☒</span></span> | <s>`2+3`</s> | <span data-ttu-id="3fb5a-386">Usare spazi intorno agli operatori binari.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-386">Use spaces around binary operators.</span></span> |
| <span data-ttu-id="3fb5a-387">☒</span><span class="sxs-lookup"><span data-stu-id="3fb5a-387">☒</span></span> | <s>`target:Qubit`</s> | <span data-ttu-id="3fb5a-388">Usare spazi intorno ai due punti dell'annotazione del tipo.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-388">Use spaces around type annotation colons.</span></span> |
| <span data-ttu-id="3fb5a-389">☑</span><span class="sxs-lookup"><span data-stu-id="3fb5a-389">☑</span></span> | `Example(a, b, c)` | <span data-ttu-id="3fb5a-390">Gli elementi nella tupla di input sono spaziati correttamente per migliorare la leggibilità.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-390">Items in input tuple are correctly spaced for readability.</span></span> |
| <span data-ttu-id="3fb5a-391">☒</span><span class="sxs-lookup"><span data-stu-id="3fb5a-391">☒</span></span> | <s>`Example (a, b, c)`</s> | <span data-ttu-id="3fb5a-392">Gli spazi devono essere eliminati dopo i nomi della funzione, dell'operazione o del tipo definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="3fb5a-392">Spaces should be suppressed after function, operation, or UDT names.</span></span> |

***

