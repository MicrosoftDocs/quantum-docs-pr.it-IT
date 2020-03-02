---
title: Installare Microsoft Quantum Development Kit (QDK)
description: Informazioni su come installare Microsoft Quantum Development Kit per ambienti C#, Python e Jupyter Notebook.
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 5fafb736f34d27f9233370a0a8a66c0613606048
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904775"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="7487f-103">Installare Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="7487f-103">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="7487f-104">Informazioni su come installare il Microsoft Quantum Development Kit (QDK), per iniziare a sviluppare con la programmazione quantistica.</span><span class="sxs-lookup"><span data-stu-id="7487f-104">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="7487f-105">Contenuto del QDK:</span><span class="sxs-lookup"><span data-stu-id="7487f-105">The QDK consists of:</span></span>

- <span data-ttu-id="7487f-106">linguaggio di programmazione Q#</span><span class="sxs-lookup"><span data-stu-id="7487f-106">the Q# programming language</span></span>
- <span data-ttu-id="7487f-107">set di librerie che estrapolano le funzionalità complesse in Q#</span><span class="sxs-lookup"><span data-stu-id="7487f-107">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="7487f-108">API per linguaggi Python e .NET (C#, F# e VB.NET) per l'esecuzione di programmi quantistici scritti in Q#</span><span class="sxs-lookup"><span data-stu-id="7487f-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="7487f-109">strumenti per facilitare lo sviluppo</span><span class="sxs-lookup"><span data-stu-id="7487f-109">tools to facilitate your development</span></span>

<span data-ttu-id="7487f-110">I programmi Q# sono spesso associati a un programma host scritto in un linguaggio .NET, in genere C#, o Python.</span><span class="sxs-lookup"><span data-stu-id="7487f-110">Q# programs are often paired with a host program written in a .NET language (typically C#) or Python.</span></span> <span data-ttu-id="7487f-111">In questo modo è possibile chiamare le operazioni quantistiche dall'interno di un programma classico.</span><span class="sxs-lookup"><span data-stu-id="7487f-111">This allows us to call quantum operations from inside a classical program.</span></span>
<span data-ttu-id="7487f-112">Inoltre, QDK fornisce il supporto Q# per Jupyter Notebook con il kernel di Jupyter IQ#.</span><span class="sxs-lookup"><span data-stu-id="7487f-112">In addition, the QDK provides Q# support for Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>

<span data-ttu-id="7487f-113">QDK è disponibile per più ambienti di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="7487f-113">The QDK is available for multiple development environments.</span></span> <span data-ttu-id="7487f-114">Selezionare la configurazione preferita dalle sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7487f-114">Select your preferred setup from the sections below:</span></span>

- <span data-ttu-id="7487f-115">[Installare Q# per C#:](xref:microsoft.quantum.install.cs) scegliere questo ambiente se si desidera combinare C# e Q# per creare un programma host C# che chiama le operazioni Q#.</span><span class="sxs-lookup"><span data-stu-id="7487f-115">[Install Q# for C#:](xref:microsoft.quantum.install.cs) choose this environment if you want to combine C# and Q# to create a C# host program that calls Q# operations.</span></span>
- <span data-ttu-id="7487f-116">[Installare Q# per Python:](xref:microsoft.quantum.install.python) scegliere questo ambiente se si desidera combinare Python e Q# per creare un programma host Python che chiama le operazioni Q#.</span><span class="sxs-lookup"><span data-stu-id="7487f-116">[Install Q# for Python:](xref:microsoft.quantum.install.python) choose this environment if you want to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>
- <span data-ttu-id="7487f-117">[Installare Q# per Jupyter Notebook:](xref:microsoft.quantum.install.jupyter) scegliere questo ambiente per eseguire il codice Q# nelle celle con testo incorporato o creare esercitazioni interattive sul calcolo quantistico.</span><span class="sxs-lookup"><span data-stu-id="7487f-117">[Install Q# for Jupyter Notebooks:](xref:microsoft.quantum.install.jupyter) choose this environment to execute Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> <span data-ttu-id="7487f-118">Non scegliere questo ambiente se si vuole combinare Q# con un programma host classico esterno.</span><span class="sxs-lookup"><span data-stu-id="7487f-118">Do not choose this environment if you want to combine Q# with an external classical host program.</span></span>
