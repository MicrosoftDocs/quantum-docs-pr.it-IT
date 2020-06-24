---
title: Creazione di un generatore quantistico di numeri casuali
description: Compilare un progetto Q# che illustra i concetti fondamentali del calcolo quantistico, ad esempio la sovrapposizione, creando un generatore quantistico di numeri casuali.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: 18e8975e513a87c0a67a6dbb5586cc7dab5a93fb
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274748"
---
# <a name="tutorial-implement-a-quantum-random-number-generator-in-q"></a><span data-ttu-id="ca6e1-103">Esercitazione: Implementare un generatore quantistico di numeri casuali in Q\#</span><span class="sxs-lookup"><span data-stu-id="ca6e1-103">Tutorial: Implement a Quantum Random Number Generator in Q\#</span></span>

<span data-ttu-id="ca6e1-104">Un semplice esempio di algoritmo quantistico scritto in Q# è un generatore quantistico di numeri casuali.</span><span class="sxs-lookup"><span data-stu-id="ca6e1-104">A simple example of a quantum algorithm written in Q# is a quantum random number generator.</span></span> <span data-ttu-id="ca6e1-105">Questo algoritmo sfrutta la natura dei meccanismi quantistici per generare un numero casuale.</span><span class="sxs-lookup"><span data-stu-id="ca6e1-105">This algorithm leverages the nature of quantum mechanics to produce a random number.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ca6e1-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="ca6e1-106">Prerequisites</span></span>

- <span data-ttu-id="ca6e1-107">Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="ca6e1-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- <span data-ttu-id="ca6e1-108">Creare un progetto Q# [usando Q# dalla riga di comando](xref:microsoft.quantum.install.standalone) oppure con un [programma host Python](xref:microsoft.quantum.install.python) o un [programma host C#](xref:microsoft.quantum.install.cs).</span><span class="sxs-lookup"><span data-stu-id="ca6e1-108">Create a Q# project for either [using Q# from the command line](xref:microsoft.quantum.install.standalone), or with a [Python host program](xref:microsoft.quantum.install.python) or [C# host program](xref:microsoft.quantum.install.cs).</span></span>

## <a name="write-a-q-operation"></a><span data-ttu-id="ca6e1-109">Scrivere un'operazione Q#</span><span class="sxs-lookup"><span data-stu-id="ca6e1-109">Write a Q# operation</span></span>

### <a name="q-operation-code"></a><span data-ttu-id="ca6e1-110">Codice dell'operazione Q#</span><span class="sxs-lookup"><span data-stu-id="ca6e1-110">Q# operation code</span></span>

1. <span data-ttu-id="ca6e1-111">Sostituire il contenuto del file Program.qs con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="ca6e1-111">Replace the contents of the Program.qs file with the following code:</span></span>

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-15,34":::

<span data-ttu-id="ca6e1-112">Come illustrato nell'articolo [Informazioni sul calcolo quantistico](xref:microsoft.quantum.overview.understanding), un qubit è un'unità di informazioni quantistiche che possono essere in sovrapposizione.</span><span class="sxs-lookup"><span data-stu-id="ca6e1-112">As mentioned in our [Understanding quantum computing](xref:microsoft.quantum.overview.understanding) article, a qubit is a unit of quantum information that can be in superposition.</span></span> <span data-ttu-id="ca6e1-113">Quando viene misurato, il valore di un qubit può essere solo 0 o 1.</span><span class="sxs-lookup"><span data-stu-id="ca6e1-113">When measured, a qubit can only be either 0 or 1.</span></span> <span data-ttu-id="ca6e1-114">Tuttavia, durante l'esecuzione lo stato del qubit rappresenta la probabilità di leggere un valore 0 o 1 con una misura.</span><span class="sxs-lookup"><span data-stu-id="ca6e1-114">However, during execution the state of the qubit represents the probability of reading either a 0 or a 1 with a measurement.</span></span> <span data-ttu-id="ca6e1-115">Questo stato probabilistico è noto come sovrapposizione.</span><span class="sxs-lookup"><span data-stu-id="ca6e1-115">This probabilistic state is known as superposition.</span></span> <span data-ttu-id="ca6e1-116">È possibile usare questa probabilità per generare numeri casuali.</span><span class="sxs-lookup"><span data-stu-id="ca6e1-116">We can use this probability to generate random numbers.</span></span>

<span data-ttu-id="ca6e1-117">Nell'operazione Q# viene introdotto il tipo di dati `Qubit`, nativo per Q#.</span><span class="sxs-lookup"><span data-stu-id="ca6e1-117">In our Q# operation, we introduce the `Qubit` datatype, native to Q#.</span></span> <span data-ttu-id="ca6e1-118">È possibile allocare un `Qubit` solo con un'istruzione `using`.</span><span class="sxs-lookup"><span data-stu-id="ca6e1-118">We can only allocate a `Qubit` with a `using` statement.</span></span> <span data-ttu-id="ca6e1-119">Quando viene allocato, un qubit è sempre nello stato `Zero`.</span><span class="sxs-lookup"><span data-stu-id="ca6e1-119">When it gets allocated, a qubit is always in the `Zero`  state.</span></span> 

<span data-ttu-id="ca6e1-120">Con l'operazione `H`, è possibile posizionare il `Qubit` in sovrapposizione.</span><span class="sxs-lookup"><span data-stu-id="ca6e1-120">Using the `H` operation, we are able to put our `Qubit` in superposition.</span></span> <span data-ttu-id="ca6e1-121">Per misurare un qubit e leggerne il valore, si usa l'operazione `M` intrinseca.</span><span class="sxs-lookup"><span data-stu-id="ca6e1-121">To measure a qubit and read its value, you use the `M` intrinsic operation.</span></span>

<span data-ttu-id="ca6e1-122">Posizionando il `Qubit` in sovrapposizione e misurandolo, il risultato sarà un valore diverso ogni volta che viene richiamato il codice.</span><span class="sxs-lookup"><span data-stu-id="ca6e1-122">By putting our `Qubit` in superposition and measuring it, our result will be a different value each time the code is invoked.</span></span>

<span data-ttu-id="ca6e1-123">Quando un oggetto `Qubit` viene deallocato, deve essere impostato in modo esplicito sullo `Zero` stato. in caso contrario, il simulatore segnalerà un errore di Runtime.</span><span class="sxs-lookup"><span data-stu-id="ca6e1-123">When a `Qubit` is deallocated it must be explicitly set back to the `Zero` state, otherwise the simulator will report a runtime error.</span></span> <span data-ttu-id="ca6e1-124">A tale scopo, richiamare `Reset`.</span><span class="sxs-lookup"><span data-stu-id="ca6e1-124">An easy way to achieve this is invoking `Reset`.</span></span>

### <a name="visualizing-the-code-with-the-bloch-sphere"></a><span data-ttu-id="ca6e1-125">Visualizzazione del codice con la sfera di Bloch</span><span class="sxs-lookup"><span data-stu-id="ca6e1-125">Visualizing the code with the Bloch sphere</span></span>

<span data-ttu-id="ca6e1-126">Nella sfera di Bloch il polo nord rappresenta il valore classico **0** e il polo sud rappresenta il valore classico **1**.</span><span class="sxs-lookup"><span data-stu-id="ca6e1-126">In the Bloch sphere, the north pole represents the classical value **0** and the south pole represents the classical value **1**.</span></span> <span data-ttu-id="ca6e1-127">Qualsiasi sovrapposizione può essere rappresentata da un punto sulla sfera (rappresentato da una freccia).</span><span class="sxs-lookup"><span data-stu-id="ca6e1-127">Any superposition can be represented by a point on the sphere (represented by an arrow).</span></span> <span data-ttu-id="ca6e1-128">Più vicina è la fine della freccia a un polo, più alta è la probabilità che il qubit collassi nel valore classico assegnato a tale polo quando viene misurato.</span><span class="sxs-lookup"><span data-stu-id="ca6e1-128">The closer the end of the arrow to a pole the higher the probability the qubit collapses into the classical value assigned to that pole when measured.</span></span> <span data-ttu-id="ca6e1-129">Ad esempio, lo stato del qubit rappresentato dalla freccia rossa nella figura seguente ha una probabilità più elevata di restituire il valore **0** se lo si misura.</span><span class="sxs-lookup"><span data-stu-id="ca6e1-129">For example, the qubit state represented by the red arrow below has a higher probability of giving the value **0** if we measure it.</span></span>

<img src="~/media/qrng-Bloch.png" width="175" alt="A qubit state with a high probability of measuring zero">

<span data-ttu-id="ca6e1-130">È possibile usare questa rappresentazione per visualizzare le operazioni eseguite dal codice:</span><span class="sxs-lookup"><span data-stu-id="ca6e1-130">We can use this representation to visualize what the code is doing:</span></span>

* <span data-ttu-id="ca6e1-131">Innanzitutto si inizia con un qubit inizializzato nello stato **0** e si applica `H` per creare una sovrapposizione in cui le probabilità per **0** e **1** sono le stesse.</span><span class="sxs-lookup"><span data-stu-id="ca6e1-131">First we start with a qubit initialized in the state **0** and apply `H` to create a superposition in which the probabilities for **0** and **1** are the same.</span></span>

<img src="~/media/qrng-H.png" width="450" alt="Preparing a qubit in superposition">

* <span data-ttu-id="ca6e1-132">Si misura quindi il qubit e si salva l'output:</span><span class="sxs-lookup"><span data-stu-id="ca6e1-132">Then we measure the qubit and save the output:</span></span>

<img src="~/media/qrng-meas.png" width="450" alt="Measuring a qubit and saving the output">

<span data-ttu-id="ca6e1-133">Poiché il risultato della misura è completamente casuale, è stato ottenuto un bit casuale.</span><span class="sxs-lookup"><span data-stu-id="ca6e1-133">Since the outcome of the measurement is completely random, we have obtained a random bit.</span></span> <span data-ttu-id="ca6e1-134">È possibile chiamare questa operazione più volte per creare valori integer.</span><span class="sxs-lookup"><span data-stu-id="ca6e1-134">We can call this operation several times to create integers.</span></span> <span data-ttu-id="ca6e1-135">Ad esempio, se si chiama l'operazione tre volte per ottenere tre bit casuali, è possibile creare numeri casuali a 3 bit, ovvero un numero casuale compreso tra 0 e 7.</span><span class="sxs-lookup"><span data-stu-id="ca6e1-135">For example, if we call the operation three times to obtain three random bits, we can build random 3-bit numbers (that is, a random number between 0 and 7).</span></span>


## <a name="creating-a-complete-random-number-generator"></a><span data-ttu-id="ca6e1-136">Creazione di un generatore di numeri casuali completo</span><span class="sxs-lookup"><span data-stu-id="ca6e1-136">Creating a complete random number generator</span></span>

<span data-ttu-id="ca6e1-137">Ora che è disponibile un'operazione Q # che genera bit casuali, è possibile usarla per compilare un generatore di numeri casuali quantistici completo.</span><span class="sxs-lookup"><span data-stu-id="ca6e1-137">Now that we have a Q# operation that generates random bits, we can use it to build a complete quantum random number generator.</span></span> <span data-ttu-id="ca6e1-138">È possibile usare applicazioni da riga di comando Q# o un programma host.</span><span class="sxs-lookup"><span data-stu-id="ca6e1-138">We can use the Q# command line applications or use a host program.</span></span>



### <a name="q-command-line-applications-with-visual-studio-or-visual-studio-code"></a>[<span data-ttu-id="ca6e1-139">Applicazioni da riga di comando Q# con Visual Studio o Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="ca6e1-139">Q# command line applications with Visual Studio or Visual Studio Code</span></span>](#tab/tabid-qsharp)

<span data-ttu-id="ca6e1-140">Per creare l'applicazione da riga di comando Q# completa, aggiungere il punto di ingresso seguente al programma Q#:</span><span class="sxs-lookup"><span data-stu-id="ca6e1-140">To create the full Q# command line application, add the following entry point to your Q# program:</span></span> 

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="17-33":::

<span data-ttu-id="ca6e1-141">Il file eseguibile eseguirà l'operazione o la funzione contrassegnata con l'attributo `@EntryPoint()` in un simulatore o in un'utilità di stima delle risorse, a seconda della configurazione del progetto e delle opzioni della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="ca6e1-141">The executable will run the operation or function marked with the `@EntryPoint()` attribute on a simulator or resource estimator, depending on the project configuration and command-line options.</span></span>

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-34":::

<span data-ttu-id="ca6e1-142">In Visual Studio è sufficiente premere CTRL+F5 per eseguire lo script.</span><span class="sxs-lookup"><span data-stu-id="ca6e1-142">In Visual Studio, simply press Ctrl + F5 to execute the script.</span></span>

<span data-ttu-id="ca6e1-143">In VS Code compilare Program.qs per la prima volta digitando quanto segue nel terminale:</span><span class="sxs-lookup"><span data-stu-id="ca6e1-143">In VS Code, build the Program.qs the first time by typing the below in the terminal:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="ca6e1-144">Per le esecuzioni successive non è necessario ripetere la compilazione.</span><span class="sxs-lookup"><span data-stu-id="ca6e1-144">For subsequent runs, there is no need to build it again.</span></span> <span data-ttu-id="ca6e1-145">Per eseguirlo, digitare il comando seguente e premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="ca6e1-145">To run it, type the following command and press enter:</span></span>

```dotnetcli
dotnet run --no-build
```

### <a name="python-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="ca6e1-146">Python con Visual Studio Code o riga di comando</span><span class="sxs-lookup"><span data-stu-id="ca6e1-146">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)

<span data-ttu-id="ca6e1-147">Per eseguire il nuovo programma Q# da Python, salvare il codice seguente come `host.py`:</span><span class="sxs-lookup"><span data-stu-id="ca6e1-147">To run your new Q# program from Python, save the following code as `host.py`:</span></span>

:::code language="python" source="~/quantum/samples/interoperability/qrng/host.py" range="11-30":::

<span data-ttu-id="ca6e1-148">È quindi possibile eseguire il programma host Python dalla riga di comando:</span><span class="sxs-lookup"><span data-stu-id="ca6e1-148">You can then run your Python host program from the command line:</span></span>

```bash
$ python host.py
Preparing Q# environment...
..The random number generated is 42
```

### <a name="c-with-visual-studio-code-or-visual-studio"></a>[<span data-ttu-id="ca6e1-149">C# con Visual Studio Code o Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ca6e1-149">C# with Visual Studio Code or Visual Studio</span></span>](#tab/tabid-csharp)

<span data-ttu-id="ca6e1-150">Per eseguire il nuovo programma Q# da C#, modificare `Driver.cs` per includere il codice C# seguente:</span><span class="sxs-lookup"><span data-stu-id="ca6e1-150">To run your new Q# program from C#, modify `Driver.cs` to include the following C# code:</span></span>

:::code language="csharp" source="~/quantum/samples/interoperability/qrng/Host.cs" range="4-39":::

<span data-ttu-id="ca6e1-151">È quindi possibile eseguire il programma host C# dalla riga di comando (in Visual Studio è necessario premere F5):</span><span class="sxs-lookup"><span data-stu-id="ca6e1-151">You can then run your C# host program from the command line (in Visual Studio you should press F5):</span></span>

```bash
$ dotnet run
The random number generated is 42
```

***
