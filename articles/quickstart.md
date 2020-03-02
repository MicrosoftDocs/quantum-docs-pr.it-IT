---
title: Introduzione al calcolo quantistico con Q#
description: Informazioni su come scrivere un programma quantistico in Q#. Sviluppare un'applicazione Stato di Bell usando Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 10/07/2019
ms.topic: tutorial
uid: microsoft.quantum.write-program
ms.openlocfilehash: 8d3b2d7c8da39a961f4eedcc5989ad3a1e134ade
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906730"
---
# <a name="quantum-basics-with-q"></a><span data-ttu-id="f96b0-104">Introduzione al calcolo quantistico con Q#</span><span class="sxs-lookup"><span data-stu-id="f96b0-104">Quantum basics with Q#</span></span>

<span data-ttu-id="f96b0-105">Questa esercitazione dell'avvio rapido illustra come scrivere un programma Q# che modifica e misura i qubit e mostra gli effetti della sovrapposizione e dell'entanglement.</span><span class="sxs-lookup"><span data-stu-id="f96b0-105">In this Quickstart, we show you how to write a Q# program that manipulates and measures qubits and demonstrates the effects of superposition and entanglement.</span></span>  <span data-ttu-id="f96b0-106">Questa guida illustra l'installazione del QDK, la compilazione del programma e l'esecuzione del programma in un simulatore quantistico.</span><span class="sxs-lookup"><span data-stu-id="f96b0-106">This guides you on installing the QDK, building the program and executing that program on a quantum simulator.</span></span>  

<span data-ttu-id="f96b0-107">Verrà scritta un'applicazione denominata Bell per illustrare l'entanglement quantistico.</span><span class="sxs-lookup"><span data-stu-id="f96b0-107">You will write an application called Bell to demonstrate quantum entanglement.</span></span>  <span data-ttu-id="f96b0-108">Il nome Bell fa riferimento agli stati di Bell, che sono stati quantistici specifici di due qubit che vengono usati per rappresentare gli esempi più semplici di sovrapposizione e di entanglement quantistico.</span><span class="sxs-lookup"><span data-stu-id="f96b0-108">The name Bell is in reference to Bell states, which are specific quantum states of two qubits that are used to represent the simplest examples of superposition and quantum entanglement.</span></span> 

## <a name="pre-requisites"></a><span data-ttu-id="f96b0-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="f96b0-109">Pre-requisites</span></span>

<span data-ttu-id="f96b0-110">Se si è pronti per iniziare a scrivere codice, seguire questa procedura prima di procedere:</span><span class="sxs-lookup"><span data-stu-id="f96b0-110">If you are ready to start coding, follow these steps before proceeding:</span></span> 

* <span data-ttu-id="f96b0-111">[Installare](xref:microsoft.quantum.install) Quantum Development Kit usando il linguaggio di programmazione e l'ambiente di sviluppo preferiti.</span><span class="sxs-lookup"><span data-stu-id="f96b0-111">[Install](xref:microsoft.quantum.install) the Quantum Development Kit using your preferred language and development environment</span></span>
* <span data-ttu-id="f96b0-112">Se il QDK è già installato, assicurarsi di aver eseguito l'[aggiornamento](xref:microsoft.quantum.update) alla versione più recente</span><span class="sxs-lookup"><span data-stu-id="f96b0-112">If you already have the QDK installed, make sure you have [updated](xref:microsoft.quantum.update) to the latest version</span></span>

<span data-ttu-id="f96b0-113">È anche possibile seguire l'esercitazione senza installare il QDK e ottenere una panoramica del linguaggio di programmazione Q# e dei concetti di base del calcolo quantistico.</span><span class="sxs-lookup"><span data-stu-id="f96b0-113">You can also follow along with the narrative without installing the QDK, reviewing the overviews of the Q# programming language and the first concepts of quantum computing.</span></span>

## <a name="demonstrating-qubit-behavior-with-q"></a><span data-ttu-id="f96b0-114">Dimostrazione del comportamento dei qubit con Q#</span><span class="sxs-lookup"><span data-stu-id="f96b0-114">Demonstrating qubit behavior with Q#</span></span>

<span data-ttu-id="f96b0-115">Ricordare la semplice [definizione di un qubit](xref:microsoft.quantum.overview.what#the-qubit).</span><span class="sxs-lookup"><span data-stu-id="f96b0-115">Recall our simple [definition of a qubit](xref:microsoft.quantum.overview.what#the-qubit).</span></span>  <span data-ttu-id="f96b0-116">Mentre i bit classici contengono un singolo valore binario come 0 o 1, lo stato di un qubit può essere una **sovrapposizione** di 0 e 1 contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="f96b0-116">Where classical bits hold a single binary value such as a 0 or 1, the state of a qubit can be in a **superposition** of 0 and 1 simultaneously.</span></span>  <span data-ttu-id="f96b0-117">Concettualmente, un qubit può essere considerato come una direzione nello spazio (nota anche come vettore).</span><span class="sxs-lookup"><span data-stu-id="f96b0-117">Conceptually, a qubit can be thought of as a direction in space (also known as a vector).</span></span>  <span data-ttu-id="f96b0-118">Un qubit può trovarsi in una qualsiasi delle direzioni possibili.</span><span class="sxs-lookup"><span data-stu-id="f96b0-118">A qubit can be in any of the possible directions.</span></span> <span data-ttu-id="f96b0-119">I due **stati classici** sono le due direzioni, che rappresentano la probabilità del 100% di misurare 0 e del 100% di misurare 1.</span><span class="sxs-lookup"><span data-stu-id="f96b0-119">The two **classical states** are the two directions; representing 100% chance of measuring 0 and 100% chance of measuring 1.</span></span>  <span data-ttu-id="f96b0-120">Questa rappresentazione è anche visualizzata in modo più formale dalla [sfera di Bloch](/quantum/concepts/the-qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).</span><span class="sxs-lookup"><span data-stu-id="f96b0-120">This representation is also more formally visualized by the [bloch sphere](/quantum/concepts/the-qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).</span></span>


<span data-ttu-id="f96b0-121">L'azione di misurazione genera un risultato binario e modifica lo stato del qubit.</span><span class="sxs-lookup"><span data-stu-id="f96b0-121">The act of measurement produces a binary result and changes a qubit state.</span></span> <span data-ttu-id="f96b0-122">La misurazione genera un valore binario, ovvero 0 o 1.</span><span class="sxs-lookup"><span data-stu-id="f96b0-122">Measurement produces a binary value, either 0 or 1.</span></span>  <span data-ttu-id="f96b0-123">Il qubit passa dall'essere in sovrapposizione (qualsiasi direzione) a uno degli stati classici.</span><span class="sxs-lookup"><span data-stu-id="f96b0-123">The qubit goes from being in superposition (any direction) to one of the classical states.</span></span>  <span data-ttu-id="f96b0-124">Successivamente, la ripetizione della stessa misurazione senza alcuna operazione genera lo stesso risultato binario.</span><span class="sxs-lookup"><span data-stu-id="f96b0-124">Thereafter, repeating the same measurement without any intervening operations produces the same binary result.</span></span>  

<span data-ttu-id="f96b0-125">Più qubit possono anche trovarsi in uno stato di **entanglement**.</span><span class="sxs-lookup"><span data-stu-id="f96b0-125">Multiple qubits can be **entangled**.</span></span> <span data-ttu-id="f96b0-126">Quando si esegue la misurazione di un qubit con entanglement, vengono aggiornate anche le informazioni sullo stato degli altri qubit.</span><span class="sxs-lookup"><span data-stu-id="f96b0-126">When we make a measurement of one entangled qubit, our knowledge of the state of the other(s) is updated as well.</span></span>

<span data-ttu-id="f96b0-127">A questo punto è possibile dimostrare in che modo Q# esprime questo comportamento.</span><span class="sxs-lookup"><span data-stu-id="f96b0-127">Now, we're ready to demonstrate how Q# expresses this behavior.</span></span>  <span data-ttu-id="f96b0-128">Si inizierà con il programma più semplice possibile e lo si svilupperà per mostrare la sovrapposizione quantistica e l'entanglement quantistico.</span><span class="sxs-lookup"><span data-stu-id="f96b0-128">You start with the simplest program possible and build it up to demonstrate quantum superposition and quantum entanglement.</span></span>

## <a name="setup"></a><span data-ttu-id="f96b0-129">Configurazione</span><span class="sxs-lookup"><span data-stu-id="f96b0-129">Setup</span></span>

<span data-ttu-id="f96b0-130">Le applicazioni sviluppate con Quantum Development Kit di Microsoft sono costituite da due parti:</span><span class="sxs-lookup"><span data-stu-id="f96b0-130">Applications developed with Microsoft's Quantum Development Kit consist of two parts:</span></span>

1. <span data-ttu-id="f96b0-131">Uno o più algoritmi quantistici, implementati usando il linguaggio di programmazione quantistico Q#.</span><span class="sxs-lookup"><span data-stu-id="f96b0-131">One or more quantum algorithms, implemented using the Q# quantum programming language.</span></span>
1. <span data-ttu-id="f96b0-132">Un programma host, implementato in un linguaggio di programmazione come Python o C# o che funge da punto di ingresso principale e richiama le operazioni Q# per eseguire un algoritmo quantistico.</span><span class="sxs-lookup"><span data-stu-id="f96b0-132">A host program, implemented in a programming language like Python or C# that serves as the main entry point and invokes Q# operations to execute a quantum algorithm.</span></span>

#### <a name="python"></a>[<span data-ttu-id="f96b0-133">Python</span><span class="sxs-lookup"><span data-stu-id="f96b0-133">Python</span></span>](#tab/tabid-python)

1. <span data-ttu-id="f96b0-134">Scegliere una posizione per l'applicazione</span><span class="sxs-lookup"><span data-stu-id="f96b0-134">Choose a location for your application</span></span>

1. <span data-ttu-id="f96b0-135">Creare un file denominato `Bell.qs`.</span><span class="sxs-lookup"><span data-stu-id="f96b0-135">Create a file called `Bell.qs`.</span></span> <span data-ttu-id="f96b0-136">Questo file conterrà il codice Q#.</span><span class="sxs-lookup"><span data-stu-id="f96b0-136">This file will contain your Q# code.</span></span>

1. <span data-ttu-id="f96b0-137">Creare un file denominato `host.py`.</span><span class="sxs-lookup"><span data-stu-id="f96b0-137">Create a file called `host.py`.</span></span> <span data-ttu-id="f96b0-138">Questo file conterrà il codice host Python.</span><span class="sxs-lookup"><span data-stu-id="f96b0-138">This file will contain your Python host code.</span></span>

#### <a name="c-command-line"></a>[<span data-ttu-id="f96b0-139">Riga di comando C#</span><span class="sxs-lookup"><span data-stu-id="f96b0-139">C# Command Line</span></span>](#tab/tabid-csharp)

1. <span data-ttu-id="f96b0-140">Creare un nuovo progetto Q#:</span><span class="sxs-lookup"><span data-stu-id="f96b0-140">Create a new Q# project:</span></span>

    ```bash
    dotnet new console -lang Q# --output Bell
    cd Bell
    ```

    <span data-ttu-id="f96b0-141">Verrà visualizzato un file `.csproj`, un file Q# denominato `Operations.qs` e un file di programma host denominato `Driver.cs`</span><span class="sxs-lookup"><span data-stu-id="f96b0-141">You should see a `.csproj` file, a Q# file called `Operations.qs`, and a host program file called `Driver.cs`</span></span>

1. <span data-ttu-id="f96b0-142">Rinominare il file Q#</span><span class="sxs-lookup"><span data-stu-id="f96b0-142">Rename the Q# file</span></span>

    ```bash
    mv Operation.qs Bell.qs
    ```

#### <a name="visual-studio"></a>[<span data-ttu-id="f96b0-143">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f96b0-143">Visual Studio</span></span>](#tab/tabid-vs2019)

1. <span data-ttu-id="f96b0-144">Creare un nuovo progetto</span><span class="sxs-lookup"><span data-stu-id="f96b0-144">Create a new project</span></span>

   * <span data-ttu-id="f96b0-145">Aprire Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f96b0-145">Open Visual Studio</span></span>
   * <span data-ttu-id="f96b0-146">Scegliere **Nuovo** -> **Progetto...** dal menu **File**</span><span class="sxs-lookup"><span data-stu-id="f96b0-146">Go to the **File** menu and select **New** -> **Project...**</span></span>
   * <span data-ttu-id="f96b0-147">In Esplora risorse di Modello di progetto digitare `Q#` nel campo di ricerca e selezionare il modello `Q# Application`</span><span class="sxs-lookup"><span data-stu-id="f96b0-147">In the project template explorer, type `Q#` into the search field and select the `Q# Application` template</span></span>
   * <span data-ttu-id="f96b0-148">Assegnare il nome `Bell` al progetto</span><span class="sxs-lookup"><span data-stu-id="f96b0-148">Give your project the name `Bell`</span></span>

1. <span data-ttu-id="f96b0-149">Rinominare il file Q#</span><span class="sxs-lookup"><span data-stu-id="f96b0-149">Rename the Q# file</span></span>

   * <span data-ttu-id="f96b0-150">Passare a **Esplora soluzioni**</span><span class="sxs-lookup"><span data-stu-id="f96b0-150">Navigate to the **Solution Explorer**</span></span>
   * <span data-ttu-id="f96b0-151">Fare clic con il pulsante destro sul file `Operations.qs`</span><span class="sxs-lookup"><span data-stu-id="f96b0-151">Right click on the `Operations.qs` file</span></span>
   * <span data-ttu-id="f96b0-152">Rinominarlo in `Bell.qs`</span><span class="sxs-lookup"><span data-stu-id="f96b0-152">Rename it to `Bell.qs`</span></span>

* * *

## <a name="write-a-q-operation"></a><span data-ttu-id="f96b0-153">Scrivere un'operazione Q#</span><span class="sxs-lookup"><span data-stu-id="f96b0-153">Write a Q# operation</span></span>

<span data-ttu-id="f96b0-154">L'obiettivo prevede la preparazione di due qubit in uno stato quantico specifico, per dimostrare come operare sui qubit con Q# per modificarne lo stato e mostrare gli effetti della sovrapposizione e dell'entanglement.</span><span class="sxs-lookup"><span data-stu-id="f96b0-154">Our goal is to prepare two qubits in a specific quantum state, demonstrating how to operate on qubits with Q# to change their state and demonstrate the effects of superposition and entanglement.</span></span> <span data-ttu-id="f96b0-155">Si procederà un pezzo alla volta per dimostrare gli stati dei qubit, le operazioni e la misura.</span><span class="sxs-lookup"><span data-stu-id="f96b0-155">We will build this up piece by piece to demonstrate qubit states, operations, and measurement.</span></span>

<span data-ttu-id="f96b0-156">**Panoramica:**  Nel primo codice riportato di seguito viene illustrato come usare i qubit in Q#.</span><span class="sxs-lookup"><span data-stu-id="f96b0-156">**Overview:**  In the first code below, we show you how to work with qubits in Q#.</span></span>  <span data-ttu-id="f96b0-157">Verranno illustrate due operazioni, `M` e `X`, che trasformano lo stato di un qubit.</span><span class="sxs-lookup"><span data-stu-id="f96b0-157">We’ll introduce two operations, `M` and `X` that transform the state of a qubit.</span></span> 

<span data-ttu-id="f96b0-158">In questo frammento di codice viene definita un'operazione `Set` che accetta come parametro un qubit e un altro parametro, `desired`, che rappresenta lo stato in cui deve trovarsi il qubit.</span><span class="sxs-lookup"><span data-stu-id="f96b0-158">In this code snippet, an operation `Set` is defined that takes as a parameter a qubit and another parameter, `desired`, representing the state that we would like the qubit to be in.</span></span>  <span data-ttu-id="f96b0-159">L'operazione `Set` esegue una misura del qubit tramite l'operazione `M`.</span><span class="sxs-lookup"><span data-stu-id="f96b0-159">The operation `Set` performs a measurement on the qubit using the operation `M`.</span></span>  <span data-ttu-id="f96b0-160">In Q# una misura di qubit restituisce sempre `Zero` o `One`.</span><span class="sxs-lookup"><span data-stu-id="f96b0-160">In Q#, a qubit measurement always returns either  `Zero` or `One`.</span></span>  <span data-ttu-id="f96b0-161">Se la misura restituisce un valore diverso da quello desiderato, "inverte" il qubit, ovvero, esegue un'operazione `X`, che modifica lo stato del qubit in un nuovo stato in cui le probabilità di una misura che restituisce `Zero` e `One` sono invertite.</span><span class="sxs-lookup"><span data-stu-id="f96b0-161">If the measurement returns a value not equal to a desired value, Set “flips” the qubit; that is, it executes an `X` operation, which changes the qubit state to a new state in which the probabilities of a measurement returning `Zero` and `One` are reversed.</span></span>  <span data-ttu-id="f96b0-162">Per illustrare l'effetto dell'operazione `Set`, viene quindi aggiunta un'operazione `TestBellState`.</span><span class="sxs-lookup"><span data-stu-id="f96b0-162">To demonstrate the effect of the `Set` operation, a `TestBellState` operation is then added.</span></span>  <span data-ttu-id="f96b0-163">Questa operazione accetta come input `Zero` o `One`, chiama l'operazione `Set` un determinato numero di volte con tale input e conta il numero di volte in cui la misura del qubit ha restituito `Zero` e il numero di volte in cui ha restituito `One`.</span><span class="sxs-lookup"><span data-stu-id="f96b0-163">This operation takes as input a `Zero` or `One`, and calls the `Set` operation some number of times with that input, and counts the number of times that `Zero` was returned from the measurement of the qubit and the number of times that `One` was returned.</span></span> <span data-ttu-id="f96b0-164">Naturalmente, in questa prima simulazione dell'operazione `TestBellState`, si prevede che l'output mostri che tutte le misure del qubit impostato con `Zero` come input del parametro restituiranno `Zero` e tutte le misure di un qubit impostato con `One` come input del parametro restituiranno `One`.</span><span class="sxs-lookup"><span data-stu-id="f96b0-164">Of course, in this first simulation of the `TestBellState` operation, we expect that the output will show that all measurements of the qubit set with `Zero` as the parameter input will return `Zero`, and all measurements of a qubit set with `One` as the parameter input will return `One`.</span></span>  <span data-ttu-id="f96b0-165">Successivamente, verrà aggiunto il codice a `TestBellState` per dimostrare la sovrapposizione e l'entanglement.</span><span class="sxs-lookup"><span data-stu-id="f96b0-165">Further on, we’ll add code to `TestBellState` to demonstrating superposition and entanglement.</span></span>


### <a name="q-operation-code"></a><span data-ttu-id="f96b0-166">Codice dell'operazione Q#</span><span class="sxs-lookup"><span data-stu-id="f96b0-166">Q# operation code</span></span>

1. <span data-ttu-id="f96b0-167">Sostituire il contenuto del file Bell.qs con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="f96b0-167">Replace the contents of the Bell.qs file with the following code:</span></span>

    ```qsharp
    namespace Quantum.Bell {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation Set(desired : Result, q1 : Qubit) : Unit {
            if (desired != M(q1)) {
                X(q1);
            }
        }
    }
    ```

    <span data-ttu-id="f96b0-168">Questa operazione può ora essere chiamata per impostare un qubit su uno stato classico, restituendo `Zero` il 100% delle volte o restituendo `One` il 100% delle volte.</span><span class="sxs-lookup"><span data-stu-id="f96b0-168">This operation may now be called to set a qubit to a classical state, either returning `Zero` 100% of the time or returning `One` 100% of the time.</span></span>  <span data-ttu-id="f96b0-169">`Zero` e `One` sono costanti che rappresentano gli unici due risultati possibili della misura di un qubit.</span><span class="sxs-lookup"><span data-stu-id="f96b0-169">`Zero` and `One` are constants that represent the only two possible results of a measurement of a qubit.</span></span>

    <span data-ttu-id="f96b0-170">L'operazione `Set` misura il qubit.</span><span class="sxs-lookup"><span data-stu-id="f96b0-170">The operation `Set` measures the qubit.</span></span>
    <span data-ttu-id="f96b0-171">Se il qubit si trova nello stato desiderato, `Set` lo lascia invariato. In caso contrario, esegue l'operazione `X` che modifica lo stato del qubit impostandolo sullo stato desiderato.</span><span class="sxs-lookup"><span data-stu-id="f96b0-171">If the qubit is in the state we want, `Set` leaves it alone; otherwise, by executing the `X` operation, we change the qubit state to the desired state.</span></span>

### <a name="about-q-operations"></a><span data-ttu-id="f96b0-172">Informazioni sulle operazioni Q#</span><span class="sxs-lookup"><span data-stu-id="f96b0-172">About Q# operations</span></span>

<span data-ttu-id="f96b0-173">Un'operazione Q# è una subroutine quantistica,</span><span class="sxs-lookup"><span data-stu-id="f96b0-173">A Q# operation is a quantum subroutine.</span></span> <span data-ttu-id="f96b0-174">vale a dire una routine chiamabile che contiene operazioni quantistiche.</span><span class="sxs-lookup"><span data-stu-id="f96b0-174">That is, it is a callable routine that contains quantum operations.</span></span>

<span data-ttu-id="f96b0-175">Gli argomenti di un'operazione vengono specificati come tuple, racchiuse tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="f96b0-175">The arguments to an operation are specified as a tuple, within parentheses.</span></span>

<span data-ttu-id="f96b0-176">Il tipo restituito dell'operazione viene specificato dopo i due punti.</span><span class="sxs-lookup"><span data-stu-id="f96b0-176">The return type of the operation is specified after a colon.</span></span> <span data-ttu-id="f96b0-177">In questo caso, l'operazione `Set` non restituisce alcun risultato, quindi viene contrassegnata come se avesse restituito `Unit`.</span><span class="sxs-lookup"><span data-stu-id="f96b0-177">In this case, the `Set` operation has no return, so it is marked as returning `Unit`.</span></span> <span data-ttu-id="f96b0-178">Si tratta dell'equivalente Q# di `unit` in F#, che è approssimativamente analogo a `void`in C# e a una tupla vuota (`Tuple[()]`) in Python.</span><span class="sxs-lookup"><span data-stu-id="f96b0-178">This is the Q# equivalent of `unit` in F#, which is roughly analogous to `void` in C#, and an empty tuple (`Tuple[()]`) in Python.</span></span>

<span data-ttu-id="f96b0-179">Nella prima operazione Q# sono state usate due operazioni quantistiche:</span><span class="sxs-lookup"><span data-stu-id="f96b0-179">You have used two quantum operations in your first Q# operation:</span></span>

* <span data-ttu-id="f96b0-180">L'operazione [M](xref:microsoft.quantum.intrinsic.m), che misura lo stato del qubit</span><span class="sxs-lookup"><span data-stu-id="f96b0-180">The [M](xref:microsoft.quantum.intrinsic.m) operation, which measures the state of the qubit</span></span>
* <span data-ttu-id="f96b0-181">L'operazione [X](xref:microsoft.quantum.intrinsic.x), che inverte lo stato del qubit</span><span class="sxs-lookup"><span data-stu-id="f96b0-181">The [X](xref:microsoft.quantum.intrinsic.x) operation, which flips the state of a qubit</span></span>

<span data-ttu-id="f96b0-182">Un'operazione quantistica trasforma lo stato di un qubit.</span><span class="sxs-lookup"><span data-stu-id="f96b0-182">A quantum operation transforms the state of a qubit.</span></span> <span data-ttu-id="f96b0-183">In alcuni casi si parla di gate quantistici anziché di operazioni, per analogia con i gate logici classici.</span><span class="sxs-lookup"><span data-stu-id="f96b0-183">Sometime people talk about quantum gates instead of operations, in analogy to classical logic gates.</span></span> <span data-ttu-id="f96b0-184">Questo risale alle fasi iniziali del calcolo quantistico quando gli algoritmi erano semplicemente un costrutto teorico e venivano visualizzati come diagrammi in modo analogo ai diagrammi di circuito nell'informatica classica.</span><span class="sxs-lookup"><span data-stu-id="f96b0-184">This is rooted in the early days of quantum computing when algorithms were merely a theoretical construct and visualized as diagrams similarly to circuit diagrams in classical computing.</span></span>

### <a name="add-q-test-code"></a><span data-ttu-id="f96b0-185">Aggiungere codice di test Q#</span><span class="sxs-lookup"><span data-stu-id="f96b0-185">Add Q# test code</span></span>

1. <span data-ttu-id="f96b0-186">Aggiungere l'operazione seguente al file `Bell.qs`, all'interno dello spazio dei nomi, dopo la fine dell'operazione `Set`:</span><span class="sxs-lookup"><span data-stu-id="f96b0-186">Add the following operation to the `Bell.qs` file, inside the namespace, after the end of the `Set` operation:</span></span>

    ```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                Set(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            Set(Zero, qubit);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
    ```

    <span data-ttu-id="f96b0-187">Questa operazione (`TestBellState`) verrà ripetuta ciclicamente per `count` iterazioni, imposterà un valore `initial` specificato in un qubit e quindi misurerà (`M`) il risultato.</span><span class="sxs-lookup"><span data-stu-id="f96b0-187">This operation (`TestBellState`) will loop for `count` iterations, set a specified `initial` value on a qubit and then measure (`M`) the result.</span></span> <span data-ttu-id="f96b0-188">Raccoglierà le statistiche sul numero di zeri e di uno misurati e li restituirà al chiamante.</span><span class="sxs-lookup"><span data-stu-id="f96b0-188">It will gather statistics on how many zeros and ones we've measured and return them to the caller.</span></span> <span data-ttu-id="f96b0-189">Esegue inoltre un'altra operazione necessaria.</span><span class="sxs-lookup"><span data-stu-id="f96b0-189">It performs one other necessary operation.</span></span> <span data-ttu-id="f96b0-190">Reimposta il qubit su uno stato noto (`Zero`) prima di restituirlo, per consentire ad altri di allocare questo qubit in uno stato noto.</span><span class="sxs-lookup"><span data-stu-id="f96b0-190">It resets the qubit to a known state (`Zero`) before returning it allowing others to allocate this qubit in a known state.</span></span> <span data-ttu-id="f96b0-191">Questo passaggio è richiesto dall'istruzione `using`.</span><span class="sxs-lookup"><span data-stu-id="f96b0-191">This is required by the `using` statement.</span></span>

### <a name="about-variables-in-q"></a><span data-ttu-id="f96b0-192">Informazioni sulle variabili in Q#</span><span class="sxs-lookup"><span data-stu-id="f96b0-192">About variables in Q#</span></span>

<span data-ttu-id="f96b0-193">Per impostazione predefinita, le variabili in Q# sono non modificabili e non è quindi possibile modificarne il valore dopo che sono state associate.</span><span class="sxs-lookup"><span data-stu-id="f96b0-193">By default, variables in Q# are immutable; their value may not be changed after they are bound.</span></span> <span data-ttu-id="f96b0-194">Viene usata la parola chiave `let` per indicare l'associazione di una variabile non modificabile.</span><span class="sxs-lookup"><span data-stu-id="f96b0-194">The `let` keyword is used to indicate the binding of an immutable variable.</span></span> <span data-ttu-id="f96b0-195">Gli argomenti dell'operazione sono sempre non modificabili.</span><span class="sxs-lookup"><span data-stu-id="f96b0-195">Operation arguments are always immutable.</span></span>

<span data-ttu-id="f96b0-196">Se occorre una variabile il cui valore può essere modificato, ad esempio `numOnes` nell'esempio, è possibile dichiarare la variabile con la parola chiave `mutable`.</span><span class="sxs-lookup"><span data-stu-id="f96b0-196">If you need a variable whose value can change, such as `numOnes` in the example, you can declare the variable with the `mutable` keyword.</span></span> <span data-ttu-id="f96b0-197">È possibile modificare il valore di una variabile modificabile usando un'istruzione `set`.</span><span class="sxs-lookup"><span data-stu-id="f96b0-197">A mutable variable's value may be changed using a `set` statement.</span></span>

<span data-ttu-id="f96b0-198">In entrambi i casi, il tipo di una variabile viene dedotto dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="f96b0-198">In both cases, the type of a variable is inferred by the compiler.</span></span> <span data-ttu-id="f96b0-199">Q# non richiede alcuna annotazione di tipo per le variabili.</span><span class="sxs-lookup"><span data-stu-id="f96b0-199">Q# doesn't require any type annotations for variables.</span></span>

### <a name="about-using-statements-in-q"></a><span data-ttu-id="f96b0-200">Informazioni sulle istruzioni `using` in Q#</span><span class="sxs-lookup"><span data-stu-id="f96b0-200">About `using` statements in Q#</span></span>

<span data-ttu-id="f96b0-201">L'istruzione `using` rappresenta un'istruzione speciale per Q#.</span><span class="sxs-lookup"><span data-stu-id="f96b0-201">The `using` statement is also special to Q#.</span></span> <span data-ttu-id="f96b0-202">Viene usata per allocare i qubit per l'uso in un blocco di codice.</span><span class="sxs-lookup"><span data-stu-id="f96b0-202">It is used to allocate qubits for use in a block of code.</span></span> <span data-ttu-id="f96b0-203">In Q# tutti i qubit vengono allocati e rilasciati in modo dinamico, anziché essere risorse fisse per l'intera durata di un algoritmo complesso.</span><span class="sxs-lookup"><span data-stu-id="f96b0-203">In Q#, all qubits are dynamically allocated and released, rather than being fixed resources that are there for the entire lifetime of a complex algorithm.</span></span> <span data-ttu-id="f96b0-204">Un'istruzione `using` alloca un set di qubit all'inizio e rilascia tali qubit alla fine del blocco.</span><span class="sxs-lookup"><span data-stu-id="f96b0-204">A `using` statement allocates a set of qubits at the start, and releases those qubits at the end of the block.</span></span>

## <a name="create-the-host-application-code"></a><span data-ttu-id="f96b0-205">Creare il codice dell'applicazione host</span><span class="sxs-lookup"><span data-stu-id="f96b0-205">Create the host application code</span></span>

#### <a name="python"></a>[<span data-ttu-id="f96b0-206">Python</span><span class="sxs-lookup"><span data-stu-id="f96b0-206">Python</span></span>](#tab/tabid-python)

1. <span data-ttu-id="f96b0-207">Aprire il file `host.py` e aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="f96b0-207">Open the `host.py` file and add the following code:</span></span>

    ```python
    import qsharp

    from qsharp import Result
    from Quantum.Bell import TestBellState

    initials = (Result.Zero, Result.One)

    for i in initials:
      res = TestBellState.simulate(count=1000, initial=i)
      (num_zeros, num_ones) = res
      print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4}')
    ```

#### <a name="c"></a>[<span data-ttu-id="f96b0-208">C#</span><span class="sxs-lookup"><span data-stu-id="f96b0-208">C#</span></span>](#tab/tabid-csharp)

1. <span data-ttu-id="f96b0-209">Sostituire il contenuto del file `Driver.cs` con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="f96b0-209">Replace the contents of the `Driver.cs` file with the following code:</span></span>

    ```csharp
    using System;

    using Microsoft.Quantum.Simulation.Core;
    using Microsoft.Quantum.Simulation.Simulators;

    namespace Quantum.Bell
    {
        class Driver
        {
            static void Main(string[] args)
            {
                using (var qsim = new QuantumSimulator())
                {
                    // Try initial values
                    Result[] initials = new Result[] { Result.Zero, Result.One };
                    foreach (Result initial in initials)
                    {
                        var res = TestBellState.Run(qsim, 1000, initial).Result;
                        var (numZeros, numOnes) = res;
                        System.Console.WriteLine(
                            $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4}");
                    }
                }

                System.Console.WriteLine("Press any key to continue...");
                Console.ReadKey();
            }
        }
    }
    ```

#### [](#tab/tabid-vs2019)

* * *

### <a name="about-the-host-application-code"></a><span data-ttu-id="f96b0-210">Informazioni sul codice dell'applicazione host</span><span class="sxs-lookup"><span data-stu-id="f96b0-210">About the host application code</span></span>

#### <a name="python"></a>[<span data-ttu-id="f96b0-211">Python</span><span class="sxs-lookup"><span data-stu-id="f96b0-211">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="f96b0-212">L'applicazione host Python è costituita da tre parti:</span><span class="sxs-lookup"><span data-stu-id="f96b0-212">The Python host application has three parts:</span></span>

* <span data-ttu-id="f96b0-213">Calcolo degli argomenti necessari per l'algoritmo quantistico.</span><span class="sxs-lookup"><span data-stu-id="f96b0-213">Compute any arguments required for the quantum algorithm.</span></span> <span data-ttu-id="f96b0-214">Nell'esempio `count` è impostato su 1000 e `initial` è il valore iniziale del qubit.</span><span class="sxs-lookup"><span data-stu-id="f96b0-214">In the example, `count` is fixed at a 1000 and `initial` is the initial value of the qubit.</span></span>
* <span data-ttu-id="f96b0-215">Esecuzione dell'algoritmo quantistico tramite la chiamata al metodo `simulate()` dell'operazione Q# importata.</span><span class="sxs-lookup"><span data-stu-id="f96b0-215">Run the quantum algorithm by calling the `simulate()` method of the imported Q# operation.</span></span>
* <span data-ttu-id="f96b0-216">Elaborazione del risultato dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="f96b0-216">Process the result of the operation.</span></span> <span data-ttu-id="f96b0-217">Nell'esempio `res` riceve il risultato dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="f96b0-217">In the example, `res` receives the result of the operation.</span></span> <span data-ttu-id="f96b0-218">In questo caso, il risultato è una tupla del numero di zeri (`num_zeros`) e del numero di uno (`num_ones`) misurati dal simulatore.</span><span class="sxs-lookup"><span data-stu-id="f96b0-218">Here the result is a tuple of the number of zeros (`num_zeros`) and number of ones (`num_ones`) measured by the simulator.</span></span> <span data-ttu-id="f96b0-219">La tupla viene decostruita per ottenere i due campi e vengono stampati i risultati.</span><span class="sxs-lookup"><span data-stu-id="f96b0-219">We deconstruct the tuple to get the two fields, and print the results.</span></span>

#### <a name="c"></a>[<span data-ttu-id="f96b0-220">C#</span><span class="sxs-lookup"><span data-stu-id="f96b0-220">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="f96b0-221">L'applicazione host C# è costituita da quattro parti:</span><span class="sxs-lookup"><span data-stu-id="f96b0-221">The C# host application has four parts:</span></span>

* <span data-ttu-id="f96b0-222">Costruzione di un simulatore quantistico.</span><span class="sxs-lookup"><span data-stu-id="f96b0-222">Construct a quantum simulator.</span></span> <span data-ttu-id="f96b0-223">Nell'esempio `qsim` è il simulatore.</span><span class="sxs-lookup"><span data-stu-id="f96b0-223">In the example, `qsim` is the simulator.</span></span>
* <span data-ttu-id="f96b0-224">Calcolo degli argomenti necessari per l'algoritmo quantistico.</span><span class="sxs-lookup"><span data-stu-id="f96b0-224">Compute any arguments required for the quantum algorithm.</span></span> <span data-ttu-id="f96b0-225">Nell'esempio `count` è impostato su 1000 e `initial` è il valore iniziale del qubit.</span><span class="sxs-lookup"><span data-stu-id="f96b0-225">In the example, `count` is fixed at a 1000 and `initial` is the initial value of the qubit.</span></span>
* <span data-ttu-id="f96b0-226">Esecuzione dell'algoritmo quantistico.</span><span class="sxs-lookup"><span data-stu-id="f96b0-226">Run the quantum algorithm.</span></span> <span data-ttu-id="f96b0-227">Ogni operazione Q# genera una classe C# con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="f96b0-227">Each Q# operation generates a C# class with the same name.</span></span> <span data-ttu-id="f96b0-228">Questa classe contiene un metodo `Run` che esegue l'operazione in modalità **asincrona**.</span><span class="sxs-lookup"><span data-stu-id="f96b0-228">This class has a `Run` method that **asynchronously** executes the operation.</span></span> <span data-ttu-id="f96b0-229">L'esecuzione è asincrona perché l'esecuzione nell'hardware effettivo sarà asincrona.</span><span class="sxs-lookup"><span data-stu-id="f96b0-229">The execution is asynchronous because execution on actual hardware will be asynchronous.</span></span> <span data-ttu-id="f96b0-230">Poiché il metodo `Run` è asincrono, viene recuperata la proprietà `Result`. L'esecuzione rimarrà così bloccata fino a quanto l'attività non viene completata e non viene restituito il risultato in modo sincrono.</span><span class="sxs-lookup"><span data-stu-id="f96b0-230">Because the `Run` method is asynchronous, we fetch the `Result` property; this blocks execution until the task completes and returns the result synchronously.</span></span>
* <span data-ttu-id="f96b0-231">Elaborazione del risultato dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="f96b0-231">Process the result of the operation.</span></span> <span data-ttu-id="f96b0-232">Nell'esempio `res` riceve il risultato dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="f96b0-232">In the example, `res` receives the result of the operation.</span></span> <span data-ttu-id="f96b0-233">In questo caso, il risultato è una tupla del numero di zeri (`numZeros`) e del numero di uno (`numOnes`) misurati dal simulatore.</span><span class="sxs-lookup"><span data-stu-id="f96b0-233">Here the result is a tuple of the number of zeros (`numZeros`) and number of ones (`numOnes`) measured by the simulator.</span></span> <span data-ttu-id="f96b0-234">In C# questo risultato viene restituito come ValueTuple.</span><span class="sxs-lookup"><span data-stu-id="f96b0-234">This is returned as a ValueTuple in C#.</span></span> <span data-ttu-id="f96b0-235">La tupla viene decostruita per ottenere i due campi, vengono stampati i risultati e si attende la pressione di un tasto.</span><span class="sxs-lookup"><span data-stu-id="f96b0-235">We deconstruct the tuple to get the two fields, print the results, and wait for a keypress.</span></span>

#### [](#tab/tabid-vs2019)

* * *

## <a name="build-and-run"></a><span data-ttu-id="f96b0-236">Compilazione ed esecuzione</span><span class="sxs-lookup"><span data-stu-id="f96b0-236">Build and run</span></span>

#### <a name="python"></a>[<span data-ttu-id="f96b0-237">Python</span><span class="sxs-lookup"><span data-stu-id="f96b0-237">Python</span></span>](#tab/tabid-python)

1. <span data-ttu-id="f96b0-238">Eseguire il comando seguente nel terminale:</span><span class="sxs-lookup"><span data-stu-id="f96b0-238">Run the following command at your terminal:</span></span>

    ```
    python host.py
    ```

    <span data-ttu-id="f96b0-239">Questo comando esegue l'applicazione host, che simula l'operazione Q#.</span><span class="sxs-lookup"><span data-stu-id="f96b0-239">This command runs the host application, which simulates the Q# operation.</span></span>

<span data-ttu-id="f96b0-240">Il risultato sarà:</span><span class="sxs-lookup"><span data-stu-id="f96b0-240">The results should be:</span></span>

```Output
Init:0    0s=1000 1s=0   
Init:1    0s=0    1s=1000
```

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="f96b0-241">Riga di comando/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f96b0-241">Command Line / Visual Studio Code</span></span>](#tab/tabid-csharp)

1. <span data-ttu-id="f96b0-242">Eseguire il comando seguente nel terminale:</span><span class="sxs-lookup"><span data-stu-id="f96b0-242">Run the following at your terminal:</span></span>

    ```bash
    dotnet run
    ```

    <span data-ttu-id="f96b0-243">Questo comando scarica automaticamente tutti i pacchetti necessari, compila l'applicazione e quindi la esegue dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="f96b0-243">This command will automatically download all required packages, build the application, then run it at the command line.</span></span>

1. <span data-ttu-id="f96b0-244">In alternativa, premere **F1** per aprire il riquadro comandi e selezionare **Debug: Avvia senza eseguire debug.**</span><span class="sxs-lookup"><span data-stu-id="f96b0-244">Alternatively, press **F1** to open the Command Palette and select **Debug: Start Without Debugging.**</span></span>
<span data-ttu-id="f96b0-245">Potrebbe essere richiesto di creare un nuovo file ``launch.json`` che descrive come avviare il programma.</span><span class="sxs-lookup"><span data-stu-id="f96b0-245">You may be prompted to create a new ``launch.json`` file describing how to start the program.</span></span>
<span data-ttu-id="f96b0-246">Il file ``launch.json`` predefinito funziona in genere correttamente per la maggior parte delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="f96b0-246">The default ``launch.json`` should work well for most applications.</span></span>

<span data-ttu-id="f96b0-247">Il risultato sarà:</span><span class="sxs-lookup"><span data-stu-id="f96b0-247">The results should be:</span></span>

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

#### <a name="visual-studio"></a>[<span data-ttu-id="f96b0-248">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f96b0-248">Visual Studio</span></span>](#tab/tabid-vs2019)

1. <span data-ttu-id="f96b0-249">È sufficiente premere `F5` per avviare ed eseguire il programma.</span><span class="sxs-lookup"><span data-stu-id="f96b0-249">Just hit `F5`, and your program should build and run!</span></span>

<span data-ttu-id="f96b0-250">Il risultato sarà:</span><span class="sxs-lookup"><span data-stu-id="f96b0-250">The results should be:</span></span>

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

<span data-ttu-id="f96b0-251">Il programma verrà chiuso dopo aver premuto un tasto.</span><span class="sxs-lookup"><span data-stu-id="f96b0-251">The program will exit after you press a key.</span></span>

* * *

## <a name="prepare-superposition"></a><span data-ttu-id="f96b0-252">Preparare la sovrapposizione</span><span class="sxs-lookup"><span data-stu-id="f96b0-252">Prepare superposition</span></span>

<span data-ttu-id="f96b0-253">**Panoramica**: a questo punto verranno esaminate le modalità di espressione di Q# per posizionare i qubit in sovrapposizione.</span><span class="sxs-lookup"><span data-stu-id="f96b0-253">**Overview** Now let’s look at how Q# expresses ways to put qubits in superposition.</span></span>  <span data-ttu-id="f96b0-254">Tenere presente che lo stato di un qubit può essere in una sovrapposizione di 0 e 1.</span><span class="sxs-lookup"><span data-stu-id="f96b0-254">Recall that the state of a qubit can be in a superposition of 0 and 1.</span></span>  <span data-ttu-id="f96b0-255">A tale scopo, verrà usata l'operazione `Hadamard`.</span><span class="sxs-lookup"><span data-stu-id="f96b0-255">We’ll use the `Hadamard` operation to accomplish this.</span></span> <span data-ttu-id="f96b0-256">Se il qubit è in uno degli stati classici (in cui una misura restituisce sempre `Zero` o sempre `One`), l'operazione `Hadamard` o `H` imposterà il qubit su uno stato in cui una misura del qubit restituirà `Zero` il 50% delle volte e `One` il 50% delle volte.</span><span class="sxs-lookup"><span data-stu-id="f96b0-256">If the qubit is in either of the classical states (where a measurement returns `Zero` always or `One` always), then the `Hadamard` or `H` operation will put the qubit in a state where a measurement of the qubit will return `Zero` 50% of the time and return `One` 50% of the time.</span></span>  <span data-ttu-id="f96b0-257">A livello concettuale, il qubit può essere considerato a metà tra `Zero` e `One`.</span><span class="sxs-lookup"><span data-stu-id="f96b0-257">Conceputually, the qubit can be thought of as halfway between the `Zero` and `One`.</span></span>  <span data-ttu-id="f96b0-258">Ora, quando si simula l'operazione `TestBellState`, si osserverà che i risultati restituiranno approssimativamente un numero uguale di `Zero` e `One` dopo la misura.</span><span class="sxs-lookup"><span data-stu-id="f96b0-258">Now, when we simulate the `TestBellState` operation, we will see the results will return roughly an equal number of `Zero` and `One` after measurement.</span></span>  

<span data-ttu-id="f96b0-259">In primo luogo, si tenterà semplicemente di invertire il qubit (se il qubit si trova nello stato `Zero` passerà a `One` e viceversa).</span><span class="sxs-lookup"><span data-stu-id="f96b0-259">First we'll just try to flip the qubit (if the qubit is in `Zero` state will flip to `One` and vice versa).</span></span> <span data-ttu-id="f96b0-260">A tale scopo, si esegue un'operazione `X` prima di misurarlo in `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="f96b0-260">This is accomplished by performing an `X` operation before we measure it in `TestBellState`:</span></span>

```qsharp
X(qubit);
let res = M(qubit);
```

<span data-ttu-id="f96b0-261">I risultati (dopo aver premuto `F5`) sono ora invertiti:</span><span class="sxs-lookup"><span data-stu-id="f96b0-261">Now the results (after pressing `F5`) are reversed:</span></span>

```Output
Init:Zero 0s=0    1s=1000
Init:One  0s=1000 1s=0
```

<span data-ttu-id="f96b0-262">Tuttavia, quanto osservato finora è un'operazione classica.</span><span class="sxs-lookup"><span data-stu-id="f96b0-262">However, everything we've seen so far is classical.</span></span> <span data-ttu-id="f96b0-263">Ora verrà generato un risultato quantistico.</span><span class="sxs-lookup"><span data-stu-id="f96b0-263">Let's get a quantum result.</span></span> <span data-ttu-id="f96b0-264">È sufficiente sostituire l'operazione `X` nell'esecuzione precedente con un'operazione `H` o un'operazione di Hadamard.</span><span class="sxs-lookup"><span data-stu-id="f96b0-264">All we need to do is replace the `X` operation in the previous run with an `H` or Hadamard operation.</span></span> <span data-ttu-id="f96b0-265">Anziché invertire il qubit da 0 a 1, verrà solo invertito a metà.</span><span class="sxs-lookup"><span data-stu-id="f96b0-265">Instead of flipping the qubit all the way from 0 to 1, we will only flip it halfway.</span></span> <span data-ttu-id="f96b0-266">Le righe sostituite in `TestBellState` ora hanno un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="f96b0-266">The replaced lines in `TestBellState` now look like:</span></span>

```qsharp
H(qubit);
let res = M(qubit);
```

<span data-ttu-id="f96b0-267">A questo punto, il risultato diventa più interessante:</span><span class="sxs-lookup"><span data-stu-id="f96b0-267">Now the results get more interesting:</span></span>

```Output
Init:Zero 0s=484  1s=516
Init:One  0s=522  1s=478
```

<span data-ttu-id="f96b0-268">Ogni volta che si esegue una misura, viene richiesto un valore classico, ma il qubit si trova a metà tra 0 e 1, quindi si ottiene (statisticamente) 0 per metà delle volte e 1 per metà delle volte.</span><span class="sxs-lookup"><span data-stu-id="f96b0-268">Every time we measure, we ask for a classical value, but the qubit is halfway between 0 and 1, so we get (statistically) 0 half the time and 1 half the time.</span></span> <span data-ttu-id="f96b0-269">Questa operazione è nota come __sovrapposizione__ e offre la prima osservazione reale dello stato quantistico.</span><span class="sxs-lookup"><span data-stu-id="f96b0-269">This is known as __superposition__ and gives us our first real view into a quantum state.</span></span>

## <a name="prepare-entanglement"></a><span data-ttu-id="f96b0-270">Preparare l'entanglement</span><span class="sxs-lookup"><span data-stu-id="f96b0-270">Prepare entanglement</span></span>

<span data-ttu-id="f96b0-271">**Panoramica:**  a questo punto, osserviamo come Q# esprime i modi per eseguire l'entanglement dei qubit.</span><span class="sxs-lookup"><span data-stu-id="f96b0-271">**Overview:**  Now let’s look at how Q# expresses ways to entangle qubits.</span></span>  <span data-ttu-id="f96b0-272">In primo luogo, si imposta il primo qubit sullo stato iniziale e quindi si usa l'operazione `H` per posizionarlo in sovrapposizione.</span><span class="sxs-lookup"><span data-stu-id="f96b0-272">First, we set the first qubit to the initial state and then use the `H` operation to put it into superposition.</span></span>  <span data-ttu-id="f96b0-273">Quindi, prima di misurare il primo qubit, viene usata una nuova operazione (`CNOT`), che sta per Controlled-Not.</span><span class="sxs-lookup"><span data-stu-id="f96b0-273">Then, before we measure the first qubit, we use a new operation (`CNOT`), which stands for Controlled-Not.</span></span>  <span data-ttu-id="f96b0-274">Il risultato dell'esecuzione di questa operazione su due qubit è l'inversione del secondo qubit se il primo qubit è `One`.</span><span class="sxs-lookup"><span data-stu-id="f96b0-274">The result of executing this operation on two qubits is to flip the second qubit if the first qubit is `One`.</span></span>  <span data-ttu-id="f96b0-275">A questo punto, i due qubit sono correlati (in entanglement).</span><span class="sxs-lookup"><span data-stu-id="f96b0-275">Now, the two qubits are entangled.</span></span>  <span data-ttu-id="f96b0-276">Le statistiche per il primo qubit sono rimaste invariate (probabilità 50-50 di `Zero` o `One`), ma ora quando viene misurato il secondo qubit, è __sempre__ uguale a quanto misurato per il primo qubit.</span><span class="sxs-lookup"><span data-stu-id="f96b0-276">Our statistics for the first qubit haven't changed (50-50 chance of a `Zero` or a `One` after measurement), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit.</span></span> <span data-ttu-id="f96b0-277">Il gate `CNOT` ha eseguito l'entanglement dei due qubit, così qualsiasi cosa accade a uno di essi, accade anche all'altro.</span><span class="sxs-lookup"><span data-stu-id="f96b0-277">Our `CNOT` has entangled the two qubits, so that whatever happens to one of them, happens to the other.</span></span> <span data-ttu-id="f96b0-278">Se sono state invertite le misure, ovvero se è stato misurato il secondo qubit prima del primo, si verificherà lo stesso risultato.</span><span class="sxs-lookup"><span data-stu-id="f96b0-278">If you reversed the measurements (did the second qubit before the first), the same thing would happen.</span></span> <span data-ttu-id="f96b0-279">La prima misura sarà casuale e la seconda si troverà nel passaggio del blocco con quanto individuato per la prima.</span><span class="sxs-lookup"><span data-stu-id="f96b0-279">The first measurement would be random and the second would be in lock step with whatever was discovered for the first.</span></span>

<span data-ttu-id="f96b0-280">Per prima cosa è necessario allocare 2 qubit invece di uno in `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="f96b0-280">The first thing we'll need to do is allocate 2 qubits instead of one in `TestBellState`:</span></span>

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

<span data-ttu-id="f96b0-281">Questo consentirà di aggiungere una nuova operazione (`CNOT`) prima di misurare (`M`) in `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="f96b0-281">This will allow us to add a new operation (`CNOT`) before we measure  (`M`) in `TestBellState`:</span></span>

```qsharp
Set(initial, q0);
Set(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

<span data-ttu-id="f96b0-282">È stata aggiunta un'altra operazione `Set` per inizializzare il primo qubit per assicurarsi che sia sempre nello stato `Zero` quando si inizia.</span><span class="sxs-lookup"><span data-stu-id="f96b0-282">We've added another `Set` operation to initialize the first qubit to make sure that it's always in the `Zero` state when we start.</span></span>

<span data-ttu-id="f96b0-283">È anche necessario reimpostare il secondo qubit prima di rilasciarlo.</span><span class="sxs-lookup"><span data-stu-id="f96b0-283">We also need to reset the second qubit before releasing it.</span></span>

```qsharp
Set(Zero, q0);
Set(Zero, q1);
```

<span data-ttu-id="f96b0-284">La routine completa ha ora un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="f96b0-284">The full routine now looks like this:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set (initial, q0);
                Set (Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
```

<span data-ttu-id="f96b0-285">Se viene eseguita,si otterrà esattamente lo stesso risultato 50-50 ottenuto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="f96b0-285">If we run this, we'll get exactly the same 50-50 result we got before.</span></span> <span data-ttu-id="f96b0-286">Tuttavia, l'aspetto interessante è il modo in cui il secondo qubit reagisce alla prima misurazione.</span><span class="sxs-lookup"><span data-stu-id="f96b0-286">However, what we're interested in is how the second qubit reacts to the first being measured.</span></span> <span data-ttu-id="f96b0-287">Questa statistica verrà aggiunta con una nuova versione dell'operazione `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="f96b0-287">We'll add this statistic with a new version of the `TestBellState` operation:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int, Int) {
        mutable numOnes = 0;
        mutable agree = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set(initial, q0);
                Set(Zero, q1);

                H(q0);
                CNOT(q0, q1);
                let res = M(q0);

                if (M(q1) == res) {
                    set agree += 1;
                }

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes, agree);
    }
```

<span data-ttu-id="f96b0-288">Il nuovo valore restituito (`agree`) tiene traccia di ogni volta che la misurazione del primo qubit corrisponde alla misurazione del secondo qubit.</span><span class="sxs-lookup"><span data-stu-id="f96b0-288">The new return value (`agree`) keeps track of every time the measurement from the first qubit matches the measurement of the second qubit.</span></span> <span data-ttu-id="f96b0-289">È anche necessario aggiornare l'applicazione host di conseguenza:</span><span class="sxs-lookup"><span data-stu-id="f96b0-289">We also have to update the host application accordingly:</span></span>

#### <a name="python"></a>[<span data-ttu-id="f96b0-290">Python</span><span class="sxs-lookup"><span data-stu-id="f96b0-290">Python</span></span>](#tab/tabid-python)

```python
import qsharp

from qsharp import Result
from Quantum.Bell import TestBellState

initials = {Result.Zero, Result.One} 

for i in initials:
    res = TestBellState.simulate(count=1000, initial=i)
    (num_zeros, num_ones, agree) = res
    print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4} agree={agree: <4}')
```

#### <a name="c"></a>[<span data-ttu-id="f96b0-291">C#</span><span class="sxs-lookup"><span data-stu-id="f96b0-291">C#</span></span>](#tab/tabid-csharp)

```csharp
            using (var qsim = new QuantumSimulator())
            {
                // Try initial values
                Result[] initials = new Result[] { Result.Zero, Result.One };
                foreach (Result initial in initials)
                {
                    var res = TestBellState.Run(qsim, 1000, initial).Result;
                    var (numZeros, numOnes, agree) = res;
                    System.Console.WriteLine(
                        $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4} agree={agree,-4}");
                }
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
```

#### [](#tab/tabid-vs2019)

* * *

<span data-ttu-id="f96b0-292">A questo punto, quando viene eseguita, si ottiene un risultato sorprendente:</span><span class="sxs-lookup"><span data-stu-id="f96b0-292">Now when we run, we get something pretty amazing:</span></span>

```Output
Init:Zero 0s=499  1s=501  agree=1000
Init:One  0s=490  1s=510  agree=1000
```

<span data-ttu-id="f96b0-293">Come dichiarato nella panoramica, le statistiche per il primo qubit sono rimaste invariate (probabilità 50-50 di uno 0 o 1), ma ora quando viene misurato il secondo qubit, è __sempre__ uguale a quanto misurato per il primo qubit perché sono correlati (in entanglement).</span><span class="sxs-lookup"><span data-stu-id="f96b0-293">As stated in the overview, our statistics for the first qubit haven't changed (50-50 chance of a 0 or a 1), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit, because they are entangled!</span></span>

<span data-ttu-id="f96b0-294">Congratulazioni, è stata completata la scrittura del primo programma quantistico.</span><span class="sxs-lookup"><span data-stu-id="f96b0-294">Congratulations, you've written your first quantum program!</span></span>

## <a name="whats-next"></a><span data-ttu-id="f96b0-295">Quali sono le operazioni successive?</span><span class="sxs-lookup"><span data-stu-id="f96b0-295">What's next?</span></span>

<span data-ttu-id="f96b0-296">L'esercitazione dell'avvio rapido sulla [Ricerca di Grover](xref:microsoft.quantum.quickstarts.search) mostra come creare ed eseguire la ricerca di Grover, uno degli algoritmi di calcolo quantistico più diffusi, e offre un esempio interessante di un programma Q# che può essere usato per risolvere problemi reali con il calcolo quantistico.</span><span class="sxs-lookup"><span data-stu-id="f96b0-296">The QuickStart [Grover’s search](xref:microsoft.quantum.quickstarts.search) shows you how to build and run Grover search, one of the most popular quantum computing algorithms and offers a nice example of a Q# program that can be used to solve real problems with quantum computing.</span></span>  

<span data-ttu-id="f96b0-297">[Introduzione a Quantum Development Kit](xref:microsoft.quantum.welcome) consiglia altri modi per imparare a usare Q# e la programmazione quantistica.</span><span class="sxs-lookup"><span data-stu-id="f96b0-297">[Get Started with the Quantum Development Kit](xref:microsoft.quantum.welcome) recommends more ways to learn Q# and quantum programming.</span></span>

