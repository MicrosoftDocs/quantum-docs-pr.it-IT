---
title: Installare Microsoft Quantum Development Kit (QDK)
description: Come installare Microsoft Quantum Development Kit per ambienti diversi.
author: bradben
ms.author: bradben
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: 3aafe78d5910027e2836f7dce72c064e75fc4436
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863719"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>Installare Microsoft Quantum Development Kit (QDK)

Informazioni su come installare il Microsoft Quantum Development Kit (QDK), per iniziare a sviluppare con la programmazione quantistica. Contenuto del QDK:

- Linguaggio di programmazione Q#
- Set di librerie che estrapolano funzionalità complesse in Q#
- API per linguaggi Python e .NET (C#, F# e VB.NET) per l'esecuzione di programmi quantistici scritti in Q#
- Strumenti per facilitare lo sviluppo

I programmi Q# possono essere eseguiti come applicazioni autonome usando Visual Studio Code o Visual Studio o tramite Jupyter Notebook con il kernel Jupyter IQ#.
Possono anche essere abbinati a un programma host scritto in un linguaggio .NET (in genere C#) o Python, per permettere la chiamata di operazioni quantistiche dall'interno di un programma classico.

I flussi di lavoro per ognuna di queste configurazioni vengono descritti e confrontati in [Modalità di esecuzione di programmi Q#](xref:microsoft.quantum.guide.host-programs).

Per procedere con l'installazione di QDK e la creazione di progetti Q#, selezionare la configurazione preferita:

[Sviluppare con applicazioni in Q#](xref:microsoft.quantum.install.standalone): scegliere questo approccio per usare Q# dal prompt dei comandi. Non è necessario un driver o un programma host come per le opzioni seguenti.

[Sviluppare con notebook di Jupyter Q#](xref:microsoft.quantum.install.jupyter): selezionare questo ambiente per eseguire il codice Q# nelle celle con testo incorporato o creare esercitazioni interattive sul calcolo quantistico. 

[Sviluppare con Q# e Python](xref:microsoft.quantum.install.python): consente di combinare Python e Q# per creare un programma host Python che chiama le operazioni Q#.

[Sviluppare con Q# e .NET](xref:microsoft.quantum.install.cs): consente di combinare C#, F# o VB.NET con Q# per creare un programma host .NET che chiama le operazioni Q#.
