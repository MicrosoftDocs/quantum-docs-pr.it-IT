---
title: Quantum Resources Estimator-Quantum Development Kit
description: "Informazioni su Microsoft QDK Resources Estimator, che consente di stimare le risorse necessarie per eseguire una determinata istanza di un' :::no-loc(Q#)::: operazione in un computer Quantum."
author: anpaz-msft
ms.author: anpaz
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: e1ec01d85a141b9c8a7a5ba5589663a0773520e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691876"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a><span data-ttu-id="e9e2a-103">Strumento di stima risorse di Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="e9e2a-103">Quantum Development Kit (QDK) resources estimator</span></span>

<span data-ttu-id="e9e2a-104">Come suggerisce il nome, la `ResourcesEstimator` classe stima le risorse necessarie per eseguire una determinata istanza di un' :::no-loc(Q#)::: operazione in un computer Quantum.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-104">As the name implies, the `ResourcesEstimator` class estimates the resources required to run a given instance of a :::no-loc(Q#)::: operation on a quantum computer.</span></span> <span data-ttu-id="e9e2a-105">Questo consente di eseguire l'operazione Quantum senza simulare effettivamente lo stato di un computer Quantum; per questo motivo, vengono stimate le risorse per :::no-loc(Q#)::: le operazioni che utilizzano migliaia di qubits, purché la parte classica del codice venga eseguita in un tempo ragionevole.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-105">It accomplishes this by running the quantum operation without actually simulating the state of a quantum computer; for this reason, it estimates resources for :::no-loc(Q#)::: operations that use thousands of qubits, provided that the classical part of the code runs in a reasonable time.</span></span>

<span data-ttu-id="e9e2a-106">Lo strumento di stima delle risorse si basa su [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), che fornisce un set più completo di metriche e strumenti per facilitare il debug dei :::no-loc(Q#)::: programmi.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-106">The resources estimator is built on top of the [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics and tools to help debug :::no-loc(Q#)::: programs.</span></span>

## <a name="invoking-and-running-the-resources-estimator"></a><span data-ttu-id="e9e2a-107">Richiamo ed esecuzione dello strumento di stima delle risorse</span><span class="sxs-lookup"><span data-stu-id="e9e2a-107">Invoking and running the resources estimator</span></span>

<span data-ttu-id="e9e2a-108">Per eseguire qualsiasi operazione, è possibile usare lo strumento di stima delle risorse :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="e9e2a-108">You can use the resources estimator to run any :::no-loc(Q#)::: operation.</span></span> <span data-ttu-id="e9e2a-109">Per ulteriori informazioni, vedere [modalità di esecuzione di un :::no-loc(Q#)::: programma](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="e9e2a-109">For additional details, see [Ways to run a :::no-loc(Q#)::: program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-resources-estimator-from-c"></a><span data-ttu-id="e9e2a-110">Richiamo dello strumento di stima delle risorse da C #</span><span class="sxs-lookup"><span data-stu-id="e9e2a-110">Invoking the resources estimator from C#</span></span> 

<span data-ttu-id="e9e2a-111">Come per altri computer di destinazione, creare prima un'istanza della classe `ResourceEstimator` e quindi passarla come primo parametro del metodo `Run` di un'operazione.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-111">As with other target machines, you first create an instance of the `ResourceEstimator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="e9e2a-112">Si noti che, a differenza della classe `QuantumSimulator`, la classe `ResourceEstimator` non implementa l'interfaccia <xref:System.IDisposable>, per cui non è necessario racchiuderla in un'istruzione `using`.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-112">Note that, unlike the `QuantumSimulator` class, the `ResourceEstimator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();
            Console.WriteLine(estimator.ToTSV());
        }
    }
}
```

<span data-ttu-id="e9e2a-113">Come illustrato nell'esempio, `ResourcesEstimator` fornisce il `ToTSV()` metodo, che genera una tabella con valori delimitati da tabulazioni (TSV).</span><span class="sxs-lookup"><span data-stu-id="e9e2a-113">As the example shows, `ResourcesEstimator` provides the `ToTSV()` method, which generates a table with tab-separated values (TSV).</span></span> <span data-ttu-id="e9e2a-114">È possibile salvare la tabella in un file o visualizzarla nella console per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-114">You can save the table to a file or display it to the console for analysis.</span></span> <span data-ttu-id="e9e2a-115">Di seguito è riportato un esempio di output del programma precedente:</span><span class="sxs-lookup"><span data-stu-id="e9e2a-115">The following is a sample output from the preceding program:</span></span>

```output
Metric          Sum
CNOT            1000
QubitClifford   1000
R               0
Measure         4002
T               0
Depth           0
Width           2
BorrowedWidth   0
```

> [!NOTE]
> <span data-ttu-id="e9e2a-116">Un' `ResourcesEstimator` istanza non reimposta i calcoli a ogni esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-116">A `ResourcesEstimator` instance does not reset its calculations on every run.</span></span> <span data-ttu-id="e9e2a-117">Se si utilizza la stessa istanza per eseguire un'altra operazione, vengono aggregati i nuovi risultati con i risultati esistenti.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-117">If you use the same instance to run another operation, it aggregates the new results with the existing results.</span></span> <span data-ttu-id="e9e2a-118">Se è necessario reimpostare i calcoli tra le esecuzioni, creare una nuova istanza per ogni esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-118">If you need to reset calculations between runs, create a new instance for every run.</span></span>

### <a name="invoking-the-resources-estimator-from-python"></a><span data-ttu-id="e9e2a-119">Richiamo dello strumento di stima delle risorse da Python</span><span class="sxs-lookup"><span data-stu-id="e9e2a-119">Invoking the resources estimator from Python</span></span>

<span data-ttu-id="e9e2a-120">Usare il metodo [estimate_resources ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) dalla libreria Python con l'operazione importata :::no-loc(Q#)::: :</span><span class="sxs-lookup"><span data-stu-id="e9e2a-120">Use the [estimate_resources()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) method from the Python library with the imported :::no-loc(Q#)::: operation:</span></span>

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a><span data-ttu-id="e9e2a-121">Richiamo dell'estimatore di risorse dalla riga di comando</span><span class="sxs-lookup"><span data-stu-id="e9e2a-121">Invoking the resources estimator from the command line</span></span>

<span data-ttu-id="e9e2a-122">Quando si esegue un :::no-loc(Q#)::: programma dalla riga di comando, usare il parametro **--Simulator** (o **-s** Shortcut) per specificare il `ResourcesEstimator` computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-122">When running a :::no-loc(Q#)::: program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the `ResourcesEstimator` target machine.</span></span> <span data-ttu-id="e9e2a-123">Il comando che segue esegue un programma usando lo strumento di stima delle risorse:</span><span class="sxs-lookup"><span data-stu-id="e9e2a-123">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a><span data-ttu-id="e9e2a-124">Richiamo dello strumento di stima delle risorse da notebook Juptyer</span><span class="sxs-lookup"><span data-stu-id="e9e2a-124">Invoking the resources estimator from Juptyer Notebooks</span></span>

<span data-ttu-id="e9e2a-125">Usare il :::no-loc(Q#)::: comando i Magic [% Estimate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) per eseguire l' :::no-loc(Q#)::: operazione.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-125">Use the I:::no-loc(Q#)::: magic command [%estimate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the :::no-loc(Q#)::: operation.</span></span>

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="e9e2a-126">Recupero dei dati stimati a livello di codice</span><span class="sxs-lookup"><span data-stu-id="e9e2a-126">Programmatically retrieving the estimated data</span></span>

<span data-ttu-id="e9e2a-127">Oltre a una tabella TSV, è possibile recuperare a livello di codice le risorse stimate durante l'esecuzione tramite la `Data` proprietà dello strumento di stima delle risorse.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-127">In addition to a TSV table, you can programmatically retrieve the resources estimated during the run via the `Data` property of the resources estimator.</span></span> <span data-ttu-id="e9e2a-128">La `Data` proprietà fornisce un' `System.DataTable` istanza con due colonne: `Metric` e `Sum` indicizzate in base ai nomi delle metriche.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-128">The `Data` property provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics' names.</span></span>

<span data-ttu-id="e9e2a-129">Nel codice seguente viene illustrato come recuperare e stampare il numero totale di `QubitClifford` `T` operazioni e `CNOT` utilizzate da un' :::no-loc(Q#)::: operazione:</span><span class="sxs-lookup"><span data-stu-id="e9e2a-129">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` operations used by a :::no-loc(Q#)::: operation:</span></span>

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();

            var data = estimator.Data;
            Console.WriteLine($"QubitCliffords: {data.Rows.Find("QubitClifford")["Sum"]}");
            Console.WriteLine($"Ts: {data.Rows.Find("T")["Sum"]}");
            Console.WriteLine($"CNOTs: {data.Rows.Find("CNOT")["Sum"]}");
        }
    }
}
```

## <a name="metrics-reported"></a><span data-ttu-id="e9e2a-130">Metriche segnalate</span><span class="sxs-lookup"><span data-stu-id="e9e2a-130">Metrics Reported</span></span>

<span data-ttu-id="e9e2a-131">Lo strumento di stima delle risorse tiene traccia delle metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="e9e2a-131">The resources estimator tracks the following metrics:</span></span>

|<span data-ttu-id="e9e2a-132">Metrica</span><span class="sxs-lookup"><span data-stu-id="e9e2a-132">Metric</span></span>|<span data-ttu-id="e9e2a-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9e2a-133">Description</span></span>|
|----|----|
|<span data-ttu-id="e9e2a-134">__CNOT__</span><span class="sxs-lookup"><span data-stu-id="e9e2a-134">__CNOT__</span></span>    |<span data-ttu-id="e9e2a-135">Il numero di esecuzioni delle `CNOT` operazioni, note anche come operazioni di Pauli X controllate.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-135">The run count of `CNOT` operations (also known as Controlled Pauli X operations).</span></span>|
|<span data-ttu-id="e9e2a-136">__QubitClifford__</span><span class="sxs-lookup"><span data-stu-id="e9e2a-136">__QubitClifford__</span></span> |<span data-ttu-id="e9e2a-137">Numero di esecuzioni di ogni singola operazione qubit Clifford e Pauli.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-137">The run count of any single qubit Clifford and Pauli operations.</span></span>|
|<span data-ttu-id="e9e2a-138">__Measure__</span><span class="sxs-lookup"><span data-stu-id="e9e2a-138">__Measure__</span></span>    |<span data-ttu-id="e9e2a-139">Numero di esecuzioni di qualsiasi misura.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-139">The run count of any measurements.</span></span>  |
|<span data-ttu-id="e9e2a-140">__R__</span><span class="sxs-lookup"><span data-stu-id="e9e2a-140">__R__</span></span>    |<span data-ttu-id="e9e2a-141">Il numero di esecuzioni di tutte le rotazioni a qubit singola, escluse le `T` operazioni Clifford e Pauli.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-141">The run count of any single-qubit rotations, excluding `T`, Clifford and Pauli operations.</span></span>  |
|<span data-ttu-id="e9e2a-142">__T__</span><span class="sxs-lookup"><span data-stu-id="e9e2a-142">__T__</span></span>    |<span data-ttu-id="e9e2a-143">Il numero di esecuzioni delle `T` operazioni e dei rispettivi coniugi, incluse le `T` operazioni, T_x = h. t. h e T_y = HY. t. HY.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-143">The run count of `T` operations and their conjugates, including the `T` operations, T_x = H.T.H, and T_y = Hy.T.Hy.</span></span>  |
|<span data-ttu-id="e9e2a-144">__Livello nidificazione__</span><span class="sxs-lookup"><span data-stu-id="e9e2a-144">__Depth__</span></span>|<span data-ttu-id="e9e2a-145">Profondità del circuito Quantum eseguito dall' :::no-loc(Q#)::: operazione (vedere di [seguito](#depth-width-and-qubitcount)).</span><span class="sxs-lookup"><span data-stu-id="e9e2a-145">Depth of the quantum circuit run by the :::no-loc(Q#)::: operation (see [below](#depth-width-and-qubitcount)).</span></span> <span data-ttu-id="e9e2a-146">Per impostazione predefinita, la metrica di profondità conta solo i `T` cancelli.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-146">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="e9e2a-147">Per informazioni dettagliate, vedere [contatore di profondità](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span><span class="sxs-lookup"><span data-stu-id="e9e2a-147">For more details, see [Depth Counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span></span>   |
|<span data-ttu-id="e9e2a-148">__Larghezza__</span><span class="sxs-lookup"><span data-stu-id="e9e2a-148">__Width__</span></span>|<span data-ttu-id="e9e2a-149">Larghezza del circuito Quantum eseguito dall' :::no-loc(Q#)::: operazione (vedere di [seguito](#depth-width-and-qubitcount)).</span><span class="sxs-lookup"><span data-stu-id="e9e2a-149">Width of the quantum circuit run by the :::no-loc(Q#)::: operation (see [below](#depth-width-and-qubitcount)).</span></span> <span data-ttu-id="e9e2a-150">Per impostazione predefinita, la metrica di profondità conta solo i `T` cancelli.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-150">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="e9e2a-151">Per informazioni dettagliate, vedere [contatore di profondità](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span><span class="sxs-lookup"><span data-stu-id="e9e2a-151">For more details, see [Depth Counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span></span>   |
|<span data-ttu-id="e9e2a-152">__QubitCount__</span><span class="sxs-lookup"><span data-stu-id="e9e2a-152">__QubitCount__</span></span>    |<span data-ttu-id="e9e2a-153">Limite inferiore per il numero massimo di qubits allocati durante l'esecuzione dell' :::no-loc(Q#)::: operazione.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-153">The lower bound for the maximum number of qubits allocated during the run of the :::no-loc(Q#)::: operation.</span></span> <span data-ttu-id="e9e2a-154">Questa metrica potrebbe non essere compatibile con la __profondità__ (vedere di seguito).</span><span class="sxs-lookup"><span data-stu-id="e9e2a-154">This metric might not be compatible with __Depth__ (see below).</span></span>  |
|<span data-ttu-id="e9e2a-155">__BorrowedWidth__</span><span class="sxs-lookup"><span data-stu-id="e9e2a-155">__BorrowedWidth__</span></span>    |<span data-ttu-id="e9e2a-156">Numero massimo di qubits presi in prestito all'interno dell' :::no-loc(Q#)::: operazione.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-156">The maximum number of qubits borrowed inside the :::no-loc(Q#)::: operation.</span></span>  |


## <a name="depth-width-and-qubitcount"></a><span data-ttu-id="e9e2a-157">Depth, Width e QubitCount</span><span class="sxs-lookup"><span data-stu-id="e9e2a-157">Depth, Width, and QubitCount</span></span>

<span data-ttu-id="e9e2a-158">Le stime di profondità e larghezza segnalate sono compatibili tra loro.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-158">Reported Depth and Width estimates are compatible with each other.</span></span>
<span data-ttu-id="e9e2a-159">(In precedenza entrambi i numeri erano raggiungibili, ma sarebbero necessari circuiti diversi per la profondità e la larghezza). Attualmente entrambe le metriche in questa coppia possono essere realizzate dallo stesso circuito nello stesso momento.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-159">(Previously both numbers were achievable, but different circuits would be required for Depth and for Width.) Currently both metrics in this pair can be achieved by the same circuit at the same time.</span></span>

<span data-ttu-id="e9e2a-160">Vengono restituite le metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="e9e2a-160">The following metrics are reported:</span></span>

<span data-ttu-id="e9e2a-161">__Profondità:__ Per l'operazione radice: tempo necessario per eseguirlo presumendo tempi di controllo specifici.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-161">__Depth:__ For the root operation - time it takes to execute it assuming specific gate times.</span></span>
<span data-ttu-id="e9e2a-162">Per le operazioni denominate o per le operazioni successive, differenza oraria tra il tempo di disponibilità qubit più recente all'inizio e la fine dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-162">For operations called or subsequent operations - time difference between latest qubit availability time at the beginning and the end of the operation.</span></span>

<span data-ttu-id="e9e2a-163">__Larghezza:__ Per l'operazione radice, il numero di qubits effettivamente usato per eseguirlo (e l'operazione che chiama).</span><span class="sxs-lookup"><span data-stu-id="e9e2a-163">__Width:__ For the root operation - number of qubits actually used to execute it (and operation it calls).</span></span>
<span data-ttu-id="e9e2a-164">Per operazioni denominate o operazioni successive: quante più qubits sono state usate oltre al qubits già usato all'inizio dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-164">For operations called or subsequent operations - how many more qubits were used in addition to the qubits already used at the beginning of the operation.</span></span>

<span data-ttu-id="e9e2a-165">Si noti che la qubits riutilizzata non contribuisce a questo numero.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-165">Please note, that reused qubits do not contribute to this number.</span></span>
<span data-ttu-id="e9e2a-166">Se, ad esempio, alcuni qubits sono stati rilasciati prima dell'avvio dell'operazione e tutti i qubit richiesti da questa operazione (e le operazioni chiamate da A) sono stati soddisfatti riutilizzando la versione precedente qubits, la larghezza dell'operazione A viene segnalata come 0.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-166">I.e. if a few qubits have been released before operation A starts, and all qubit demanded by this operation A (and operations called from A) were satisfied by reusing previously release qubits, the Width of operation A is reported as 0.</span></span> <span data-ttu-id="e9e2a-167">I qubits presi in prestito non contribuiscono alla larghezza.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-167">Successfully borrowed qubits do not contribute to the Width either.</span></span>

<span data-ttu-id="e9e2a-168">__QubitCount:__ Per l'operazione radice: numero minimo di qubits che sarebbe sufficiente per eseguire l'operazione (e le operazioni chiamate da esso).</span><span class="sxs-lookup"><span data-stu-id="e9e2a-168">__QubitCount:__ For the root operation - minimum number of qubits that would be sufficient to execute this operation (and operations called from it).</span></span>
<span data-ttu-id="e9e2a-169">Per le operazioni chiamate o operazioni successive: numero minimo di qubits che sarebbe sufficiente per eseguire questa operazione separatamente.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-169">For operations called or subsequent operations - minimum number of qubits that would be sufficient to execute this operation separately.</span></span> <span data-ttu-id="e9e2a-170">Questo numero non include qubits di input.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-170">This number doesn't include input qubits.</span></span> <span data-ttu-id="e9e2a-171">Include qubits presi in prestito.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-171">It does include borrowed qubits.</span></span>

<span data-ttu-id="e9e2a-172">Sono supportate due modalità operative.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-172">Two modes of operation are supported.</span></span> <span data-ttu-id="e9e2a-173">Per selezionare la modalità, impostare QCTraceSimulatorConfiguration. OptimizeDepth.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-173">Mode is selected by setting QCTraceSimulatorConfiguration.OptimizeDepth.</span></span>

<span data-ttu-id="e9e2a-174">__OptimizeDepth = true:__ QubitManager è sconsigliato dal riutilizzo di qubit e alloca nuovi qubit ogni volta che viene richiesto un qubit.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-174">__OptimizeDepth=true:__ QubitManager is discouraged from qubit reuse and allocates new qubit every time it is asked for a qubit.</span></span> <span data-ttu-id="e9e2a-175">Per la __profondità__ dell'operazione radice diventa la profondità minima (limite inferiore).</span><span class="sxs-lookup"><span data-stu-id="e9e2a-175">For the root operation __Depth__ becomes the minimum depth (lower bound).</span></span> <span data-ttu-id="e9e2a-176">Per questa profondità viene segnalata la __larghezza__ compatibile, che è possibile ottenere contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-176">Compatible __Width__ is reported for this depth (both can be achieved at the same time).</span></span> <span data-ttu-id="e9e2a-177">Si noti che questa larghezza sarà probabilmente non ottimale in base a questa profondità.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-177">Note, that this width will likely be not optimal given this depth.</span></span> <span data-ttu-id="e9e2a-178">__QubitCount__ può essere inferiore alla larghezza per l'operazione radice perché presuppone il riutilizzo.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-178">__QubitCount__ may be lower than Width for the root operation because it assumes reuse.</span></span>

<span data-ttu-id="e9e2a-179">__OptimizeDepth = false:__ QubitManager è consigliato per il riutilizzo di qubits e riutilizzerà il qubits rilasciato prima di allocarne di nuovi.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-179">__OptimizeDepth=false:__ QubitManager is encouraged to reuse qubits and will reuse released qubits before allocating new ones.</span></span> <span data-ttu-id="e9e2a-180">Per la __larghezza__ dell'operazione radice diventa la larghezza minima (limite inferiore).</span><span class="sxs-lookup"><span data-stu-id="e9e2a-180">For the root operation __Width__ becomes the minimal width (lower bound).</span></span> <span data-ttu-id="e9e2a-181">Viene segnalato un livello di __profondità__ compatibile su cui è possibile ottenerlo.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-181">Compatible __Depth__ is reported on which it can be achieved.</span></span> <span data-ttu-id="e9e2a-182">__QubitCount__ sarà uguale a __Width__ per l'operazione radice presumendo che non si prenda in prestito.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-182">__QubitCount__ will be the same as __Width__ for the root operation assuming no borrowing.</span></span>

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="e9e2a-183">Come fornire la probabilità dei risultati di misurazione</span><span class="sxs-lookup"><span data-stu-id="e9e2a-183">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="e9e2a-184">È possibile utilizzare <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> dallo <xref:Microsoft.Quantum.Diagnostics> spazio dei nomi per fornire informazioni sulla probabilità prevista di un'operazione di misurazione.</span><span class="sxs-lookup"><span data-stu-id="e9e2a-184">You can use <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> from the <xref:Microsoft.Quantum.Diagnostics> namespace to provide information about the expected probability of a measurement operation.</span></span> <span data-ttu-id="e9e2a-185">Per altre informazioni, vedere [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span><span class="sxs-lookup"><span data-stu-id="e9e2a-185">For more information, see [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span></span>

## <a name="see-also"></a><span data-ttu-id="e9e2a-186">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9e2a-186">See also</span></span>

- [<span data-ttu-id="e9e2a-187">Simulatore di traccia Quantum</span><span class="sxs-lookup"><span data-stu-id="e9e2a-187">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="e9e2a-188">Simulatore di Toffoli</span><span class="sxs-lookup"><span data-stu-id="e9e2a-188">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="e9e2a-189">Simulatore di stato completo</span><span class="sxs-lookup"><span data-stu-id="e9e2a-189">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 
