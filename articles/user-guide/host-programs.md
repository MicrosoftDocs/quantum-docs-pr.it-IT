---
title: 'Modalità di esecuzione di un programma Q #'
description: 'Panoramica dei diversi modi per eseguire i programmi Q #. Dalla riga di comando, i notebook Q # Jupyter e i programmi host classici in Python o in un linguaggio .NET.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 05/15/2020
ms.topic: article
uid: microsoft.quantum.guide.host-programs
ms.openlocfilehash: 132c138d7c392ed2b4bd3d0079180b68adae4cfc
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2020
ms.locfileid: "85887741"
---
# <a name="ways-to-run-a-q-program"></a>Modalità di esecuzione di un programma Q #

Uno dei principali punti di forza del kit di sviluppo di Quantum è la sua flessibilità tra piattaforme e ambienti di sviluppo.
Tuttavia, ciò significa anche che i nuovi utenti di Q # potrebbero trovarsi confusi o sopraffatti dalle numerose opzioni disponibili nella [Guida all'installazione](xref:microsoft.quantum.install).
In questa pagina viene illustrato cosa accade quando viene eseguito un programma Q # e si confrontano i vari modi in cui gli utenti possono eseguire questa operazione.

Una distinzione principale è che è possibile eseguire Q #:
- come applicazione autonoma, dove Q # è l'unica lingua utilizzata e il programma viene richiamato direttamente. In realtà, due metodi rientreranno in questa categoria:
  - interfaccia della riga di comando
  - Jupyter Notebooks in Q#
- con un *programma host*aggiuntivo, scritto in Python o in un linguaggio .NET, ad esempio C# o F #, che quindi richiama il programma ed è in grado di elaborare ulteriormente i risultati restituiti.

Per comprendere meglio questi processi e le relative differenze, viene considerato un semplice programma Q # e vengono confrontati i modi in cui può essere eseguito.

## <a name="basic-q-program"></a>Programma Q # di base

Un programma Quantum di base può comportare la preparazione di un qubit in una superposizione uguale di States $ \ket {0} $ e $ \ket {1} $, la relativa misurazione e la restituzione del risultato, che sarà casuale uno di questi due stati con probabilità uguale.
In realtà, questo processo è alla base della Guida introduttiva del [Generatore di numeri casuali Quantum](xref:microsoft.quantum.quickstarts.qrng) .

In Q # questa operazione verrebbe eseguita dal codice seguente:

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

Tuttavia, questo solo codice non può essere eseguito da Q #.
A tale scopo, deve costituire il corpo di un' [operazione](xref:microsoft.quantum.guide.basics#q-operations-and-functions), che viene quindi eseguita quando viene chiamato---direttamente o da un'altra operazione. Quindi, è possibile scrivere un'operazione nel formato seguente:
```qsharp
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) {
            H(q);
            return MResetZ(q);
        }
    }
```
È stata definita un'operazione, `MeasureSuperposition` , che non accetta input e restituisce un valore di tipo [result](xref:microsoft.quantum.guide.types).

Mentre gli esempi in questa pagina sono costituiti solo da *operazioni*q #, tutti i concetti illustrati si riferiscono ugualmente alle *funzioni*q #, quindi si fa riferimento a essi collettivamente come *chiamabili*. Le differenze sono illustrate in [Q # nozioni di base: operazioni e funzioni](xref:microsoft.quantum.guide.basics#q-operations-and-functions)e altri dettagli sulla relativa definizione sono reperibili in [Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions).

### <a name="callable-defined-in-a-q-file"></a>Richiamabile definito in un file Q #

Il callable è esattamente ciò che viene chiamato ed eseguito da Q #.
Tuttavia, sono necessarie altre aggiunte per includere un `*.qs` file Q # completo.

Tutti i tipi Q # e chiamabili (sia quelli definiti che quelli intrinseci al linguaggio) sono definiti all'interno degli *spazi dei nomi*, che forniscono a ognuno un nome completo a cui è possibile fare riferimento.

Ad esempio, le [`H`](xref:microsoft.quantum.intrinsic.h) [`MResetZ`](xref:microsoft.quantum.measurement.mresetz) operazioni e si trovano negli [`Microsoft.Quantum.Instrinsic`](xref:microsoft.quantum.intrinsic) [`Microsoft.Quantum.Measurement`](xref:microsoft.quantum.measurement) spazi dei nomi e (parte delle [librerie standard Q #](xref:microsoft.quantum.qsharplibintro)).
Di conseguenza, possono sempre essere chiamati tramite i nomi *completi* , `Microsoft.Quantum.Intrinsic.H(<qubit>)` e `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` , ma sempre questa operazione porterebbe a un codice molto ingombrante.

Al contrario, `open` le istruzioni consentono di fare riferimento a chiamabili con una sintassi più concisa, come è stato fatto nel corpo dell'operazione precedente.
Il file Q # completo che contiene l'operazione sarà quindi costituito dalla definizione di uno spazio dei nomi personalizzato, aprendo gli spazi dei nomi per le Callable utilizzate dall'operazione e quindi l'operazione:

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
> Gli spazi dei nomi possono anche essere associati a un *alias* all'apertura, che può essere utile se i nomi chiamabili/di tipo in due spazi dei nomi sono in conflitto.
> Ad esempio, è possibile usare in `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` precedenza e quindi chiamare `H` tramite `NamespaceWithH.H(<qubit>)` .

> [!NOTE]
> Un'eccezione a tutto questo è lo [`Microsoft.Quantum.Core`](xref:microsoft.quantum.core) spazio dei nomi, che viene sempre aperto automaticamente.
> Pertanto, le chiamabili come [`Length`](xref:microsoft.quantum.core.length) possono sempre essere utilizzate direttamente.

### <a name="execution-on-target-machines"></a>Esecuzione nei computer di destinazione

A questo punto, il modello di esecuzione generale di un programma Q # diventa chiaro.

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt="Q# program execution diagram" width="400">

In primo luogo, l'oggetto chiamabile specifico da eseguire può accedere a qualsiasi altro tipo e chiamabile definito nello stesso spazio dei nomi.
Consente inoltre di accedere a tali librerie da una qualsiasi delle [librerie Q #](xref:microsoft.quantum.libraries), ma è necessario fare riferimento a esse tramite il relativo nome completo o utilizzando le `open` istruzioni descritte in precedenza.

Il callable stesso viene quindi eseguito in un *[computer di destinazione](xref:microsoft.quantum.machines)*.
I computer di destinazione possono essere hardware Quantum effettivo o più simulatori disponibili come parte del QDK.
Per i nostri scopi, il computer di destinazione più utile è un'istanza del [simulatore a stato completo](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator` , che calcola il comportamento del programma come se fosse in esecuzione su un computer Quantum senza rumore.

Fino a questo punto, è stato descritto cosa accade quando viene eseguita una specifica domande e risposte.
Indipendentemente dal fatto che Q # venga usato in un'applicazione autonoma o con un programma host, questo processo generale è più o meno lo stesso---, di conseguenza la flessibilità del QDK.
Le differenze tra le diverse modalità di chiamata a Quantum Development Kit, quindi, rivelano la modalità di chiamata di Q # Callable per l'esecuzione e *il* modo in cui vengono restituiti tutti i risultati.
Più precisamente, le differenze riguardano 
1. che indica che è necessario eseguire Q # callable,
2. il modo in cui vengono forniti gli argomenti chiamabili possibili,
3. specificare il computer di destinazione in cui eseguirlo e
4. il modo in cui vengono restituiti i risultati.

In primo luogo, viene illustrato come eseguire questa operazione con l'applicazione Q # autonoma dalla riga di comando e quindi procedere con l'uso di Python e dei programmi host C#.
Si riserva l'applicazione autonoma dei notebook Q # Jupyter per ultimo, perché a differenza dei primi tre, la funzionalità principale non è incentrata su un file Q # locale.

> [!NOTE]
> Sebbene non venga illustrato in questi esempi, una comunanza tra i metodi di esecuzione è che tutti i messaggi stampati dall'interno del programma Q # (tramite [`Message`](xref:microsoft.quantum.intrinsic.message) o [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) , ad esempio) vengono in genere stampati nella rispettiva console.

## <a name="q-from-the-command-line"></a>Q # dalla riga di comando
Uno dei modi più semplici per iniziare a scrivere programmi Q # consiste nel evitare di preoccuparsi di file separati e di un secondo linguaggio.
L'uso di Visual Studio Code o Visual Studio con l'estensione QDK consente un flusso di lavoro trasparente in cui viene eseguito Callable Q # da un singolo file Q #.

A tale scopo, verrà richiamata l'esecuzione del programma immettendo
```dotnetcli
dotnet run
```
nella riga di comando.
Il flusso di lavoro più semplice è quando il percorso della directory del terminale è identico a quello del file Q #, che può essere facilmente gestito insieme alla modifica di file Q # usando il terminale integrato in VS Code, ad esempio.
Tuttavia, il [ `dotnet run` comando](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) accetta numerose opzioni e il programma può essere eseguito anche da una posizione diversa semplicemente specificando `--project <PATH>` il percorso del file Q #.


### <a name="add-entry-point-to-q-file"></a>Aggiungi punto di ingresso al file Q #

La maggior parte dei file Q # conterrà più richiamabili, quindi naturalmente è necessario consentire al compilatore di scoprire *quale* richiamabile eseguire quando si fornisce il `dotnet run` comando.
Questa operazione viene eseguita con una semplice modifica al file Q #: 
    - aggiungere una riga che `@EntryPoint()` precede direttamente il richiamabile.

Il file precedente diventa pertanto
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

A questo punto, una chiamata di `dotnet run` dalla riga di comando comporta `MeasureSuperposition` l'esecuzione e il valore restituito viene quindi stampato direttamente nel terminale.
Quindi, viene visualizzato `One` o `Zero` stampato. 

Si noti che non è importante se si dispone di più Callable definiti sotto di esso, solo `MeasureSuperposition` verrà eseguito.
Non è inoltre possibile che il richiamabile includa i [commenti della documentazione](xref:microsoft.quantum.guide.filestructure#documentation-comments) prima della Dichiarazione `@EntryPoint()` . l'attributo può essere semplicemente inserito sopra di essi.

### <a name="callable-arguments"></a>Argomenti chiamabili

Finora è stata considerata solo un'operazione che non accetta input.
Si supponga di voler eseguire un'operazione simile, ma su più qubits---il numero di cui viene fornito come argomento.
Un'operazione di questo tipo può essere scritta come
```qsharp
    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {              // allocate a register of n qubits
            ApplyToEach(H, qubits);              // apply H to each qubit in the register
            return ForEach(MResetZ, qubits);     // perform MResetZ on each qubit, returns the resulting array
        }
    }
```
dove il valore restituito è una matrice dei risultati della misurazione.
Si noti che [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) e [`ForEach`](xref:microsoft.quantum.arrays.foreach) si trovano [`Microsoft.Quantum.Canon`](xref:microsoft.quantum.canon) negli [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) spazi dei nomi e, richiedendo `open` istruzioni aggiuntive per ciascuna di esse.

Se si sposta l' `@EntryPoint()` attributo in modo che preceda questa nuova operazione (si noti che può essere presente solo una riga di questo tipo in un file), il tentativo di eseguirlo con semplicemente `dotnet run` genera un messaggio di errore che indica quali opzioni aggiuntive della riga di comando sono necessarie e come esporle.

Il formato generale per la riga di comando è in realtà `dotnet run [options]` e gli argomenti chiamabili sono disponibili.
In questo caso, l'argomento `n` è mancante e mostra che è necessario specificare l'opzione `-n <n>` . Per eseguire `MeasureSuperpositionArray` per `n=4` qubits, si usa quindi

```dotnetcli
dotnet run -n 4
```

produzione di un output simile a

```output
[Zero,One,One,One]
```

Questo naturalmente si estende a più argomenti.

> [!NOTE]
> I nomi degli argomenti definiti in `camelCase` sono leggermente modificati dal compilatore per essere accettati come input Q #. Se, ad esempio, invece di `n` è stato usato il nome `numQubits` precedente, questo input verrebbe fornito nella riga di comando tramite `--num-qubits 4` invece di `-n 4` .

Il messaggio di errore fornisce anche altre opzioni che è possibile usare, inclusa la modalità di modifica del computer di destinazione.

### <a name="different-target-machines"></a>Computer di destinazione diversi

Poiché gli output delle nostre operazioni sono stati finora i risultati previsti della loro azione su qubits reali, è evidente che il computer di destinazione predefinito dalla riga di comando è il simulatore quauntum a stato completo, `QuantumSimulator` .
Tuttavia, è possibile impostare l'esecuzione di Callable in un computer di destinazione specifico con l'opzione `--simulator` (o la sintassi abbreviata `-s` ).

Ad esempio, è possibile eseguirlo in [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) :

```dotnetcli
dotnet run -n 4 -s ResourcesEstimator
```

L'output stampato è quindi

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

Per informazioni dettagliate su ciò che indica le metriche, vedere [Resource Estimator: Metrics reported](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).

### <a name="command-line-execution-summary"></a>Riepilogo esecuzione riga di comando
<br/>
<img src="../media/hostprograms_command_line_diagram.png" alt="Q# program from command line" width="700">

### <a name="non-q-dotnet-run-options"></a>Opzioni non Q # `dotnet run`

Come accennato in precedenza con l' `--project` opzione, il [ `dotnet run` comando](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) accetta anche le opzioni non correlate agli argomenti Q # Callable.
Se si specificano entrambi i tipi di opzioni, le `dotnet` Opzioni specifiche di devono essere fornite per prime, seguite da un un delimitatore `--` e quindi dalle opzioni specifiche di Q #.
Ad esempio, specifica un percorso insieme a un numero qubits per l'operazione precedente verrebbe eseguito tramite `dotnet run --project <PATH> -- -n <n>` .

## <a name="q-with-host-programs"></a>Q # con programmi host

Con il file Q # a disposizione, un'alternativa alla chiamata di un'operazione o di una funzione direttamente dalla riga di comando consiste nell'usare un *programma host* in un altro linguaggio classico. In particolare, questa operazione può essere eseguita con Python o un linguaggio .NET, ad esempio C# o F # (per motivi di brevità verrà illustrato solo C#).
Per abilitare l'interoperabilità è necessaria una maggiore configurazione, ma queste informazioni sono disponibili nelle guide all' [installazione](xref:microsoft.quantum.install).

In breve, la situazione ora include un file di programma host, ad esempio `*.py` o, `*.cs` nella stessa posizione del file Q #.
È ora il programma *host* che viene eseguito e, nel corso dell'esecuzione, può chiamare operazioni e funzioni Q # specifiche dal file q #.
Il nucleo dell'interoperabilità è basato sul compilatore Q # che rende il contenuto del file Q # accessibile al programma host in modo che possano essere chiamati.

Uno dei principali vantaggi derivanti dall'uso di un programma host è che i dati classici restituiti dal programma Q # possono essere elaborati ulteriormente nel linguaggio host.
Questo può essere costituito da un'elaborazione avanzata dei dati (ad esempio, un elemento che non può essere eseguita internamente in Q #) e quindi la chiamata di altre azioni Q # in base a tali risultati, o qualcosa di semplice come il tracciato dei risultati Q #.

Lo schema generale è illustrato di seguito e vengono illustrate le implementazioni specifiche per Python e C#. Un esempio di utilizzo di un programma host F # si trova negli [esempi di interoperabilità .NET](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt="Q# program from a host program" width="700">

> [!NOTE]
> L' `@EntryPoint()` attributo usato per le applicazioni della riga di comando Q # non può essere usato con i programmi host.
> Se presente nel file Q # chiamato da un host, verrà generato un errore. 

Per lavorare con programmi host diversi, non sono necessarie modifiche a un `*.qs` file Q #.
Tutte le implementazioni del programma host seguenti funzionano con lo stesso file Q #:

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

Selezionare la scheda corrispondente alla lingua host di interesse.

### <a name="python"></a>[Python](#tab/tabid-python)
Un programma host Python viene costruito come segue:
1. Importare il `qsharp` modulo, che registra il caricatore del modulo per l'interoperabilità Q #. 
    Questo consente di visualizzare gli spazi dei nomi Q # come moduli Python, da cui è possibile "importare" domande e risposte.
    Si noti che non si tratta tecnicamente di domande e risposte che vengono importate, bensì Stub Python che consentono di chiamarli.
    Si comportano quindi come oggetti di classi Python, in cui vengono usati i metodi per specificare i computer di destinazione a cui inviare l'operazione per l'esecuzione.

2. Importare i richiamabili Q # che verranno richiamati direttamente---in questo caso, `MeasureSuperposition` e `MeasureSuperpositionArray` .
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    Con il `qsharp` modulo importato, è anche possibile importare i richiamabili direttamente dagli spazi dei nomi della libreria Q #.

3. Tra qualsiasi altro codice Python, è ora possibile chiamare tali chiamate su computer di destinazione specifici e assegnare i relativi ritorni alle variabili (se restituiscono un valore) per un ulteriore utilizzo.

#### <a name="specifying-target-machines"></a>Specifica di computer di destinazione
La chiamata di un'operazione da eseguire in un computer di destinazione specifico viene eseguita tramite diversi metodi Python sull'oggetto importato.
Ad esempio, `.simulate(<args>)` , USA `QuantumSimulator` per eseguire l'operazione, mentre a tale scopo `.estimate_resources(<args>)` su `ResourcesEstimator` .

#### <a name="passing-inputs-to-q"></a>Passaggio di input a Q\#
Gli argomenti per il Callable Q # devono essere forniti sotto forma di argomento di parola chiave, dove la parola chiave è il nome dell'argomento nella definizione Q # Callable.
Ovvero `MeasureSuperpositionArray.simulate(n=4)` è valido, mentre `MeasureSuperpositionArray.simulate(4)` genera un errore.

Quindi, il programma host Python 

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

Restituisce un output simile al seguente:

```python
Single qubit:
1
{'CNOT': 0, 'QubitClifford': 1, 'R': 0, 'Measure': 1, 'T': 0, 'Depth': 0, 'Width': 1, 'BorrowedWidth': 0}

Multiple qubits:
[0, 1, 1, 1]
{'CNOT': 0, 'QubitClifford': 4, 'R': 0, 'Measure': 4, 'T': 0, 'Depth': 0, 'Width': 4, 'BorrowedWidth': 0}
```

### <a name="c"></a>[C#](#tab/tabid-csharp)

Un programma host C# ha più componenti e funziona molto attentamente con alcuni componenti di QDK, ad esempio i simulatori, che vengono creati in C#.

Il compilatore Q # funziona qui generando uno spazio dei nomi C# con nome equivalente dallo spazio dei nomi Q # nel file Q #.
Genera ulteriormente una classe C# denominata in modo equivalente per ognuno dei tipi o chiamabili Q # definiti in esso.

In primo luogo, le classi usate nel programma host sono disponibili con `using` le istruzioni, che sono approssimativamente analogo alle `open` istruzioni nel file Q #:

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (e.g. QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the Q# namespace available
```

A questo punto, si dichiara lo spazio dei nomi C#, alcuni altri bit e parti (vedere il blocco di codice completo riportato di seguito) e quindi qualsiasi programmazione classica che si desidera (ad esempio, l'elaborazione degli argomenti per i Callable Q #).
Quest'ultimo non è necessario in questo caso, ma un esempio di tale utilizzo si trova nell' [esempio di interoperabilità .NET](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).

#### <a name="target-machines"></a>Computer di destinazione

Tornando a Q #, è necessario creare un'istanza del computer di destinazione in cui si eseguiranno le operazioni.

```csharp
            using var sim = new QuantumSimulator();
```

L'uso di altri computer di destinazione è semplice come creare un'istanza di un altro computer, anche se la modalità di esecuzione e l'elaborazione dei ritorni possono essere leggermente diversi.
Per brevità, è necessario attenersi al [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) per il momento e includere quanto [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [segue](#including-the-resources-estimator).

Ogni classe C# generata dalle operazioni Q # ha un `Run` metodo, il primo argomento di cui deve essere l'istanza del computer di destinazione.
Quindi, per `MeasureSuperposition` l'esecuzione in `QuantumSimulator` , viene utilizzato `MeasureSuperposition.Run(sim)` .
I risultati restituiti possono quindi essere assegnati alle variabili in C#:

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> Il `Run` metodo viene eseguito in modo asincrono perché si tratta del caso di hardware Quantum reale e pertanto la `await` parola chiave blocca ulteriormente l'esecuzione fino al completamento dell'attività.

Se il Callable Q # non ha alcun valore restituito (ovvero ha un tipo restituito `Unit` ), l'esecuzione può comunque essere eseguita nello stesso modo senza assegnarla a una variabile.
In tal caso, l'intera riga costituirebbe semplicemente 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a>Arguments

Tutti gli argomenti di Q # Callable vengono semplicemente passati come argomenti aggiuntivi dopo il computer di destinazione.
Di conseguenza, i risultati di `MeasureSuperpositionArray` su `n=4` qubits vengono recuperati tramite 

```csharp
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);
```

Un programma host C# completo potrebbe quindi essere simile a

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

Nel percorso del file C#, è possibile eseguire il programma host dalla riga di comando immettendo
```dotnetcli
dotnet run
```
e in questo caso verrà visualizzato un output scritto nella console simile a 
```output
Single qubit result: One
Multiple qubit result: [One,One,Zero,Zero]
```

> [!NOTE]
> A causa dell'interoperabilità del compilatore con gli spazi dei nomi, è possibile rendere disponibili i richiamabili Q # senza l' `using NamespaceName;` istruzione e semplicemente abbinando il titolo dello spazio dei nomi C#.
> Ovvero sostituendo `namespace host` con `namespace NamespaceName` .

#### <a name="including-the-resources-estimator"></a>Inclusione dello strumento di stima delle risorse

[`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator)Richiede un'implementazione leggermente diversa per recuperare l'output.

In primo luogo, invece di crearne un'istanza come variabile con un' `using` istruzione, come in questo caso `QuantumSimulator` , viene creata un'istanza più direttamente di oggetti della classe tramite

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

Si noti che invece di un singolo simulatore di destinazione deve essere usato da più operazioni Q #, ne è stata creata un'istanza per ciascuna. Poiché gli oggetti stessi vengono modificati quando vengono utilizzati come computer di destinazione e i relativi risultati possono quindi essere recuperati successivamente con il metodo della classe `.ToTSV()` .

Per eseguire le operazioni sugli estimatori di risorse, si usa

```csharp
            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);
```
e quindi recuperare i risultati come valori delimitati da tabulazioni (TSV) con `estimatorSingleQ.ToTSV()` e `estimatorMultiQ.ToTSV()` .

Pertanto, un programma host C# completo che utilizza sia `QuantumSimulator` che `ResourcesEstimator` può assumere il formato seguente:

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


che restituisce un output simile a

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

## <a name="q-jupyter-notebooks"></a>Jupyter Notebooks in Q#
Q # Jupyter Notebooks usa il kernel IQ #, che consente di definire, compilare ed eseguire i Callable Q # in un singolo notebook---tutti insieme a istruzioni, note e altro contenuto.
Ciò significa che, sebbene sia possibile importare e usare il contenuto dei `*.qs` file Q #, non sono necessari nel modello di esecuzione.

In questo articolo viene illustrato in dettaglio come eseguire le operazioni Q # definite in precedenza, ma un'introduzione più ampia all'uso dei notebook Q # Jupyter è disponibile in [Introduzione ai notebook q # e Jupyter](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).

### <a name="defining-operations"></a>Definizione di operazioni

In una Jupyter Notebook Q # immettere il codice Q # esattamente come si farebbe dall'interno dello spazio dei nomi di un file Q #.

È quindi possibile abilitare l'accesso a Callable dalle [librerie standard Q #](xref:microsoft.quantum.qsharplibintro) con `open` istruzioni per i rispettivi spazi dei nomi.
Quando si esegue una cella con tale istruzione, le definizioni di tali spazi dei nomi sono disponibili nell'area di lavoro.

> [!NOTE]
> I richiamabili da [Microsoft. Quantum. Intrinsic](xref:microsoft.quantum.intrinsic) e [Microsoft. Quantum. Canon](xref:microsoft.quantum.canon) (ad esempio [`H`](xref:microsoft.quantum.intrinsic.h) e [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) ) sono automaticamente disponibili per le operazioni definite all'interno delle celle nei notebook Q # Jupyter.
> Tuttavia, questo non è vero per il codice introdotto da file di origine Q # esterni (un processo illustrato in [Introduzione ai notebook q # e Jupyter](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)). 
> 

Analogamente, per la definizione delle operazioni è necessario scrivere solo il codice Q # ed eseguire la cella.

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining Q# operations" width="600">

L'output elenca quindi le operazioni che possono essere chiamate dalle celle future.

### <a name="target-machines"></a>Computer di destinazione

La funzionalità per l'esecuzione di operazioni su computer di destinazione specifici viene fornita tramite i [comandi IQ # Magic](xref:microsoft.quantum.guide.quickref.iqsharp).
Ad esempio, USA `%simulate` l'oggetto `QuantumSimulator` e `%estimate` Usa `ResourcesEstimator` :

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Simulate and estimate resources Jupyter cell" width="500">

### <a name="passing-inputs-to-functions-and-operations"></a>Passaggio di input a funzioni e operazioni

Attualmente i comandi Magic di esecuzione possono essere utilizzati solo con operazioni che non accettano argomenti. Quindi, per eseguire `MeasureSuperpositionArray` , è necessario definire un'operazione "wrapper" che quindi chiama l'operazione con gli argomenti:

<img src="../media/hostprograms_jupyter_wrapper_def_sim_crop.png" alt="Wrapper function and simulate Jupyter cell" width="550">

Questa operazione può naturalmente essere utilizzata in modo analogo con `%estimate` e altri comandi di esecuzione.
