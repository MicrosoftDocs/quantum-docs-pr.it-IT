---
title: Strumento di stima risorse del kit di sviluppo Quantum
description: "Informazioni sullo strumento di stima delle risorse, che consente di stimare le risorse necessarie per eseguire un'istanza specifica di un'operazione Q # in un computer Quantum."
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 1/22/2019
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: b0c800c3946d2e4ba4457127fb9495dc9dcf2934
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274888"
---
# <a name="the-resources-estimator-target-machine"></a>Computer di destinazione dello strumento di stima risorse

Come suggerisce il nome, il `ResourcesEstimator` stima le risorse necessarie per eseguire un'istanza specifica di un'operazione Q # in un computer Quantum.
Questo consente di eseguire l'operazione Quantum senza simulare effettivamente lo stato di un computer Quantum; per questo motivo, può stimare le risorse per le operazioni Q # che usano migliaia di qubits, se la parte classica del codice può essere eseguita in un tempo ragionevole.

## <a name="usage"></a>Utilizzo

`ResourcesEstimator`È solo un altro tipo di computer di destinazione, quindi può essere usato per eseguire qualsiasi operazione Q #. 

Come altri computer di destinazione, per usarlo in un programma host C# creare un'istanza e passarla come primo parametro del metodo dell'operazione `Run` :

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

Come illustrato nell'esempio, `ResourcesEstimator` fornisce un `ToTSV()` metodo per generare una tabella con valori delimitati da tabulazioni (TSV) che possono essere salvati in un file o scritti nella console per l'analisi. L'output del programma precedente dovrebbe avere un aspetto simile al seguente:

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
> Non `ResourcesEstimator` Reimposta i calcoli a ogni esecuzione, se viene utilizzata la stessa istanza per eseguire un'altra operazione, i conteggi vengono aggregati in base ai risultati esistenti.
> Se è necessario reimpostare i calcoli tra le esecuzioni, creare una nuova istanza per ogni esecuzione.


## <a name="programmatically-retrieving-the-estimated-data"></a>Recupero dei dati stimati a livello di codice

Oltre a una tabella TSV, le risorse stimate possono essere recuperate a livello di codice tramite la `ResourcesEstimator` `Data` proprietà di. `Data`fornisce un' `System.DataTable` istanza con due colonne: `Metric` e `Sum` , indicizzate in base ai nomi delle metriche.

Il codice seguente illustra come recuperare e stampare il numero totale di `QubitClifford` `T` porte e di `CNOT` cancelli usati da un'operazione Q #:

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

## <a name="metrics-reported"></a>Metriche segnalate

Di seguito è riportato l'elenco delle metriche stimate dal `ResourcesEstimator` :

* __CNOT__: il conteggio di CNOT (noto anche come controllo di Pauli X) eseguito.
* __QubitClifford__: numero di ogni singolo qubit Clifford e Pauli Gate eseguiti.
* __Measure__: numero di eventuali misurazioni eseguite.
* __R__: numero di tutte le rotazioni qubit eseguite, escluse le verifiche T, Clifford e Pauli.
* __T__: conteggio di t Gates e dei rispettivi coniugi, inclusi t gate, T_x = h. t. h e T_y = HY. t. HY, eseguito.
* __Depth__: profondità del circuito Quantum eseguito dall'operazione Q #. Per impostazione predefinita, solo i cancelli T vengono conteggiati nella profondità, vedere il [contatore Depth](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) per i dettagli.
* __Width__: numero massimo di qubits allocati durante l'esecuzione dell'operazione Q #.
* __BorrowedWidth__: numero massimo di qubits presi in prestito nell'operazione Q #.


## <a name="providing-the-probability-of-measurement-outcomes"></a>Fornire la probabilità dei risultati di misurazione

<xref:microsoft.quantum.intrinsic.assertprob>dallo <xref:microsoft.quantum.intrinsic> spazio dei nomi può essere usato per fornire informazioni sulla probabilità prevista di una misurazione per facilitare l'esecuzione del programma Q #. L'esempio seguente illustra questi concetti.

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

Quando il `ResourcesEstimator` rileva che esegue la `AssertProb` misurazione `PauliZ` su `source` e `q` deve essere fornito un risultato di `Zero` con probabilità 0,5. Quando viene eseguito `M` in un secondo momento, troverà i valori registrati delle probabilità di risultato e `M` restituirà `Zero` o `One` con la probabilità 0,5.


## <a name="see-also"></a>Vedi anche

`ResourcesEstimator`Si basa sul [simulatore di traccia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Quantum computer, che fornisce un set più completo di metriche, la possibilità di segnalare le metriche nel grafico chiamato completo e funzionalità come il [controllo degli input distinti](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) per facilitare la ricerca di bug nei programmi Q #. Per ulteriori informazioni, fare riferimento alla documentazione del [simulatore di traccia](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
