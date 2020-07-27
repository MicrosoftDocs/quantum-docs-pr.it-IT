---
title: Sviluppare con notebook di Jupyter Q#
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: bbd1f58ba7de205e452be7bac72b5fd78e7acd56
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871451"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="c40ce-102">Sviluppare con notebook di Jupyter Q#</span><span class="sxs-lookup"><span data-stu-id="c40ce-102">Develop with Q# Jupyter Notebooks</span></span>

<span data-ttu-id="c40ce-103">Installare il QDK per sviluppare operazioni Q# nei notebook di Jupyter Q#.</span><span class="sxs-lookup"><span data-stu-id="c40ce-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="c40ce-104">I notebook di Jupyter consentono l'esecuzione di codice sul posto, unitamente a istruzioni, note e altro contenuto.</span><span class="sxs-lookup"><span data-stu-id="c40ce-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="c40ce-105">Questo ambiente è ideale per la scrittura di codice Q# con spiegazioni incorporate o esercitazioni interattive sul calcolo quantistico.</span><span class="sxs-lookup"><span data-stu-id="c40ce-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="c40ce-106">Ecco cosa occorre fare per iniziare a creare notebook Q#.</span><span class="sxs-lookup"><span data-stu-id="c40ce-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

> [!NOTE]
> * <span data-ttu-id="c40ce-107">Nei notebook di Jupyter Q# è possibile eseguire solo codice Q# e non è possibile chiamare operazioni da programmi host esterni, ad esempio file Python o C#.</span><span class="sxs-lookup"><span data-stu-id="c40ce-107">In Q# Jupyter Notebooks, you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="c40ce-108">Questo ambiente non è appropriato se si intende combinare un programma host classico esterno con il programma quantistico.</span><span class="sxs-lookup"><span data-stu-id="c40ce-108">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

## <a name="install-the-iq-jupyter-kernel"></a><span data-ttu-id="c40ce-109">Installare il kernel IQ# per Jupyter</span><span class="sxs-lookup"><span data-stu-id="c40ce-109">Install the IQ# Jupyter kernel</span></span>

<span data-ttu-id="c40ce-110">IQ # (pronunciato i-q-sharp) è un'estensione usata principalmente da Jupyter e Python in .NET Core SDK che fornisce le funzionalità essenziali per la compilazione e la simulazione di operazioni Q#.</span><span class="sxs-lookup"><span data-stu-id="c40ce-110">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

### <a name="install-using-conda-recommended"></a>[<span data-ttu-id="c40ce-111">Installazione con conda (scelta consigliata)</span><span class="sxs-lookup"><span data-stu-id="c40ce-111">Install using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="c40ce-112">Installare [Miniconda](https://docs.conda.io/en/latest/miniconda.html) o [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span><span class="sxs-lookup"><span data-stu-id="c40ce-112">Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span></span> <span data-ttu-id="c40ce-113">**Nota:** è richiesta l'installazione a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="c40ce-113">**Note:** 64-bit installation required.</span></span>

1. <span data-ttu-id="c40ce-114">Aprire un prompt di Anaconda.</span><span class="sxs-lookup"><span data-stu-id="c40ce-114">Open an Anaconda Prompt.</span></span>

   - <span data-ttu-id="c40ce-115">In alternativa, se si preferisce usare PowerShell o pwsh, aprire una shell, eseguire `conda init powershell`, quindi chiudere e riaprire la shell.</span><span class="sxs-lookup"><span data-stu-id="c40ce-115">Or, if you prefer to use PowerShell or pwsh: open a shell, run `conda init powershell`, then close and re-open the shell.</span></span>

1. <span data-ttu-id="c40ce-116">Creare e attivare un nuovo ambiente conda denominato `qsharp-env` con i pacchetti necessari, inclusi Jupyter Notebook e IQ#, eseguendo i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c40ce-116">Create and activate a new conda environment named `qsharp-env` with the required packages (including Jupyter Notebook and IQ#) by running the following commands:</span></span>

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. <span data-ttu-id="c40ce-117">Eseguire `python -c "import qsharp"` dallo stesso terminale per verificare l'installazione e popolare la cache del pacchetto locale con tutti i componenti di QDK necessari.</span><span class="sxs-lookup"><span data-stu-id="c40ce-117">Run `python -c "import qsharp"` from the same terminal to verify your installation and populate your local package cache with all required QDK components.</span></span>

### <a name="install-using-net-cli-advanced"></a>[<span data-ttu-id="c40ce-118">Installazione con l'interfaccia della riga di comando .NET (opzione avanzata)</span><span class="sxs-lookup"><span data-stu-id="c40ce-118">Install using .NET CLI (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="c40ce-119">Prerequisiti:</span><span class="sxs-lookup"><span data-stu-id="c40ce-119">Prerequisites:</span></span>

    - <span data-ttu-id="c40ce-120">[Python](https://www.python.org/downloads/) 3.6 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="c40ce-120">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="c40ce-121">Notebook di Jupyter</span><span class="sxs-lookup"><span data-stu-id="c40ce-121">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="c40ce-122">.NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="c40ce-122">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="c40ce-123">Installare il pacchetto `Microsoft.Quantum.IQSharp`.</span><span class="sxs-lookup"><span data-stu-id="c40ce-123">Install the `Microsoft.Quantum.IQSharp` package.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="c40ce-124">Se durante il passaggio `dotnet iqsharp install` viene visualizzato un errore, aprire una nuova finestra del terminale e riprovare.</span><span class="sxs-lookup"><span data-stu-id="c40ce-124">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="c40ce-125">Se il problema persiste, provare a individuare lo strumento `dotnet-iqsharp` installato (in Windows `dotnet-iqsharp.exe`) ed eseguire:</span><span class="sxs-lookup"><span data-stu-id="c40ce-125">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="c40ce-126">dove `/path/to/dotnet-iqsharp` deve essere sostituito con il percorso assoluto dello strumento `dotnet-iqsharp` nel file system.</span><span class="sxs-lookup"><span data-stu-id="c40ce-126">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="c40ce-127">Tale strumento si trova in genere in `.dotnet/tools` nella cartella del profilo utente.</span><span class="sxs-lookup"><span data-stu-id="c40ce-127">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
    
***

<span data-ttu-id="c40ce-128">L'operazione è terminata.</span><span class="sxs-lookup"><span data-stu-id="c40ce-128">That's it!</span></span> <span data-ttu-id="c40ce-129">È ora disponibile il kernel IQ# per Jupyter, che fornisce la funzionalità di base per la compilazione e l'esecuzione di operazioni Q# da notebook di Jupyter Q#.</span><span class="sxs-lookup"><span data-stu-id="c40ce-129">You now have the IQ# kernel for Jupyter, which provides the core functionality for compiling and executing Q# operations from Q# Jupyter Notebooks.</span></span>

## <a name="create-your-first-q-notebook"></a><span data-ttu-id="c40ce-130">Creare il primo notebook Q#</span><span class="sxs-lookup"><span data-stu-id="c40ce-130">Create your first Q# notebook</span></span>

<span data-ttu-id="c40ce-131">A questo punto è possibile verificare l'installazione del notebook di Jupyter Q# scrivendo ed eseguendo una semplice operazione Q#.</span><span class="sxs-lookup"><span data-stu-id="c40ce-131">Now you are ready to verify your Q# Jupyter Notebook installation by writing and executing a simple Q# operation.</span></span>

1. <span data-ttu-id="c40ce-132">Nell'ambiente creato durante l'installazione, ovvero l'ambiente conda creato o l'ambiente Python in cui è stato installato Jupyter, eseguire il comando seguente per avviare il server di notebook di Jupyter:</span><span class="sxs-lookup"><span data-stu-id="c40ce-132">From the environment you created during installation (i.e., either the conda environment you created, or the Python environment where you installed Jupyter), run the following command to start the Jupyter Notebook server:</span></span>

    ```
    jupyter notebook
    ```

    - <span data-ttu-id="c40ce-133">Se il notebook di Jupyter non si apre automaticamente nel browser, copiare e incollare l'URL fornito dalla riga di comando nel browser.</span><span class="sxs-lookup"><span data-stu-id="c40ce-133">If the Jupyter Notebook doesn't open automatically in your browser, copy and paste the URL provided by the command line into your browser.</span></span>

1. <span data-ttu-id="c40ce-134">Scegliere "Nuovo" → "Q#" per creare un notebook di Jupyter con un kernel Q# e aggiungere il codice seguente nella prima cella del notebook:</span><span class="sxs-lookup"><span data-stu-id="c40ce-134">Choose "New" → "Q#" to create a Jupyter Notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="6-13":::

1. <span data-ttu-id="c40ce-135">Eseguire la cella del notebook:</span><span class="sxs-lookup"><span data-stu-id="c40ce-135">Run this cell of the notebook:</span></span>

    ![Cella di notebook di Jupyter con codice Q#](~/media/install-guide-jupyter.png)

    <span data-ttu-id="c40ce-137">Nell'output della cella verrà visualizzato `SampleQuantumRandomNumberGenerator`.</span><span class="sxs-lookup"><span data-stu-id="c40ce-137">You should see `SampleQuantumRandomNumberGenerator` in the output of the cell.</span></span> <span data-ttu-id="c40ce-138">Quando è in esecuzione in Jupyter Notebook, il codice Q# viene compilato e la cella restituisce il nome di tutte le operazioni che trova.</span><span class="sxs-lookup"><span data-stu-id="c40ce-138">When running in Jupyter Notebook, the Q# code is compiled, and the cell outputs the name of any operations that it finds.</span></span>

1. <span data-ttu-id="c40ce-139">In una nuova cella eseguire l'operazione appena creata (in un simulatore) usando il comando `%simulate`:</span><span class="sxs-lookup"><span data-stu-id="c40ce-139">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

    ![Cella di notebook di Jupyter con il magic %simulate](~/media/install-guide-jupyter-simulate.png)

    <span data-ttu-id="c40ce-141">Verrà visualizzato il risultato dell'operazione richiamata.</span><span class="sxs-lookup"><span data-stu-id="c40ce-141">You should see the result of the operation you invoked.</span></span> <span data-ttu-id="c40ce-142">In questo caso, poiché l'operazione genera un risultato casuale, sullo schermo verrà visualizzato `Zero` o `One`.</span><span class="sxs-lookup"><span data-stu-id="c40ce-142">In this case, because your operation generates a random result, you will see either `Zero` or `One` printed on the screen.</span></span> <span data-ttu-id="c40ce-143">Se la cella viene eseguita ripetutamente, si vedrà ogni risultato per circa la metà del tempo.</span><span class="sxs-lookup"><span data-stu-id="c40ce-143">If you execute the cell repeatedly, you should see each result approximately half the time.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c40ce-144">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="c40ce-144">Next steps</span></span>

<span data-ttu-id="c40ce-145">Ora che è stato installato QDK per notebook di Jupyter Q#, è possibile scrivere ed eseguire il [primo programma quantistico](xref:microsoft.quantum.quickstarts.qrng) scrivendo il codice Q# direttamente nell'ambiente di Jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="c40ce-145">Now that you have installed the QDK for Q# Jupyter Notebooks, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng) by writing Q# code directly within the Jupyter Notebook environment.</span></span>

<span data-ttu-id="c40ce-146">Per altri esempi sulle operazioni che è possibile eseguire con i notebook di Jupyter Q#, vedere:</span><span class="sxs-lookup"><span data-stu-id="c40ce-146">For more examples of what you can do with Q# Jupyter Notebooks, please take a look at:</span></span>

- <span data-ttu-id="c40ce-147">[Introduzione a Q# e Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span><span class="sxs-lookup"><span data-stu-id="c40ce-147">[Intro to Q# and Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span></span> <span data-ttu-id="c40ce-148">Questo articolo include un notebook di Jupyter Q# che fornisce altri dettagli su come usare Q# in questo ambiente.</span><span class="sxs-lookup"><span data-stu-id="c40ce-148">There you will find a Q# Jupyter Notebook that provides more details on how to use Q# in the Jupyter environment.</span></span>
- <span data-ttu-id="c40ce-149">[Quantum Katas](xref:microsoft.quantum.overview.katas), una raccolta open source di esercitazioni autogestite e set di esercizi di programmazione sotto forma di notebook di Jupyter Q#.</span><span class="sxs-lookup"><span data-stu-id="c40ce-149">[Quantum Katas](xref:microsoft.quantum.overview.katas), an open-source collection of self-paced tutorials and sets of programming exercises in the form of Q# Jupyter Notebooks.</span></span> <span data-ttu-id="c40ce-150">I [notebook delle esercitazioni di Quantum Katas](https://github.com/microsoft/QuantumKatas#tutorial-topics) costituiscono un valido punto di partenza.</span><span class="sxs-lookup"><span data-stu-id="c40ce-150">The [Quantum Katas tutorial notebooks](https://github.com/microsoft/QuantumKatas#tutorial-topics) are a good starting point.</span></span> <span data-ttu-id="c40ce-151">Le esercitazioni Quantum Katas sono infatti ideali per apprendere sia i concetti del calcolo quantistico che della programmazione Q#.</span><span class="sxs-lookup"><span data-stu-id="c40ce-151">The Quantum Katas are aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span> <span data-ttu-id="c40ce-152">Si tratta di un ottimo esempio del tipo di contenuto che è possibile creare con i notebook di Jupyter Q#.</span><span class="sxs-lookup"><span data-stu-id="c40ce-152">They're an excellent example of what kind of content you can create with Q# Jupyter Notebooks.</span></span>
