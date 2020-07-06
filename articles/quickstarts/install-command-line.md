---
title: Sviluppare con le applicazioni della riga di comando di Q#
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 15015d1673f47faf5a13dde516f834916b4319d6
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2020
ms.locfileid: "85884284"
---
# <a name="develop-with-q-command-line-applications"></a><span data-ttu-id="8cea0-102">Sviluppare con le applicazioni della riga di comando di Q#</span><span class="sxs-lookup"><span data-stu-id="8cea0-102">Develop with Q# command line applications</span></span>

<span data-ttu-id="8cea0-103">I programmi Q# possono essere eseguiti autonomamente, senza un driver in un linguaggio host come C#, F# o Python.</span><span class="sxs-lookup"><span data-stu-id="8cea0-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8cea0-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="8cea0-104">Prerequisites</span></span>

- [<span data-ttu-id="8cea0-105">.NET Core SDK 3.1 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="8cea0-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="8cea0-106">Installazione</span><span class="sxs-lookup"><span data-stu-id="8cea0-106">Installation</span></span>

<span data-ttu-id="8cea0-107">Anche se è possibile compilare applicazioni della riga di comando di Q# in qualsiasi IDE, è consigliabile usare Visual Studio Code (VS Code) o l'IDE di Visual Studio per le applicazioni di Q#.</span><span class="sxs-lookup"><span data-stu-id="8cea0-107">While you can build Q# command line applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="8cea0-108">Lo sviluppo in questi ambienti include le funzionalità avanzate dell'estensione QDK, tra cui avvisi, evidenziazione della sintassi, modelli di progetto e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="8cea0-108">Developing in these environments includes the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span>

<span data-ttu-id="8cea0-109">Per configurare VS Code:</span><span class="sxs-lookup"><span data-stu-id="8cea0-109">To configure VS Code:</span></span>

1. <span data-ttu-id="8cea0-110">Scaricare e installare [VS Code](https://code.visualstudio.com/download) (Windows, Linux e Mac).</span><span class="sxs-lookup"><span data-stu-id="8cea0-110">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="8cea0-111">Installare [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="8cea0-111">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="8cea0-112">Per configurare Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="8cea0-112">To configure Visual Studio:</span></span>

1. <span data-ttu-id="8cea0-113">Scaricare e installare [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 o versione successiva, con il carico di lavoro per lo sviluppo multipiattaforma .NET Core abilitato.</span><span class="sxs-lookup"><span data-stu-id="8cea0-113">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="8cea0-114">Scaricare e installare [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="8cea0-114">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

<span data-ttu-id="8cea0-115">Per installare QDK per un altro ambiente, immettere quanto segue nella riga di comando:</span><span class="sxs-lookup"><span data-stu-id="8cea0-115">To install the QDK for another environment, enter in the command line:</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-q"></a><span data-ttu-id="8cea0-116">Sviluppare con Q#</span><span class="sxs-lookup"><span data-stu-id="8cea0-116">Develop with Q#</span></span>

<span data-ttu-id="8cea0-117">Seguire le istruzioni riportate nella scheda corrispondente al proprio ambiente.</span><span class="sxs-lookup"><span data-stu-id="8cea0-117">Follow the instructions at the tab corresponding to your environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="8cea0-118">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="8cea0-118">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="8cea0-119">Installare i modelli di progetto Q#:</span><span class="sxs-lookup"><span data-stu-id="8cea0-119">Install the Q# project templates:</span></span>

1. <span data-ttu-id="8cea0-120">Aprire Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="8cea0-120">Open VS Code.</span></span>
2. <span data-ttu-id="8cea0-121">Fare clic su **Visualizza** -> **Riquadro comandi**.</span><span class="sxs-lookup"><span data-stu-id="8cea0-121">Click **View** -> **Command Palette**.</span></span>
3. <span data-ttu-id="8cea0-122">Selezionare **Q#: Install project templates** (Q#: Installa modelli di progetto).</span><span class="sxs-lookup"><span data-stu-id="8cea0-122">Select **Q#: Install project templates**.</span></span>

<span data-ttu-id="8cea0-123">Quando viene visualizzato il messaggio **Project templates installed successfully** (Modelli di progetto installati), il QDK è pronto per l'uso con applicazioni e librerie personalizzate.</span><span class="sxs-lookup"><span data-stu-id="8cea0-123">When **Project templates installed successfully** displays, the QDK is ready to use with your own applications and libraries.</span></span>

<span data-ttu-id="8cea0-124">Per creare un nuovo progetto:</span><span class="sxs-lookup"><span data-stu-id="8cea0-124">To create a new project:</span></span>

1. <span data-ttu-id="8cea0-125">Fare clic su **Visualizza** -> **Riquadro comandi** e selezionare **Q#: Create New Project**(ASA: Crea nuovo progetto).</span><span class="sxs-lookup"><span data-stu-id="8cea0-125">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="8cea0-126">Click **Standalone console application** (Applicazione console autonoma).</span><span class="sxs-lookup"><span data-stu-id="8cea0-126">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="8cea0-127">Passare al percorso in cui salvare il progetto e fare clic su **Create Project** (Crea progetto).</span><span class="sxs-lookup"><span data-stu-id="8cea0-127">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="8cea0-128">Al termine dell'operazione, fare clic su **Open new project** (Apri nuovo progetto) in basso a destra.</span><span class="sxs-lookup"><span data-stu-id="8cea0-128">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="8cea0-129">Esaminare il progetto.</span><span class="sxs-lookup"><span data-stu-id="8cea0-129">Inspect the project.</span></span> <span data-ttu-id="8cea0-130">Dovrebbe essere visualizzato un file di origine denominato `Program.qs`, che corrisponde a un programma Q# in cui viene definita una semplice operazione per stampare un messaggio nella console.</span><span class="sxs-lookup"><span data-stu-id="8cea0-130">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="8cea0-131">Per eseguire l'applicazione:</span><span class="sxs-lookup"><span data-stu-id="8cea0-131">To run the application:</span></span>
1. <span data-ttu-id="8cea0-132">Fare clic su **Terminale** -> **Nuovo terminale**.</span><span class="sxs-lookup"><span data-stu-id="8cea0-132">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="8cea0-133">Al prompt del terminale, immettere `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="8cea0-133">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="8cea0-134">Nella finestra di output verrà visualizzato il testo seguente: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="8cea0-134">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="8cea0-135">Le aree di lavoro con più cartelle radice non sono attualmente supportate dall'estensione Q# di VS Code.</span><span class="sxs-lookup"><span data-stu-id="8cea0-135">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="8cea0-136">Se sono presenti più progetti all'interno di un'area di lavoro di Visual Studio Code, è necessario che tutti i progetti siano contenuti all'interno della stessa cartella radice.</span><span class="sxs-lookup"><span data-stu-id="8cea0-136">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="8cea0-137">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8cea0-137">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="8cea0-138">Verificare l'installazione di Visual Studio creando un'applicazione Q# `Hello World`.</span><span class="sxs-lookup"><span data-stu-id="8cea0-138">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="8cea0-139">Per creare una nuova applicazione Q#:</span><span class="sxs-lookup"><span data-stu-id="8cea0-139">To create a new Q# application:</span></span>
1. <span data-ttu-id="8cea0-140">Aprire Visual Studio e fare clic su **File** -> **Nuovo** -> **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="8cea0-140">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="8cea0-141">Digitare `Q#` nella casella di ricerca, selezionare **Q# Application** (Applicazione Q#) e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8cea0-141">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="8cea0-142">Immettere un nome e un percorso per l'applicazione e fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="8cea0-142">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="8cea0-143">Esaminare il progetto.</span><span class="sxs-lookup"><span data-stu-id="8cea0-143">Inspect the project.</span></span> <span data-ttu-id="8cea0-144">Dovrebbe essere visualizzato un file di origine denominato `Program.qs`, che corrisponde a un programma Q# in cui viene definita una semplice operazione per stampare un messaggio nella console.</span><span class="sxs-lookup"><span data-stu-id="8cea0-144">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="8cea0-145">Per eseguire l'applicazione:</span><span class="sxs-lookup"><span data-stu-id="8cea0-145">To run the application:</span></span>
1. <span data-ttu-id="8cea0-146">Selezionare **Debug** -> **Avvia senza eseguire debug**.</span><span class="sxs-lookup"><span data-stu-id="8cea0-146">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="8cea0-147">Verrà visualizzato il testo `Hello quantum world!` stampato in una finestra della console.</span><span class="sxs-lookup"><span data-stu-id="8cea0-147">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="8cea0-148">Se sono presenti più progetti all'interno di una soluzione di Visual Studio, è necessario che tutti i progetti contenuti nella soluzione si trovino nella stessa cartella della soluzione o in una delle relative sottocartelle.</span><span class="sxs-lookup"><span data-stu-id="8cea0-148">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-line"></a>[<span data-ttu-id="8cea0-149">Altri editor con la riga di comando</span><span class="sxs-lookup"><span data-stu-id="8cea0-149">Other editors with the command line</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="8cea0-150">Verificare l'installazione creando un'applicazione `Hello World` Q#.</span><span class="sxs-lookup"><span data-stu-id="8cea0-150">Verify your installation by creating a Q# `Hello World` application.</span></span>

1. <span data-ttu-id="8cea0-151">Creare una nuova applicazione:</span><span class="sxs-lookup"><span data-stu-id="8cea0-151">Create a new application:</span></span>
    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

2. <span data-ttu-id="8cea0-152">Passare alla directory dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="8cea0-152">Navigate to the application directory:</span></span>
    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="8cea0-153">Questa directory dovrebbe ora contenere un file `Program.qs`, che corrisponde a un programma Q# in cui viene definita una semplice operazione per stampare un messaggio nella console.</span><span class="sxs-lookup"><span data-stu-id="8cea0-153">This directory should now contain a file `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="8cea0-154">È possibile modificare questo modello con un editor di testo e sovrascriverlo con le proprie applicazioni quantistiche.</span><span class="sxs-lookup"><span data-stu-id="8cea0-154">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

3. <span data-ttu-id="8cea0-155">Eseguire il programma:</span><span class="sxs-lookup"><span data-stu-id="8cea0-155">Run the program:</span></span>
    ```dotnetcli
    dotnet run
    ```

4. <span data-ttu-id="8cea0-156">Verrà visualizzato il testo seguente: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="8cea0-156">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="8cea0-157">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="8cea0-157">Next steps</span></span>

<span data-ttu-id="8cea0-158">Ora che è stato installato Quantum Development Kit nell'ambiente preferito, è possibile scrivere ed eseguire [il primo programma quantistico](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="8cea0-158">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
