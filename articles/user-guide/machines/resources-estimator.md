---
title: Quantum Resources Estimator-Quantum Development Kit
description: Informazioni su Microsoft QDK Resources Estimator, che consente di stimare le risorse necessarie per eseguire una determinata istanza di un' Q# operazione in un computer Quantum.
author: anpaz
ms.author: anpaz
ms.date: 06/26/2020
ms.topic: conceptual
uid: microsoft.quantum.machines.resources-estimator
no-loc:
- Q#
- $$v
ms.openlocfilehash: c3aa94c8b34ad7247fbdeab4bf4dcb96ce746014
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847470"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a><span data-ttu-id="2e1ed-103">Strumento di stima risorse di Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="2e1ed-103">Quantum Development Kit (QDK) resources estimator</span></span>

<span data-ttu-id="2e1ed-104">Come suggerisce il nome, la `ResourcesEstimator` classe stima le risorse necessarie per eseguire una determinata istanza di un' Q# operazione in un computer Quantum.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-104">As the name implies, the `ResourcesEstimator` class estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span> <span data-ttu-id="2e1ed-105">Questo consente di eseguire l'operazione Quantum senza simulare effettivamente lo stato di un computer Quantum; per questo motivo, vengono stimate le risorse per Q# le operazioni che utilizzano migliaia di qubits, purché la parte classica del codice venga eseguita in un tempo ragionevole.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-105">It accomplishes this by running the quantum operation without actually simulating the state of a quantum computer; for this reason, it estimates resources for Q# operations that use thousands of qubits, provided that the classical part of the code runs in a reasonable time.</span></span>

<span data-ttu-id="2e1ed-106">Lo strumento di stima delle risorse si basa su [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), che fornisce un set più completo di metriche e strumenti per facilitare il debug dei Q# programmi.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-106">The resources estimator is built on top of the [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics and tools to help debug Q# programs.</span></span>

## <a name="invoking-and-running-the-resources-estimator"></a><span data-ttu-id="2e1ed-107">Richiamo ed esecuzione dello strumento di stima delle risorse</span><span class="sxs-lookup"><span data-stu-id="2e1ed-107">Invoking and running the resources estimator</span></span>

<span data-ttu-id="2e1ed-108">Per eseguire qualsiasi operazione, è possibile usare lo strumento di stima delle risorse Q# .</span><span class="sxs-lookup"><span data-stu-id="2e1ed-108">You can use the resources estimator to run any Q# operation.</span></span> <span data-ttu-id="2e1ed-109">Per ulteriori informazioni, vedere [modalità di esecuzione di un Q# programma](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="2e1ed-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-resources-estimator-from-c"></a><span data-ttu-id="2e1ed-110">Richiamo dello strumento di stima delle risorse da C #</span><span class="sxs-lookup"><span data-stu-id="2e1ed-110">Invoking the resources estimator from C#</span></span> 

<span data-ttu-id="2e1ed-111">Come per altri computer di destinazione, creare prima un'istanza della classe `ResourcesEstimator` e quindi passarla come primo parametro del metodo `Run` di un'operazione.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-111">As with other target machines, you first create an instance of the `ResourcesEstimator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="2e1ed-112">Si noti che, a differenza della classe `QuantumSimulator`, la classe `ResourcesEstimator` non implementa l'interfaccia <xref:System.IDisposable>, per cui non è necessario racchiuderla in un'istruzione `using`.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-112">Note that, unlike the `QuantumSimulator` class, the `ResourcesEstimator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

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

<span data-ttu-id="2e1ed-113">Come illustrato nell'esempio, `ResourcesEstimator` fornisce il `ToTSV()` metodo, che genera una tabella con valori delimitati da tabulazioni (TSV).</span><span class="sxs-lookup"><span data-stu-id="2e1ed-113">As the example shows, `ResourcesEstimator` provides the `ToTSV()` method, which generates a table with tab-separated values (TSV).</span></span> <span data-ttu-id="2e1ed-114">È possibile salvare la tabella in un file o visualizzarla nella console per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-114">You can save the table to a file or display it to the console for analysis.</span></span> <span data-ttu-id="2e1ed-115">Di seguito è riportato un esempio di output del programma precedente:</span><span class="sxs-lookup"><span data-stu-id="2e1ed-115">The following is a sample output from the preceding program:</span></span>

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
> <span data-ttu-id="2e1ed-116">Un' `ResourcesEstimator` istanza non reimposta i calcoli a ogni esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-116">A `ResourcesEstimator` instance does not reset its calculations on every run.</span></span> <span data-ttu-id="2e1ed-117">Se si utilizza la stessa istanza per eseguire un'altra operazione, vengono aggregati i nuovi risultati con i risultati esistenti.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-117">If you use the same instance to run another operation, it aggregates the new results with the existing results.</span></span> <span data-ttu-id="2e1ed-118">Se è necessario reimpostare i calcoli tra le esecuzioni, creare una nuova istanza per ogni esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-118">If you need to reset calculations between runs, create a new instance for every run.</span></span>

### <a name="invoking-the-resources-estimator-from-python"></a><span data-ttu-id="2e1ed-119">Richiamo dello strumento di stima delle risorse da Python</span><span class="sxs-lookup"><span data-stu-id="2e1ed-119">Invoking the resources estimator from Python</span></span>

<span data-ttu-id="2e1ed-120">Usare il metodo [estimate_resources ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) dalla libreria Python con l'operazione importata Q# :</span><span class="sxs-lookup"><span data-stu-id="2e1ed-120">Use the [estimate_resources()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) method from the Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a><span data-ttu-id="2e1ed-121">Richiamo dell'estimatore di risorse dalla riga di comando</span><span class="sxs-lookup"><span data-stu-id="2e1ed-121">Invoking the resources estimator from the command line</span></span>

<span data-ttu-id="2e1ed-122">Quando si esegue un Q# programma dalla riga di comando, usare il parametro **--Simulator** (o **-s** Shortcut) per specificare il `ResourcesEstimator` computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-122">When running a Q# program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the `ResourcesEstimator` target machine.</span></span> <span data-ttu-id="2e1ed-123">Il comando che segue esegue un programma usando lo strumento di stima delle risorse:</span><span class="sxs-lookup"><span data-stu-id="2e1ed-123">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a><span data-ttu-id="2e1ed-124">Richiamo dello strumento di stima delle risorse da notebook Juptyer</span><span class="sxs-lookup"><span data-stu-id="2e1ed-124">Invoking the resources estimator from Juptyer Notebooks</span></span>

<span data-ttu-id="2e1ed-125">Usare il Q# comando i Magic [% Estimate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) per eseguire l' Q# operazione.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-125">Use the IQ# magic command [%estimate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="2e1ed-126">Recupero dei dati stimati a livello di codice</span><span class="sxs-lookup"><span data-stu-id="2e1ed-126">Programmatically retrieving the estimated data</span></span>

<span data-ttu-id="2e1ed-127">Oltre a una tabella TSV, è possibile recuperare a livello di codice le risorse stimate durante l'esecuzione tramite la `Data` proprietà dello strumento di stima delle risorse.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-127">In addition to a TSV table, you can programmatically retrieve the resources estimated during the run via the `Data` property of the resources estimator.</span></span> <span data-ttu-id="2e1ed-128">La `Data` proprietà fornisce un' `System.DataTable` istanza con due colonne: `Metric` e `Sum` indicizzate in base ai nomi delle metriche.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-128">The `Data` property provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics' names.</span></span>

<span data-ttu-id="2e1ed-129">Nel codice seguente viene illustrato come recuperare e stampare il numero totale di `QubitClifford` `T` operazioni e `CNOT` utilizzate da un' Q# operazione:</span><span class="sxs-lookup"><span data-stu-id="2e1ed-129">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` operations used by a Q# operation:</span></span>

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

## <a name="metrics-reported"></a><span data-ttu-id="2e1ed-130">Metriche segnalate</span><span class="sxs-lookup"><span data-stu-id="2e1ed-130">Metrics Reported</span></span>

<span data-ttu-id="2e1ed-131">Lo strumento di stima delle risorse tiene traccia delle metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="2e1ed-131">The resources estimator tracks the following metrics:</span></span>

|<span data-ttu-id="2e1ed-132">Metrica</span><span class="sxs-lookup"><span data-stu-id="2e1ed-132">Metric</span></span>|<span data-ttu-id="2e1ed-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2e1ed-133">Description</span></span>|
|----|----|
|<span data-ttu-id="2e1ed-134">__CNOT__</span><span class="sxs-lookup"><span data-stu-id="2e1ed-134">__CNOT__</span></span>    |<span data-ttu-id="2e1ed-135">Il numero di esecuzioni delle `CNOT` operazioni, note anche come operazioni di Pauli X controllate.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-135">The run count of `CNOT` operations (also known as Controlled Pauli X operations).</span></span>|
|<span data-ttu-id="2e1ed-136">__QubitClifford__</span><span class="sxs-lookup"><span data-stu-id="2e1ed-136">__QubitClifford__</span></span> |<span data-ttu-id="2e1ed-137">Numero di esecuzioni di ogni singola operazione qubit Clifford e Pauli.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-137">The run count of any single qubit Clifford and Pauli operations.</span></span>|
|<span data-ttu-id="2e1ed-138">__Measure__</span><span class="sxs-lookup"><span data-stu-id="2e1ed-138">__Measure__</span></span>    |<span data-ttu-id="2e1ed-139">Numero di esecuzioni di qualsiasi misura.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-139">The run count of any measurements.</span></span>  |
|<span data-ttu-id="2e1ed-140">__R__</span><span class="sxs-lookup"><span data-stu-id="2e1ed-140">__R__</span></span>    |<span data-ttu-id="2e1ed-141">Il numero di esecuzioni di tutte le rotazioni a qubit singola, escluse le `T` operazioni Clifford e Pauli.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-141">The run count of any single-qubit rotations, excluding `T`, Clifford and Pauli operations.</span></span>  |
|<span data-ttu-id="2e1ed-142">__T__</span><span class="sxs-lookup"><span data-stu-id="2e1ed-142">__T__</span></span>    |<span data-ttu-id="2e1ed-143">Il numero di esecuzioni delle `T` operazioni e dei rispettivi coniugi, incluse le `T` operazioni, T_x = h. t. h e T_y = HY. t. HY.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-143">The run count of `T` operations and their conjugates, including the `T` operations, T_x = H.T.H, and T_y = Hy.T.Hy.</span></span>  |
|<span data-ttu-id="2e1ed-144">__Livello nidificazione__</span><span class="sxs-lookup"><span data-stu-id="2e1ed-144">__Depth__</span></span>|<span data-ttu-id="2e1ed-145">Profondità del circuito Quantum eseguito dall' Q# operazione (vedere di [seguito](#depth-width-and-qubitcount)).</span><span class="sxs-lookup"><span data-stu-id="2e1ed-145">Depth of the quantum circuit run by the Q# operation (see [below](#depth-width-and-qubitcount)).</span></span> <span data-ttu-id="2e1ed-146">Per impostazione predefinita, la metrica di profondità conta solo i `T` cancelli.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-146">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="2e1ed-147">Per informazioni dettagliate, vedere [contatore di profondità](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span><span class="sxs-lookup"><span data-stu-id="2e1ed-147">For more details, see [Depth Counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span></span>   |
|<span data-ttu-id="2e1ed-148">__Larghezza__</span><span class="sxs-lookup"><span data-stu-id="2e1ed-148">__Width__</span></span>|<span data-ttu-id="2e1ed-149">Larghezza del circuito Quantum eseguito dall' Q# operazione (vedere di [seguito](#depth-width-and-qubitcount)).</span><span class="sxs-lookup"><span data-stu-id="2e1ed-149">Width of the quantum circuit run by the Q# operation (see [below](#depth-width-and-qubitcount)).</span></span> <span data-ttu-id="2e1ed-150">Per impostazione predefinita, la metrica di profondità conta solo i `T` cancelli.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-150">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="2e1ed-151">Per altri dettagli, vedere [contatore della larghezza](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter).</span><span class="sxs-lookup"><span data-stu-id="2e1ed-151">For more details, see [Width Counter](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter).</span></span>   |
|<span data-ttu-id="2e1ed-152">__QubitCount__</span><span class="sxs-lookup"><span data-stu-id="2e1ed-152">__QubitCount__</span></span>    |<span data-ttu-id="2e1ed-153">Limite inferiore per il numero massimo di qubits allocati durante l'esecuzione dell' Q# operazione.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-153">The lower bound for the maximum number of qubits allocated during the run of the Q# operation.</span></span> <span data-ttu-id="2e1ed-154">Questa metrica potrebbe non essere compatibile con la __profondità__ (vedere di seguito).</span><span class="sxs-lookup"><span data-stu-id="2e1ed-154">This metric might not be compatible with __Depth__ (see below).</span></span>  |
|<span data-ttu-id="2e1ed-155">__BorrowedWidth__</span><span class="sxs-lookup"><span data-stu-id="2e1ed-155">__BorrowedWidth__</span></span>    |<span data-ttu-id="2e1ed-156">Numero massimo di qubits presi in prestito all'interno dell' Q# operazione.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-156">The maximum number of qubits borrowed inside the Q# operation.</span></span>  |


## <a name="depth-width-and-qubitcount"></a><span data-ttu-id="2e1ed-157">Depth, Width e QubitCount</span><span class="sxs-lookup"><span data-stu-id="2e1ed-157">Depth, Width, and QubitCount</span></span>

<span data-ttu-id="2e1ed-158">Le stime di profondità e larghezza segnalate sono compatibili tra loro.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-158">Reported Depth and Width estimates are compatible with each other.</span></span>
<span data-ttu-id="2e1ed-159">(In precedenza entrambi i numeri erano raggiungibili, ma sarebbero necessari circuiti diversi per la profondità e la larghezza). Attualmente entrambe le metriche in questa coppia possono essere realizzate dallo stesso circuito nello stesso momento.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-159">(Previously both numbers were achievable, but different circuits would be required for Depth and for Width.) Currently both metrics in this pair can be achieved by the same circuit at the same time.</span></span>

<span data-ttu-id="2e1ed-160">Vengono restituite le metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="2e1ed-160">The following metrics are reported:</span></span>

<span data-ttu-id="2e1ed-161">__Profondità:__ Per l'operazione radice: tempo necessario per eseguirlo presumendo tempi di controllo configurati.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-161">__Depth:__ For the root operation - time it takes to execute it assuming configured gate times.</span></span>
<span data-ttu-id="2e1ed-162">Per le operazioni denominate o per le operazioni successive, differenza oraria tra il più recente tempo di disponibilità qubit all'inizio e la fine dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-162">For operations called or subsequent operations - time difference between the latest qubit availability time at the beginning and the end of the operation.</span></span>

<span data-ttu-id="2e1ed-163">__Larghezza:__ Per l'operazione radice, il numero di qubits effettivamente usato per eseguirlo (e l'operazione che chiama).</span><span class="sxs-lookup"><span data-stu-id="2e1ed-163">__Width:__ For the root operation - number of qubits actually used to execute it (and operation it calls).</span></span>
<span data-ttu-id="2e1ed-164">Per operazioni denominate o operazioni successive: quante più qubits sono state usate oltre al qubits già usato all'inizio dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-164">For operations called or subsequent operations - how many more qubits were used in addition to the qubits already used at the beginning of the operation.</span></span>

<span data-ttu-id="2e1ed-165">Si noti che la qubits riutilizzata non contribuisce a questo numero.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-165">Please note, that reused qubits do not contribute to this number.</span></span>
<span data-ttu-id="2e1ed-166">Se, ad esempio, alcuni qubits sono stati rilasciati prima dell'avvio dell'operazione e tutti i qubit richiesti da questa operazione (e le operazioni chiamate da A) sono stati soddisfatti riutilizzando la versione precedente qubits, la larghezza dell'operazione A viene segnalata come 0.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-166">I.e. if a few qubits have been released before operation A starts, and all qubit demanded by this operation A (and operations called from A) were satisfied by reusing previously release qubits, the Width of operation A is reported as 0.</span></span> <span data-ttu-id="2e1ed-167">I qubits presi in prestito non contribuiscono alla larghezza.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-167">Successfully borrowed qubits do not contribute to the Width either.</span></span>

<span data-ttu-id="2e1ed-168">__QubitCount:__ Per l'operazione radice: numero minimo di qubits che sarebbe sufficiente per eseguire l'operazione (e le operazioni chiamate da esso).</span><span class="sxs-lookup"><span data-stu-id="2e1ed-168">__QubitCount:__ For the root operation - minimum number of qubits that would be sufficient to execute this operation (and operations called from it).</span></span>
<span data-ttu-id="2e1ed-169">Per le operazioni chiamate o operazioni successive: numero minimo di qubits che sarebbe sufficiente per eseguire questa operazione separatamente.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-169">For operations called or subsequent operations - minimum number of qubits that would be sufficient to execute this operation separately.</span></span> <span data-ttu-id="2e1ed-170">Questo numero non include qubits di input.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-170">This number doesn't include input qubits.</span></span> <span data-ttu-id="2e1ed-171">Include qubits presi in prestito.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-171">It does include borrowed qubits.</span></span>

<span data-ttu-id="2e1ed-172">Sono supportate due modalità operative.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-172">Two modes of operation are supported.</span></span> <span data-ttu-id="2e1ed-173">Per selezionare la modalità, impostare QCTraceSimulatorConfiguration. OptimizeDepth.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-173">Mode is selected by setting QCTraceSimulatorConfiguration.OptimizeDepth.</span></span>

<span data-ttu-id="2e1ed-174">__OptimizeDepth = false:__ Questa è la modalità predefinita.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-174">__OptimizeDepth=false:__ This is the default mode.</span></span> <span data-ttu-id="2e1ed-175">QubitManager è consigliato per il riutilizzo di qubits e riutilizzerà il qubits rilasciato prima di allocarne di nuovi.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-175">QubitManager is encouraged to reuse qubits and will reuse released qubits before allocating new ones.</span></span> <span data-ttu-id="2e1ed-176">Per la __larghezza__ dell'operazione radice diventa la larghezza minima (limite inferiore).</span><span class="sxs-lookup"><span data-stu-id="2e1ed-176">For the root operation __Width__ becomes the minimal width (lower bound).</span></span> <span data-ttu-id="2e1ed-177">Viene segnalato un livello di __profondità__ compatibile su cui è possibile ottenerlo.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-177">Compatible __Depth__ is reported on which it can be achieved.</span></span> <span data-ttu-id="2e1ed-178">__QubitCount__ sarà uguale a __Width__ per l'operazione radice presumendo che non si prenda in prestito.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-178">__QubitCount__ will be the same as __Width__ for the root operation assuming no borrowing.</span></span>

<span data-ttu-id="2e1ed-179">__OptimizeDepth = true:__ QubitManager è sconsigliato dal riuso di qubit e l'ottimizzazione basata su euristica per il riutilizzo del qubit viene eseguita durante e dopo l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-179">__OptimizeDepth=true:__ QubitManager is discouraged from qubit reuse and heuristic-based optimization for qubit reuse is performed during and after execution.</span></span> <span data-ttu-id="2e1ed-180">Per la __profondità__ dell'operazione radice diventa la profondità minima (limite inferiore).</span><span class="sxs-lookup"><span data-stu-id="2e1ed-180">For the root operation __Depth__ becomes the minimum depth (lower bound).</span></span> <span data-ttu-id="2e1ed-181">Per questa profondità viene segnalata la __larghezza__ compatibile, che è possibile ottenere contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-181">Compatible __Width__ is reported for this depth (both can be achieved at the same time).</span></span> <span data-ttu-id="2e1ed-182">Per ottimizzare la larghezza, le attività di controllo rilevate in un secondo momento nel programma potrebbero essere pianificate prima che vengano rilevate in precedenza nel programma, ma è stato pianificato il riutilizzo di qubits in modo tale che la profondità rimanga minima.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-182">To optimize width, gates encountered later in the program may be scheduled before the gates encountered earlier in the program, but qubits are scheduled to be reused in such a way that the depth remains minimal.</span></span> <span data-ttu-id="2e1ed-183">Quando qubits vengono riutilizzati in base ai valori temporali, è consigliabile che i tempi di controllo siano configurati come valori integer.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-183">As qubits are reused based on time values, it is recommended that the gate times are configured to be integer values.</span></span> <span data-ttu-id="2e1ed-184">Non è garantito che la __larghezza__ sia ottimale.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-184">__Width__ is not guaranteed to be optimal.</span></span> <span data-ttu-id="2e1ed-185">Per ulteriori informazioni, vedere la [larghezza e la profondità](https://github.com/microsoft/qsharp-runtime/tree/main/src/Simulation/Simulators/QCTraceSimulator/Docs)del white paper nello Tracer.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-185">More information can be found in the whitepaper [Width and Depth in the Tracer](https://github.com/microsoft/qsharp-runtime/tree/main/src/Simulation/Simulators/QCTraceSimulator/Docs).</span></span>

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="2e1ed-186">Come fornire la probabilità dei risultati di misurazione</span><span class="sxs-lookup"><span data-stu-id="2e1ed-186">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="2e1ed-187">È possibile utilizzare <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> dallo <xref:Microsoft.Quantum.Diagnostics> spazio dei nomi per fornire informazioni sulla probabilità prevista di un'operazione di misurazione.</span><span class="sxs-lookup"><span data-stu-id="2e1ed-187">You can use <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> from the <xref:Microsoft.Quantum.Diagnostics> namespace to provide information about the expected probability of a measurement operation.</span></span> <span data-ttu-id="2e1ed-188">Per altre informazioni, vedere [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span><span class="sxs-lookup"><span data-stu-id="2e1ed-188">For more information, see [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span></span>

## <a name="see-also"></a><span data-ttu-id="2e1ed-189">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="2e1ed-189">See also</span></span>

- [<span data-ttu-id="2e1ed-190">Simulatore di traccia Quantum</span><span class="sxs-lookup"><span data-stu-id="2e1ed-190">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="2e1ed-191">Simulatore di Toffoli</span><span class="sxs-lookup"><span data-stu-id="2e1ed-191">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="2e1ed-192">Simulatore di stato completo</span><span class="sxs-lookup"><span data-stu-id="2e1ed-192">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 
