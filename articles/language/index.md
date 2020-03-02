---
title: Linguaggio di programmazione Q#
description: Introduzione al linguaggio Q# per lo sviluppo di programmi quantistici.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.intro
ms.openlocfilehash: b62e6866fc3609d95c26a5eab2a6eac325dfe330
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907376"
---
# <a name="the-q-programming-language"></a>Linguaggio di programmazione Q#

## <a name="introduction"></a>Introduzione

Un modello naturale per il calcolo quantistico consiste nel considerare il computer quantistico come un coprocessore, simile a quello usato per GPU, FPGA e altri processori aggiuntivi.
La logica di controllo principale esegue il codice classico in un computer "host" classico.
Quando appropriato e necessario, il programma host può richiamare una subroutine che viene eseguita nel processore aggiuntivo.
Al termine della subroutine, il programma host ottiene l'accesso ai risultati della subroutine.

Q# (Q-Sharp) è un linguaggio di programmazione specifico di dominio usato per esprimere gli algoritmi quantistici.
Deve essere usato per la scrittura di subroutine che vengono eseguite su un processore quantistico aggiuntivo, sotto il controllo di un computer e un programma host classico.
Fintanto che i processori quantistici non sono ampiamente disponibili, le subroutine Q# vengono eseguite in un simulatore.

Q# fornisce un set ridotto di tipi primitivi, insieme a due modi (matrici e tuple) per la creazione di nuovi tipi strutturati.
Supporta un modello procedurale di base per la scrittura di programmi, con cicli e istruzioni if/then (se/allora).
I costrutti di primo livello in Q# sono tipi, operazioni e funzioni definiti dall'utente.

Le sezioni seguenti illustrano in dettaglio:
- [Modello di tipo](xref:microsoft.quantum.language.type-model)
- [Espressioni](xref:microsoft.quantum.language.expressions)
- [Istruzioni](xref:microsoft.quantum.language.statements)
- [Struttura dei file](xref:microsoft.quantum.language.file-structure)

## <a name="conventions"></a>Convenzioni

Stiamo lavorando per garantire che i segni di punteggiatura comuni vengano usati in modo coerente in tutte le situazioni.
Questo ha l'obiettivo di facilitare l'apprendimento e la lettura di Q#, dal momento che tali segni hanno sempre lo stesso significato e lo stesso concetto è sempre rappresentato nel medesimo modo.

In particolare:

- Il punto e virgola, `;`, viene usato per terminare un'istruzione o una direttiva a riga singola.
  Non viene usato per altri scopi.
- La virgola, `,`, viene usata per separare gli elementi di una sequenza. Viene usata per i valori letterali tupla, i valori letterali matrice, gli elenchi di argomenti, le definizioni di tuple e gli elenchi di tipi. **A seguito di una modifica rispetto alle versioni precedenti, `;` non è più supportato come separatore di valori letterali matrice.**
- I due punti, `:`, vengono usati per introdurre un'annotazione di tipo e sono principalmente usati nelle firme chiamabili.
  Poiché i due punti introducono sempre una firma del tipo, l'operatore condizionale ternario introdotto nella versione 0.3 usa una barra verticale, `|`, per separare i valori true e false. Di conseguenza, Q# usa `cond ? tval | fval` anziché i due punti come separatore, come in C.
  
