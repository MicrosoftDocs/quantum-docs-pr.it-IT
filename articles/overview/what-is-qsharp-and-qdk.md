---
title: Informazioni sul linguaggio di programmazione Q# e su QDK
description: Informazioni sul kit di sviluppo Microsoft Quantum, il linguaggio di programmazione Q# e su come creare programmi quantistici.
author: bradben
ms.author: bradben
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.q-sharp
no-loc:
- Q#
- $$v
ms.openlocfilehash: 3ee9e897eb142bbc9503a617cc3e25c1a665ff35
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87866945"
---
# <a name="what-are-the-no-locq-programming-language-and-qdk"></a>Informazioni sul linguaggio di programmazione Q# e su QDK

Q# è il linguaggio di programmazione open source di Microsoft per lo sviluppo e l'esecuzione di algoritmi quantistici. Fa parte del kit di sviluppo Microsoft Quantum (QDK), che include [ librerie Q#](xref:microsoft.quantum.libraries), [simulatori quantistici](xref:microsoft.quantum.machines), [estensioni per altri ambienti di programmazione](xref:microsoft.quantum.install) e [documentazione dell'API](xref:microsoft.quantum.standardlibsintro). Oltre alla libreria Q# standard, il QDK include le librerie di chimica, apprendimento automatico e numeriche.

Come linguaggio di programmazione, Q# trae elementi noti da Python, C# ed F# e supporta un modello procedurale di base per la scrittura di programmi con cicli, istruzioni if/then e tipi di dati comuni. Introduce anche nuove strutture di dati e operazioni specifiche del calcolo quantistico.

## <a name="what-can-i-do-with-the-qdk"></a>Che cosa si può fare con il QDK?

QDK è un kit di sviluppo completo per Q# che è possibile usare con gli strumenti e i linguaggi comuni per sviluppare applicazioni quantistiche che si possono eseguire in vari ambienti. I programmi Q# possono essere eseguiti come un'app da riga di comando, tramite Jupyter Notebook o un programma host Python o .NET.

### <a name="develop-in-common-tools-and-environments"></a>Sviluppare in strumenti e ambienti comuni

Integrare lo sviluppo quantistico con [Visual Studio, Visual Studio Code](xref:microsoft.quantum.install.standalone) e [Jupyter Notebook](xref:microsoft.quantum.install.jupyter). Usare le API predefinite per associare i programmi ai linguaggi host [Python](xref:microsoft.quantum.install.python) e [.NET](xref:microsoft.quantum.install.cs).

### <a name="try-quantum-operations-and-domain-specific-libraries"></a>Provare le operazioni quantistiche e le librerie specifiche del dominio

Scrivere e testare algoritmi quantistici per esplorare la sovrapposizione, l'entanglement e altre operazioni quantistiche. Le librerie Q# consentono di eseguire operazioni quantistiche complesse senza dover progettare sequenze di operazioni di basso livello.

### <a name="run-programs-in-simulators"></a>Eseguire i programmi nei simulatori

Eseguire i programmi quantistici in un simulatore quantistico di stato completo, un simulatore di Toffoli con ambito limitato o testare il codice Q# in strumenti di stima delle risorse diversi. 

## <a name="where-can-i-learn-more"></a>Altre informazioni

|||
| ---- | ---- |
| **Non ho familiarità con il calcolo quantistico** | Esaminare alcune nozioni di base sulla fisica quantistica e il calcolo quantistico nei [Concetti principali](xref:microsoft.quantum.overview.understanding).|
| **Desidero approfondire il linguaggio Q#** | Esplorare i tipi, le espressioni, le variabili e la struttura dei programmi quantistici nel [Manuale dell'utente di Q#](xref:microsoft.quantum.guide).|
| **Desidero solo iniziare a scrivere programmi quantistici** | Configurare l'ambiente Q# e iniziare a scrivere programmi quantistici seguendo le [Guide di avvio rapido](xref:microsoft.quantum.install).|

## <a name="how-does-no-locq-work"></a>Come funziona Q#?

Un programma Q# può essere compilato in un'applicazione della riga di comando autonoma o essere chiamato da un programma host scritto in Python o in un linguaggio .NET.

Quando si compila ed esegue il programma, viene creata un'istanza del simulatore quantistico a cui viene passato il codice Q#. Il simulatore usa il codice Q# per creare i qubit (simulazioni di particelle quantistiche) e applicare le trasformazioni per modificarne lo stato. I risultati delle operazioni quantistiche nel simulatore vengono quindi restituiti al programma.  

L'isolamento del codice Q# nel simulatore garantisce che gli algoritmi seguano le leggi della fisica quantistica e possano essere eseguiti correttamente nei computer quantistici.

![qsharp-code-flow](~/media/qsharp-code-flow.png)

## <a name="how-do-i-use-the-qdk"></a>Come si usa il QDK?

Tutto ciò che serve per scrivere ed eseguire programmi Q#, ad esempio il compilatore Q#, le librerie Q# e i simulatori quantistici, può essere installato ed eseguito dal computer locale. In futuro sarà anche possibile eseguire i programmi Q# in modalità remota in un computer quantistico effettivo, ma fino a quel momento i simulatori quantistici forniti con QDK garantiscono risultati accurati e affidabili.

- L'esecuzione di [Q# dalla riga di comando](xref:microsoft.quantum.install.standalone) rappresenta il modo più rapido per iniziare.

- È anche possibile eseguire [Jupyter Notebook con IQ#](xref:microsoft.quantum.install.jupyter), un'estensione autonoma di Jupyter per la compilazione, la simulazione e la visualizzazione di programmi Q#.

- Se si ha familiarità con [Python](xref:microsoft.quantum.install.python), è possibile usarlo come piattaforma di programmazione host per iniziare. Python è ampiamente usato non solo tra gli sviluppatori, ma anche tra gli scienziati, i ricercatori e i docenti.

- Se si ha già esperienza con [C#, F# o VB.NET](xref:microsoft.quantum.install.cs) e si ha familiarità con l'ambiente di sviluppo di Visual Studio, è necessario aggiungere solo alcune estensioni di Visual Studio per prepararlo per Q#.  

## <a name="summary"></a>Summary

Q# è un linguaggio di programmazione open source per lo sviluppo di programmi quantistici. Fornisce librerie che consentono di creare operazioni quantistiche complesse e simulatori quantistici per eseguire e testare accuratamente i programmi. I programmi Q# possono essere eseguiti come app autonome o essere chiamati da un programma host Python o .NET e possono essere scritti, eseguiti e testati nel computer locale.

## <a name="next-steps"></a>Passaggi successivi

[Algebra lineare per il calcolo quantistico](xref:microsoft.quantum.overview.algebra)
