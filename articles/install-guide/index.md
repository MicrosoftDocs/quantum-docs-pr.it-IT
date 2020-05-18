---
title: Installare Microsoft Quantum Development Kit (QDK)
description: Come installare Microsoft Quantum Development Kit per ambienti diversi.
author: natke
ms.author: nakersha
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 2041b90ba021b7640615d73c35841cc21f025ac0
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426463"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="c0a83-103">Installare Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="c0a83-103">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="c0a83-104">Informazioni su come installare il Microsoft Quantum Development Kit (QDK), per iniziare a sviluppare con la programmazione quantistica.</span><span class="sxs-lookup"><span data-stu-id="c0a83-104">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="c0a83-105">Contenuto del QDK:</span><span class="sxs-lookup"><span data-stu-id="c0a83-105">The QDK consists of:</span></span>

- <span data-ttu-id="c0a83-106">Linguaggio di programmazione Q#</span><span class="sxs-lookup"><span data-stu-id="c0a83-106">The Q# programming language</span></span>
- <span data-ttu-id="c0a83-107">Set di librerie che estrapolano funzionalità complesse in Q#</span><span class="sxs-lookup"><span data-stu-id="c0a83-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="c0a83-108">API per linguaggi Python e .NET (C#, F# e VB.NET) per l'esecuzione di programmi quantistici scritti in Q#</span><span class="sxs-lookup"><span data-stu-id="c0a83-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="c0a83-109">Strumenti per facilitare lo sviluppo</span><span class="sxs-lookup"><span data-stu-id="c0a83-109">Tools to facilitate your development</span></span>

<span data-ttu-id="c0a83-110">I programmi Q# possono essere eseguiti come applicazioni autonome usando Visual Studio Code o Visual Studio o tramite Jupyter Notebook con il kernel Jupyter IQ#.</span><span class="sxs-lookup"><span data-stu-id="c0a83-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, or through Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>

<span data-ttu-id="c0a83-111">Possono anche essere abbinati a un programma host scritto in un linguaggio .NET (in genere C#) o Python, per permettere la chiamata di operazioni quantistiche dall'interno di un programma classico.</span><span class="sxs-lookup"><span data-stu-id="c0a83-111">They can also be paired with a host program written in a .NET language (typically C#) or Python, enabling you to call quantum operations from inside a classical program.</span></span>

<span data-ttu-id="c0a83-112">QDK è disponibile per più ambienti di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="c0a83-112">The QDK is available for multiple development environments.</span></span> <span data-ttu-id="c0a83-113">Selezionare la configurazione preferita tra le seguenti:</span><span class="sxs-lookup"><span data-stu-id="c0a83-113">Select your preferred setup from:</span></span>

<span data-ttu-id="c0a83-114">[**Sviluppare con applicazioni della riga di comando di Q#** ](xref:microsoft.quantum.install.standalone): scegliere questo approccio per usare Q# dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="c0a83-114">[**Develop with Q# command line applications**](xref:microsoft.quantum.install.standalone) - Choose this approach to work with Q# from the command line.</span></span> <span data-ttu-id="c0a83-115">Non è necessario un driver o un programma host come per le opzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="c0a83-115">This does not require a driver or a host program like the below options.</span></span>

<span data-ttu-id="c0a83-116">[**Sviluppare con Jupyter Notebook Q#** ](xref:microsoft.quantum.install.jupyter): selezionare questo ambiente per eseguire il codice Q# nelle celle con testo incorporato o creare esercitazioni interattive sul calcolo quantistico.</span><span class="sxs-lookup"><span data-stu-id="c0a83-116">[**Develop with Q# Jupyter Notebooks**](xref:microsoft.quantum.install.jupyter) - Select this environment to run Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> 

<span data-ttu-id="c0a83-117">[**Sviluppare con Q# e Python**](xref:microsoft.quantum.install.python): consente di combinare Python e Q# per creare un programma host Python che chiama le operazioni Q#.</span><span class="sxs-lookup"><span data-stu-id="c0a83-117">[**Develop with Q# and Python**](xref:microsoft.quantum.install.python) - Enables you to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>

<span data-ttu-id="c0a83-118">[**Sviluppare con Q# e .NET**](xref:microsoft.quantum.install.cs): combinare C#, F# o VB.NET con Q# per creare un programma host .NET che chiama le operazioni Q#.</span><span class="sxs-lookup"><span data-stu-id="c0a83-118">[**Develop with Q# and .NET**](xref:microsoft.quantum.install.cs) - Combine C#, F#, or VB.NET with Q# to create a .NET host program that calls Q# operations.</span></span>
