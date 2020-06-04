---
title: Informazioni sul calcolo quantistico
description: Che cosa sono i computer quantistici e come usano i principi di meccanica quantistica?
author: bradben
ms.author: bradben
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.understanding
ms.openlocfilehash: aa3de9290250e82bc2f3ea5f1d35a16095469f7e
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327731"
---
# <a name="understanding-quantum-computing"></a>Informazioni sul calcolo quantistico

Il calcolo quantistico usa i principi della meccanica quantistica per elaborare le informazioni. Per questo motivo, il calcolo quantistico richiede un approccio diverso rispetto al calcolo classico.  Un esempio di questa differenza è il processore usato nei computer quantistici.  Laddove i computer classici usano chip noti basati su silicio, i computer quantistici usano materiali quantistici, ad esempio atomi, ioni, fotoni o elettroni.  

Il materiale quantistico si comporta in base alle leggi della meccanica quantistica, sfruttando concetti quali calcolo probabilistico, sovrapposizione ed entanglement. Questi concetti rappresentano la base per gli algoritmi quantistici che sfruttano la potenza del calcolo quantistico per risolvere problemi complessi. Questo articolo descrive alcuni dei concetti fondamentali della meccanica quantistica su cui è basato il calcolo quantistico.

## <a name="a-birds-eye-view-of-quantum-mechanics"></a>Panoramica della meccanica quantistica

La meccanica quantistica, denominata anche teoria dei quanti, è un ramo della fisica che riguarda le particelle a livello atomico e subatomico. Al livello quantistico, tuttavia, non si applicano molte delle leggi della meccanica che si danno per scontate. La sovrapposizione, la misura quantistica e l'entanglement sono tre fenomeni fondamentali per il calcolo quantistico.  

### <a name="superposition-vs-binary-computing"></a>Confronto tra sovrapposizione e calcolo binario

Si supponga di svolgere attività fisica nel proprio soggiorno. Ci si volta completamente a sinistra e quindi completamente a destra. Provare quindi a voltarsi a sinistra e a destra contemporaneamente. Non è possibile farlo, o almeno, non senza dividersi a metà.  Ovviamente, non è possibile trovarsi contemporaneamente in entrambi questi stati. Non si può essere rivolti verso sinistra e verso destra allo stesso tempo.

Tuttavia, se si è una particella quantistica, è possibile avere una certa probabilità di essere *rivolti verso sinistra* E una certa probabilità di essere *rivolti verso destra* a causa di un fenomeno noto come **sovrapposizione** (denominato anche **coerenza**).

Una particella quantistica, ad esempio un elettrone, ha le sue proprietà "rivolta verso sinistra o verso destra" specifiche, ad esempio lo **spin o rotazione intorno al proprio asse** verso l'alto o verso il basso, o per renderla più correlabile al calcolo binario classico, ovvero 1 o 0. Quando una particella quantistica si trova in uno stato di sovrapposizione, si tratta di una combinazione lineare di un numero infinito di stati compreso tra 1 e 0, ma non si sa quale sarà fino a quando non lo si esaminerà, tramite il fenomeno successivo, ovvero la **misura quantistica**.

### <a name="quantum-measurement"></a>Misura quantistica

Si supponga che un amico venga a trovarci e che desideri scattare una foto mentre facciamo attività fisica. È molto probabile che ottenga un'immagine sfocata mentre ci stiamo girando completamente a sinistra e completamente a destra.

Tuttavia, se si è una particella quantistica, si verifica una fatto interessante. Indipendentemente dalla posizione in cui ci si trova mentre viene scattata la foto, si verrà ripresi solo completamente rivolti a sinistra o completamente rivolti a destra, ma in nessuno stato intermedio.

Questo dipende dal fatto che l'atto di osservare o misurare una particella quantistica **collassa** lo stato di sovrapposizione (noto anche come **decoerenza**) e la particella assume uno stato binario classico di 1 o 0.

Questo stato binario è utile perché nel calcolo è possibile eseguire molte operazioni con gli 1 e gli 0. Tuttavia, una volta che una particella quantistica viene misurata e collassa, rimane in tale stato sempre (proprio come l'immagine) e sarà sempre 1 o 0. Come si vedrà in seguito, tuttavia, nel calcolo quantistico sono previste operazioni che possono "reimpostare" nuovamente una particella a uno stato di sovrapposizione, per poterla riutilizzare per i calcoli quantistici.

### <a name="entanglement"></a>Entanglement

Probabilmente il fenomeno più interessante della meccanica quantistica è la capacità di due o più particelle quantistiche di diventare correlate tramite **entanglement**. Quando le particelle sono correlate, formano un singolo sistema in modo che lo stato quantistico di una particella non possa essere descritto indipendentemente dallo stato quantistico delle altre particelle. Ciò significa che qualsiasi operazione o processo applicato a una particella è correlato anche alle altre particelle.

Oltre a questa interdipendenza, le particelle possono mantenere questa connessione anche quando sono separate da distanze incredibilmente elevate, anche anni luce. Gli effetti della misura quantistica si applicano anche alle particelle correlate, tanto che quando una particella viene misurata e collassa, collassa anche l'altra particella. Poiché esiste una correlazione tra i qubit con entanglement, la misura dello stato di un qubit fornisce informazioni sullo stato degli altri qubit. Questa proprietà specifica è molto utile nel calcolo quantistico.

### <a name="qubits-and-probability"></a>Qubit e probabilità

I computer classici archiviano ed elaborano le informazioni in bit, che possono avere uno stato di 1 o 0, ma mai entrambi. L'equivalente nel calcolo quantistico è il **qubit**, che rappresenta lo stato di una particella quantistica. A causa della sovrapposizione, i qubit possono essere in uno stato di 1 o 0 o di qualsiasi altro valore compreso tra essi. A seconda della configurazione, un qubit ha una certa *probabilità* di collassare in 1 o 0. La probabilità del qubit di collassare in un modo o nell'altro è determinata dall'**interferenza quantistica**. 

Torniamo all'amico che ci ha scattato la foto. Si supponga che abbia applicato alla fotocamera dei filtri speciali denominati filtri di *interferenza*. Selezionando il filtro *70/30* e scattando le foto, nel 70% delle immagini verremo ritratti mentre siamo rivolti verso sinistra e nel 30% saremo rivolti verso destra. Il filtro ha interferito con lo stato regolare della fotocamera per influenzare la probabilità del suo comportamento.

Analogamente, l'interferenza quantistica influisce sullo stato di un qubit per influenzare la probabilità di un determinato risultato durante la misura e questo stato probabilistico è il punto di eccellenza della potenza del calcolo quantistico.

Ad esempio, per due bit in un computer classico, ogni bit può archiviare un valore di 1 o 0 e vengono così archiviati insieme quattro valori possibili: **00**, **01**, **10**e **11**, ma solo uno di questi alla volta. Con due qubit in sovrapposizione, tuttavia, ogni qubit può essere 1 o 0 o *entrambi*, quindi è possibile rappresentare contemporaneamente gli stessi quattro valori. Con tre qubit è possibile rappresentare otto valori, con quattro qubit è possibile rappresentare 16 valori e così via.

## <a name="summary"></a>Summary

Questi concetti rappresentano solo alcuni cenni superficiali della meccanica quantistica, ma sono fondamentali da conoscere per il calcolo quantistico.

- **Sovrapposizione**: possibilità delle particelle quantistiche di essere una combinazione di tutti gli stati possibili.
- **Misura quantistica**: l'atto di osservare una particella quantistica in sovrapposizione e di ottenere uno degli stati possibili.
- **Entanglement**: possibilità delle particelle quantistiche di correlare i risultati della misura l'una con l'altra.
- **Qubit**: unità di base delle informazioni nel calcolo quantistico. Un qubit rappresenta una particella quantistica con sovrapposizione di tutti gli stati possibili.
- **Interferenza**: comportamento intrinseco di un qubit a causa della sovrapposizione per influenzare la probabilità che collassi in un modo o in un altro.

## <a name="next-steps"></a>Passaggi successivi

[Computer e simulatori quantistici](xref:microsoft.quantum.overview.simulators)
