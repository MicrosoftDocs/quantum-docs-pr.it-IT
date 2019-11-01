---
title: Informazioni su come installare Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 3ec53934436b47908fd4d794a98933010f6059a7
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035295"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="f6363-102">Installare Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="f6363-102">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="f6363-103">Informazioni su come installare il Microsoft Quantum Development Kit (QDK), per iniziare a sviluppare con la programmazione quantistica.</span><span class="sxs-lookup"><span data-stu-id="f6363-103">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="f6363-104">Contenuto del QDK:</span><span class="sxs-lookup"><span data-stu-id="f6363-104">The QDK consists of:</span></span>

- <span data-ttu-id="f6363-105">linguaggio di programmazione Q#</span><span class="sxs-lookup"><span data-stu-id="f6363-105">the Q# programming language</span></span>
- <span data-ttu-id="f6363-106">set di librerie che estrapolano le funzionalità complesse in Q#</span><span class="sxs-lookup"><span data-stu-id="f6363-106">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="f6363-107">applicazione host (scritta in Python o in un linguaggio .NET) che esegue operazioni quantistiche scritte in Q#</span><span class="sxs-lookup"><span data-stu-id="f6363-107">a host application (written in Python or a .NET language) that runs quantum operations written in Q#</span></span>
- <span data-ttu-id="f6363-108">strumenti per facilitare lo sviluppo</span><span class="sxs-lookup"><span data-stu-id="f6363-108">tools to facilitate your development</span></span>

<span data-ttu-id="f6363-109">A seconda dell'ambiente di sviluppo scelto, sono disponibili procedure di installazione diverse.</span><span class="sxs-lookup"><span data-stu-id="f6363-109">Depending on your chosen development environment, there are different installation steps.</span></span> <span data-ttu-id="f6363-110">Scegliere l'ambiente nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="f6363-110">Choose your environment from the sections below.</span></span>

## <a name="develop-with-python"></a><span data-ttu-id="f6363-111">Sviluppare con Python</span><span class="sxs-lookup"><span data-stu-id="f6363-111">Develop with Python</span></span>

1. <span data-ttu-id="f6363-112">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="f6363-112">Pre-requisites</span></span>

    - <span data-ttu-id="f6363-113">[Python](https://www.python.org/downloads/) 3.6 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="f6363-113">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="f6363-114">Gestione pacchetti Python [PIP](https://pip.pypa.io/en/stable/installing)</span><span class="sxs-lookup"><span data-stu-id="f6363-114">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="f6363-115">.NET Core SDK 2.1 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="f6363-115">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="f6363-116">Installare il pacchetto `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="f6363-116">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="f6363-117">Installare il pacchetto `qsharp`</span><span class="sxs-lookup"><span data-stu-id="f6363-117">Install the `qsharp` package</span></span>

    ```bash
    pip install qsharp
    ```

1. <span data-ttu-id="f6363-118">Verificare l'installazione creando un'applicazione `Hello World`</span><span class="sxs-lookup"><span data-stu-id="f6363-118">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="f6363-119">Creare un'operazione Q# minima creando un file denominato `Operation.qs` e aggiungendovi il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="f6363-119">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

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

    - <span data-ttu-id="f6363-120">Creare un programma Python denominato `hello_world.py` per chiamare l'operazione `SayHello()` Q#:</span><span class="sxs-lookup"><span data-stu-id="f6363-120">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="f6363-121">Eseguire il programma:</span><span class="sxs-lookup"><span data-stu-id="f6363-121">Run the program:</span></span>

        ```bash
        python hello_world.py
        ```

    - <span data-ttu-id="f6363-122">Verificare l'output.</span><span class="sxs-lookup"><span data-stu-id="f6363-122">Verify the output.</span></span> <span data-ttu-id="f6363-123">Il programma restituirà le righe seguenti:</span><span class="sxs-lookup"><span data-stu-id="f6363-123">Your program should output the following lines:</span></span>

        ```bash
        Hello from quantum world!
       0
       ```

## <a name="develop-with-jupyter-notebooks"></a><span data-ttu-id="f6363-124">Sviluppare con Jupyter Notebooks</span><span class="sxs-lookup"><span data-stu-id="f6363-124">Develop with Jupyter notebooks</span></span>

1. <span data-ttu-id="f6363-125">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="f6363-125">Pre-requisites</span></span>

    - <span data-ttu-id="f6363-126">[Python](https://www.python.org/downloads/) 3.6 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="f6363-126">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="f6363-127">Notebook di Jupyter</span><span class="sxs-lookup"><span data-stu-id="f6363-127">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="f6363-128">.NET Core SDK 2.1 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="f6363-128">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="f6363-129">Installare il pacchetto `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="f6363-129">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="f6363-130">Verificare l'installazione creando un'applicazione `Hello World`</span><span class="sxs-lookup"><span data-stu-id="f6363-130">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="f6363-131">Eseguire il comando seguente per avviare il server Notebook:</span><span class="sxs-lookup"><span data-stu-id="f6363-131">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="f6363-132">Passare all'URL visualizzato nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="f6363-132">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="f6363-133">Ad esempio: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]</span><span class="sxs-lookup"><span data-stu-id="f6363-133">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

    - <span data-ttu-id="f6363-134">Creare un notebook Jupyter con un kernel Q# e aggiungere il codice seguente alla prima cella del notebook:</span><span class="sxs-lookup"><span data-stu-id="f6363-134">Create a Jupyter notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="f6363-135">Eseguire la cella del notebook:</span><span class="sxs-lookup"><span data-stu-id="f6363-135">Run this cell of the notebook:</span></span>

        ![Cella del notebook Jupyter](~/media/install-guide-jupyter.png)

        <span data-ttu-id="f6363-137">Nell'output della cella verrà visualizzato `SayHello`.</span><span class="sxs-lookup"><span data-stu-id="f6363-137">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="f6363-138">Quando è in esecuzione nei notebook Jupyter, il codice Q# viene compilato e il notebook restituisce il nome delle operazioni trovate.</span><span class="sxs-lookup"><span data-stu-id="f6363-138">When running in jupyter notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>

## <a name="develop-with-c-on-windows-using-visual-studio"></a><span data-ttu-id="f6363-139">Sviluppare con C# in Windows, usando Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f6363-139">Develop with C# on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="f6363-140">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="f6363-140">Pre-requisites</span></span>

    - <span data-ttu-id="f6363-141">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, con il carico di lavoro per lo sviluppo multipiattaforma .NET Core abilitato</span><span class="sxs-lookup"><span data-stu-id="f6363-141">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>

1. <span data-ttu-id="f6363-142">Installare l'estensione di Visual Studio per Q#</span><span class="sxs-lookup"><span data-stu-id="f6363-142">Install the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="f6363-143">Scaricare l'[estensione di Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="f6363-143">Download the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="f6363-144">Aggiungere l'estensione a Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f6363-144">Add the extension to Visual Studio</span></span>

1. <span data-ttu-id="f6363-145">Verificare l'installazione creando un'applicazione `Hello World`</span><span class="sxs-lookup"><span data-stu-id="f6363-145">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="f6363-146">Creare una nuova applicazione Q#</span><span class="sxs-lookup"><span data-stu-id="f6363-146">Create a new Q# application</span></span>

        - <span data-ttu-id="f6363-147">Passare a **File** -> **Nuovo** -> **Progetto**</span><span class="sxs-lookup"><span data-stu-id="f6363-147">Go to **File** -> **New** -> **Project**</span></span>
        - <span data-ttu-id="f6363-148">Digitare `Q#` nella casella di ricerca</span><span class="sxs-lookup"><span data-stu-id="f6363-148">Type `Q#` in the search box</span></span>
        - <span data-ttu-id="f6363-149">Selezionare **Applicazione Q#**</span><span class="sxs-lookup"><span data-stu-id="f6363-149">Select **Q# Application**</span></span>
        - <span data-ttu-id="f6363-150">Selezionare **Avanti**</span><span class="sxs-lookup"><span data-stu-id="f6363-150">Select **Next**</span></span>
        - <span data-ttu-id="f6363-151">Scegliere un nome e una posizione per l'applicazione</span><span class="sxs-lookup"><span data-stu-id="f6363-151">Choose a name and location for your application</span></span>
        - <span data-ttu-id="f6363-152">Selezionare **Crea**</span><span class="sxs-lookup"><span data-stu-id="f6363-152">Select **Create**</span></span>

    - <span data-ttu-id="f6363-153">Esaminare il progetto</span><span class="sxs-lookup"><span data-stu-id="f6363-153">Inspect the project</span></span>

        <span data-ttu-id="f6363-154">Si noterà che sono stati creati due file: `Driver.cs`, ovvero l'applicazione host C# e `Operation.qs`, ovvero un programma Q# che definisce una semplice operazione per stampare un messaggio nella console.</span><span class="sxs-lookup"><span data-stu-id="f6363-154">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

    - <span data-ttu-id="f6363-155">Eseguire l'applicazione</span><span class="sxs-lookup"><span data-stu-id="f6363-155">Run the application</span></span>

        - <span data-ttu-id="f6363-156">Selezionare **Debug** -> **Avvia senza eseguire il debug**</span><span class="sxs-lookup"><span data-stu-id="f6363-156">Select **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="f6363-157">Verrà visualizzato il testo `Hello quantum world!` stampato in una finestra della console.</span><span class="sxs-lookup"><span data-stu-id="f6363-157">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="f6363-158">Se sono presenti più progetti all'interno di una soluzione di Visual Studio, è necessario che tutti i progetti contenuti nella soluzione si trovino nella stessa cartella della soluzione o in una delle relative sottocartelle.</span><span class="sxs-lookup"><span data-stu-id="f6363-158">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="develop-with-c-using-vs-code"></a><span data-ttu-id="f6363-159">Sviluppare con C# usando Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f6363-159">Develop with C#, using VS Code</span></span>

1. <span data-ttu-id="f6363-160">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="f6363-160">Pre-requisites</span></span>

   - [<span data-ttu-id="f6363-161">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f6363-161">VS Code</span></span>](https://code.visualstudio.com/download)
   - [<span data-ttu-id="f6363-162">.NET Core SDK 2.1 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="f6363-162">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="f6363-163">Installare l'estensione Visual Studio Code per il calcolo quantistico</span><span class="sxs-lookup"><span data-stu-id="f6363-163">Install the Quantum VS Code extension</span></span>

    - <span data-ttu-id="f6363-164">Installare l'[estensione Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span><span class="sxs-lookup"><span data-stu-id="f6363-164">Install the [VS Code extension](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span></span>

1. <span data-ttu-id="f6363-165">Installare i modelli di progetto di calcolo quantistico:</span><span class="sxs-lookup"><span data-stu-id="f6363-165">Install the Quantum project templates:</span></span>

   - <span data-ttu-id="f6363-166">Passare a **Visualizza** -> **Riquadro comandi**</span><span class="sxs-lookup"><span data-stu-id="f6363-166">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="f6363-167">Selezionare **Q#: Installa modelli di progetto**</span><span class="sxs-lookup"><span data-stu-id="f6363-167">Select **Q#: Install project templates**</span></span>

    <span data-ttu-id="f6363-168">Quantum Development Kit è ora installato e pronto per l'uso nelle applicazioni e nelle librerie.</span><span class="sxs-lookup"><span data-stu-id="f6363-168">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="f6363-169">Verificare l'installazione creando un'applicazione `Hello World`</span><span class="sxs-lookup"><span data-stu-id="f6363-169">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="f6363-170">Creare un nuovo progetto:</span><span class="sxs-lookup"><span data-stu-id="f6363-170">Create a new project:</span></span>

        - <span data-ttu-id="f6363-171">Passare a **Visualizza** -> **Riquadro comandi**</span><span class="sxs-lookup"><span data-stu-id="f6363-171">Go to **View** -> **Command Palette**</span></span>
        - <span data-ttu-id="f6363-172">Selezionare **Q#: Crea nuovo progetto**</span><span class="sxs-lookup"><span data-stu-id="f6363-172">Select **Q#: Create New Project**</span></span>
        - <span data-ttu-id="f6363-173">Passare al percorso del file system in cui si vuole creare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="f6363-173">Navigate to the location on the file system where you would like to create the application</span></span>
        - <span data-ttu-id="f6363-174">Al termine della creazione del progetto, fare clic sul pulsante **Apri nuovo progetto...**</span><span class="sxs-lookup"><span data-stu-id="f6363-174">Click on the **Open new project...** button, once the project has been created</span></span>

    - <span data-ttu-id="f6363-175">Eseguire l'applicazione:</span><span class="sxs-lookup"><span data-stu-id="f6363-175">Run the application:</span></span>

        - <span data-ttu-id="f6363-176">Passare a **Debug** -> **Avvia senza eseguire il debug**</span><span class="sxs-lookup"><span data-stu-id="f6363-176">Go to **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="f6363-177">Nella finestra di output verrà visualizzato il testo seguente: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="f6363-177">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> * > * <span data-ttu-id="f6363-178">Le aree di lavoro con più cartelle radice non sono attualmente supportate dall'estensione Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="f6363-178">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="f6363-179">Se sono presenti più progetti all'interno di un'area di lavoro di Visual Studio Code, è necessario che tutti i progetti siano contenuti all'interno della stessa cartella radice.</span><span class="sxs-lookup"><span data-stu-id="f6363-179">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="f6363-180">Sviluppare con C# usando lo strumento da riga di comando `dotnet`</span><span class="sxs-lookup"><span data-stu-id="f6363-180">Develop with C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="f6363-181">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="f6363-181">Pre-requisites</span></span>

    - [<span data-ttu-id="f6363-182">.NET Core SDK 2.1 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="f6363-182">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="f6363-183">Installare i modelli di progetto di calcolo quantistico per .NET</span><span class="sxs-lookup"><span data-stu-id="f6363-183">Install the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    <span data-ttu-id="f6363-184">Quantum Development Kit è ora installato e pronto per l'uso nelle applicazioni e nelle librerie.</span><span class="sxs-lookup"><span data-stu-id="f6363-184">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="f6363-185">Verificare l'installazione creando un'applicazione `Hello World`</span><span class="sxs-lookup"><span data-stu-id="f6363-185">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="f6363-186">Creare una nuova applicazione</span><span class="sxs-lookup"><span data-stu-id="f6363-186">Create a new application</span></span>

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - <span data-ttu-id="f6363-187">Passare alla directory della nuova applicazione</span><span class="sxs-lookup"><span data-stu-id="f6363-187">Navigate to the new application directory</span></span>

       ```bash
       cd runSayHello
       ```

    <span data-ttu-id="f6363-188">Si noterà che sono stati creati due file, insieme ai file di progetto dell'applicazione: un file Q# (`Operation.qs`) e un file host C# (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="f6363-188">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

    - <span data-ttu-id="f6363-189">Eseguire l'applicazione</span><span class="sxs-lookup"><span data-stu-id="f6363-189">Run the application</span></span>

        ```bash
        dotnet run
        ```

        <span data-ttu-id="f6363-190">Verrà visualizzato l'output seguente: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="f6363-190">You should see the following output: `Hello quantum world!`</span></span>

## <a name="whats-next"></a><span data-ttu-id="f6363-191">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="f6363-191">What's next?</span></span>

<span data-ttu-id="f6363-192">Ora che è stato installato Quantum Development Kit nell'ambiente preferito, è possibile scrivere ed eseguire [il primo programma quantistico](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="f6363-192">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
