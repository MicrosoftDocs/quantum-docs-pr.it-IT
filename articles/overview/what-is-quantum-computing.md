---
title: Che cos'è il calcolo quantistico?
description: Informazioni sul calcolo quantistico e sulle operazioni eseguibili con un computer quantistico
author: natke
ms.author: nakersha
ms.date: 10/22/2019
ms.topic: article
uid: microsoft.quantum.overview.what
ms.openlocfilehash: 2f3b64b00a0a9552e52e34cb1e3652810b266eab
ms.sourcegitcommit: edcf15044d7bdf4f8b21fb8f6af4bde475eb13a0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73529937"
---
# <a name="what-is-quantum-computing"></a>Che cos'è il calcolo quantistico?

Alcuni problemi sono talmente complessi e di un tale impatto che, anche se ogni supercomputer al mondo lavorasse su un problema, il tempo necessario per risolverlo supererebbe comunque la durata dell'universo.

I computer quantistici promettono di risolvere alcune delle principali sfide del pianeta in termini di ambiente, agricoltura, salute, energia, clima, scienza dei materiali e problemi ancora inimmaginabili. L'impatto dei computer quantistici sarà di vasta portata e avrà un impatto paragonabile a quello della creazione del transistor nel 1947, che ha spianato la strada alla moderna economia digitale.

Il calcolo quantistico sfrutta lo speciale comportamento della fisica quantistica per offrire un modello di calcolo nuovo e potente. La teoria della fisica quantistica postula che la materia, a livello quantistico, può trovarsi in una sovrapposizione di più stati classici. E questi numerosi stati interferiscono l'uno con l'altro come onde in una pozza di marea.  Lo stato della materia dopo una misura "collassa" in uno degli stati classici. 

Successivamente, la ripetizione della stessa misura genererà lo stesso risultato classico.  L'entanglement quantistico si verifica quando le particelle interagiscono in modo tale che lo stato quantistico di ognuna non può essere descritto indipendentemente dalle altre, anche se le particelle sono fisicamente distanti.  

Il calcolo quantistico archivia le informazioni negli stati quantistici della materia e usa la relativa natura quantistica della sovrapposizione e dell'entanglement per eseguire operazioni quantistiche che vengono calcolate in base a tali informazioni, sfruttando l'interferenza quantistica e imparando a programmarla.

Il calcolo quantistico può sembrare un'impresa ardua, ma con le risorse appropriate è possibile iniziare a creare applicazioni quantistiche oggi stesso.

## <a name="the-qubit"></a>Qubit

Il calcolo quantistico definisce i concetti di calcolo che riflettono il comportamento quantistico.  Il calcolo quantistico inizia con la nozione di qubit.  Nel calcolo quantistico il **qubit** (forma contratta di quantum bit) è unità di informazione quantistica, simile a un bit classico. Mentre i bit classici contengono un singolo valore binario come 0 o 1, lo stato di un qubit può essere una **sovrapposizione** di 0 e 1 contemporaneamente.  

L'azione di misura di un qubit modifica lo stato di un qubit. Con la misura, il qubit passa dall'essere in sovrapposizione a uno degli stati classici.  

Più qubit possono inoltre essere **correlati** (in entanglement). Quando si esegue la misurazione di un qubit con entanglement, vengono aggiornate anche le informazioni sullo stato degli altri qubit.

## <a name="quantum-algorithms"></a>Algoritmi quantistici

Gli algoritmi quantistici sono progettati per usufruire dei vantaggi offerti dalla natura e dal comportamento quantistici per accelerare gli algoritmi classici o per offrire modalità completamente nuove per la modellazione di sistemi fisici.  Questi algoritmi sfruttano il modo in cui i qubit codificano le informazioni e la natura parallela di operare su più qubit correlati in sovrapposizione.  

I computer classici codificano le informazioni in bit, dove ogni bit codifica 0 possibili valori, 0 o 1.  Un qubit codifica contemporaneamente due valori, 0 e 1.  Due bit classici codificano uno di 4 valori possibili, ovvero 00, 01, 10, 11, mentre due qubit codificano contemporaneamente qualsiasi sovrapposizione di questi 4 stati, anche se si può ottenere uno solo di questi valori durante la misura. Quattro qubit codificano contemporaneamente ogni sovrapposizione di 16 valori e così via, in modo esponenziale.  100 qubit possono codificare più informazioni rispetto a quelle attualmente disponibili nei sistemi informatici più potenti al mondo.  

Inoltre, quando più qubit correlati agiscono in modo coerente, possono elaborare più opzioni contemporaneamente. I qubit correlati possono elaborare le informazioni in una frazione del tempo che impiegherebbero persino i sistemi non quantistici più veloci.

La ricerca sugli algoritmi quantistici degli ultimi decenni si è concentrata sul modo in cui sfruttare questi attributi quantistici e sono state trovate numerose tecniche innovative che consentono di risolvere i problemi in una frazione del tempo necessario con la modalità classica.  

Uno degli algoritmi quantistici più famosi è l'_algoritmo di Shor_ per la fattorizzazione, grazie al quale la risoluzione del problema notoriamente intrattabile della fattorizzazione di un numero grande in due numeri primi diventa talmente rapida da sfidare la crittografia tradizionale.

Dal punto di vista più costruttivo, gli algoritmi per la distribuzione sicura delle chiavi crittografiche sono resi possibili dalla sovrapposizione, dall'entanglement quantistico e dalla proprietà di **non clonazione** dei qubit, che impedisce la copia dei qubit senza rilevamento.

_L'algoritmo di Grover_ evidenzia una tecnica di algoritmo quantistico che fornisce un'accelerazione quadratica per la ricerca nei dati non strutturati.

## <a name="quantum-hardware"></a>Hardware quantistico

Nei computer classici i bit corrispondono ai livelli di tensione nei circuiti al silicio. L'hardware quantistico può essere implementato in diverse realizzazioni fisiche dei qubit: ioni intrappolati, superconduttori, atomi neutri, spin elettronico, polarizzazione della luce, qubit topologici. L'hardware quantistico è una tecnologia emergente, I qubit sono fragili per natura e diventano meno coerenti in quanto interagiscono con il proprio ambiente. È quindi necessario bilanciare la fedeltà del sistema con la scalabilità. Maggiore è la scala, ovvero il numero di qubit, più elevato sarà il tasso di errore.

Microsoft sta sviluppando un computer quantistico basato su qubit topologici. Si ritiene che un qubit topologico sarà meno interessato ai cambiamenti nel proprio ambiente, riducendo in tal modo il grado di correzione degli errori esterni. I qubit topologici sono caratterizzati da una maggiore stabilità e resistenza al rumore ambientale, il che significa che possono essere ridimensionati più facilmente e rimanere affidabili più a lungo.

## <a name="quantum-computing--a-full-hardware-and-software-stack"></a>Calcolo quantistico: stack hardware e software completo

Il programma quantistico di Microsoft è unico nel suo genere, in quanto si basa sulla scalabilità di ogni componente del sistema per garantire un impatto quantistico effettivo. Questo approccio completo prevede:

* la creazione di un computer quantistico tramite qubit topologici affidabili, scalabili e con tolleranza di errore, 
* la progettazione di un piano di controllo criogenico esclusivo con bassa potenza e dissipazione di calore, 
* lo sviluppo di uno stack software completo per consentire la programmazione del computer quantistico e il controllo del sistema su larga scala.

L'introduzione del Microsoft Quantum Development Kit (QDK) open source rende più accessibile la programmazione quantistica e lo sviluppo di algoritmi. Il linguaggio di programmazione generale, Q#, consente di risolvere le problematiche della programmazione quantistica.  Q# è stato progettato come linguaggio di programmazione generale incentrato sul calcolo quantistico mirato per lo sviluppo di algoritmi e applicazioni. Il compilatore Q# è integrato in uno stack software che permette di compilare un algoritmo quantistico fino alle operazioni primitive di un computer quantistico.  Fino a una certa scala (numero di qubit) è possibile simulare il calcolo quantistico in un computer classico. Grazie alla simulazione, è possibile iniziare a scrivere oggi programmi quantistici che verranno eseguiti in hardware quantistico domani.  Q# è inoltre abbinato a esempi, librerie ed esercizi di formazione per semplificare i primi passi nella programmazione quantistica. 

## <a name="next-steps"></a>Passaggi successivi

* [Cosa è possibile fare con i computer quantistici?](xref:microsoft.quantum.overview.computers)
* [Introduzione a Microsoft Quantum Development Kit](xref:microsoft.quantum.welcome)
* Altre informazioni sui [concetti del calcolo quantistico](xref:microsoft.quantum.concepts.intro)
