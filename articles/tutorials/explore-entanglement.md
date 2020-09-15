---
title: Esplora l'intreccio con Q#
description: Informazioni su come scrivere un programma Quantum in Q# . Sviluppare un'applicazione Stato di Bell usando Quantum Development Kit (QDK)
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 05/29/2020
ms.topic: tutorial
uid: microsoft.quantum.write-program
no-loc:
- Q#
- $$v
ms.openlocfilehash: 3e95f142572e104fe1e133b109d197ed5bb01d9a
ms.sourcegitcommit: af2e9691c1900ced7e09d6320255617c9939ed55
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2020
ms.locfileid: "90063241"
---
# <a name="tutorial-explore-entanglement-with-q"></a><span data-ttu-id="7b745-104">Esercitazione: Esplorare l'entanglement con Q#\#</span><span class="sxs-lookup"><span data-stu-id="7b745-104">Tutorial: Explore entanglement with Q\#</span></span>

<span data-ttu-id="7b745-105">Questa esercitazione illustra come scrivere un Q# programma che manipola e misura qubits e illustra gli effetti della superposizione e del groviglio.</span><span class="sxs-lookup"><span data-stu-id="7b745-105">In this tutorial, we show you how to write a Q# program that manipulates and measures qubits and demonstrates the effects of superposition and entanglement.</span></span>

<span data-ttu-id="7b745-106">Verrà scritta un'applicazione denominata Bell per illustrare l'entanglement quantistico.</span><span class="sxs-lookup"><span data-stu-id="7b745-106">You will write an application called Bell to demonstrate quantum entanglement.</span></span>
<span data-ttu-id="7b745-107">Il nome Bell fa riferimento agli stati di Bell, che sono stati quantistici specifici di due qubit che vengono usati per rappresentare gli esempi più semplici di sovrapposizione e di entanglement quantistico.</span><span class="sxs-lookup"><span data-stu-id="7b745-107">The name Bell is in reference to Bell states, which are specific quantum states of two qubits that are used to represent the simplest examples of superposition and quantum entanglement.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="7b745-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="7b745-108">Pre-requisites</span></span>

<span data-ttu-id="7b745-109">Se si è pronti per iniziare a scrivere codice, seguire questa procedura prima di procedere:</span><span class="sxs-lookup"><span data-stu-id="7b745-109">If you are ready to start coding, follow these steps before proceeding:</span></span> 

* <span data-ttu-id="7b745-110">[Installare](xref:microsoft.quantum.install) Quantum Development Kit usando il linguaggio e l'ambiente di sviluppo preferiti.</span><span class="sxs-lookup"><span data-stu-id="7b745-110">[Install](xref:microsoft.quantum.install) the Quantum Development Kit using your  preferred language and development environment.</span></span>
* <span data-ttu-id="7b745-111">Se il QDK è già installato, assicurarsi di aver eseguito l'[aggiornamento](xref:microsoft.quantum.update) alla versione più recente</span><span class="sxs-lookup"><span data-stu-id="7b745-111">If you already have the QDK installed, make sure you have [updated](xref:microsoft.quantum.update) to the latest version</span></span>

<span data-ttu-id="7b745-112">È anche possibile seguire la descrizione senza installare QDK, esaminando le panoramiche del Q# linguaggio di programmazione e i primi concetti di quantum computing.</span><span class="sxs-lookup"><span data-stu-id="7b745-112">You can also follow along with the narrative without installing the QDK, reviewing  the overviews of the Q# programming language and the first concepts of quantum computing.</span></span>

## <a name="in-this-tutorial-youll-learn-how-to"></a><span data-ttu-id="7b745-113">In questa esercitazione si apprenderà come:</span><span class="sxs-lookup"><span data-stu-id="7b745-113">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="7b745-114">Creare e combinare operazioni in Q\#</span><span class="sxs-lookup"><span data-stu-id="7b745-114">Create and combine operations in Q\#</span></span>
> * <span data-ttu-id="7b745-115">Consente di creare operazioni per inserire qubits nella superposizione, impigliarli e misurarli.</span><span class="sxs-lookup"><span data-stu-id="7b745-115">Create operations to put qubits in superposition, entangle and measure them.</span></span>
> * <span data-ttu-id="7b745-116">Dimostrare l'intrico di Quantum con un Q# programma eseguito in un simulatore.</span><span class="sxs-lookup"><span data-stu-id="7b745-116">Demonstrate quantum entanglement with a Q# program run in a simulator.</span></span> 

## <a name="demonstrating-qubit-behavior-with-the-qdk"></a><span data-ttu-id="7b745-117">Dimostrazione del comportamento di qubit con QDK</span><span class="sxs-lookup"><span data-stu-id="7b745-117">Demonstrating qubit behavior with the QDK</span></span>

<span data-ttu-id="7b745-118">Mentre i bit classici contengono un singolo valore binario come 0 o 1, lo stato di un [qubit](xref:microsoft.quantum.glossary#qubit) può essere una **sovrapposizione** di 0 e 1.</span><span class="sxs-lookup"><span data-stu-id="7b745-118">Where classical bits hold a single binary value such as a 0 or 1, the state of a [qubit](xref:microsoft.quantum.glossary#qubit) can be in a **superposition** of 0 and 1.</span></span>  <span data-ttu-id="7b745-119">A livello concettuale, lo stato di un qubit può essere considerato come una direzione in uno spazio astratto (noto anche come vettore).</span><span class="sxs-lookup"><span data-stu-id="7b745-119">Conceptually, the state of a qubit can be thought of as a direction in an abstract space (also known as a vector).</span></span>  <span data-ttu-id="7b745-120">Uno stato qubit può essere in una delle direzioni possibili.</span><span class="sxs-lookup"><span data-stu-id="7b745-120">A qubit state can be in any of the possible directions.</span></span> <span data-ttu-id="7b745-121">I due **stati classici** sono le due direzioni, che rappresentano la probabilità del 100% di misurare 0 e del 100% di misurare 1.</span><span class="sxs-lookup"><span data-stu-id="7b745-121">The two **classical states** are the two directions; representing 100% chance of measuring 0 and 100% chance of measuring 1.</span></span>

<span data-ttu-id="7b745-122">L'azione di misurazione genera un risultato binario e modifica lo stato del qubit.</span><span class="sxs-lookup"><span data-stu-id="7b745-122">The act of measurement produces a binary result and changes a qubit state.</span></span>
<span data-ttu-id="7b745-123">La misurazione produce un valore binario, ovvero 0 o 1.</span><span class="sxs-lookup"><span data-stu-id="7b745-123">Measurement  produces a binary value, either 0 or 1.</span></span>  <span data-ttu-id="7b745-124">Il qubit passa dall'essere in sovrapposizione (qualsiasi direzione) a uno degli stati classici.</span><span class="sxs-lookup"><span data-stu-id="7b745-124">The qubit goes from being in superposition (any direction) to one of the classical states.</span></span>  <span data-ttu-id="7b745-125">Successivamente, la ripetizione della stessa misurazione senza alcuna operazione genera lo stesso risultato binario.</span><span class="sxs-lookup"><span data-stu-id="7b745-125">Thereafter, repeating the same measurement without any intervening operations produces the same binary result.</span></span>  

<span data-ttu-id="7b745-126">Più qubit possono anche trovarsi in uno stato di [**entanglement**](xref:microsoft.quantum.glossary#entanglement).</span><span class="sxs-lookup"><span data-stu-id="7b745-126">Multiple qubits can be [**entangled**](xref:microsoft.quantum.glossary#entanglement).</span></span>  <span data-ttu-id="7b745-127">Quando si esegue la misurazione di un qubit con entanglement, vengono aggiornate anche le informazioni sullo stato degli altri qubit.</span><span class="sxs-lookup"><span data-stu-id="7b745-127">When we make a measurement of one entangled qubit, our knowledge of the state of the other(s) is updated as well.</span></span>

<span data-ttu-id="7b745-128">A questo punto si è pronti per dimostrare in che modo Q# esprime questo comportamento.</span><span class="sxs-lookup"><span data-stu-id="7b745-128">Now, we're ready to demonstrate how Q# expresses this behavior.</span></span>  <span data-ttu-id="7b745-129">Si inizierà con il programma più semplice possibile e lo si svilupperà per mostrare la sovrapposizione quantistica e l'entanglement quantistico.</span><span class="sxs-lookup"><span data-stu-id="7b745-129">You start with the simplest program possible and build it up to demonstrate quantum superposition and quantum entanglement.</span></span>

## <a name="creating-a-no-locq-project"></a><span data-ttu-id="7b745-130">Creazione di un Q# progetto</span><span class="sxs-lookup"><span data-stu-id="7b745-130">Creating a Q# project</span></span>

<span data-ttu-id="7b745-131">La prima cosa da fare è creare un nuovo Q# progetto.</span><span class="sxs-lookup"><span data-stu-id="7b745-131">The first thing we have to do is to create a new Q# project.</span></span> <span data-ttu-id="7b745-132">In questa esercitazione verrà usato l'ambiente in base alle [ Q# applicazioni con vs code](xref:microsoft.quantum.install.standalone).</span><span class="sxs-lookup"><span data-stu-id="7b745-132">In this tutorial we are going to use the environment based on [Q# applications with VS Code](xref:microsoft.quantum.install.standalone).</span></span>

<span data-ttu-id="7b745-133">Per creare un nuovo progetto, in VS Code:</span><span class="sxs-lookup"><span data-stu-id="7b745-133">To create a new project, in VS Code:</span></span> 

1. <span data-ttu-id="7b745-134">Fare clic su **Visualizza** -> **Riquadro comandi** e selezionare **Q#: Create New Project**(ASA: Crea nuovo progetto).</span><span class="sxs-lookup"><span data-stu-id="7b745-134">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="7b745-135">Click **Standalone console application** (Applicazione console autonoma).</span><span class="sxs-lookup"><span data-stu-id="7b745-135">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="7b745-136">Passare al percorso in cui salvare il progetto e fare clic su **Create Project** (Crea progetto).</span><span class="sxs-lookup"><span data-stu-id="7b745-136">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="7b745-137">Al termine dell'operazione, fare clic su **Open new project** (Apri nuovo progetto) in basso a destra.</span><span class="sxs-lookup"><span data-stu-id="7b745-137">When the project is successfully created, click **Open new project...** in the lower right.</span></span>

<span data-ttu-id="7b745-138">In questo caso è stato chiamato il progetto `Bell` .</span><span class="sxs-lookup"><span data-stu-id="7b745-138">In this case we called the project `Bell`.</span></span> <span data-ttu-id="7b745-139">Vengono generati due file: `Bell.csproj` , il file di progetto e `Program.qs` , un modello di Q# applicazione che verrà usato per scrivere l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7b745-139">This generates two files: `Bell.csproj`, the project file and `Program.qs`, a template of a Q# application that we will use to write our application.</span></span> <span data-ttu-id="7b745-140">Il contenuto di `Program.qs` deve essere:</span><span class="sxs-lookup"><span data-stu-id="7b745-140">The content of `Program.qs` should be:</span></span>

```qsharp
   namespace Bell {

      open Microsoft.Quantum.Canon;
      open Microsoft.Quantum.Intrinsic;
    

      @EntryPoint()
      operation HelloQ() : Unit {
          Message("Hello quantum world!");
      }
   }
```

## <a name="write-the-q-application"></a><span data-ttu-id="7b745-141">Scrivere l' \# applicazione Q</span><span class="sxs-lookup"><span data-stu-id="7b745-141">Write the Q\# application</span></span>
 
<span data-ttu-id="7b745-142">L'obiettivo è quello di preparare due qubits in uno stato quantico specifico, dimostrando come operare su qubits con Q# per modificare il proprio stato e dimostrare gli effetti della superposizione e del groviglio.</span><span class="sxs-lookup"><span data-stu-id="7b745-142">Our goal is to prepare two qubits in a specific quantum state, demonstrating how to operate on qubits with Q# to change their state and demonstrate the effects of superposition and entanglement.</span></span> <span data-ttu-id="7b745-143">Questa operazione verrà compilata in base a un elemento per introdurre gli Stati, le operazioni e la misurazione di qubit.</span><span class="sxs-lookup"><span data-stu-id="7b745-143">We will build this up piece by piece to introduce qubit states, operations, and measurement.</span></span>

### <a name="initialize-qubit-using-measurement"></a><span data-ttu-id="7b745-144">Inizializzare qubit usando la misurazione</span><span class="sxs-lookup"><span data-stu-id="7b745-144">Initialize qubit using measurement</span></span>

<span data-ttu-id="7b745-145">Nel primo codice riportato di seguito viene illustrato come utilizzare qubits in Q# .</span><span class="sxs-lookup"><span data-stu-id="7b745-145">In the first code below, we show you how to work with qubits in Q#.</span></span>  <span data-ttu-id="7b745-146">Verranno introdotte due operazioni, [`M`](xref:microsoft.quantum.intrinsic.m) [`X`](xref:microsoft.quantum.intrinsic.x) che trasformano lo stato di un qubit.</span><span class="sxs-lookup"><span data-stu-id="7b745-146">We’ll introduce two operations, [`M`](xref:microsoft.quantum.intrinsic.m) and [`X`](xref:microsoft.quantum.intrinsic.x) that transform the state of a qubit.</span></span> <span data-ttu-id="7b745-147">In questo frammento di codice viene definita un'operazione `SetQubitState` che accetta come parametro un qubit e un altro parametro, `desired`, che rappresenta lo stato in cui deve trovarsi il qubit.</span><span class="sxs-lookup"><span data-stu-id="7b745-147">In this code snippet, an operation `SetQubitState` is defined that takes as a parameter a qubit and another parameter, `desired`, representing the state that we would like the qubit to be in.</span></span>  <span data-ttu-id="7b745-148">L'operazione `SetQubitState` esegue una misura del qubit tramite l'operazione `M`.</span><span class="sxs-lookup"><span data-stu-id="7b745-148">The operation `SetQubitState` performs a measurement on the qubit using the operation `M`.</span></span>  <span data-ttu-id="7b745-149">In Q# una misura qubit restituisce sempre `Zero` o `One` .</span><span class="sxs-lookup"><span data-stu-id="7b745-149">In Q#, a qubit measurement always returns either `Zero` or `One`.</span></span>  <span data-ttu-id="7b745-150">Se la misurazione restituisce un valore diverso da quello desiderato, `SetQubitState` "capovolge" qubit, ovvero esegue un' `X` operazione, che modifica lo stato qubit in un nuovo stato in cui le probabilità di una misurazione `Zero` che restituisce e `One` sono invertite.</span><span class="sxs-lookup"><span data-stu-id="7b745-150">If the measurement returns a value not equal to the desired value, `SetQubitState` “flips” the qubit; that is, it executes an `X` operation, which changes the qubit state to a new state in which the probabilities of a measurement returning `Zero` and `One` are reversed.</span></span> <span data-ttu-id="7b745-151">In questo modo, `SetQubitState` inserisce sempre il qubit di destinazione nello stato desiderato.</span><span class="sxs-lookup"><span data-stu-id="7b745-151">This way, `SetQubitState` always puts the target qubit in the desired state.</span></span>

<span data-ttu-id="7b745-152">Sostituire il contenuto di `Program.qs` con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="7b745-152">Replace the contents of `Program.qs` with the following code:</span></span>


```qsharp
   namespace Bell {
       open Microsoft.Quantum.Intrinsic;
       open Microsoft.Quantum.Canon;

       operation SetQubitState(desired : Result, q1 : Qubit) : Unit {
           if (desired != M(q1)) {
               X(q1);
           }
       }
   }
```

<span data-ttu-id="7b745-153">Questa operazione può ora essere chiamata per impostare un qubit su uno stato classico, restituendo `Zero` il 100% delle volte o restituendo `One` il 100% delle volte.</span><span class="sxs-lookup"><span data-stu-id="7b745-153">This operation may now be called to set a qubit to a classical state, either returning `Zero` 100% of the time or returning `One` 100% of the time.</span></span>
<span data-ttu-id="7b745-154">`Zero` e `One` sono costanti che rappresentano gli unici due risultati possibili della misura di un qubit.</span><span class="sxs-lookup"><span data-stu-id="7b745-154">`Zero` and `One` are constants that represent the only two possible results of a measurement of a qubit.</span></span>

<span data-ttu-id="7b745-155">L'operazione `SetQubitState` misura il qubit.</span><span class="sxs-lookup"><span data-stu-id="7b745-155">The operation `SetQubitState` measures the qubit.</span></span> <span data-ttu-id="7b745-156">Se il qubit si trova nello stato desiderato, `SetQubitState` lo lascia invariato. In caso contrario, esegue l'operazione `X` che modifica lo stato del qubit impostandolo sullo stato desiderato.</span><span class="sxs-lookup"><span data-stu-id="7b745-156">If the qubit is in the state we want, `SetQubitState` leaves it alone; otherwise, by executing the `X` operation, we change the qubit state to the desired state.</span></span>

#### <a name="about-no-locq-operations"></a><span data-ttu-id="7b745-157">Informazioni sulle Q# operazioni</span><span class="sxs-lookup"><span data-stu-id="7b745-157">About Q# operations</span></span>

<span data-ttu-id="7b745-158">Un' Q# operazione è una subroutine Quantum.</span><span class="sxs-lookup"><span data-stu-id="7b745-158">A Q# operation is a quantum subroutine.</span></span> <span data-ttu-id="7b745-159">Ovvero una routine chiamabile che contiene chiamate ad altre operazioni Quantum.</span><span class="sxs-lookup"><span data-stu-id="7b745-159">That is, it is a callable routine that contains calls to other quantum operations.</span></span>

<span data-ttu-id="7b745-160">Gli argomenti di un'operazione vengono specificati come tuple, racchiuse tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="7b745-160">The arguments to an operation are specified as a tuple, within parentheses.</span></span>

<span data-ttu-id="7b745-161">Il tipo restituito dell'operazione viene specificato dopo i due punti.</span><span class="sxs-lookup"><span data-stu-id="7b745-161">The return type of the operation is specified after a colon.</span></span> <span data-ttu-id="7b745-162">In questo caso, l'operazione `SetQubitState` non restituisce alcun risultato, quindi viene contrassegnata come se avesse restituito `Unit`.</span><span class="sxs-lookup"><span data-stu-id="7b745-162">In this case, the `SetQubitState` operation has no return, so it is marked as returning `Unit`.</span></span> <span data-ttu-id="7b745-163">Si tratta dell' Q# equivalente di `unit` in F #, che è approssimativamente analogo a `void` in C# e di una tupla vuota in Python ( `()` , rappresentata dall'hint di tipo `Tuple[()]` ).</span><span class="sxs-lookup"><span data-stu-id="7b745-163">This is the Q# equivalent of `unit` in F#, which is roughly analogous to `void` in C#, and an empty tuple in Python (`()`, represented by the type hint `Tuple[()]`).</span></span>

<span data-ttu-id="7b745-164">Sono state usate due operazioni Quantum nella prima Q# operazione:</span><span class="sxs-lookup"><span data-stu-id="7b745-164">You have used two quantum operations in your first Q# operation:</span></span>

* <span data-ttu-id="7b745-165">[`M`](xref:microsoft.quantum.intrinsic.m)Operazione, che misura lo stato di qubit</span><span class="sxs-lookup"><span data-stu-id="7b745-165">The [`M`](xref:microsoft.quantum.intrinsic.m) operation, which measures the state of the qubit</span></span>
* <span data-ttu-id="7b745-166">[`X`](xref:microsoft.quantum.intrinsic.x)Operazione, che capovolge lo stato di un qubit</span><span class="sxs-lookup"><span data-stu-id="7b745-166">The [`X`](xref:microsoft.quantum.intrinsic.x) operation, which flips the state of a qubit</span></span>

<span data-ttu-id="7b745-167">Un'operazione quantistica trasforma lo stato di un qubit.</span><span class="sxs-lookup"><span data-stu-id="7b745-167">A quantum operation transforms the state of a qubit.</span></span> <span data-ttu-id="7b745-168">In alcuni casi si parla di gate quantistici anziché di operazioni, per analogia con i gate logici classici.</span><span class="sxs-lookup"><span data-stu-id="7b745-168">Sometime people talk about quantum gates instead of operations, in analogy to classical logic gates.</span></span> <span data-ttu-id="7b745-169">Questo risale alle fasi iniziali del calcolo quantistico quando gli algoritmi erano semplicemente un costrutto teorico e venivano visualizzati come diagrammi in modo analogo ai diagrammi di circuito nell'informatica classica.</span><span class="sxs-lookup"><span data-stu-id="7b745-169">This is rooted in the early days of quantum computing when algorithms were merely a theoretical construct and visualized as diagrams similarly to circuit diagrams in classical computing.</span></span>

### <a name="counting-measurement-outcomes"></a><span data-ttu-id="7b745-170">Conteggio dei risultati di misurazione</span><span class="sxs-lookup"><span data-stu-id="7b745-170">Counting measurement outcomes</span></span>

<span data-ttu-id="7b745-171">Per illustrare l'effetto dell'operazione `SetQubitState`, viene quindi aggiunta un'operazione `TestBellState`.</span><span class="sxs-lookup"><span data-stu-id="7b745-171">To demonstrate the effect of the `SetQubitState` operation, a `TestBellState` operation is then added.</span></span> <span data-ttu-id="7b745-172">Questa operazione accetta come input `Zero` o `One`, chiama l'operazione `SetQubitState` un determinato numero di volte con tale input e conta il numero di volte in cui la misura del qubit ha restituito `Zero` e il numero di volte in cui ha restituito `One`.</span><span class="sxs-lookup"><span data-stu-id="7b745-172">This operation takes as input a `Zero` or `One`, and calls the `SetQubitState` operation some number of times with that input, and counts the number of times that `Zero` was returned from the measurement of the qubit and the number of times that `One` was returned.</span></span> <span data-ttu-id="7b745-173">Naturalmente, in questa prima simulazione dell'operazione `TestBellState`, si prevede che l'output mostri che tutte le misure del qubit impostato con `Zero` come input del parametro restituiranno `Zero` e tutte le misure di un qubit impostato con `One` come input del parametro restituiranno `One`.</span><span class="sxs-lookup"><span data-stu-id="7b745-173">Of course, in this first simulation of the `TestBellState` operation, we expect that the output will show that all measurements of the qubit set with `Zero` as the parameter input will return `Zero`, and all measurements of a qubit set with `One` as the parameter input will return `One`.</span></span> <span data-ttu-id="7b745-174">Successivamente, verrà aggiunto il codice a `TestBellState` per dimostrare la superposizione e l'aggancio.</span><span class="sxs-lookup"><span data-stu-id="7b745-174">Further on, we’ll add code to `TestBellState` to demonstrate superposition and entanglement.</span></span>

<span data-ttu-id="7b745-175">Aggiungere l'operazione seguente al file `Program.qs`, all'interno dello spazio dei nomi, dopo la fine dell'operazione `SetQubitState`:</span><span class="sxs-lookup"><span data-stu-id="7b745-175">Add the following operation to the `Program.qs` file, inside the namespace, after the end of the `SetQubitState` operation:</span></span>

```qsharp
   operation TestBellState(count : Int, initial : Result) : (Int, Int) {

       mutable numOnes = 0;
       using (qubit = Qubit()) {

           for (test in 1..count) {
               SetQubitState(initial, qubit);
               let res = M(qubit);

               // Count the number of ones we saw:
               if (res == One) {
                   set numOnes += 1;
               }
           }
            
           SetQubitState(Zero, qubit);
       }

       // Return number of times we saw a |0> and number of times we saw a |1>
       Message("Test results (# of 0s, # of 1s): ");
       return (count - numOnes, numOnes);
   }
```
<span data-ttu-id="7b745-176">Si noti che è stata aggiunta una riga prima `return` di per stampare un messaggio esplicativo nella console con la funzione ( `Message` ) [Microsoft. Quantum. intrinsec. Message]</span><span class="sxs-lookup"><span data-stu-id="7b745-176">Note that we added a line before the `return` to print an explanatory message in the console with the function (`Message`)[microsoft.quantum.intrinsic.message]</span></span>

<span data-ttu-id="7b745-177">Questa operazione (`TestBellState`) verrà ripetuta ciclicamente per `count` iterazioni, imposterà un valore `initial` specificato in un qubit e quindi misurerà (`M`) il risultato.</span><span class="sxs-lookup"><span data-stu-id="7b745-177">This operation (`TestBellState`) will loop for `count` iterations, set a specified `initial` value on a qubit and then measure (`M`) the result.</span></span> <span data-ttu-id="7b745-178">Raccoglierà le statistiche sul numero di zeri e di uno misurati e li restituirà al chiamante.</span><span class="sxs-lookup"><span data-stu-id="7b745-178">It will gather statistics on how many zeros and ones we've measured and return them to the caller.</span></span> <span data-ttu-id="7b745-179">Esegue inoltre un'altra operazione necessaria.</span><span class="sxs-lookup"><span data-stu-id="7b745-179">It performs one other necessary operation.</span></span> <span data-ttu-id="7b745-180">Reimposta il qubit su uno stato noto (`Zero`) prima di restituirlo, per consentire ad altri di allocare questo qubit in uno stato noto.</span><span class="sxs-lookup"><span data-stu-id="7b745-180">It resets the qubit to a known state (`Zero`) before returning it allowing others to allocate this qubit in a known state.</span></span> <span data-ttu-id="7b745-181">Questo passaggio è richiesto dall'istruzione `using`.</span><span class="sxs-lookup"><span data-stu-id="7b745-181">This is required by the `using` statement.</span></span>

#### <a name="about-variables-in-q"></a><span data-ttu-id="7b745-182">Informazioni sulle variabili in Q\#</span><span class="sxs-lookup"><span data-stu-id="7b745-182">About variables in Q\#</span></span>

<span data-ttu-id="7b745-183">Per impostazione predefinita, le variabili in Q# non sono modificabili. il relativo valore non può essere modificato dopo l'associazione.</span><span class="sxs-lookup"><span data-stu-id="7b745-183">By default, variables in Q# are immutable; their value may not be changed after they are bound.</span></span> <span data-ttu-id="7b745-184">Viene usata la parola chiave `let` per indicare l'associazione di una variabile non modificabile.</span><span class="sxs-lookup"><span data-stu-id="7b745-184">The `let` keyword is used to indicate the binding of an immutable variable.</span></span> <span data-ttu-id="7b745-185">Gli argomenti dell'operazione sono sempre non modificabili.</span><span class="sxs-lookup"><span data-stu-id="7b745-185">Operation arguments are always immutable.</span></span>

<span data-ttu-id="7b745-186">Se occorre una variabile il cui valore può essere modificato, ad esempio `numOnes` nell'esempio, è possibile dichiarare la variabile con la parola chiave `mutable`.</span><span class="sxs-lookup"><span data-stu-id="7b745-186">If you need a variable whose value can change, such as `numOnes` in the example, you can declare the variable with the `mutable` keyword.</span></span> <span data-ttu-id="7b745-187">È possibile modificare il valore di una variabile modificabile usando un'istruzione `setQubitState`.</span><span class="sxs-lookup"><span data-stu-id="7b745-187">A mutable variable's value may be changed using a `setQubitState` statement.</span></span>

<span data-ttu-id="7b745-188">In entrambi i casi, il tipo di una variabile viene dedotto dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="7b745-188">In both cases, the type of a variable is inferred by the compiler.</span></span> <span data-ttu-id="7b745-189">Q# non richiede alcuna annotazione di tipo per le variabili.</span><span class="sxs-lookup"><span data-stu-id="7b745-189">Q# doesn't require any type annotations for variables.</span></span>

#### <a name="about-using-statements-in-q"></a><span data-ttu-id="7b745-190">Informazioni sulle `using` istruzioni in Q\#</span><span class="sxs-lookup"><span data-stu-id="7b745-190">About `using` statements in Q\#</span></span>

<span data-ttu-id="7b745-191">L' `using` istruzione è inoltre speciale per Q# .</span><span class="sxs-lookup"><span data-stu-id="7b745-191">The `using` statement is also special to Q#.</span></span> <span data-ttu-id="7b745-192">Viene usata per allocare i qubit per l'uso in un blocco di codice.</span><span class="sxs-lookup"><span data-stu-id="7b745-192">It is used to allocate qubits for use in a block of code.</span></span> <span data-ttu-id="7b745-193">In Q# tutti i qubits vengono allocati e rilasciati in modo dinamico, anziché essere risorse fisse per l'intera durata di un algoritmo complesso.</span><span class="sxs-lookup"><span data-stu-id="7b745-193">In Q#, all qubits are dynamically allocated and released, rather than being fixed resources that are there for the entire lifetime of a complex algorithm.</span></span> <span data-ttu-id="7b745-194">Un'istruzione `using` alloca un set di qubit all'inizio e rilascia tali qubit alla fine del blocco.</span><span class="sxs-lookup"><span data-stu-id="7b745-194">A `using` statement allocates a set of qubits at the start, and releases those qubits at the end of the block.</span></span>

## <a name="run-the-code-from-the-command-prompt"></a><span data-ttu-id="7b745-195">Eseguire il codice dal prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="7b745-195">Run the code from the command prompt</span></span>

<span data-ttu-id="7b745-196">Per eseguire il codice è necessario specificare il compilatore *che* è possibile chiamare per l'esecuzione quando si fornisce il `dotnet run` comando.</span><span class="sxs-lookup"><span data-stu-id="7b745-196">In order to run the code we need to specify the compiler *which* callable to run when we provide the `dotnet run` command.</span></span> <span data-ttu-id="7b745-197">Questa operazione viene eseguita con una semplice modifica apportata al Q# file aggiungendo una riga con `@EntryPoint()` direttamente prima di callable: l' `TestBellState` operazione in questo caso.</span><span class="sxs-lookup"><span data-stu-id="7b745-197">This is done with a simple change in the Q# file by adding a line with `@EntryPoint()` directly preceding the callable: the `TestBellState` operation in this case.</span></span> <span data-ttu-id="7b745-198">Il codice completo deve essere:</span><span class="sxs-lookup"><span data-stu-id="7b745-198">The full code should be:</span></span>

```qsharp
namespace Bell {
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Intrinsic;

    operation SetQubitState(desired : Result, target : Qubit) : Unit {
        if (desired != M(target)) {
            X(target);
        }
    }

    @EntryPoint()
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                SetQubitState(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }

            SetQubitState(Zero, qubit);
        }

    // Return number of times we saw a |0> and number of times we saw a |1>
    Message("Test results (# of 0s, # of 1s): ");
    return (count - numOnes, numOnes);
    }
}
```

<span data-ttu-id="7b745-199">Per eseguire il programma, è necessario specificare `count` `initial` gli argomenti e dal prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="7b745-199">To run the program we need to specify `count` and `initial` arguments from the command prompt.</span></span> <span data-ttu-id="7b745-200">Si sceglierà ad esempio `count = 1000` e `initial = One` .</span><span class="sxs-lookup"><span data-stu-id="7b745-200">Let's choose for example `count = 1000` and `initial = One`.</span></span> <span data-ttu-id="7b745-201">Immettere il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="7b745-201">Enter the following command:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```

<span data-ttu-id="7b745-202">Ed è necessario osservare l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="7b745-202">And you should observe the following output:</span></span>

```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

<span data-ttu-id="7b745-203">Se si prova a usare `initial = Zero` , è necessario osservare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="7b745-203">If you try with `initial = Zero` you should observe:</span></span>

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

## <a name="prepare-superposition"></a><span data-ttu-id="7b745-204">Preparare la sovrapposizione</span><span class="sxs-lookup"><span data-stu-id="7b745-204">Prepare superposition</span></span>

<span data-ttu-id="7b745-205">Si esaminerà ora il modo in cui vengono illustrate le Q# modalità di inserimento di qubits in superposition.</span><span class="sxs-lookup"><span data-stu-id="7b745-205">Now let’s look at how Q# expresses ways to put qubits in superposition.</span></span>  <span data-ttu-id="7b745-206">Tenere presente che lo stato di un qubit può essere in una sovrapposizione di 0 e 1.</span><span class="sxs-lookup"><span data-stu-id="7b745-206">Recall that the state of a qubit can be in a superposition of 0 and 1.</span></span>  <span data-ttu-id="7b745-207">A tale scopo, verrà usata l'operazione `Hadamard`.</span><span class="sxs-lookup"><span data-stu-id="7b745-207">We’ll use the `Hadamard` operation to accomplish this.</span></span> <span data-ttu-id="7b745-208">Se il qubit è in uno degli stati classici (in cui una misura restituisce sempre `Zero` o sempre `One`), l'operazione `Hadamard` o `H` imposterà il qubit su uno stato in cui una misura del qubit restituirà `Zero` il 50% delle volte e `One` il 50% delle volte.</span><span class="sxs-lookup"><span data-stu-id="7b745-208">If the qubit is in either of the classical states (where a measurement returns `Zero` always or `One` always), then the `Hadamard` or `H` operation will put the qubit in a state where a measurement of the qubit will return `Zero` 50% of the time and return `One` 50% of the time.</span></span>  <span data-ttu-id="7b745-209">A livello concettuale, il qubit può essere considerato a metà tra `Zero` e `One`.</span><span class="sxs-lookup"><span data-stu-id="7b745-209">Conceputually, the qubit can be thought of as halfway between the `Zero` and `One`.</span></span>  <span data-ttu-id="7b745-210">Ora, quando si simula l'operazione `TestBellState`, si osserverà che i risultati restituiranno approssimativamente un numero uguale di `Zero` e `One` dopo la misura.</span><span class="sxs-lookup"><span data-stu-id="7b745-210">Now, when we simulate the `TestBellState` operation, we will see the results will return roughly an equal number of `Zero` and `One` after measurement.</span></span>  

### <a name="x-flips-qubit-state"></a><span data-ttu-id="7b745-211">`X` capovolge lo stato qubit</span><span class="sxs-lookup"><span data-stu-id="7b745-211">`X` flips qubit state</span></span>

<span data-ttu-id="7b745-212">In primo luogo, si tenterà semplicemente di invertire il qubit (se il qubit si trova nello stato `Zero` passerà a `One` e viceversa).</span><span class="sxs-lookup"><span data-stu-id="7b745-212">First we'll just try to flip the qubit (if the qubit is in `Zero` state will flip to `One` and vice versa).</span></span> <span data-ttu-id="7b745-213">A tale scopo, si esegue un'operazione `X` prima di misurarlo in `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="7b745-213">This is accomplished by performing an `X` operation before we measure it in `TestBellState`:</span></span>

```qsharp
X(qubit);
let res = M(qubit);
```

<span data-ttu-id="7b745-214">I risultati sono ora invertiti:</span><span class="sxs-lookup"><span data-stu-id="7b745-214">Now the results are reversed:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```

```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

<span data-ttu-id="7b745-215">Verranno ora esaminate le proprietà Quantum del qubits.</span><span class="sxs-lookup"><span data-stu-id="7b745-215">Now let's explore the quantum properties of the qubits.</span></span>

### <a name="h-prepares-superposition"></a><span data-ttu-id="7b745-216">`H` prepara la superposizione</span><span class="sxs-lookup"><span data-stu-id="7b745-216">`H` prepares superposition</span></span>

<span data-ttu-id="7b745-217">È sufficiente sostituire l'operazione `X` nell'esecuzione precedente con un'operazione `H` o un'operazione di Hadamard.</span><span class="sxs-lookup"><span data-stu-id="7b745-217">All we need to do is replace the `X` operation in the previous run with an `H` or Hadamard operation.</span></span> <span data-ttu-id="7b745-218">Anziché invertire il qubit da 0 a 1, verrà solo invertito a metà.</span><span class="sxs-lookup"><span data-stu-id="7b745-218">Instead of flipping the qubit all the way from 0 to 1, we will only flip it halfway.</span></span> <span data-ttu-id="7b745-219">Le righe sostituite in `TestBellState` ora hanno un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="7b745-219">The replaced lines in `TestBellState` now look like:</span></span>

```qsharp
H(qubit);
let res = M(qubit);
```

<span data-ttu-id="7b745-220">A questo punto, il risultato diventa più interessante:</span><span class="sxs-lookup"><span data-stu-id="7b745-220">Now the results get more interesting:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```

```output
Test results (# of 0s, # of 1s):
(496, 504)
```

```dotnetcli
dotnet run --count 1000 --initial Zero
```

```output
Test results (# of 0s, # of 1s):
(506, 494)
```

<span data-ttu-id="7b745-221">Ogni volta che si esegue una misura, viene richiesto un valore classico, ma il qubit si trova a metà tra 0 e 1, quindi si ottiene (statisticamente) 0 per metà delle volte e 1 per metà delle volte.</span><span class="sxs-lookup"><span data-stu-id="7b745-221">Every time we measure, we ask for a classical value, but the qubit is halfway between 0 and 1, so we get (statistically) 0 half the time and 1 half the time.</span></span>
<span data-ttu-id="7b745-222">Questa operazione è nota come **sovrapposizione** e offre la prima osservazione reale dello stato quantistico.</span><span class="sxs-lookup"><span data-stu-id="7b745-222">This is known as **superposition** and gives us our first real view into a quantum state.</span></span>

## <a name="prepare-entanglement"></a><span data-ttu-id="7b745-223">Preparare l'entanglement</span><span class="sxs-lookup"><span data-stu-id="7b745-223">Prepare entanglement</span></span>

<span data-ttu-id="7b745-224">Esaminiamo ora come esprimere i Q# modi per impigliare qubits.</span><span class="sxs-lookup"><span data-stu-id="7b745-224">Now let’s look at how Q# expresses ways to entangle qubits.</span></span>
<span data-ttu-id="7b745-225">In primo luogo, si imposta il primo qubit sullo stato iniziale e quindi si usa l'operazione `H` per posizionarlo in sovrapposizione.</span><span class="sxs-lookup"><span data-stu-id="7b745-225">First, we set the first qubit to the initial state and then use the `H` operation to put it into superposition.</span></span>  <span data-ttu-id="7b745-226">Quindi, prima di misurare il primo qubit, viene usata una nuova operazione ( `CNOT` ), che sta per essere controllata.</span><span class="sxs-lookup"><span data-stu-id="7b745-226">Then, before we measure the first qubit, we use a new operation (`CNOT`), which stands for Controlled-NOT.</span></span>  <span data-ttu-id="7b745-227">Il risultato dell'esecuzione di questa operazione su due qubit è l'inversione del secondo qubit se il primo qubit è `One`.</span><span class="sxs-lookup"><span data-stu-id="7b745-227">The result of executing this operation on two qubits is to flip the second qubit if the first qubit is `One`.</span></span>  <span data-ttu-id="7b745-228">A questo punto, i due qubit sono correlati (in entanglement).</span><span class="sxs-lookup"><span data-stu-id="7b745-228">Now, the two qubits are entangled.</span></span>  <span data-ttu-id="7b745-229">Le statistiche per il primo qubit sono rimaste invariate (probabilità 50-50 di `Zero` o `One`), ma ora quando viene misurato il secondo qubit, è __sempre__ uguale a quanto misurato per il primo qubit.</span><span class="sxs-lookup"><span data-stu-id="7b745-229">Our statistics for the first qubit haven't changed (50-50 chance of a `Zero` or a `One` after measurement), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit.</span></span> <span data-ttu-id="7b745-230">Il gate `CNOT` ha eseguito l'entanglement dei due qubit, così qualsiasi cosa accade a uno di essi, accade anche all'altro.</span><span class="sxs-lookup"><span data-stu-id="7b745-230">Our `CNOT` has entangled the two qubits, so that whatever happens to one of them, happens to the other.</span></span> <span data-ttu-id="7b745-231">Se sono state invertite le misure, ovvero se è stato misurato il secondo qubit prima del primo, si verificherà lo stesso risultato.</span><span class="sxs-lookup"><span data-stu-id="7b745-231">If you reversed the measurements (did the second qubit before the first), the same thing would happen.</span></span> <span data-ttu-id="7b745-232">La prima misura sarà casuale e la seconda si troverà nel passaggio del blocco con quanto individuato per la prima.</span><span class="sxs-lookup"><span data-stu-id="7b745-232">The first measurement would be random and the second would be in lock step with whatever was discovered for the first.</span></span>

<span data-ttu-id="7b745-233">Per prima cosa è necessario allocare due qubits anziché uno in `TestBellState` :</span><span class="sxs-lookup"><span data-stu-id="7b745-233">The first thing we'll need to do is allocate two qubits instead of one in `TestBellState`:</span></span>

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

<span data-ttu-id="7b745-234">Questo consentirà di aggiungere una nuova operazione (`CNOT`) prima di misurare (`M`) in `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="7b745-234">This will allow us to add a new operation (`CNOT`) before we measure  (`M`) in `TestBellState`:</span></span>

```qsharp
SetQubitState(initial, q0);
SetQubitState(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

<span data-ttu-id="7b745-235">È stata aggiunta un'altra operazione `SetQubitState` per inizializzare il primo qubit per assicurarsi che sia sempre nello stato `Zero` quando si inizia.</span><span class="sxs-lookup"><span data-stu-id="7b745-235">We've added another `SetQubitState` operation to initialize the first qubit to make sure that it's always in the `Zero` state when we start.</span></span>

<span data-ttu-id="7b745-236">È anche necessario reimpostare il secondo qubit prima di rilasciarlo.</span><span class="sxs-lookup"><span data-stu-id="7b745-236">We also need to reset the second qubit before releasing it.</span></span>

```qsharp
SetQubitState(Zero, q0);
SetQubitState(Zero, q1);
```

<span data-ttu-id="7b745-237">La routine completa ha ora un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="7b745-237">The full routine now looks like this:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                SetQubitState(initial, q0);
                SetQubitState(Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }

            SetQubitState(Zero, q0);
            SetQubitState(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
```

<span data-ttu-id="7b745-238">Se viene eseguita,si otterrà esattamente lo stesso risultato 50-50 ottenuto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="7b745-238">If we run this, we'll get exactly the same 50-50 result we got before.</span></span> <span data-ttu-id="7b745-239">Tuttavia, l'aspetto interessante è il modo in cui il secondo qubit reagisce alla prima misurazione.</span><span class="sxs-lookup"><span data-stu-id="7b745-239">However, what we're interested in is how the second qubit reacts to the first being measured.</span></span> <span data-ttu-id="7b745-240">Questa statistica verrà aggiunta con una nuova versione dell'operazione `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="7b745-240">We'll add this statistic with a new version of the `TestBellState` operation:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int, Int) {
        mutable numOnes = 0;
        mutable agree = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                SetQubitState(initial, q0);
                SetQubitState(Zero, q1);

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
            
            SetQubitState(Zero, q0);
            SetQubitState(Zero, q1);
        }

        // Return times we saw |0>, times we saw |1>, and times measurements agreed
        Message("Test results (# of 0s, # of 1s, # of agreements)");
        return (count-numOnes, numOnes, agree);
    }
```

<span data-ttu-id="7b745-241">Il nuovo valore restituito (`agree`) tiene traccia di ogni volta che la misurazione del primo qubit corrisponde alla misurazione del secondo qubit.</span><span class="sxs-lookup"><span data-stu-id="7b745-241">The new return value (`agree`) keeps track of every time the measurement from the first qubit matches the measurement of the second qubit.</span></span>

<span data-ttu-id="7b745-242">Esecuzione del codice ottenuto:</span><span class="sxs-lookup"><span data-stu-id="7b745-242">Running the code we obtain:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```
```output
(505, 495, 1000)
```
```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s, # of agreements)
(507, 493, 1000)
```

<span data-ttu-id="7b745-243">Come dichiarato nella panoramica, le statistiche per il primo qubit sono rimaste invariate (probabilità 50-50 di uno 0 o 1), ma ora quando viene misurato il secondo qubit, è __sempre__ uguale a quanto misurato per il primo qubit perché sono correlati (in entanglement).</span><span class="sxs-lookup"><span data-stu-id="7b745-243">As stated in the overview, our statistics for the first qubit haven't changed (50-50 chance of a 0 or a 1), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit, because they are entangled!</span></span>

## <a name="next-steps"></a><span data-ttu-id="7b745-244">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="7b745-244">Next steps</span></span>

<span data-ttu-id="7b745-245">L'esercitazione relativa alla [ricerca di Grover](xref:microsoft.quantum.quickstarts.search) Mostra come compilare ed eseguire la ricerca Grover, uno degli algoritmi di calcolo quantistica più diffusi e offre un esempio interessante di Q# programma che può essere usato per risolvere i problemi reali con l'elaborazione quantistica.</span><span class="sxs-lookup"><span data-stu-id="7b745-245">The tutorial [Grover’s search](xref:microsoft.quantum.quickstarts.search) shows you how to build and run Grover search, one of the most popular quantum computing algorithms and offers a nice example of a Q# program that can be used to solve real problems with quantum computing.</span></span>  

<span data-ttu-id="7b745-246">[Introduzione a Quantum Development Kit](xref:microsoft.quantum.welcome) suggerisce altri modi per apprendere Q# e programmare la programmazione quantistica.</span><span class="sxs-lookup"><span data-stu-id="7b745-246">[Get Started with the Quantum Development Kit](xref:microsoft.quantum.welcome) recommends more ways to learn Q# and quantum programming.</span></span>
