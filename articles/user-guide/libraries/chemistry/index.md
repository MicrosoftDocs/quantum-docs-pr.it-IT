---
title: Introduzione alla libreria di chimica quantistica
description: Informazioni sulla libreria di chimica quantistica Microsoft e su come viene usata per simulare problemi relativi alle strutture elettroniche nei computer quantistici.
author: QuantumWriter
ms.author: ageller
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 15439a34933bd561dc011acf48e669abeb031e33
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835792"
---
# <a name="introduction-to-the-quantum-chemistry-library"></a>Introduzione alla libreria di chimica quantistica

La simulazione di sistemi fisici ha svolto a lungo un ruolo centrale nel calcolo quantistico.  Questo perché si ritiene che la dinamica quantistica sia intrattabile per la simulazione in computer quantistici, ovvero che la complessità della simulazione del sistema sia esponenzialmente proporzionale alle dimensioni del sistema quantistico in questione.  La simulazione di problemi nell'ambito della chimica e della scienza dei materiali rimane forse l'applicazione più suggestiva del calcolo quantistico e consentirà di sondare meccanismi di reazione chimica che finora non era possibile misurare o simulare.  Consentirà anche di simulare materiali elettronici correlati, come i superconduttori ad alta temperatura. L'elenco delle applicazioni in questo ambito è notevole.

Scopo di questa documentazione è quello di offrire una breve introduzione alla simulazione di problemi dei sistemi elettronici in computer quantistici per aiutare il lettore a comprendere il ruolo che molti aspetti della libreria di simulazione hamiltoniana giocano nello spazio.  Si inizierà con una breve introduzione alla meccanica quantistica per poi passare a esaminare gli aspetti della modellazione dei sistemi elettronici.  Verrà quindi spiegato in che modo è possibile emulare la dinamica quantistica usando un computer quantistico.  Al termine verranno analizzati due metodi usati per compilare la dinamica quantistica in sequenze di gate elementari, ovvero qubitizzazione e decomposizioni di Trotter-Suzuki.
