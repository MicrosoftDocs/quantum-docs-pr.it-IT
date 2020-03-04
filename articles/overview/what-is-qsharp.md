---
title: Che cosa sono Q# e il QDK?
description: Informazioni su Q#, un linguaggio di programmazione creato da Microsoft per lo sviluppo di applicazioni per computer quantistici e componente principale del Quantum Development Kit di Microsoft
author: natke
ms.author: nakersha
ms.date: 10/22/2019
ms.topic: article
uid: microsoft.quantum.overview.qsharp
ms.openlocfilehash: a4bf21887e34ac85f75e5e0b9a033138464fd09d
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907002"
---
# <a name="what-are-q-and-the-qdk"></a>Che cosa sono Q# e il QDK?

Q # è un linguaggio di programmazione con funzionalità appositamente progettate per il calcolo quantistico.
In quanto componente principale del Quantum Development Kit di Microsoft, Q# offre ai programmatori quantistici un framework che consente loro di concentrarsi sugli algoritmi senza doversi preoccupare dei dettagli tecnici, come l'ottimizzazione della sequenza di gate o l'implementazione fisica di un computer quantistico.

Il QDK è costituito da un'ampia gamma di strumenti che offrono agli sviluppatori tutto ciò che serve per iniziare a scrivere programmi quantistici.
Oltre al linguaggio Q#, QDK include:
* Le *librerie Q#* , che consentono agli sviluppatori di iniziare immediatamente a creare applicazioni quantistiche del mondo reale oggi stesso
* Vari *computer di destinazione* in cui è possibile eseguire i programmi Q#. Questi includono estimatori e simulatori di risorse per programmi quantistici di dimensioni elevate, nonché un simulatore quantistico con stato completo, che si comporta come un computer quantistico senza rumore. Quest'ultimo è molto utile per ritoccare le idee, eseguire il debug di programmi e apprendere i concetti di fisica quantistica, ma risulta efficiente solo per i programmi con un numero ridotto di qubit. Ci auguriamo che in futuro l'hardware per il calcolo quantistico sia disponibile come computer di destinazione.
* Gli *strumenti* per semplificare l'uso di Q#, ad esempio le estensioni per Visual Studio e VS Code e i pacchetti da usare con Python e Jupyter Notebook.
* *Documentazione dell'API* per l'associazione di Q# ai linguaggi host classici come Python e C#

Le applicazioni sviluppate con Quantum Development Kit di Microsoft sono in genere costituite da due parti:
1. Uno o più algoritmi quantistici, implementati usando il linguaggio di programmazione quantistico Q# e richiamati dal programma host classico. Sono costituiti da 
    - Operazioni Q#: subroutine contenenti operazioni quantistiche e 
    - Funzioni Q#: subroutine classiche usate nell'algoritmo quantistico.
2. Un programma classico, implementato in un linguaggio di programmazione come Python o C#, che funge da punto di ingresso principale e che richiamerà le operazioni Q# per eseguire un algoritmo quantistico.

## <a name="write-quantum-programs-not-quantum-circuits"></a>Scrivere programmi quantistici, non circuiti quantistici

Nelle fasi iniziali del calcolo quantistico gli algoritmi venivano visualizzati come diagrammi in modo analogo ai diagrammi di circuito nell'informatica classica.
Anche se il modello a circuiti è stato utile per molti anni nella ricerca del calcolo quantistico, in Microsoft si ritiene che gli sviluppatori debbano superare i circuiti quantistici e sviluppare applicazioni e algoritmi quantistici usando Q#.
Il linguaggio Q# è il frutto dell'esperienza maturata in decenni di sviluppo di software classico e offre agli sviluppatori quantistici funzionalità del linguaggio generali destinate al calcolo quantistico.

## <a name="how-does-q-work"></a>Come funziona il linguaggio Q#?

Il linguaggio di programmazione Q# offre un set intuitivo di tipi, operazioni ed espressioni logiche per sviluppare algoritmi senza doversi preoccupare della logica interna del computer quantistico.

Uno degli pilastri del linguaggio Q# è il tipo `Qubit`, che non prevede la copia o l'accesso diretto, proprio come un qubit.
È invece possibile misurarlo e archiviare il risultato della misurazione in una variabile `Result`, un tipo Q# che accetta due valori possibili, ovvero `Zero` e `One`.
Costrutti come questo garantiscono che gli algoritmi rispettino sempre le leggi della fisica quantistica e possono essere eseguiti correttamente in computer o simulatori quantistici.

Q# include anche funzionalità di logica classica, come cicli e istruzioni condizionali con alcune particolarità, per garantire il rispetto di tutte le regole quantistiche.
Ad esempio, è possibile vincolare la modalità di esecuzione dei cicli per garantire che le operazioni quantistiche non vengano chiamate all'interno di funzioni che possono contenere solo subroutine classiche deterministiche.

I programmi Q# sono spesso abbinati a un programma host scritto in C# o Python, che costituisce una soluzione pratica per organizzare codice classico e codice quantistico.
Oltre a supportare linguaggi come C# e Python, il QDK include il supporto per Jupyter Notebook con il kernel Jupyter IQ#.

## <a name="what-can-i-use-q-for"></a>A che cosa serve Q#?

### <a name="use-q-to-learn-quantum-computing"></a>Usare Q# per apprendere il calcolo quantistico

Fino ad ora, per apprendere il calcolo quantistico necessario era necessario imparare a usare il modello a circuiti per comprendere gli algoritmi sotto forma di sequenze ordinate di gate e misurazioni quantistiche. Con Q# è possibile intraprendere un'altra via: apprendere il calcolo quantistico scrivendo programmi quantistici.

### <a name="use-q-to-design-quantum-algorithms"></a>Usare Q# per progettare algoritmi quantistici

Q# include un numero sempre maggiore di librerie e tipi definiti dall'utente che consentono di implementare strumenti e creare algoritmi quantistici avanzati. Ad esempio, se è necessario eseguire l'entanglement di due qubit Q1 e Q2, è possibile usare l'operazione predefinita `PrepareEntangledState([q1], [q2])` invece di applicare singolarmente i gate necessari per l'entanglement dei qubit.

### <a name="use-q-to-estimate-quantum-resources"></a>Usare Q# per stimare le risorse quantistiche

È possibile simulare l'esecuzione del programma Q# usando il simulatore quantistico dello stato completo fornito con Quantum Development Kit (QDK).  Il QDK include anche strumenti di stima delle risorse che forniscono informazioni dettagliate sulle prestazioni dei programmi Q# troppo grandi per essere eseguiti in un simulatore.  Si tratta di strumenti estremamente preziosi per i progettisti di algoritmi, che possono così ottimizzare i propri programmi in modo da usare un minor numero di risorse (ad esempio, un minor numero di qubit in esecuzione per un minor numero di operazioni), da eseguire su hardware quantistico meno recente su scala ridotta.

### <a name="use-q-to-validate-hardware-performance"></a>Usare Q# per convalidare le prestazioni dell'hardware

Il vantaggio offerto da Q# sta nel fatto che un programma può essere scritto una sola volta ed essere eseguito in simulatori quantistici per il debug e in computer quantistici diversi.  È possibile eseguire programmi di benchmark scritti in Q# per convalidare le prestazioni hardware e confrontare i risultati man mano che i computer quantistici si evolvono e nuovi computer quantistici diventano disponibili.  

## <a name="next-steps"></a>Passaggi successivi

* [In che modo è possibile ottenere informazioni sul calcolo quantistico?](xref:microsoft.quantum.overview.learn)
* [Introduzione a Microsoft Quantum Development Kit](xref:microsoft.quantum.welcome)
