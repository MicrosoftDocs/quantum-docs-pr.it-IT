---
title: Strumento di stima risorse del kit di sviluppo Quantum | Microsoft Docs
description: Panoramica dello strumento di stima risorse Microsoft Quantum Development Kit
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 1/22/2019
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: 591e306b3001934bd81342a533e3f6ca25129781
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184985"
---
# <a name="the-resourcesestimator-target-machine"></a><span data-ttu-id="f97ef-103">Il computer di destinazione ResourcesEstimator</span><span class="sxs-lookup"><span data-stu-id="f97ef-103">The ResourcesEstimator Target Machine</span></span>

<span data-ttu-id="f97ef-104">Come suggerisce il nome, il `ResourcesEstimator` stima le risorse necessarie per eseguire un'istanza specifica di un'operazione Q # in un computer Quantum.</span><span class="sxs-lookup"><span data-stu-id="f97ef-104">As the name implies, the `ResourcesEstimator` estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>
<span data-ttu-id="f97ef-105">Questo consente di eseguire l'operazione Quantum senza simulare effettivamente lo stato di un computer Quantum; per questo motivo, è possibile stimare le risorse per le operazioni Q # che usano migliaia di qubits.</span><span class="sxs-lookup"><span data-stu-id="f97ef-105">It accomplishes this by executing the quantum operation without actually simulating the state of a quantum computer; for this reason, it can estimate resources for Q# operations that use thousands of qubits.</span></span>

## <a name="usage"></a><span data-ttu-id="f97ef-106">Utilizzo</span><span class="sxs-lookup"><span data-stu-id="f97ef-106">Usage</span></span>

<span data-ttu-id="f97ef-107">Il `ResourcesEstimator` è solo un altro tipo di computer di destinazione, quindi può essere usato per eseguire qualsiasi operazione Q #.</span><span class="sxs-lookup"><span data-stu-id="f97ef-107">The `ResourcesEstimator` is just another type of target machine, thus it can be used to run any Q# operation.</span></span> 

<span data-ttu-id="f97ef-108">Come altri computer di destinazione, per utilizzarlo in C# un programma host creare un'istanza di e passarla come primo parametro del metodo di `Run` dell'operazione:</span><span class="sxs-lookup"><span data-stu-id="f97ef-108">As other target machines, to use it on a C# host program create an instance and pass it as the first parameter of the operation's `Run` method:</span></span>

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

<span data-ttu-id="f97ef-109">Come illustrato nell'esempio, il `ResourcesEstimator` fornisce un metodo `ToTSV()` per generare una tabella con valori separati da tabulazioni (TSV) che possono essere salvati in un file o scritti nella console per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="f97ef-109">As the example shows, the `ResourcesEstimator` provides a `ToTSV()` method to generate a table with tab-seperated-values (TSV) that can be saved into a file or written to the console for analysis.</span></span> <span data-ttu-id="f97ef-110">L'output del programma precedente dovrebbe avere un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="f97ef-110">The output of the above program should look something like this:</span></span>

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
> <span data-ttu-id="f97ef-111">Il `ResourcesEstimator` non reimposta i calcoli a ogni esecuzione, se viene utilizzata la stessa istanza per eseguire un'altra operazione, i conteggi vengono aggregati in base ai risultati esistenti.</span><span class="sxs-lookup"><span data-stu-id="f97ef-111">The `ResourcesEstimator` does not reset its calculations on every run, if the same instance is used to execute another operation it will keep aggregating counts on top of existing results.</span></span>
> <span data-ttu-id="f97ef-112">Se è necessario reimpostare i calcoli tra le esecuzioni, creare una nuova istanza per ogni esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f97ef-112">If you need to reset calculations between runs, create a new instance for every execution.</span></span>


## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="f97ef-113">Recupero dei dati stimati a livello di codice</span><span class="sxs-lookup"><span data-stu-id="f97ef-113">Programmatically Retrieving the Estimated Data</span></span>

<span data-ttu-id="f97ef-114">Oltre a una tabella TSV, le risorse stimate possono essere recuperate a livello di codice tramite la proprietà `Data` del `ResourcesEstimator`.</span><span class="sxs-lookup"><span data-stu-id="f97ef-114">In addition to a TSV table, the resources estimated can be retrieved programmatically via the `ResourcesEstimator`'s `Data` property.</span></span> <span data-ttu-id="f97ef-115">`Data` fornisce un'istanza `System.DataTable` con due colonne: `Metric` e `Sum`, indicizzate in base ai nomi delle metriche.</span><span class="sxs-lookup"><span data-stu-id="f97ef-115">`Data` provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics names.</span></span>

<span data-ttu-id="f97ef-116">Il codice seguente illustra come recuperare e stampare il numero totale di `QubitClifford`, `T` e `CNOT` Gate usati da un'operazione Q #:</span><span class="sxs-lookup"><span data-stu-id="f97ef-116">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` gates used by a Q# operation:</span></span>

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

## <a name="metrics-reported"></a><span data-ttu-id="f97ef-117">Metriche segnalate</span><span class="sxs-lookup"><span data-stu-id="f97ef-117">Metrics Reported</span></span>

<span data-ttu-id="f97ef-118">Di seguito è riportato l'elenco delle metriche stimate dal `ResourcesEstimator`:</span><span class="sxs-lookup"><span data-stu-id="f97ef-118">The following is the list of metrics estimated by the `ResourcesEstimator`:</span></span>

* <span data-ttu-id="f97ef-119">__CNOT__: il conteggio di CNOT (noto anche come controllo di Pauli X) eseguito.</span><span class="sxs-lookup"><span data-stu-id="f97ef-119">__CNOT__: The count of CNOT (also known as the Controlled Pauli X gate) gates executed.</span></span>
* <span data-ttu-id="f97ef-120">__QubitClifford__: numero di ogni singolo qubit Clifford e Pauli Gate eseguiti.</span><span class="sxs-lookup"><span data-stu-id="f97ef-120">__QubitClifford__: The count of any single qubit Clifford and Pauli gates executed.</span></span>
* <span data-ttu-id="f97ef-121">__Measure__: numero di eventuali misurazioni eseguite.</span><span class="sxs-lookup"><span data-stu-id="f97ef-121">__Measure__:  The count of any measurements executed.</span></span>
* <span data-ttu-id="f97ef-122">__R__: numero di tutte le rotazioni qubit eseguite, escluse le verifiche T, Clifford e Pauli.</span><span class="sxs-lookup"><span data-stu-id="f97ef-122">__R__: The count of any single qubit rotations executed, excluding T, Clifford and Pauli gates.</span></span>
* <span data-ttu-id="f97ef-123">__T__: conteggio di t Gates e dei rispettivi coniugi, inclusi t Gate, T_x = H. t. h e T_y = HY. t. HY, eseguito.</span><span class="sxs-lookup"><span data-stu-id="f97ef-123">__T__: The count of T gates and their conjugates, including the T gate, T_x = H.T.H, and T_y = Hy.T.Hy, executed.</span></span>
* <span data-ttu-id="f97ef-124">__Depth__: profondità del circuito Quantum eseguito dall'operazione Q #.</span><span class="sxs-lookup"><span data-stu-id="f97ef-124">__Depth__: Depth of the quantum circuit executed by the Q# operation.</span></span> <span data-ttu-id="f97ef-125">Per impostazione predefinita, solo i cancelli T vengono conteggiati nella profondità, vedere il [contatore Depth](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) per i dettagli.</span><span class="sxs-lookup"><span data-stu-id="f97ef-125">By default, only T gates are counted in the depth, see [depth counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) for details.</span></span>
* <span data-ttu-id="f97ef-126">__Width__: numero massimo di qubits allocati durante l'esecuzione dell'operazione Q #.</span><span class="sxs-lookup"><span data-stu-id="f97ef-126">__Width__: Maximum number of qubits allocated during the execution of the Q# operation.</span></span>
* <span data-ttu-id="f97ef-127">__BorrowedWidth__: numero massimo di qubits presi in prestito nell'operazione Q #.</span><span class="sxs-lookup"><span data-stu-id="f97ef-127">__BorrowedWidth__: Maximum number of qubits borrowed inside the Q# operation.</span></span>


## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="f97ef-128">Fornire la probabilità di risultati di misurazione</span><span class="sxs-lookup"><span data-stu-id="f97ef-128">Providing the Probability of Measurement Outcomes</span></span>

<span data-ttu-id="f97ef-129"><xref:microsoft.quantum.primitive.assertprob> dallo spazio dei nomi <xref:microsoft.quantum.primitive> può essere usato per fornire informazioni sulla probabilità prevista di una misurazione per facilitare l'esecuzione del programma Q #.</span><span class="sxs-lookup"><span data-stu-id="f97ef-129"><xref:microsoft.quantum.primitive.assertprob> from the <xref:microsoft.quantum.primitive> namespace can be used to provide information about the expected probability of a measurement to help drive the execution of the Q# program.</span></span> <span data-ttu-id="f97ef-130">L'esempio seguente illustra questi concetti.</span><span class="sxs-lookup"><span data-stu-id="f97ef-130">The following example illustrates this:</span></span>

```qsharp
operation Teleportation (source : Qubit, target : Qubit) : Unit {

    using (ancilla = Qubit()) {

        H(ancilla);
        CNOT(ancilla, target);

        CNOT(source, ancilla);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [ancilla], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(ancilla) == One) { X(target); X(ancilla); }
    }
}
```

<span data-ttu-id="f97ef-131">Quando il `ResourcesEstimator` incontra `AssertProb`, registrerà che la misurazione `PauliZ` su `source` e `ancilla` deve avere un risultato di `Zero` con probabilità 0,5.</span><span class="sxs-lookup"><span data-stu-id="f97ef-131">When the `ResourcesEstimator` encounters `AssertProb` it will record that measuring `PauliZ` on `source` and `ancilla` should be given an outcome of `Zero` with probability 0.5.</span></span> <span data-ttu-id="f97ef-132">Quando viene eseguito `M` in un secondo momento, troverà i valori registrati delle probabilità di risultato e `M` restituirà `Zero` o `One` con probabilità 0,5.</span><span class="sxs-lookup"><span data-stu-id="f97ef-132">When it executes `M` later, it will find the recorded values of the outcome probabilities and `M` will return `Zero` or `One` with probability 0.5.</span></span>


## <a name="see-also"></a><span data-ttu-id="f97ef-133">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="f97ef-133">See also</span></span>

<span data-ttu-id="f97ef-134">Il `ResourcesEstimator` si basa sul [simulatore di traccia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Quantum computer, che fornisce un set più completo di metriche, la possibilità di segnalare le metriche nel grafico chiamato completo e funzionalità come il [controllo degli input distinti](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) per facilitare la ricerca di bug nei programmi Q #.</span><span class="sxs-lookup"><span data-stu-id="f97ef-134">The `ResourcesEstimator` is built on top of the quantum computer [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics, the ability to report metrics on the full call-graph, and features like [distinct inputs checker](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) to help find bugs on Q# programs.</span></span> <span data-ttu-id="f97ef-135">Per ulteriori informazioni, fare riferimento alla documentazione del [simulatore di traccia](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="f97ef-135">Please refer to the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) documentation for more information.</span></span>

