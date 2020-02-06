---
title: 'Informazioni su come creare un progetto Q # con Quantum Development Kit (QDK)'
description: "Inizializzare un progetto per lo sviluppo di Quantum con QDK e Q # nell'ambiente di sviluppo scelto"
author: natke
ms.author: nakersha
ms.date: 10/19/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.howto.createproject
ms.openlocfilehash: c093284f1ea33b72d4d264992b0ba6bf6bc72782
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036441"
---
# <a name="create-a-q-project-in-your-development-environment"></a><span data-ttu-id="cc8c2-103">Creare un progetto Q # nell'ambiente di sviluppo</span><span class="sxs-lookup"><span data-stu-id="cc8c2-103">Create a Q# project in your development environment</span></span>

<span data-ttu-id="cc8c2-104">Informazioni su come creare un progetto Q # con QDK.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-104">Learn how to create a Q# project with the QDK.</span></span>

<span data-ttu-id="cc8c2-105">Un progetto Q # contiene file Q # contenenti codice quantico, oltre a un programma host per l'esecuzione del programma Quantum.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-105">A Q# project contains Q# files containing quantum code, as well as a host program to run the quantum program.</span></span> <span data-ttu-id="cc8c2-106">È possibile scrivere il programma host nei linguaggi .NET C#, ad esempio, o in Python.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-106">You can write the host program in .NET languages such as C#, or in Python.</span></span> <span data-ttu-id="cc8c2-107">È anche possibile eseguire il codice Q # in un notebook di Jupyter usando il kernel IQ #.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-107">You can also run Q# code in a Jupyter notebook using the IQ# kernel.</span></span>

<span data-ttu-id="cc8c2-108">Scegliere l'ambiente di sviluppo e la lingua dalle sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cc8c2-108">Choose your development environment and language from the sections below:</span></span>

* [<span data-ttu-id="cc8c2-109">Python</span><span class="sxs-lookup"><span data-stu-id="cc8c2-109">Python</span></span>](#create-a-python-project)
* [<span data-ttu-id="cc8c2-110">Notebook Q # Jupyter</span><span class="sxs-lookup"><span data-stu-id="cc8c2-110">Q# Jupyter notebooks</span></span>](#create-a-q-jupyter-notebook-project)
* [<span data-ttu-id="cc8c2-111">C#con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cc8c2-111">C# with Visual Studio</span></span>](#create-a-c-project-on-windows-using-visual-studio)
* [<span data-ttu-id="cc8c2-112">C#con VS Code</span><span class="sxs-lookup"><span data-stu-id="cc8c2-112">C# with VS Code</span></span>](#create-a-c-project-using-vs-code)
* [<span data-ttu-id="cc8c2-113">C#con la riga di comando</span><span class="sxs-lookup"><span data-stu-id="cc8c2-113">C# with the command line</span></span>](#create-a-c-project-using-the-dotnet-command-line-tool)

## <a name="create-a-python-project"></a><span data-ttu-id="cc8c2-114">Creare un progetto Python</span><span class="sxs-lookup"><span data-stu-id="cc8c2-114">Create a Python project</span></span>

1. <span data-ttu-id="cc8c2-115">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="cc8c2-115">Pre-requisites</span></span>

     * <span data-ttu-id="cc8c2-116">Installare [Quantum Development Kit per Python](xref:microsoft.quantum.install.python)</span><span class="sxs-lookup"><span data-stu-id="cc8c2-116">Install the [Quantum Development Kit for Python](xref:microsoft.quantum.install.python)</span></span>

1. <span data-ttu-id="cc8c2-117">Creare una cartella per il progetto e passare a tale cartella</span><span class="sxs-lookup"><span data-stu-id="cc8c2-117">Create a folder for your project, and navigate to that folder</span></span>

1. <span data-ttu-id="cc8c2-118">Creare un file Q # denominato `Operation.qs`e aggiungervi il codice Q #.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-118">Create a Q# file called `Operation.qs`, and add your Q# code to it.</span></span> <span data-ttu-id="cc8c2-119">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cc8c2-119">For example:</span></span>

    ```qsharp
    namespace HelloWorld {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation SayHello() : Result {
            Message("Hello from quantum world!");
            return Zero;
        }
    }
    ```

1. <span data-ttu-id="cc8c2-120">Creare un file host Python denominato `host.py` per chiamare l'operazione Q #.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-120">Create a python host file called `host.py` to call your Q# operation.</span></span> <span data-ttu-id="cc8c2-121">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cc8c2-121">For example:</span></span>

    ```python
    import qsharp

    from HelloWorld import SayHello

    SayHello.simulate()
    ```

1. <span data-ttu-id="cc8c2-122">Eseguire il programma:</span><span class="sxs-lookup"><span data-stu-id="cc8c2-122">Run the program:</span></span>

    ```bash
    python host.py
    ```

1. <span data-ttu-id="cc8c2-123">Verificare l'output.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-123">Verify the output.</span></span> <span data-ttu-id="cc8c2-124">Il programma restituirà le righe seguenti:</span><span class="sxs-lookup"><span data-stu-id="cc8c2-124">Your program should output the following lines:</span></span>

    ```bash
    Hello from quantum world!
    0
    ```

<span data-ttu-id="cc8c2-125">È ora possibile continuare a sviluppare il programma Quantum.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-125">You can now continue to develop your quantum program.</span></span>

## <a name="create-a-q-jupyter-notebook-project"></a><span data-ttu-id="cc8c2-126">Creare un progetto Q # Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="cc8c2-126">Create a Q# Jupyter Notebook project</span></span>

1. <span data-ttu-id="cc8c2-127">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="cc8c2-127">Pre-requisites</span></span>

    * <span data-ttu-id="cc8c2-128">Installare [Quantum Development Kit per notebook di Jupyter](xref:microsoft.quantum.install.jupyter)</span><span class="sxs-lookup"><span data-stu-id="cc8c2-128">Install the [Quantum Development Kit for Jupyter notebooks](xref:microsoft.quantum.install.jupyter)</span></span>

1. <span data-ttu-id="cc8c2-129">Eseguire il comando seguente per avviare il server Notebook:</span><span class="sxs-lookup"><span data-stu-id="cc8c2-129">Run the following command to start the notebook server:</span></span>

    ```bash
    jupyter notebook
    ```

1. <span data-ttu-id="cc8c2-130">Passare all'URL visualizzato nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-130">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="cc8c2-131">Ad esempio: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span><span class="sxs-lookup"><span data-stu-id="cc8c2-131">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

1. <span data-ttu-id="cc8c2-132">Nel browser viene visualizzata una pagina Jupyter.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-132">A Jupyter page appears in the browser.</span></span> <span data-ttu-id="cc8c2-133">Nella scheda **file** selezionare **nuovo** > **Q #** per creare un notebook di Jupyter con un kernel Q #.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-133">On the **Files** tab, select **New** > **Q#** to create a Jupyter notebook with a Q# kernel.</span></span> <span data-ttu-id="cc8c2-134">Aggiungere il codice seguente alla prima cella del notebook:</span><span class="sxs-lookup"><span data-stu-id="cc8c2-134">Add the following code to the first notebook cell:</span></span>

    ```qsharp
    operation SayHello() : Unit {
        Message("Hello from quantum world!");
    }
    ```

1. <span data-ttu-id="cc8c2-135">Selezionare **cella** > **eseguire celle** per eseguire il notebook.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-135">Select **Cell** > **Run Cells** to run the notebook.</span></span> <span data-ttu-id="cc8c2-136">`SayHello` verrà visualizzato a breve nell'output della cella:</span><span class="sxs-lookup"><span data-stu-id="cc8c2-136">`SayHello` will soon appear in the cell output:</span></span>

    ![Cella di notebook di Jupyter con codice Q#](~/media/install-guide-jupyter.png)

    <span data-ttu-id="cc8c2-138">Quando è in esecuzione in Jupyter notebook, il codice Q # viene compilato e il notebook restituisce il nome delle operazioni trovate.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-138">When running in Jupyter Notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>

1. <span data-ttu-id="cc8c2-139">In una nuova cella simulare in un computer quantistico l'esecuzione dell'operazione appena creata usando il magic `%simulate`:</span><span class="sxs-lookup"><span data-stu-id="cc8c2-139">In a new cell, simulate the execution in a quantum computer of the operation you just created by using the `%simulate` magic:</span></span>

    ![Cella di notebook di Jupyter con il magic %simulate](~/media/install-guide-jupyter-simulate.png)

    <span data-ttu-id="cc8c2-141">Il messaggio verrà visualizzato sullo schermo insieme al risultato dell'operazione richiamata (in questo caso, vuoto).</span><span class="sxs-lookup"><span data-stu-id="cc8c2-141">You should see the message printed on the screen along with the result of the operation you invoked (in this case, empty).</span></span>

<span data-ttu-id="cc8c2-142">È ora possibile aggiungere altre operazioni Q # per continuare lo sviluppo del quantum.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-142">You can now add other Q# operations to continue your quantum development.</span></span>

## <a name="create-a-c-project-on-windows-using-visual-studio"></a><span data-ttu-id="cc8c2-143">Creare un C# progetto in Windows con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cc8c2-143">Create a C# project on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="cc8c2-144">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="cc8c2-144">Pre-requisites</span></span>

    * <span data-ttu-id="cc8c2-145">Installare l' [estensione Quantum Development Kit per Visual Studio](xref:microsoft.quantum.install.cs)</span><span class="sxs-lookup"><span data-stu-id="cc8c2-145">Install the [Quantum Development Kit extension for Visual Studio](xref:microsoft.quantum.install.cs)</span></span>

1. <span data-ttu-id="cc8c2-146">Creare una nuova applicazione Q#</span><span class="sxs-lookup"><span data-stu-id="cc8c2-146">Create a new Q# application</span></span>

    * <span data-ttu-id="cc8c2-147">Passare a **File** -> **Nuovo** -> **Progetto**</span><span class="sxs-lookup"><span data-stu-id="cc8c2-147">Go to **File** -> **New** -> **Project**</span></span>
    * <span data-ttu-id="cc8c2-148">Digitare `Q#` nella casella di ricerca</span><span class="sxs-lookup"><span data-stu-id="cc8c2-148">Type `Q#` in the search box</span></span>
    * <span data-ttu-id="cc8c2-149">Selezionare **Applicazione Q#**</span><span class="sxs-lookup"><span data-stu-id="cc8c2-149">Select **Q# Application**</span></span>
    * <span data-ttu-id="cc8c2-150">Selezionare **Avanti**</span><span class="sxs-lookup"><span data-stu-id="cc8c2-150">Select **Next**</span></span>
    * <span data-ttu-id="cc8c2-151">Scegliere un nome e una posizione per l'applicazione</span><span class="sxs-lookup"><span data-stu-id="cc8c2-151">Choose a name and location for your application</span></span>
    * <span data-ttu-id="cc8c2-152">Selezionare **Crea**</span><span class="sxs-lookup"><span data-stu-id="cc8c2-152">Select **Create**</span></span>

1. <span data-ttu-id="cc8c2-153">Esaminare il progetto</span><span class="sxs-lookup"><span data-stu-id="cc8c2-153">Inspect the project</span></span>

    <span data-ttu-id="cc8c2-154">Si noterà che sono stati creati due file: `Driver.cs`, ovvero l'applicazione host C# e `Operation.qs`, ovvero un programma Q# che definisce una semplice operazione per stampare un messaggio nella console.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-154">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

1. <span data-ttu-id="cc8c2-155">Eseguire l'applicazione</span><span class="sxs-lookup"><span data-stu-id="cc8c2-155">Run the application</span></span>

    * <span data-ttu-id="cc8c2-156">Selezionare **Debug** -> **Avvia senza eseguire il debug**</span><span class="sxs-lookup"><span data-stu-id="cc8c2-156">Select **Debug** -> **Start Without Debugging**</span></span>
    * <span data-ttu-id="cc8c2-157">Verrà visualizzato il testo `Hello quantum world!` stampato in una finestra della console.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-157">You should see the text `Hello quantum world!` printed to a console window.</span></span>

<span data-ttu-id="cc8c2-158">È ora possibile continuare lo sviluppo di Quantum con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cc8c2-158">You can now continue your quantum development using Visual Studio</span></span>

> [!NOTE]
> * <span data-ttu-id="cc8c2-159">Se sono presenti più progetti all'interno di una soluzione di Visual Studio, è necessario che tutti i progetti contenuti nella soluzione si trovino nella stessa cartella della soluzione o in una delle relative sottocartelle.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-159">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="create-a-c-project-using-vs-code"></a><span data-ttu-id="cc8c2-160">Creare un C# progetto utilizzando vs code</span><span class="sxs-lookup"><span data-stu-id="cc8c2-160">Create a C# project, using VS Code</span></span>

1. <span data-ttu-id="cc8c2-161">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="cc8c2-161">Pre-requisites</span></span>

    * <span data-ttu-id="cc8c2-162">Installare l' [estensione del kit di sviluppo di Quantum per vs code](xref:microsoft.quantum.install.cs)</span><span class="sxs-lookup"><span data-stu-id="cc8c2-162">Install the [Quantum Development Kit extension for VS Code](xref:microsoft.quantum.install.cs)</span></span>

1. <span data-ttu-id="cc8c2-163">Creare un nuovo progetto:</span><span class="sxs-lookup"><span data-stu-id="cc8c2-163">Create a new project:</span></span>

    * <span data-ttu-id="cc8c2-164">Passare a **Visualizza** -> **Riquadro comandi**</span><span class="sxs-lookup"><span data-stu-id="cc8c2-164">Go to **View** -> **Command Palette**</span></span>
    * <span data-ttu-id="cc8c2-165">Selezionare **Q #: Crea nuovo progetto**</span><span class="sxs-lookup"><span data-stu-id="cc8c2-165">Select **Q#: Create New Project**</span></span>
    * <span data-ttu-id="cc8c2-166">Seleziona **applicazione console autonoma**</span><span class="sxs-lookup"><span data-stu-id="cc8c2-166">Select **Standalone console application**</span></span>
    * <span data-ttu-id="cc8c2-167">Passare al percorso del file system in cui si vuole creare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="cc8c2-167">Navigate to the location on the file system where you would like to create the application</span></span>
    * <span data-ttu-id="cc8c2-168">Al termine della creazione del progetto, fare clic sul pulsante **Apri nuovo progetto...**</span><span class="sxs-lookup"><span data-stu-id="cc8c2-168">Click on the **Open new project...** button, once the project has been created</span></span>

1. <span data-ttu-id="cc8c2-169">Eseguire l'applicazione:</span><span class="sxs-lookup"><span data-stu-id="cc8c2-169">Run the application:</span></span>

    * <span data-ttu-id="cc8c2-170">Vai al **terminale** -> **nuovo terminale**</span><span class="sxs-lookup"><span data-stu-id="cc8c2-170">Go to **Terminal** -> **New Terminal**</span></span>
    * <span data-ttu-id="cc8c2-171">Immettere `dotnet run`</span><span class="sxs-lookup"><span data-stu-id="cc8c2-171">Enter `dotnet run`</span></span>
    * <span data-ttu-id="cc8c2-172">Nella finestra di output verrà visualizzato il testo seguente: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="cc8c2-172">You should see the following text in the output window `Hello quantum world!`</span></span>

<span data-ttu-id="cc8c2-173">È ora possibile continuare lo sviluppo di Quantum usando Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-173">You can now continue your quantum development using Visual Studio Code.</span></span>

> [!NOTE]
> * <span data-ttu-id="cc8c2-174">Le aree di lavoro con più cartelle radice non sono attualmente supportate dall'estensione Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-174">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="cc8c2-175">Se sono presenti più progetti all'interno di un'area di lavoro di Visual Studio Code, è necessario che tutti i progetti siano contenuti all'interno della stessa cartella radice.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-175">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="create-a-c-project-using-the-dotnet-command-line-tool"></a><span data-ttu-id="cc8c2-176">Creare un C# progetto, usando lo strumento da riga di comando `dotnet`</span><span class="sxs-lookup"><span data-stu-id="cc8c2-176">Create a C# project, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="cc8c2-177">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="cc8c2-177">Pre-requisites</span></span>

    * <span data-ttu-id="cc8c2-178">Installare [Quantum Development Kit per la riga di comando](xref:microsoft.quantum.install.cs)</span><span class="sxs-lookup"><span data-stu-id="cc8c2-178">Install the [Quantum Development Kit for the Command Line](xref:microsoft.quantum.install.cs)</span></span>

1. <span data-ttu-id="cc8c2-179">Creare una nuova applicazione</span><span class="sxs-lookup"><span data-stu-id="cc8c2-179">Create a new application</span></span>

    ```dotnetcli
    dotnet new console -lang Q# -o <project name>
    ```

1. <span data-ttu-id="cc8c2-180">Passare alla directory della nuova applicazione</span><span class="sxs-lookup"><span data-stu-id="cc8c2-180">Navigate to the new application directory</span></span>

    ```bash
    cd <project name>
    ```

    <span data-ttu-id="cc8c2-181">Si noterà che sono stati creati due file, insieme ai file di progetto dell'applicazione: un file Q# (`Operation.qs`) e un file host C# (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="cc8c2-181">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

1. <span data-ttu-id="cc8c2-182">Eseguire l'applicazione</span><span class="sxs-lookup"><span data-stu-id="cc8c2-182">Run the application</span></span>

    ```dotnetcli
    dotnet run
    ```

    <span data-ttu-id="cc8c2-183">Verrà visualizzato l'output seguente: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="cc8c2-183">You should see the following output: `Hello quantum world!`</span></span>

<span data-ttu-id="cc8c2-184">È ora possibile continuare lo sviluppo di Quantum, usando gli strumenti da riga di comando.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-184">You now continue your quantum development, using command line tools.</span></span>

## <a name="whats-next"></a><span data-ttu-id="cc8c2-185">Quali sono le operazioni successive?</span><span class="sxs-lookup"><span data-stu-id="cc8c2-185">What's next?</span></span>

<span data-ttu-id="cc8c2-186">Ora che è stato creato un progetto nell'ambiente preferito, è possibile continuare lo sviluppo di Quantum.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-186">Now that you have created a project in your preferred environment, you can continue your quantum development.</span></span>
