---
title: Note sulla versione del kit di sviluppo Quantum
description: Informazioni sugli aggiornamenti più recenti per Microsoft Quantum Development Kit (anteprima).
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
uid: microsoft.quantum.relnotes
ms.openlocfilehash: e48f4157438fba063877b2b79fbc7629710fc9f3
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274803"
---
# <a name="microsoft-quantum-development-kit-release-notes"></a>Note sulla versione di Microsoft Quantum Development Kit

Questo articolo contiene informazioni su tutte le versioni di Quantum Development Kit.

Per le istruzioni sull'installazione, vedere la [Guida all'installazione](xref:microsoft.quantum.install).

Per le istruzioni sull'aggiornamento, vedere la [Guida all'aggiornamento](xref:microsoft.quantum.update).

## <a name="version-0112006403"></a>Versione 0.11.2006.403

*Data di rilascio: 4 giugno 2020*

In questa versione viene corretto un bug che riguarda la compilazione di progetti Q#.

## <a name="version-0112006207"></a>Versione 0.11.2006.207

*Data di rilascio: 3 giugno 2020*

Questa versione contiene quanto segue:

- I notebook Q# e i programmi host Python non genereranno più errori se è presente un punto di ingresso Q#
- Aggiornamenti della [libreria standard](xref:microsoft.quantum.libraries.standard.intro) per l'uso di modificatori di accesso
- Il compilatore ora consente l'inserimento di passaggi di riscrittura tra passaggi di riscrittura predefiniti
- Diverse funzioni e operazioni deprecate sono state rimosse in seguito alla pianificazione descritta nei [principi per le API](xref:microsoft.quantum.contributing.api-design). I programmi e le librerie Q# compilati senza avvisi nella versione 0.11.2004.2825 continueranno a funzionare senza modifiche.

Vedere l'elenco completo delle richieste pull chiuse relative a [librerie](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compilatore](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [esempi](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed), [IQ#](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) e [kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

> [!NOTE]
> Questa versione contiene un bug che riguarda la compilazione di progetti Q#. È consigliabile eseguire l'aggiornamento a una versione più recente.

## <a name="version-01120042825"></a>Versione 0.11.2004.2825

*Data di rilascio: 30 aprile 2020*

Questa versione contiene quanto segue:

- Nuovo supporto per le applicazioni della riga di comando di Q#, che non richiedono più un file host Python o C#. Per altre informazioni su come iniziare a usare le applicazioni della riga di comando di Q#, vedere [qui](xref:microsoft.quantum.install.standalone).
- È stata aggiornata la guida di avvio rapido del generatore quantistico di numero casuali per non richiedere più un file host C# o Python. Vedere la guida di [avvio rapido](xref:microsoft.quantum.quickstarts.qrng) aggiornata
- Miglioramenti delle prestazioni alle immagini Docker per IQ#

> [!NOTE]
> Attualmente non è possibile chiamare le applicazioni della riga di comando di Q# che usano il nuovo attributo [`@EntryPoint()`](xref:microsoft.quantum.core.entrypoint) da programmi host Python o .NET.
> Per altre informazioni, vedere le guide all'interoperabilità di [Python](xref:microsoft.quantum.install.python) e [.NET](xref:microsoft.quantum.install.cs).

## <a name="version-01120033107"></a>Versione 0.11.2003.3107

*Data di rilascio: 31 marzo 2020*

Questa versione contiene correzioni di bug secondari per la versione 0.11.2003.2506.

## <a name="version-01120032506"></a>Versione 0.11.2003.2506

*Data di rilascio: 26 marzo 2020*

Questa versione contiene quanto segue:

- Aggiunta del supporto per i modificatori di accesso in Q#. Per altre informazioni, vedere [Strutture di file](xref:microsoft.quantum.guide.filestructure)
- Aggiornamento a .NET Core SDK 3.1

Vedere l'elenco completo delle richieste pull chiuse relative a [librerie](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compilatore](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [esempi](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) e [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-01020022610"></a>Versione 0.10.2002.2610

*Data di rilascio: 27 febbraio 2020*

Questa versione contiene quanto segue:

- Nuova libreria di apprendimento automatico quantistico. Per altre informazioni, vedere la [pagina della documentazione sull'apprendimento automatico quantistico](https://docs.microsoft.com/quantum/libraries/machine-learning/?view=qsharp-preview).
- Correzioni di bug di IQ#, che consentono di incrementare di 10-20 volte le prestazioni durante il caricamento di pacchetti NuGet

Vedere l'elenco completo delle richieste pull chiuse relative a [librerie](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compilatore](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [esempi](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) e [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-01020012831"></a>Versione 0.10.2001.2831

*Data di rilascio: 29 gennaio 2020*

Questa versione contiene quanto segue:

- Nuovo pacchetto NuGet Microsoft.Quantum.SDK che sostituirà il pacchetto NuGet Microsoft.Quantum.Development.Kit quando si creano nuovi progetti. Il pacchetto NuGet Microsoft.Quantum.Development.Kit continuerà a essere supportato per i progetti esistenti. 
- Supporto per le estensioni del compilatore Q#, abilitate dal nuovo pacchetto NuGet Microsoft.Quantum.SDK. Per altre informazioni, vedere la [documentazione su GitHub](https://github.com/microsoft/qsharp-compiler/tree/master/src/QuantumSdk#extending-the-q-compiler), l'[di esempio relativo alle estensioni del compilatore](https://github.com/microsoft/qsharp-compiler/tree/master/examples/CompilerExtensions) e il [blog degli sviluppatori Q#](https://devblogs.microsoft.com/qsharp/extending-the-q-compiler/).
- Aggiunto il supporto per .NET Core 3.1. È consigliabile installare la versione 3.1.100 perché la compilazione con versioni di .NET Core SDK precedenti può causare problemi
- Nuove trasformazioni del compilatore disponibili in Microsoft.Quantum.QsCompiler.Experimental
- Nuove funzionalità per esporre i vettori di stato di output come HTML in IQ#
- Aggiunto il supporto per EstimateFrequencyA in Microsoft.Quantum.Characterization per i test Hadamard e SWAP
- Lo spazio dei nomi AmplitudeAmplification ora usa la guida di stile Q#

Vedere l'elenco completo delle richieste pull chiuse relative a [librerie](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compilatore](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [esempi](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) e [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-01019120501"></a>Versione 0.10.1912.0501

*Data di rilascio: 5 dicembre 2019*

Questa versione contiene quanto segue:

- Nuovo attributo Test per il testing unità Q#. Vedere la documentazione aggiornata dell'API disponibile [qui](https://docs.microsoft.com/qsharp/api/qsharp/microsoft.quantum.diagnostics.test) e la guida aggiornata su test e debug disponibile [qui](xref:microsoft.quantum.guide.testingdebugging)
- Aggiunta dell'analisi dello stack in caso di errore di esecuzione del programma Q#
- Supporto per punti di interruzione in Visual Studio Code in seguito a un aggiornamento nell'[estensione C# per Visual Studio Code di OmniSharp](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)

Vedere l'elenco completo delle richieste pull chiuse relative a [librerie](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compilatore](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [esempi](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) e [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-01019111607"></a>Versione 0.10.1911.1607

*Data di rilascio: 17 novembre 2019*

Questa versione contiene quanto segue:

- Correzione delle prestazioni per notebook di [Quantum Katas](https://github.com/Microsoft/QuantumKatas) e Jupyter

Vedere l'elenco completo delle richieste pull chiuse relative a [librerie](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compilatore](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [esempi](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) e [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  


## <a name="version-0101911307"></a>Versione 0.10.1911.307

*Data di rilascio: 1° novembre 2019*

Questa versione contiene quanto segue:

- Aggiornamenti delle estensioni di Visual Studio Code e Visual Studio per la distribuzione di server di linguaggio come eseguibili autonomi, eliminando la necessità della dipendenza da versioni di .NET Core SDK  
- Migrazione a .NET Core 3.0
- Modifica di rilievo apportata a Microsoft.Quantum.Simulation.Core.IOperationFactory con l'introduzione del nuovo metodo `Fail`. Influisce solo sui simulatori personalizzati che non estendono SimulatorBase. Per altre informazioni, [vedere la richiesta pull in GitHub](https://github.com/microsoft/qsharp-runtime/pull/59).
- Nuovo supporto per attributi deprecati

Vedere l'elenco completo delle richieste pull chiuse relative a [librerie](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compilatore](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [esempi](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) e [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-0919093002"></a>Versione 0.9.1909.3002

*Data di rilascio: 30 settembre 2019*

Questa versione contiene quanto segue:

- Nuovo supporto per il completamento del codice Q# in Visual Studio 2019 (versioni 16.3 e successive) e Visual Studio Code
- Nuovo [Quantum Kata](https://github.com/Microsoft/QuantumKatas) per gli addizionatori quantistici

Vedere l'elenco completo delle richieste pull chiuse relative a [librerie](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compilatore](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [esempi](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) e [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-09-packagereference-0919082902"></a>Versione 0.9 (*PackageReference 0.9.1908.2902*)

*Data di rilascio: 29 agosto 2019*

Questa versione contiene quanto segue:

- Nuovo supporto per le [istruzioni di coniugazione](xref:microsoft.quantum.guide.operationsfunctions#conjugations) in Q#
- Nuove azioni di codice nel compilatore, ad esempio "replace with", "add documentation" e aggiornamento degli elementi di matrici semplici
- Aggiunta dei comandi per l'installazione di modelli e la creazione di un nuovo progetto all'estensione di Visual Studio Code
- Aggiunta di nuove varianti del combinatore ApplyIf, ad esempio [Microsoft.Quantum.Canon.ApplyIfOne](xref:microsoft.quantum.canon.applyifone)
- Conversione di altri [Quantum Kata](https://github.com/Microsoft/QuantumKatas) in Jupyter Notebook
- L'estensione di Visual Studio richiede ora Visual Studio 2019

Vedere l'elenco completo delle richieste pull chiuse relative a [librerie](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compilatore](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [esempi](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) e [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

Di seguito vengono riepilogate le modifiche insieme alle istruzioni per l'aggiornamento dei programmi esistenti.  Per altre informazioni su queste modifiche, vedere il [blog degli sviluppatori Q#](https://devblogs.microsoft.com/qsharp).

## <a name="version-08-packagereference-0819071701"></a>Versione 0.8 (*PackageReference 0.8.1907.1701*)

*Data di rilascio: 12 luglio 2019*

Questa versione contiene quanto segue:

- Nuovi percorsi di indicizzazione per le matrici di sezionamento. Per altri dettagli, vedere le [informazioni di riferimento sul linguaggio](xref:microsoft.quantum.guide.expressions#array-slices).
- Aggiunta di Dockerfile ospitato nel [registro contenitori di Microsoft](https://github.com/microsoft/ContainerRegistry). Per altre informazioni, vedere il [repository IQ#](https://github.com/microsoft/iqsharp/blob/master/README.md)
- Modifica di rilievo per il [simulatore di traccia](xref:microsoft.quantum.machines.qc-trace-simulator.intro), aggiornamento delle impostazioni di configurazione, modifiche dei nomi. Per informazioni sui nomi aggiornati, vedere il [browser di API .NET](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulatorconfiguration).

Vedere l'elenco completo delle richieste pull chiuse relative a [librerie](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) ed [esempi](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-07-packagereference-0719053109"></a>Versione 0.7 (*PackageReference 0.7.1905.3109*)

*Data di rilascio: 31 maggio 2019*

Questa versione contiene quanto segue:
- Aggiunte al linguaggio Q# 
- Aggiornamenti della libreria di chimica 
- Nuova libreria per il calcolo numerico.

Vedere l'elenco completo delle richieste pull chiuse relative a [librerie](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) ed [esempi](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).  

Di seguito vengono riepilogate le modifiche insieme alle istruzioni per l'aggiornamento dei programmi esistenti.  Per altre informazioni su queste modifiche, vedere il [blog degli sviluppatori Q#](https://devblogs.microsoft.com/qsharp).

### <a name="q-language-syntax"></a>Sintassi del linguaggio Q#
In questa versione è stata aggiunta una nuova sintassi del linguaggio Q#:
* Aggiunta di elementi denominati per i [tipi definiti dall'utente](xref:microsoft.quantum.guide.types#user-defined-types).  
* È ora possibile usare i costruttori di tipi definiti dall'utente come funzioni.
* Aggiunta del supporto per le operazioni di [copia e aggiornamento](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) e [applicazione e riassegnazione](xref:microsoft.quantum.guide.variables#rebinding-of-mutable-symbols) nei tipi definiti dall'utente.
* Il blocco di correzioni per i cicli di [ripetizione fino al completamento](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop) è ora facoltativo.
* Sono ora supportati i cicli while nelle funzioni (non nelle operazioni).

### <a name="library"></a>Libreria 

In questa versione è stata aggiunta una nuova libreria per il calcolo numerico. Per altre informazioni, vedere come [usare la nuova libreria per il calcolo numerico](xref:microsoft.quantum.numerics.usage) e provare i [nuovi esempi](https://github.com/microsoft/quantum/tree/master/Numerics).  [Richiesta pull 102](https://github.com/Microsoft/QuantumLibraries/pull/102).  

In questa versione la libreria di chimica è stata riorganizzata, ampliata e aggiornata:
* Maggiore modularità dei componenti, estendibilità, pulizia generale del codice.  [Richiesta pull 58](https://github.com/microsoft/QuantumLibraries/pull/58).
* Aggiunta del supporto per [funzioni d'onda multi-riferimento](xref:microsoft.quantum.chemistry.concepts.multireference), sia funzioni d'onda multi-riferimento sparse che cluster ad accoppiamento unitario.  [Richiesta pull 110](https://github.com/Microsoft/QuantumLibraries/pull/110).
* (Grazie!) Collaboratore [1QBit](https://1qbit.com) ([@valentinS4t1qbit](https://github.com/ValentinS4t1qbit)): Valutazione dell'energia con ansatz variazionale. [Richiesta pull 120](https://github.com/Microsoft/QuantumLibraries/pull/120).
* Aggiornamento dello schema [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) alla nuova [versione 0.2](xref:microsoft.quantum.libraries.chemistry.schema.spec_v_0_2), aggiunta della specifica del cluster ad accoppiamento unitario. [Problema 65](https://github.com/microsoft/QuantumLibraries/issues/65).
* Aggiunta dell'interoperabilità di Python alle funzioni della libreria di chimica. Provare questo [esempio](https://github.com/microsoft/Quantum/tree/master/Chemistry/PythonIntegration). [Problema #53](https://github.com/microsoft/QuantumLibraries/issues/53) [Richiesta pull #110](https://github.com/Microsoft/QuantumLibraries/pull/110).

## <a name="version-061905"></a>Versione 0.6.1905

*Data di rilascio: 3 maggio 2019*

Questa versione contiene quanto segue:
- Aggiunta di modifiche al linguaggio Q# 
- Ristrutturazione delle librerie di Quantum Development Kit 
- Aggiunta di nuovi esempi 
- Correzione dei bug.  Diverse richieste pull chiuse relative a [librerie](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) ed [esempi](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).  

Di seguito vengono riepilogate le modifiche insieme alle istruzioni per l'aggiornamento dei programmi esistenti.  Per altre informazioni su queste modifiche, visitare la pagina devblogs.microsoft.com/qsharp.

### <a name="q-language-syntax"></a>Sintassi del linguaggio Q#
In questa versione è stata aggiunta una nuova sintassi del linguaggio Q#:
* Aggiunta di un [modo abbreviato per esprimere le specializzazioni delle operazioni quantistiche](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations) (controllo e operatori aggiunti) con operatori `+`.  La sintassi precedente è deprecata.  I programmi che usano la sintassi precedente (ad esempio `: adjoint`) continueranno a funzionare, ma verrà generato un avviso in fase di compilazione.  
* Aggiunta di un nuovo operatore per l'operazione di [copia e aggiornamento](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions), `w/`, che è possibile usare per esprimere la creazione di matrici come modifica di una matrice esistente.
* Aggiunta dell'istruzione comune di [applicazione e aggiornamento](xref:microsoft.quantum.guide.variables#rebinding-of-mutable-symbols), ad esempio `+=`, `w/=`.
* Aggiunta di un modo per specificare un nome breve per gli spazi dei nomi in [direttive open](xref:microsoft.quantum.guide.filestructure#open-directives).

In questa versione non è più consentito specificare un elemento di matrice sul lato sinistro di un'istruzione set.  Il motivo è che questa sintassi implica che le matrici sono modificabili quando in realtà il risultato dell'operazione è sempre stato la creazione di una nuova matrice con la modifica.  Verrà invece generato un errore del compilatore con il suggerimento di usare il nuovo operatore di copia e aggiornamento, `w/`, per ottenere lo stesso risultato.  

### <a name="library-restructuring"></a>Ristrutturazione delle librerie
In questa versione le librerie sono state riorganizzate per favorirne la crescita in modo coerente:
* Lo spazio dei nomi Microsoft.Quantum.Primitive è stato rinominato in Microsoft.Quantum.Intrinsic.  Queste operazioni sono implementate dal computer di destinazione.  Lo spazio dei nomi Microsoft.Quantum.Primitive è deprecato.  Un avviso del runtime indicherà quando i programmi chiamano operazioni e funzioni con nomi deprecati.

* Il pacchetto Microsoft.Quantum.Canon è stato rinominato in Microsoft.Quantum.Standard.  Questo pacchetto contiene gli spazi dei nomi comuni alla maggior parte dei programmi Q#.  ad esempio:  
    - Microsoft.Quantum.Canon per operazioni comuni
    - Microsoft.Quantum.Arithmetic per operazioni aritmetiche di utilizzo generico
    - Microsoft.Quantum.Preparation per le operazioni usate per preparare lo stato dei qubit
    - Microsoft.Quantum.Simulation per la funzionalità di simulazione

Con questa modifica, nei programmi che includono una singola istruzione "open" per lo spazio dei nomi Microsoft.Quatum.Canon si possono verificare errori di compilazione se viene fatto riferimento a operazioni che sono state spostate negli altri tre nuovi spazi dei nomi.  L'aggiunta di altre istruzioni open per i tre nuovi spazi dei nomi offre la possibilità di risolvere rapidamente questo problema.  

* Diversi spazi dei nomi sono stati deprecati perché le operazioni al loro interno sono state riorganizzate in altri spazi dei nomi. I programmi che usano questi spazi dei nomi continueranno a funzionare e un avviso in fase di compilazione indicherà lo spazio dei nomi in cui è definita l'operazione.  

* Lo spazio dei nomi Microsoft.Quantum.Arithmetic è stato normalizzato per l'uso del tipo definito dall'utente <xref:microsoft.quantum.arithmetic.littleendian>. Usare la funzione [BigEndianAsLittleEndian](xref:microsoft.quantum.arithmetic.bigendianaslittleendian) quando è necessario eseguire la conversione in little endian.  

* I nomi di diversi funzioni e operazioni chiamabili sono stati cambiati per la conformità alla [Guida di stile di Q#](xref:microsoft.quantum.contributing.style).  I nomi delle funzioni e operazioni chiamabili precedenti sono deprecati.  I programmi che li usano continueranno a funzionare con un avviso in fase di compilazione. 

### <a name="new-samples"></a>Nuovi esempi

È stato aggiunto un [esempio dell'uso di Q# con il driver F#](https://github.com/Microsoft/Quantum/pull/164).  

**Grazie** al collaboratore seguente che ha contribuito per la base di codice open source all'indirizzo http://github.com/Microsoft/Quantum. Questi contributi arricchiscono ulteriormente gli esempi avanzati di codice Q#:

* Mathias Soeken ([@msoeken](https://github.com/msoeken)): Sintesi delle funzioni di Oracle. [Richiesta pull 135](https://github.com/Microsoft/Quantum/pull/135).

### <a name="migrating-existing-projects-to-061905"></a>Migrazione dei progetti esistenti a 0.6.1905.

Per aggiornare QDK, vedere la [Guida all'installazione](xref:microsoft.quantum.install).
  
Se sono presenti progetti Q# della versione 0.5 di Quantum Development Kit, di seguito è riportata la procedura per eseguirne la migrazione alla versione più recente.

    1. I progetti devono essere aggiornati nell'ordine indicato.  Se una soluzione include più progetti, aggiornare ognuno nell'ordine in cui vi si fa riferimento.
    2. Da una riga di comando eseguire `dotnet clean` per rimuovere tutti i file binari e i file intermedi esistenti.
    3. In un editor di testo modificare il file con estensione csproj per sostituire la versione di tutte le istruzioni `PackageReference` relative a "Microsoft. Quantum" con la versione 0.6.1904 e cambiare il nome del pacchetto "Microsoft.Quantum.Canon" in "Microsoft.Quantum.Standard", ad esempio:

         ```xml
        <PackageReference Include="Microsoft.Quantum.Standard" Version="0.6.1905.301" />
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.6.1905.301" />
        ```
    4. Dalla riga di comando eseguire questo comando: `dotnet msbuild`  
    5. Al termine, può comunque essere necessario risolvere manualmente gli errori dovuti alle modifiche di cui sopra.  In molti casi, questi errori verranno segnalati anche da IntelliSense in Visual Studio o Visual Studio Code.
        - Aprire la cartella radice del progetto o della soluzione che lo contiene in Visual Studio 2019 o Visual Studio Code.
        - Dopo aver aperto un file con estensione qs nell'editor, si dovrebbe vedere l'output dell'estensione del linguaggio Q# nella finestra di output.
        - Una volta caricato correttamente il progetto (come indicato nella finestra di output), aprire ogni file e risolvere manualmente tutti i problemi rimanenti.

> [!NOTE]
> * Per la versione 0.6, il server di linguaggio incluso in Quantum Development Kit non supporta aree di lavoro multiple.
> * Per gestire un progetto in Visual Studio Code, aprire la cartella radice contenente il progetto stesso e tutti i progetti a cui si fa riferimento.   
> * Per gestire una soluzione in Visual Studio, è necessario che tutti i progetti contenuti nella soluzione si trovino nella stessa cartella della soluzione o in una delle relative sottocartelle.  
> * I riferimenti tra i progetti trasferiti alla versione 0.6 e successive e i progetti che usano le versioni di pacchetti precedenti **non** sono supportati.

## <a name="version-051904"></a>Versione 0.5.1904

*Data di rilascio: 15 aprile 2019*

Questa versione contiene correzioni di bug.


## <a name="version-051903"></a>Versione 0.5.1903

*Data di rilascio: 27 marzo 2019*

Questa versione contiene quanto segue:

- Aggiunta del supporto per Jupyter Notebook, che offre ampie possibilità di imparare a usare Q#.  [Vedere i nuovi esempi di Jupyter Notebook per imparare a scrivere notebook personalizzati](xref:microsoft.quantum.install). 

- Aggiunta dell'aritmetica di addizionatori di interi alla libreria Quantum Canon.  Vedere anche un notebook di Jupyter che [descrive come usare i nuovi addizionatori di interi](https://github.com/microsoft/Quantum/blob/master/samples/arithmetic/AdderExample.ipynb).

- Correzione del bug per il problema di DumpRegister segnalato dalla community ([148](https://github.com/Microsoft/Quantum/issues/148)).

- Aggiunta della possibilità di restituire valori dall'interno di un'[istruzione using](xref:microsoft.quantum.guide.qubits#allocating-qubits).

- [Guida introduttiva](xref:microsoft.quantum.install) rinnovata.


## <a name="version-051902"></a>Versione 0.5.1902

*Data di rilascio: 27 febbraio 2019*

Questa versione contiene quanto segue:

- Aggiunta del supporto per host Python multipiattaforma.  Il pacchetto di `qsharp` per Python semplifica la simulazione di operazioni e funzioni Q# all'interno di Python. Vedere altre informazioni sull'[interoperabilità di Python](xref:microsoft.quantum.install). 

- Le estensioni di Visual Studio e Visual Studio Code supportano ora la ridenominazione dei simboli, ad esempio funzioni e operazioni.

- È ora possibile installare l'estensione di Visual Studio in Visual Studio 2019.

## <a name="version-041901"></a>Versione 0.4.1901

*Data di rilascio: 30 gennaio 2019*

Questa versione contiene quanto segue:

- Aggiunta del supporto per un nuovo tipo primitivo, BigInt, che rappresenta un intero con segno di dimensione arbitraria.  Vedere altre informazioni sul [tipo BigInt](xref:microsoft.quantum.guide.types).
- Aggiunta di un nuovo simulatore Toffoli, un simulatore rapido per scopi specifici che consente di simulare le operazioni quantistiche X, CNOT e X multi-controllate con un numero molto elevato di qubit.  Vedere altre informazioni sul [simulatore Toffoli](xref:microsoft.quantum.machines.toffoli-simulator).
- Aggiunta di un semplice strumento di stima che consente di stimare le risorse necessarie per eseguire un'istanza specifica di un'operazione Q# in un computer quantistico.  Vedere altre informazioni sullo [strumento di stima delle risorse](xref:microsoft.quantum.machines.resources-estimator).


## <a name="version-0318112802"></a>Versione 0.3.1811.2802

*Data di rilascio: 28 novembre 2018*

Anche se non è interessata dal problema, l'estensione di VS Code è stata contrassegnata e rimossa dal Marketplace durante la [ripulitura delle estensioni](https://code.visualstudio.com/blogs/2018/11/26/event-stream) correlate al pacchetto NPM `event-stream`. In questa versione sono state rimosse tutte le dipendenze di runtime che potrebbero attivare la segnalazione di problemi nell'estensione.

Se in precedenza è stata installata l'estensione, sarà necessario installarla di nuovo visitando la pagina del [Microsoft Quantum Development Kit per l'estensione di Visual Studio Code](vscode:extension/quantum.quantum-devkit-vscode) nel Visual Studio Marketplace e quindi premere Installa. Ci scusiamo per l'inconveniente.


## <a name="version-0318111511"></a>Versione 0.3.1811.1511

*Data di rilascio: 20 novembre 2018*

In questa versione è stato corretto un bug che impedisce ad alcuni utenti di caricare correttamente l'estensione di Visual Studio.

Se si sta eseguendo l'aggiornamento dalla versione 0.2 di Quantum Development Kit, vedere altre informazioni sulle [modifiche del linguaggio Q# e sulla migrazione del programma Q#](xref:microsoft.quantum.relnotes.migration-0-3).

## <a name="version-031811203"></a>Versione 0.3.1811.203

*Data di rilascio: 2 novembre 2018*

Questa versione include alcune correzioni di bug, tra cui:

* La chiamata a `DumpMachine` potrebbe cambiare lo stato del simulatore in determinate situazioni.
* Sono stati rimossi gli avvisi di compilazione visualizzati durante la creazione di progetti con una versione di .NET Core precedente a 2.1.403.
* È stata eseguita la pulizia della documentazione, in particolare per le descrizioni comando visualizzate al passaggio del mouse in VS Code o Visual Studio.

Se si sta eseguendo l'aggiornamento dalla versione 0.2 di Quantum Development Kit, vedere altre informazioni sulle [modifiche del linguaggio Q# e sulla migrazione del programma Q#](xref:microsoft.quantum.relnotes.migration-0-3).

## <a name="version-0318102508"></a>Versione 0.3.1810.2508

*Data di rilascio: 29 ottobre 2018*

Questa versione include nuove funzionalità del linguaggio e un'esperienza di sviluppo migliorata:

* Questa versione include un server di linguaggio per Q#, oltre alle integrazioni client per Visual Studio e Visual Studio Code. È quindi ora disponibile un nuovo set di funzionalità di IntelliSense, oltre al feedback in tempo reale sulla digitazione sotto forma di sottolineature ondulate di errori e avvisi. 
* Questo aggiornamento migliora notevolmente i messaggi di diagnostica in generale, con l'esplorazione semplificata e intervalli precisi per la diagnostica, oltre a dettagli aggiuntivi nelle informazioni visualizzate al passaggio del mouse.
* Il linguaggio Q# è stato esteso in modo da unificare l'esecuzione di operazioni di sviluppo comuni, oltre che con nuovi miglioramenti apportati alle funzionalità per far risaltare la potenza del calcolo quantistico.  In questa versione sono state apportate alcune modifiche di rilievo al linguaggio Q#.   

Vedere altre informazioni sulle [modifiche del linguaggio Q# e sulla migrazione del programma Q#](xref:microsoft.quantum.relnotes.migration-0-3).

Questa versione include anche una nuova libreria di chimica quantistica:

* La libreria di chimica contiene nuove funzionalità di simulazione hamiltoniana, tra cui:
    - Integratori Trotter-Suzuki di ordine pari arbitrario per una maggiore accuratezza della simulazione.
    - Tecnica di simulazione di qubitizzazione con ottimizzazioni specifiche della chimica per ridurre la complessità dei gate $T$.
* È stato introdotto un nuovo schema open source, denominato schema Broombridge (in riferimento a un [luogo storico](https://en.wikipedia.org/wiki/Broom_Bridge) celebrato come luogo di nascita degli hamiltoniani), per l'importazione e la simulazione di rappresentazioni di molecole.
* Tramite lo schema Broombridge vengono fornite più rappresentazioni chimiche.  Questi modelli sono stati generati da [NWChem](http://www.nwchem-sw.org/), uno strumento di chimica computazionale open source a elevate prestazioni.
* Esercitazioni ed esempi descrivono come usare la libreria di chimica e i modelli di dati Broombridge per:
    - Costruire semplici sistemi hamiltoniani con la libreria di chimica
    - Visualizzare le energie di terra e di eccitazione dell'idruro di litio usando la stima delle fasi.
    - Eseguire stime delle risorse della simulazione della chimica quantistica.
    - Stimare i livelli energetici delle molecole rappresentate dallo schema Broombridge.
* La documentazione descrive come usare NWChem per generare altri modelli chimici per la simulazione quantistica con Q#.

Vedere altre informazioni sulla [libreria di chimica del Quantum Development Kit](xref:microsoft.quantum.chemistry.concepts.intro).

Con la nuova libreria di chimica, le librerie vengono separate in un nuovo repository di GitHub, [Microsoft/QuantumLibraries](https://github.com/Microsoft/QuantumLibraries).  Gli esempi rimangono nel repository [Microsoft/Quantum](https://github.com/Microsoft/Quantum).  Sono benvenuti contributi per entrambi.

Questa versione include correzioni di bug e funzionalità per i problemi segnalati dalla community:

* Intellisense per Q#? ([UserVoice](https://quantum.uservoice.com/forums/906943/suggestions/32656918)).
* File con estensione qs ([UserVoice](https://quantum.uservoice.com/forums/906097/suggestions/32593049)).
* Miglioramento del messaggio di errore visualizzato quando si usano le abbreviazioni con parentesi graffe nelle istruzioni if ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/34718518)).
* Supporto della decostruzione di tuple nel (re-)binding modificabile ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/35020444)).
* Errore durante l'esecuzione del codice BitFlipCode fornito ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546)).
* Visualizzazione occasionale di grandi picchi per H2SimulationGUI ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34668370)).

### <a name="community-contributions"></a>Contributi della community

**Grazie** ai collaboratori seguenti che hanno contribuito per la base di codice open source all'indirizzo http://github.com/Microsoft/Quantum. Questi contributi arricchiscono ulteriormente gli esempi avanzati di codice Q#:

* Rolf Huisman ([@RolfHuisman](https://github.com/RolfHuisman)): Miglioramento dell'esperienza per gli sviluppatori QASM/Q# con la creazione di un convertitore QASM-Q#. [Richiesta pull 58](https://github.com/Microsoft/Quantum/pull/58).

* Andrew Helwer ([@ahelwer](https://github.com/ahelwer)):  Invio di un'implementazione di esempio di CHSH, un gioco quantistico correlato alla non località.  [Richiesta pull 84](https://github.com/Microsoft/Quantum/pull/84).

Grazie anche a Rohit Gupta ([@guptarohit](https://github.com/guptarohit),[richiesta pull 90](https://github.com/Microsoft/quantum/pull/90)), Tanaka Takayoshi ([@tanaka-takayoshi](https://github.com/tanaka-takayoshi),[richiesta pull 289](https://github.com/MicrosoftDocs/quantum-docs-pr/pull/289)) e Lee James O'Riordan ([@mlxd](https://github.com/mlxd),[richiesta pull 96](https://github.com/Microsoft/Quantum/pull/96)) per il loro lavoro destinato a migliorare i contenuti tramite correzioni della documentazione, dell'ortografia e degli errori di digitazione. 

## <a name="version-021809701"></a>Versione 0.2.1809.701

*Data di rilascio: 10 settembre 2018*

Questa versione include correzioni di bug per i problemi segnalati dalla community, tra cui:

* Non è possibile usare l'operatore shift ([GitHub](https://github.com/Microsoft/Quantum/issues/75)).
* `DumpMachine` / `DumpRegister` non riesce in `QCTraceSimulator` durante la stampa sulla console ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34709680)).
* Consentire l'allocazione di 0 qubit ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34768069-allow-allocating-0-qubits)).
* `AssertQubitState` richiede una chiamata Complex () esplicita ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34713733-assertqubitstate-requires-explicit-complex-call)).
* L'operazione `Measure` restituisce sempre `One` in macOS ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546)).

Grazie. 

## <a name="version-0218063001"></a>Versione 0.2.1806.3001

*Data di rilascio: 30 giugno 2018*

Questa versione è semplicemente una correzione rapida per il [problema 48 segnalato in GitHub](https://github.com/Microsoft/Quantum/issues/48) (la compilazione Q# non riesce se il nome utente contiene uno spazio vuoto). Seguire le stesse istruzioni di aggiornamento indicate per `0.2.1806.1503` con la nuova versione corrispondente (`0.2.1806.3001-preview`).

## <a name="version-0218061503"></a>Versione 0.2.1806.1503

*Data di rilascio: 22 giugno 2018*

Questa versione include diversi contributi della community, oltre a un'esperienza di debug migliorata e a prestazioni migliorate.  In particolare:

* Miglioramenti delle prestazioni per le simulazioni di qualsiasi dimensione per il computer di destinazione QuantumSimulator.
* Miglioramento della funzionalità di debug.
* Contributi della community per correzioni di bug, nuove funzioni helper, nuove operazioni e nuovi esempi.

### <a name="performance-improvements"></a>Miglioramenti delle prestazioni.

Questo aggiornamento include miglioramenti significativi delle prestazioni per la simulazione di qualsiasi numero di qubit per tutti i computer di destinazione.  Questo miglioramento è facilmente visibile con la simulazione H<sub>2</sub>, che è un esempio standard in Quantum Development Kit.

### <a name="improved-debugging-functionality"></a>Miglioramento della funzionalità di debug

Questo aggiornamento include nuove funzionalità di debug:
* Aggiunta di due nuove operazioni, @"microsoft.quantum.extensions.diagnostics.dumpmachine" e @"microsoft.quantum.extensions.diagnostics.dumpregister", che restituiscono informazioni sulle funzioni d'onda relative al computer quantistico di destinazione in un determinato momento.  
* In Visual Studio la probabilità di misurare un $\ket{1}$ su un singolo qubit viene ora mostrata automaticamente nella finestra di debug per il computer di destinazione QuantumSimulator.
* In Visual Studio è stata migliorata la visualizzazione delle proprietà delle variabili nelle finestre di debug **Auto** e **Variabili locali**. 

Vedere altre informazioni su [test e debug](xref:microsoft.quantum.guide.testingdebugging).

### <a name="community-contributions"></a>Contributi della community

La community di autori di codice Q# continua a crescere e siamo entusiasti di vedere le prime versioni di librerie ed esempi creati dai collaboratori e inviate alla base di codice open source all'indirizzo http://github.com/Microsoft/quantum.  **Un grande grazie** ai collaboratori seguenti:
* Mathias Soeken ([@msoeken](https://github.com/msoeken)): ha fornito un esempio che definisce un metodo di sintesi logica basato su trasformazioni per creare reti Toffoli e implementare una determinata permutazione. Il codice è scritto interamente con funzioni e operazioni Q#.  [Richiesta pull 41](https://github.com/Microsoft/Quantum/pull/41).
* RolfHuisman ([@RolfHuisman](https://github.com/RolfHuisman)): Rolf Huis, Microsoft MVP, ha fornito un esempio che genera codice QASM flat da codice Q# per una categoria limitata di programmi che non includono un flusso di controllo classico e hanno operazioni quantistiche limitate. [Richiesta pull 59](https://github.com/Microsoft/Quantum/pull/59)
* Sarah Kasier ([@crazy4pi314](https://github.com/crazy4pi314)): ha contribuito a migliorare la base di codice inviando una funzione di libreria per le operazioni controllate. [Richiesta pull 53](https://github.com/Microsoft/Quantum/pull/53)
* Jessica Lemieux ([@Lemj3111](https://github.com/Lemj3111)): ha corretto @"microsoft.quantum.canon.quantumphaseestimation" e creato nuovi unit test.  [Richiesta pull 54](https://github.com/Microsoft/Quantum/pull/54)
* Tama McGlinn ([@TamaHobbit](https://github.com/TamaHobbit)): ha pulito l'esempio di teletrasporto assicurando che l'istanza di QuantumSimulator venga eliminata. [Richiesta pull 20](https://github.com/Microsoft/Quantum/pull/20)

Inoltre, un grande **grazie** a questi Microsoft Software Engineer del team Commercial Engineering Services che hanno apportato modifiche importanti alla documentazione durante un evento hackathon.  Queste modifiche hanno decisamente migliorato la chiarezza della documentazione e l'esperienza di onboarding:
* Sascha Corti
* Mihaela Curmei
* John Donnelly
* Kirill Logachev
* Jan Pospisil
* Anita Ramanan
* Frances Tibble
* Alessandro Vozza

### <a name="update-existing-projects"></a>Aggiornare i progetti esistenti

Questa versione è completamente compatibile con le versioni precedenti. È sufficiente aggiornare i pacchetti NuGet nei progetti alla versione `0.2.1806.1503-preview` ed eseguire una **ricompilazione completa** per assicurarsi che vengano generati tutti i file intermedi.

In Visual Studio seguire le normali istruzioni su come [aggiornare un pacchetto](https://docs.microsoft.com/nuget/tools/package-manager-ui#updating-a-package).

Per aggiornare i modelli di progetto per la riga di comando, eseguire il comando seguente:
```
dotnet new -i "Microsoft.Quantum.ProjectTemplates::0.2.1806.1503-preview"
```

Dopo aver eseguito questo comando, tutti i nuovi progetti creati con `dotnet new <project-type> -lang Q#` useranno automaticamente questa versione di Quantum Development Kit.

Per aggiornare un progetto esistente per l'uso della versione più recente, eseguire il comando seguente dalla directory di ogni progetto:

```
dotnet add package Microsoft.Quantum.Development.Kit -v "0.2.1806.1503-preview"
dotnet add package Microsoft.Quantum.Canon -v "0.2.1806.1503-preview"
```

Se un progetto esistente usa anche l'integrazione XUnit per gli unit test, è possibile usare un comando simile per aggiornare anche questo pacchetto:
```
dotnet add package Microsoft.Quantum.Xunit -v "0.2.1806.1503-preview"
```

A seconda della versione di XUnit usata per il progetto di test, potrebbe essere necessario aggiornare XUnit alla versione 2.3.1:
```
dotnet add package xunit -v "2.3.1" 
```

Dopo l'aggiornamento, assicurarsi di rimuovere tutti i file temporanei generati dalla versione precedente eseguendo questo comando:
```
dotnet clean 
```

### <a name="known-issues"></a>Problemi noti

Nessun ulteriore problema noto da segnalare.


## <a name="version-0218022202"></a>Versione 0.2.1802.2202

*Data di rilascio: 26 febbraio 2018*

Questa versione include il supporto per lo sviluppo in più piattaforme, l'interoperabilità dei linguaggi e miglioramenti delle prestazioni. In particolare:

- Supporto per lo sviluppo basato su macOS e Linux. 
- Compatibilità con .NET Core, incluso il supporto per Visual Studio Code in più piattaforme.
- Una licenza open source completa per le librerie di Quantum Development Kit.
- Miglioramento delle prestazioni del simulatore nei progetti che richiedono almeno 20 qubit.
- Interoperabilità con il linguaggio Python (versione di anteprima disponibile in Windows).

### <a name="net-editions"></a>Edizioni .NET

La piattaforma .NET è disponibile in due edizioni diverse, .NET Framework fornito con Windows e .NET Core open source disponibile in Windows, macOS e Linux.
Con questa versione, la maggior parte dei componenti di Quantum Development Kit vengono forniti come librerie per .NET Standard, il set di classi comuni a Framework e Core.
Queste librerie sono quindi compatibili con le versioni recenti di .NET Framework o .NET Core.

Pertanto, per garantire che i progetti scritti con Quantum Development Kit siano il più portabili possibile, è consigliabile che i progetti di libreria scritti con il kit siano destinati a .NET Standard, mentre le applicazioni console a .NET Core.
Poiché le versioni precedenti di Quantum Development Kit supportano solo .NET Framework, può essere necessario eseguire la migrazione dei progetti esistenti. Per informazioni su come eseguire questa operazione, vedere di seguito.

### <a name="project-migration"></a>Migrazione dei progetti

I progetti creati con versioni precedenti di Quantum Development Kit continueranno a funzionare, purché non vengano aggiornati i pacchetti NuGet usati al loro interno. Per eseguire la migrazione del codice esistente alla nuova versione, seguire questa procedura:
1. Creare un nuovo progetto .NET Core usando il tipo di modello di progetto Q# appropriato (applicazione, raccolta o progetto di test).
2. Copiare i file con estensione qs e cs/fs esistenti dal progetto precedente a quello nuovo (Aggiungi > Elemento esistente). Non copiare il file AssemblyInfo.cs.
3. Compilare ed eseguire il nuovo progetto.

Si noti che l'operazione RandomWalkPhaseEstimation dello spazio dei nomi Microsoft.Quantum.Canon è stata spostata nello spazio dei nomi Microsoft.Research.Quantum.RandomWalkPhaseEstimation nel repository [Microsoft/Quantum-NC](https://github.com/microsoft/quantum-nc).

### <a name="known-issues"></a>Problemi noti

- L'opzione `--filter` in `dotnet test` non funziona correttamente per i test scritti in Q#.
  Di conseguenza, i singoli unit test non possono essere eseguiti in Visual Studio Code; per eseguire nuovamente tutti i test, è consigliabile usare `dotnet test` dalla riga di comando.

## <a name="version-0118011707"></a>Versione 0.1.1801.1707

*Data di rilascio: 18 gennaio 2018*

Questa versione include le correzioni per alcuni problemi segnalati dalla community, vale a dire:

- Il simulatore ora funziona con le prime CPU non abilitate per AVX.
- Le impostazioni internazionali relative ai separatori decimali non causano errori nel parser Q#.
- L'operazione primitiva `SignD` restituisce ora `Int` invece di `Double`.


## <a name="version-011712901"></a>Versione 0.1.1712.901

*Data di rilascio: 11 dicembre 2017*

### <a name="known-issues"></a>Problemi noti

#### <a name="hardware-and-software-requirements"></a>Requisiti hardware e software

- Per eseguire il simulatore incluso in Quantum Development Kit, è necessario installare la versione a 64 bit di Microsoft.
- Il simulatore quantistico di Microsoft, installato con Quantum Development Kit, utilizza le istruzioni AVX (Advanced Vector Extensions) e richiede una CPU appositamente abilitata. I processori Intel distribuiti nel primo trimestre 2011 (Sandy Bridge) o versioni successive supportano AVX. Stiamo valutando di aggiungere il supporto per le CPU meno recenti e potremmo annunciare i dettagli in un secondo momento.

#### <a name="project-creation"></a>Creazione di progetti

- Quando si crea una soluzione (con estensione sln) che userà Q#, è necessario inserirla in una directory superiore rispetto a qualsiasi progetto (con estensione csproj) incluso al suo interno. A questo scopo, durante la creazione di una nuova soluzione, assicurarsi che la casella di controllo "Crea directory per la soluzione" sia selezionata nella finestra di dialogo "Nuovo progetto". In caso contrario, sarà necessario installare manualmente i pacchetti NuGet di Quantum Development Kit.

#### <a name="q"></a>Q#

- IntelliSense non visualizza errori corretti per il codice Q#. Per visualizzare gli errori corretti di Q#, assicurarsi di visualizzare gli errori di compilazione nell'elenco errori di Visual Studio. Tenere anche presente che gli errori di Q# vengono visualizzati solo dopo aver completato una compilazione.
- L'uso di una matrice modificabile in un'applicazione parziale può generare un comportamento imprevisto.
- L'associazione di una matrice non modificabile a una matrice modificabile (sia a = b, dove b è una matrice modificabile) può generare un comportamento imprevisto.
- La profilatura, il code coverage e altri plug-in di Visual Studio potrebbero non sempre conteggiare accuratamente le righe e i blocchi di Q#.
- Il compilatore Q# non convalida le stringhe interpolate. È possibile creare errori di compilazione C# inserendo errori ortografici nei nomi delle variabili o usando espressioni nelle stringhe interpolate Q#.

#### <a name="simulation"></a>Simulazione

- Il simulatore quantistico usa OpenMP per parallelizzare l'algebra lineare necessaria. Per impostazione predefinita, OpenMP usa tutti i thread hardware disponibili, il che significa che i programmi con un numero basso di qubit vengono spesso eseguiti lentamente perché il coordinamento necessario ostacolerà il lavoro effettivo. Questo problema può essere risolto impostando la variabile di ambiente OMP_NUM_THREADS su un numero basso. Come regola empirica molto approssimativa, 1 thread è adatto per un totale di circa 4 qubit, quindi è consigliabile aggiungere un altro thread per ogni qubit, anche se dipende pesantemente dall'algoritmo.

#### <a name="debugging"></a>Debug

- F11 (esegui istruzione) non funziona nel codice Q#.
- L'evidenziazione del codice in Q# in corrispondenza di un punto di interruzione o di una pausa di un singolo passaggio è talvolta imprecisa. Verrà evidenziata la riga corretta, ma a volte l'evidenziazione inizierà e terminerà su colonne non corrette della riga.

#### <a name="testing"></a>Test

- I test devono essere eseguiti in modalità a 64 bit. Se i test hanno esito negativo con BadImageFormatException, passare al menu Test e selezionare Impostazioni test > Architettura processore predefinita > x64.
- L'esecuzione di alcuni test richiede tempi lunghi, a volte fino a 5 minuti a seconda del computer in uso. Ciò è normale, perché in alcuni test si usano più di 20 qubit. I nostri test più estesi attualmente vengono eseguiti su 23 qubit.

#### <a name="samples"></a>Esempi

- In alcuni computer è possibile che alcuni piccoli esempi vengano eseguiti lentamente a meno che la variabile di ambiente OMP_NUM_THREADS non sia impostata su "1". Vedere anche la nota sulla versione in "Simulazione".

#### <a name="libraries"></a>Librerie

- Esiste un presupposto implicito che i qubit passati a un'operazione in argomenti diversi siano tutti distinti. Ad esempio, tutte le operazioni con le librerie (e tutti i simulatori) presuppongono che i due qubit passati a un CNOT siano diversi tra loro. La violazione di questo presupposto può generare un comportamento imprevisto. È possibile testare questa condizione usando il simulatore di traccia del computer quantistico.
- La funzione Microsoft.Quantum.Bind potrebbe non generare i risultati previsti in tutti i casi.
- Nello spazio dei nomi Microsoft.Quantum.Extensions.Math la funzione SignD restituisce un valore Double anziché Int, anche se la funzione System.Math.Sign sottostante restituisce sempre un valore integer. È possibile confrontare il risultato con 1,0, -1,0 e 0,0, perché questi valori Double hanno tutte rappresentazioni binarie esatte.