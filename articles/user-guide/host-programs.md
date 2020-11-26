---
title: Modalità di esecuzione di un Q# programma
description: Panoramica dei diversi modi per eseguire i Q# programmi. Dal prompt dei comandi, Q# Jupyter notebook e programmi host classici in Python o in un linguaggio .NET.
author: gillenhaalb
ms.author: a-gibec
ms.date: 05/15/2020
ms.topic: article
uid: microsoft.quantum.guide.host-programs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 2c5bdebc826bb85f6d7e0ade6232e15e29e8fb19
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231690"
---
# <a name="ways-to-run-a-no-locq-program"></a><span data-ttu-id="b4ac6-104">Modalità di esecuzione di un Q# programma</span><span class="sxs-lookup"><span data-stu-id="b4ac6-104">Ways to run a Q# program</span></span>

<span data-ttu-id="b4ac6-105">Uno dei principali punti di forza del kit di sviluppo di Quantum è la sua flessibilità tra piattaforme e ambienti di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-105">One of the Quantum Development Kit's greatest strengths is its flexibility across platforms and development environments.</span></span>
<span data-ttu-id="b4ac6-106">Tuttavia, ciò significa anche che Q# i nuovi utenti potrebbero trovarsi confusi o sopraffatti dalle numerose opzioni disponibili nella [Guida all'installazione](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="b4ac6-106">However, this also means that new Q# users may find themselves confused or overwhelmed by the numerous options found in the [install guide](xref:microsoft.quantum.install).</span></span>
<span data-ttu-id="b4ac6-107">In questa pagina viene illustrato cosa accade quando Q# viene eseguito un programma e si confrontano i vari modi in cui gli utenti possono eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-107">On this page, we explain what happens when a Q# program is run, and compare the different ways in which users can do so.</span></span>

<span data-ttu-id="b4ac6-108">Una distinzione principale è che è Q# possibile eseguire:</span><span class="sxs-lookup"><span data-stu-id="b4ac6-108">A primary distinction is that Q# can be run:</span></span>
- <span data-ttu-id="b4ac6-109">come applicazione autonoma, dove Q# è l'unico linguaggio necessario e il programma viene richiamato direttamente.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-109">as a standalone application, where Q# is the only language involved and the program is invoked directly.</span></span> <span data-ttu-id="b4ac6-110">In realtà, due metodi rientreranno in questa categoria:</span><span class="sxs-lookup"><span data-stu-id="b4ac6-110">Two methods actually fall in this category:</span></span>
  - <span data-ttu-id="b4ac6-111">interfaccia della riga di comando</span><span class="sxs-lookup"><span data-stu-id="b4ac6-111">the command-line interface</span></span>
  - <span data-ttu-id="b4ac6-112">Q# Notebook di Jupyter</span><span class="sxs-lookup"><span data-stu-id="b4ac6-112">Q# Jupyter Notebooks</span></span>
- <span data-ttu-id="b4ac6-113">con un *programma host* aggiuntivo, scritto in Python o in un linguaggio .NET (ad esempio, C# o F #), che quindi richiama il programma ed è in grado di elaborare ulteriormente i risultati restituiti.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-113">with an additional *host program*, written in Python or a .NET language (for example, C# or F#), which then invokes the program and can further process returned results.</span></span>

<span data-ttu-id="b4ac6-114">Per comprendere meglio questi processi e le relative differenze, si considera un Q# programma semplice e si confrontano i modi in cui può essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-114">To best understand these processes and their differences, we consider a simple Q# program and compare the ways it can be run.</span></span>

## <a name="basic-no-locq-program"></a><span data-ttu-id="b4ac6-115">Programma di base Q#</span><span class="sxs-lookup"><span data-stu-id="b4ac6-115">Basic Q# program</span></span>

<span data-ttu-id="b4ac6-116">Un programma Quantum di base può comportare la preparazione di un qubit in una superposizione uguale di States $ \ket {0} $ e $ \ket {1} $, la relativa misurazione e la restituzione del risultato, che sarà casuale uno di questi due stati con probabilità uguale.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-116">A basic quantum program might consist of preparing a qubit in an equal superposition of states $\ket{0}$ and $\ket{1}$, measuring it, and returning the result, which will be randomly either one of these two states with equal probability.</span></span>
<span data-ttu-id="b4ac6-117">In realtà, questo processo è alla base della Guida introduttiva del [Generatore di numeri casuali Quantum](xref:microsoft.quantum.quickstarts.qrng) .</span><span class="sxs-lookup"><span data-stu-id="b4ac6-117">Indeed, this process is at the core of the [quantum random number generator](xref:microsoft.quantum.quickstarts.qrng) quickstart.</span></span>

<span data-ttu-id="b4ac6-118">In Q# , questa operazione verrebbe eseguita dal codice seguente:</span><span class="sxs-lookup"><span data-stu-id="b4ac6-118">In Q#, this would be performed by the following code:</span></span>

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

<span data-ttu-id="b4ac6-119">Tuttavia, questo solo codice non può essere eseguito da Q# .</span><span class="sxs-lookup"><span data-stu-id="b4ac6-119">However, this code alone can't be run by Q#.</span></span>
<span data-ttu-id="b4ac6-120">A tale scopo, deve costituire il corpo di un' [operazione](xref:microsoft.quantum.qsharp.operationsandfunctions), che viene quindi eseguita quando viene chiamato---direttamente o da un'altra operazione.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-120">For that, it needs to make up the body of an [operation](xref:microsoft.quantum.qsharp.operationsandfunctions), which is then run when called---either directly or by another operation.</span></span> <span data-ttu-id="b4ac6-121">Quindi, è possibile scrivere un'operazione nel formato seguente:</span><span class="sxs-lookup"><span data-stu-id="b4ac6-121">Hence, you can write an operation of the following form:</span></span>
```qsharp
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) {
            H(q);
            return MResetZ(q);
        }
    }
```
<span data-ttu-id="b4ac6-122">È stata definita un'operazione, `MeasureSuperposition` , che non accetta input e restituisce un valore di tipo [result](xref:microsoft.quantum.qsharp.typesystem-index#available-types).</span><span class="sxs-lookup"><span data-stu-id="b4ac6-122">You have defined an operation, `MeasureSuperposition`, which takes no inputs and returns a value of type [Result](xref:microsoft.quantum.qsharp.typesystem-index#available-types).</span></span>

<span data-ttu-id="b4ac6-123">Oltre alle operazioni, Q# consente inoltre di incapsulare calcoli deterministici in funzioni.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-123">In addition to operations, Q# also allows to encapsulate deterministic computations into functions.</span></span> <span data-ttu-id="b4ac6-124">A parte la garanzia di determinismo che implica che i calcoli che agiscono su qubits devono essere incapsulati in operazioni anziché in funzioni, c'è poca differenza tra operazioni e funzioni.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-124">Aside from the determinism guarantee that implies that computations that act on qubits need to be encapsulated into operations rather than functions, there is little difference between operations and function.</span></span> <span data-ttu-id="b4ac6-125">I riferimenti sono collettivamente *richiamabili*.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-125">We refer to them collectively as *callables*.</span></span>

### <a name="callable-defined-in-a-no-locq-file"></a><span data-ttu-id="b4ac6-126">Chiamabile definito in un Q# file</span><span class="sxs-lookup"><span data-stu-id="b4ac6-126">Callable defined in a Q# file</span></span>

<span data-ttu-id="b4ac6-127">Il callable è esattamente ciò che viene chiamato ed eseguito da Q# .</span><span class="sxs-lookup"><span data-stu-id="b4ac6-127">The callable is precisely what's called and run by Q#.</span></span>
<span data-ttu-id="b4ac6-128">Tuttavia, sono necessarie altre aggiunte per includere un `*.qs` Q# file completo.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-128">However, it requires a few more additions to comprise a full `*.qs` Q# file.</span></span>

<span data-ttu-id="b4ac6-129">Tutti i Q# tipi e i chiamabili (sia quelli definiti che quelli intrinseci al linguaggio) sono definiti all'interno degli *spazi dei nomi*, che forniscono a ognuno un nome completo a cui è possibile fare riferimento.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-129">All Q# types and callables (both those you define and those intrinsic to the language) are defined within *namespaces*, which provide each a full name that can then be referenced.</span></span>

<span data-ttu-id="b4ac6-130">Ad esempio, le [`H`](xref:Microsoft.Quantum.Intrinsic.H) [`MResetZ`](xref:Microsoft.Quantum.Measurement.MResetZ) operazioni e si trovano negli [`Microsoft.Quantum.Instrinsic`](xref:Microsoft.Quantum.Intrinsic) [`Microsoft.Quantum.Measurement`](xref:Microsoft.Quantum.Measurement) spazi dei nomi e (parte delle [ Q# librerie standard](xref:microsoft.quantum.libraries.standard.intro)).</span><span class="sxs-lookup"><span data-stu-id="b4ac6-130">For example, the [`H`](xref:Microsoft.Quantum.Intrinsic.H) and [`MResetZ`](xref:Microsoft.Quantum.Measurement.MResetZ) operations are found in the [`Microsoft.Quantum.Instrinsic`](xref:Microsoft.Quantum.Intrinsic) and [`Microsoft.Quantum.Measurement`](xref:Microsoft.Quantum.Measurement) namespaces (part of the [Q# Standard Libraries](xref:microsoft.quantum.libraries.standard.intro)).</span></span>
<span data-ttu-id="b4ac6-131">Di conseguenza, possono sempre essere chiamati tramite i nomi *completi* , `Microsoft.Quantum.Intrinsic.H(<qubit>)` e `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` , ma sempre questa operazione porterebbe a un codice molto ingombrante.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-131">As such, they can always be called via their *full* names, `Microsoft.Quantum.Intrinsic.H(<qubit>)` and `Microsoft.Quantum.Measurement.MResetZ(<qubit>)`, but always doing this would lead to very cluttered code.</span></span>

<span data-ttu-id="b4ac6-132">Al contrario, `open` le istruzioni consentono di fare riferimento a chiamabili con una sintassi più concisa, come è stato fatto nel corpo dell'operazione precedente.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-132">Instead, `open` statements allow callables to be referenced with more concise shorthand, as we've done in the operation body above.</span></span>
<span data-ttu-id="b4ac6-133">Il Q# file completo che contiene l'operazione sarà quindi costituito dalla definizione di uno spazio dei nomi personalizzato, aprendo gli spazi dei nomi per le Callable utilizzate dall'operazione e quindi l'operazione:</span><span class="sxs-lookup"><span data-stu-id="b4ac6-133">The full Q# file containing our operation would therefore consist of defining our own namespace, opening the namespaces for those callables our operation uses, and then our operation:</span></span>

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

> [!NOTE]
> <span data-ttu-id="b4ac6-134">Gli spazi dei nomi possono anche essere associati a un *alias* all'apertura, che può essere utile se i nomi chiamabili/di tipo in due spazi dei nomi sono in conflitto.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-134">Namespaces can also be *aliased* when opened, which can be helpful if callable/type names in two namespaces conflict.</span></span>
> <span data-ttu-id="b4ac6-135">Ad esempio, è possibile usare in `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` precedenza e quindi chiamare `H` tramite `NamespaceWithH.H(<qubit>)` .</span><span class="sxs-lookup"><span data-stu-id="b4ac6-135">For example, we could instead use `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` above, and then call `H` via `NamespaceWithH.H(<qubit>)`.</span></span>

> [!NOTE]
> <span data-ttu-id="b4ac6-136">Un'eccezione a tutto questo è lo [`Microsoft.Quantum.Core`](xref:Microsoft.Quantum.Core) spazio dei nomi, che viene sempre aperto automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-136">One exception to all of this is the [`Microsoft.Quantum.Core`](xref:Microsoft.Quantum.Core) namespace, which is always automatically opened.</span></span>
> <span data-ttu-id="b4ac6-137">Pertanto, le chiamabili come [`Length`](xref:Microsoft.Quantum.Core.Length) possono sempre essere utilizzate direttamente.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-137">Therefore, callables like [`Length`](xref:Microsoft.Quantum.Core.Length) can always be used directly.</span></span>

### <a name="running-on-target-machines"></a><span data-ttu-id="b4ac6-138">In esecuzione nei computer di destinazione</span><span class="sxs-lookup"><span data-stu-id="b4ac6-138">Running on target machines</span></span>

<span data-ttu-id="b4ac6-139">A questo punto, il modello di esecuzione generale di un Q# programma diventa chiaro.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-139">Now the general run model of a Q# program becomes clear.</span></span>

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt="Q# program execution diagram" width="400">

<span data-ttu-id="b4ac6-140">In primo luogo, l'oggetto chiamabile specifico da eseguire può accedere a qualsiasi altro tipo e chiamabile definito nello stesso spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-140">Firstly, the specific callable to be run has access to any other callables and types defined in the same namespace.</span></span>
<span data-ttu-id="b4ac6-141">Consente inoltre di accedere a tali librerie da qualsiasi [ Q# libreria](xref:microsoft.quantum.libraries), ma è necessario farvi riferimento tramite il nome completo o tramite l'utilizzo di `open` istruzioni descritte in precedenza.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-141">It also access those from any of the [Q# libraries](xref:microsoft.quantum.libraries), but those must be referenced either via their full name, or through the use of `open` statements described above.</span></span>

<span data-ttu-id="b4ac6-142">Il callable stesso viene quindi eseguito in un *[computer di destinazione](xref:microsoft.quantum.machines)*.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-142">The callable itself is then run on a *[target machine](xref:microsoft.quantum.machines)*.</span></span>
<span data-ttu-id="b4ac6-143">I computer di destinazione possono essere hardware Quantum effettivo o più simulatori disponibili come parte del QDK.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-143">Such target machines can be actual quantum hardware or the multiple simulators available as part of the QDK.</span></span>
<span data-ttu-id="b4ac6-144">Per i nostri scopi, il computer di destinazione più utile è un'istanza del [simulatore a stato completo](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator` , che calcola il comportamento del programma come se fosse in esecuzione su un computer Quantum senza rumore.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-144">For our purposes here, the most useful target machine is an instance of the [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator`, which calculates the program's behavior as if it were being run on a noise-free quantum computer.</span></span>

<span data-ttu-id="b4ac6-145">Fino ad ora, abbiamo descritto cosa accade quando Q# viene eseguito un richiamabile specifico.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-145">So far, we've described what happens when a specific Q# callable is being run.</span></span>
<span data-ttu-id="b4ac6-146">Indipendentemente dal fatto che Q# venga usato in un'applicazione autonoma o con un programma host, questo processo generale è più o meno lo stesso---quindi la flessibilità di QDK.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-146">Regardless of whether Q# is used in a standalone application or with a host program, this general process is more or less the same---hence the QDK's flexibility.</span></span>
<span data-ttu-id="b4ac6-147">Le differenze tra le modalità di chiamata al kit di sviluppo di Quantum si rivelano quindi nel *modo* in cui Q# viene chiamata l'esecuzione chiamabile e in che modo vengono restituiti tutti i risultati.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-147">The differences between the ways of calling into the Quantum Development Kit therefore reveal themselves in *how* that Q# callable is called to be run, and in what manner any results are returned.</span></span>
<span data-ttu-id="b4ac6-148">In particolare, le differenze riguardano:</span><span class="sxs-lookup"><span data-stu-id="b4ac6-148">More specifically, the differences revolve around:</span></span>

- <span data-ttu-id="b4ac6-149">Che indica Q# la chiamabile da eseguire</span><span class="sxs-lookup"><span data-stu-id="b4ac6-149">Indicating which Q# callable is to be run</span></span>
- <span data-ttu-id="b4ac6-150">Come vengono forniti i potenziali argomenti chiamabili</span><span class="sxs-lookup"><span data-stu-id="b4ac6-150">How potential callable arguments are provided</span></span>
- <span data-ttu-id="b4ac6-151">Specifica del computer di destinazione in cui eseguirlo</span><span class="sxs-lookup"><span data-stu-id="b4ac6-151">Specifying the target machine on which to run it</span></span>
- <span data-ttu-id="b4ac6-152">Come vengono restituiti i risultati</span><span class="sxs-lookup"><span data-stu-id="b4ac6-152">How any results are returned</span></span>

<span data-ttu-id="b4ac6-153">In primo luogo, viene illustrato come eseguire questa operazione con l' Q# applicazione autonoma dal prompt dei comandi e quindi procedere con l'uso di Python e dei programmi host C#.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-153">First, we discuss how this is done with the Q# standalone application from the command prompt, and then proceed to using Python and C# host programs.</span></span>
<span data-ttu-id="b4ac6-154">Si riserva l'applicazione autonoma dei Q# notebook di Jupyter per ultimo, perché a differenza dei primi tre, la funzionalità principale non è centrata su un Q# file locale.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-154">We reserve the standalone application of Q# Jupyter Notebooks for last, because unlike the first three, it's primary functionality does not center around a local Q# file.</span></span>

> [!NOTE]
> <span data-ttu-id="b4ac6-155">Sebbene non venga illustrato in questi esempi, una comunanza tra i metodi Run è che tutti i messaggi stampati dall'interno del Q# programma ( [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) [`DumpMachine`](xref:Microsoft.Quantum.Diagnostics.DumpMachine) ad esempio, o) verranno sempre stampati nella rispettiva console.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-155">Although we don't illustrate it in these examples, one commonality between the run methods is that any messages printed from inside the Q# program (by way of [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) or [`DumpMachine`](xref:Microsoft.Quantum.Diagnostics.DumpMachine), for example) will typically always be printed to the respective console.</span></span>

## <a name="no-locq-from-the-command-prompt"></a><span data-ttu-id="b4ac6-156">Q# dal prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="b4ac6-156">Q# from the command prompt</span></span>
<span data-ttu-id="b4ac6-157">Uno dei modi più semplici per iniziare a scrivere Q# programmi consiste nell'evitare di preoccuparsi di file separati e di un secondo linguaggio.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-157">One of the easiest ways to get started writing Q# programs is to avoid worrying about separate files and a second language altogether.</span></span>
<span data-ttu-id="b4ac6-158">L'uso di Visual Studio Code o Visual Studio con l'estensione QDK consente un flusso di lavoro trasparente in cui viene eseguito Q# Callable da un unico Q# file.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-158">Using Visual Studio Code or Visual Studio with the QDK extension allows for a seamless work flow in which we run Q# callables from only a single Q# file.</span></span>

<span data-ttu-id="b4ac6-159">A tale scopo, verrà eseguito il programma immettendo</span><span class="sxs-lookup"><span data-stu-id="b4ac6-159">For this, we will ultimately run the program by entering</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="b4ac6-160">al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-160">at the command prompt.</span></span>
<span data-ttu-id="b4ac6-161">Il flusso di lavoro più semplice è quando il percorso della directory del terminale è identico a quello del Q# file, che può essere facilmente gestito insieme alla Q# modifica dei file usando il terminale integrato in vs code, ad esempio.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-161">The simplest workflow is when the terminal's directory location is the same as the Q# file, which can be easily handled alongside Q# file editing by using the integrated terminal in VS Code, for example.</span></span>
<span data-ttu-id="b4ac6-162">Tuttavia, il [ `dotnet run` comando](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) accetta numerose opzioni e il programma può essere eseguito anche da una posizione diversa semplicemente fornendo `--project <PATH>` il percorso del Q# file.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-162">However, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) accepts numerous options, and the program can also be run from a different location by simply providing `--project <PATH>` with the location of the Q# file.</span></span>


### <a name="add-entry-point-to-no-locq-file"></a><span data-ttu-id="b4ac6-163">Aggiungi punto di ingresso al Q# file</span><span class="sxs-lookup"><span data-stu-id="b4ac6-163">Add entry point to Q# file</span></span>

<span data-ttu-id="b4ac6-164">La maggior parte dei file conterrà Q# più richiamabili, quindi naturalmente è necessario consentire al compilatore di scoprire *quale* richiamabile eseguire quando si fornisce il `dotnet run` comando.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-164">Most Q# files will contain more than one callable, so naturally we need to let the compiler know *which* callable to run when we provide the `dotnet run` command.</span></span>
<span data-ttu-id="b4ac6-165">Questa operazione viene eseguita con una semplice modifica al Q# file stesso:</span><span class="sxs-lookup"><span data-stu-id="b4ac6-165">This is done with a simple change to the Q# file itself:</span></span> 
    - <span data-ttu-id="b4ac6-166">aggiungere una riga che `@EntryPoint()` precede direttamente il richiamabile.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-166">add a line with `@EntryPoint()` directly preceding the callable.</span></span>

<span data-ttu-id="b4ac6-167">Il file precedente diventa pertanto</span><span class="sxs-lookup"><span data-stu-id="b4ac6-167">Our file from above would therefore become</span></span>
```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    @EntryPoint()
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

<span data-ttu-id="b4ac6-168">A questo punto, una chiamata di `dotnet run` dal prompt dei comandi comporta `MeasureSuperposition` l'esecuzione e il valore restituito viene quindi stampato direttamente nel terminale.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-168">Now, a call of `dotnet run` from the command prompt leads to `MeasureSuperposition` being run, and the returned value is then printed directly to the terminal.</span></span>
<span data-ttu-id="b4ac6-169">Quindi, viene visualizzato `One` o `Zero` stampato.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-169">So, you will see either `One` or `Zero` printed.</span></span> 

<span data-ttu-id="b4ac6-170">Si noti che non è importante se si dispone di più Callable definiti sotto di esso, solo `MeasureSuperposition` verrà eseguito.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-170">Note that it doesn't matter if you have more callables defined below it, only `MeasureSuperposition` will be run.</span></span>
<span data-ttu-id="b4ac6-171">Non è inoltre possibile che il richiamabile includa i [commenti della documentazione](xref:microsoft.quantum.qsharp.comments#documentation-comments) prima della Dichiarazione `@EntryPoint()` . l'attributo può essere semplicemente inserito sopra di essi.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-171">Additionally, it's no problem if your callable includes [documentation comments](xref:microsoft.quantum.qsharp.comments#documentation-comments) before its declaration, the `@EntryPoint()` attribute can be simply placed above them.</span></span>

### <a name="callable-arguments"></a><span data-ttu-id="b4ac6-172">Argomenti chiamabili</span><span class="sxs-lookup"><span data-stu-id="b4ac6-172">Callable arguments</span></span>

<span data-ttu-id="b4ac6-173">Finora è stata considerata solo un'operazione che non accetta input.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-173">So far, we've only considered an operation that takes no inputs.</span></span>
<span data-ttu-id="b4ac6-174">Si supponga di voler eseguire un'operazione simile, ma su più qubits---il numero di cui viene fornito come argomento.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-174">Suppose we wanted to perform a similar operation, but on multiple qubits---the number of which is provided as an argument.</span></span>
<span data-ttu-id="b4ac6-175">Un'operazione di questo tipo può essere scritta come</span><span class="sxs-lookup"><span data-stu-id="b4ac6-175">Such an operation could be written as</span></span>
```qsharp
    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {              // allocate a register of n qubits
            ApplyToEach(H, qubits);              // apply H to each qubit in the register
            return ForEach(MResetZ, qubits);     // perform MResetZ on each qubit, returns the resulting array
        }
    }
```
<span data-ttu-id="b4ac6-176">dove il valore restituito è una matrice dei risultati della misurazione.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-176">where the returned value is an array of the measurement results.</span></span>
<span data-ttu-id="b4ac6-177">Si noti che [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) e [`ForEach`](xref:Microsoft.Quantum.Arrays.ForEach) si trovano [`Microsoft.Quantum.Canon`](xref:Microsoft.Quantum.Canon) negli [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) spazi dei nomi e, richiedendo `open` istruzioni aggiuntive per ciascuna di esse.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-177">Note that [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) and [`ForEach`](xref:Microsoft.Quantum.Arrays.ForEach) are in the [`Microsoft.Quantum.Canon`](xref:Microsoft.Quantum.Canon) and [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) namespaces, requiring additional `open` statements for each.</span></span>

<span data-ttu-id="b4ac6-178">Se si sposta l' `@EntryPoint()` attributo in modo che preceda questa nuova operazione (si noti che può essere presente solo una riga di questo tipo in un file), il tentativo di eseguirlo con semplicemente `dotnet run` genera un messaggio di errore che indica quali opzioni aggiuntive della riga di comando sono necessarie e come esporle.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-178">If we move the `@EntryPoint()` attribute to precede this new operation (note there can only be one such line in a file), attempting to run it with simply `dotnet run` results in an error message which indicates what additional command-line options are required, and how to express them.</span></span>

<span data-ttu-id="b4ac6-179">Il formato generale per la riga di comando è in realtà `dotnet run [options]` e gli argomenti chiamabili sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-179">The general format for the command line is actually `dotnet run [options]`, and callable arguments are provided there.</span></span>
<span data-ttu-id="b4ac6-180">In questo caso, l'argomento `n` è mancante e mostra che è necessario specificare l'opzione `-n <n>` .</span><span class="sxs-lookup"><span data-stu-id="b4ac6-180">In this case, the argument `n` is missing, and it shows that we need to provide the option `-n <n>`.</span></span> <span data-ttu-id="b4ac6-181">Per eseguire `MeasureSuperpositionArray` per `n=4` qubits, si usa quindi</span><span class="sxs-lookup"><span data-stu-id="b4ac6-181">To run `MeasureSuperpositionArray` for `n=4` qubits, we therefore use</span></span>

```dotnetcli
dotnet run -n 4
```

<span data-ttu-id="b4ac6-182">produzione di un output simile a</span><span class="sxs-lookup"><span data-stu-id="b4ac6-182">yielding an output similar to</span></span>

```output
[Zero,One,One,One]
```

<span data-ttu-id="b4ac6-183">Questo naturalmente si estende a più argomenti.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-183">This of course extends to multiple arguments.</span></span>

> [!NOTE]
> <span data-ttu-id="b4ac6-184">I nomi degli argomenti definiti in `camelCase` sono leggermente modificati dal compilatore per essere accettati come Q# input.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-184">Argument names defined in `camelCase` are slightly altered by the compiler to be accepted as Q# inputs.</span></span> <span data-ttu-id="b4ac6-185">Se, ad esempio, invece di `n` è stato usato il nome `numQubits` precedente, questo input verrebbe fornito nella riga di comando tramite `--num-qubits 4` invece di `-n 4` .</span><span class="sxs-lookup"><span data-stu-id="b4ac6-185">For example, if instead of `n`, we used the name `numQubits` above, then this input would be provided in the command line via `--num-qubits 4` instead of `-n 4`.</span></span>

<span data-ttu-id="b4ac6-186">Il messaggio di errore fornisce anche altre opzioni che è possibile usare, inclusa la modalità di modifica del computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-186">The error message also provides other options which can be used, including how to change the target machine.</span></span>

### <a name="different-target-machines"></a><span data-ttu-id="b4ac6-187">Computer di destinazione diversi</span><span class="sxs-lookup"><span data-stu-id="b4ac6-187">Different target machines</span></span>

<span data-ttu-id="b4ac6-188">Poiché gli output delle nostre operazioni sono stati finora i risultati previsti della loro azione su qubits reali, è evidente che il computer di destinazione predefinito dalla riga di comando è il simulatore di Quantum a stato completo, `QuantumSimulator` .</span><span class="sxs-lookup"><span data-stu-id="b4ac6-188">As the outputs from our operations thus far have been the expected results of their action on real qubits, it's clear that the default target machine from the command line is the full-state quantum simulator, `QuantumSimulator`.</span></span>
<span data-ttu-id="b4ac6-189">Tuttavia, è possibile impostare l'esecuzione di Callable in un computer di destinazione specifico con l'opzione `--simulator` (o la sintassi abbreviata `-s` ).</span><span class="sxs-lookup"><span data-stu-id="b4ac6-189">However, we can instruct callables to be run on a specific target machine with the option `--simulator` (or the shorthand `-s`).</span></span>

<span data-ttu-id="b4ac6-190">Ad esempio, è possibile eseguirlo in [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) :</span><span class="sxs-lookup"><span data-stu-id="b4ac6-190">For example, we could run it on [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator):</span></span>

```dotnetcli
dotnet run -n 4 -s ResourcesEstimator
```

<span data-ttu-id="b4ac6-191">L'output stampato è quindi</span><span class="sxs-lookup"><span data-stu-id="b4ac6-191">The printed output is then</span></span>

```output
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

<span data-ttu-id="b4ac6-192">Per informazioni dettagliate su ciò che indica le metriche, vedere [Resource Estimator: Metrics reported](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).</span><span class="sxs-lookup"><span data-stu-id="b4ac6-192">For details on what these metrics indicate, see [Resource estimator: metrics reported](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).</span></span>

### <a name="command-line-run-summary"></a><span data-ttu-id="b4ac6-193">Riepilogo dell'esecuzione della riga di comando</span><span class="sxs-lookup"><span data-stu-id="b4ac6-193">Command line run summary</span></span>
<br/>
<img src="../media/hostprograms_command_line_diagram.png" alt="Q# program from command line" width="700">

### <a name="non-no-locq-dotnet-run-options"></a><span data-ttu-id="b4ac6-194">Opzioni non Q# `dotnet run` disponibili</span><span class="sxs-lookup"><span data-stu-id="b4ac6-194">Non-Q# `dotnet run` options</span></span>

<span data-ttu-id="b4ac6-195">Come accennato in precedenza con l' `--project` opzione, il [ `dotnet run` comando](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) accetta anche le opzioni non correlate agli Q# argomenti chiamabili.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-195">As we briefly mentioned above with the `--project` option, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) also accepts options unrelated to the Q# callable arguments.</span></span>
<span data-ttu-id="b4ac6-196">Se si specificano entrambi i tipi di opzioni, le `dotnet` Opzioni specifiche di devono essere fornite per prime, seguite da un un delimitatore `--` e quindi dalle Q# Opzioni specifiche di.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-196">If providing both kinds of options, the `dotnet`-specific options must be provided first, followed by a delimeter `--`, and then the Q#-specific options.</span></span>
<span data-ttu-id="b4ac6-197">Ad esempio, se si specifica un percorso insieme a un numero qubits per l'operazione precedente, viene eseguito tramite `dotnet run --project <PATH> -- -n <n>` .</span><span class="sxs-lookup"><span data-stu-id="b4ac6-197">For example, specifying a path along with a number qubits for the operation above would be run via `dotnet run --project <PATH> -- -n <n>`.</span></span>

## <a name="no-locq-with-host-programs"></a><span data-ttu-id="b4ac6-198">Q# con programmi host</span><span class="sxs-lookup"><span data-stu-id="b4ac6-198">Q# with host programs</span></span>

<span data-ttu-id="b4ac6-199">Con il Q# file a disposizione, un'alternativa alla chiamata di un'operazione o di una funzione direttamente dal prompt dei comandi consiste nell'usare un *programma host* in un altro linguaggio classico.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-199">With our Q# file in hand, an alternative to calling an operation or function directly from the command prompt is to use a *host program* in another classical language.</span></span> <span data-ttu-id="b4ac6-200">In particolare, questa operazione può essere eseguita con Python o un linguaggio .NET, ad esempio C# o F # (per motivi di brevità verrà illustrato solo C#).</span><span class="sxs-lookup"><span data-stu-id="b4ac6-200">Specifically, this can be done with either Python or a .NET language such as C# or F# (for the sake of brevity we will only detail C# here).</span></span>
<span data-ttu-id="b4ac6-201">Per abilitare l'interoperabilità è necessaria una maggiore configurazione, ma queste informazioni sono disponibili nelle guide all' [installazione](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="b4ac6-201">A little more setup is required to enable the interoperability, but those details can be found in the [install guides](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="b4ac6-202">In breve, la situazione ora include un file di programma host, ad esempio `*.py` o, `*.cs` nella stessa posizione del Q# file.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-202">In a nutshell, the situation now includes a host program file (for example, `*.py` or `*.cs`) in the same location as our Q# file.</span></span>
<span data-ttu-id="b4ac6-203">È ora il programma *host* che viene eseguito e mentre è in esecuzione, può chiamare Q# operazioni e funzioni specifiche dal Q# file.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-203">It's now the *host* program that gets run, and while it is running, it can call specific Q# operations and functions from the Q# file.</span></span>
<span data-ttu-id="b4ac6-204">Il nucleo dell'interoperabilità è basato sul Q# compilatore che rende il contenuto del Q# file accessibile al programma host in modo che possano essere chiamati.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-204">The core of the interoperability is based on the Q# compiler making the contents of the Q# file accessible to the host program so that they can be called.</span></span>

<span data-ttu-id="b4ac6-205">Uno dei principali vantaggi derivanti dall'utilizzo di un programma host è che i dati classici restituiti dal Q# programma possono essere elaborati ulteriormente nel linguaggio host.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-205">One of the main benefits of using a host program is that the classical data returned by the Q# program can then be further processed in the host language.</span></span>
<span data-ttu-id="b4ac6-206">Questo può essere costituito da un'elaborazione avanzata dei dati (ad esempio, un elemento che non può essere eseguita internamente in Q# ) e quindi dalla chiamata di altre Q# azioni in base a tali risultati, o un elemento semplice come tracciare i Q# risultati.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-206">This could consist of some advanced data processing (for example, something that can't be performed internally in Q#), and then calling further Q# actions based on those results, or something as simple as plotting the Q# results.</span></span>

<span data-ttu-id="b4ac6-207">Lo schema generale è illustrato di seguito e vengono illustrate le implementazioni specifiche per Python e C#.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-207">The general scheme is shown here, and we discuss the specific implementations for Python and C# below.</span></span> <span data-ttu-id="b4ac6-208">Un esempio di utilizzo di un programma host F # si trova negli [esempi di interoperabilità .NET](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span><span class="sxs-lookup"><span data-stu-id="b4ac6-208">A sample using an F# host program can be found at the [.NET interoperability samples](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span></span>

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt="Q# program from a host program" width="700">

> [!NOTE]
> <span data-ttu-id="b4ac6-209">L' `@EntryPoint()` attributo utilizzato per Q# le applicazioni non può essere utilizzato con i programmi host.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-209">The `@EntryPoint()` attribute used for Q# applications cannot be used with host programs.</span></span>
> <span data-ttu-id="b4ac6-210">Se presente nel Q# file chiamato da un host, verrà generato un errore.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-210">An error will be raised if it is present in the Q# file being called by a host.</span></span> 

<span data-ttu-id="b4ac6-211">Per lavorare con programmi host diversi, non sono necessarie modifiche a un `*.qs` Q# file.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-211">To work with different host programs, there are no changes required to a `*.qs` Q# file.</span></span>
<span data-ttu-id="b4ac6-212">Tutte le implementazioni del programma host seguenti funzionano con lo stesso Q# file:</span><span class="sxs-lookup"><span data-stu-id="b4ac6-212">The following host program implementations all work with the same Q# file:</span></span>

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // contains H
    open Microsoft.Quantum.Measurement;   // MResetZ
    open Microsoft.Quantum.Canon;         // ApplyToEach
    open Microsoft.Quantum.Arrays;        // ForEach

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }

    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {  
            ApplyToEach(H, qubits); 
            return ForEach(MResetZ, qubits);    
        }
    }
}
```

<span data-ttu-id="b4ac6-213">Selezionare la scheda corrispondente alla lingua host di interesse.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-213">Select the tab corresponding to your host language of interest.</span></span>

### <a name="python"></a>[<span data-ttu-id="b4ac6-214">Python</span><span class="sxs-lookup"><span data-stu-id="b4ac6-214">Python</span></span>](#tab/tabid-python)
<span data-ttu-id="b4ac6-215">Un programma host Python viene costruito come segue:</span><span class="sxs-lookup"><span data-stu-id="b4ac6-215">A Python host program is constructed as follows:</span></span>
1. <span data-ttu-id="b4ac6-216">Importare il `qsharp` modulo, che registra il caricatore del modulo per l' Q# interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-216">Import the `qsharp` module, which registers the module loader for Q# interoperability.</span></span> 
    <span data-ttu-id="b4ac6-217">In questo modo gli Q# spazi dei nomi possono apparire come moduli Python, da cui è possibile "importare" Q# chiamabili.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-217">This allows Q# namespaces to appear as Python modules, from which we can "import" Q# callables.</span></span>
    <span data-ttu-id="b4ac6-218">Si noti che non si tratta tecnicamente dei Q# richiamabili che vengono importati, ma piuttosto degli stub Python che consentono di chiamarli.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-218">Note that it is technically not the Q# callables themselves which are imported, but rather Python stubs which allow calling into them.</span></span>
    <span data-ttu-id="b4ac6-219">Si comportano come oggetti di classi Python.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-219">These behave as objects of Python classes.</span></span> <span data-ttu-id="b4ac6-220">Si usano i metodi su questi oggetti per specificare i computer di destinazione a cui si invia l'operazione quando si esegue il programma.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-220">We use methods on these objects to specify the target machines that we send the operation to when running the program.</span></span>

2. <span data-ttu-id="b4ac6-221">Importare i Q# richiamabili che verranno richiamati direttamente---in questo caso, `MeasureSuperposition` e `MeasureSuperpositionArray` .</span><span class="sxs-lookup"><span data-stu-id="b4ac6-221">Import those Q# callables which we will directly invoke---in this case, `MeasureSuperposition` and `MeasureSuperpositionArray`.</span></span>
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    <span data-ttu-id="b4ac6-222">Con il `qsharp` modulo importato, è anche possibile importare i richiamabili direttamente dagli Q# spazi dei nomi della libreria.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-222">With the `qsharp` module imported, you can also import callables directly from the Q# library namespaces.</span></span>

3. <span data-ttu-id="b4ac6-223">Tra qualsiasi altro codice Python, è ora possibile chiamare tali chiamate su computer di destinazione specifici e assegnare i relativi ritorni alle variabili (se restituiscono un valore) per un ulteriore utilizzo.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-223">Among any other Python code, you can now call those callables on specific target machines, and assign their returns to variables (if they return a value) for further use.</span></span>

#### <a name="specifying-target-machines"></a><span data-ttu-id="b4ac6-224">Specifica di computer di destinazione</span><span class="sxs-lookup"><span data-stu-id="b4ac6-224">Specifying target machines</span></span>
<span data-ttu-id="b4ac6-225">La chiamata di un'operazione da eseguire in un computer di destinazione specifico viene eseguita tramite diversi metodi Python sull'oggetto importato.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-225">Calling an operation to be run on a specific target machine is done via different Python methods on the imported object.</span></span>
<span data-ttu-id="b4ac6-226">Ad esempio, `.simulate(<args>)` , USA `QuantumSimulator` per eseguire l'operazione, mentre a tale scopo `.estimate_resources(<args>)` su `ResourcesEstimator` .</span><span class="sxs-lookup"><span data-stu-id="b4ac6-226">For example, `.simulate(<args>)`, uses the `QuantumSimulator` to run the operation, whereas `.estimate_resources(<args>)` does so on the `ResourcesEstimator`.</span></span>

#### <a name="passing-inputs-to-q"></a><span data-ttu-id="b4ac6-227">Passaggio di input a Q\#</span><span class="sxs-lookup"><span data-stu-id="b4ac6-227">Passing inputs to Q\#</span></span>
<span data-ttu-id="b4ac6-228">Gli argomenti per l'oggetto Q# chiamabile devono essere forniti sotto forma di argomento di parola chiave, dove la parola chiave è il nome dell'argomento nella Q# definizione chiamabile.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-228">Arguments for the Q# callable should be provided in the form of a keyword argument, where the keyword is the argument name in the Q# callable definition.</span></span>
<span data-ttu-id="b4ac6-229">Ovvero `MeasureSuperpositionArray.simulate(n=4)` è valido, mentre `MeasureSuperpositionArray.simulate(4)` genera un errore.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-229">That is, `MeasureSuperpositionArray.simulate(n=4)` is valid, whereas `MeasureSuperpositionArray.simulate(4)` would throw an error.</span></span>

<span data-ttu-id="b4ac6-230">Quindi, il programma host Python</span><span class="sxs-lookup"><span data-stu-id="b4ac6-230">Therefore, the Python host program</span></span> 

```python
import qsharp
from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray

single_qubit_result = MeasureSuperposition.simulate()
single_qubit_resources = MeasureSuperposition.estimate_resources()

multi_qubit_result = MeasureSuperpositionArray.simulate(n=4)
multi_qubit_resources = MeasureSuperpositionArray.estimate_resources(n=4)

print('Single qubit:\n' + str(single_qubit_result))
print(single_qubit_resources)

print('\nMultiple qubits:\n' + str(multi_qubit_result))
print(multi_qubit_resources)
```

<span data-ttu-id="b4ac6-231">Restituisce un output simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="b4ac6-231">results in an output like the following:</span></span>

```output
Single qubit:
1
{'CNOT': 0, 'QubitClifford': 1, 'R': 0, 'Measure': 1, 'T': 0, 'Depth': 0, 'Width': 1, 'BorrowedWidth': 0}

Multiple qubits:
[0, 1, 1, 1]
{'CNOT': 0, 'QubitClifford': 4, 'R': 0, 'Measure': 4, 'T': 0, 'Depth': 0, 'Width': 4, 'BorrowedWidth': 0}
```

#### <a name="using-no-locq-code-from-other-projects-or-packages"></a><span data-ttu-id="b4ac6-232">Uso Q# del codice da altri progetti o pacchetti</span><span class="sxs-lookup"><span data-stu-id="b4ac6-232">Using Q# code from other projects or packages</span></span>

<span data-ttu-id="b4ac6-233">Per impostazione predefinita, il `import qsharp` comando carica tutti i `.qs` file nella cartella corrente e rende disponibili le Q# operazioni e le funzioni da usare all'interno dello script Python.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-233">By default, the `import qsharp` command loads all of the `.qs` files in the current folder and makes their Q# operations and functions available for use from inside the Python script.</span></span>

<span data-ttu-id="b4ac6-234">Per caricare Q# il codice da un'altra cartella, è possibile usare l' [ `qsharp.projects` API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects) per aggiungere un riferimento a un `.csproj` file per un Q# progetto, ovvero un progetto che fa riferimento a `Microsoft.Quantum.Sdk` .</span><span class="sxs-lookup"><span data-stu-id="b4ac6-234">To load Q# code from another folder, the [`qsharp.projects` API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects) can be used to add a reference to a `.csproj` file for a Q# project (that is, a project that references `Microsoft.Quantum.Sdk`).</span></span>
<span data-ttu-id="b4ac6-235">Tramite questo comando vengono compilati tutti i `.qs` file nella cartella contenente le `.csproj` sottocartelle e.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-235">This command will compile any `.qs` files in the folder containing the `.csproj` and its subfolders.</span></span> <span data-ttu-id="b4ac6-236">Inoltre, caricherà in modo ricorsivo tutti i pacchetti a cui viene fatto riferimento tramite `PackageReference` o i Q# progetti a cui viene fatto riferimento tramite `ProjectReference` in tale `.csproj` file.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-236">It will also recursively load any packages referenced via `PackageReference` or Q# projects referenced via `ProjectReference` in that `.csproj` file.</span></span>

<span data-ttu-id="b4ac6-237">Ad esempio, il codice Python seguente importa un progetto esterno, facendo riferimento al relativo percorso relativo alla cartella corrente e richiama una delle Q# operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b4ac6-237">As an example, the following Python code imports an external project, referencing its path relative to the current folder, and invokes one of its Q# operations:</span></span>

```python
import qsharp
qsharp.projects.add("../qrng/Qrng.csproj")
from Qrng import SampleQuantumRandomNumberGenerator
print(f"Qrng result: {SampleQuantumRandomNumberGenerator.simulate()}")
```

<span data-ttu-id="b4ac6-238">Viene restituito un output simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="b4ac6-238">This results in output like the following:</span></span>

```output
Adding reference to project: ../qrng/Qrng.csproj
Qrng result: 0
```

<span data-ttu-id="b4ac6-239">Per caricare pacchetti esterni che contengono Q# codice, usare l' [ `qsharp.packages` API](https://docs.microsoft.com/python/qsharp-core/qsharp.packages.packages).</span><span class="sxs-lookup"><span data-stu-id="b4ac6-239">To load external packages containing Q# code, use the [`qsharp.packages` API](https://docs.microsoft.com/python/qsharp-core/qsharp.packages.packages).</span></span>

<span data-ttu-id="b4ac6-240">Se il Q# codice nella cartella corrente dipende da progetti o pacchetti esterni, è possibile che vengano visualizzati errori durante `import qsharp` l'esecuzione, perché le dipendenze non sono state ancora caricate.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-240">If the Q# code in the current folder depends on external projects or packages, you may see errors when running `import qsharp`, since the dependencies have not yet been loaded.</span></span>
<span data-ttu-id="b4ac6-241">Per caricare i pacchetti o i Q# progetti esterni richiesti durante il `import qsharp` comando, assicurarsi che la cartella con lo script Python contenga un `.csproj` file che fa riferimento a `Microsoft.Quantum.Sdk` .</span><span class="sxs-lookup"><span data-stu-id="b4ac6-241">To load required external packages or Q# projects during the `import qsharp` command, ensure that the folder with the Python script contains a `.csproj` file which references `Microsoft.Quantum.Sdk`.</span></span> <span data-ttu-id="b4ac6-242">`.csproj`Aggiungere la proprietà `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` a `<PropertyGroup>` .</span><span class="sxs-lookup"><span data-stu-id="b4ac6-242">In that `.csproj`, add the property `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` to the `<PropertyGroup>`.</span></span> <span data-ttu-id="b4ac6-243">In questo modo si indicherà Q# a di caricare in modo ricorsivo tutti `ProjectReference` `PackageReference` gli elementi o trovati `.csproj` durante il `import qsharp` comando.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-243">This will instruct IQ# to recursively load any `ProjectReference` or `PackageReference` items found in that `.csproj` during the `import qsharp` command.</span></span>

<span data-ttu-id="b4ac6-244">Ad esempio, di seguito è riportato un semplice `.csproj` file che consente Q# di caricare automaticamente il `Microsoft.Quantum.Chemistry` pacchetto:</span><span class="sxs-lookup"><span data-stu-id="b4ac6-244">For example, here is a simple `.csproj` file that causes IQ# to automatically load the `Microsoft.Quantum.Chemistry` package:</span></span>

```xml
<Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    <PropertyGroup>
        <OutputType>Library</OutputType>
        <TargetFramework>netstandard2.1</TargetFramework>
        <IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>
    </PropertyGroup>
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Chemistry" Version="0.12.20072031" />
    </ItemGroup>
</Project>
```

> [!NOTE]
> <span data-ttu-id="b4ac6-245">Attualmente questa `<IQSharpLoadAutomatically>` proprietà personalizzata è richiesta dagli host Python, ma in futuro può diventare il comportamento predefinito per un `.csproj` file che si trova nella stessa cartella dello script Python.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-245">Currently this custom `<IQSharpLoadAutomatically>` property is required by Python hosts, but in the future, this may become the default behavior for a `.csproj` file located in the same folder as the Python script.</span></span>

> [!NOTE]
> <span data-ttu-id="b4ac6-246">Attualmente l' `<QsharpCompile>` impostazione in `.csproj` viene ignorata dagli host Python e tutti `.qs` i file nella cartella di `.csproj` (incluse le sottocartelle) vengono caricati e compilati.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-246">Currently the `<QsharpCompile>` setting in the `.csproj` is ignored by Python hosts, and all `.qs` files in the folder of the `.csproj` (including subfolders) are loaded and compiled.</span></span> <span data-ttu-id="b4ac6-247">Il supporto per `.csproj` le impostazioni verrà migliorato in futuro (vedere [iqsharp # 277](https://github.com/microsoft/iqsharp/issues/277) per altri dettagli).</span><span class="sxs-lookup"><span data-stu-id="b4ac6-247">Support for `.csproj` settings will be improved in the future (see [iqsharp#277](https://github.com/microsoft/iqsharp/issues/277) for more details).</span></span>


### <a name="c"></a>[<span data-ttu-id="b4ac6-248">C#</span><span class="sxs-lookup"><span data-stu-id="b4ac6-248">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="b4ac6-249">Un programma host C# ha più componenti e funziona molto attentamente con alcuni componenti di QDK, ad esempio i simulatori, che vengono creati in C#.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-249">A C# host program has multiple components, and works very closely with some components of the QDK, such as the simulators, which are themselves built on C#.</span></span>

<span data-ttu-id="b4ac6-250">Il Q# compilatore funziona qui generando uno spazio dei nomi C# denominato in modo equivalente dallo Q# spazio dei nomi nel Q# file.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-250">The Q# compiler works here by generating an equivalently named C# namespace from the Q# namespace in our Q# file.</span></span>
<span data-ttu-id="b4ac6-251">Genera ulteriormente una classe C# denominata in modo equivalente per ognuno dei Q# tipi chiamabili o dei tipi definiti.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-251">It further generates an equivalently named C# class for each of the Q# callables or types defined therein.</span></span>

<span data-ttu-id="b4ac6-252">In primo luogo, le classi usate nel programma host sono disponibili con `using` le istruzioni, che sono approssimativamente analogo alle `open` istruzioni nel Q# file:</span><span class="sxs-lookup"><span data-stu-id="b4ac6-252">First, we make any classes used in our host program available with `using` statements, which are roughly analagous to the `open` statements in our Q# file:</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (for example, QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the Q# namespace available
```

<span data-ttu-id="b4ac6-253">A questo punto, si dichiara lo spazio dei nomi C#, altri bit e parti (vedere il blocco di codice completo riportato di seguito) e quindi qualsiasi programmazione classica, ad esempio per l'elaborazione degli argomenti per i Q# chiamabili.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-253">Next, we declare our C# namespace, a few other bits and pieces (see the full code block below), and then any classical programming we would like (for example, computing arguments for the Q# callables).</span></span>
<span data-ttu-id="b4ac6-254">Quest'ultimo non è necessario in questo caso, ma un esempio di tale utilizzo si trova nell'  [esempio di interoperabilità .NET](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span><span class="sxs-lookup"><span data-stu-id="b4ac6-254">The latter isn't necessary in our case, but an example of such usage can be found at the  [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span></span>

#### <a name="target-machines"></a><span data-ttu-id="b4ac6-255">Computer di destinazione</span><span class="sxs-lookup"><span data-stu-id="b4ac6-255">Target machines</span></span>

<span data-ttu-id="b4ac6-256">Tornando a Q# , è necessario creare un'istanza di qualsiasi computer di destinazione su cui si eseguiranno le operazioni.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-256">Getting back to Q#, we must create an instance of whatever target machine we will run our operations on.</span></span>

```csharp
            using var sim = new QuantumSimulator();
```

<span data-ttu-id="b4ac6-257">L'uso di altri computer di destinazione è semplice come creare un'istanza di un altro computer, anche se la modalità di esecuzione e l'elaborazione dei ritorni possono essere leggermente diversi.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-257">Using other target machines is as simple as instantiating a different one, although the manner of doing so and processing the returns can be slightly different.</span></span>
<span data-ttu-id="b4ac6-258">Per brevità, è necessario attenersi al [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) per il momento e includere quanto [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [segue](#including-the-resources-estimator).</span><span class="sxs-lookup"><span data-stu-id="b4ac6-258">For brevity, we stick to the [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) for now, and include the [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [below](#including-the-resources-estimator).</span></span>

<span data-ttu-id="b4ac6-259">Ogni classe C# generata dalle Q# operazioni dispone di un `Run` metodo, il primo argomento di che deve essere l'istanza del computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-259">Each C# class generated from the Q# operations have a `Run` method, the first argument of which must be the target machine instance.</span></span>
<span data-ttu-id="b4ac6-260">Quindi, per `MeasureSuperposition` l'esecuzione in `QuantumSimulator` , viene utilizzato `MeasureSuperposition.Run(sim)` .</span><span class="sxs-lookup"><span data-stu-id="b4ac6-260">So, to run `MeasureSuperposition` on the `QuantumSimulator`, we use `MeasureSuperposition.Run(sim)`.</span></span>
<span data-ttu-id="b4ac6-261">I risultati restituiti possono quindi essere assegnati alle variabili in C#:</span><span class="sxs-lookup"><span data-stu-id="b4ac6-261">The returned results can then be assigned to variables in C#:</span></span>

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> <span data-ttu-id="b4ac6-262">Il `Run` metodo viene eseguito in modo asincrono perché si tratta del caso di hardware Quantum reale e pertanto la `await` parola chiave blocca ulteriormente l'elaborazione fino al completamento dell'attività.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-262">The `Run` method is run asynchronously because this will be the case for real quantum hardware, and therefore the `await` keyword blocks further processing until the task completes.</span></span>

<span data-ttu-id="b4ac6-263">Se l'oggetto Q# chiamabile non ha alcun valore restituito (ad esempio, ha un tipo restituito `Unit` ), l'esecuzione può comunque essere eseguita nello stesso modo senza assegnarla a una variabile.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-263">If the Q# callable does not have any returns (for example, it has return type `Unit`), then the run can still be done in the same manner without assigning it to a variable.</span></span>
<span data-ttu-id="b4ac6-264">In tal caso, l'intera riga costituirebbe semplicemente</span><span class="sxs-lookup"><span data-stu-id="b4ac6-264">In that case, the entire line would simply consist of</span></span> 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a><span data-ttu-id="b4ac6-265">Argomenti</span><span class="sxs-lookup"><span data-stu-id="b4ac6-265">Arguments</span></span>

<span data-ttu-id="b4ac6-266">Tutti gli argomenti per l'oggetto Q# chiamabile vengono semplicemente passati come argomenti aggiuntivi dopo il computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-266">Any arguments to the Q# callable are simply passed as additional arguments after the target machine.</span></span>
<span data-ttu-id="b4ac6-267">Di conseguenza, i risultati di `MeasureSuperpositionArray` su `n=4` qubits vengono recuperati tramite</span><span class="sxs-lookup"><span data-stu-id="b4ac6-267">Hence the results of `MeasureSuperpositionArray` on `n=4` qubits would fetched via</span></span> 

```csharp
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);
```

<span data-ttu-id="b4ac6-268">Un programma host C# completo potrebbe quindi essere simile a</span><span class="sxs-lookup"><span data-stu-id="b4ac6-268">A full C# host program could thus look like</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine($"Multiple qubit result: {multiQubitResult}");
        }
    }
}
```

<span data-ttu-id="b4ac6-269">Nel percorso del file C#, è possibile eseguire il programma host dal prompt dei comandi immettendo</span><span class="sxs-lookup"><span data-stu-id="b4ac6-269">At the location of the C# file, the host program can be run from the command prompt by entering</span></span>
```dotnetcli
dotnet run
```
<span data-ttu-id="b4ac6-270">e in questo caso verrà visualizzato un output scritto nella console simile a</span><span class="sxs-lookup"><span data-stu-id="b4ac6-270">and in this case you will see output written to the console similar to</span></span> 
```output
Single qubit result: One
Multiple qubit result: [One,One,Zero,Zero]
```

> [!NOTE]
> <span data-ttu-id="b4ac6-271">A causa dell'interoperabilità del compilatore con gli spazi dei nomi, è possibile rendere Q# disponibili le richiamabili senza l' `using NamespaceName;` istruzione e semplicemente abbinando il titolo dello spazio dei nomi C#.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-271">Due to the compiler's interoperability with namespaces, we could alternatively make our Q# callables available without the `using NamespaceName;` statement, and simply matching the C# namespace title to it.</span></span>
> <span data-ttu-id="b4ac6-272">Ovvero sostituendo `namespace host` con `namespace NamespaceName` .</span><span class="sxs-lookup"><span data-stu-id="b4ac6-272">That is, by replacing `namespace host` with `namespace NamespaceName`.</span></span>

#### <a name="including-the-resources-estimator"></a><span data-ttu-id="b4ac6-273">Inclusione dello strumento di stima delle risorse</span><span class="sxs-lookup"><span data-stu-id="b4ac6-273">Including the resources estimator</span></span>

<span data-ttu-id="b4ac6-274">[`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator)Richiede un'implementazione leggermente diversa per recuperare l'output.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-274">The [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) requires a slightly different implementation to retrieve the output.</span></span>

<span data-ttu-id="b4ac6-275">In primo luogo, invece di crearne un'istanza come variabile con un' `using` istruzione, come in questo caso `QuantumSimulator` , viene creata un'istanza più direttamente di oggetti della classe tramite</span><span class="sxs-lookup"><span data-stu-id="b4ac6-275">Firstly, instead of instantiating them as a variable with a `using` statement (as we do with the `QuantumSimulator`), we more directly instantiate objects of the class via</span></span>

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

<span data-ttu-id="b4ac6-276">Si noti che invece di un singolo simulatore di destinazione deve essere usato da più Q# operazioni, ne è stata creata un'istanza per ciascuna.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-276">Notice that instead of a single target simulator to be used by multiple Q# operations, we have instantiated one for each.</span></span> <span data-ttu-id="b4ac6-277">Poiché gli oggetti stessi vengono modificati quando vengono utilizzati come computer di destinazione e i relativi risultati possono quindi essere recuperati successivamente con il metodo della classe `.ToTSV()` .</span><span class="sxs-lookup"><span data-stu-id="b4ac6-277">This is because the objects themselves are modified when used as target machines, and their results can then be retrieved afterwards with the class method `.ToTSV()`.</span></span>

<span data-ttu-id="b4ac6-278">Per eseguire le operazioni sugli estimatori di risorse, si usa</span><span class="sxs-lookup"><span data-stu-id="b4ac6-278">To run the operations on the resource estimators, we use</span></span>

```csharp
            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);
```
<span data-ttu-id="b4ac6-279">e quindi recuperare i risultati come valori delimitati da tabulazioni (TSV) con `estimatorSingleQ.ToTSV()` e `estimatorMultiQ.ToTSV()` .</span><span class="sxs-lookup"><span data-stu-id="b4ac6-279">and then fetch the results as tab-separated-values (TSV) with `estimatorSingleQ.ToTSV()` and `estimatorMultiQ.ToTSV()`.</span></span>

<span data-ttu-id="b4ac6-280">Pertanto, un programma host C# completo che utilizza sia `QuantumSimulator` che `ResourcesEstimator` può assumere il formato seguente:</span><span class="sxs-lookup"><span data-stu-id="b4ac6-280">So, a full C# host program making use of both the `QuantumSimulator` and `ResourcesEstimator` could take the form:</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine("Single qubit resources:");
            Console.WriteLine(estimatorSingleQ.ToTSV());

            Console.WriteLine($"\nMultiple qubit result: {multiQubitResult}");
            Console.WriteLine("Multiple qubit resources:");
            Console.WriteLine(estimatorMultiQ.ToTSV());
        }
    }
}
```


<span data-ttu-id="b4ac6-281">che restituisce un output simile a</span><span class="sxs-lookup"><span data-stu-id="b4ac6-281">which would yield output similar to</span></span>

```output
Single qubit result: One
Single qubit resources:
Metric          Sum
CNOT            0
QubitClifford   1
R               0
Measure         1
T               0
Depth           0
Width           1
BorrowedWidth   0

Multiple qubit result: [One,One,One,Zero]
Multiple qubit resources:
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

***

## <a name="no-locq-jupyter-notebooks"></a><span data-ttu-id="b4ac6-282">Q# Notebook di Jupyter</span><span class="sxs-lookup"><span data-stu-id="b4ac6-282">Q# Jupyter Notebooks</span></span>
<span data-ttu-id="b4ac6-283">Q# I notebook di Jupyter usano il kernel i Q# , che consente di definire, compilare ed eseguire Q# Callable in un unico notebook---tutti insieme a istruzioni, note e altro contenuto.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-283">Q# Jupyter Notebooks make use of the IQ# kernel, which allows you to define, compile, and run Q# callables in a single notebook---all alongside instructions, notes, and other content.</span></span>
<span data-ttu-id="b4ac6-284">Ciò significa che, sebbene sia possibile importare e utilizzare il contenuto dei `*.qs` Q# file, non sono necessari nel modello di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-284">This means that while it is possible to import and use the contents of `*.qs` Q# files, they are not necessary in the run model.</span></span>

<span data-ttu-id="b4ac6-285">In questo articolo verrà illustrato in dettaglio come eseguire le Q# operazioni definite in precedenza, ma un'introduzione più ampia all'uso di Q# notebook di Jupyter è disponibile in [Introduzione ai Q# notebook di e Jupyter](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).</span><span class="sxs-lookup"><span data-stu-id="b4ac6-285">Here, we will detail how to run the Q# operations defined above, but a more broad introduction to using Q# Jupyter Notebooks is provided at [Intro to Q# and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).</span></span>

### <a name="defining-operations"></a><span data-ttu-id="b4ac6-286">Definizione di operazioni</span><span class="sxs-lookup"><span data-stu-id="b4ac6-286">Defining operations</span></span>

<span data-ttu-id="b4ac6-287">In una Q# Jupyter notebook, immettere Q# il codice esattamente come si farebbe dall'interno dello spazio dei nomi di un Q# file.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-287">In a Q# Jupyter Notebook, you enter Q# code just as we would from inside the namespace of a Q# file.</span></span>

<span data-ttu-id="b4ac6-288">È quindi possibile abilitare l'accesso alle funzioni chiamabili dalle [ Q# librerie standard](xref:microsoft.quantum.libraries.standard.intro) con `open` istruzioni per i rispettivi spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-288">So, we can enable access to callables from the [Q# standard libraries](xref:microsoft.quantum.libraries.standard.intro) with `open` statements for their respective namespaces.</span></span>
<span data-ttu-id="b4ac6-289">Quando si esegue una cella con tale istruzione, le definizioni di tali spazi dei nomi sono disponibili nell'area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-289">Upon running a cell with such a statement, the definitions from those namespaces are available throughout the workspace.</span></span>

> [!NOTE]
> <span data-ttu-id="b4ac6-290">Le Callable da [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic) e [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon) (ad esempio, [`H`](xref:Microsoft.Quantum.Intrinsic.H) e [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) ) sono automaticamente disponibili per le operazioni definite all'interno di celle in Q# Jupyter notebook.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-290">Callables from [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic) and [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon) (for example, [`H`](xref:Microsoft.Quantum.Intrinsic.H) and [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach)) are automatically available to operations defined within cells in Q# Jupyter Notebooks.</span></span>
> <span data-ttu-id="b4ac6-291">Tuttavia, questo non è vero per il codice introdotto da Q# file di origine esterni (un processo illustrato in [Introduzione ai Q# notebook di Jupyter](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)).</span><span class="sxs-lookup"><span data-stu-id="b4ac6-291">However, this is not true for code brought in from external Q# source files (a process shown at [Intro to Q# and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)).</span></span> 
> 

<span data-ttu-id="b4ac6-292">Analogamente, per la definizione delle operazioni è necessario scrivere solo il Q# codice ed eseguire la cella.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-292">Similarly, defining operations requires only writing the Q# code and running the cell.</span></span>

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining Q# operations" width="773">

<span data-ttu-id="b4ac6-293">L'output elenca quindi le operazioni che possono essere chiamate dalle celle future.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-293">The output then lists those operations, which can then be called from future cells.</span></span>

### <a name="target-machines"></a><span data-ttu-id="b4ac6-294">Computer di destinazione</span><span class="sxs-lookup"><span data-stu-id="b4ac6-294">Target machines</span></span>

<span data-ttu-id="b4ac6-295">La funzionalità per l'esecuzione di operazioni su computer di destinazione specifici viene fornita tramite [i Q# Comandi Magic](xref:microsoft.quantum.guide.quickref.iqsharp).</span><span class="sxs-lookup"><span data-stu-id="b4ac6-295">The functionality to run operations on specific target machines is provided via [IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp).</span></span>
<span data-ttu-id="b4ac6-296">Ad esempio, USA `%simulate` l'oggetto `QuantumSimulator` e `%estimate` Usa `ResourcesEstimator` :</span><span class="sxs-lookup"><span data-stu-id="b4ac6-296">For example, `%simulate` makes use of the `QuantumSimulator`, and `%estimate` uses the `ResourcesEstimator`:</span></span>

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Jupyter cell simulating a Q# operation and running resource estimation" width="773">

### <a name="passing-inputs-to-functions-and-operations"></a><span data-ttu-id="b4ac6-297">Passaggio di input a funzioni e operazioni</span><span class="sxs-lookup"><span data-stu-id="b4ac6-297">Passing inputs to functions and operations</span></span>

<span data-ttu-id="b4ac6-298">Per passare gli input alle Q# operazioni, gli argomenti possono essere passati come `key=value` coppie al comando Run Magic.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-298">To pass inputs to the Q# operations, the arguments can be passed as `key=value` pairs to the run magic command.</span></span>
<span data-ttu-id="b4ac6-299">Quindi, per eseguire `MeasureSuperpositionArray` con quattro qubits, è possibile eseguire `%simulate MeasureSuperpositionArray n=4` :</span><span class="sxs-lookup"><span data-stu-id="b4ac6-299">So, to run `MeasureSuperpositionArray` with four qubits, we can run `%simulate MeasureSuperpositionArray n=4`:</span></span>

<img src="../media/hostprograms_jupyter_args_sim_crop.png" alt="Jupyter cell simulating a Q# operation with arguments" width="773">

<span data-ttu-id="b4ac6-300">Questo modello può essere usato in modo analogo con `%estimate` e altri comandi di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-300">This pattern can be used similarly with `%estimate` and other run commands.</span></span>

### <a name="using-no-locq-code-from-other-projects-or-packages"></a><span data-ttu-id="b4ac6-301">Uso Q# del codice da altri progetti o pacchetti</span><span class="sxs-lookup"><span data-stu-id="b4ac6-301">Using Q# code from other projects or packages</span></span>

<span data-ttu-id="b4ac6-302">Per impostazione predefinita, un Q# Jupyter notebook carica tutti i `.qs` file nella cartella corrente e rende disponibili le Q# operazioni e le funzioni da usare all'interno del notebook.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-302">By default, a Q# Jupyter Notebook loads all of the `.qs` files in the current folder and makes their Q# operations and functions available for use from inside the notebook.</span></span> <span data-ttu-id="b4ac6-303">Il [ `%who` comando Magic](xref:microsoft.quantum.iqsharp.magic-ref.who) elenca tutte Q# le operazioni e le funzioni attualmente disponibili.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-303">The [`%who` magic command](xref:microsoft.quantum.iqsharp.magic-ref.who) lists all currently-available Q# operations and functions.</span></span>

<span data-ttu-id="b4ac6-304">Per caricare Q# il codice da un'altra cartella, è possibile usare il [ `%project` comando Magic](xref:microsoft.quantum.iqsharp.magic-ref.project) per aggiungere un riferimento a un `.csproj` file per un Q# progetto, ovvero un progetto che fa riferimento a `Microsoft.Quantum.Sdk` .</span><span class="sxs-lookup"><span data-stu-id="b4ac6-304">To load Q# code from another folder, the [`%project` magic command](xref:microsoft.quantum.iqsharp.magic-ref.project) can be used to add a reference to a `.csproj` file for a Q# project (that is, a project that references `Microsoft.Quantum.Sdk`).</span></span> <span data-ttu-id="b4ac6-305">Tramite questo comando vengono compilati tutti `.qs` i file nella cartella contenente le `.csproj` sottocartelle (e).</span><span class="sxs-lookup"><span data-stu-id="b4ac6-305">This command will compile any `.qs` files in the folder containing the `.csproj` (and subfolders).</span></span> <span data-ttu-id="b4ac6-306">Inoltre, caricherà in modo ricorsivo tutti i pacchetti a cui viene fatto riferimento tramite `PackageReference` o i Q# progetti a cui viene fatto riferimento tramite `ProjectReference` in tale `.csproj` file.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-306">It will also recursively load any packages referenced via `PackageReference` or Q# projects referenced via `ProjectReference` in that `.csproj` file.</span></span> 

<span data-ttu-id="b4ac6-307">Ad esempio, nelle celle seguenti viene simulata un' Q# operazione da un progetto esterno, in cui viene fatto riferimento al percorso del progetto relativo alla cartella corrente:</span><span class="sxs-lookup"><span data-stu-id="b4ac6-307">As an example, the following cells simulate a Q# operation from an external project, where the project path is referenced relative to the current folder:</span></span>

<img src="../media/hostprograms_jupyter_project_crop.png" alt="Jupyter cell simulating a Q# operation from an external project" width="773">

<span data-ttu-id="b4ac6-308">Per caricare pacchetti esterni contenenti Q# codice, utilizzare il [ `%package` comando Magic](xref:microsoft.quantum.iqsharp.magic-ref.package).</span><span class="sxs-lookup"><span data-stu-id="b4ac6-308">To load external packages containing Q# code, use the [`%package` magic command](xref:microsoft.quantum.iqsharp.magic-ref.package).</span></span>
<span data-ttu-id="b4ac6-309">Il caricamento di un pacchetto renderà disponibili anche tutti i comandi Magic personalizzati o i codificatori di visualizzazione contenuti in tutti gli assembly che fanno parte del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-309">Loading a package will also make available any custom magic commands or display encoders that are contained in any assemblies that are part of the package.</span></span>

<span data-ttu-id="b4ac6-310">Per caricare pacchetti o Q# progetti esterni in inizializzazione della tempo del notebook, verificare che la cartella del notebook contenga un `.csproj` file a cui fa riferimento `Microsoft.Quantum.Sdk` .</span><span class="sxs-lookup"><span data-stu-id="b4ac6-310">To load external packages or Q# projects at notebook intialization time, ensure that the notebook folder contains a `.csproj` file which references `Microsoft.Quantum.Sdk`.</span></span> <span data-ttu-id="b4ac6-311">`.csproj`Aggiungere la proprietà `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` a `<PropertyGroup>` .</span><span class="sxs-lookup"><span data-stu-id="b4ac6-311">In that `.csproj`, add the property `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` to the `<PropertyGroup>`.</span></span> <span data-ttu-id="b4ac6-312">In questo modo si indicherà Q# di caricare in modo ricorsivo tutti `ProjectReference` `PackageReference` gli elementi trovati in tale `.csproj` data in fase di caricamento del notebook.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-312">This will instruct IQ# to recursively load any `ProjectReference` or `PackageReference` items found in that `.csproj` at notebook load time.</span></span>

<span data-ttu-id="b4ac6-313">Ad esempio, di seguito è riportato un semplice `.csproj` file che consente Q# di caricare automaticamente il `Microsoft.Quantum.Chemistry` pacchetto:</span><span class="sxs-lookup"><span data-stu-id="b4ac6-313">For example, here is a simple `.csproj` file that causes IQ# to automatically load the `Microsoft.Quantum.Chemistry` package:</span></span>

```xml
<Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    <PropertyGroup>
        <OutputType>Library</OutputType>
        <TargetFramework>netstandard2.1</TargetFramework>
        <IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>
    </PropertyGroup>
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Chemistry" Version="0.12.20072031" />
    </ItemGroup>
</Project>
```

> [!NOTE]
> <span data-ttu-id="b4ac6-314">Attualmente questa `<IQSharpLoadAutomatically>` proprietà personalizzata è richiesta dagli Q# host Jupyter notebook, ma in futuro può diventare il comportamento predefinito per un `.csproj` file che si trova nella stessa cartella del file del notebook.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-314">Currently this custom `<IQSharpLoadAutomatically>` property is required by Q# Jupyter Notebook hosts, but in the future, this may become the default behavior for a `.csproj` file located in the same folder as the notebook file.</span></span>

> [!NOTE]
> <span data-ttu-id="b4ac6-315">Attualmente l' `<QsharpCompile>` impostazione in `.csproj` viene ignorata dagli Q# host Jupyter notebook e tutti i `.qs` file nella cartella di `.csproj` (incluse le sottocartelle) vengono caricati e compilati.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-315">Currently the `<QsharpCompile>` setting in the `.csproj` is ignored by Q# Jupyter Notebook hosts, and all `.qs` files in the folder of the `.csproj` (including subfolders) are loaded and compiled.</span></span> <span data-ttu-id="b4ac6-316">Il supporto per `.csproj` le impostazioni verrà migliorato in futuro (vedere [iqsharp # 277](https://github.com/microsoft/iqsharp/issues/277) per altri dettagli).</span><span class="sxs-lookup"><span data-stu-id="b4ac6-316">Support for `.csproj` settings will be improved in the future (see [iqsharp#277](https://github.com/microsoft/iqsharp/issues/277) for more details).</span></span>
