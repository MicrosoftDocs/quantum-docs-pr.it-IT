---
title: Introduzione al calcolo quantistico
description: Informazioni sul calcolo quantistico, sulle operazioni eseguibili con i computer quantistici e su come apprendere il calcolo quantistico.
author: bradben
ms.author: bradben
ms.date: 05/05/2020
ms.topic: overview
uid: microsoft.quantum.overview.introduction
no-loc:
- Q#
- $$v
ms.openlocfilehash: 59cb595ac207d6e84358fc6ba742e0e0019c76f9
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87866979"
---
# <a name="introduction-to-quantum-computing-and-the-quantum-development-kit"></a>Introduzione al calcolo quantistico e al kit di sviluppo Microsoft Quantum

Il kit di sviluppo Microsoft Quantum (QDK) è un set di strumenti open source progettati per consentire agli sviluppatori di apprendere gli algoritmi quantistici e scrivere programmi quantistici. Il calcolo quantistico promette di risolvere alcune delle principali sfide del pianeta in termini di ambiente, agricoltura, salute, energia, clima, scienza dei materiali e problemi ancora non incontrati.  

Per alcuni di questi problemi, anche i computer più potenti al mondo possono riscontrare difficoltà. Sebbene la tecnologia quantistica abbia appena iniziato a influenzare il mondo informatico, è di vasta portata e potrebbe cambiare radicalmente il modo in cui si pensa all'informatica.

## <a name="what-is-quantum-computing"></a>Che cos'è il calcolo quantistico?

Nell'utilizzo moderno, il termine 'quanto' indica l'unità discreta più piccola possibile di qualsiasi proprietà fisica, che in genere fa riferimento a proprietà di particelle atomiche o subatomiche. I computer quantistici usano particelle quantistiche effettive, atomi artificiali o proprietà collettive di particelle quantistiche come unità di elaborazione e sono dispositivi di grandi dimensioni, complessi e costosi.

Sfruttando il comportamento specifico della fisica quantistica e applicandolo al calcolo, i computer quantistici introducono nuovi concetti nei metodi di programmazione tradizionali, usando comportamenti della fisica quantistica come sovrapposizione, entanglement e interferenza quantistica.

## <a name="what-can-a-quantum-computer-do"></a>Cosa è possibile fare con un computer quantistico?

Un computer quantistico non è un supercomputer che può eseguire tutte le operazioni più velocemente, ma esistono alcune aree in cui i computer quantistici garantiscono risultati eccezionali.

- [Simulazione quantistica](xref:microsoft.quantum.overview.introduction#quantum-simulation)
- [Crittografia](xref:microsoft.quantum.overview.introduction#cryptography-and-shors-algorithm)
- [Ricerca](xref:microsoft.quantum.overview.introduction#search-and-grovers-algorithm)
- [Ottimizzazione](xref:microsoft.quantum.overview.introduction#quantum-inspired-computing-and-optimization)
- [Machine Learning](xref:microsoft.quantum.overview.introduction#quantum-machine-learning)

## <a name="quantum-simulation"></a>Simulazione quantistica

Poiché i computer quantistici usano i fenomeni quantistici nel calcolo, sono particolarmente adatti per la modellazione di altri sistemi quantistici. La fotosintesi, la superconduttività e le formazioni molecolari complesse sono esempi di meccanismi quantistici che i programmi quantistici possono simulare.

## <a name="cryptography-and-shors-algorithm"></a>Crittografia e algoritmo di Shor

Nel 1994 Peter Shor ha dimostrato che un computer quantistico scalabile può violare tecniche di crittografia ampiamente diffuse, ad esempio l'algoritmo RSA. La crittografia classica si basa sull'intrattabilità dei problemi, ad esempio la fattorizzazione di interi o i logaritmi discreti, molti dei quali possono essere risolti in modo più efficiente con i computer quantistici.

## <a name="search-and-grovers-algorithm"></a>Ricerca e algoritmo di Grover

Nel 1996 Lov Grover ha sviluppato un algoritmo quantistico che accelera notevolmente la soluzione di ricerche di dati non strutturati, eseguendo la ricerca in un minor numero di passaggi rispetto a qualsiasi algoritmo classico.

## <a name="quantum-inspired-computing-and-optimization"></a>Calcolo e ottimizzazione di ispirazione quantistica

Gli algoritmi di ispirazione quantistica usano principi quantistici per incrementare velocità e accuratezza, ma vengono implementati in sistemi di computer classici. Questo approccio consente agli sviluppatori di sfruttare la potenza delle nuove tecniche quantistiche già oggi senza attendere la disponibilità dell'hardware quantistico, che è ancora un settore emergente.

L'ottimizzazione è il processo di individuazione della migliore soluzione a un problema, in base al risultato desiderato e ai vincoli. Fattori quali i costi, la qualità o il tempo di produzione giocano tutti un ruolo strategico nelle decisioni prese dal settore e dalla scienza. Gli algoritmi di ottimizzazione di ispirazione quantistica in esecuzione nei computer classici odierni possono trovare soluzioni finora impossibili. Oltre all'ottimizzazione del flusso di traffico per ridurre la congestione, consente l'assegnazione dei gate aerei, il recapito dei pacchi, la pianificazione dei processi e altro ancora. Grazie all'innovazione nella scienza dei materiali, saranno disponibili nuove forme di energia, batterie con capacità più elevata o materiali più leggeri ma più durevoli.

> [!NOTE]
> Leggere altre informazioni su come il calcolo di ispirazione quantistica Microsoft è usato nella [scienza dei materiali](https://cloudblogs.microsoft.com/quantum/2020/01/21/oti-lumionics-accelerating-materials-design-microsoft-azure-quantum/), nella [gestione dei rischi](https://cloudblogs.microsoft.com/quantum/2019/05/22/microsoft-quantum-collaborates-with-willis-towers-watson-to-transform-risk-management-solutions/) e nella [medicina](https://blogs.microsoft.com/blog/2018/05/18/microsoft-quantum-helps-case-western-reserve-university-advance-mri-research/).

## <a name="quantum-machine-learning"></a>Apprendimento automatico quantistico

L'apprendimento automatico nei computer classici sta rivoluzionando il mondo della scienza e dell'impresa. Tuttavia, il costo di calcolo elevato del training dei modelli ostacola lo sviluppo e l'ambito del campo. L'area dell'apprendimento automatico quantistico esplora come definire e implementare il software quantistico che abilita l'apprendimento automatico che viene eseguito più rapidamente che nei computer classici.

Il kit di sviluppo Microsoft Quantum include la [libreria di apprendimento automatico quantistico](xref:microsoft.quantum.machine-learning.concepts.intro) che consente di eseguire esperimenti di apprendimento automatico ibrido quantistico/classico. La libreria include esempi ed esercitazioni e fornisce gli strumenti necessari per implementare un nuovo algoritmo quantistico-classico ibrido, il classificatore quantistico incentrato sul circuito, per risolvere i problemi di classificazione supervisionati.

## <a name="no-locq-and-the-microsoft-quantum-development-kit-qdk"></a>Q# e kit di sviluppo Microsoft Quantum (QDK)

Q# è il linguaggio di programmazione open source di Microsoft per lo sviluppo e l'esecuzione di algoritmi quantistici. Fa parte del [QDK](https://docs.microsoft.com/quantum/), un kit di sviluppo completo per Q# che è possibile usare con gli strumenti e i linguaggi standard per sviluppare applicazioni quantistiche che si possono eseguire in vari ambienti, incluso il simulatore quantistico di stato completo predefinito.

Sono disponibili estensioni per Visual Studio e VS Code e pacchetti da usare con Python e Jupyter Notebook.

Il QDK include una libreria standard insieme a librerie specializzate di chimica, apprendimento automatico e numeriche.

La documentazione include una guida al linguaggio Q#, le esercitazioni e il codice di esempio per iniziare rapidamente e articoli avanzati che consentono di approfondire i concetti relativi al calcolo quantistico.  

## <a name="microsoft-quantum-hardware-partners"></a>Partner di Microsoft per l'hardware quantistico

Microsoft collabora con le aziende produttrici di hardware quantistico per fornire agli sviluppatori l'accesso al cloud per l'hardware quantistico. Sfruttando la piattaforma [Azure Quantum](https://azure.microsoft.com/services/quantum/) e il linguaggio Q#, gli sviluppatori hanno la possibilità di esplorare gli algoritmi quantistici ed eseguire programmi quantistici su diversi tipi di hardware quantistico.

[IonQ](https://ionq.com/news/november-4-2019-microsoft-partnership) e [Honeywell](https://www.honeywell.com/en-us/newsroom/news/2019/11/the-future-of-quantum-computing) usano entrambi **processori basati su ioni intrappolati**, che usano singoli ioni intrappolati in un campo elettronico, mentre [QCI](https://quantumcircuits.com/news-and-publications/quantum-circuits-partners-with-microsoft-on-azure-quantum) usa circuiti superconduttori.

## <a name="next-steps"></a>Passaggi successivi

[Concetti principali per il calcolo quantistico](xref:microsoft.quantum.overview.understanding)
[Guide di avvio rapido](xref:microsoft.quantum.welcome)