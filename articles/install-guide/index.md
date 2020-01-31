---
title: Informazioni su come installare Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: b209f0b600d973c3870c66060e1b484ec519322f
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820709"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="a5a34-102">Installare Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="a5a34-102">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="a5a34-103">Informazioni su come installare il Microsoft Quantum Development Kit (QDK), per iniziare a sviluppare con la programmazione quantistica.</span><span class="sxs-lookup"><span data-stu-id="a5a34-103">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="a5a34-104">Contenuto del QDK:</span><span class="sxs-lookup"><span data-stu-id="a5a34-104">The QDK consists of:</span></span>

- <span data-ttu-id="a5a34-105">linguaggio di programmazione Q#</span><span class="sxs-lookup"><span data-stu-id="a5a34-105">the Q# programming language</span></span>
- <span data-ttu-id="a5a34-106">set di librerie che estrapolano le funzionalità complesse in Q#</span><span class="sxs-lookup"><span data-stu-id="a5a34-106">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="a5a34-107">API per i linguaggi Python e .NET (ad esempio: C#, F# e VB.NET) per l'esecuzione di programmi quantistici scritti in Q#</span><span class="sxs-lookup"><span data-stu-id="a5a34-107">APIs for Python and .NET languages (i.e.: C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="a5a34-108">strumenti per facilitare lo sviluppo</span><span class="sxs-lookup"><span data-stu-id="a5a34-108">tools to facilitate your development</span></span>

<span data-ttu-id="a5a34-109">I programmi Q# sono spesso associati a un programma host scritto in un linguaggio .NET, in genere C#, o Python.</span><span class="sxs-lookup"><span data-stu-id="a5a34-109">Q# programs are often paired with a host program written in a .NET language (typically C#) or Python.</span></span> <span data-ttu-id="a5a34-110">In questo modo è possibile chiamare le operazioni quantistiche dall'interno di un programma classico.</span><span class="sxs-lookup"><span data-stu-id="a5a34-110">This allows us to call quantum operations from inside a classical program.</span></span>
<span data-ttu-id="a5a34-111">Inoltre, QDK fornisce il supporto Q# per Jupyter Notebook con il kernel di Jupyter IQ#.</span><span class="sxs-lookup"><span data-stu-id="a5a34-111">In addition, the QDK provides Q# support for Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>

<span data-ttu-id="a5a34-112">QDK è disponibile per più ambienti di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="a5a34-112">The QDK is available for multiple development environments.</span></span> <span data-ttu-id="a5a34-113">Selezionare la configurazione preferita dalle sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a5a34-113">Select your preferred setup from the sections below:</span></span>

- <span data-ttu-id="a5a34-114">[Installare Q# per C#:](xref:microsoft.quantum.install.cs) scegliere questo ambiente se si desidera combinare C# e Q# per creare un programma host C# che chiama le operazioni Q#.</span><span class="sxs-lookup"><span data-stu-id="a5a34-114">[Install Q# for C#:](xref:microsoft.quantum.install.cs) choose this environment if you want to combine C# and Q# to create a C# host program that calls Q# operations.</span></span>
- <span data-ttu-id="a5a34-115">[Installare Q# per Python:](xref:microsoft.quantum.install.python) scegliere questo ambiente se si desidera combinare Python e Q# per creare un programma host Python che chiama le operazioni Q#.</span><span class="sxs-lookup"><span data-stu-id="a5a34-115">[Install Q# for Python:](xref:microsoft.quantum.install.python) choose this environment if you want to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>
- <span data-ttu-id="a5a34-116">[Installare Q# per Jupyter Notebook:](xref:microsoft.quantum.install.jupyter) scegliere questo ambiente per eseguire il codice Q# nelle celle con testo incorporato o creare esercitazioni interattive sul calcolo quantistico.</span><span class="sxs-lookup"><span data-stu-id="a5a34-116">[Install Q# for Jupyter Notebooks:](xref:microsoft.quantum.install.jupyter) choose this environment to execute Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> <span data-ttu-id="a5a34-117">Non scegliere questo ambiente se si vuole combinare Q# con un programma host classico esterno.</span><span class="sxs-lookup"><span data-stu-id="a5a34-117">Do not choose this environment if you want to combine Q# with an external classical host program.</span></span>
