---
title: 'Sviluppare con notebook Q # Jupyter'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: b7276f9b273f601f30e4938018398353b6a9102d
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76831070"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="7dce4-102">Sviluppare con notebook Q # Jupyter</span><span class="sxs-lookup"><span data-stu-id="7dce4-102">Develop with Q# Jupyter notebooks</span></span>

<span data-ttu-id="7dce4-103">Installare QDK per lo sviluppo di operazioni Q # nei notebook Q # Jupyter.</span><span class="sxs-lookup"><span data-stu-id="7dce4-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="7dce4-104">I notebook di Jupyter consentono l'esecuzione di codice sul posto insieme a istruzioni, note e altro contenuto.</span><span class="sxs-lookup"><span data-stu-id="7dce4-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="7dce4-105">Questo ambiente è ideale per la scrittura di codice Q # con spiegazioni incorporate o esercitazioni interattive di quantum computing.</span><span class="sxs-lookup"><span data-stu-id="7dce4-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="7dce4-106">Ecco cosa occorre fare per iniziare a creare notebook Q#.</span><span class="sxs-lookup"><span data-stu-id="7dce4-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="7dce4-107">IQ # (pronunciato i-q-sharp) è un'estensione usata principalmente da Jupyter e Python in .NET Core SDK che fornisce le funzionalità essenziali per la compilazione e la simulazione di operazioni Q#.</span><span class="sxs-lookup"><span data-stu-id="7dce4-107">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

> [!NOTE]
> * <span data-ttu-id="7dce4-108">Nei notebook Q # Jupyter è possibile eseguire solo il codice Q # e non è possibile chiamare le operazioni da programmi host esterni, ad esempio Python o C# file.</span><span class="sxs-lookup"><span data-stu-id="7dce4-108">In Q# Jupyter Notebooks you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="7dce4-109">Questo ambiente non è appropriato se l'obiettivo consiste nel combinare un programma host classico esterno con il programma Quantum.</span><span class="sxs-lookup"><span data-stu-id="7dce4-109">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

1. <span data-ttu-id="7dce4-110">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="7dce4-110">Pre-requisites</span></span>

    - <span data-ttu-id="7dce4-111">[Python](https://www.python.org/downloads/) 3.6 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="7dce4-111">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="7dce4-112">Notebook di Jupyter</span><span class="sxs-lookup"><span data-stu-id="7dce4-112">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="7dce4-113">.NET Core SDK 3,1 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="7dce4-113">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="7dce4-114">Installare il pacchetto `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="7dce4-114">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="7dce4-115">Verificare l'installazione creando un'applicazione `Hello World`</span><span class="sxs-lookup"><span data-stu-id="7dce4-115">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="7dce4-116">Eseguire il comando seguente per avviare il server Notebook:</span><span class="sxs-lookup"><span data-stu-id="7dce4-116">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="7dce4-117">Per aprire la copia del notebook di Jupyter e incollare l'URL fornito dalla riga di comando nel browser.</span><span class="sxs-lookup"><span data-stu-id="7dce4-117">To open the Jupyter notebook copy and paste the URL provided by the command line into your browser.</span></span>

    - <span data-ttu-id="7dce4-118">Creare un notebook Jupyter con un kernel Q# e aggiungere il codice seguente alla prima cella del notebook:</span><span class="sxs-lookup"><span data-stu-id="7dce4-118">Create a Jupyter notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="7dce4-119">Eseguire la cella del notebook:</span><span class="sxs-lookup"><span data-stu-id="7dce4-119">Run this cell of the notebook:</span></span>

        ![Cella di notebook di Jupyter con codice Q#](~/media/install-guide-jupyter.png)

        <span data-ttu-id="7dce4-121">Nell'output della cella verrà visualizzato `SayHello`.</span><span class="sxs-lookup"><span data-stu-id="7dce4-121">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="7dce4-122">Quando è in esecuzione nei notebook Jupyter, il codice Q# viene compilato e il notebook restituisce il nome delle operazioni trovate.</span><span class="sxs-lookup"><span data-stu-id="7dce4-122">When running in jupyter notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="7dce4-123">In una nuova cella, eseguire l'operazione appena creata (in un simulatore) usando il comando `%simulate`:</span><span class="sxs-lookup"><span data-stu-id="7dce4-123">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

        ![Cella di notebook di Jupyter con il magic %simulate](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="7dce4-125">Dovrebbe essere visualizzato il messaggio stampato sullo schermo insieme al risultato dell'operazione richiamata (in questo caso, viene visualizzata la tupla vuota `()` perché l'operazione restituisce semplicemente un tipo di `Unit`).</span><span class="sxs-lookup"><span data-stu-id="7dce4-125">You should see the message printed on the screen along with the result of the operation you invoked (here, we see the empty tuple `()` because our operation simply returns a `Unit` type).</span></span>

## <a name="whats-next"></a><span data-ttu-id="7dce4-126">Potrai anche</span><span class="sxs-lookup"><span data-stu-id="7dce4-126">What's next?</span></span>

<span data-ttu-id="7dce4-127">Ora che è stato installato Quantum Development Kit nell'ambiente preferito, è possibile scrivere ed eseguire [il primo programma quantistico](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="7dce4-127">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
