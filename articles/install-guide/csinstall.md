---
title: 'Sviluppare con Q # +C#'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 7803846279f230f5fc0ee8424bd39be735a650ca
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036288"
---
# <a name="develop-with-q--c"></a><span data-ttu-id="1f261-102">Sviluppare con Q # +C#</span><span class="sxs-lookup"><span data-stu-id="1f261-102">Develop with Q# + C#</span></span>

<span data-ttu-id="1f261-103">Installare QDK per sviluppare C# programmi host per chiamare le operazioni Q #.</span><span class="sxs-lookup"><span data-stu-id="1f261-103">Install the QDK to develop C# host programs to call Q# operations.</span></span>

<span data-ttu-id="1f261-104">Q # è progettato per essere eseguito correttamente con i linguaggi .NET, C#in particolare.</span><span class="sxs-lookup"><span data-stu-id="1f261-104">Q# is built to play well with .NET languages--specifically C#.</span></span> <span data-ttu-id="1f261-105">È possibile utilizzare questa associazione all'interno di diversi ambienti di sviluppo:</span><span class="sxs-lookup"><span data-stu-id="1f261-105">You can work with this pairing inside different development environments:</span></span>

- [<span data-ttu-id="1f261-106">Domande e risposte C# con Visual Studio (Windows)</span><span class="sxs-lookup"><span data-stu-id="1f261-106">Q# + C# using Visual Studio (Windows)</span></span>](#VS)
- [<span data-ttu-id="1f261-107">Domande e risposte C# con Visual Studio Code (Windows, Linux e Mac)</span><span class="sxs-lookup"><span data-stu-id="1f261-107">Q# + C# using Visual Studio Code (Windows, Linux and Mac)</span></span>](#VSC)
- [<span data-ttu-id="1f261-108">Q # + C# uso dello strumento da riga di comando `dotnet`</span><span class="sxs-lookup"><span data-stu-id="1f261-108">Q# + C# using the `dotnet` command-line tool</span></span>](#command)

## <span data-ttu-id="1f261-109">Sviluppare con Q # + C# con Visual Studio <a name="VS"></a></span><span class="sxs-lookup"><span data-stu-id="1f261-109">Develop with Q# + C# using Visual Studio <a name="VS"></a></span></span>

<span data-ttu-id="1f261-110">Visual Studio offre un ambiente completo per lo sviluppo di programmi Q #.</span><span class="sxs-lookup"><span data-stu-id="1f261-110">Visual Studio offers a rich environment for developing Q# programs.</span></span> <span data-ttu-id="1f261-111">L'estensione Q # di Visual Studio contiene i modelli per i file e i progetti Q #, nonché l'evidenziazione della sintassi, il completamento del codice e il supporto IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="1f261-111">The Q# Visual Studio extension contains templates for Q# files and projects as well as syntax highlighting, code completion and IntelliSense support.</span></span>


1. <span data-ttu-id="1f261-112">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="1f261-112">Pre-requisites</span></span>

    - <span data-ttu-id="1f261-113">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, con il carico di lavoro per lo sviluppo multipiattaforma .NET Core abilitato</span><span class="sxs-lookup"><span data-stu-id="1f261-113">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>

1. <span data-ttu-id="1f261-114">Installare l'estensione di Visual Studio per Q#</span><span class="sxs-lookup"><span data-stu-id="1f261-114">Install the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="1f261-115">Scaricare e installare l' [estensione di Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="1f261-115">Download and install the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>

1. <span data-ttu-id="1f261-116">Verificare l'installazione creando un'applicazione `Hello World`</span><span class="sxs-lookup"><span data-stu-id="1f261-116">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="1f261-117">Creare una nuova applicazione Q#</span><span class="sxs-lookup"><span data-stu-id="1f261-117">Create a new Q# application</span></span>

        - <span data-ttu-id="1f261-118">Passare a **File** -> **Nuovo** -> **Progetto**</span><span class="sxs-lookup"><span data-stu-id="1f261-118">Go to **File** -> **New** -> **Project**</span></span>
        - <span data-ttu-id="1f261-119">Digitare `Q#` nella casella di ricerca</span><span class="sxs-lookup"><span data-stu-id="1f261-119">Type `Q#` in the search box</span></span>
        - <span data-ttu-id="1f261-120">Selezionare **Applicazione Q#**</span><span class="sxs-lookup"><span data-stu-id="1f261-120">Select **Q# Application**</span></span>
        - <span data-ttu-id="1f261-121">Selezionare **Avanti**</span><span class="sxs-lookup"><span data-stu-id="1f261-121">Select **Next**</span></span>
        - <span data-ttu-id="1f261-122">Scegliere un nome e una posizione per l'applicazione</span><span class="sxs-lookup"><span data-stu-id="1f261-122">Choose a name and location for your application</span></span>
        - <span data-ttu-id="1f261-123">Selezionare **Crea**</span><span class="sxs-lookup"><span data-stu-id="1f261-123">Select **Create**</span></span>

    - <span data-ttu-id="1f261-124">Esaminare il progetto</span><span class="sxs-lookup"><span data-stu-id="1f261-124">Inspect the project</span></span>

        <span data-ttu-id="1f261-125">Si noterà che sono stati creati due file: `Driver.cs`, ovvero l'applicazione host C# e `Operation.qs`, ovvero un programma Q# che definisce una semplice operazione per stampare un messaggio nella console.</span><span class="sxs-lookup"><span data-stu-id="1f261-125">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

    - <span data-ttu-id="1f261-126">Eseguire l'applicazione</span><span class="sxs-lookup"><span data-stu-id="1f261-126">Run the application</span></span>

        - <span data-ttu-id="1f261-127">Selezionare **Debug** -> **Avvia senza eseguire il debug**</span><span class="sxs-lookup"><span data-stu-id="1f261-127">Select **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="1f261-128">Verrà visualizzato il testo `Hello quantum world!` stampato in una finestra della console.</span><span class="sxs-lookup"><span data-stu-id="1f261-128">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="1f261-129">Se sono presenti più progetti all'interno di una soluzione di Visual Studio, è necessario che tutti i progetti contenuti nella soluzione si trovino nella stessa cartella della soluzione o in una delle relative sottocartelle.</span><span class="sxs-lookup"><span data-stu-id="1f261-129">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <span data-ttu-id="1f261-130">Sviluppare con Q # + C# usando Visual Studio Code <a name="VSC"></a></span><span class="sxs-lookup"><span data-stu-id="1f261-130">Develop with Q# + C# using Visual Studio Code <a name="VSC"></a></span></span>

<span data-ttu-id="1f261-131">Visual Studio Code (VS Code) offre un ambiente completo per lo sviluppo di programmi Q # in Windows, Linux e Mac.</span><span class="sxs-lookup"><span data-stu-id="1f261-131">Visual Studio Code (VS Code) offers a rich environment for developing Q# programs on Windows, Linux and Mac.</span></span>  <span data-ttu-id="1f261-132">L'estensione Q # VS Code include il supporto per l'evidenziazione della sintassi Q #, il completamento del codice e i frammenti di codice Q #.</span><span class="sxs-lookup"><span data-stu-id="1f261-132">The Q# VS Code extension includes support for Q# syntax highlighting, code completion, and Q# code snippets.</span></span>

1. <span data-ttu-id="1f261-133">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="1f261-133">Pre-requisites</span></span>

   - [<span data-ttu-id="1f261-134">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="1f261-134">VS Code</span></span>](https://code.visualstudio.com/download)
   - [<span data-ttu-id="1f261-135">.NET Core SDK 3,1 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="1f261-135">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="1f261-136">Installare l'estensione Visual Studio Code per il calcolo quantistico</span><span class="sxs-lookup"><span data-stu-id="1f261-136">Install the Quantum VS Code extension</span></span>

    - <span data-ttu-id="1f261-137">Installare l'[estensione Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span><span class="sxs-lookup"><span data-stu-id="1f261-137">Install the [VS Code extension](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span></span>

1. <span data-ttu-id="1f261-138">Installare i modelli di progetto di calcolo quantistico:</span><span class="sxs-lookup"><span data-stu-id="1f261-138">Install the Quantum project templates:</span></span>

   - <span data-ttu-id="1f261-139">Passare a **Visualizza** -> **Riquadro comandi**</span><span class="sxs-lookup"><span data-stu-id="1f261-139">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="1f261-140">Selezionare **Q #: installare i modelli di progetto**</span><span class="sxs-lookup"><span data-stu-id="1f261-140">Select **Q#: Install project templates**</span></span>

    <span data-ttu-id="1f261-141">Quantum Development Kit è ora installato e pronto per l'uso nelle applicazioni e nelle librerie.</span><span class="sxs-lookup"><span data-stu-id="1f261-141">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="1f261-142">Verificare l'installazione creando un'applicazione `Hello World`</span><span class="sxs-lookup"><span data-stu-id="1f261-142">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="1f261-143">Creare un nuovo progetto:</span><span class="sxs-lookup"><span data-stu-id="1f261-143">Create a new project:</span></span>

        - <span data-ttu-id="1f261-144">Passare a **Visualizza** -> **Riquadro comandi**</span><span class="sxs-lookup"><span data-stu-id="1f261-144">Go to **View** -> **Command Palette**</span></span>
        - <span data-ttu-id="1f261-145">Selezionare **Q #: Crea nuovo progetto**</span><span class="sxs-lookup"><span data-stu-id="1f261-145">Select **Q#: Create New Project**</span></span>
        - <span data-ttu-id="1f261-146">Seleziona **applicazione console autonoma**</span><span class="sxs-lookup"><span data-stu-id="1f261-146">Select **Standalone console application**</span></span>
        - <span data-ttu-id="1f261-147">Passare al percorso del file system in cui si vuole creare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="1f261-147">Navigate to the location on the file system where you would like to create the application</span></span>
        - <span data-ttu-id="1f261-148">Al termine della creazione del progetto, fare clic sul pulsante **Apri nuovo progetto...**</span><span class="sxs-lookup"><span data-stu-id="1f261-148">Click on the **Open new project...** button, once the project has been created</span></span>

    - <span data-ttu-id="1f261-149">Se non si ha già l' C# estensione per vs code installata, verrà visualizzato un popup.</span><span class="sxs-lookup"><span data-stu-id="1f261-149">If you don't already have the C# extension for VS Code installed, a pop-up will appear.</span></span> <span data-ttu-id="1f261-150">Installare l'estensione.</span><span class="sxs-lookup"><span data-stu-id="1f261-150">Install the extension.</span></span> 

    - <span data-ttu-id="1f261-151">Eseguire l'applicazione:</span><span class="sxs-lookup"><span data-stu-id="1f261-151">Run the application:</span></span>

        - <span data-ttu-id="1f261-152">Vai al **terminale** -> **nuovo terminale**</span><span class="sxs-lookup"><span data-stu-id="1f261-152">Go to **Terminal** -> **New Terminal**</span></span>
        - <span data-ttu-id="1f261-153">Immettere `dotnet run`</span><span class="sxs-lookup"><span data-stu-id="1f261-153">Enter `dotnet run`</span></span>
        - <span data-ttu-id="1f261-154">Nella finestra di output verrà visualizzato il testo seguente: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="1f261-154">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> * <span data-ttu-id="1f261-155">Le aree di lavoro con più cartelle radice non sono attualmente supportate dall'estensione Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="1f261-155">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="1f261-156">Se sono presenti più progetti all'interno di un'area di lavoro di Visual Studio Code, è necessario che tutti i progetti siano contenuti all'interno della stessa cartella radice.</span><span class="sxs-lookup"><span data-stu-id="1f261-156">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <span data-ttu-id="1f261-157">Sviluppare con Q # + C# usando lo strumento da riga di comando `dotnet` <a name="command"></a></span><span class="sxs-lookup"><span data-stu-id="1f261-157">Develop with Q# + C# using the `dotnet` command-line tool <a name="command"></a></span></span>

<span data-ttu-id="1f261-158">Naturalmente, è anche possibile compilare ed eseguire programmi Q# dalla riga di comando installando semplicemente .NET Core SDK e i modelli di progetto QDK.</span><span class="sxs-lookup"><span data-stu-id="1f261-158">Of course, you can also build and run Q# programs from the command line by simply installing the .NET Core SDK and the QDK project templates.</span></span> 

1. <span data-ttu-id="1f261-159">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="1f261-159">Pre-requisites</span></span>

    - [<span data-ttu-id="1f261-160">.NET Core SDK 3,1 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="1f261-160">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="1f261-161">Installare i modelli di progetto di calcolo quantistico per .NET</span><span class="sxs-lookup"><span data-stu-id="1f261-161">Install the Quantum project templates for .NET</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    <span data-ttu-id="1f261-162">Quantum Development Kit è ora installato e pronto per l'uso nelle applicazioni e nelle librerie.</span><span class="sxs-lookup"><span data-stu-id="1f261-162">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="1f261-163">Verificare l'installazione creando un'applicazione `Hello World`</span><span class="sxs-lookup"><span data-stu-id="1f261-163">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="1f261-164">Creare una nuova applicazione</span><span class="sxs-lookup"><span data-stu-id="1f261-164">Create a new application</span></span>

       ```dotnetcli
       dotnet new console -lang "Q#" -o runSayHello
       ```

    - <span data-ttu-id="1f261-165">Passare alla directory della nuova applicazione</span><span class="sxs-lookup"><span data-stu-id="1f261-165">Navigate to the new application directory</span></span>

       ```bash
       cd runSayHello
       ```

    <span data-ttu-id="1f261-166">Si noterà che sono stati creati due file, insieme ai file di progetto dell'applicazione: un file Q# (`Operation.qs`) e un file host C# (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="1f261-166">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

    - <span data-ttu-id="1f261-167">Eseguire l'applicazione</span><span class="sxs-lookup"><span data-stu-id="1f261-167">Run the application</span></span>

        ```dotnetcli
        dotnet run
        ```

        <span data-ttu-id="1f261-168">Verrà visualizzato l'output seguente: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="1f261-168">You should see the following output: `Hello quantum world!`</span></span>

    
## <a name="whats-next"></a><span data-ttu-id="1f261-169">Quali sono le operazioni successive?</span><span class="sxs-lookup"><span data-stu-id="1f261-169">What's next?</span></span>

<span data-ttu-id="1f261-170">Ora che è stato installato Quantum Development Kit nell'ambiente preferito, è possibile scrivere ed eseguire [il primo programma quantistico](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="1f261-170">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
