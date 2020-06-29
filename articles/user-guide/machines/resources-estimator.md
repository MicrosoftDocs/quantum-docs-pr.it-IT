---
title: Strumento di stima risorse del kit di sviluppo Quantum
description: "Informazioni sullo strumento di stima delle risorse, che consente di stimare le risorse necessarie per eseguire un'istanza specifica di un'operazione Q # in un computer Quantum."
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 1/22/2019
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: cbb1c274b64738cc4b47869563d7d02eb717afbc
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415259"
---
# <a name="the-resources-estimator-target-machine"></a><span data-ttu-id="7dc5a-103">Computer di destinazione dello strumento di stima risorse</span><span class="sxs-lookup"><span data-stu-id="7dc5a-103">The Resources Estimator Target Machine</span></span>

<span data-ttu-id="7dc5a-104">Come suggerisce il nome, il `ResourcesEstimator` stima le risorse necessarie per eseguire un'istanza specifica di un'operazione Q # in un computer Quantum.</span><span class="sxs-lookup"><span data-stu-id="7dc5a-104">As the name implies, the `ResourcesEstimator` estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>
<span data-ttu-id="7dc5a-105">Questo consente di eseguire l'operazione Quantum senza simulare effettivamente lo stato di un computer Quantum; per questo motivo, può stimare le risorse per le operazioni Q # che usano migliaia di qubits, se la parte classica del codice può essere eseguita in un tempo ragionevole.</span><span class="sxs-lookup"><span data-stu-id="7dc5a-105">It accomplishes this by executing the quantum operation without actually simulating the state of a quantum computer; for this reason, it can estimate resources for Q# operations that use thousands of qubits, if the classical part of the code can be run in a reasonable time.</span></span>

## <a name="usage"></a><span data-ttu-id="7dc5a-106">Uso</span><span class="sxs-lookup"><span data-stu-id="7dc5a-106">Usage</span></span>

<span data-ttu-id="7dc5a-107">`ResourcesEstimator`È solo un altro tipo di computer di destinazione, quindi può essere usato per eseguire qualsiasi operazione Q #.</span><span class="sxs-lookup"><span data-stu-id="7dc5a-107">The `ResourcesEstimator` is just another type of target machine, thus it can be used to run any Q# operation.</span></span> 

<span data-ttu-id="7dc5a-108">Come altri computer di destinazione, per usarlo in un programma host C# creare un'istanza e passarla come primo parametro del metodo dell'operazione `Run` :</span><span class="sxs-lookup"><span data-stu-id="7dc5a-108">As other target machines, to use it on a C# host program create an instance and pass it as the first parameter of the operation's `Run` method:</span></span>

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

<span data-ttu-id="7dc5a-109">Come illustrato nell'esempio, `ResourcesEstimator` fornisce un `ToTSV()` metodo per generare una tabella con valori delimitati da tabulazioni (TSV) che possono essere salvati in un file o scritti nella console per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="7dc5a-109">As the example shows, the `ResourcesEstimator` provides a `ToTSV()` method to generate a table with tab-separated-values (TSV) that can be saved into a file or written to the console for analysis.</span></span> <span data-ttu-id="7dc5a-110">L'output del programma precedente dovrebbe avere un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="7dc5a-110">The output of the above program should look something like this:</span></span>

```Output
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
> <span data-ttu-id="7dc5a-111">Non `ResourcesEstimator` Reimposta i calcoli a ogni esecuzione, se viene utilizzata la stessa istanza per eseguire un'altra operazione, i conteggi vengono aggregati in base ai risultati esistenti.</span><span class="sxs-lookup"><span data-stu-id="7dc5a-111">The `ResourcesEstimator` does not reset its calculations on every run, if the same instance is used to execute another operation it will keep aggregating counts on top of existing results.</span></span>
> <span data-ttu-id="7dc5a-112">Se è necessario reimpostare i calcoli tra le esecuzioni, creare una nuova istanza per ogni esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7dc5a-112">If you need to reset calculations between runs, create a new instance for every execution.</span></span>


## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="7dc5a-113">Recupero dei dati stimati a livello di codice</span><span class="sxs-lookup"><span data-stu-id="7dc5a-113">Programmatically Retrieving the Estimated Data</span></span>

<span data-ttu-id="7dc5a-114">Oltre a una tabella TSV, le risorse stimate possono essere recuperate a livello di codice tramite la `ResourcesEstimator` `Data` proprietà di.</span><span class="sxs-lookup"><span data-stu-id="7dc5a-114">In addition to a TSV table, the resources estimated can be retrieved programmatically via the `ResourcesEstimator`'s `Data` property.</span></span> <span data-ttu-id="7dc5a-115">`Data`fornisce un' `System.DataTable` istanza con due colonne: `Metric` e `Sum` , indicizzate in base ai nomi delle metriche.</span><span class="sxs-lookup"><span data-stu-id="7dc5a-115">`Data` provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics names.</span></span>

<span data-ttu-id="7dc5a-116">Il codice seguente illustra come recuperare e stampare il numero totale di `QubitClifford` `T` porte e di `CNOT` cancelli usati da un'operazione Q #:</span><span class="sxs-lookup"><span data-stu-id="7dc5a-116">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` gates used by a Q# operation:</span></span>

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

## <a name="metrics-reported"></a><span data-ttu-id="7dc5a-117">Metriche segnalate</span><span class="sxs-lookup"><span data-stu-id="7dc5a-117">Metrics Reported</span></span>

<span data-ttu-id="7dc5a-118">Di seguito è riportato l'elenco delle metriche stimate dal `ResourcesEstimator` :</span><span class="sxs-lookup"><span data-stu-id="7dc5a-118">The following is the list of metrics estimated by the `ResourcesEstimator`:</span></span>

* <span data-ttu-id="7dc5a-119">__CNOT__: il conteggio di CNOT (noto anche come controllo di Pauli X) eseguito.</span><span class="sxs-lookup"><span data-stu-id="7dc5a-119">__CNOT__: The count of CNOT (also known as the Controlled Pauli X gate) gates executed.</span></span>
* <span data-ttu-id="7dc5a-120">__QubitClifford__: numero di ogni singolo qubit Clifford e Pauli Gate eseguiti.</span><span class="sxs-lookup"><span data-stu-id="7dc5a-120">__QubitClifford__: The count of any single qubit Clifford and Pauli gates executed.</span></span>
* <span data-ttu-id="7dc5a-121">__Measure__: numero di eventuali misurazioni eseguite.</span><span class="sxs-lookup"><span data-stu-id="7dc5a-121">__Measure__:  The count of any measurements executed.</span></span>
* <span data-ttu-id="7dc5a-122">__R__: numero di tutte le rotazioni qubit eseguite, escluse le verifiche T, Clifford e Pauli.</span><span class="sxs-lookup"><span data-stu-id="7dc5a-122">__R__: The count of any single qubit rotations executed, excluding T, Clifford and Pauli gates.</span></span>
* <span data-ttu-id="7dc5a-123">__T__: conteggio di t Gates e dei rispettivi coniugi, inclusi t gate, T_x = h. t. h e T_y = HY. t. HY, eseguito.</span><span class="sxs-lookup"><span data-stu-id="7dc5a-123">__T__: The count of T gates and their conjugates, including the T gate, T_x = H.T.H, and T_y = Hy.T.Hy, executed.</span></span>
* <span data-ttu-id="7dc5a-124">__Depth__: limite inferiore per la profondità del circuito Quantum eseguito dall'operazione Q #.</span><span class="sxs-lookup"><span data-stu-id="7dc5a-124">__Depth__: The lower bound for the depth of the quantum circuit executed by the Q# operation.</span></span> <span data-ttu-id="7dc5a-125">Per impostazione predefinita, solo i cancelli T vengono conteggiati nella profondità, vedere il [contatore Depth](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) per i dettagli.</span><span class="sxs-lookup"><span data-stu-id="7dc5a-125">By default, only T gates are counted in the depth, see [depth counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) for details.</span></span>
* <span data-ttu-id="7dc5a-126">__Width__: limite inferiore per il numero massimo di qubits allocati durante l'esecuzione dell'operazione Q #.</span><span class="sxs-lookup"><span data-stu-id="7dc5a-126">__Width__: The lower bound for the maximum number of qubits allocated during the execution of the Q# operation.</span></span> <span data-ttu-id="7dc5a-127">Potrebbe non essere possibile ottenere contemporaneamente i limiti inferiori di __profondità__ e __larghezza__ .</span><span class="sxs-lookup"><span data-stu-id="7dc5a-127">It might not be possible to achieve both __Depth__ and __Width__ lower bounds simultaneously.</span></span>
* <span data-ttu-id="7dc5a-128">__BorrowedWidth__: numero massimo di qubits presi in prestito nell'operazione Q #.</span><span class="sxs-lookup"><span data-stu-id="7dc5a-128">__BorrowedWidth__: Maximum number of qubits borrowed inside the Q# operation.</span></span>


## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="7dc5a-129">Fornire la probabilità dei risultati di misurazione</span><span class="sxs-lookup"><span data-stu-id="7dc5a-129">Providing the Probability of Measurement Outcomes</span></span>

<span data-ttu-id="7dc5a-130"><xref:microsoft.quantum.intrinsic.assertprob>dallo <xref:microsoft.quantum.intrinsic> spazio dei nomi può essere usato per fornire informazioni sulla probabilità prevista di una misurazione per facilitare l'esecuzione del programma Q #.</span><span class="sxs-lookup"><span data-stu-id="7dc5a-130"><xref:microsoft.quantum.intrinsic.assertprob> from the <xref:microsoft.quantum.intrinsic> namespace can be used to provide information about the expected probability of a measurement to help drive the execution of the Q# program.</span></span> <span data-ttu-id="7dc5a-131">L'esempio seguente illustra questi concetti.</span><span class="sxs-lookup"><span data-stu-id="7dc5a-131">The following example illustrates this:</span></span>

```qsharp
operation Teleport(source : Qubit, target : Qubit) : Unit {

    using (qubit = Qubit()) {

        H(q);
        CNOT(qubit, target);

        CNOT(source, qubit);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [qubit], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(qubit) == One) { X(target); X(qubit); }
    }
}
```

<span data-ttu-id="7dc5a-132">Quando il `ResourcesEstimator` rileva che esegue la `AssertProb` misurazione `PauliZ` su `source` e `q` deve essere fornito un risultato di `Zero` con probabilità 0,5.</span><span class="sxs-lookup"><span data-stu-id="7dc5a-132">When the `ResourcesEstimator` encounters `AssertProb` it will record that measuring `PauliZ` on `source` and `q` should be given an outcome of `Zero` with probability 0.5.</span></span> <span data-ttu-id="7dc5a-133">Quando viene eseguito `M` in un secondo momento, troverà i valori registrati delle probabilità di risultato e `M` restituirà `Zero` o `One` con la probabilità 0,5.</span><span class="sxs-lookup"><span data-stu-id="7dc5a-133">When it executes `M` later, it will find the recorded values of the outcome probabilities and `M` will return `Zero` or `One` with probability 0.5.</span></span>


## <a name="see-also"></a><span data-ttu-id="7dc5a-134">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="7dc5a-134">See also</span></span>

<span data-ttu-id="7dc5a-135">`ResourcesEstimator`Si basa sul [simulatore di traccia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Quantum computer, che fornisce un set più completo di metriche, la possibilità di segnalare le metriche nel grafico chiamato completo e funzionalità come il [controllo degli input distinti](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) per facilitare la ricerca di bug nei programmi Q #.</span><span class="sxs-lookup"><span data-stu-id="7dc5a-135">The `ResourcesEstimator` is built on top of the quantum computer [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics, the ability to report metrics on the full call-graph, and features like [distinct inputs checker](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) to help find bugs on Q# programs.</span></span> <span data-ttu-id="7dc5a-136">Per ulteriori informazioni, fare riferimento alla documentazione del [simulatore di traccia](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="7dc5a-136">Please refer to the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) documentation for more information.</span></span>

