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
ms.openlocfilehash: de425c2d91c6528b13c3bedd81acb4b4273ed711
ms.sourcegitcommit: 7c687495a79d75ae9e029e5a41baec84d9e07bb0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2020
ms.locfileid: "96604644"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a>Strumento di stima risorse di Quantum Development Kit (QDK)

Come suggerisce il nome, la `ResourcesEstimator` classe stima le risorse necessarie per eseguire una determinata istanza di un' Q# operazione in un computer Quantum. Questo consente di eseguire l'operazione Quantum senza simulare effettivamente lo stato di un computer Quantum; per questo motivo, vengono stimate le risorse per Q# le operazioni che utilizzano migliaia di qubits, purché la parte classica del codice venga eseguita in un tempo ragionevole.

Lo strumento di stima delle risorse si basa su [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), che fornisce un set più completo di metriche e strumenti per facilitare il debug dei Q# programmi.

## <a name="invoking-and-running-the-resources-estimator"></a>Richiamo ed esecuzione dello strumento di stima delle risorse

Per eseguire qualsiasi operazione, è possibile usare lo strumento di stima delle risorse Q# . Per ulteriori informazioni, vedere [modalità di esecuzione di un Q# programma](xref:microsoft.quantum.guide.host-programs).

### <a name="invoking-the-resources-estimator-from-c"></a>Richiamo dello strumento di stima delle risorse da C # 

Come per altri computer di destinazione, creare prima un'istanza della classe `ResourcesEstimator` e quindi passarla come primo parametro del metodo `Run` di un'operazione.

Si noti che, a differenza della classe `QuantumSimulator`, la classe `ResourcesEstimator` non implementa l'interfaccia <xref:System.IDisposable>, per cui non è necessario racchiuderla in un'istruzione `using`.

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
|__Measure__    |Numero di esecuzioni di qualsiasi misura.  |
|__R__    |Il numero di esecuzioni di tutte le rotazioni a qubit singola, escluse le `T` operazioni Clifford e Pauli.  |
|__T__    |Il numero di esecuzioni delle `T` operazioni e dei rispettivi coniugi, incluse le `T` operazioni, T_x = h. t. h e T_y = HY. t. HY.  |
|__Livello nidificazione__|Profondità del circuito Quantum eseguito dall' Q# operazione (vedere di [seguito](#depth-width-and-qubitcount)). Per impostazione predefinita, la metrica di profondità conta solo i `T` cancelli. Per informazioni dettagliate, vedere [contatore di profondità](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).   |
|__Larghezza__|Larghezza del circuito Quantum eseguito dall' Q# operazione (vedere di [seguito](#depth-width-and-qubitcount)). Per impostazione predefinita, la metrica di profondità conta solo i `T` cancelli. Per altri dettagli, vedere [contatore della larghezza](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter).   |
|__QubitCount__    |Limite inferiore per il numero massimo di qubits allocati durante l'esecuzione dell' Q# operazione. Questa metrica potrebbe non essere compatibile con la __profondità__ (vedere di seguito).  |
|__BorrowedWidth__    |Numero massimo di qubits presi in prestito all'interno dell' Q# operazione.  |


## <a name="depth-width-and-qubitcount"></a>Depth, Width e QubitCount

Le stime di profondità e larghezza segnalate sono compatibili tra loro.
(In precedenza entrambi i numeri erano raggiungibili, ma sarebbero necessari circuiti diversi per la profondità e la larghezza). Attualmente entrambe le metriche in questa coppia possono essere realizzate dallo stesso circuito nello stesso momento.

Vengono restituite le metriche seguenti:

__Profondità:__ Per l'operazione radice: tempo necessario per eseguirlo presumendo tempi di controllo specifici.
Per le operazioni denominate o per le operazioni successive, differenza oraria tra il tempo di disponibilità qubit più recente all'inizio e la fine dell'operazione.

__Larghezza:__ Per l'operazione radice, il numero di qubits effettivamente usato per eseguirlo (e l'operazione che chiama).
Per operazioni denominate o operazioni successive: quante più qubits sono state usate oltre al qubits già usato all'inizio dell'operazione.

Si noti che la qubits riutilizzata non contribuisce a questo numero.
Se, ad esempio, alcuni qubits sono stati rilasciati prima dell'avvio dell'operazione e tutti i qubit richiesti da questa operazione (e le operazioni chiamate da A) sono stati soddisfatti riutilizzando la versione precedente qubits, la larghezza dell'operazione A viene segnalata come 0. I qubits presi in prestito non contribuiscono alla larghezza.

__QubitCount:__ Per l'operazione radice: numero minimo di qubits che sarebbe sufficiente per eseguire l'operazione (e le operazioni chiamate da esso).
Per le operazioni chiamate o operazioni successive: numero minimo di qubits che sarebbe sufficiente per eseguire questa operazione separatamente. Questo numero non include qubits di input. Include qubits presi in prestito.

Sono supportate due modalità operative. Per selezionare la modalità, impostare QCTraceSimulatorConfiguration. OptimizeDepth.

__OptimizeDepth = true:__ QubitManager è sconsigliato dal riutilizzo di qubit e alloca nuovi qubit ogni volta che viene richiesto un qubit. Per la __profondità__ dell'operazione radice diventa la profondità minima (limite inferiore). Per questa profondità viene segnalata la __larghezza__ compatibile, che è possibile ottenere contemporaneamente. Si noti che questa larghezza sarà probabilmente non ottimale in base a questa profondità. __QubitCount__ può essere inferiore alla larghezza per l'operazione radice perché presuppone il riutilizzo.

__OptimizeDepth = false:__ QubitManager è consigliato per il riutilizzo di qubits e riutilizzerà il qubits rilasciato prima di allocarne di nuovi. Per la __larghezza__ dell'operazione radice diventa la larghezza minima (limite inferiore). Viene segnalato un livello di __profondità__ compatibile su cui è possibile ottenerlo. __QubitCount__ sarà uguale a __Width__ per l'operazione radice presumendo che non si prenda in prestito.

## <a name="providing-the-probability-of-measurement-outcomes"></a>Come fornire la probabilità dei risultati di misurazione

È possibile utilizzare <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> dallo <xref:Microsoft.Quantum.Diagnostics> spazio dei nomi per fornire informazioni sulla probabilità prevista di un'operazione di misurazione. Per altre informazioni, vedere [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)

## <a name="see-also"></a>Vedere anche

- [Simulatore di traccia Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [Simulatore di Toffoli](xref:microsoft.quantum.machines.toffoli-simulator)
- [Simulatore di stato completo](xref:microsoft.quantum.machines.full-state-simulator) 
