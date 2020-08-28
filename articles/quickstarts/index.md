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
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="50b3d-103">Installare Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="50b3d-103">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="50b3d-104">Informazioni su come installare il Microsoft Quantum Development Kit (QDK), per iniziare a sviluppare con la programmazione quantistica.</span><span class="sxs-lookup"><span data-stu-id="50b3d-104">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="50b3d-105">Contenuto del QDK:</span><span class="sxs-lookup"><span data-stu-id="50b3d-105">The QDK consists of:</span></span>

- <span data-ttu-id="50b3d-106">Linguaggio di programmazione Q#</span><span class="sxs-lookup"><span data-stu-id="50b3d-106">The Q# programming language</span></span>
- <span data-ttu-id="50b3d-107">Set di librerie che estrapolano funzionalità complesse in Q#</span><span class="sxs-lookup"><span data-stu-id="50b3d-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="50b3d-108">API per linguaggi Python e .NET (C#, F# e VB.NET) per l'esecuzione di programmi quantistici scritti in Q#</span><span class="sxs-lookup"><span data-stu-id="50b3d-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="50b3d-109">Strumenti per facilitare lo sviluppo</span><span class="sxs-lookup"><span data-stu-id="50b3d-109">Tools to facilitate your development</span></span>

<span data-ttu-id="50b3d-110">I programmi Q# possono essere eseguiti come applicazioni autonome usando Visual Studio Code o Visual Studio o tramite Jupyter Notebook con il kernel Jupyter IQ#.</span><span class="sxs-lookup"><span data-stu-id="50b3d-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, or through Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>
<span data-ttu-id="50b3d-111">Possono anche essere abbinati a un programma host scritto in un linguaggio .NET (in genere C#) o Python, per permettere la chiamata di operazioni quantistiche dall'interno di un programma classico.</span><span class="sxs-lookup"><span data-stu-id="50b3d-111">They can also be paired with a host program written in a .NET language (typically C#) or Python, enabling you to call quantum operations from inside a classical program.</span></span>

<span data-ttu-id="50b3d-112">I flussi di lavoro per ognuna di queste configurazioni vengono descritti e confrontati in [Modalità di esecuzione di programmi Q#](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="50b3d-112">The workflows for each of these setups are described and compared at [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

<span data-ttu-id="50b3d-113">Per procedere con l'installazione di QDK e la creazione di progetti Q#, selezionare la configurazione preferita:</span><span class="sxs-lookup"><span data-stu-id="50b3d-113">To proceed with installing the QDK and creating Q# projects, select your preferred setup:</span></span>

<span data-ttu-id="50b3d-114">[Sviluppare con applicazioni in Q#](xref:microsoft.quantum.install.standalone): scegliere questo approccio per usare Q# dal prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="50b3d-114">[Develop with Q# applications](xref:microsoft.quantum.install.standalone) - Choose this approach to work with Q# from the command prompt.</span></span> <span data-ttu-id="50b3d-115">Non è necessario un driver o un programma host come per le opzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="50b3d-115">This does not require a driver or a host program like the below options.</span></span>

<span data-ttu-id="50b3d-116">[Sviluppare con notebook di Jupyter Q#](xref:microsoft.quantum.install.jupyter): selezionare questo ambiente per eseguire il codice Q# nelle celle con testo incorporato o creare esercitazioni interattive sul calcolo quantistico.</span><span class="sxs-lookup"><span data-stu-id="50b3d-116">[Develop with Q# Jupyter Notebooks](xref:microsoft.quantum.install.jupyter) - Select this environment to run Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> 

<span data-ttu-id="50b3d-117">[Sviluppare con Q# e Python](xref:microsoft.quantum.install.python): consente di combinare Python e Q# per creare un programma host Python che chiama le operazioni Q#.</span><span class="sxs-lookup"><span data-stu-id="50b3d-117">[Develop with Q# and Python](xref:microsoft.quantum.install.python) - Enables you to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>

<span data-ttu-id="50b3d-118">[Sviluppare con Q# e .NET](xref:microsoft.quantum.install.cs): consente di combinare C#, F# o VB.NET con Q# per creare un programma host .NET che chiama le operazioni Q#.</span><span class="sxs-lookup"><span data-stu-id="50b3d-118">[Develop with Q# and .NET](xref:microsoft.quantum.install.cs) - Combine C#, F#, or VB.NET with Q# to create a .NET host program that calls Q# operations.</span></span>
