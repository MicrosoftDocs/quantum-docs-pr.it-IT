---
title: Che cos'è Q#?
description: Informazioni su Q#, un linguaggio di programmazione creato da Microsoft per lo sviluppo di applicazioni per computer quantistici
author: natke
ms.author: nakersha
ms.date: 10/22/2019
ms.topic: article
uid: microsoft.quantum.overview.qsharp
ms.openlocfilehash: e04228ff62092a15c529297bd56b9ee48399f4a5
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2019
ms.locfileid: "73443954"
---
# <a name="what-is-q"></a>Che cos'è Q#?

Q# è un linguaggio di programmazione con funzionalità specifiche per il calcolo quantistico. Q# offre ai programmatori quantistici un framework che consente loro di concentrarsi sugli algoritmi senza doversi preoccupare dei dettagli tecnici, come l'ottimizzazione della sequenza di gate o l'implementazione fisica di un computer quantistico.

Il linguaggio di programmazione Q# offre un set intuitivo di tipi, operazioni ed espressioni logiche per sviluppare algoritmi senza doversi preoccupare della logica interna del computer quantistico.

## <a name="code-algorithms"></a>Algoritmi di codice

Nelle fasi iniziali del calcolo quantistico gli algoritmi venivano visualizzati come diagrammi in modo analogo ai diagrammi di circuito nell'informatica classica.  Anche se il modello a circuiti sia stato molto utile per molti anni nella ricerca del calcolo quantistico, Microsoft si ritiene che gli sviluppatori debbano superare i circuiti quantistici e sviluppare algoritmi e applicazioni quantistiche usando Q#. Il linguaggio Q# è il frutto dell'esperienza maturata in decenni di sviluppo di software classico e offre agli sviluppatori quantistici funzioni del linguaggio di alto livello specificamente destinate al calcolo quantistico.


## <a name="how-does-q-work"></a>Come funziona il linguaggio Q#?

Uno degli pilastri del linguaggio Q# è il tipo `Qubit`, che non prevede la copia o l'accesso diretto, proprio come un qubit. È invece possibile misurarlo e archiviare il risultato della misurazione in una variabile `Result`, un tipo Q# che accetta due valori possibili, ovvero `Zero` e `One`. Costrutti come questo garantiscono che gli algoritmi rispettino sempre le leggi della fisica quantistica e possono essere eseguiti correttamente in computer o simulatori quantistici.

Q# include anche funzionalità di logica classica, come cicli o istruzioni condizionali con alcune particolarità, per garantire il rispetto di tutte le regole quantistiche. Le operazioni quantistiche devono, ad esempio, essere reversibili. Questa regola impone alcuni vincoli sulla modalità di esecuzione dei cicli.

I programmi Q# sono spesso abbinati a un programma host scritto in C# o Python, che costituisce una soluzione pratica per organizzare codice classico e codice quantistico. Oltre a supportare linguaggi .NET, come C# e Python, il QDK include il supporto per Jupyter Notebook con il kernel Jupyter IQ#.

## <a name="use-q-to-learn-quantum-computing"></a>Usare Q# per apprendere il calcolo quantistico

Fino ad ora, per apprendere il calcolo quantistico necessario era necessario imparare a usare il modello a circuiti per comprendere gli algoritmi sotto forma di sequenze ordinate di gate e misurazioni quantistiche. Con Q# è possibile intraprendere un'altra via: apprendere il calcolo quantistico scrivendo programmi quantistici.

## <a name="use-q-to-design-quantum-algorithms"></a>Usare Q# per progettare algoritmi quantistici

Q# include un numero sempre maggiore di librerie e tipi definiti dall'utente che consentono di implementare strumenti e creare algoritmi quantistici avanzati. Ad esempio, se è necessario eseguire l'entanglement di due qubit Q1 e Q2, è possibile usare l'operazione predefinita `PrepareEntangledState([q1], [q2])` invece di applicare singolarmente i gate necessari per l'entanglement dei qubit.

## <a name="use-q-to-estimate-quantum-resources"></a>Usare Q# per stimare le risorse quantistiche

È possibile simulare l'esecuzione del programma Q# usando il simulatore quantistico dello stato completo fornito con Quantum Development Kit (QDK).  Il QDK include anche strumenti di stima delle risorse che forniscono informazioni dettagliate sulle prestazioni dei programmi Q# troppo grandi per essere eseguiti in un simulatore.  Si tratta di strumenti estremamente preziosi per i progettisti di algoritmi, che possono così ottimizzare i propri programmi in modo da usare un minor numero di risorse (ad esempio, un minor numero di qubit in esecuzione per un minor numero di operazioni), da eseguire su hardware quantistico meno recente su scala ridotta.   

## <a name="use-q-to-validate-hardware-performance"></a>Usare Q# per convalidare le prestazioni dell'hardware

Il vantaggio offerto da Q# sta nel fatto che un programma può essere scritto una sola volta ed essere eseguito in simulatori quantistici per il debug e in più computer quantistici.  È possibile eseguire programmi di benchmark scritti in Q# per convalidare le prestazioni hardware e confrontare i risultati man mano che i computer quantistici si evolvono e nuovi computer quantistici diventano disponibili.  

## <a name="next-steps"></a>Passaggi successivi

* [Come è possibile apprendere il calcolo quantistico?](xref:microsoft.quantum.overview.learn)
* [Introduzione a Microsoft Quantum Development Kit](xref:microsoft.quantum.welcome)
