---
title: Sviluppare con applicazioni Q# in un IDE
description: Informazioni su come creare un'applicazione Q# che viene eseguita dal prompt dei comandi.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: quickstart
uid: microsoft.quantum.install.standalone
no-loc:
- Q#
- $$v
ms.openlocfilehash: 3e4f1e97477ecb0547b1586b1c7603c8a9954584
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844325"
---
# <a name="develop-with-no-locq-applications-in-an-ide"></a><span data-ttu-id="20897-103">Sviluppare con applicazioni Q# in un IDE</span><span class="sxs-lookup"><span data-stu-id="20897-103">Develop with Q# applications in an IDE</span></span>

<span data-ttu-id="20897-104">I programmi Q# possono essere eseguiti autonomamente, senza un driver in un linguaggio host come C#, F# o Python.</span><span class="sxs-lookup"><span data-stu-id="20897-104">Q# programs can run on their own, without a driver in a host language like C#, F#, or Python.</span></span> <span data-ttu-id="20897-105">È possibile sviluppare applicazioni Q# in Visual Studio Code (VS Code), Visual Studio, Visual Studio Codespaces o con qualsiasi editor/IDE ed eseguire applicazioni dalla console .NET.</span><span class="sxs-lookup"><span data-stu-id="20897-105">You can develop Q# applications in Visual Studio Code (VS Code), Visual Studio, Visual Studio Codespaces, or with any editor/IDE and run applications from the .NET console.</span></span> 

## <a name="prerequisites-for-all-environments"></a><span data-ttu-id="20897-106">Prerequisiti per tutti gli ambienti</span><span class="sxs-lookup"><span data-stu-id="20897-106">Prerequisites for all environments</span></span>

- [<span data-ttu-id="20897-107">.NET Core SDK 3.1 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="20897-107">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="20897-108">Installazione</span><span class="sxs-lookup"><span data-stu-id="20897-108">Installation</span></span>

<span data-ttu-id="20897-109">Anche se è possibile compilare applicazioni Q# in qualsiasi IDE, è consigliabile usare Visual Studio Code (VS Code) o l'IDE di Visual Studio per sviluppare le applicazioni Q# in locale.</span><span class="sxs-lookup"><span data-stu-id="20897-109">While you can build Q# applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for developing your Q# applications locally.</span></span> <span data-ttu-id="20897-110">Per sviluppare nel cloud tramite il Web browser, è consigliabile usare Visual Studio Codespaces.</span><span class="sxs-lookup"><span data-stu-id="20897-110">For developing in the Cloud via the web browser, we recommend Visual Studio Codespaces.</span></span> <span data-ttu-id="20897-111">Per lo sviluppo in questi ambienti vengono sfruttate le funzionalità avanzate dell'estensione QDK, tra cui avvisi, evidenziazione della sintassi, modelli di progetto e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="20897-111">Developing in these environments leverages the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span> 

### <a name="to-configure-for-vs-code"></a><span data-ttu-id="20897-112">Per eseguire la configurazione per VS Code:</span><span class="sxs-lookup"><span data-stu-id="20897-112">To configure for VS Code:</span></span>

1. <span data-ttu-id="20897-113">Scaricare e installare [VS Code](https://code.visualstudio.com/download) (Windows, Linux e Mac).</span><span class="sxs-lookup"><span data-stu-id="20897-113">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="20897-114">Installare [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="20897-114">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

### <a name="to-configure-for-visual-studio"></a><span data-ttu-id="20897-115">Per eseguire la configurazione per Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="20897-115">To configure for Visual Studio:</span></span>

1. <span data-ttu-id="20897-116">Scaricare e installare [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 o versione successiva, con il carico di lavoro per lo sviluppo multipiattaforma .NET Core abilitato.</span><span class="sxs-lookup"><span data-stu-id="20897-116">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="20897-117">Scaricare e installare [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="20897-117">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

### <a name="to-configure-for-another-environment"></a><span data-ttu-id="20897-118">Per eseguire la configurazione per un altro ambiente:</span><span class="sxs-lookup"><span data-stu-id="20897-118">To configure for another environment:</span></span> 

1. <span data-ttu-id="20897-119">Al prompt dei comandi immettere quanto segue</span><span class="sxs-lookup"><span data-stu-id="20897-119">Enter the following at the command prompt</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

### <a name="to-configure-for-visual-studio-codespaces"></a><span data-ttu-id="20897-120">Per eseguire la configurazione per Visual Studio Codespaces:</span><span class="sxs-lookup"><span data-stu-id="20897-120">To configure for Visual Studio Codespaces:</span></span>

1. <span data-ttu-id="20897-121">Creare un [account Azure](https://azure.microsoft.com/free/).</span><span class="sxs-lookup"><span data-stu-id="20897-121">Create an [Azure account](https://azure.microsoft.com/free/).</span></span>
2. <span data-ttu-id="20897-122">Creare un ambiente Codespaces.</span><span class="sxs-lookup"><span data-stu-id="20897-122">Create a Codespaces environment.</span></span> <span data-ttu-id="20897-123">Seguire la [guida di avvio rapido](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser).</span><span class="sxs-lookup"><span data-stu-id="20897-123">Please follow the [quickstart guide](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser).</span></span> <span data-ttu-id="20897-124">Quando si crea il codespace, è consigliabile immettere `microsoft/Quantum` nel campo "Repository GIT" per caricare le impostazioni specifiche di QDK.</span><span class="sxs-lookup"><span data-stu-id="20897-124">When creating the Codespace, we recommend to enter `microsoft/Quantum` in the "Git Repository" field to load QDK-specific settings.</span></span>
3. <span data-ttu-id="20897-125">È ora possibile avviare il nuovo ambiente e iniziare a sviluppare nel browser tramite l'[IDE cloud di VS Codespaces](https://online.visualstudio.com/environments).</span><span class="sxs-lookup"><span data-stu-id="20897-125">You can now launch your new environment and start developing in the browser via the [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments).</span></span> <span data-ttu-id="20897-126">In alternativa, è possibile usare l'installazione locale di VS Code e usare Codespaces come [ambiente remoto](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span><span class="sxs-lookup"><span data-stu-id="20897-126">Alternatively, it is possible to use your local installation of VS Code and use Codespaces as a [remote environment](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span></span>

## <a name="develop-with-no-locq"></a><span data-ttu-id="20897-127">Sviluppare con Q#</span><span class="sxs-lookup"><span data-stu-id="20897-127">Develop with Q#</span></span>

<span data-ttu-id="20897-128">Seguire le istruzioni riportate nella scheda corrispondente al proprio ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="20897-128">Follow the instructions on the tab corresponding to your development environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="20897-129">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="20897-129">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="20897-130">Per creare un nuovo progetto:</span><span class="sxs-lookup"><span data-stu-id="20897-130">To create a new project:</span></span>

1. <span data-ttu-id="20897-131">Fare clic su **Visualizza** -> **Riquadro comandi** e selezionare **Q#: Create New Project**(ASA: Crea nuovo progetto).</span><span class="sxs-lookup"><span data-stu-id="20897-131">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="20897-132">Click **Standalone console application** (Applicazione console autonoma).</span><span class="sxs-lookup"><span data-stu-id="20897-132">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="20897-133">Passare alla posizione in cui salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="20897-133">Navigate to the location to save the project.</span></span> <span data-ttu-id="20897-134">Immettere il nome del progetto e fare clic su **Crea progetto**.</span><span class="sxs-lookup"><span data-stu-id="20897-134">Enter the project name and click **Create Project**.</span></span>
4. <span data-ttu-id="20897-135">Al termine dell'operazione, fare clic su **Open new project** (Apri nuovo progetto) in basso a destra.</span><span class="sxs-lookup"><span data-stu-id="20897-135">When the project is successfully created, click **Open new project...** in the lower right.</span></span>

<span data-ttu-id="20897-136">Esaminare il progetto.</span><span class="sxs-lookup"><span data-stu-id="20897-136">Inspect the project.</span></span> <span data-ttu-id="20897-137">Dovrebbe essere visualizzato un file di origine denominato `Program.qs`, che corrisponde a un programma Q# in cui viene definita una semplice operazione per stampare un messaggio nella console.</span><span class="sxs-lookup"><span data-stu-id="20897-137">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="20897-138">Per eseguire l'applicazione:</span><span class="sxs-lookup"><span data-stu-id="20897-138">To run the application:</span></span>

1. <span data-ttu-id="20897-139">Fare clic su **Terminale** -> **Nuovo terminale**.</span><span class="sxs-lookup"><span data-stu-id="20897-139">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="20897-140">Al prompt del terminale, immettere `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="20897-140">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="20897-141">Nella finestra di output verrà visualizzato il testo seguente: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="20897-141">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> <span data-ttu-id="20897-142">Le aree di lavoro con più cartelle radice non sono attualmente supportate dall'estensione VS Code per Q#.</span><span class="sxs-lookup"><span data-stu-id="20897-142">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="20897-143">Se sono presenti più progetti all'interno di un'area di lavoro di Visual Studio Code, è necessario che tutti i progetti siano contenuti all'interno della stessa cartella radice.</span><span class="sxs-lookup"><span data-stu-id="20897-143">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="20897-144">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="20897-144">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="20897-145">Verificare l'installazione di Visual Studio creando un'applicazione `Hello World` Q#.</span><span class="sxs-lookup"><span data-stu-id="20897-145">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="20897-146">Per creare una nuova applicazione Q#:</span><span class="sxs-lookup"><span data-stu-id="20897-146">To create a new Q# application:</span></span>

1. <span data-ttu-id="20897-147">Aprire Visual Studio e fare clic su **File** -> **Nuovo** -> **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="20897-147">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="20897-148">Digitare `Q#` nella casella di ricerca, selezionare **Q# Application** (Applicazione Q#) e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20897-148">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="20897-149">Immettere un nome e un percorso per l'applicazione e fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="20897-149">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="20897-150">Esaminare il progetto.</span><span class="sxs-lookup"><span data-stu-id="20897-150">Inspect the project.</span></span> <span data-ttu-id="20897-151">Dovrebbe essere visualizzato un file di origine denominato `Program.qs`, che corrisponde a un programma Q# in cui viene definita una semplice operazione per stampare un messaggio nella console.</span><span class="sxs-lookup"><span data-stu-id="20897-151">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="20897-152">Per eseguire l'applicazione:</span><span class="sxs-lookup"><span data-stu-id="20897-152">To run the application:</span></span>

1. <span data-ttu-id="20897-153">Selezionare **Debug** -> **Avvia senza eseguire debug**.</span><span class="sxs-lookup"><span data-stu-id="20897-153">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="20897-154">Verrà visualizzato il testo `Hello quantum world!` stampato in una finestra della console.</span><span class="sxs-lookup"><span data-stu-id="20897-154">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="20897-155">Se sono presenti più progetti all'interno di una soluzione di Visual Studio, è necessario che tutti i progetti contenuti nella soluzione si trovino nella stessa cartella della soluzione o in una delle relative sottocartelle.</span><span class="sxs-lookup"><span data-stu-id="20897-155">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-prompt"></a>[<span data-ttu-id="20897-156">Altri editor con il prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="20897-156">Other editors with the command prompt</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="20897-157">Verificare l'installazione creando un'applicazione `Hello World` Q#.</span><span class="sxs-lookup"><span data-stu-id="20897-157">Verify your installation by creating a Q# `Hello World` application.</span></span>

1. <span data-ttu-id="20897-158">Creare una nuova applicazione:</span><span class="sxs-lookup"><span data-stu-id="20897-158">Create a new application:</span></span>

    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. <span data-ttu-id="20897-159">Passare alla directory dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="20897-159">Navigate to the application directory:</span></span>

    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="20897-160">Questa directory dovrebbe ora contenere un file `Program.qs`, che corrisponde a un programma Q# in cui viene definita una semplice operazione per stampare un messaggio nella console.</span><span class="sxs-lookup"><span data-stu-id="20897-160">This directory should now contain a file `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="20897-161">È possibile modificare questo modello con un editor di testo e sovrascriverlo con le proprie applicazioni quantistiche.</span><span class="sxs-lookup"><span data-stu-id="20897-161">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

1. <span data-ttu-id="20897-162">Eseguire il programma:</span><span class="sxs-lookup"><span data-stu-id="20897-162">Run the program:</span></span>

    ```dotnetcli
    dotnet run
    ```

1. <span data-ttu-id="20897-163">Verrà visualizzato il testo seguente: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="20897-163">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="20897-164">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="20897-164">Next steps</span></span>

<span data-ttu-id="20897-165">Ora che è stato installato Quantum Development Kit nell'ambiente preferito, è possibile scrivere ed eseguire [il primo programma quantistico](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="20897-165">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
