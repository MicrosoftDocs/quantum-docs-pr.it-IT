---
title: Quantum Resources Estimator-Quantum Development Kit
description: Informazioni su Microsoft QDK Resources Estimator, che consente di stimare le risorse necessarie per eseguire una determinata istanza di un' Q# operazione in un computer Quantum.
author: anpaz-msft
ms.author: anpaz
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6138c098a4efe2797c7d7360573ddcb9cb70a6c1
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835928"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a><span data-ttu-id="e795e-103">Strumento di stima risorse di Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="e795e-103">Quantum Development Kit (QDK) resources estimator</span></span>

<span data-ttu-id="e795e-104">Come suggerisce il nome, la `ResourcesEstimator` classe stima le risorse necessarie per eseguire una determinata istanza di un' Q# operazione in un computer Quantum.</span><span class="sxs-lookup"><span data-stu-id="e795e-104">As the name implies, the `ResourcesEstimator` class estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span> <span data-ttu-id="e795e-105">Questo consente di eseguire l'operazione Quantum senza simulare effettivamente lo stato di un computer Quantum; per questo motivo, vengono stimate le risorse per Q# le operazioni che utilizzano migliaia di qubits, purché la parte classica del codice venga eseguita in un tempo ragionevole.</span><span class="sxs-lookup"><span data-stu-id="e795e-105">It accomplishes this by running the quantum operation without actually simulating the state of a quantum computer; for this reason, it estimates resources for Q# operations that use thousands of qubits, provided that the classical part of the code runs in a reasonable time.</span></span>

<span data-ttu-id="e795e-106">Lo strumento di stima delle risorse si basa su [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), che fornisce un set più completo di metriche e strumenti per facilitare il debug dei Q# programmi.</span><span class="sxs-lookup"><span data-stu-id="e795e-106">The resources estimator is built on top of the [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics and tools to help debug Q# programs.</span></span>

## <a name="invoking-and-running-the-resources-estimator"></a><span data-ttu-id="e795e-107">Richiamo ed esecuzione dello strumento di stima delle risorse</span><span class="sxs-lookup"><span data-stu-id="e795e-107">Invoking and running the resources estimator</span></span>

<span data-ttu-id="e795e-108">Per eseguire qualsiasi operazione, è possibile usare lo strumento di stima delle risorse Q# .</span><span class="sxs-lookup"><span data-stu-id="e795e-108">You can use the resources estimator to run any Q# operation.</span></span> <span data-ttu-id="e795e-109">Per ulteriori informazioni, vedere [modalità di esecuzione di un Q# programma](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="e795e-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-resources-estimator-from-c"></a><span data-ttu-id="e795e-110">Richiamo dello strumento di stima delle risorse da C #</span><span class="sxs-lookup"><span data-stu-id="e795e-110">Invoking the resources estimator from C#</span></span> 

<span data-ttu-id="e795e-111">Come per altri computer di destinazione, creare prima un'istanza della classe `ResourceEstimator` e quindi passarla come primo parametro del metodo `Run` di un'operazione.</span><span class="sxs-lookup"><span data-stu-id="e795e-111">As with other target machines, you first create an instance of the `ResourceEstimator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="e795e-112">Si noti che, a differenza della classe `QuantumSimulator`, la classe `ResourceEstimator` non implementa l'interfaccia <xref:System.IDisposable>, per cui non è necessario racchiuderla in un'istruzione `using`.</span><span class="sxs-lookup"><span data-stu-id="e795e-112">Note that, unlike the `QuantumSimulator` class, the `ResourceEstimator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

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

<span data-ttu-id="e795e-113">Come illustrato nell'esempio, `ResourcesEstimator` fornisce il `ToTSV()` metodo, che genera una tabella con valori delimitati da tabulazioni (TSV).</span><span class="sxs-lookup"><span data-stu-id="e795e-113">As the example shows, `ResourcesEstimator` provides the `ToTSV()` method, which generates a table with tab-separated values (TSV).</span></span> <span data-ttu-id="e795e-114">È possibile salvare la tabella in un file o visualizzarla nella console per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="e795e-114">You can save the table to a file or display it to the console for analysis.</span></span> <span data-ttu-id="e795e-115">Di seguito è riportato un esempio di output del programma precedente:</span><span class="sxs-lookup"><span data-stu-id="e795e-115">The following is a sample output from the preceding program:</span></span>

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
> <span data-ttu-id="e795e-116">Un' `ResourcesEstimator` istanza non reimposta i calcoli a ogni esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e795e-116">A `ResourcesEstimator` instance does not reset its calculations on every run.</span></span> <span data-ttu-id="e795e-117">Se si utilizza la stessa istanza per eseguire un'altra operazione, vengono aggregati i nuovi risultati con i risultati esistenti.</span><span class="sxs-lookup"><span data-stu-id="e795e-117">If you use the same instance to run another operation, it aggregates the new results with the existing results.</span></span> <span data-ttu-id="e795e-118">Se è necessario reimpostare i calcoli tra le esecuzioni, creare una nuova istanza per ogni esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e795e-118">If you need to reset calculations between runs, create a new instance for every run.</span></span>

### <a name="invoking-the-resources-estimator-from-python"></a><span data-ttu-id="e795e-119">Richiamo dello strumento di stima delle risorse da Python</span><span class="sxs-lookup"><span data-stu-id="e795e-119">Invoking the resources estimator from Python</span></span>

<span data-ttu-id="e795e-120">Usare il metodo [estimate_resources ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) dalla libreria Python con l'operazione importata Q# :</span><span class="sxs-lookup"><span data-stu-id="e795e-120">Use the [estimate_resources()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) method from the Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a><span data-ttu-id="e795e-121">Richiamo dell'estimatore di risorse dalla riga di comando</span><span class="sxs-lookup"><span data-stu-id="e795e-121">Invoking the resources estimator from the command line</span></span>

<span data-ttu-id="e795e-122">Quando si esegue un Q# programma dalla riga di comando, usare il parametro **--Simulator** (o **-s** Shortcut) per specificare il `ResourcesEstimator` computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e795e-122">When running a Q# program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the `ResourcesEstimator` target machine.</span></span> <span data-ttu-id="e795e-123">Il comando che segue esegue un programma usando lo strumento di stima delle risorse:</span><span class="sxs-lookup"><span data-stu-id="e795e-123">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a><span data-ttu-id="e795e-124">Richiamo dello strumento di stima delle risorse da notebook Juptyer</span><span class="sxs-lookup"><span data-stu-id="e795e-124">Invoking the resources estimator from Juptyer Notebooks</span></span>

<span data-ttu-id="e795e-125">Usare il Q# comando i Magic [% Estimate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) per eseguire l' Q# operazione.</span><span class="sxs-lookup"><span data-stu-id="e795e-125">Use the IQ# magic command [%estimate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="e795e-126">Recupero dei dati stimati a livello di codice</span><span class="sxs-lookup"><span data-stu-id="e795e-126">Programmatically retrieving the estimated data</span></span>

<span data-ttu-id="e795e-127">Oltre a una tabella TSV, è possibile recuperare a livello di codice le risorse stimate durante l'esecuzione tramite la `Data` proprietà dello strumento di stima delle risorse.</span><span class="sxs-lookup"><span data-stu-id="e795e-127">In addition to a TSV table, you can programmatically retrieve the resources estimated during the run via the `Data` property of the resources estimator.</span></span> <span data-ttu-id="e795e-128">La `Data` proprietà fornisce un' `System.DataTable` istanza con due colonne: `Metric` e `Sum` indicizzate in base ai nomi delle metriche.</span><span class="sxs-lookup"><span data-stu-id="e795e-128">The `Data` property provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics' names.</span></span>

<span data-ttu-id="e795e-129">Nel codice seguente viene illustrato come recuperare e stampare il numero totale di `QubitClifford` `T` operazioni e `CNOT` utilizzate da un' Q# operazione:</span><span class="sxs-lookup"><span data-stu-id="e795e-129">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` operations used by a Q# operation:</span></span>

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

## <a name="metrics-reported"></a><span data-ttu-id="e795e-130">Metriche segnalate</span><span class="sxs-lookup"><span data-stu-id="e795e-130">Metrics Reported</span></span>

<span data-ttu-id="e795e-131">Lo strumento di stima delle risorse tiene traccia delle metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="e795e-131">The resources estimator tracks the following metrics:</span></span>

|<span data-ttu-id="e795e-132">Metrica</span><span class="sxs-lookup"><span data-stu-id="e795e-132">Metric</span></span>|<span data-ttu-id="e795e-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e795e-133">Description</span></span>|
|----|----|
|<span data-ttu-id="e795e-134">__CNOT__</span><span class="sxs-lookup"><span data-stu-id="e795e-134">__CNOT__</span></span>    |<span data-ttu-id="e795e-135">Il numero di esecuzioni delle `CNOT` operazioni, note anche come operazioni di Pauli X controllate.</span><span class="sxs-lookup"><span data-stu-id="e795e-135">The run count of `CNOT` operations (also known as Controlled Pauli X operations).</span></span>|
|<span data-ttu-id="e795e-136">__QubitClifford__</span><span class="sxs-lookup"><span data-stu-id="e795e-136">__QubitClifford__</span></span> |<span data-ttu-id="e795e-137">Numero di esecuzioni di ogni singola operazione qubit Clifford e Pauli.</span><span class="sxs-lookup"><span data-stu-id="e795e-137">The run count of any single qubit Clifford and Pauli operations.</span></span>|
|<span data-ttu-id="e795e-138">__Measure__</span><span class="sxs-lookup"><span data-stu-id="e795e-138">__Measure__</span></span>    |<span data-ttu-id="e795e-139">Numero di esecuzioni di qualsiasi misura.</span><span class="sxs-lookup"><span data-stu-id="e795e-139">The run count of any measurements.</span></span>  |
|<span data-ttu-id="e795e-140">__R__</span><span class="sxs-lookup"><span data-stu-id="e795e-140">__R__</span></span>    |<span data-ttu-id="e795e-141">Il numero di esecuzioni di tutte le rotazioni a qubit singola, escluse le `T` operazioni Clifford e Pauli.</span><span class="sxs-lookup"><span data-stu-id="e795e-141">The run count of any single-qubit rotations, excluding `T`, Clifford and Pauli operations.</span></span>  |
|<span data-ttu-id="e795e-142">__T__</span><span class="sxs-lookup"><span data-stu-id="e795e-142">__T__</span></span>    |<span data-ttu-id="e795e-143">Il numero di esecuzioni delle `T` operazioni e dei rispettivi coniugi, incluse le `T` operazioni, T_x = h. t. h e T_y = HY. t. HY.</span><span class="sxs-lookup"><span data-stu-id="e795e-143">The run count of `T` operations and their conjugates, including the `T` operations, T_x = H.T.H, and T_y = Hy.T.Hy.</span></span>  |
|<span data-ttu-id="e795e-144">__Depth__</span><span class="sxs-lookup"><span data-stu-id="e795e-144">__Depth__</span></span>|<span data-ttu-id="e795e-145">Limite inferiore per la profondità del circuito Quantum eseguito dall' Q# operazione.</span><span class="sxs-lookup"><span data-stu-id="e795e-145">The lower bound for the depth of the quantum circuit run by the Q# operation.</span></span> <span data-ttu-id="e795e-146">Per impostazione predefinita, la metrica di profondità conta solo i `T` cancelli.</span><span class="sxs-lookup"><span data-stu-id="e795e-146">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="e795e-147">Per informazioni dettagliate, vedere [contatore di profondità](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span><span class="sxs-lookup"><span data-stu-id="e795e-147">For more details, see [Depth Counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span></span>   |
|<span data-ttu-id="e795e-148">__Larghezza__</span><span class="sxs-lookup"><span data-stu-id="e795e-148">__Width__</span></span>    |<span data-ttu-id="e795e-149">Limite inferiore per il numero massimo di qubits allocati durante l'esecuzione dell' Q# operazione.</span><span class="sxs-lookup"><span data-stu-id="e795e-149">The lower bound for the maximum number of qubits allocated during the run of the Q# operation.</span></span> <span data-ttu-id="e795e-150">Potrebbe non essere possibile ottenere contemporaneamente i limiti inferiori di __profondità__ e __larghezza__ .</span><span class="sxs-lookup"><span data-stu-id="e795e-150">It might not be possible to achieve both __Depth__ and __Width__ lower bounds simultaneously.</span></span>  |
|<span data-ttu-id="e795e-151">__BorrowedWidth__</span><span class="sxs-lookup"><span data-stu-id="e795e-151">__BorrowedWidth__</span></span>    |<span data-ttu-id="e795e-152">Numero massimo di qubits presi in prestito all'interno dell' Q# operazione.</span><span class="sxs-lookup"><span data-stu-id="e795e-152">The maximum number of qubits borrowed inside the Q# operation.</span></span>  |

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="e795e-153">Come fornire la probabilità dei risultati di misurazione</span><span class="sxs-lookup"><span data-stu-id="e795e-153">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="e795e-154">È possibile utilizzare <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> dallo <xref:microsoft.quantum.diagnostics> spazio dei nomi per fornire informazioni sulla probabilità prevista di un'operazione di misurazione.</span><span class="sxs-lookup"><span data-stu-id="e795e-154">You can use <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> from the <xref:microsoft.quantum.diagnostics> namespace to provide information about the expected probability of a measurement operation.</span></span> <span data-ttu-id="e795e-155">Per altre informazioni, vedere [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span><span class="sxs-lookup"><span data-stu-id="e795e-155">For more information, see [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span></span>

## <a name="see-also"></a><span data-ttu-id="e795e-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e795e-156">See also</span></span>

- [<span data-ttu-id="e795e-157">Simulatore di traccia Quantum</span><span class="sxs-lookup"><span data-stu-id="e795e-157">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="e795e-158">Simulatore di Toffoli</span><span class="sxs-lookup"><span data-stu-id="e795e-158">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="e795e-159">Simulatore di stato completo</span><span class="sxs-lookup"><span data-stu-id="e795e-159">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 