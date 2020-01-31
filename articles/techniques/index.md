---
title: Tecniche di sviluppo quantistico | Microsoft Docs
description: Tecniche di sviluppo quantistico
keywords: Non aggiungere o modificare parole chiave senza consultare l'esperto SEO.
author: QuantumWriter
ms.author: MSFT-alias-person-or-DL
ms.date: 9/20/2019
ms.topic: article-type-from-white-list
uid: microsoft.quantum.techniques.intro
ms.openlocfilehash: c1263edb75f903702ab3c16cec0443857150b662
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820811"
---
# <a name="quantum-development-techniques"></a>Tecniche di sviluppo quantistico

Questa sezione della documentazione illustra in dettaglio i concetti di base usati per creare programmi quantistici in Q# e per interagire con tali programmi da applicazioni classiche.
Si presuppone una *conoscenza di base* dei concetti di calcolo quantistico, come quelli descritti in [Concetti di calcolo quantistico](xref:microsoft.quantum.concepts.intro), ma non è necessario essere un esperto di calcolo quantistico per affrontare il contenuto di queste sezioni.

Contenuto delle sezioni.

- [Panoramica del programma Q#](xref:microsoft.quantum.techniques.file-structure) fornisce una panoramica dello scopo e delle funzionalità del linguaggio di programmazione Q#. 
    In particolare, chiarisce il motivo per cui Q# *non* è un linguaggio per la mera simulazione della meccanica quantistica, anche se tale funzionalità è naturalmente fornita dal simulatore di stato completo. 
    Piuttosto, Q# è stato progettato con un occhio al futuro e i relativi programmi descrivono come un computer di controllo classico *interagisce* con i qubit. 

- [Operazioni e funzioni](xref:microsoft.quantum.techniques.opsandfunctions) fornisce informazioni dettagliate sui due tipi chiamabili del linguaggio Q#: le *operazioni*, che includono l'azione sui qubit e sui sistemi quantistici e le *funzioni*, che operano esclusivamente con le informazioni classiche. 
    Se le informazioni classiche e quantistiche non operassero in tandem, il calcolo quantistico sarebbe fuori portata. 
    Questa sezione descrive come definire e usare i tipi chiamabili all'interno del flusso di controllo di un programma Q#.

- [Variabili locali](xref:microsoft.quantum.techniques.local-variables) descrive il ruolo delle variabili nei programmi Q# e come sfruttarle in modo efficace. 
    In particolare, si osserverà la differenza tra le variabili non modificabili/modificabili e verrà illustrato come assegnarle/riassegnarle.

- [Uso dei qubit](xref:microsoft.quantum.techniques.qubits) descrive le funzionalità di Q# che è possibile usare per risolvere singoli qubit e sistemi di qubit, 
    in particolare, come allocarli, eseguire operazioni su di essi e infine, come misurarli. 
    Si apprenderanno inoltre alcune tecniche utili per il flusso di controllo.

- In [Riepilogo generale](xref:microsoft.quantum.techniques.puttingittogether) verranno usate le tecniche descritte nelle sezioni precedenti per creare un programma che esegue il **teletrasporto quantistico** che prevede l'uso di due bit classici per "teletrasportare" lo stato completo di un qubit su un altro.

- In [Tecniche avanzate](xref:microsoft.quantum.techniques.going-further) vengono illustrate tecniche avanzate che possono risultare utili quando si passa alla programmazione quantistica più complessa. 
    Nello specifico, verrà descritto l'uso di operazioni e funzioni *con parametri del tipo* in Q#, che abilitano il flusso di controllo di ordine superiore indipendentemente dai tipi specifici di input/output, nonché il *prestito* di qubit. 
    Quest'ultima operazione è diversa dall'allocazione di base di qubit in quanto un'operazione Q# può usare qubit "dirty", ovvero qubit non necessariamente inizializzati a uno stato noto, per facilitare i calcoli.

- [Testing e debug](xref:microsoft.quantum.techniques.testing-and-debugging) fornisce informazioni dettagliate su alcune tecniche per assicurarsi che il codice esegua le operazioni previste. 
    A causa dell'opacità generale delle informazioni sul calcolo quantistico, il debug di un programma quantistico può richiedere tecniche specializzate. 
    Fortunatamente, Q# supporta molte delle tecniche di debug classiche normalmente usate dai programmatori, oltre a quelle specifiche del calcolo quantistico. Ad esempio, la creazione/esecuzione di unit test in Q#, l'incorporamento di *asserzioni* su valori e probabilità nel codice e le funzioni `Dump` che restituiscono lo stato del computer di destinazione. 
    Quest'ultima tecnica può essere usata insieme al simulatore di stato completo per eseguire il debug di determinate parti dei calcoli aggirando alcuni limiti del calcolo quantistico, ad esempio il teorema di no-cloning.


![Calcolo quantistico](~/media/mobius_strip_preview.png)
