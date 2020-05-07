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
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="167c4-103">Installare Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="167c4-103">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="167c4-104">Informazioni su come installare il Microsoft Quantum Development Kit (QDK), per iniziare a sviluppare con la programmazione quantistica.</span><span class="sxs-lookup"><span data-stu-id="167c4-104">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="167c4-105">Contenuto del QDK:</span><span class="sxs-lookup"><span data-stu-id="167c4-105">The QDK consists of:</span></span>

- <span data-ttu-id="167c4-106">linguaggio di programmazione Q#</span><span class="sxs-lookup"><span data-stu-id="167c4-106">the Q# programming language</span></span>
- <span data-ttu-id="167c4-107">set di librerie che estrapolano le funzionalità complesse in Q#</span><span class="sxs-lookup"><span data-stu-id="167c4-107">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="167c4-108">API per linguaggi Python e .NET (C#, F# e VB.NET) per l'esecuzione di programmi quantistici scritti in Q#</span><span class="sxs-lookup"><span data-stu-id="167c4-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="167c4-109">strumenti per facilitare lo sviluppo</span><span class="sxs-lookup"><span data-stu-id="167c4-109">tools to facilitate your development</span></span>

<span data-ttu-id="167c4-110">I programmi Q# sono spesso associati a un programma host scritto in un linguaggio .NET, in genere C#, o Python.</span><span class="sxs-lookup"><span data-stu-id="167c4-110">Q# programs are often paired with a host program written in a .NET language (typically C#) or Python.</span></span> <span data-ttu-id="167c4-111">In questo modo è possibile chiamare le operazioni quantistiche dall'interno di un programma classico.</span><span class="sxs-lookup"><span data-stu-id="167c4-111">This allows us to call quantum operations from inside a classical program.</span></span>
<span data-ttu-id="167c4-112">Inoltre, QDK fornisce il supporto Q# per Jupyter Notebook con il kernel di Jupyter IQ#.</span><span class="sxs-lookup"><span data-stu-id="167c4-112">In addition, the QDK provides Q# support for Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>

<span data-ttu-id="167c4-113">QDK è disponibile per più ambienti di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="167c4-113">The QDK is available for multiple development environments.</span></span> <span data-ttu-id="167c4-114">Selezionare la configurazione preferita dalle sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="167c4-114">Select your preferred setup from the sections below:</span></span>

- <span data-ttu-id="167c4-115">[Applicazione della riga di comando di Q#:](xref:microsoft.quantum.install.standalone) scegliere questo approccio se si vuole usare Q# dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="167c4-115">[Q# command line application:](xref:microsoft.quantum.install.standalone) choose this approach if you want to work with Q# from the command line.</span></span> <span data-ttu-id="167c4-116">Non è necessario un driver o un programma host come per le opzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="167c4-116">This does not require a driver or a host program like the below options.</span></span>
- <span data-ttu-id="167c4-117">[Installare Q# per Jupyter Notebook:](xref:microsoft.quantum.install.jupyter) scegliere questo ambiente per eseguire il codice Q# nelle celle con testo incorporato o creare esercitazioni interattive sul calcolo quantistico.</span><span class="sxs-lookup"><span data-stu-id="167c4-117">[Install Q# for Jupyter Notebooks:](xref:microsoft.quantum.install.jupyter) choose this environment to execute Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> 
- <span data-ttu-id="167c4-118">[Sviluppare con Q# e Python:](xref:microsoft.quantum.install.python) scegliere questo ambiente se si vuole combinare Python e Q# per creare un programma host Python che chiama le operazioni Q#.</span><span class="sxs-lookup"><span data-stu-id="167c4-118">[Develop with Q# and Python:](xref:microsoft.quantum.install.python) if you want to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>
- <span data-ttu-id="167c4-119">[Sviluppare con Q# e C# o F#:](xref:microsoft.quantum.install.cs) scegliere questo ambiente se si vuole combinare C# o F# e Q# per creare un programma host .NET che chiama le operazioni Q#.</span><span class="sxs-lookup"><span data-stu-id="167c4-119">[Develop with Q# and C# or F#:](xref:microsoft.quantum.install.cs) if you want to combine C# or F# and Q# to create a .NET host program that calls Q# operations.</span></span>
