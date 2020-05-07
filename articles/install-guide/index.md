---
title: Informazioni su come installare Microsoft Quantum Development Kit (QDK)
description: Informazioni su come installare Microsoft Quantum Development Kit per ambienti C#, Python e Jupyter Notebook.
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: bca700660094b91f1c0dfa03f9bce1336073ca51
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/01/2020
ms.locfileid: "82680183"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>Installare Microsoft Quantum Development Kit (QDK)

Informazioni su come installare il Microsoft Quantum Development Kit (QDK), per iniziare a sviluppare con la programmazione quantistica. Contenuto del QDK:

- linguaggio di programmazione Q#
- set di librerie che estrapolano le funzionalità complesse in Q#
- API per linguaggi Python e .NET (C#, F# e VB.NET) per l'esecuzione di programmi quantistici scritti in Q#
- strumenti per facilitare lo sviluppo

I programmi Q# sono spesso associati a un programma host scritto in un linguaggio .NET, in genere C#, o Python. In questo modo è possibile chiamare le operazioni quantistiche dall'interno di un programma classico.
Inoltre, QDK fornisce il supporto Q# per Jupyter Notebook con il kernel di Jupyter IQ#.

QDK è disponibile per più ambienti di sviluppo. Selezionare la configurazione preferita dalle sezioni seguenti:

- [Applicazione della riga di comando di Q#:](xref:microsoft.quantum.install.standalone) scegliere questo approccio se si vuole usare Q# dalla riga di comando. Non è necessario un driver o un programma host come per le opzioni seguenti.
- [Installare Q# per Jupyter Notebook:](xref:microsoft.quantum.install.jupyter) scegliere questo ambiente per eseguire il codice Q# nelle celle con testo incorporato o creare esercitazioni interattive sul calcolo quantistico. 
- [Sviluppare con Q# e Python:](xref:microsoft.quantum.install.python) scegliere questo ambiente se si vuole combinare Python e Q# per creare un programma host Python che chiama le operazioni Q#.
- [Sviluppare con Q# e C# o F#:](xref:microsoft.quantum.install.cs) scegliere questo ambiente se si vuole combinare C# o F# e Q# per creare un programma host .NET che chiama le operazioni Q#.
