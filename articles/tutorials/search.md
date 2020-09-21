---
title: Eseguire l'algoritmo di ricerca di Grover in Q# -Quantum Development Kit
description: Compilare un Q# progetto che illustra l'algoritmo di Grover, uno degli algoritmi quantistici canonici.
author: cgranade
ms.author: chgranad
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
no-loc:
- Q#
- $$v
ms.openlocfilehash: 86c6a651a117b788eb4c8fdd805ead7ab8f54dd7
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834806"
---
# <a name="tutorial-implement-grovers-search-algorithm-in-q"></a><span data-ttu-id="142ff-103">Esercitazione: Implementare l'algoritmo di ricerca di Grover in Q\#</span><span class="sxs-lookup"><span data-stu-id="142ff-103">Tutorial: Implement Grover's search algorithm in Q\#</span></span>

<span data-ttu-id="142ff-104">In questa esercitazione si apprenderà a creare e a eseguire una ricerca di Grover per accelerare la ricerca di dati non strutturati.</span><span class="sxs-lookup"><span data-stu-id="142ff-104">In this tutorial, you can learn how to build and run Grover search to speed up the search of unstructured data.</span></span>  <span data-ttu-id="142ff-105">La ricerca di Grover è uno degli algoritmi di calcolo quantum più diffusi e questa implementazione relativamente piccola Q# offre un'idea di alcuni dei vantaggi della programmazione di soluzioni Quantum con un Q# linguaggio di programmazione quantistica di alto livello per esprimere gli algoritmi quantistici.</span><span class="sxs-lookup"><span data-stu-id="142ff-105">Grover's search is one of the most popular quantum computing algorithms, and this relatively small Q# implementation gives you a sense of some of the advantages of programming quantum solutions with a high-level Q# quantum programming language to express quantum algorithms.</span></span>  <span data-ttu-id="142ff-106">Alla fine della guida si osserverà che l'output della simulazione dimostra come viene restituita una stringa specifica tra un elenco di voci non ordinate in una frazione del tempo necessario per eseguire una ricerca nell'elenco completo con un computer classico.</span><span class="sxs-lookup"><span data-stu-id="142ff-106">At the end of the guide, you will see the simulation output demonstrates successfully finding a specific string among a list of unordered entries in a fraction of the time it would take to search the whole list on a classical computer.</span></span>

<span data-ttu-id="142ff-107">L'algoritmo di Grover esegue la ricerca di elementi specifici in un elenco di dati non strutturati.</span><span class="sxs-lookup"><span data-stu-id="142ff-107">Grover's algorithm searches a list of unstructured data for specific items.</span></span> <span data-ttu-id="142ff-108">Ad esempio, può rispondere alla domanda: Questa carta estratta da un mazzo di carte è un asso di cuori?</span><span class="sxs-lookup"><span data-stu-id="142ff-108">For example, it can answer the question: Is this card drawn from a pack of cards an ace of hearts?</span></span> <span data-ttu-id="142ff-109">L'assegnazione di etichette all'elemento specifico viene chiamata _input contrassegnato_.</span><span class="sxs-lookup"><span data-stu-id="142ff-109">The labeling of the specific item is called _marked input_.</span></span>

<span data-ttu-id="142ff-110">Usando l'algoritmo di ricerca di Grover, un computer quantistico garantisce l'esecuzione di questa ricerca in un minor numero di passaggi rispetto al numero di elementi nell'elenco in cui viene eseguita la ricerca, risultato che nessun algoritmo classico può raggiungere.</span><span class="sxs-lookup"><span data-stu-id="142ff-110">Using Grover's search algorithm, a quantum computer is guaranteed to run this search in fewer steps than the number of items in the list that you're searching — something no classical algorithm can do.</span></span> <span data-ttu-id="142ff-111">L'aumento della velocità nel caso di un mazzo di carte è trascurabile. Tuttavia, negli elenchi contenenti milioni o miliardi di elementi, diventa significativo.</span><span class="sxs-lookup"><span data-stu-id="142ff-111">The increased speed in the case of a pack of cards is negligible; however, in lists containing millions or billions of items, it becomes significant.</span></span>

<span data-ttu-id="142ff-112">È possibile creare l'algoritmo di ricerca di Grover con solo poche righe di codice.</span><span class="sxs-lookup"><span data-stu-id="142ff-112">You can build Grover's search algorithm with just a few lines of code.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="142ff-113">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="142ff-113">Prerequisites</span></span>

- <span data-ttu-id="142ff-114">Microsoft [Quantum Development Kit][install].</span><span class="sxs-lookup"><span data-stu-id="142ff-114">The Microsoft [Quantum Development Kit][install].</span></span>

## <a name="what-does-grovers-search-algorithm-do"></a><span data-ttu-id="142ff-115">Che cosa fa l'algoritmo di ricerca di Grover?</span><span class="sxs-lookup"><span data-stu-id="142ff-115">What does Grover's search algorithm do?</span></span>

<span data-ttu-id="142ff-116">L'algoritmo di Grover chiede se un elemento in un elenco è quello che si sta cercando.</span><span class="sxs-lookup"><span data-stu-id="142ff-116">Grover's algorithm asks whether an item in a list is the one we are searching for.</span></span> <span data-ttu-id="142ff-117">A tale scopo, costruisce una sovrapposizione quantistica degli indici dell'elenco con ogni coefficiente, o ampiezza di probabilità, che rappresenta la probabilità che l'indice specifico sia quello che si sta cercando.</span><span class="sxs-lookup"><span data-stu-id="142ff-117">It does this by constructing a quantum superposition of the indexes of the list with each coefficient, or probability amplitude, representing the probability of that specific index being the one you are looking for.</span></span>

<span data-ttu-id="142ff-118">Il nucleo dell'algoritmo è costituito da due passaggi che aumentano in modo incrementale il coefficiente dell'indice cercato, fino a quando l'ampiezza di probabilità di tale coefficiente non si avvicina a uno.</span><span class="sxs-lookup"><span data-stu-id="142ff-118">At the heart of the algorithm are two steps that incrementally boost the coefficient of the index that we are looking for, until the probability amplitude of that coefficient approaches one.</span></span>

<span data-ttu-id="142ff-119">Il numero di aumenti incrementali è minore del numero di elementi nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="142ff-119">The number of incremental boosts is fewer than the number of items in the list.</span></span> <span data-ttu-id="142ff-120">Questo è il motivo per cui l'algoritmo di ricerca di Grover esegue la ricerca in un minor numero di passaggi rispetto a qualsiasi algoritmo classico.</span><span class="sxs-lookup"><span data-stu-id="142ff-120">This is why Grover's search algorithm performs the search in fewer steps than any classical algorithm.</span></span>

![Diagramma funzionale dell'algoritmo di ricerca di Grover](~/media/grover.png)

## <a name="write-the-code"></a><span data-ttu-id="142ff-122">Scrivere il codice</span><span class="sxs-lookup"><span data-stu-id="142ff-122">Write the code</span></span>

1. <span data-ttu-id="142ff-123">Utilizzando Quantum Development Kit, [creare un nuovo Q# progetto per l'applicazione](xref:microsoft.quantum.install.standalone).</span><span class="sxs-lookup"><span data-stu-id="142ff-123">Using the Quantum Development Kit, [create a new Q# project for the application](xref:microsoft.quantum.install.standalone).</span></span> <span data-ttu-id="142ff-124">Assegnare al progetto il titolo `Grover`.</span><span class="sxs-lookup"><span data-stu-id="142ff-124">Title the project `Grover`.</span></span>

1. <span data-ttu-id="142ff-125">Nel nuovo progetto aggiungere il codice seguente al file `Program.qs`:</span><span class="sxs-lookup"><span data-stu-id="142ff-125">Add the following code to the `Program.qs` file in your new project:</span></span>

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-41":::

1. <span data-ttu-id="142ff-126">Per definire l'elenco in cui verrà eseguita la ricerca, creare un nuovo file `Reflections.qs` e incollare il codice seguente al suo interno:</span><span class="sxs-lookup"><span data-stu-id="142ff-126">To define the list that we're searching, create a new file `Reflections.qs`, and paste in the following code:</span></span>

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    <span data-ttu-id="142ff-127">L'operazione `ReflectAboutMarked` definisce l'input contrassegnato che si sta cercando: la stringa di zeri e uno alternati.</span><span class="sxs-lookup"><span data-stu-id="142ff-127">The `ReflectAboutMarked` operation defines the marked input that you are searching for: the string of alternating zeros and ones.</span></span> <span data-ttu-id="142ff-128">In questo esempio l'input contrassegnato è hardcoded e può essere esteso per cercare input diversi o generalizzato per qualsiasi input.</span><span class="sxs-lookup"><span data-stu-id="142ff-128">This sample hard-codes the marked input, and can be extended to search for different inputs or generalized for any input.</span></span>

1. <span data-ttu-id="142ff-129">Eseguire quindi il nuovo Q# programma per trovare l'elemento contrassegnato da `ReflectAboutMarked` .</span><span class="sxs-lookup"><span data-stu-id="142ff-129">Next, run your new Q# program to find the item marked by `ReflectAboutMarked`.</span></span>

### <a name="no-locq-applications-with-visual-studio-or-visual-studio-code"></a><span data-ttu-id="142ff-130">Q# applicazioni con Visual Studio o Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="142ff-130">Q# applications with Visual Studio or Visual Studio Code</span></span>

<span data-ttu-id="142ff-131">Il programma eseguirà l'operazione o la funzione contrassegnata con l' `@EntryPoint()` attributo in un simulatore o in un estimatore di risorse, a seconda della configurazione del progetto e delle opzioni della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="142ff-131">The program will run the operation or function marked with the `@EntryPoint()` attribute on a simulator or resource estimator, depending on the project configuration and command-line options.</span></span>

<span data-ttu-id="142ff-132">In Visual Studio è sufficiente premere CTRL + F5 per eseguire lo script.</span><span class="sxs-lookup"><span data-stu-id="142ff-132">In Visual Studio, simply press Ctrl + F5 to run the script.</span></span>

<span data-ttu-id="142ff-133">In VS Code compilare `Program.qs` per la prima volta digitando quanto segue nel terminale:</span><span class="sxs-lookup"><span data-stu-id="142ff-133">In VS Code, build the `Program.qs` the first time by typing the below in the terminal:</span></span>

```Command line
dotnet build
```

<span data-ttu-id="142ff-134">Per le esecuzioni successive non è necessario ripetere la compilazione.</span><span class="sxs-lookup"><span data-stu-id="142ff-134">For subsequent runs, there is no need to build it again.</span></span> <span data-ttu-id="142ff-135">Per eseguirlo, digitare il comando seguente e premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="142ff-135">To run it, type the following command and press enter:</span></span>

```Command line
dotnet run --no-build
```

<span data-ttu-id="142ff-136">Nel terminale dovrebbe essere visualizzato il messaggio seguente:</span><span class="sxs-lookup"><span data-stu-id="142ff-136">You should see the following message displayed in the terminal:</span></span>

```
operations.qs:
This operation applies Grover's algorithm to search all possible inputs to an operation to find a particular marked state.
Usage:
operations.qs [options] [command]

--n-qubits <n-qubits> (REQUIRED)
-s, --simulator <simulator>         The name of the simulator to use.
--version                           Show version information
-?, -h, --help                      Show help and usage information
Commands:
```

<span data-ttu-id="142ff-137">Questo perché non è stato specificato il numero di qubits che si voleva usare, quindi il terminale Mostra i comandi disponibili per il programma eseguibile.</span><span class="sxs-lookup"><span data-stu-id="142ff-137">This is because you didn't specify the number of qubits you wanted to use, so the terminal shows you the commands available for the executable program.</span></span> <span data-ttu-id="142ff-138">Se si vuole usare 5 qubits, è necessario digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="142ff-138">If we want to use 5 qubits, we should type:</span></span>

```Command line
dotnet run --n-qubits 5
```

<span data-ttu-id="142ff-139">Premendo INVIO verrà visualizzato l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="142ff-139">Pressing enter you should see the following output:</span></span>

```
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
[Zero,One,Zero,One,Zero]
```

## <a name="next-steps"></a><span data-ttu-id="142ff-140">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="142ff-140">Next steps</span></span>

<span data-ttu-id="142ff-141">Se questa esercitazione è stata apprezzata, consultare alcune delle risorse riportate di seguito per ulteriori informazioni su come utilizzare Q# per scrivere le proprie applicazioni Quantum:</span><span class="sxs-lookup"><span data-stu-id="142ff-141">If you enjoyed this tutorial, check out some of the resources below to learn more about how you can use Q# to write your own quantum applications:</span></span>

- [<span data-ttu-id="142ff-142">Tornare alla guida Introduzione a QDK</span><span class="sxs-lookup"><span data-stu-id="142ff-142">Back to the Getting Started with QDK guide</span></span>](xref:microsoft.quantum.welcome)
- <span data-ttu-id="142ff-143">Provare un [esempio](https://github.com/microsoft/Quantum/tree/main/samples/algorithms/database-search) di algoritmo di ricerca di Grover più generale</span><span class="sxs-lookup"><span data-stu-id="142ff-143">Try a more general Grover's search algorithm [sample](https://github.com/microsoft/Quantum/tree/main/samples/algorithms/database-search)</span></span>
- [<span data-ttu-id="142ff-144">Altre informazioni sulla ricerca di Grover con la serie Quantum Katas</span><span class="sxs-lookup"><span data-stu-id="142ff-144">Learn more about Grover's search with the Quantum Katas</span></span>](xref:microsoft.quantum.overview.katas)
- <span data-ttu-id="142ff-145">Altre informazioni sull'[amplificazione dell'ampiezza][amplitude-amplification], la tecnica di calcolo quantistico alla base dell'algoritmo di ricerca di Grover</span><span class="sxs-lookup"><span data-stu-id="142ff-145">Read more about [Amplitude amplification][amplitude-amplification], the quantum computing technique behind Grover's search algorithm</span></span>
- [<span data-ttu-id="142ff-146">Concetti di calcolo quantistico</span><span class="sxs-lookup"><span data-stu-id="142ff-146">Quantum computing concepts</span></span>](xref:microsoft.quantum.concepts.intro)
- [<span data-ttu-id="142ff-147">Esempi di Quantum Development Kit</span><span class="sxs-lookup"><span data-stu-id="142ff-147">Quantum Development Kit Samples</span></span>](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
[amplitude-amplification]: xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification
