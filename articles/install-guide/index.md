---
title: Informazioni su come installare Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 580ac14f2e839d723884a96e9c5fd336ebcb5da0
ms.sourcegitcommit: 30fcb35986b43388ad65dfb876eb3ad8ad0533ce
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73799155"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="1ad72-102">Installare Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="1ad72-102">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="1ad72-103">Informazioni su come installare il Microsoft Quantum Development Kit (QDK), per iniziare a sviluppare con la programmazione quantistica.</span><span class="sxs-lookup"><span data-stu-id="1ad72-103">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="1ad72-104">Contenuto del QDK:</span><span class="sxs-lookup"><span data-stu-id="1ad72-104">The QDK consists of:</span></span>

- <span data-ttu-id="1ad72-105">linguaggio di programmazione Q#</span><span class="sxs-lookup"><span data-stu-id="1ad72-105">the Q# programming language</span></span>
- <span data-ttu-id="1ad72-106">set di librerie che estrapolano le funzionalità complesse in Q#</span><span class="sxs-lookup"><span data-stu-id="1ad72-106">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="1ad72-107">applicazione host (scritta in Python o in un linguaggio .NET) che esegue operazioni quantistiche scritte in Q#</span><span class="sxs-lookup"><span data-stu-id="1ad72-107">a host application (written in Python or a .NET language) that runs quantum operations written in Q#</span></span>
- <span data-ttu-id="1ad72-108">strumenti per facilitare lo sviluppo</span><span class="sxs-lookup"><span data-stu-id="1ad72-108">tools to facilitate your development</span></span>

<span data-ttu-id="1ad72-109">A seconda dell'ambiente di sviluppo scelto, sono disponibili procedure di installazione diverse.</span><span class="sxs-lookup"><span data-stu-id="1ad72-109">Depending on your chosen development environment, there are different installation steps.</span></span> <span data-ttu-id="1ad72-110">Scegliere l'ambiente nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="1ad72-110">Choose your environment from the sections below.</span></span>

## <a name="develop-with-python"></a><span data-ttu-id="1ad72-111">Sviluppare con Python</span><span class="sxs-lookup"><span data-stu-id="1ad72-111">Develop with Python</span></span>

<span data-ttu-id="1ad72-112">Il pacchetto qsharp per Python semplifica la simulazione di operazioni e funzioni Q# all'interno di Python.</span><span class="sxs-lookup"><span data-stu-id="1ad72-112">The qsharp package for Python makes it easy to simulate Q# operations and functions from within Python.</span></span> <span data-ttu-id="1ad72-113">IQ # (pronunciato i-q-sharp) è un'estensione usata principalmente da Jupyter e Python che fornisce le funzionalità essenziali per la compilazione e la simulazione di operazioni Q#.</span><span class="sxs-lookup"><span data-stu-id="1ad72-113">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python that provides the core functionality for compiling and simulating Q# operations.</span></span>

1. <span data-ttu-id="1ad72-114">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="1ad72-114">Pre-requisites</span></span>

    - <span data-ttu-id="1ad72-115">[Python](https://www.python.org/downloads/) 3.6 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="1ad72-115">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="1ad72-116">Gestione pacchetti Python [PIP](https://pip.pypa.io/en/stable/installing)</span><span class="sxs-lookup"><span data-stu-id="1ad72-116">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="1ad72-117">.NET Core SDK 3.0 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="1ad72-117">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="1ad72-118">Installare il pacchetto `qsharp`</span><span class="sxs-lookup"><span data-stu-id="1ad72-118">Install the `qsharp` package</span></span>

    ```bash
    pip install qsharp
    ```

1. <span data-ttu-id="1ad72-119">Installare il pacchetto `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="1ad72-119">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="1ad72-120">Verificare l'installazione creando un'applicazione `Hello World`</span><span class="sxs-lookup"><span data-stu-id="1ad72-120">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="1ad72-121">Creare un'operazione Q# minima creando un file denominato `Operation.qs` e aggiungendovi il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="1ad72-121">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld
        {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Result {
                Message("Hello from quantum world!");
                return Zero;
            }
        }
        ```

    - <span data-ttu-id="1ad72-122">Creare un programma Python denominato `hello_world.py` per chiamare l'operazione `SayHello()` Q#:</span><span class="sxs-lookup"><span data-stu-id="1ad72-122">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="1ad72-123">Eseguire il programma:</span><span class="sxs-lookup"><span data-stu-id="1ad72-123">Run the program:</span></span>

        ```bash
        python hello_world.py
        ```

    - <span data-ttu-id="1ad72-124">Verificare l'output.</span><span class="sxs-lookup"><span data-stu-id="1ad72-124">Verify the output.</span></span> <span data-ttu-id="1ad72-125">Il programma restituirà le righe seguenti:</span><span class="sxs-lookup"><span data-stu-id="1ad72-125">Your program should output the following lines:</span></span>

        ```bash
        Hello from quantum world!
       0
       ```

## <a name="develop-with-jupyter-notebooks"></a><span data-ttu-id="1ad72-126">Sviluppare con Jupyter Notebooks</span><span class="sxs-lookup"><span data-stu-id="1ad72-126">Develop with Jupyter notebooks</span></span>

<span data-ttu-id="1ad72-127">Jupyter Notebook, una delle applicazioni più apprezzate in ambienti accademici, laboratori scientifici e siti di programmazione collaborativa online, offre l'esecuzione di codice sul posto, ora anche del codice Q#, oltre a istruzioni, note e altri contenuti.</span><span class="sxs-lookup"><span data-stu-id="1ad72-127">A favorite of academic settings, scientific labs, and online-based collaborative programming, Jupyter Notebooks offer in-place code execution—now including Q# code—along with instructions, notes, and other content.</span></span>  <span data-ttu-id="1ad72-128">Ecco cosa occorre fare per iniziare a creare notebook Q#.</span><span class="sxs-lookup"><span data-stu-id="1ad72-128">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="1ad72-129">IQ # (pronunciato i-q-sharp) è un'estensione usata principalmente da Jupyter e Python in .NET Core SDK che fornisce le funzionalità essenziali per la compilazione e la simulazione di operazioni Q#.</span><span class="sxs-lookup"><span data-stu-id="1ad72-129">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>


1. <span data-ttu-id="1ad72-130">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="1ad72-130">Pre-requisites</span></span>

    - <span data-ttu-id="1ad72-131">[Python](https://www.python.org/downloads/) 3.6 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="1ad72-131">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="1ad72-132">Notebook di Jupyter</span><span class="sxs-lookup"><span data-stu-id="1ad72-132">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="1ad72-133">.NET Core SDK 3.0 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="1ad72-133">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="1ad72-134">Installare il pacchetto `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="1ad72-134">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="1ad72-135">Verificare l'installazione creando un'applicazione `Hello World`</span><span class="sxs-lookup"><span data-stu-id="1ad72-135">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="1ad72-136">Eseguire il comando seguente per avviare il server Notebook:</span><span class="sxs-lookup"><span data-stu-id="1ad72-136">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="1ad72-137">Passare all'URL visualizzato nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="1ad72-137">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="1ad72-138">Ad esempio: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]</span><span class="sxs-lookup"><span data-stu-id="1ad72-138">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

    - <span data-ttu-id="1ad72-139">Creare un notebook Jupyter con un kernel Q# e aggiungere il codice seguente alla prima cella del notebook:</span><span class="sxs-lookup"><span data-stu-id="1ad72-139">Create a Jupyter notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="1ad72-140">Eseguire la cella del notebook:</span><span class="sxs-lookup"><span data-stu-id="1ad72-140">Run this cell of the notebook:</span></span>

        ![Cella di notebook di Jupyter con codice Q#](~/media/install-guide-jupyter.png)

        <span data-ttu-id="1ad72-142">Nell'output della cella verrà visualizzato `SayHello`.</span><span class="sxs-lookup"><span data-stu-id="1ad72-142">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="1ad72-143">Quando è in esecuzione nei notebook Jupyter, il codice Q# viene compilato e il notebook restituisce il nome delle operazioni trovate.</span><span class="sxs-lookup"><span data-stu-id="1ad72-143">When running in jupyter notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="1ad72-144">In una nuova cella simulare in un computer quantistico l'esecuzione dell'operazione appena creata usando il magic `%simulate`:</span><span class="sxs-lookup"><span data-stu-id="1ad72-144">In a new cell, simulate the execution in a quantum computer of the operation you just created by using the `%simulate` magic:</span></span>

        ![Cella di notebook di Jupyter con il magic %simulate](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="1ad72-146">Il messaggio verrà visualizzato sullo schermo insieme al risultato dell'operazione richiamata (in questo caso, vuoto).</span><span class="sxs-lookup"><span data-stu-id="1ad72-146">You should see the message printed on the screen along with the result of the operation you invoked (in this case, empty).</span></span>


## <a name="develop-with-c-on-windows-using-visual-studio"></a><span data-ttu-id="1ad72-147">Sviluppare con C# in Windows, usando Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1ad72-147">Develop with C# on Windows, using Visual Studio</span></span>

<span data-ttu-id="1ad72-148">Visual Studio offre un ambiente completo per lo sviluppo di programmi Q#, con funzionalità avanzate come il completamento del codice e l'evidenziazione della sintassi che guidano lo sviluppatore nella compilazione delle sue applicazioni.</span><span class="sxs-lookup"><span data-stu-id="1ad72-148">Visual Studio offers a rich environment for developing Q# programs, offering great features like code completion and syntax highlighting that guide the developer in building their applications.</span></span>  <span data-ttu-id="1ad72-149">L'estensione Q# di Visual Studio contiene i modelli per i file e i progetti Q#, oltre al supporto per l'evidenziazione della sintassi e per IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="1ad72-149">The Q# Visual Studio extension contains templates for Q# files and projects as well as syntax highlighting and IntelliSense support.</span></span>


1. <span data-ttu-id="1ad72-150">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="1ad72-150">Pre-requisites</span></span>

    - <span data-ttu-id="1ad72-151">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, con il carico di lavoro per lo sviluppo multipiattaforma .NET Core abilitato</span><span class="sxs-lookup"><span data-stu-id="1ad72-151">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>

1. <span data-ttu-id="1ad72-152">Installare l'estensione di Visual Studio per Q#</span><span class="sxs-lookup"><span data-stu-id="1ad72-152">Install the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="1ad72-153">Scaricare l'[estensione di Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="1ad72-153">Download the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="1ad72-154">Aggiungere l'estensione a Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1ad72-154">Add the extension to Visual Studio</span></span>

1. <span data-ttu-id="1ad72-155">Verificare l'installazione creando un'applicazione `Hello World`</span><span class="sxs-lookup"><span data-stu-id="1ad72-155">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="1ad72-156">Creare una nuova applicazione Q#</span><span class="sxs-lookup"><span data-stu-id="1ad72-156">Create a new Q# application</span></span>

        - <span data-ttu-id="1ad72-157">Passare a **File** -> **Nuovo** -> **Progetto**</span><span class="sxs-lookup"><span data-stu-id="1ad72-157">Go to **File** -> **New** -> **Project**</span></span>
        - <span data-ttu-id="1ad72-158">Digitare `Q#` nella casella di ricerca</span><span class="sxs-lookup"><span data-stu-id="1ad72-158">Type `Q#` in the search box</span></span>
        - <span data-ttu-id="1ad72-159">Selezionare **Applicazione Q#**</span><span class="sxs-lookup"><span data-stu-id="1ad72-159">Select **Q# Application**</span></span>
        - <span data-ttu-id="1ad72-160">Selezionare **Avanti**</span><span class="sxs-lookup"><span data-stu-id="1ad72-160">Select **Next**</span></span>
        - <span data-ttu-id="1ad72-161">Scegliere un nome e una posizione per l'applicazione</span><span class="sxs-lookup"><span data-stu-id="1ad72-161">Choose a name and location for your application</span></span>
        - <span data-ttu-id="1ad72-162">Selezionare **Crea**</span><span class="sxs-lookup"><span data-stu-id="1ad72-162">Select **Create**</span></span>

    - <span data-ttu-id="1ad72-163">Esaminare il progetto</span><span class="sxs-lookup"><span data-stu-id="1ad72-163">Inspect the project</span></span>

        <span data-ttu-id="1ad72-164">Si noterà che sono stati creati due file: `Driver.cs`, ovvero l'applicazione host C# e `Operation.qs`, ovvero un programma Q# che definisce una semplice operazione per stampare un messaggio nella console.</span><span class="sxs-lookup"><span data-stu-id="1ad72-164">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

    - <span data-ttu-id="1ad72-165">Eseguire l'applicazione</span><span class="sxs-lookup"><span data-stu-id="1ad72-165">Run the application</span></span>

        - <span data-ttu-id="1ad72-166">Selezionare **Debug** -> **Avvia senza eseguire il debug**</span><span class="sxs-lookup"><span data-stu-id="1ad72-166">Select **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="1ad72-167">Verrà visualizzato il testo `Hello quantum world!` stampato in una finestra della console.</span><span class="sxs-lookup"><span data-stu-id="1ad72-167">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="1ad72-168">Se sono presenti più progetti all'interno di una soluzione di Visual Studio, è necessario che tutti i progetti contenuti nella soluzione si trovino nella stessa cartella della soluzione o in una delle relative sottocartelle.</span><span class="sxs-lookup"><span data-stu-id="1ad72-168">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="develop-with-c-using-visual-studio-code"></a><span data-ttu-id="1ad72-169">Sviluppare con C# in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="1ad72-169">Develop with C#, using Visual Studio Code</span></span>

<span data-ttu-id="1ad72-170">Visual Studio Code (VS Code) offre un ambiente completo per lo sviluppo di programmi Q# in molti ambienti di calcolo diversi, tra cui Windows, Linux e Mac, con funzionalità avanzate come il completamento del codice e l'evidenziazione della sintassi che guidano lo sviluppatore nella compilazione delle sue applicazioni.</span><span class="sxs-lookup"><span data-stu-id="1ad72-170">Visual Studio Code (VS Code) offers a rich environment for developing Q# programs across many multiple computer environments, including Windows, Linux and Mac, offering great features like code completion and syntax highlighting that guide the developer in building their applications.</span></span>  <span data-ttu-id="1ad72-171">L'estensione Q# di VS Code contiene l'evidenziazione della sintassi e i frammenti di codice Q#.</span><span class="sxs-lookup"><span data-stu-id="1ad72-171">The Q# VS Code extension contains syntax highlighting, and Q# code snippets.</span></span>

1. <span data-ttu-id="1ad72-172">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="1ad72-172">Pre-requisites</span></span>

   - [<span data-ttu-id="1ad72-173">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="1ad72-173">VS Code</span></span>](https://code.visualstudio.com/download)
   - [<span data-ttu-id="1ad72-174">.NET Core SDK 3.0 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="1ad72-174">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="1ad72-175">Installare l'estensione Visual Studio Code per il calcolo quantistico</span><span class="sxs-lookup"><span data-stu-id="1ad72-175">Install the Quantum VS Code extension</span></span>

    - <span data-ttu-id="1ad72-176">Installare l'[estensione Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span><span class="sxs-lookup"><span data-stu-id="1ad72-176">Install the [VS Code extension](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span></span>

1. <span data-ttu-id="1ad72-177">Installare i modelli di progetto di calcolo quantistico:</span><span class="sxs-lookup"><span data-stu-id="1ad72-177">Install the Quantum project templates:</span></span>

   - <span data-ttu-id="1ad72-178">Passare a **Visualizza** -> **Riquadro comandi**</span><span class="sxs-lookup"><span data-stu-id="1ad72-178">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="1ad72-179">Selezionare **Q#: Installa modelli di progetto**</span><span class="sxs-lookup"><span data-stu-id="1ad72-179">Select **Q#: Install project templates**</span></span>

    <span data-ttu-id="1ad72-180">Quantum Development Kit è ora installato e pronto per l'uso nelle applicazioni e nelle librerie.</span><span class="sxs-lookup"><span data-stu-id="1ad72-180">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="1ad72-181">Verificare l'installazione creando un'applicazione `Hello World`</span><span class="sxs-lookup"><span data-stu-id="1ad72-181">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="1ad72-182">Creare un nuovo progetto:</span><span class="sxs-lookup"><span data-stu-id="1ad72-182">Create a new project:</span></span>

        - <span data-ttu-id="1ad72-183">Passare a **Visualizza** -> **Riquadro comandi**</span><span class="sxs-lookup"><span data-stu-id="1ad72-183">Go to **View** -> **Command Palette**</span></span>
        - <span data-ttu-id="1ad72-184">Selezionare **Q#: Crea nuovo progetto**</span><span class="sxs-lookup"><span data-stu-id="1ad72-184">Select **Q#: Create New Project**</span></span>
        - <span data-ttu-id="1ad72-185">Passare al percorso del file system in cui si vuole creare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="1ad72-185">Navigate to the location on the file system where you would like to create the application</span></span>
        - <span data-ttu-id="1ad72-186">Al termine della creazione del progetto, fare clic sul pulsante **Apri nuovo progetto...**</span><span class="sxs-lookup"><span data-stu-id="1ad72-186">Click on the **Open new project...** button, once the project has been created</span></span>

    - <span data-ttu-id="1ad72-187">Eseguire l'applicazione:</span><span class="sxs-lookup"><span data-stu-id="1ad72-187">Run the application:</span></span>

        - <span data-ttu-id="1ad72-188">Passare a **Debug** -> **Avvia senza eseguire il debug**</span><span class="sxs-lookup"><span data-stu-id="1ad72-188">Go to **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="1ad72-189">Nella finestra di output verrà visualizzato il testo seguente: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="1ad72-189">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> * > * <span data-ttu-id="1ad72-190">Le aree di lavoro con più cartelle radice non sono attualmente supportate dall'estensione Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="1ad72-190">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="1ad72-191">Se sono presenti più progetti all'interno di un'area di lavoro di Visual Studio Code, è necessario che tutti i progetti siano contenuti all'interno della stessa cartella radice.</span><span class="sxs-lookup"><span data-stu-id="1ad72-191">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="1ad72-192">Sviluppare con C# usando lo strumento da riga di comando `dotnet`</span><span class="sxs-lookup"><span data-stu-id="1ad72-192">Develop with C#, using the `dotnet` command-line tool</span></span>

<span data-ttu-id="1ad72-193">Naturalmente, è anche possibile compilare ed eseguire programmi Q# dalla riga di comando installando semplicemente .NET Core SDK e i modelli di progetto QDK.</span><span class="sxs-lookup"><span data-stu-id="1ad72-193">Of course, you can also build and run Q# programs from the command line by simply installing the .NET Core SDK and the QDK project templates.</span></span> 

1. <span data-ttu-id="1ad72-194">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="1ad72-194">Pre-requisites</span></span>

    - [<span data-ttu-id="1ad72-195">.NET Core SDK 3.0 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="1ad72-195">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="1ad72-196">Installare i modelli di progetto di calcolo quantistico per .NET</span><span class="sxs-lookup"><span data-stu-id="1ad72-196">Install the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    <span data-ttu-id="1ad72-197">Quantum Development Kit è ora installato e pronto per l'uso nelle applicazioni e nelle librerie.</span><span class="sxs-lookup"><span data-stu-id="1ad72-197">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="1ad72-198">Verificare l'installazione creando un'applicazione `Hello World`</span><span class="sxs-lookup"><span data-stu-id="1ad72-198">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="1ad72-199">Creare una nuova applicazione</span><span class="sxs-lookup"><span data-stu-id="1ad72-199">Create a new application</span></span>

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - <span data-ttu-id="1ad72-200">Passare alla directory della nuova applicazione</span><span class="sxs-lookup"><span data-stu-id="1ad72-200">Navigate to the new application directory</span></span>

       ```bash
       cd runSayHello
       ```

    <span data-ttu-id="1ad72-201">Si noterà che sono stati creati due file, insieme ai file di progetto dell'applicazione: un file Q# (`Operation.qs`) e un file host C# (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="1ad72-201">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

    - <span data-ttu-id="1ad72-202">Eseguire l'applicazione</span><span class="sxs-lookup"><span data-stu-id="1ad72-202">Run the application</span></span>

        ```bash
        dotnet run
        ```

        <span data-ttu-id="1ad72-203">Verrà visualizzato l'output seguente: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="1ad72-203">You should see the following output: `Hello quantum world!`</span></span>

## <a name="whats-next"></a><span data-ttu-id="1ad72-204">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="1ad72-204">What's next?</span></span>

<span data-ttu-id="1ad72-205">Ora che è stato installato Quantum Development Kit nell'ambiente preferito, è possibile scrivere ed eseguire [il primo programma quantistico](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="1ad72-205">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
