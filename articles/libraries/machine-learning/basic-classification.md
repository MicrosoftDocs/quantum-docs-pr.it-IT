---
title: Classificazione di base con la libreria Quantum Machine Learning
description: 'Informazioni su come eseguire un classificatore sequenziale quantistico scritto in Q # usando la libreria Quantum Machine Learning di Microsoft QDK.'
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.basics
ms.openlocfilehash: f42e3e4492f934d7a8f03d4fec6fa0de765401d7
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77909926"
---
# <a name="basic-classification-classify-data-with-the-qdk"></a><span data-ttu-id="be30f-103">Classificazione di base: classificare i dati con QDK</span><span class="sxs-lookup"><span data-stu-id="be30f-103">Basic classification: Classify data with the QDK</span></span>

<span data-ttu-id="be30f-104">In questa Guida introduttiva si apprenderà come eseguire un classificatore sequenziale quantistico scritto in Q # usando la libreria Quantum Machine Learning della QDK.</span><span class="sxs-lookup"><span data-stu-id="be30f-104">In this Quickstart, you will learn how to execute a quantum sequential classifier written in Q# using the Quantum Machine Learning library of the QDK.</span></span> 

<span data-ttu-id="be30f-105">In questa guida verrà usato il set di dati Half-Moon, usando una struttura di classificazione definita in Q #.</span><span class="sxs-lookup"><span data-stu-id="be30f-105">In this guide we will use the half-moon dataset, using a classifier structure defined in Q#.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="be30f-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="be30f-106">Prerequisites</span></span>

- <span data-ttu-id="be30f-107">Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="be30f-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- [<span data-ttu-id="be30f-108">Creare un progetto Q#</span><span class="sxs-lookup"><span data-stu-id="be30f-108">Create a Q# Project</span></span>](xref:microsoft.quantum.howto.createproject)

## <a name="host-program"></a><span data-ttu-id="be30f-109">Programma host</span><span class="sxs-lookup"><span data-stu-id="be30f-109">Host program</span></span>

<span data-ttu-id="be30f-110">Il programma host è costituito da tre parti:</span><span class="sxs-lookup"><span data-stu-id="be30f-110">Your host program consists of three parts:</span></span>

- <span data-ttu-id="be30f-111">Caricare il set di dati e scegliere un set di parametri iniziali per il modello.</span><span class="sxs-lookup"><span data-stu-id="be30f-111">Load the dataset and choose a set of starting parameters for your model.</span></span>
- <span data-ttu-id="be30f-112">Eseguire il training per determinare i parametri e la distorsione del modello.</span><span class="sxs-lookup"><span data-stu-id="be30f-112">Execute training to determine the parameters and bias of the model.</span></span>
- <span data-ttu-id="be30f-113">Convalidare il modello per determinarne l'accuratezza</span><span class="sxs-lookup"><span data-stu-id="be30f-113">Validate the model to determine its accuracy</span></span>

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="be30f-114">Python con Visual Studio Code o riga di comando</span><span class="sxs-lookup"><span data-stu-id="be30f-114">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)

    <span data-ttu-id="be30f-115">Per eseguire il classificatore Q # da Python, salvare il codice seguente come `host.py`.</span><span class="sxs-lookup"><span data-stu-id="be30f-115">To run your the Q# classifier from Python, save the following code as `host.py`.</span></span> <span data-ttu-id="be30f-116">Tenere presente che è necessario anche il file Q # `Training.qs` descritto più avanti in questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="be30f-116">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="3-42":::

    <span data-ttu-id="be30f-117">È quindi possibile eseguire il programma host Python dalla riga di comando:</span><span class="sxs-lookup"><span data-stu-id="be30f-117">You can then run your Python host program from the command line:</span></span>

    ```bash
    $ python host.py
    Preparing Q# environment...
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="be30f-118">C# con Visual Studio Code o riga di comando</span><span class="sxs-lookup"><span data-stu-id="be30f-118">C# with Visual Studio Code or the Command Line</span></span>](#tab/tabid-csharp)

    <span data-ttu-id="be30f-119">Per eseguire l'utente è il classificatore Q # C#da, salvare il codice seguente come `Host.cs`.</span><span class="sxs-lookup"><span data-stu-id="be30f-119">To run your the Q# classifier from C#, save the following code as `Host.cs`.</span></span> <span data-ttu-id="be30f-120">Tenere presente che è necessario anche il file Q # `Training.qs` descritto più avanti in questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="be30f-120">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    <span data-ttu-id="be30f-121">È quindi possibile eseguire il programma host C# dalla riga di comando:</span><span class="sxs-lookup"><span data-stu-id="be30f-121">You can then run your C# host program from the command line:</span></span>

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-2019"></a>[<span data-ttu-id="be30f-122">C# con Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="be30f-122">C# with Visual Studio 2019</span></span>](#tab/tabid-vs2019)

    <span data-ttu-id="be30f-123">Per eseguire il nuovo programma Q # da C# in Visual Studio, modificare `Host.cs` in modo da includere C# il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="be30f-123">To run your new Q# program from C# in Visual Studio, modify `Host.cs` to include the following C# code.</span></span> <span data-ttu-id="be30f-124">Tenere presente che è necessario anche il file Q # `Training.qs` descritto più avanti in questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="be30f-124">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    <span data-ttu-id="be30f-125">Premere quindi F5. L'esecuzione del programma verrà avviata e verrà visualizzata una nuova finestra con i risultati seguenti:</span><span class="sxs-lookup"><span data-stu-id="be30f-125">Then press F5, the program will start execution and a new windows will pop-up with the following results:</span></span> 

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```
    ***

## <a name="q-classifier-code"></a><span data-ttu-id="be30f-126">D\# codice di classificazione</span><span class="sxs-lookup"><span data-stu-id="be30f-126">Q\# classifier code</span></span>

<span data-ttu-id="be30f-127">A questo punto è possibile vedere in che modo le operazioni richiamate dal programma host sono definite in Q #.</span><span class="sxs-lookup"><span data-stu-id="be30f-127">Now let's see how the operations invoked by the host program are defined in Q#.</span></span>
<span data-ttu-id="be30f-128">Il codice seguente viene salvato in un file denominato `Training.qs`.</span><span class="sxs-lookup"><span data-stu-id="be30f-128">We save the following code in a file named `Training.qs`.</span></span>

:::code language="qsharp" source="~/quantum/samples/machine-learning/half-moons/Training.qs" range="4-116":::

<span data-ttu-id="be30f-129">Le funzioni e le operazioni più importanti definite nel codice precedente sono:</span><span class="sxs-lookup"><span data-stu-id="be30f-129">The most important functions and operations defined in the code above are:</span></span>

- <span data-ttu-id="be30f-130">`ClassifierStructure() : ControlledRotation[]`: in questa funzione è stata impostata la struttura del modello di circuito aggiungendo i livelli delle attività di controllo controllate.</span><span class="sxs-lookup"><span data-stu-id="be30f-130">`ClassifierStructure() : ControlledRotation[]` : in this function we set the structure of our circuit model by adding the layers of the controlled gates we consider.</span></span> <span data-ttu-id="be30f-131">Questo passaggio è analogo alla dichiarazione di livelli di neuroni in un modello di apprendimento avanzato sequenziale.</span><span class="sxs-lookup"><span data-stu-id="be30f-131">This step is analogous to the declaration of layers of neurons in a sequential deep learning model.</span></span>
- <span data-ttu-id="be30f-132">`TrainHalfMoonModel() : TrainWineModel() : (Double[], Double)`: questa operazione è la parte principale del codice e definisce il training.</span><span class="sxs-lookup"><span data-stu-id="be30f-132">`TrainHalfMoonModel() : TrainWineModel() : (Double[], Double)` : this operation is the core part of the code and defines the training.</span></span> <span data-ttu-id="be30f-133">Qui vengono caricati gli esempi dal set di dati incluso nella libreria, vengono impostati i parametri Hyper e i parametri iniziali per il training e viene avviato il training chiamando l'operazione `TrainSequentialClassifier` inclusa nella libreria.</span><span class="sxs-lookup"><span data-stu-id="be30f-133">Here we load the samples from the dataset included in the library, we set the hyper parameters and the initial parameters for the training and we start the training by calling the operation `TrainSequentialClassifier` included in the library.</span></span> <span data-ttu-id="be30f-134">Restituisce i parametri e la distorsione che determinano il classificatore.</span><span class="sxs-lookup"><span data-stu-id="be30f-134">It outputs the parameters and the bias that determine the classifier.</span></span>
- <span data-ttu-id="be30f-135">`ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int`: questa operazione definisce il processo di convalida per la valutazione del modello.</span><span class="sxs-lookup"><span data-stu-id="be30f-135">`ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int` : this operation defines the validation process to evaluate the model.</span></span> <span data-ttu-id="be30f-136">Qui vengono caricati gli esempi per la convalida, il numero di misure per campione e la tolleranza.</span><span class="sxs-lookup"><span data-stu-id="be30f-136">Here we load the samples for validation, the number of measurements per sample and the tolerance.</span></span> <span data-ttu-id="be30f-137">Restituisce il numero di classificazioni non configurate nel batch di campioni scelto per la convalida.</span><span class="sxs-lookup"><span data-stu-id="be30f-137">It outputs the number of misclassifications on the chosen batch of samples for validation.</span></span>

## <a name="next-steps"></a><span data-ttu-id="be30f-138">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="be30f-138">Next steps</span></span>

<span data-ttu-id="be30f-139">In primo luogo, è possibile riprodurre il codice e provare a modificare alcuni parametri per vedere come influiscono sul training.</span><span class="sxs-lookup"><span data-stu-id="be30f-139">First, you can play with the code and try to change some parameters to see how it affects the training.</span></span> <span data-ttu-id="be30f-140">Quindi, nell'esercitazione successiva, [progettare un classificatore personalizzato](xref:microsoft.quantum.libraries.machine-learning.design), si apprenderà come definire la struttura del classificatore.</span><span class="sxs-lookup"><span data-stu-id="be30f-140">Then, in the next tutorial, [Design your own classifier](xref:microsoft.quantum.libraries.machine-learning.design),  you will learn how to define the structure of the classifier.</span></span>