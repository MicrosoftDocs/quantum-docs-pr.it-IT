---
title: Installare Microsoft Quantum Development Kit (QDK)
description: Come installare Microsoft Quantum Development Kit per ambienti diversi.
author: bradben
ms.author: bradben
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 6a52eb0a9cdf699e8bb37578ffa3d73fe96a990e
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85273487"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>Installare Microsoft Quantum Development Kit (QDK)

Informazioni su come installare il Microsoft Quantum Development Kit (QDK), per iniziare a sviluppare con la programmazione quantistica. Contenuto del QDK:

- Linguaggio di programmazione Q#
- Set di librerie che estrapolano funzionalità complesse in Q#
- API per linguaggi Python e .NET (C#, F# e VB.NET) per l'esecuzione di programmi quantistici scritti in Q#
- Strumenti per facilitare lo sviluppo

I programmi Q# possono essere eseguiti come applicazioni autonome usando Visual Studio Code o Visual Studio o tramite Jupyter Notebook con il kernel Jupyter IQ#.

Possono anche essere abbinati a un programma host scritto in un linguaggio .NET (in genere C#) o Python, per permettere la chiamata di operazioni quantistiche dall'interno di un programma classico.

QDK è disponibile per più ambienti di sviluppo. Selezionare la configurazione preferita tra le seguenti:

[Sviluppare con applicazioni della riga di comando di Q#](xref:microsoft.quantum.install.standalone): scegliere questo approccio per usare Q# dalla riga di comando. Non è necessario un driver o un programma host come per le opzioni seguenti.

[Sviluppare con Jupyter Notebook Q#](xref:microsoft.quantum.install.jupyter): selezionare questo ambiente per eseguire il codice Q# nelle celle con testo incorporato o creare esercitazioni interattive sul calcolo quantistico. 

[Sviluppare con Q# e Python](xref:microsoft.quantum.install.python): consente di combinare Python e Q# per creare un programma host Python che chiama le operazioni Q#.

[Sviluppare con Q# e .NET](xref:microsoft.quantum.install.cs): combinare C#, F# o VB.NET con Q# per creare un programma host .NET che chiama le operazioni Q#.