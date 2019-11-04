---
title: Simulatori quantistici e driver classici | Microsoft Docs
description: Descrive come eseguire i simulatori quantistici con un linguaggio .NET per il calcolo classico, in genere C# o Q#.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines
ms.openlocfilehash: 5ac79280669ae0acfe993a1c2ae1c069b0c01848
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035110"
---
# <a name="classical-drivers-and-machines"></a>Driver e computer classici

## <a name="what-youll-learn"></a>Contenuto dell'esercitazione

> [!div class="checklist"]
> * Come vengono eseguiti gli algoritmi quantistici
> * Quali simulatori quantistici sono inclusi in questa versione
> * Come scrivere un driver C# per l'algoritmo quantistico

## <a name="the-quantum-development-kit-execution-model"></a>Modello di esecuzione di Quantum Development Kit

In [Scrittura di un programma quantistico](xref:microsoft.quantum.write-program), l'algoritmo quantistico è stato eseguito passando un oggetto `QuantumSimulator` al metodo `Run` della classe dell'algoritmo.
La classe `QuantumSimulator` esegue l'algoritmo quantistico simulando completamente il vettore di stato quantistico, perfetto per l'esecuzione e il test di `Teleport`.
Per altre informazioni sui vettori di stato quantistici, vedere la [Guida ai concetti](xref:microsoft.quantum.concepts.intro).

Per eseguire un algoritmo quantistico, è possibile usare altri computer di destinazione.
Il computer è responsabile della fornitura di implementazioni di primitive quantistiche per l'algoritmo.
Sono incluse operazioni primitive come H, CNOT e misura, oltre alla gestione e al monitoraggio di qubit.
Classi diverse di computer quantistici rappresentano modelli di esecuzione diversi per lo stesso algoritmo quantistico.

Ogni tipo di computer quantistico può fornire implementazioni diverse di tali primitive.
Ad esempio, il simulatore di traccia del computer quantistico incluso nel kit di sviluppo non esegue alcuna simulazione.
Piuttosto, tiene traccia dell'utilizzo di gate, qubit e altre risorse per l'algoritmo.

### <a name="quantum-machines"></a>Computer quantistici

In futuro, verranno definite ulteriori classi di computer quantistici per supportare altri tipi di simulazione e per supportare l'esecuzione in computer quantistici topologici.
Consentire all'algoritmo di rimanere costante e variando al contempo l'implementazione del computer sottostante semplifica il test e il debug di un algoritmo in simulazione, per poterlo eseguire nell'hardware reale con la certezza che l'algoritmo non è stato modificato.

### <a name="whats-included-in-this-release"></a>Contenuti di questa versione

Questa versione di Quantum Developer Kit include numerose classi di computer quantistico.
Tutte le classi sono definite nello spazio dei nomi `Microsoft.Quantum.Simulation.Simulators`.

* Un [simulatore di vettori di stato completo](xref:microsoft.quantum.machines.full-state-simulator), la classe `QuantumSimulator`.
* Uno [strumento di stima risorse semplice](xref:microsoft.quantum.machines.resources-estimator), la classe `ResourcesEstimator`, consente un'analisi generale delle risorse necessarie per eseguire un algoritmo quantistico.
* Un [strumento di stima delle risorse basato su traccia](xref:microsoft.quantum.machines.qc-trace-simulator.intro), la classe `QCTraceSimulator`, consente l'analisi avanzata dei consumi di risorse per l'intero grafico di chiamata dell'algoritmo.
* Un [simulatore di Toffoli](xref:microsoft.quantum.machines.toffoli-simulator), la classe `ToffoliSimulator`.

## <a name="writing-a-classical-driver-program"></a>Scrittura di un programma driver classico

In [Scrittura di un programma quantistico](xref:microsoft.quantum.write-program), è stato creato un semplice driver C# per l'algoritmo di teletrasporto. Gli scopi principali di un driver C# sono quattro:

* Creazione del computer di destinazione
* Calcolo degli argomenti necessari per l'algoritmo quantistico
* Esecuzione dell'algoritmo quantistico tramite il simulatore
* Elaborazione del risultato dell'operazione

Ora verrà illustrato ogni passaggio in dettaglio.

### <a name="constructing-the-target-machine"></a>Creazione del computer di destinazione

I computer quantistici sono istanze di classi .NET normali, che vengono quindi create richiamandone il costruttore, come per qualsiasi altra classe .NET.
Alcuni simulatori, incluso `QuantumSimulator`, implementano l'interfaccia .NET <xref:System.IDisposable?displayProperty=nameWithType> e devono quindi essere racchiusi in un'istruzione `using` C#.

### <a name="computing-arguments-for-the-algorithm"></a>Calcolo degli argomenti per l'algoritmo

Nell'esempio `Teleport` sono stati calcolati alcuni argomenti relativamente artificiali da passare all'algoritmo quantistico.
In genere, tuttavia, l'algoritmo richiede grandi quantità di dati ed è più facile fornirli dal driver classico.

Ad esempio, quando si esegue una simulazione chimica, l'algoritmo quantistico richiede una tabella di grandi dimensioni di integrali di interazione tra orbitali molecolari.
Questi vengono normalmente letti da un file che viene fornito quando si esegue l'algoritmo.
Poiché Q# non dispone di un meccanismo per accedere al file system, questo tipo di dati viene raccolto in modo più efficace dal driver classico e quindi i dati vengono passati al metodo `Run` dell'algoritmo quantistico.

Il driver classico gioca un ruolo fondamentale anche nel caso dei metodi variazionali.
In questa classe di algoritmi uno stato quantistico viene preparato in base ad alcuni parametri classici e tale stato viene usato per calcolare un valore di interesse.
I parametri vengono rettificati in base a un tipo di algoritmo hill climbing o di apprendimento automatico e l'algoritmo quantistico viene eseguito nuovamente.
Per questi algoritmi, l'algoritmo hill climbing stesso viene implementato in modo ottimale come funzione puramente classica chiamata dal driver classico. I risultati dell'algoritmo hill climbing vengono quindi passati alla successiva esecuzione dell'algoritmo quantistico.

### <a name="running-the-quantum-algorithm"></a>Esecuzione dell'algoritmo quantistico

Questa parte è in genere molto semplice.
Ogni operazione Q# viene compilata in una classe che fornisce un metodo `Run` statico.
Gli argomenti di questo metodo vengono forniti dalla tupla di argomenti bidimensionali dell'operazione stessa, oltre a un primo argomento aggiuntivo che è il simulatore da usare per l'esecuzione. Per un'operazione che prevede la tupla denominata di tipo `(a: String, (b: Double, c: Double))` la controparte bidimensionale è di tipo `(String a, Double b, Double c)`.


Il passaggio di argomenti a un metodo `Run` prevede alcune particolarità:

* Le matrici devono essere racchiuse in un oggetto `Microsoft.Quantum.Simulation.Core.QArray<T>`.
    Una classe `QArray` dispone di un costruttore che può eseguire qualsiasi raccolta ordinata (`IEnumerable<T>`) di oggetti appropriati.
* La tupla vuota, `()` in Q#, è rappresentata da `QVoid.Instance` in C#.
* Le tuple non vuote sono rappresentate come istanze di `ValueType` .NET.
* I tipi definiti dall'utente Q# vengono passati come tipo di base.
* Per passare un'operazione o una funzione a un metodo `Run`, è necessario ottenere un'istanza della classe dell'operazione o della funzione, usando il metodo `Get<>` del simulatore.

### <a name="processing-the-results"></a>Elaborazione dei risultati

I risultati dell'algoritmo quantistico vengono restituiti dal metodo `Run`.
Il metodo `Run` viene eseguito in modo asincrono in modo che restituisca un'istanza di <xref:System.Threading.Tasks.Task`1>.
Sono disponibili diversi modi per ottenere i risultati dell'operazione effettiva. Il più semplice consiste nell'usare la [proprietà `Result`](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task-1.result) di `Task`:

```csharp
    var res = BellTest.Run(sim, 1000, initial).Result;
```
ma anche altre tecniche, ad esempio l'uso del [metodo `Wait`](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task.wait) o della [parola chiave `await`](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await) C#, funzioneranno.

Come per gli argomenti, le tuple Q# sono rappresentate come istanze di `ValueTuple` e le matrici Q# sono rappresentate come istanze di `QArray`.
I tipi definiti dall'utente vengono restituiti come tipi di base.
La tupla vuota, `()`, viene restituita come istanza della classe `QVoid`.

Molti algoritmi quantistici richiedono una sostanziale post-elaborazione per la derivazione di risposte utili.
Ad esempio, la parte quantistica dell'algoritmo di Shor è solo l'inizio di un calcolo che trova i fattori di un numero.

Nella maggior parte dei casi, è più semplice eseguire questo tipo di post-elaborazione nel driver classico.
Solo il driver classico può segnalare i risultati all'utente o scriverli su disco.
Il driver classico avrà accesso alle librerie di analisi e ad altre funzioni matematiche non esposte in Q#.


## <a name="failures"></a>Errori

Quando viene raggiunta l'istruzione `fail` Q# durante l'esecuzione di un'operazione, viene generata un'eccezione `ExecutionFailException`.

A causa dell'utilizzo di `System.Task` nel metodo `Run`, l'eccezione generata come risultato di un'istruzione `fail` verrà racchiusa in un'eccezione `System.AggregateException`.
Per individuare il motivo effettivo dell'errore, è necessario eseguire un'iterazione nella `AggregateException` 
`InnerExceptions`, ad esempio:

```csharp

            try
            {
                using(var sim = new QuantumSimulator())
                {
                    /// call your operations here...
                }
            }
            catch (AggregateException e)
            {
                // Unwrap AggregateException to get the message from Q# fail statement.
                // Go through all inner exceptions.
                foreach (Exception inner in e.InnerExceptions)
                {
                    // If the exception of type ExecutionFailException
                    if (inner is ExecutionFailException failException)
                    {
                        // Print the message it contains
                        Console.WriteLine($" {failException.Message}");
                    }
                }
            }
```

## <a name="other-classical-languages"></a>Altri linguaggi classici

Sebbene gli esempi forniti siano scritti in C#, F# e Python, Quantum Development Kit supporta anche la scrittura di programmi host classici in altri linguaggi.
Se, ad esempio, si vuole scrivere un programma host in Visual Basic, [non dovrebbero verificarsi problemi](https://github.com/tcNickolas/MiscQSharp/blob/master/Quantum_VBNet/README.md#using-q-with-visual-basic-net).
