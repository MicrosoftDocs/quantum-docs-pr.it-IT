---
title: Sviluppare con Q# + Jupyter Notebooks
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: b80d95a160b5f46c1132d3428ba32ad6dcd5656e
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630339"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="c0fa5-102">Sviluppare con Q# + Jupyter Notebooks</span><span class="sxs-lookup"><span data-stu-id="c0fa5-102">Develop with Q# Jupyter Notebooks</span></span>

<span data-ttu-id="c0fa5-103">Installare QDK per lo sviluppo di operazioni Q # nei notebook Q # Jupyter.</span><span class="sxs-lookup"><span data-stu-id="c0fa5-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="c0fa5-104">I notebook di Jupyter consentono l'esecuzione di codice sul posto insieme a istruzioni, note e altro contenuto.</span><span class="sxs-lookup"><span data-stu-id="c0fa5-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="c0fa5-105">Questo ambiente è ideale per la scrittura di codice Q # con spiegazioni incorporate o esercitazioni interattive di quantum computing.</span><span class="sxs-lookup"><span data-stu-id="c0fa5-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="c0fa5-106">Ecco cosa occorre fare per iniziare a creare notebook Q#.</span><span class="sxs-lookup"><span data-stu-id="c0fa5-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="c0fa5-107">IQ # (pronunciato i-q-sharp) è un'estensione usata principalmente da Jupyter e Python in .NET Core SDK che fornisce le funzionalità essenziali per la compilazione e la simulazione di operazioni Q#.</span><span class="sxs-lookup"><span data-stu-id="c0fa5-107">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

> [!NOTE]
> * <span data-ttu-id="c0fa5-108">Nei notebook Q # Jupyter è possibile eseguire solo il codice Q # e non è possibile chiamare le operazioni da programmi host esterni, ad esempio file Python o C#.</span><span class="sxs-lookup"><span data-stu-id="c0fa5-108">In Q# Jupyter Notebooks you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="c0fa5-109">Questo ambiente non è appropriato se l'obiettivo consiste nel combinare un programma host classico esterno con il programma Quantum.</span><span class="sxs-lookup"><span data-stu-id="c0fa5-109">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

1. <span data-ttu-id="c0fa5-110">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="c0fa5-110">Prerequisites</span></span>

    - <span data-ttu-id="c0fa5-111">[Python](https://www.python.org/downloads/) 3,6 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="c0fa5-111">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="c0fa5-112">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="c0fa5-112">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="c0fa5-113">.NET Core SDK 3,1</span><span class="sxs-lookup"><span data-stu-id="c0fa5-113">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="c0fa5-114">Installare il pacchetto `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="c0fa5-114">Install the `iqsharp` package</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="c0fa5-115">Se viene visualizzato un errore durante il `dotnet iqsharp install` passaggio, aprire una nuova finestra del terminale e riprovare.</span><span class="sxs-lookup"><span data-stu-id="c0fa5-115">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="c0fa5-116">Se questa operazione non funziona ancora, provare a individuare lo `dotnet-iqsharp` strumento installato (in Windows `dotnet-iqsharp.exe` ) e a eseguire:</span><span class="sxs-lookup"><span data-stu-id="c0fa5-116">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="c0fa5-117">dove `/path/to/dotnet-iqsharp` deve essere sostituito con il percorso assoluto dello `dotnet-iqsharp` strumento nel file System.</span><span class="sxs-lookup"><span data-stu-id="c0fa5-117">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="c0fa5-118">Questa operazione si trova in genere `.dotnet/tools` nella cartella del profilo utente.</span><span class="sxs-lookup"><span data-stu-id="c0fa5-118">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>

1. <span data-ttu-id="c0fa5-119">Verificare l'installazione creando un'applicazione `Hello World`</span><span class="sxs-lookup"><span data-stu-id="c0fa5-119">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="c0fa5-120">Eseguire il comando seguente per avviare il server Notebook:</span><span class="sxs-lookup"><span data-stu-id="c0fa5-120">Run the following command to start the notebook server:</span></span>

        ```
        jupyter notebook
        ```

    - <span data-ttu-id="c0fa5-121">Per aprire la Jupyter Notebook, copiare e incollare l'URL fornito dalla riga di comando nel browser.</span><span class="sxs-lookup"><span data-stu-id="c0fa5-121">To open the Jupyter Notebook, copy and paste the URL provided by the command line into your browser.</span></span>

    - <span data-ttu-id="c0fa5-122">Creare una Jupyter Notebook con un kernel Q # e aggiungere il codice seguente alla prima cella del notebook:</span><span class="sxs-lookup"><span data-stu-id="c0fa5-122">Create a Jupyter Notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="c0fa5-123">Eseguire la cella del notebook:</span><span class="sxs-lookup"><span data-stu-id="c0fa5-123">Run this cell of the notebook:</span></span>

        ![Jupyter Notebook cella con codice Q #](~/media/install-guide-jupyter.png)

        <span data-ttu-id="c0fa5-125">Nell'output della cella verrà visualizzato `SayHello`.</span><span class="sxs-lookup"><span data-stu-id="c0fa5-125">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="c0fa5-126">Quando è in esecuzione in Jupyter Notebook, il codice Q # viene compilato e il notebook restituisce il nome delle operazioni trovate.</span><span class="sxs-lookup"><span data-stu-id="c0fa5-126">When running in Jupyter Notebook, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="c0fa5-127">In una nuova cella, eseguire l'operazione appena creata (in un simulatore) usando il `%simulate` comando:</span><span class="sxs-lookup"><span data-stu-id="c0fa5-127">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

        ![Jupyter Notebook cella con% simulare Magic](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="c0fa5-129">Dovrebbe essere visualizzato il messaggio stampato sullo schermo insieme al risultato dell'operazione richiamata (in questo caso, viene visualizzata la tupla vuota `()` perché l'operazione restituisce semplicemente un `Unit` tipo).</span><span class="sxs-lookup"><span data-stu-id="c0fa5-129">You should see the message printed on the screen along with the result of the operation you invoked (here, we see the empty tuple `()` because our operation simply returns a `Unit` type).</span></span>

## <a name="next-steps"></a><span data-ttu-id="c0fa5-130">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="c0fa5-130">Next steps</span></span>

<span data-ttu-id="c0fa5-131">Ora che è stato installato il QDK per i notebook Q # Jupyter, è possibile scrivere ed eseguire [il primo programma Quantum](xref:microsoft.quantum.quickstarts.qrng) scrivendo il codice Q # direttamente all'interno dell'ambiente Jupyter notebook.</span><span class="sxs-lookup"><span data-stu-id="c0fa5-131">Now that you have installed the QDK for Q# Jupyter Notebooks, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng) by writing your Q# code directly within the Jupyter Notebook environment.</span></span>

<span data-ttu-id="c0fa5-132">Per altri esempi sulle operazioni che è possibile eseguire con i notebook Q # Jupyter, vedere:</span><span class="sxs-lookup"><span data-stu-id="c0fa5-132">For more examples of what you can do with Q# Jupyter Notebooks, please take a look at:</span></span>
- <span data-ttu-id="c0fa5-133">[Introduzione a Q # e Jupyter notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span><span class="sxs-lookup"><span data-stu-id="c0fa5-133">[Intro to Q# and Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span></span> <span data-ttu-id="c0fa5-134">Qui sarà disponibile un Jupyter Notebook Q # che Mostra come usare Q # in questo ambiente.</span><span class="sxs-lookup"><span data-stu-id="c0fa5-134">There you will find a Q# Jupyter Notebook that shows how to use Q# in this environment.</span></span>
- <span data-ttu-id="c0fa5-135">[Quantum Katas](xref:microsoft.quantum.overview.katas), una raccolta Open Source di esercitazioni autosufficienti e set di esercizi di programmazione sotto forma di notebook Q # Jupyter.</span><span class="sxs-lookup"><span data-stu-id="c0fa5-135">[Quantum Katas](xref:microsoft.quantum.overview.katas), an open-source collection of self-paced tutorials and sets of programming exercises in the form of Q# Jupyter Notebooks.</span></span> <span data-ttu-id="c0fa5-136">I [notebook di Quantum Katas tutorial](https://github.com/microsoft/QuantumKatas#tutorial-topics) sono un valido punto di partenza.</span><span class="sxs-lookup"><span data-stu-id="c0fa5-136">The [Quantum Katas tutorial notebooks](https://github.com/microsoft/QuantumKatas#tutorial-topics) are a good starting point.</span></span> <span data-ttu-id="c0fa5-137">I Kata Quantum hanno lo scopo di insegnare gli elementi del quantum computing e la programmazione Q # allo stesso tempo.</span><span class="sxs-lookup"><span data-stu-id="c0fa5-137">The Quantum Katas are aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span> <span data-ttu-id="c0fa5-138">Si tratta di un ottimo esempio del tipo di contenuto che è possibile creare con i notebook Q # Jupyter.</span><span class="sxs-lookup"><span data-stu-id="c0fa5-138">They're an excellent example of what kind of content you can create with Q# Jupyter Notebooks.</span></span>
