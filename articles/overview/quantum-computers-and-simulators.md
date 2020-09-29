---
title: Computer e simulatori quantistici
description: Informazioni su hardware quantistico, simulatori quantistici e sul funzionamento delle operazioni quantistiche.
author: bradben
ms.author: v-benbra
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.simulators
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8691838b2d6c54baa40042245eee8c901a7ca965
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835010"
---
# <a name="quantum-computers-and-quantum-simulators"></a>Computer e simulatori quantistici

I computer quantistici sono ancora in una fase iniziale di sviluppo. L'hardware e la manutenzione sono costosi e la maggior parte dei sistemi si trovano in università e laboratori di ricerca. La tecnologia sta avanzando, tuttavia, ed è disponibile un accesso pubblico limitato ad alcuni sistemi.

I simulatori quantistici sono programmi software eseguiti in computer classici che consentono di eseguire e testare i programmi quantistici in un ambiente che permette di prevedere il modo in cui i qubit reagiranno a diverse operazioni.

## <a name="quantum-hardware"></a>Hardware quantistico

Un computer quantistico è costituito da tre parti principali: un'area in cui sono ospitati i qubit, un metodo per il trasferimento dei segnali ai qubit e un computer classico per l'esecuzione di un programma e l'invio di istruzioni.

- Il materiale quantistico usato per i qubit è fragile e molto sensibile alle interferenze ambientali. Per alcuni metodi di archiviazione dei qubit, l'unità che ospita i qubit viene mantenuta a una temperatura appena sopra zero assoluto per massimizzare la coerenza. Altri tipi di alloggiamento dei qubit usano una camera sottovuoto per ridurre al minimo le vibrazioni e stabilizzare i qubit.  
- I segnali possono essere inviati ai qubit usando diversi metodi, tra cui microonde, laser e tensione.

Per funzionare correttamente, i computer quantistici devono affrontare numerose problematiche. La correzione degli errori nei computer quantistici rappresenta un problema significativo e la scalabilità, ovvero l'aggiunta di più qubit, aumenta la frequenza degli errori. A causa di queste limitazioni, la disponibilità di un PC quantistico per il desktop è una prospettiva molto lontana nel futuro, ma un computer quantistico commerciale per laboratorio è una possibilità più vicina.

## <a name="quantum-simulators"></a>Simulatori quantistici

I simulatori quantistici eseguiti in computer classici consentono di simulare il calcolo di algoritmi quantistici in un sistema quantistico.  Il kit di sviluppo Microsoft Quantum include un simulatore vettoriale di stato completo insieme ad altri simulatori quantistici specializzati.

## <a name="topological-qubit"></a>Qubit topologico

Microsoft sta sviluppando un computer quantistico basato su qubit topologici. Un qubit topologico sarà meno interessato dai cambiamenti nel proprio ambiente, riducendo in tal modo il grado di correzione degli errori esterni necessario.

I qubit topologici sono caratterizzati da una maggiore stabilità e resistenza al rumore ambientale, il che significa che possono essere ridimensionati più facilmente e rimanere affidabili più a lungo.

## <a name="microsoft-and-quantum-hardware-partnerships"></a>Partnership di Microsoft per l'hardware quantistico

Microsoft collabora con i produttori di hardware quantistico IonQ, Honeywell e QCI per rendere i computer quantistici accessibili agli sviluppatori in futuro. Sfruttando la piattaforma Azure Quantum, gli sviluppatori potranno usare il kit di sviluppo Microsoft Quantum e Q# per scrivere programmi quantistici ed eseguirli in modalità remota.

## <a name="quantum-computations"></a>Calcoli quantistici

L'esecuzione di calcoli in un computer quantistico o un simulatore quantistico segue un processo di base:

- Accesso ai qubit
- Inizializzazione dei qubit sullo stato desiderato
- Esecuzione di operazioni per trasformare gli stati dei qubit
- Misura dei nuovi stati dei qubit

L'inizializzazione e la trasformazione dei qubit vengono eseguite mediante **operazioni quantistiche**, talvolta denominate gate quantistici. Le operazioni quantistiche sono simili alle operazioni logiche del calcolo classico, ad esempio AND, OR, NOT e XOR. Un'operazione può essere elementare, come il capovolgimento dello stato di un qubit da 1 a 0 o la correlazione di una coppia di qubit, oppure prevedere l'uso di più operazioni in serie per influire sulla probabilità che un qubit sovrapposto collassi in un modo o nell'altro.

> [!NOTE] 
> Le [librerie Q#](xref:microsoft.quantum.libraries) forniscono operazioni predefinite che definiscono combinazioni complesse di operazioni quantistiche di basso livello. È possibile usare le operazioni della libreria per trasformare i qubit e per creare operazioni definite dall'utente più complesse.  

La misura del risultato del calcolo indica una risposta, ma per alcuni algoritmi quantistici non è necessariamente la risposta corretta. Poiché il risultato di alcuni algoritmi quantistici è basato sulla probabilità configurata dalle operazioni quantistiche, questi calcoli vengono eseguiti più volte per ottenere una distribuzione di probabilità e perfezionare l'accuratezza dei risultati.  La certezza che un'operazione ha restituito una risposta corretta è nota come verifica quantistica e rappresenta una sfida significativa nel calcolo quantistico.

## <a name="summary"></a>Summary

Il calcolo quantistico condivide alcuni degli stessi concetti del calcolo classico, con l'aggiunta di nuove peculiarità. Di seguito sono riportate alcune considerazioni importanti:

- L'hardware quantistico è costoso e fragile da usare, quindi per scrivere e testare i programmi vengono usati simulatori quantistici.
- Sia i computer classici che quelli quantistici usano operazioni logiche (o gate) per preparare i calcoli.
- I calcoli quantistici restituiscono probabilità.

Le innovazioni tecnologiche nell'hardware e nelle tecniche quantistiche stanno cambiando rapidamente il settore. Di seguito sono riportati alcuni dei [nuovi sviluppi](https://phys.org/search/?search=quantum+computer&s=0).

## <a name="next-steps"></a>Passaggi successivi

[Informazioni sul linguaggio di programmazione Q# e su QDK](xref:microsoft.quantum.overview.q-sharp)
