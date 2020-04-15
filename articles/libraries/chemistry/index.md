---
title: Introduzione alla libreria di chimica quantistica
description: Informazioni sulla libreria di chimica quantistica Microsoft e su come viene usata per simulare problemi relativi alle strutture elettroniche nei computer quantistici.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.intro
ms.openlocfilehash: 4268eafa5e53c0a026d179503ac6db88652a8f90
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "77907325"
---
# <a name="introduction-to-the-quantum-chemistry-library"></a>Introduzione alla libreria di chimica quantistica

La simulazione di sistemi fisici ha svolto a lungo un ruolo centrale nel calcolo quantistico.  Questo perché si ritiene che la dinamica quantistica sia intrattabile per la simulazione in computer quantistici, ovvero che la complessità della simulazione del sistema sia esponenzialmente proporzionale alle dimensioni del sistema quantistico in questione.  La simulazione di problemi nell'ambito della chimica e della scienza dei materiali rimane forse l'applicazione più suggestiva del calcolo quantistico e consentirà di sondare meccanismi di reazione chimica che finora non era possibile misurare o simulare.  Consentirà anche di simulare materiali elettronici correlati, come i superconduttori ad alta temperatura. L'elenco delle applicazioni in questo ambito è notevole.

Scopo di questa documentazione è quello di offrire una breve introduzione alla simulazione di problemi dei sistemi elettronici in computer quantistici per aiutare il lettore a comprendere il ruolo che molti aspetti della libreria di simulazione hamiltoniana giocano nello spazio.  Si inizierà con una breve introduzione alla meccanica quantistica per poi passare a esaminare gli aspetti della modellazione dei sistemi elettronici.  Verrà quindi spiegato in che modo è possibile emulare la dinamica quantistica usando un computer quantistico.  Al termine verranno analizzati due metodi usati per compilare la dinamica quantistica in sequenze di gate elementari, ovvero qubitizzazione e decomposizioni di Trotter-Suzuki.
