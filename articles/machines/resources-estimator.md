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
# <a name="the-resourcesestimator-target-machine"></a>Il computer di destinazione ResourcesEstimator

Come suggerisce il nome, il `ResourcesEstimator` stima le risorse necessarie per eseguire un'istanza specifica di un'operazione Q # in un computer Quantum.
Questo consente di eseguire l'operazione Quantum senza simulare effettivamente lo stato di un computer Quantum; per questo motivo, è possibile stimare le risorse per le operazioni Q # che usano migliaia di qubits.

## <a name="usage"></a>Utilizzo

Il `ResourcesEstimator` è solo un altro tipo di computer di destinazione, quindi può essere usato per eseguire qualsiasi operazione Q #. 

Come altri computer di destinazione, per utilizzarlo in C# un programma host creare un'istanza di e passarla come primo parametro del metodo di `Run` dell'operazione:

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

Come illustrato nell'esempio, il `ResourcesEstimator` fornisce un metodo `ToTSV()` per generare una tabella con valori separati da tabulazioni (TSV) che possono essere salvati in un file o scritti nella console per l'analisi. L'output del programma precedente dovrebbe avere un aspetto simile al seguente:

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
> Il `ResourcesEstimator` non reimposta i calcoli a ogni esecuzione, se viene utilizzata la stessa istanza per eseguire un'altra operazione, i conteggi vengono aggregati in base ai risultati esistenti.
> Se è necessario reimpostare i calcoli tra le esecuzioni, creare una nuova istanza per ogni esecuzione.


## <a name="programmatically-retrieving-the-estimated-data"></a>Recupero dei dati stimati a livello di codice

Oltre a una tabella TSV, le risorse stimate possono essere recuperate a livello di codice tramite la proprietà `Data` del `ResourcesEstimator`. `Data` fornisce un'istanza `System.DataTable` con due colonne: `Metric` e `Sum`, indicizzate in base ai nomi delle metriche.

Il codice seguente illustra come recuperare e stampare il numero totale di `QubitClifford`, `T` e `CNOT` Gate usati da un'operazione Q #:

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

Di seguito è riportato l'elenco delle metriche stimate dal `ResourcesEstimator`:

* __CNOT__: il conteggio di CNOT (noto anche come controllo di Pauli X) eseguito.
* __QubitClifford__: numero di ogni singolo qubit Clifford e Pauli Gate eseguiti.
* __Measure__: numero di eventuali misurazioni eseguite.
* __R__: numero di tutte le rotazioni qubit eseguite, escluse le verifiche T, Clifford e Pauli.
* __T__: conteggio di t Gates e dei rispettivi coniugi, inclusi t Gate, T_x = H. t. h e T_y = HY. t. HY, eseguito.
* __Depth__: profondità del circuito Quantum eseguito dall'operazione Q #. Per impostazione predefinita, solo i cancelli T vengono conteggiati nella profondità, vedere il [contatore Depth](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) per i dettagli.
* __Width__: numero massimo di qubits allocati durante l'esecuzione dell'operazione Q #.
* __BorrowedWidth__: numero massimo di qubits presi in prestito nell'operazione Q #.


## <a name="providing-the-probability-of-measurement-outcomes"></a>Fornire la probabilità di risultati di misurazione

<xref:microsoft.quantum.primitive.assertprob> dallo spazio dei nomi <xref:microsoft.quantum.primitive> può essere usato per fornire informazioni sulla probabilità prevista di una misurazione per facilitare l'esecuzione del programma Q #. L'esempio seguente illustra questi concetti.

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

Quando il `ResourcesEstimator` incontra `AssertProb`, registrerà che la misurazione `PauliZ` su `source` e `ancilla` deve avere un risultato di `Zero` con probabilità 0,5. Quando viene eseguito `M` in un secondo momento, troverà i valori registrati delle probabilità di risultato e `M` restituirà `Zero` o `One` con probabilità 0,5.


## <a name="see-also"></a>Vedi anche

Il `ResourcesEstimator` si basa sul [simulatore di traccia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Quantum computer, che fornisce un set più completo di metriche, la possibilità di segnalare le metriche nel grafico chiamato completo e funzionalità come il [controllo degli input distinti](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) per facilitare la ricerca di bug nei programmi Q #. Per ulteriori informazioni, fare riferimento alla documentazione del [simulatore di traccia](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .

