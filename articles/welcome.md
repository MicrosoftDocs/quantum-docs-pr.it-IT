---
uid: microsoft.quantum.welcome
title: Introduzione al Quantum Development Kit (QDK)
description: Informazioni su come iniziare a programmare progetti quantistici in Q# con Microsoft Quantum Development Kit (QDK).
author: natke
ms.author: nakersha
ms.date: 10/23/2019
ms.topic: overview
ms.openlocfilehash: cea39e47ec5e7e2ad97adbbb39ba586274564967
ms.sourcegitcommit: 7d350db4b5e766cd243633aee7d0a839b6274bd6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "77907631"
---
# <a name="get-started-with-the-quantum-development-kit-qdk"></a>Introduzione al Quantum Development Kit (QDK)

Benvenuti in Microsoft Quantum Development Kit.  
Il QDK contiene tutti gli strumenti necessari per creare programmi ed esperimenti quantistici con Q#, un linguaggio di programmazione progettato specificamente per lo sviluppo di applicazioni quantistiche. 

Per iniziare immediatamente, è possibile passare alla [Guida all'installazione di QDK](xref:microsoft.quantum.install).
Verrà quindi illustrato come installare Quantum Development Kit nei computer Windows, Linux o MacOS per lo sviluppo di programmi quantistici personalizzati.

Se non si è pronti per iniziare a scrivere codice, ma si desidera approfondire i concetti sul calcolo quantistico e su Q#, è consigliabile leggere comunque questo articolo per una panoramica generale delle risorse a propria disposizione. Nella sezione [cinque domande sul calcolo quantistico](#five-questions-about-quantum-computing) sono disponibili i collegamenti diretti a ciò che si sta cercando.

## <a name="get-started-programming"></a>Iniziare a programmare

Quantum Development Kit fornisce molti modi per imparare a sviluppare un programma quantistico con Q#.
Per muovere i primi passi nel calcolo quantistico, è possibile provare le guide di *avvio rapido*:

* Il [generatore quantistico di numeri casuali](xref:microsoft.quantum.quickstarts.qrng) è un'applicazione in stile "Hello World Q#", che offre una breve introduzione ai concetti del calcolo quantistico e che consente di compilare ed eseguire un'applicazione quantistica in pochi minuti.
* L'[Introduzione al calcolo quantistico con Q#](xref:microsoft.quantum.write-program) assiste l'utente durante la scrittura di un programma Q# che illustra alcuni dei concetti fondamentali della programmazione quantistica. 
    Se non si è pronti per iniziare a scrivere codice, è comunque possibile seguire l'esercitazione senza installare il QDK e ottenere una panoramica del linguaggio di programmazione Q# e dei concetti di base del calcolo quantistico.
* L'[algoritmo di ricerca di Grover](xref:microsoft.quantum.quickstarts.search) offre un esempio di programma Q# per ottenere un'idea della potenza di Q# per esprimere l'algoritmo quantistico in modo da estrapolare le operazioni quantistiche di basso livello. 
    La guida di avvio rapido assiste l'utente durante lo sviluppo del programma usando un'ampia gamma di ambienti di programmazione (con un host Python o con l'host del linguaggio .NET e con Visual Studio o Visual Studio Code).

### <a name="learning-further"></a>Ulteriori approfondimenti
* Per approfondire ulteriormente la programmazione in Q#, vedere la raccolta [Quantum Katas](https://github.com/Microsoft/QuantumKatas), una serie di esercizi di programmazione autogestiti che forniscono informazioni di base sul calcolo quantistico tramite esercizi di programmazione in Q#.
    Molti di questi kata sono disponibili anche come notebook Q#. 
* Il [repository degli esempi](https://github.com/Microsoft/Quantum) presenta numerosi esempi su come scrivere programmi quantistici usando Q#. La maggior parte di questi esempi è scritta con le [librerie per il calcolo quantistico](https://github.com/Microsoft/QuantumLibraries) open source, incluse le librerie [standard](xref:microsoft.quantum.libraries.standard.intro) e di [chimica](xref:microsoft.quantum.chemistry.concepts.intro) (per altre informazioni, vedere più avanti).

## <a name="five-questions-about-quantum-computing"></a>Cinque domande sul calcolo quantistico

Per coloro che non hanno familiarità con lo sviluppo quantistico, i primi approcci potrebbero risultare scoraggianti. Tuttavia, sono disponibili numerose risorse che consentono di iniziare ad apprendere i concetti di calcolo quantistico. E con l'aiuto di questi brevi articoli, sarà possibile iniziare a programmare in pochissimo tempo.
* [Che cos'è il calcolo quantistico?](xref:microsoft.quantum.overview.what)
* [Cosa è possibile fare con i computer quantistici?](xref:microsoft.quantum.overview.computers)
* [Perché apprendere il calcolo quantistico?](xref:microsoft.quantum.overview.why)
* [Che cos'è Q#?](xref:microsoft.quantum.overview.qsharp)
* [Come è possibile apprendere il calcolo quantistico con Q#?](xref:microsoft.quantum.overview.learn)

## <a name="quantum-development-kit-documentation"></a>Documentazione di Quantum Development Kit

La documentazione corrente include gli argomenti aggiuntivi seguenti.

### <a name="using-q"></a>Utilizzo di Q#
* [Tecniche di sviluppo quantistico](xref:microsoft.quantum.techniques.intro) specifica i concetti di base usati per creare programmi quantistici in Q#. Gli argomenti includono strutture di file, operazioni e funzioni, uso dei qubit e alcuni argomenti avanzati.
* [Riferimento al linguaggio Q#](xref:microsoft.quantum.language.intro) fornisce informazioni dettagliate sul linguaggio Q#, incluse le modalità di utilizzo del modello del tipo, delle espressioni, delle istruzioni e del compilatore.
* [Simulatori quantistici e applicazioni host](xref:microsoft.quantum.machines) descrive il modo in cui vengono eseguiti gli algoritmi quantistici, quali computer quantistici sono disponibili e come scrivere un driver non Q# per il programma quantistico.

### <a name="q-libraries"></a>Librerie Q#
* Le [librerie standard Q#](xref:microsoft.quantum.libraries.standard.intro) illustrano le operazioni e le funzioni che supportano sia il requisito di controllo del linguaggio classico che gli algoritmi quantistici Q#. 
    Gli argomenti includono il flusso di controllo, le strutture dei dati, la correzione degli errori, il test e il debug. 
* La [libreria di chimica Q#](xref:microsoft.quantum.chemistry.concepts.intro) descrive le operazioni e le funzioni che supportano la simulazione della chimica quantistica, un'applicazione critica del calcolo quantistico. Gli argomenti includono la simulazione della dinamica hamiltoniana e la stima delle fasi del calcolo quantistico, tra gli altri.
* La [libreria per il calcolo numerico Q#](xref:microsoft.quantum.numerics.intro) descrive le operazioni e le funzioni che supportano l'espressione di funzioni aritmetiche complesse in termini di operazioni native dei computer di destinazione.
* Il [riferimento alla libreria Q#](xref:microsoft.quantum.standardlibsintro) contiene informazioni di riferimento sulle entità di libreria per spazio dei nomi.

### <a name="general-quantum-computing"></a>Calcolo quantistico generale
* [Concetti di calcolo quantistico](xref:microsoft.quantum.concepts.intro) include argomenti come la pertinenza dell'algebra lineare rispetto al calcolo quantistico, la natura e l'uso di un qubit, come leggere un circuito quantistico e altro ancora.
* Il [Glossario del calcolo quantistico](xref:microsoft.quantum.glossary) è un glossario contenente alcuni termini cruciali specifici per il calcolo quantistico e lo sviluppo di programmi. 
    Se non si ha familiarità con l'argomento, costituisce un riferimento utile durante la lettura della documentazione.
* [Altre letture](xref:microsoft.quantum.more-information) contiene riferimenti selezionati appositamente per un ulteriore approfondimento degli argomenti relativi al calcolo quantistico.

### <a name="additional-info"></a>Informazioni aggiuntive
* [Note sulla versione del kit di sviluppo Microsoft Quantum](xref:microsoft.quantum.relnotes).


## <a name="be-a-part-of-the-q-open-source-community"></a>Partecipare alla community di Q# open source
Quantum Development Kit è un kit di sviluppo open source che consente agli sviluppatori di rendere il calcolo quantistico più accessibile a tutti, per risolvere alcune delle sfide più urgenti del mondo.  Gli istituti accademici che necessitano di software open source potranno distribuire Q# per l'apprendimento e lo sviluppo quantistico. Un kit di sviluppo open source permette inoltre agli sviluppatori e agli esperti di dominio di introdurre miglioramenti e idee tramite il proprio codice.

I feedback, la partecipazione e i contributi degli utenti a Quantum Development Kit sono molto importanti.  Per altre informazioni sulle fonti di Quantum Development Kit, inviare feedback e scoprire come partecipare alle decisioni e contribuire a questa piattaforma di sviluppo quantistico in continua evoluzione, vedere [Contribuire al Quantum Development Kit](xref:microsoft.quantum.contributing).

Per informazioni più generali sull'iniziativa di Microsoft per il calcolo quantistico, vedere [Microsoft Quantum](https://www.microsoft.com/en-us/quantum/).
