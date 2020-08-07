---
title: Libreria di apprendimento automatico quantistico
author: alexeib2
ms.author: alexei.bocharov@microsoft.com
ms.date: 2/27/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.training
no-loc:
- Q#
- $$v
ms.openlocfilehash: 52c3f69fb99384270a27e57c4f32212d18bee1a4
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868900"
---
# <a name="quantum-machine-learning-glossary"></a>Glossario Machine Learning Quantum

Il training di un classificatore Quantum incentrato sul circuito è un processo con molte parti mobili che richiedono la stessa quantità (o leggermente maggiore) di calibrazione per valutazione ed errore come training dei classificatori tradizionali. Qui vengono definiti i concetti e gli ingredienti principali di questo processo di training.

## <a name="trainingtesting-schedules"></a>Pianificazioni di training/test

Nel contesto del training del classificatore una *pianificazione* descrive un subset di campioni di dati in un set di training o di testing globale. Una pianificazione viene in genere definita come una raccolta di indici di esempio.

## <a name="parameterbias-scores"></a>Punteggi di parametri/distorsioni

Dato un vettore di parametro candidato e una polarizzazione del classificatore, il *Punteggio di convalida* viene misurato in relazione a una pianificazione di convalida scelta e viene espressa da un numero di classificazioni errate conteggiate su tutti gli esempi nella pianificazione.

## <a name="hyperparameters"></a>Iperparametri

Il processo di training del modello è regolato da determinati valori preimpostati detti *iperparametri*:

### <a name="learning-rate"></a>Velocità di apprendimento

È uno degli iperparametri chiave. Definisce la quantità di stima della sfumatura stocastica corrente che influisca sull'aggiornamento del parametro. La dimensione del Delta di aggiornamento del parametro è proporzionale alla velocità di apprendimento. I valori di velocità di apprendimento inferiori portano a un'evoluzione più lenta dei parametri e alla convergenza più lenta, ma i valori eccessivamente grandi di LR possono compromettere la convergenza, perché la discesa della sfumatura non viene mai vincolata a un minimo locale specifico. Mentre la velocità di apprendimento è in modo adattivo regolata dall'algoritmo di training in una certa misura, la selezione di un buon valore iniziale è importante. Un normale valore iniziale predefinito per la velocità di apprendimento è 0,1. La selezione del valore migliore della velocità di apprendimento è un'arte (vedere, ad esempio, la sezione 4,3 di Goodfellow et al., "Deep Learning", MIT Press, 2017).

### <a name="minibatch-size"></a>Dimensioni Minibatch

Definisce il numero di campioni di dati usati per una singola stima della sfumatura stocastica. I valori più grandi delle dimensioni minibatch in genere comportano una convergenza più affidabile e monotona, ma possono potenzialmente rallentare il processo di training, in quanto il costo di una stima di sfumatura è proporzionale alle dimensioni corrispondenza minima. Un valore predefinito usuale per la dimensione minibatch è 10.

### <a name="training-epochs-tolerance-gridlocks"></a>Epoche di training, tolleranza, paralisi

"Epoch" significa che un pass-through completo dei dati di training pianificati.
Il numero massimo di epoche per un thread di training (vedere di seguito) dovrebbe essere limitato. Il thread di training viene definito per terminare (con i parametri candidati più noti) quando è stato eseguito il numero massimo di epoche. Questa formazione, tuttavia, termina in precedenza quando la frequenza di classificazione errata nella pianificazione della convalida scende al di sotto di una tolleranza scelta. Si supponga, ad esempio, che la tolleranza di classificazione errata sia 0,01 (1%); se nel set di convalida di 2000 campioni vengono visualizzati meno di 20 classificazioni errate, il livello di tolleranza è stato raggiunto. Un thread di training termina anche in modo anomalo se il Punteggio di convalida del modello candidato non mostra alcun miglioramento rispetto a più epoche consecutive (un ingorgo). La logica per la terminazione dello stato di ingorghi è attualmente hardcoded.

### <a name="measurements-count"></a>Conteggio misure

La stima dei punteggi di Training/convalida e dei componenti della sfumatura stocastica su un dispositivo Quantum equivale a stimare le sovrapposizioni dello stato del quantum che richiedono più misurazioni delle osservabili appropriate. Il numero di misure deve essere ridimensionato come $O (1/\ Epsilon ^ 2) $ dove $ \epsilon $ rappresenta l'errore di stima desiderato.
Come regola generale, il conteggio delle misure iniziali potrebbe essere approssimativamente $1/\ mbox {Tolerance} ^ 2 $ (vedere la definizione di tolleranza nel paragrafo precedente). È necessario rivedere il conteggio delle misure verso l'alto se la discesa della sfumatura risulta troppo irregolare e la convergenza è troppo difficile da raggiungere.

### <a name="training-threads"></a>Thread di training

La funzione di probabilità, che è l'utilità di training per il classificatore, è molto raramente convessa, vale a dire che in genere ha una moltitudine di Optima locali nello spazio dei parametri che può variare significativamente in base alla qualità. Poiché il processo SGD può convergere a un solo Optimum specifico, è importante esplorare più vettori di parametri iniziali. Una pratica comune in machine learning consiste nell'inizializzare i vettori di avvio in modo casuale. L' Q# API di training accetta una matrice arbitraria di questi vettori iniziali, ma il codice sottostante li Esplora in modo sequenziale. In un computer multicore o in effetti su qualsiasi architettura di elaborazione parallela è consigliabile eseguire diverse chiamate all'API di Q# training in parallelo con diverse inizializzazioni di parametri tra le chiamate.

#### <a name="how-to-modify-the-hyperparameters"></a>Come modificare gli iperparametri

Nella libreria QML, il modo migliore per modificare gli iperparametri consiste nell'eseguire l'override dei valori predefiniti del tipo definito dall'utente [`TrainingOptions`](xref:microsoft.quantum.machinelearning.trainingoptions) . A tale scopo, viene chiamato con la funzione [`DefaultTrainingOptions`](xref:microsoft.quantum.machinelearning.defaulttrainingoptions) e viene applicato l'operatore `w/` per eseguire l'override dei valori predefiniti. Ad esempio, per usare le misurazioni 100.000 e una velocità di apprendimento di 0,01:
 ```qsharp
let options = DefaultTrainingOptions()
w/ LearningRate <- 0.01
w/ NMeasurements <- 100000;
 ```
