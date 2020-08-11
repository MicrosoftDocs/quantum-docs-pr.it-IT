---
title: Sviluppare con le applicazioni della riga di comando di Q#
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
no-loc:
- Q#
- $$v
ms.openlocfilehash: 630dc7b8acf2dd8f258eb27dfbc367b812cd1c19
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867608"
---
# <a name="develop-with-no-locq-command-line-applications"></a><span data-ttu-id="70398-102">Sviluppare con le applicazioni della riga di comando di Q#</span><span class="sxs-lookup"><span data-stu-id="70398-102">Develop with Q# command line applications</span></span>

<span data-ttu-id="70398-103">I programmi Q# possono essere eseguiti autonomamente, senza un driver in un linguaggio host come C#, F# o Python.</span><span class="sxs-lookup"><span data-stu-id="70398-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="70398-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="70398-104">Prerequisites</span></span>

- [<span data-ttu-id="70398-105">.NET Core SDK 3.1 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="70398-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="70398-106">Installazione</span><span class="sxs-lookup"><span data-stu-id="70398-106">Installation</span></span>

<span data-ttu-id="70398-107">Anche se è possibile compilare applicazioni della riga di comando di Q# in qualsiasi IDE, è consigliabile usare Visual Studio Code (VS Code) o l'IDE di Visual Studio per sviluppare le applicazioni Q# in locale.</span><span class="sxs-lookup"><span data-stu-id="70398-107">While you can build Q# command line applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for developing your Q# applications locally.</span></span> <span data-ttu-id="70398-108">Per sviluppare nel cloud tramite il Web browser, è consigliabile usare Visual Studio Codespaces.</span><span class="sxs-lookup"><span data-stu-id="70398-108">For developing in the Cloud via the web browser, we recommend Visual Studio Codespaces.</span></span> <span data-ttu-id="70398-109">Lo sviluppo in questi ambienti include le funzionalità avanzate dell'estensione QDK, tra cui avvisi, evidenziazione della sintassi, modelli di progetto e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="70398-109">Developing in these environments includes the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span> 

<span data-ttu-id="70398-110">Per configurare VS Code:</span><span class="sxs-lookup"><span data-stu-id="70398-110">To configure VS Code:</span></span>

1. <span data-ttu-id="70398-111">Scaricare e installare [VS Code](https://code.visualstudio.com/download) (Windows, Linux e Mac).</span><span class="sxs-lookup"><span data-stu-id="70398-111">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="70398-112">Installare [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="70398-112">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="70398-113">Per configurare Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="70398-113">To configure Visual Studio:</span></span>

1. <span data-ttu-id="70398-114">Scaricare e installare [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 o versione successiva, con il carico di lavoro per lo sviluppo multipiattaforma .NET Core abilitato.</span><span class="sxs-lookup"><span data-stu-id="70398-114">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="70398-115">Scaricare e installare [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="70398-115">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

<span data-ttu-id="70398-116">Per configurare Visual Studio Codespaces:</span><span class="sxs-lookup"><span data-stu-id="70398-116">To configure Visual Studio Codespaces:</span></span>

1. <span data-ttu-id="70398-117">Creare un [account Azure](https://azure.microsoft.com/free/).</span><span class="sxs-lookup"><span data-stu-id="70398-117">Create an [Azure account](https://azure.microsoft.com/free/).</span></span>
2. <span data-ttu-id="70398-118">Creare un ambiente Codespaces.</span><span class="sxs-lookup"><span data-stu-id="70398-118">Create a Codespaces environment.</span></span> <span data-ttu-id="70398-119">Seguire la [guida di avvio rapido](https://docs.microsoft.com/visualstudio/online/quickstarts/browser).</span><span class="sxs-lookup"><span data-stu-id="70398-119">Please follow the [quickstart guide](https://docs.microsoft.com/visualstudio/online/quickstarts/browser).</span></span> <span data-ttu-id="70398-120">Quando si crea il codespace, è consigliabile immettere `microsoft/Quantum` nel campo "Repository GIT" per caricare le impostazioni specifiche di QDK.</span><span class="sxs-lookup"><span data-stu-id="70398-120">When creating the Codespace, we recommend to enter `microsoft/Quantum` in the "Git Repository" field to load QDK-specific settings.</span></span>
3. <span data-ttu-id="70398-121">È ora possibile avviare il nuovo ambiente e iniziare a sviluppare nel browser tramite l'[IDE cloud di VS Codespaces](https://online.visualstudio.com/environments).</span><span class="sxs-lookup"><span data-stu-id="70398-121">You can now launch your new environment and start developing in the browser via the [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments).</span></span> <span data-ttu-id="70398-122">In alternativa, è possibile usare l'installazione locale di VS Code e usare Codespaces come [ambiente remoto](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span><span class="sxs-lookup"><span data-stu-id="70398-122">Alternatively, it is possible to use your local installation of VS Code and use Codespaces as a [remote environment](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span></span>


<span data-ttu-id="70398-123">Per installare QDK per un altro ambiente, immettere quanto segue nella riga di comando:</span><span class="sxs-lookup"><span data-stu-id="70398-123">To install the QDK for another environment, enter in the command line:</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-no-locq"></a><span data-ttu-id="70398-124">Sviluppare con Q#</span><span class="sxs-lookup"><span data-stu-id="70398-124">Develop with Q#</span></span>

<span data-ttu-id="70398-125">Seguire le istruzioni riportate nella scheda corrispondente al proprio ambiente.</span><span class="sxs-lookup"><span data-stu-id="70398-125">Follow the instructions at the tab corresponding to your environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="70398-126">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="70398-126">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="70398-127">Per creare un nuovo progetto:</span><span class="sxs-lookup"><span data-stu-id="70398-127">To create a new project:</span></span>

1. <span data-ttu-id="70398-128">Fare clic su **Visualizza** -> **Riquadro comandi** e selezionare **Q#: Create New Project**(ASA: Crea nuovo progetto).</span><span class="sxs-lookup"><span data-stu-id="70398-128">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="70398-129">Click **Standalone console application** (Applicazione console autonoma).</span><span class="sxs-lookup"><span data-stu-id="70398-129">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="70398-130">Passare al percorso in cui salvare il progetto e fare clic su **Create Project** (Crea progetto).</span><span class="sxs-lookup"><span data-stu-id="70398-130">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="70398-131">Al termine dell'operazione, fare clic su **Open new project** (Apri nuovo progetto) in basso a destra.</span><span class="sxs-lookup"><span data-stu-id="70398-131">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="70398-132">Esaminare il progetto.</span><span class="sxs-lookup"><span data-stu-id="70398-132">Inspect the project.</span></span> <span data-ttu-id="70398-133">Dovrebbe essere visualizzato un file di origine denominato `Program.qs`, che corrisponde a un programma Q# in cui viene definita una semplice operazione per stampare un messaggio nella console.</span><span class="sxs-lookup"><span data-stu-id="70398-133">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="70398-134">Per eseguire l'applicazione:</span><span class="sxs-lookup"><span data-stu-id="70398-134">To run the application:</span></span>
1. <span data-ttu-id="70398-135">Fare clic su **Terminale** -> **Nuovo terminale**.</span><span class="sxs-lookup"><span data-stu-id="70398-135">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="70398-136">Al prompt del terminale, immettere `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="70398-136">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="70398-137">Nella finestra di output verrà visualizzato il testo seguente: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="70398-137">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="70398-138">Le aree di lavoro con più cartelle radice non sono attualmente supportate dall'estensione VS Code per Q#.</span><span class="sxs-lookup"><span data-stu-id="70398-138">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="70398-139">Se sono presenti più progetti all'interno di un'area di lavoro di Visual Studio Code, è necessario che tutti i progetti siano contenuti all'interno della stessa cartella radice.</span><span class="sxs-lookup"><span data-stu-id="70398-139">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="70398-140">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="70398-140">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="70398-141">Verificare l'installazione di Visual Studio creando un'applicazione `Hello World` Q#.</span><span class="sxs-lookup"><span data-stu-id="70398-141">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="70398-142">Per creare una nuova applicazione Q#:</span><span class="sxs-lookup"><span data-stu-id="70398-142">To create a new Q# application:</span></span>
1. <span data-ttu-id="70398-143">Aprire Visual Studio e fare clic su **File** -> **Nuovo** -> **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="70398-143">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="70398-144">Digitare `Q#` nella casella di ricerca, selezionare **Q# Application** (Applicazione Q#) e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="70398-144">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="70398-145">Immettere un nome e un percorso per l'applicazione e fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="70398-145">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="70398-146">Esaminare il progetto.</span><span class="sxs-lookup"><span data-stu-id="70398-146">Inspect the project.</span></span> <span data-ttu-id="70398-147">Dovrebbe essere visualizzato un file di origine denominato `Program.qs`, che corrisponde a un programma Q# in cui viene definita una semplice operazione per stampare un messaggio nella console.</span><span class="sxs-lookup"><span data-stu-id="70398-147">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="70398-148">Per eseguire l'applicazione:</span><span class="sxs-lookup"><span data-stu-id="70398-148">To run the application:</span></span>
1. <span data-ttu-id="70398-149">Selezionare **Debug** -> **Avvia senza eseguire debug**.</span><span class="sxs-lookup"><span data-stu-id="70398-149">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="70398-150">Verrà visualizzato il testo `Hello quantum world!` stampato in una finestra della console.</span><span class="sxs-lookup"><span data-stu-id="70398-150">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="70398-151">Se sono presenti più progetti all'interno di una soluzione di Visual Studio, è necessario che tutti i progetti contenuti nella soluzione si trovino nella stessa cartella della soluzione o in una delle relative sottocartelle.</span><span class="sxs-lookup"><span data-stu-id="70398-151">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-line"></a>[<span data-ttu-id="70398-152">Altri editor con la riga di comando</span><span class="sxs-lookup"><span data-stu-id="70398-152">Other editors with the command line</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="70398-153">Verificare l'installazione creando un'applicazione `Hello World` Q#.</span><span class="sxs-lookup"><span data-stu-id="70398-153">Verify your installation by creating a Q# `Hello World` application.</span></span>

1. <span data-ttu-id="70398-154">Installare i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="70398-154">Install the project templates.</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. <span data-ttu-id="70398-155">Creare una nuova applicazione:</span><span class="sxs-lookup"><span data-stu-id="70398-155">Create a new application:</span></span>
    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. <span data-ttu-id="70398-156">Passare alla directory dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="70398-156">Navigate to the application directory:</span></span>
    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="70398-157">Questa directory dovrebbe ora contenere un file `Program.qs`, che corrisponde a un programma Q# in cui viene definita una semplice operazione per stampare un messaggio nella console.</span><span class="sxs-lookup"><span data-stu-id="70398-157">This directory should now contain a file `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="70398-158">È possibile modificare questo modello con un editor di testo e sovrascriverlo con le proprie applicazioni quantistiche.</span><span class="sxs-lookup"><span data-stu-id="70398-158">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

1. <span data-ttu-id="70398-159">Eseguire il programma:</span><span class="sxs-lookup"><span data-stu-id="70398-159">Run the program:</span></span>
    ```dotnetcli
    dotnet run
    ```

1. <span data-ttu-id="70398-160">Verrà visualizzato il testo seguente: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="70398-160">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="70398-161">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="70398-161">Next steps</span></span>

<span data-ttu-id="70398-162">Ora che è stato installato Quantum Development Kit nell'ambiente preferito, è possibile scrivere ed eseguire [il primo programma quantistico](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="70398-162">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
