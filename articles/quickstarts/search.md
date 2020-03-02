---
title: Eseguire l'algoritmo di ricerca di Grover in Q# - Quantum Development Kit
description: Compilare un progetto Q# che dimostra l'algoritmo di Grover, uno degli algoritmi quantistici canonici.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
ms.openlocfilehash: 0e64fcd56929fa33397c45bf1b2e99bf687eca6f
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906951"
---
# <a name="quickstart-implement-grovers-search-algorithm-in-q"></a><span data-ttu-id="da828-103">Guida introduttiva: Implementare l'algoritmo di ricerca di Grover in Q#</span><span class="sxs-lookup"><span data-stu-id="da828-103">Quickstart: Implement Grover's search algorithm in Q#</span></span>

<span data-ttu-id="da828-104">In questa esercitazione dell'avvio rapido si apprenderà a creare e a eseguire una ricerca di Grover per accelerare la ricerca di dati non strutturati.</span><span class="sxs-lookup"><span data-stu-id="da828-104">In this Quickstart, you can learn how to build and run Grover search to speed up the search of unstructured data.</span></span>  <span data-ttu-id="da828-105">La ricerca di Grover è uno degli algoritmi di calcolo quantistico più diffusi e questa implementazione Q# relativamente ridotta consente di farsi un'idea dei vantaggi della programmazione di soluzioni quantistiche con un linguaggio di programmazione quantistico Q# generale per esprimere gli algoritmi quantistici.</span><span class="sxs-lookup"><span data-stu-id="da828-105">Grover's search is one of the most popular quantum computing algorithms, and this relatively small Q# implementation gives you a sense of some of the advantages of programming quantum solutions with a high-level Q# quantum programming language to express quantum algorithms.</span></span>  <span data-ttu-id="da828-106">Alla fine della guida si osserverà che l'output della simulazione dimostra come viene restituita una stringa specifica tra un elenco di voci non ordinate in una frazione del tempo necessario per eseguire una ricerca nell'elenco completo con un computer classico.</span><span class="sxs-lookup"><span data-stu-id="da828-106">At the end of the guide, you will see the simulation output demonstrates successfully finding a specific string among a list of onordered entries in a fraction of the time it would take to search the whole list on a classical computer.</span></span>

<span data-ttu-id="da828-107">L'algoritmo di Grover esegue la ricerca di elementi specifici in un elenco di dati non strutturati.</span><span class="sxs-lookup"><span data-stu-id="da828-107">Grover's algorithm searches a list of unstructured data for specific items.</span></span> <span data-ttu-id="da828-108">Ad esempio, può rispondere alla domanda: Questa carta estratta da un mazzo di carte è un asso di cuori?</span><span class="sxs-lookup"><span data-stu-id="da828-108">For example, it can answer the question: Is this card drawn from a pack of cards an ace of hearts?</span></span> <span data-ttu-id="da828-109">L'assegnazione di etichette all'elemento specifico viene chiamata _input contrassegnato_.</span><span class="sxs-lookup"><span data-stu-id="da828-109">The labeling of the specific item is called _marked input_.</span></span>

<span data-ttu-id="da828-110">Usando l'algoritmo di ricerca di Grover, un computer quantistico garantisce l'esecuzione di questa ricerca in un minor numero di passaggi rispetto al numero di elementi nell'elenco in cui viene eseguita la ricerca, risultato che nessun algoritmo classico può raggiungere.</span><span class="sxs-lookup"><span data-stu-id="da828-110">Using Grover's search algorithm, a quantum computer is guaranteed to run this search in fewer steps than the number of items in the list that you're searching — something no classical algorithm can do.</span></span> <span data-ttu-id="da828-111">L'aumento della velocità nel caso di un mazzo di carte è trascurabile. Tuttavia, negli elenchi contenenti milioni o miliardi di elementi, diventa significativo.</span><span class="sxs-lookup"><span data-stu-id="da828-111">The increased speed in the case of a pack of cards is negligible; however, in lists containing millions or billions of items, it becomes significant.</span></span>

<span data-ttu-id="da828-112">È possibile creare l'algoritmo di ricerca di Grover con solo poche righe di codice.</span><span class="sxs-lookup"><span data-stu-id="da828-112">You can build Grover's search algorithm with just a few lines of code.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="da828-113">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="da828-113">Prerequisites</span></span>

- <span data-ttu-id="da828-114">Microsoft [Quantum Development Kit][install].</span><span class="sxs-lookup"><span data-stu-id="da828-114">The Microsoft [Quantum Development Kit][install].</span></span>

## <a name="what-does-grovers-search-algorithm-do"></a><span data-ttu-id="da828-115">Che cosa fa l'algoritmo di ricerca di Grover?</span><span class="sxs-lookup"><span data-stu-id="da828-115">What does Grover's search algorithm do?</span></span>

<span data-ttu-id="da828-116">L'algoritmo di Grover chiede se un elemento in un elenco è quello che si sta cercando.</span><span class="sxs-lookup"><span data-stu-id="da828-116">Grover's algorithm asks whether an item in a list is the one we are searching for.</span></span> <span data-ttu-id="da828-117">A tale scopo, costruisce una sovrapposizione quantistica degli indici dell'elenco con ogni coefficiente, o ampiezza di probabilità, che rappresenta la probabilità che l'indice specifico sia quello che si sta cercando.</span><span class="sxs-lookup"><span data-stu-id="da828-117">It does this by constructing a quantum superposition of the indexes of the list with each coefficient, or probability amplitude, representing the probability of that specific index being the one you are looking for.</span></span>

<span data-ttu-id="da828-118">Il nucleo dell'algoritmo è costituito da due passaggi che aumentano in modo incrementale il coefficiente dell'indice cercato, fino a quando l'ampiezza di probabilità di tale coefficiente non si avvicina a uno.</span><span class="sxs-lookup"><span data-stu-id="da828-118">At the heart of the algorithm are two steps that incrementally boost the coefficient of the index that we are looking for, until the probability amplitude of that coefficient approaches one.</span></span>

<span data-ttu-id="da828-119">Il numero di aumenti incrementali è minore del numero di elementi nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="da828-119">The number of incremental boosts is fewer than the number of items in the list.</span></span> <span data-ttu-id="da828-120">Questo è il motivo per cui l'algoritmo di ricerca di Grover esegue la ricerca in un minor numero di passaggi rispetto a qualsiasi algoritmo classico.</span><span class="sxs-lookup"><span data-stu-id="da828-120">This is why Grover's search algorithm performs the search in fewer steps than any classical algorithm.</span></span>

![Diagramma funzionale dell'algoritmo di ricerca di Grover](~/media/grover.png)

## <a name="write-the-code"></a><span data-ttu-id="da828-122">Scrivere il codice</span><span class="sxs-lookup"><span data-stu-id="da828-122">Write the code</span></span>

1. <span data-ttu-id="da828-123">Usando Quantum Development Kit, [creare un nuovo progetto Q#](xref:microsoft.quantum.howto.createproject) denominato `Grover` nell'ambiente di sviluppo preferito.</span><span class="sxs-lookup"><span data-stu-id="da828-123">Using the Quantum Development Kit, [create a new Q# project](xref:microsoft.quantum.howto.createproject) called `Grover`, in your development environment of choice.</span></span>

1. <span data-ttu-id="da828-124">Nel nuovo progetto aggiungere il codice seguente al file `Operations.qs`:</span><span class="sxs-lookup"><span data-stu-id="da828-124">Add the following code to the `Operations.qs` file in your new project:</span></span>

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-40":::

1. <span data-ttu-id="da828-125">Per definire l'elenco in cui verrà eseguita la ricerca, creare un nuovo file `Reflections.qs` e incollare il codice seguente al suo interno:</span><span class="sxs-lookup"><span data-stu-id="da828-125">To define the list that we're searching, create a new file `Reflections.qs`, and paste in the following code:</span></span>

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    <span data-ttu-id="da828-126">L'operazione `ReflectAboutMarked` definisce l'input contrassegnato che si sta cercando: la stringa di zeri e uno alternati.</span><span class="sxs-lookup"><span data-stu-id="da828-126">The `ReflectAboutMarked` operation defines the marked input that you are searching for: the string of alternating zeros and ones.</span></span> <span data-ttu-id="da828-127">In questo esempio l'input contrassegnato è hardcoded e può essere esteso per cercare input diversi o generalizzato per qualsiasi input.</span><span class="sxs-lookup"><span data-stu-id="da828-127">This sample hard-codes the marked input, and can be extended to search for different inputs or generalized for any input.</span></span>

1. <span data-ttu-id="da828-128">Eseguire quindi il nuovo programma Q# per trovare l'elemento contrassegnato da `ReflectAboutMarked`.</span><span class="sxs-lookup"><span data-stu-id="da828-128">Next, run your new Q# program to find the item marked by `ReflectAboutMarked`.</span></span>

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="da828-129">Python con Visual Studio Code o riga di comando</span><span class="sxs-lookup"><span data-stu-id="da828-129">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)

    <span data-ttu-id="da828-130">Per eseguire il nuovo programma Q# da Python, salvare il codice seguente come `host.py`:</span><span class="sxs-lookup"><span data-stu-id="da828-130">To run your new Q# program from Python, save the following code as `host.py`:</span></span>

    :::code language="python" source="~/quantum/samples/algorithms/simple-grover/host.py" range="9-14":::

    <span data-ttu-id="da828-131">È quindi possibile eseguire il programma host Python dalla riga di comando:</span><span class="sxs-lookup"><span data-stu-id="da828-131">You can then run your Python host program from the command line:</span></span>

    ```bash
    $ python host.py
    Preparing Q# environment...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    [0, 1, 0, 1, 0]
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="da828-132">C# con Visual Studio Code o riga di comando</span><span class="sxs-lookup"><span data-stu-id="da828-132">C# with Visual Studio Code or the Command Line</span></span>](#tab/tabid-csharp)

    <span data-ttu-id="da828-133">Per eseguire il nuovo programma Q# da C#, modificare `Driver.cs` per includere il codice C# seguente:</span><span class="sxs-lookup"><span data-stu-id="da828-133">To run your new Q# program from C#, modify `Driver.cs` to include the following C# code:</span></span>

    :::code language="csharp" source="~/quantum/samples/algorithms/simple-grover/Host.cs" range="4-23":::

    <span data-ttu-id="da828-134">È quindi possibile eseguire il programma host C# dalla riga di comando:</span><span class="sxs-lookup"><span data-stu-id="da828-134">You can then run your C# host program from the command line:</span></span>

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```

    ### <a name="c-with-visual-studio-2019"></a>[<span data-ttu-id="da828-135">C# con Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="da828-135">C# with Visual Studio 2019</span></span>](#tab/tabid-vs2019)

    <span data-ttu-id="da828-136">Per eseguire il nuovo programma Q# da C# in Visual Studio, modificare `Driver.cs` per includere il codice C# seguente:</span><span class="sxs-lookup"><span data-stu-id="da828-136">To run your new Q# program from C# in Visual Studio, modify `Driver.cs` to include the following C# code:</span></span>

    :::code language="csharp" source="~/quantum/samples/algorithms/simple-grover/Host.cs" range="4-23":::

    <span data-ttu-id="da828-137">Premere quindi F5. L'esecuzione del programma verrà avviata e verrà visualizzata una nuova finestra con i risultati seguenti:</span><span class="sxs-lookup"><span data-stu-id="da828-137">Then press F5, the program will start execution and a new windows will pop-up with the following results:</span></span> 

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```
    ***

    <span data-ttu-id="da828-138">L'operazione `ReflectAboutMarked` viene chiamata solo quattro volte, ma il programma Q# è riuscito a trovare l'input "01010" tra $2 ^{5} = $32 di possibili input.</span><span class="sxs-lookup"><span data-stu-id="da828-138">The `ReflectAboutMarked` operation is called only four times, but your Q# program was able to find the "01010" input amongst $2^{5} = 32$ possible inputs!</span></span>

## <a name="next-steps"></a><span data-ttu-id="da828-139">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="da828-139">Next steps</span></span>

<span data-ttu-id="da828-140">Se questa guida di avvio rapido è stata interessante, è possibile consultare alcune delle risorse riportate di seguito per altre informazioni su come usare Q# per scrivere applicazioni quantistiche personalizzate:</span><span class="sxs-lookup"><span data-stu-id="da828-140">If you enjoyed this quickstart, check out some of the resources below to learn more about how you can use Q# to write your own quantum applications:</span></span>

- [<span data-ttu-id="da828-141">Tornare alla guida Introduzione a QDK</span><span class="sxs-lookup"><span data-stu-id="da828-141">Back to the Getting Started with QDK guide</span></span>](xref:microsoft.quantum.welcome)
- <span data-ttu-id="da828-142">Provare un [esempio](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search) di algoritmo di ricerca di Grover più generale</span><span class="sxs-lookup"><span data-stu-id="da828-142">Try a more general Grover's search algorithm [sample](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search)</span></span>
- [<span data-ttu-id="da828-143">Altre informazioni sulla ricerca di Grover con la serie Quantum Katas</span><span class="sxs-lookup"><span data-stu-id="da828-143">Learn more about Grover's search with the Quantum Katas</span></span>](xref:microsoft.quantum.overview.katas)
- <span data-ttu-id="da828-144">Altre informazioni sull'[amplificazione dell'ampiezza](xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification), la tecnica di calcolo quantistico alla base dell'algoritmo di ricerca di Grover</span><span class="sxs-lookup"><span data-stu-id="da828-144">Read more about [Amplitude amplification](xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification), the quantum computing technique behind Grover's search algorithm</span></span>
- [<span data-ttu-id="da828-145">Concetti di calcolo quantistico</span><span class="sxs-lookup"><span data-stu-id="da828-145">Quantum computing concepts</span></span>](xref:microsoft.quantum.concepts.intro)
- [<span data-ttu-id="da828-146">Esempi di Quantum Development Kit</span><span class="sxs-lookup"><span data-stu-id="da828-146">Quantum Development Kit Samples</span></span>](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
