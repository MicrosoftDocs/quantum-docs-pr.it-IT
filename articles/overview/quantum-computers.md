---
title: Cosa è possibile fare con i computer quantistici?
description: Informazioni sull'impatto del calcolo quantistico, a partire dai nuovi algoritmi quantistici agli algoritmi di ispirazione quantistica in esecuzione nei computer classici.
author: natke
ms.author: nakersha
ms.date: 10/23/2019
ms.topic: article
uid: microsoft.quantum.overview.computers
ms.openlocfilehash: d4be970c635ca090e8dcb1b58d5c840eebd4d110
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2019
ms.locfileid: "73443835"
---
# <a name="what-can-a-quantum-computer-do"></a>Cosa è possibile fare con un computer quantistico?

Quali operazioni è possibile eseguire con un computer quantistico rispetto a quelle eseguibili con uno classico?

Per risolvere alcuni dei problemi più complessi del mondo, in cui la ricerca di una soluzione richiederebbe miliardi di anni con i computer attualmente disponibili, un computer quantistico può impiegare giorni, ore o persino minuti. Il calcolo quantistico consentirà ai ricercatori di sviluppare nuovi catalizzatori e nuovi materiali, migliorare i farmaci, accelerare i progressi nell'intelligenza artificiale e rispondere a domande fondamentali sulle origini dell'universo.

## <a name="quantum-simulation"></a>Simulazione quantistica

L'uso di programmi quantistici per modellare i sistemi quantistici ha un immenso potenziale per svelare informazioni dettagliate per l'innovazione in molti settori. Fotosintesi, superconduttori e molecole complesse sono esempi di sistemi quantistici che possono essere simulati usando programmi quantistici.

La simulazione di sistemi microscopici il cui funzionamento risponde alle leggi della meccanica quantistica è particolarmente onerosa dal punto di vista del calcolo. È necessario considerare tutti gli stati possibili che possono rientrare nella sovrapposizione, tenendo presente che il numero di stati aumenta in modo esponenziale in base alle dimensioni del sistema. In un computer quantistico non è necessario modellare tutti gli stati del sistema. Lo stato quantistico del sistema che si vuole simulare viene invece incorporato nei qubit del computer stesso e la simulazione viene eseguita con un set specifico di gate quantistici. In altre parole si usa un computer quantistico per simulare un sistema quantistico.

Le molecole chimiche sono sistemi quantistici e quindi possono essere analizzate in questo modo. Una di queste sostanze chimiche specifiche è l'enzima _nitrogenasi_, le cui proprietà, se adeguatamente comprese, potrebbero consentire la riduzione del consumo energetico e le emissioni di gas serra degli attuali fertilizzanti.

## <a name="cryptography"></a>Crittografia

Probabilmente l'applicazione più famosa dei computer quantistici è nella crittografia, per cui Peter Shor ha mostrato in 1994 che un computer quantistico scalabile può violare tutte le tecniche di crittografia ampiamente usate.  La crittografia classica si basa sull'intrattabilità delle operazioni su numeri elevati, ad esempio la fattorizzazione di numeri di grandi dimensioni in due numeri primi.  Con il calcolo quantistico queste operazioni diventano teoricamente trattabili tramite l'algoritmo di Shor. Anche se l'implementazione di questo algoritmo non è fisicamente possibile con la scala corrente dell'hardware quantistico, ha generato lo sviluppo di algoritmi quantistici resistenti per la sicurezza dei dati a prova di futuro, inclusi i nuovi algoritmi quantistici per la crittografia e la distribuzione di chiavi crittografiche.  Microsoft vanta un team leader mondiale nel settore della crittografia e della sicurezza post-quantistiche che sviluppa algoritmi resistenti al calcolo quantistico. 

## <a name="optimization"></a>Ottimizzazione

L'ottimizzazione è un'attività che prevede l'esecuzione di una ricerca di grandi dimensioni in uno spazio altamente dimensionale per una soluzione davvero efficace che riduce al minimo una funzione con un costo specifico.   In un computer quantistico è possibile accelerare gli algoritmi di ottimizzazione per trovare soluzioni che altrimenti non sono possibili. Le applicazioni possibili possono variare dal trasporto e la logistica, al sistema sanitario, alla diagnostica e alla scienza dei materiali. L'impatto dell'aumento di efficienza di questi settori può risultare particolarmente significativo. 

L'ottimizzazione con calcolo quantistico consente di innovare il trasporto e la logistica in modi impensabili con i sistemi classici odierni. L'ottimizzazione del flusso del traffico può ridurre le congestioni.  Oltre alla pianificazione dei percorsi, consente l'assegnazione dei gate aerei, il recapito dei pacchi, la pianificazione dei processi e altro ancora.  Grazie all'innovazione nella scienza dei materiali, saranno disponibili nuove forme di energia, batterie con capacità più elevata o materiali più leggeri ma più resistenti. 

## <a name="machine-learning"></a>Machine learning

L'esecuzione di un numero elevato di calcoli numerici nel calcolo classico prevede essenzialmente la risoluzione di sistemi lineari di equazioni. Questa considerazione è valida in special modo nel campo dell'apprendimento automatico, in cui la maggior parte del costo di calcolo è dovuta al calcolo l'inverso di enormi matrici.

Fortunatamente, esiste un algoritmo quantistico che consente di risolvere il sistema in modo notevolmente più rapido rispetto a un computer classico. Questo approccio si traduce in una notevole accelerazione quando si affrontano problemi che richiedono la risoluzione di sistemi lineari di equazioni.

Le soluzioni ai problemi in queste aree consentiranno di risolvere la crisi energetica, il cambiamento climatico, la scarsità di cibo e la diagnosi medica personale e precisa.

## <a name="quantum-inspired-computing"></a>Calcolo di ispirazione quantistica

Gli algoritmi di ispirazione quantistica vengono implementati con software classico, ma usano principi quantistici per incrementare velocità e accuratezza.

Gli algoritmi di ispirazione quantistica vengono applicati alla ricerca medica, ad esempio per migliorare l'accuratezza delle scansioni a risonanza magnetica. Il calcolo di ispirazione quantistica viene usato per ottimizzare la configurazione dei dispositivi per risonanza magnetica allo scopo di identificare patologie specifiche.

## <a name="next-steps"></a>Passaggi successivi

* [Quali sono i vantaggi derivanti dall'apprendimento del calcolo quantistico?](xref:microsoft.quantum.overview.why)
* [Introduzione a Microsoft Quantum Development Kit](xref:microsoft.quantum.welcome)
