---
title: Quantum Resources Estimator-Quantum Development Kit
description: Informazioni su Microsoft QDK Resources Estimator, che consente di stimare le risorse necessarie per eseguire una determinata istanza di un' Q# operazione in un computer Quantum.
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1892431c3e332385a5bcefa357eb64a9fac3f381
ms.sourcegitcommit: 11bd357baeb6ab53a402882979e75964d0869b57
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2020
ms.locfileid: "88992242"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a>Strumento di stima risorse di Quantum Development Kit (QDK)

Come suggerisce il nome, la `ResourcesEstimator` classe stima le risorse necessarie per eseguire una determinata istanza di un' Q# operazione in un computer Quantum. Questo consente di eseguire l'operazione Quantum senza simulare effettivamente lo stato di un computer Quantum; per questo motivo, vengono stimate le risorse per Q# le operazioni che utilizzano migliaia di qubits, purché la parte classica del codice venga eseguita in un tempo ragionevole.

Lo strumento di stima delle risorse si basa su [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), che fornisce un set più completo di metriche e strumenti per facilitare il debug dei Q# programmi.

## <a name="invoking-and-running-the-resources-estimator"></a>Richiamo ed esecuzione dello strumento di stima delle risorse

Per eseguire qualsiasi operazione, è possibile usare lo strumento di stima delle risorse Q# . Per ulteriori informazioni, vedere [modalità di esecuzione di un Q# programma](xref:microsoft.quantum.guide.host-programs).

### <a name="invoking-the-resources-estimator-from-c"></a>Richiamo dello strumento di stima delle risorse da C # 

Come per altri computer di destinazione, creare prima un'istanza della classe `ResourceEstimator` e quindi passarla come primo parametro del metodo `Run` di un'operazione.

Si noti che, a differenza della classe `QuantumSimulator`, la classe `ResourceEstimator` non implementa l'interfaccia <xref:System.IDisposable>, per cui non è necessario racchiuderla in un'istruzione `using`.

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

Come illustrato nell'esempio, `ResourcesEstimator` fornisce il `ToTSV()` metodo, che genera una tabella con valori delimitati da tabulazioni (TSV). È possibile salvare la tabella in un file o visualizzarla nella console per l'analisi. Di seguito è riportato un esempio di output del programma precedente:

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
> Un' `ResourcesEstimator` istanza non reimposta i calcoli a ogni esecuzione. Se si utilizza la stessa istanza per eseguire un'altra operazione, vengono aggregati i nuovi risultati con i risultati esistenti. Se è necessario reimpostare i calcoli tra le esecuzioni, creare una nuova istanza per ogni esecuzione.

### <a name="invoking-the-resources-estimator-from-python"></a>Richiamo dello strumento di stima delle risorse da Python

Usare il metodo [estimate_resources ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) dalla libreria Python con l'operazione importata Q# :

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a>Richiamo dell'estimatore di risorse dalla riga di comando

Quando si esegue un Q# programma dalla riga di comando, usare il parametro **--Simulator** (o **-s** Shortcut) per specificare il `ResourcesEstimator` computer di destinazione. Il comando che segue esegue un programma usando lo strumento di stima delle risorse: 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a>Richiamo dello strumento di stima delle risorse da notebook Juptyer

Usare il Q# comando i Magic [% Estimate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) per eseguire l' Q# operazione.

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a>Recupero dei dati stimati a livello di codice

Oltre a una tabella TSV, è possibile recuperare a livello di codice le risorse stimate durante l'esecuzione tramite la `Data` proprietà dello strumento di stima delle risorse. La `Data` proprietà fornisce un' `System.DataTable` istanza con due colonne: `Metric` e `Sum` indicizzate in base ai nomi delle metriche.

Nel codice seguente viene illustrato come recuperare e stampare il numero totale di `QubitClifford` `T` operazioni e `CNOT` utilizzate da un' Q# operazione:

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

Lo strumento di stima delle risorse tiene traccia delle metriche seguenti:

|Metrica|Descrizione|
|----|----|
|__CNOT__    |Il numero di esecuzioni delle `CNOT` operazioni, note anche come operazioni di Pauli X controllate.|
|__QubitClifford__ |Numero di esecuzioni di ogni singola operazione qubit Clifford e Pauli.|
|__Misura__    |Numero di esecuzioni di qualsiasi misura.  |
|__R__    |Il numero di esecuzioni di tutte le rotazioni a qubit singola, escluse le `T` operazioni Clifford e Pauli.  |
|__T__    |Il numero di esecuzioni delle `T` operazioni e dei rispettivi coniugi, incluse le `T` operazioni, T_x = h. t. h e T_y = HY. t. HY.  |
|__Depth__|Limite inferiore per la profondità del circuito Quantum eseguito dall' Q# operazione. Per impostazione predefinita, la metrica di profondità conta solo i `T` cancelli. Per informazioni dettagliate, vedere [contatore di profondità](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).   |
|__Larghezza__    |Limite inferiore per il numero massimo di qubits allocati durante l'esecuzione dell' Q# operazione. Potrebbe non essere possibile ottenere contemporaneamente i limiti inferiori di __profondità__ e __larghezza__ .  |
|__BorrowedWidth__    |Numero massimo di qubits presi in prestito all'interno dell' Q# operazione.  |

## <a name="providing-the-probability-of-measurement-outcomes"></a>Come fornire la probabilità dei risultati di misurazione

È possibile utilizzare <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> dallo <xref:microsoft.quantum.diagnostics> spazio dei nomi per fornire informazioni sulla probabilità prevista di un'operazione di misurazione. Per altre informazioni, vedere [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)

## <a name="see-also"></a>Vedere anche

- [Simulatore di traccia Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [Simulatore di Toffoli](xref:microsoft.quantum.machines.toffoli-simulator)
- [Simulatore di stato completo](xref:microsoft.quantum.machines.full-state-simulator) 