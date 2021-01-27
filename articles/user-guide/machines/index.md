---
title: Simulatori quantistici e programmi Q#
description: Informazioni sui simulatori quantistici disponibili come computer di destinazione per i programmi Q#.
author: QuantumWriter
ms.author: v-benbra
ms.date: 6/17/2020
ms.topic: conceptual
uid: microsoft.quantum.machines
no-loc:
- Q#
- $$v
ms.openlocfilehash: 408c636d5383cf594e7ebec6ab2edd66e20ffb82
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858777"
---
# <a name="quantum-simulators"></a>Simulatori quantistici

I simulatori quantistici sono programmi software eseguiti in computer classici che fungono da *computer di destinazione* per un programma Q#, rendendo possibile l'esecuzione e i test di programmi quantistici in un ambiente che consente di prevedere quale sarà la reazione dei qubit a diverse operazioni. Questo articolo descrive i simulatori quantistici inclusi nel kit di sviluppo Microsoft Quantum (QDK) e i diversi modi in cui è possibile passare un programma Q# a questi simulatori, ad esempio tramite la riga di comando o con un codice di driver scritto in un linguaggio classico.  



## <a name="the-quantum-development-kit-qdk-quantum-simulators"></a>Simulatori quantistici del Quantum Development Kit (QDK)

Il simulatore quantistico serve a fornire le implementazioni di primitive quantistiche per l'algoritmo. Sono incluse operazioni primitive come `H`, `CNOT` e `Measure`, oltre alla gestione e al monitoraggio di qubit. Il QDK include classi diverse di simulatori quantistici, che rappresentano diversi modi per simulare lo stesso algoritmo quantistico. 


Ogni tipo di simulatore quantistico può fornire implementazioni diverse di tali primitive. Ad esempio, il [simulatore di stato completo](xref:microsoft.quantum.machines.full-state-simulator) esegue l'algoritmo quantistico simulando completamente il [vettore di stato quantico](xref:microsoft.quantum.glossary#quantum-state), mentre il [simulatore di traccia del computer quantistico](xref:microsoft.quantum.machines.qc-trace-simulator.intro) non considera affatto lo stato quantico effettivo. Piuttosto, tiene traccia dell'utilizzo di gate, qubit e altre risorse per l'algoritmo.

### <a name="quantum-machine-classes"></a>Classi di computer quantistici

In futuro, il QDK definirà ulteriori classi di computer quantistici per supportare altri tipi di simulazione e l'esecuzione in hardware quantistico. Consentire all'algoritmo di rimanere costante e variando al contempo l'implementazione del computer sottostante semplifica il test e il debug di un algoritmo in simulazione, per poterlo eseguire nell'hardware reale con la certezza che l'algoritmo non è stato modificato.

Il QDK include diverse classi di computer quantistici, tutte definite nello spazio dei nomi `Microsoft.Quantum.Simulation.Simulators`.

|Simulatore |Classe|Descrizione|
|-----|------|---|
|[Simulatore di stato completo](xref:microsoft.quantum.machines.full-state-simulator)| `QuantumSimulator` | Esegue e sottopone a debug gli algoritmi e prevede un limite di circa 30 qubit. |
|[Strumento semplice di stima risorse](xref:microsoft.quantum.machines.resources-estimator)| `ResourcesEstimator` | Esegue un'analisi generale delle risorse necessarie per eseguire un algoritmo quantistico e supporta migliaia di qubit.|
|[Strumento di stima risorse basato su traccia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)|  `QCTraceSimulator` |Esegue un'analisi avanzata del consumo di risorse per l'intero grafico di chiamata dell'algoritmo e supporta migliaia di qubit.|
|[Simulatore di Toffoli](xref:microsoft.quantum.machines.toffoli-simulator)| `ToffoliSimulator` |Simula gli algoritmi quantistici limitati alle operazioni quantistiche `X`, `CNOT` e `X` multi-controllate e supporta milioni di qubit. |

## <a name="invoking-the-quantum-simulator"></a>Come richiamare il simulatore quantistico

L'articolo [Modalità di esecuzione di programmi Q#](xref:microsoft.quantum.guide.host-programs) illustra i tre modi disponibili per passare il codice Q# al simulatore quantistico: 

* Uso della riga di comando
* Uso di un programma host Python
* Uso di un programma host C#

I computer quantistici sono istanze di classi .NET normali, che vengono quindi create richiamandone il costruttore, come per qualsiasi altra classe .NET. Il modo in cui si procede dipende da come viene eseguito il programma Q#.

## <a name="next-steps"></a>Passaggi successivi

* Per informazioni dettagliate su come richiamare i computer di destinazione per programmi Q# in ambienti diversi, vedere [Modalità di esecuzione di programmi Q#](xref:microsoft.quantum.guide.host-programs).
