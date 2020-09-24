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
ms.openlocfilehash: 74b9b3d8f694072f5b5f4d0eb520263387de8919
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834483"
---
# <a name="setting-up-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="f53eb-103">Configurazione del kit di sviluppo Microsoft Quantum (QDK)</span><span class="sxs-lookup"><span data-stu-id="f53eb-103">Setting up the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="f53eb-104">Informazioni su come configurare il kit di sviluppo Microsoft Quantum (QDK) per l'ambiente, per iniziare a sviluppare con la programmazione quantistica.</span><span class="sxs-lookup"><span data-stu-id="f53eb-104">Learn how to set up the Microsoft Quantum Development Kit (QDK) for your environment, so that you can get started with quantum programming.</span></span> <span data-ttu-id="f53eb-105">Contenuto del QDK:</span><span class="sxs-lookup"><span data-stu-id="f53eb-105">The QDK consists of:</span></span>

- <span data-ttu-id="f53eb-106">Linguaggio di programmazione Q#</span><span class="sxs-lookup"><span data-stu-id="f53eb-106">The Q# programming language</span></span>
- <span data-ttu-id="f53eb-107">Set di librerie che estrapolano funzionalità complesse in Q#</span><span class="sxs-lookup"><span data-stu-id="f53eb-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="f53eb-108">API per linguaggi Python e .NET (C#, F# e VB.NET) per l'esecuzione di programmi quantistici scritti in Q#</span><span class="sxs-lookup"><span data-stu-id="f53eb-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="f53eb-109">Strumenti per facilitare lo sviluppo</span><span class="sxs-lookup"><span data-stu-id="f53eb-109">Tools to facilitate your development</span></span>

<span data-ttu-id="f53eb-110">I programmi Q# possono essere eseguiti come applicazioni autonome usando Visual Studio Code o Visual Studio, tramite notebook di Jupyter con il kernel Jupyter IQ# oppure abbinati a un programma host scritto in Python o in un linguaggio .NET (C#, F#).</span><span class="sxs-lookup"><span data-stu-id="f53eb-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, through Jupyter Notebooks with the IQ# Jupyter kernel, or paired with a host program written in Python or a .NET language (C#, F#).</span></span> <span data-ttu-id="f53eb-111">È anche possibile eseguire i programmi Q# online usando [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/) o [Docker](#use-the-qdk-with-docker).</span><span class="sxs-lookup"><span data-stu-id="f53eb-111">You can also run Q# programs online using [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/), or [Docker](#use-the-qdk-with-docker).</span></span> 

## <a name="options-for-setting-up-the-qdk"></a><span data-ttu-id="f53eb-112">Opzioni per la configurazione del QDK</span><span class="sxs-lookup"><span data-stu-id="f53eb-112">Options for setting up the QDK</span></span>

<span data-ttu-id="f53eb-113">È possibile usare il QDK in tre modi:</span><span class="sxs-lookup"><span data-stu-id="f53eb-113">You can use the QDK in three ways:</span></span>

- [<span data-ttu-id="f53eb-114">Installare il QDK in locale</span><span class="sxs-lookup"><span data-stu-id="f53eb-114">Install the QDK locally</span></span>](#install-the-qdk-locally)
- [<span data-ttu-id="f53eb-115">Usare il QDK online</span><span class="sxs-lookup"><span data-stu-id="f53eb-115">Use the QDK online</span></span>](#use-the-qdk-online)
- [<span data-ttu-id="f53eb-116">Usare un'immagine Docker del QDK</span><span class="sxs-lookup"><span data-stu-id="f53eb-116">Use a QDK Docker image</span></span>](#use-the-qdk-with-docker)

## <a name="install-the-qdk-locally"></a><span data-ttu-id="f53eb-117">Installare il QDK in locale</span><span class="sxs-lookup"><span data-stu-id="f53eb-117">Install the QDK locally</span></span>

<span data-ttu-id="f53eb-118">È possibile sviluppare codice Q# nella maggior parte degli IDE preferiti, nonché integrare Q# con altri linguaggi, ad esempio Python e .NET (C#, F#).</span><span class="sxs-lookup"><span data-stu-id="f53eb-118">You can develop Q# code in most of your favorites IDEs, as well as integrate Q# with other languages such as Python and .NET (C#, F#).</span></span>

|&nbsp; | <span data-ttu-id="f53eb-119">**VS Code<br>(2019 o versione successiva)**</span><span class="sxs-lookup"><span data-stu-id="f53eb-119">**VS Code<br>(2019 or later)**</span></span>| <span data-ttu-id="f53eb-120">**Visual Studio<br>(2019 o versione successiva)**</span><span class="sxs-lookup"><span data-stu-id="f53eb-120">**Visual Studio<br>(2019 or later)**</span></span> | <span data-ttu-id="f53eb-121">**Jupyter Notebook**</span><span class="sxs-lookup"><span data-stu-id="f53eb-121">**Jupyter Notebooks**</span></span> | <span data-ttu-id="f53eb-122">**Riga di comando**</span><span class="sxs-lookup"><span data-stu-id="f53eb-122">**Command line**</span></span>|
|:-----|:-----:|:-----:|:-----:|:-----:|
|<span data-ttu-id="f53eb-123">**Sistema operativo**</span><span class="sxs-lookup"><span data-stu-id="f53eb-123">**OS**</span></span> |<span data-ttu-id="f53eb-124">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="f53eb-124">Windows, macOS, Linux</span></span> |<span data-ttu-id="f53eb-125">Solo Windows</span><span class="sxs-lookup"><span data-stu-id="f53eb-125">Windows only</span></span> |<span data-ttu-id="f53eb-126">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="f53eb-126">Windows, macOS, Linux</span></span> |<span data-ttu-id="f53eb-127">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="f53eb-127">Windows, macOS, Linux</span></span> |
|<br><span data-ttu-id="f53eb-128">**Q# autonomo**</span><span class="sxs-lookup"><span data-stu-id="f53eb-128">**Q# standalone**</span></span> |<br>[<span data-ttu-id="f53eb-129">Installazione</span><span class="sxs-lookup"><span data-stu-id="f53eb-129">Install</span></span>](xref:microsoft.quantum.install.standalone) |<br> [<span data-ttu-id="f53eb-130">Installazione</span><span class="sxs-lookup"><span data-stu-id="f53eb-130">Install</span></span>](xref:microsoft.quantum.install.standalone)  |<br> [<span data-ttu-id="f53eb-131">Installazione</span><span class="sxs-lookup"><span data-stu-id="f53eb-131">Install</span></span>](xref:microsoft.quantum.install.jupyter) |<br>[<span data-ttu-id="f53eb-132">Installazione</span><span class="sxs-lookup"><span data-stu-id="f53eb-132">Install</span></span>](xref:microsoft.quantum.install.standalone)|
|<span data-ttu-id="f53eb-133">**Q# e Python**</span><span class="sxs-lookup"><span data-stu-id="f53eb-133">**Q#  and Python**</span></span> |[<span data-ttu-id="f53eb-134">Installazione</span><span class="sxs-lookup"><span data-stu-id="f53eb-134">Install</span></span>](xref:microsoft.quantum.install.python) |[<span data-ttu-id="f53eb-135">Installazione</span><span class="sxs-lookup"><span data-stu-id="f53eb-135">Install</span></span>](xref:microsoft.quantum.install.python) |[<span data-ttu-id="f53eb-136">Installazione</span><span class="sxs-lookup"><span data-stu-id="f53eb-136">Install</span></span>](xref:microsoft.quantum.install.jupyter) |[<span data-ttu-id="f53eb-137">Installazione</span><span class="sxs-lookup"><span data-stu-id="f53eb-137">Install</span></span>](xref:microsoft.quantum.install.python) |
|<span data-ttu-id="f53eb-138">**Q# e .NET (C#, F#)**</span><span class="sxs-lookup"><span data-stu-id="f53eb-138">**Q# and .NET (C#, F#)**</span></span>|[<span data-ttu-id="f53eb-139">Installazione</span><span class="sxs-lookup"><span data-stu-id="f53eb-139">Install</span></span>](xref:microsoft.quantum.install.cs) |[<span data-ttu-id="f53eb-140">Installazione</span><span class="sxs-lookup"><span data-stu-id="f53eb-140">Install</span></span>](xref:microsoft.quantum.install.cs)|<span data-ttu-id="f53eb-141">&#10006;</span><span class="sxs-lookup"><span data-stu-id="f53eb-141">&#10006;</span></span> |[<span data-ttu-id="f53eb-142">Installazione</span><span class="sxs-lookup"><span data-stu-id="f53eb-142">Install</span></span>](xref:microsoft.quantum.install.cs) |

## <a name="use-the-qdk-online"></a><span data-ttu-id="f53eb-143">Usare il QDK online</span><span class="sxs-lookup"><span data-stu-id="f53eb-143">Use the QDK Online</span></span>

<span data-ttu-id="f53eb-144">È anche possibile sviluppare codice Q# senza installare niente in locale con queste opzioni:</span><span class="sxs-lookup"><span data-stu-id="f53eb-144">You can also develop Q# code without installing anything locally with these options:</span></span>

|<span data-ttu-id="f53eb-145">Risorsa</span><span class="sxs-lookup"><span data-stu-id="f53eb-145">Resource</span></span>|<span data-ttu-id="f53eb-146">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="f53eb-146">Advantages</span></span>|<span data-ttu-id="f53eb-147">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="f53eb-147">Limitations</span></span>|
|---|---|---|
|[<span data-ttu-id="f53eb-148">**Visual Studio Codespaces**</span><span class="sxs-lookup"><span data-stu-id="f53eb-148">**Visual Studio Codespaces**</span></span>](xref:microsoft.quantum.install.standalone)|<span data-ttu-id="f53eb-149">Un ambiente di sviluppo online avanzato</span><span class="sxs-lookup"><span data-stu-id="f53eb-149">A rich online development environment</span></span>  |<span data-ttu-id="f53eb-150">Richiede una sottoscrizione e un piano di Azure</span><span class="sxs-lookup"><span data-stu-id="f53eb-150">Requires an Azure subscription and plan</span></span> |
|[<span data-ttu-id="f53eb-151">**Binder**</span><span class="sxs-lookup"><span data-stu-id="f53eb-151">**Binder**</span></span>](xref:microsoft.quantum.install.binder) | <span data-ttu-id="f53eb-152">Esperienza gratuita di notebook online</span><span class="sxs-lookup"><span data-stu-id="f53eb-152">Free online notebook experience</span></span> |<span data-ttu-id="f53eb-153">Nessuna persistenza</span><span class="sxs-lookup"><span data-stu-id="f53eb-153">No persistence</span></span> |

## <a name="use-the-qdk-with-docker"></a><span data-ttu-id="f53eb-154">Usare il QDK con Docker</span><span class="sxs-lookup"><span data-stu-id="f53eb-154">Use the QDK with Docker</span></span>

<span data-ttu-id="f53eb-155">È possibile usare l'immagine Docker del QDK nell'installazione locale di Docker o nel cloud tramite qualsiasi servizio che supporti immagini Docker, ad esempio Istanze di Azure Container.</span><span class="sxs-lookup"><span data-stu-id="f53eb-155">You can use our QDK Docker image in your local Docker installation or in the cloud via any service that supports Docker images, such as ACI.</span></span>

<span data-ttu-id="f53eb-156">È possibile scaricare l'immagine Docker IQ# da https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span><span class="sxs-lookup"><span data-stu-id="f53eb-156">You can download the IQ# Docker image from https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span></span> 

<span data-ttu-id="f53eb-157">È anche possibile usare Docker con un contenitore di sviluppo remoto di Visual Studio Code per definire rapidamente gli ambienti di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="f53eb-157">You can also use Docker with a Visual Studio Code Remote Development Container to quickly define development environments.</span></span> <span data-ttu-id="f53eb-158">Per altre informazioni sui contenitori di sviluppo di VS Code, vedere https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span><span class="sxs-lookup"><span data-stu-id="f53eb-158">For more information about VS Code Development Containers, see https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f53eb-159">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="f53eb-159">Next steps</span></span>

<span data-ttu-id="f53eb-160">I flussi di lavoro per ognuna di queste configurazioni vengono descritti e confrontati in [Modalità di esecuzione di programmi Q#](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="f53eb-160">The workflows for each of these setups are described and compared at [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>
