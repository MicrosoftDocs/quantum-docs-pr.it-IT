---
title: Configurazione del kit di sviluppo Microsoft Quantum (QDK)
description: Informazioni su come configurare il kit di sviluppo Microsoft Quantum per ambienti diversi.
author: bradben
ms.author: v-benbra
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: f0c3df1998f9b64ff6544867b83a7afe52b6f46d
ms.sourcegitcommit: fd57a845d013ae4578715d04b1ed1edc1c8ff6b4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2020
ms.locfileid: "94870822"
---
# <a name="setting-up-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="13470-103">Configurazione del kit di sviluppo Microsoft Quantum (QDK)</span><span class="sxs-lookup"><span data-stu-id="13470-103">Setting up the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="13470-104">Informazioni su come configurare il kit di sviluppo Microsoft Quantum (QDK) per l'ambiente, per iniziare a sviluppare con la programmazione quantistica.</span><span class="sxs-lookup"><span data-stu-id="13470-104">Learn how to set up the Microsoft Quantum Development Kit (QDK) for your environment, so that you can get started with quantum programming.</span></span> <span data-ttu-id="13470-105">Contenuto del QDK:</span><span class="sxs-lookup"><span data-stu-id="13470-105">The QDK consists of:</span></span>

- <span data-ttu-id="13470-106">Linguaggio di programmazione Q#</span><span class="sxs-lookup"><span data-stu-id="13470-106">The Q# programming language</span></span>
- <span data-ttu-id="13470-107">Set di librerie che estrapolano funzionalità complesse in Q#</span><span class="sxs-lookup"><span data-stu-id="13470-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="13470-108">API per linguaggi Python e .NET (C#, F# e VB.NET) per l'esecuzione di programmi quantistici scritti in Q#</span><span class="sxs-lookup"><span data-stu-id="13470-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="13470-109">Strumenti per facilitare lo sviluppo</span><span class="sxs-lookup"><span data-stu-id="13470-109">Tools to facilitate your development</span></span>

<span data-ttu-id="13470-110">I programmi Q# possono essere eseguiti come applicazioni autonome usando Visual Studio Code o Visual Studio, tramite notebook di Jupyter con il kernel Jupyter IQ# oppure abbinati a un programma host scritto in Python o in un linguaggio .NET (C#, F#).</span><span class="sxs-lookup"><span data-stu-id="13470-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, through Jupyter Notebooks with the IQ# Jupyter kernel, or paired with a host program written in Python or a .NET language (C#, F#).</span></span> <span data-ttu-id="13470-111">È anche possibile eseguire i programmi Q# online usando [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/) o [Docker](#use-the-qdk-with-docker).</span><span class="sxs-lookup"><span data-stu-id="13470-111">You can also run Q# programs online using [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/), or [Docker](#use-the-qdk-with-docker).</span></span> 

## <a name="options-for-setting-up-the-qdk"></a><span data-ttu-id="13470-112">Opzioni per la configurazione del QDK</span><span class="sxs-lookup"><span data-stu-id="13470-112">Options for setting up the QDK</span></span>

<span data-ttu-id="13470-113">È possibile usare il QDK in tre modi:</span><span class="sxs-lookup"><span data-stu-id="13470-113">You can use the QDK in three ways:</span></span>

- [<span data-ttu-id="13470-114">Installare il QDK in locale</span><span class="sxs-lookup"><span data-stu-id="13470-114">Install the QDK locally</span></span>](#install-the-qdk-locally)
- [<span data-ttu-id="13470-115">Usare il QDK online</span><span class="sxs-lookup"><span data-stu-id="13470-115">Use the QDK online</span></span>](#use-the-qdk-online)
- [<span data-ttu-id="13470-116">Usare un'immagine Docker del QDK</span><span class="sxs-lookup"><span data-stu-id="13470-116">Use a QDK Docker image</span></span>](#use-the-qdk-with-docker)

## <a name="install-the-qdk-locally"></a><span data-ttu-id="13470-117">Installare il QDK in locale</span><span class="sxs-lookup"><span data-stu-id="13470-117">Install the QDK locally</span></span>

<span data-ttu-id="13470-118">È possibile sviluppare codice Q# nella maggior parte degli IDE preferiti, nonché integrare Q# con altri linguaggi, ad esempio Python e .NET (C#, F#).</span><span class="sxs-lookup"><span data-stu-id="13470-118">You can develop Q# code in most of your favorites IDEs, as well as integrate Q# with other languages such as Python and .NET (C#, F#).</span></span>

<table>
    <tr>
        <th width=10%>&nbsp;</th>
        <th>&nbsp;</th>
        <th align="center" width=18%><img src="~/media/vs_code.png" alt="VS Code" width="50"/><br><span data-ttu-id="13470-119"><b>Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="13470-119"><b>VS Code</span></span><br><span data-ttu-id="13470-120">(2019 o versione successiva)</b></span><span class="sxs-lookup"><span data-stu-id="13470-120">(2019 or later)</b></span></span></th>
        <th align="center" width=18%><img src="~/media/vs_studio.png" alt="VS Studio" width="50"/><br><span data-ttu-id="13470-121"><b>VS Studio</span><span class="sxs-lookup"><span data-stu-id="13470-121"><b>VS Studio</span></span><br><span data-ttu-id="13470-122">(2019 o versione successiva)</b></span><span class="sxs-lookup"><span data-stu-id="13470-122">(2019 or later)</b></span></span></th>
        <th align="center" width=18%><img src="~/media/jupyter-wht.png" alt="jupyter install" width="65"/><br><span data-ttu-id="13470-123"><b>Jupyter Notebook</b></span><span class="sxs-lookup"><span data-stu-id="13470-123"><b>Jupyter Notebooks</b></span></span></th>
        <th align="center" width=18%><img src="~/media/blank.png" alt="blank spacer" width="65"/><br><span data-ttu-id="13470-124"><b>Riga di comando</b></span><span class="sxs-lookup"><span data-stu-id="13470-124"><b>Command line</b></span></span></th>
    </tr>
    <tr>
        <th>&nbsp;</th>
        <td align="left"><span data-ttu-id="13470-125"><b>Supporto sistema operativo</b></span><span class="sxs-lookup"><span data-stu-id="13470-125"><b>OS support:</b></span></span></td>
        <td align="center"><span data-ttu-id="13470-126">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="13470-126">Windows, macOS, Linux</span></span></td>
        <td align="center"><span data-ttu-id="13470-127">Solo Windows</span><span class="sxs-lookup"><span data-stu-id="13470-127">Windows only</span></span></td>
        <td align="center"><span data-ttu-id="13470-128">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="13470-128">Windows, macOS, Linux</span></span></td>
        <td align="center"><span data-ttu-id="13470-129">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="13470-129">Windows, macOS, Linux</span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/quantum-wht.png" alt="QDK" width="60"/></td>
        <td align="left"><span data-ttu-id="13470-130"><b>Q# autonomo</b></span><span class="sxs-lookup"><span data-stu-id="13470-130"><b>Q# standalone</b></span></span></td>
        <td align="center"><span data-ttu-id="13470-131"><a href="xref:microsoft.quantum.install.standalone">Installazione</a></span><span class="sxs-lookup"><span data-stu-id="13470-131"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="13470-132"><a href="xref:microsoft.quantum.install.standalone">Installazione</a></span><span class="sxs-lookup"><span data-stu-id="13470-132"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="13470-133"><a href="xref:microsoft.quantum.install.jupyter">Installazione</a></span><span class="sxs-lookup"><span data-stu-id="13470-133"><a href="xref:microsoft.quantum.install.jupyter">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="13470-134"><a href="xref:microsoft.quantum.install.standalone">Installazione</a></span><span class="sxs-lookup"><span data-stu-id="13470-134"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/python.png" alt="python install" width="50"/></td>
        <td align="left"><span data-ttu-id="13470-135"><b>Q# e Python</b></span><span class="sxs-lookup"><span data-stu-id="13470-135"><b>Q# and Python</b></span></span></td>
        <td align="center"><span data-ttu-id="13470-136"><a href="xref:microsoft.quantum.install.python">Installazione</a></span><span class="sxs-lookup"><span data-stu-id="13470-136"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="13470-137"><a href="xref:microsoft.quantum.install.python">Installazione</a></span><span class="sxs-lookup"><span data-stu-id="13470-137"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="13470-138"><a href="xref:microsoft.quantum.install.jupyter">Installazione</a></span><span class="sxs-lookup"><span data-stu-id="13470-138"><a href="xref:microsoft.quantum.install.jupyter">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="13470-139"><a href="xref:microsoft.quantum.install.python">Installazione</a></span><span class="sxs-lookup"><span data-stu-id="13470-139"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/dot_net.png" alt="dotnet install" width="50"/></td>
        <td align="left"><span data-ttu-id="13470-140"><b>Q# e .NET (C#, F#)</b></span><span class="sxs-lookup"><span data-stu-id="13470-140"><b>Q# and .NET (C#, F#)</b></span></span></td> 
        <td align="center"><span data-ttu-id="13470-141"><a href="xref:microsoft.quantum.install.cs">Installazione</a></span><span class="sxs-lookup"><span data-stu-id="13470-141"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="13470-142"><a href="xref:microsoft.quantum.install.cs">Installazione</a></span><span class="sxs-lookup"><span data-stu-id="13470-142"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="13470-143">&#10006;</span><span class="sxs-lookup"><span data-stu-id="13470-143">&#10006;</span></span></td>
        <td align="center"><span data-ttu-id="13470-144"><a href="xref:microsoft.quantum.install.cs">Installazione</a></span><span class="sxs-lookup"><span data-stu-id="13470-144"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
   </tr>
</table>

## <a name="use-the-qdk-online"></a><span data-ttu-id="13470-145">Usare il QDK online</span><span class="sxs-lookup"><span data-stu-id="13470-145">Use the QDK Online</span></span>

<span data-ttu-id="13470-146">È anche possibile sviluppare codice Q# senza installare niente in locale con queste opzioni:</span><span class="sxs-lookup"><span data-stu-id="13470-146">You can also develop Q# code without installing anything locally with these options:</span></span>

|<span data-ttu-id="13470-147">Risorsa</span><span class="sxs-lookup"><span data-stu-id="13470-147">Resource</span></span>|<span data-ttu-id="13470-148">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="13470-148">Advantages</span></span>|<span data-ttu-id="13470-149">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="13470-149">Limitations</span></span>|
|---|---|---|
|[<span data-ttu-id="13470-150">**Visual Studio Codespaces**</span><span class="sxs-lookup"><span data-stu-id="13470-150">**Visual Studio Codespaces**</span></span>](xref:microsoft.quantum.install.standalone)|<span data-ttu-id="13470-151">Un ambiente di sviluppo online avanzato</span><span class="sxs-lookup"><span data-stu-id="13470-151">A rich online development environment</span></span>  |<span data-ttu-id="13470-152">Richiede una sottoscrizione e un piano di Azure</span><span class="sxs-lookup"><span data-stu-id="13470-152">Requires an Azure subscription and plan</span></span> |
|[<span data-ttu-id="13470-153">**Binder**</span><span class="sxs-lookup"><span data-stu-id="13470-153">**Binder**</span></span>](xref:microsoft.quantum.install.binder) | <span data-ttu-id="13470-154">Esperienza gratuita di notebook online</span><span class="sxs-lookup"><span data-stu-id="13470-154">Free online notebook experience</span></span> |<span data-ttu-id="13470-155">Nessuna persistenza</span><span class="sxs-lookup"><span data-stu-id="13470-155">No persistence</span></span> |

## <a name="use-the-qdk-with-docker"></a><span data-ttu-id="13470-156">Usare il QDK con Docker</span><span class="sxs-lookup"><span data-stu-id="13470-156">Use the QDK with Docker</span></span>

<span data-ttu-id="13470-157">È possibile usare l'immagine Docker del QDK nell'installazione locale di Docker o nel cloud tramite qualsiasi servizio che supporti immagini Docker, ad esempio Istanze di Azure Container.</span><span class="sxs-lookup"><span data-stu-id="13470-157">You can use our QDK Docker image in your local Docker installation or in the cloud via any service that supports Docker images, such as ACI.</span></span>

<span data-ttu-id="13470-158">È possibile scaricare l'immagine Docker IQ# da https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span><span class="sxs-lookup"><span data-stu-id="13470-158">You can download the IQ# Docker image from https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span></span> 

<span data-ttu-id="13470-159">È anche possibile usare Docker con un contenitore di sviluppo remoto di Visual Studio Code per definire rapidamente gli ambienti di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="13470-159">You can also use Docker with a Visual Studio Code Remote Development Container to quickly define development environments.</span></span> <span data-ttu-id="13470-160">Per altre informazioni sui contenitori di sviluppo di VS Code, vedere https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span><span class="sxs-lookup"><span data-stu-id="13470-160">For more information about VS Code Development Containers, see https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span></span>

## <a name="next-steps"></a><span data-ttu-id="13470-161">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="13470-161">Next steps</span></span>

<span data-ttu-id="13470-162">I flussi di lavoro per ognuna di queste configurazioni vengono descritti e confrontati in [Modalità di esecuzione di programmi Q#](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="13470-162">The workflows for each of these setups are described and compared at [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>
