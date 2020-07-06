---
title: Sviluppare con Q# e Python
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 7fbbb81b1ee51bff74b287745bf4447004a0254c
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2020
ms.locfileid: "85885539"
---
# <a name="develop-with-q-and-python"></a><span data-ttu-id="d4ef1-102">Sviluppare con Q# e Python</span><span class="sxs-lookup"><span data-stu-id="d4ef1-102">Develop with Q# and Python</span></span>

<span data-ttu-id="d4ef1-103">Installare il QDK per sviluppare programmi host Python che chiamino operazioni Q#.</span><span class="sxs-lookup"><span data-stu-id="d4ef1-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

## <a name="install-the-qsharp-python-package"></a><span data-ttu-id="d4ef1-104">Installare il pacchetto Python `qsharp`</span><span class="sxs-lookup"><span data-stu-id="d4ef1-104">Install the `qsharp` Python package</span></span>

### <a name="install-using-conda-recommended"></a>[<span data-ttu-id="d4ef1-105">Installazione con conda (scelta consigliata)</span><span class="sxs-lookup"><span data-stu-id="d4ef1-105">Install using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="d4ef1-106">Installare [Miniconda](https://docs.conda.io/en/latest/miniconda.html) o [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span><span class="sxs-lookup"><span data-stu-id="d4ef1-106">Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span></span>

1. <span data-ttu-id="d4ef1-107">Aprire un prompt di Anaconda.</span><span class="sxs-lookup"><span data-stu-id="d4ef1-107">Open an Anaconda Prompt.</span></span>

   - <span data-ttu-id="d4ef1-108">In alternativa, se si preferisce usare PowerShell o pwsh, aprire una shell, eseguire `conda init powershell`, quindi chiudere e riaprire la shell.</span><span class="sxs-lookup"><span data-stu-id="d4ef1-108">Or, if you prefer to use PowerShell or pwsh: open a shell, run `conda init powershell`, then close and re-open the shell.</span></span>

1. <span data-ttu-id="d4ef1-109">Creare e attivare un nuovo ambiente conda denominato `qsharp-env` con i pacchetti necessari, inclusi Jupyter Notebook e IQ#, eseguendo i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4ef1-109">Create and activate a new conda environment named `qsharp-env` with the required packages (including Jupyter Notebook and IQ#) by running the following commands:</span></span>

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. <span data-ttu-id="d4ef1-110">Eseguire `python -c "import qsharp"` dallo stesso terminale per verificare l'installazione e popolare la cache del pacchetto locale con tutti i componenti di QDK necessari.</span><span class="sxs-lookup"><span data-stu-id="d4ef1-110">Run `python -c "import qsharp"` from the same terminal to verify your installation and populate your local package cache with all required QDK components.</span></span>

### <a name="install-using-net-cli-and-pip-advanced"></a>[<span data-ttu-id="d4ef1-111">Installazione con l'interfaccia della riga di comando .NET e pip (opzione avanzata)</span><span class="sxs-lookup"><span data-stu-id="d4ef1-111">Install using .NET CLI and pip (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="d4ef1-112">Prerequisiti:</span><span class="sxs-lookup"><span data-stu-id="d4ef1-112">Prerequisites:</span></span>

    - <span data-ttu-id="d4ef1-113">[Python](https://www.python.org/downloads/) 3.6 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="d4ef1-113">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="d4ef1-114">Gestione pacchetti Python [PIP](https://pip.pypa.io/en/stable/installing)</span><span class="sxs-lookup"><span data-stu-id="d4ef1-114">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="d4ef1-115">.NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="d4ef1-115">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. <span data-ttu-id="d4ef1-116">Installare `qsharp`, un pacchetto Python che consente l'interoperabilità tra Q# e Python.</span><span class="sxs-lookup"><span data-stu-id="d4ef1-116">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```
    pip install qsharp
    ```

1. <span data-ttu-id="d4ef1-117">Installare IQ#, un kernel usato principalmente da Jupyter e Python che fornisce le funzionalità essenziali per la compilazione e l'esecuzione di operazioni Q#.</span><span class="sxs-lookup"><span data-stu-id="d4ef1-117">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="d4ef1-118">Se durante il passaggio `dotnet iqsharp install` viene visualizzato un errore, aprire una nuova finestra del terminale e riprovare.</span><span class="sxs-lookup"><span data-stu-id="d4ef1-118">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="d4ef1-119">Se il problema persiste, provare a individuare lo strumento `dotnet-iqsharp` installato (in Windows `dotnet-iqsharp.exe`) ed eseguire:</span><span class="sxs-lookup"><span data-stu-id="d4ef1-119">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="d4ef1-120">dove `/path/to/dotnet-iqsharp` deve essere sostituito con il percorso assoluto dello strumento `dotnet-iqsharp` nel file system.</span><span class="sxs-lookup"><span data-stu-id="d4ef1-120">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="d4ef1-121">Tale strumento si trova in genere in `.dotnet/tools` nella cartella del profilo utente.</span><span class="sxs-lookup"><span data-stu-id="d4ef1-121">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
    
***

<span data-ttu-id="d4ef1-122">L'operazione è terminata.</span><span class="sxs-lookup"><span data-stu-id="d4ef1-122">That's it!</span></span> <span data-ttu-id="d4ef1-123">Sono ora disponibili il pacchetto Python `qsharp` e il kernel IQ# per Jupyter, che fornisce la funzionalità di base per la compilazione e l'esecuzione di operazioni Q# da Python e consente di usare notebook di Jupyter Q#.</span><span class="sxs-lookup"><span data-stu-id="d4ef1-123">You now have both the `qsharp` Python package and the IQ# kernel for Jupyter, which provides the core functionality for compiling and executing Q# operations from Python and allows you to use Q# Jupyter Notebooks.</span></span>

## <a name="choose-your-ide"></a><span data-ttu-id="d4ef1-124">Scegliere l'IDE</span><span class="sxs-lookup"><span data-stu-id="d4ef1-124">Choose your IDE</span></span>

<span data-ttu-id="d4ef1-125">Anche se è possibile usare Q# con Python in qualsiasi IDE, è consigliabile usare l'IDE di Visual Studio Code (VS Code) per le applicazioni che combinano Q# e Python.</span><span class="sxs-lookup"><span data-stu-id="d4ef1-125">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="d4ef1-126">Con l'estensione QDK di Visual Studio Code è possibile accedere a funzionalità più avanzate, ad esempio avvisi, evidenziazione della sintassi, modelli di progetto e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="d4ef1-126">With the QDK Visual Studio Code extension you gain access to richer functionality such as warnings, syntax highlighting, project templates, and more.</span></span>

<span data-ttu-id="d4ef1-127">Se si vuole usare VS Code:</span><span class="sxs-lookup"><span data-stu-id="d4ef1-127">If you would like to use VS Code:</span></span>

- <span data-ttu-id="d4ef1-128">Installare [VS Code](https://code.visualstudio.com/download) (Windows, Linux e Mac).</span><span class="sxs-lookup"><span data-stu-id="d4ef1-128">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
- <span data-ttu-id="d4ef1-129">Installare l'[estensione QDK per VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="d4ef1-129">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="d4ef1-130">Se si vuole usare un editor diverso, è possibile seguire le istruzioni sopra riportate.</span><span class="sxs-lookup"><span data-stu-id="d4ef1-130">If you would like to use a different editor, the instructions above have you all set.</span></span>

## <a name="write-your-first-q-program"></a><span data-ttu-id="d4ef1-131">Scrivere il primo programma Q#</span><span class="sxs-lookup"><span data-stu-id="d4ef1-131">Write your first Q# program</span></span>

<span data-ttu-id="d4ef1-132">A questo punto è possibile verificare l'installazione del pacchetto Python `qsharp` scrivendo ed eseguendo un semplice programma Q#.</span><span class="sxs-lookup"><span data-stu-id="d4ef1-132">Now you are ready to verify your `qsharp` Python package installation by writing and executing a simple Q# program.</span></span>

1. <span data-ttu-id="d4ef1-133">Creare un'operazione Q# minima creando un file denominato `Operation.qs` e aggiungendovi il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="d4ef1-133">Create a minimal Q# operation by creating a file called `Operation.qs` and adding the following code to it:</span></span>

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="3-14":::

1. <span data-ttu-id="d4ef1-134">Nella stessa cartella di `Operation.qs`creare un programma Python denominato `host.py` per simulare l'operazione `SampleQuantumRandomNumberGenerator()` Q#:</span><span class="sxs-lookup"><span data-stu-id="d4ef1-134">In the same folder as `Operation.qs`, create a Python program called `host.py` to simulate the Q# `SampleQuantumRandomNumberGenerator()` operation:</span></span>

    ```python
    import qsharp
    from Qrng import SampleQuantumRandomNumberGenerator

    SampleQuantumRandomNumberGenerator.simulate()
    ```

1. <span data-ttu-id="d4ef1-135">Nell'ambiente creato durante l'installazione, ovvero l'ambiente conda o l'ambiente Python in cui è stato installato `qsharp`, eseguire il programma:</span><span class="sxs-lookup"><span data-stu-id="d4ef1-135">From the environment you created during installation (i.e., the conda or Python environment where you installed `qsharp`), run the program:</span></span>

    ```
    python host.py
    ```

1. <span data-ttu-id="d4ef1-136">Verrà visualizzato il risultato dell'operazione richiamata.</span><span class="sxs-lookup"><span data-stu-id="d4ef1-136">You should see the result of the operation you invoked.</span></span> <span data-ttu-id="d4ef1-137">In questo caso, poiché l'operazione genera un risultato casuale, sullo schermo verrà visualizzato `Zero` o `One`.</span><span class="sxs-lookup"><span data-stu-id="d4ef1-137">In this case, because your operation generates a random result, you will see either `Zero` or `One` printed on the screen.</span></span> <span data-ttu-id="d4ef1-138">Se il programma viene eseguito ripetutamente, si vedrà ogni risultato per circa la metà del tempo.</span><span class="sxs-lookup"><span data-stu-id="d4ef1-138">If you execute the program repeatedly, you should see each result approximately half the time.</span></span>

> [!NOTE]
> * <span data-ttu-id="d4ef1-139">Il codice Python è un normale programma Python.</span><span class="sxs-lookup"><span data-stu-id="d4ef1-139">The Python code is just a normal Python program.</span></span> <span data-ttu-id="d4ef1-140">Per scrivere il programma Python e chiamare le operazioni Q#, è possibile usare qualsiasi ambiente Python, inclusi i notebook di Jupyter basati su Python.</span><span class="sxs-lookup"><span data-stu-id="d4ef1-140">You can use any Python environment, including Python-based Jupyter Notebooks, to write the Python program and call Q# operations.</span></span> <span data-ttu-id="d4ef1-141">Il programma Python può importare operazioni Q# da qualsiasi file con estensione qs situato nella stessa cartella del codice Python.</span><span class="sxs-lookup"><span data-stu-id="d4ef1-141">The Python program can import Q# operations from any .qs files located in the same folder as the Python code itself.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d4ef1-142">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="d4ef1-142">Next steps</span></span>

<span data-ttu-id="d4ef1-143">Ora che è stato installato Quantum Development Kit nell'ambiente preferito, è possibile seguire questa esercitazione per scrivere ed eseguire [il primo programma quantistico](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="d4ef1-143">Now that you have installed the Quantum Development Kit in your preferred environment, you can follow this tutorial to write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
