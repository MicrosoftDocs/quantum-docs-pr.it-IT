---
title: Manuale dell'utente di Q#
description: Panoramica dello scopo e del contenuto del Manuale dell'utente
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
ms.openlocfilehash: c5611f3e2907791f2dfc1644be0a45515d50dfd7
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415366"
---
# <a name="the-q-user-guide"></a>Manuale dell'utente di Q#

Benvenuti nel Manuale dell'utente di Q#. 

Nei vari argomenti di questa guida vengono illustrati in dettaglio i concetti di base del linguaggio Q# e vengono fornite tutte le informazioni necessarie per la scrittura di programmi quantistici.

## <a name="user-guide-contents"></a>Sommario del Manuale dell'utente

- [Nozioni di base su Q#](xref:microsoft.quantum.guide.basics): offre una panoramica introduttiva dello scopo e delle funzionalità del linguaggio di programmazione Q#. 

### <a name="q-language"></a>Linguaggio Q#

- [Tipi in Q#](xref:microsoft.quantum.guide.types): definisce il modello di tipo Q# e descrive la sintassi per specificare e usare i tipi.

- [Espressioni di tipo](xref:microsoft.quantum.guide.expressions): illustra in dettaglio come specificare, fare riferimento, combinare e operare su valori di ogni tipo in Q#. 

### <a name="using-q"></a>Utilizzo di Q#

- [Struttura dei file Q#](xref:microsoft.quantum.guide.filestructure): illustra la struttura e la sintassi di un file Q# con estensione `*.qs`.

- [Operazioni e funzioni](xref:microsoft.quantum.guide.operationsfunctions): illustra in dettaglio i due tipi chiamabili del linguaggio Q#, ovvero le *operazioni*, che includono l'azione sui registri qubit, e le *funzioni*, che operano esclusivamente con le informazioni classiche. 
    In questo articolo viene illustrato come definirli e chiamarli e vengono descritte le versioni controllata e contigua delle operazioni quantistiche.

- [Variabili](xref:microsoft.quantum.guide.variables): descrive il ruolo delle variabili nei programmi Q# e spiega come sfruttarle in modo efficace. 
    Include, ad esempio, informazioni sugli ambiti di associazione, nonché sulla differenza tra variabili modificabili e non modificabili e su come assegnarle o riassegnarle.

- [Uso dei qubit](xref:microsoft.quantum.guide.qubits): descrive le funzionalità di Q # usate per risolvere singoli qubit e sistemi di qubit, in particolare, come allocarli, eseguire operazioni su di essi e come misurarli. 

- [Flusso di controllo](xref:microsoft.quantum.guide.controlflow): descrive in dettaglio i modelli di flusso di controllo di programmazione disponibili in Q#, che include numerose tecniche standard (ad esempio esecuzione condizionale, cicli for, cicli while e così via), nonché il modello "ripetizione fino al completamento" specifico del calcolo quantistico.

- [Test e debug](xref:microsoft.quantum.guide.testingdebugging): illustra in dettaglio alcune tecniche per assicurarsi che il codice esegua le operazioni previste. 
    A causa dell'opacità generale delle informazioni sul calcolo quantistico, il debug di un programma quantistico può richiedere tecniche specializzate. 
    Fortunatamente, Q# supporta molte delle tecniche di debug classiche già note ai programmatori, oltre a quelle specifiche del calcolo quantistico. Ad esempio, la creazione ed esecuzione di unit test in Q#, l'incorporamento di *asserzioni* su valori e probabilità nel codice e le funzioni `Dump` che restituiscono gli stati dei computer di destinazione. 
    Quest'ultima tecnica può essere usata insieme al simulatore di stato completo per eseguire il debug di determinate parti dei calcoli aggirando alcuni limiti del calcolo quantistico, ad esempio il [teorema di no-cloning](xref:microsoft.quantum.concepts.pauli).

### <a name="quantum-simulators-and-resource-estimators"></a>Simulatori quantistici e strumenti di stima delle risorse

- [Simulatori quantistici e applicazioni host](xref:microsoft.quantum.machines): offre una panoramica dei diversi simulatori disponibili e illustra il modello di esecuzione generico tra i programmi host e i computer di destinazione.

- [Simulatore di stato completo](xref:microsoft.quantum.machines.full-state-simulator): computer di destinazione che simula lo stato quantistico completo. Utile per l'esecuzione completa o il debug di programmi di scala ridotta (meno di alcune decine di qubit).

- [Stima delle risorse](xref:microsoft.quantum.machines.resources-estimator): stima le risorse necessarie per eseguire un'istanza specifica di un'operazione Q# in un computer quantistico.

- [Simulatore di traccia](xref:microsoft.quantum.machines.qc-trace-simulator.intro): esegue un programma quantistico senza simulare effettivamente lo stato di un computer quantistico, di conseguenza può eseguire programmi quantistici che usano migliaia di qubit. Utile per il debug di codice classico in un programma quantistico, nonché per la stima delle risorse necessarie.

- [Simulatore di Toffoli](xref:microsoft.quantum.machines.toffoli-simulator): simulatore quantistico per scopi specifici che può essere usato con milioni di qubit, ma solo per i programmi con un set limitato di operazioni quantistiche, ovvero X, CNOT e X multi-controllate.

### <a name="quick-reference-pages"></a>Pagine di riferimento rapido

- [Comandi magic di IQ#](xref:microsoft.quantum.guide.quickref.iqsharp): Pagina di riferimento rapido per i comandi magic di IQ# in Jupyter Notebook Q#.
