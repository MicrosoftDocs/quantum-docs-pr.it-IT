---
title: 'Scrivere e simulare programmi a livello di qubit in Q #'
description: Esercitazione dettagliata sulla scrittura e la simulazione di un programma Quantum che opera a livello di singolo qubit
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 10/06/2019
uid: microsoft.quantum.circuit-tutorial
ms.topic: tutorial
ms.openlocfilehash: e7ebdec4cd1aa201030d82759a3aa56473b26417
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274780"
---
# <a name="tutorial-write-and-simulate-qubit-level-programs-in-q"></a><span data-ttu-id="0d0a4-103">Esercitazione: scrivere e simulare programmi a livello di qubit in Q\#</span><span class="sxs-lookup"><span data-stu-id="0d0a4-103">Tutorial: Write and simulate qubit-level programs in Q\#</span></span>

<span data-ttu-id="0d0a4-104">Introduzione all'esercitazione su Quantum Development Kit per la scrittura e la simulazione di un programma Quantum di base che opera sui singoli qubits.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-104">Welcome to the Quantum Development Kit tutorial on writing and simulating a basic quantum program that operates on individual qubits.</span></span> 

<span data-ttu-id="0d0a4-105">Anche se Q # è stato creato principalmente come linguaggio di programmazione di alto livello per i programmi Quantum su larga scala, può essere usato altrettanto facilmente per esplorare il livello inferiore dei programmi quantistici: indirizzamento diretto a qubits specifici.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-105">Although Q# was primarily created as a high-level programming language for large-scale quantum programs, it can just as easily be used to explore the lower level of quantum programs: directly addressing specific qubits.</span></span>
<span data-ttu-id="0d0a4-106">La flessibilità di Q # consente agli utenti di approcciare i sistemi quantistici da un livello di astrazione di questo tipo e in questa esercitazione viene approfondita la qubits.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-106">The flexibility of Q# allows users to approach quantum systems from any such level of abstraction, and in this tutorial we dive into the qubits themselves.</span></span>
<span data-ttu-id="0d0a4-107">In particolare, diamo uno sguardo al cofano della [trasformazione Quantum Fourier](https://en.wikipedia.org/wiki/Quantum_Fourier_transform), una subroutine che è parte integrante di molti algoritmi quantistici più grandi.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-107">Specifically, we take a look under the hood of the [quantum Fourier transform](https://en.wikipedia.org/wiki/Quantum_Fourier_transform), a subroutine that is integral to many larger quantum algorithms.</span></span>

<span data-ttu-id="0d0a4-108">Si noti che questa visualizzazione di basso livello dell'elaborazione delle informazioni sui quantum è spesso descritta in termini di "[circuiti quantistici](xref:microsoft.quantum.concepts.circuits)", che rappresentano l'applicazione sequenziale delle attività di controllo per qubits specifici di un sistema.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-108">Note that this low-level view of quantum information processing is often described in terms of "[quantum circuits](xref:microsoft.quantum.concepts.circuits)," which represent the sequential application of gates to specific qubits of a system.</span></span>

<span data-ttu-id="0d0a4-109">Quindi, le operazioni a singolo e multiqubit che si applicano in modo sequenziale possono essere facilmente rappresentate in un "diagramma di circuito".</span><span class="sxs-lookup"><span data-stu-id="0d0a4-109">Thus, the single- and multi-qubit operations we sequentially apply can be readily represented in a "circuit diagram."</span></span>
<span data-ttu-id="0d0a4-110">In questo caso, si definirà un'operazione Q # per eseguire la trasformazione completa del quantum a tre qubit, che presenta la rappresentazione seguente come circuito:</span><span class="sxs-lookup"><span data-stu-id="0d0a4-110">In our case, we will define a Q# operation to perform the full three-qubit quantum Fourier transform, which has the following representation as a circuit:</span></span>

<br/>
<img src="../media/qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

## <a name="prerequisites"></a><span data-ttu-id="0d0a4-111">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="0d0a4-111">Prerequisites</span></span>

* <span data-ttu-id="0d0a4-112">[Installare](xref:microsoft.quantum.install) Quantum Development Kit usando il linguaggio e l'ambiente di sviluppo preferiti.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-112">[Install](xref:microsoft.quantum.install) the Quantum Development Kit using your preferred language and development environment.</span></span>
* <span data-ttu-id="0d0a4-113">Se il QDK è già installato, assicurarsi di aver eseguito l'[aggiornamento](xref:microsoft.quantum.update) alla versione più recente</span><span class="sxs-lookup"><span data-stu-id="0d0a4-113">If you already have the QDK installed, make sure you have [updated](xref:microsoft.quantum.update) to the latest version</span></span>


## <a name="in-this-tutorial-youll-learn-how-to"></a><span data-ttu-id="0d0a4-114">In questa esercitazione si apprenderà come:</span><span class="sxs-lookup"><span data-stu-id="0d0a4-114">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="0d0a4-115">Definire le operazioni Quantum in Q #</span><span class="sxs-lookup"><span data-stu-id="0d0a4-115">Define quantum operations in Q#</span></span>
> * <span data-ttu-id="0d0a4-116">Chiamare le operazioni Q # direttamente dalla riga di comando o usando un programma host classico</span><span class="sxs-lookup"><span data-stu-id="0d0a4-116">Call Q# operations directly from the command line or using a classical host program</span></span>
> * <span data-ttu-id="0d0a4-117">Simulare un'operazione Quantum dall'allocazione qubit all'output di misurazione</span><span class="sxs-lookup"><span data-stu-id="0d0a4-117">Simulate a quantum operation from qubit allocation to measurement output</span></span>
> * <span data-ttu-id="0d0a4-118">Osservare il modo in cui il zero simulato del sistema quantistica evolve durante l'operazione</span><span class="sxs-lookup"><span data-stu-id="0d0a4-118">Observe how the quantum system's simulated wavefunction evolves throughout the operation</span></span>

<span data-ttu-id="0d0a4-119">L'esecuzione di un programma Quantum con Microsoft Quantum Development Kit in genere è costituita da due parti:</span><span class="sxs-lookup"><span data-stu-id="0d0a4-119">Running a quantum program with Microsoft's Quantum Development Kit typically consists of two parts:</span></span>
1. <span data-ttu-id="0d0a4-120">Il programma stesso, che viene implementato usando il linguaggio di programmazione Quantum Q #, quindi viene richiamato per l'esecuzione in un computer Quantum o un simulatore Quantum.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-120">The program itself, which is implemented using the Q# quantum programming language, and then invoked to run on a quantum computer or quantum simulator.</span></span> <span data-ttu-id="0d0a4-121">Sono costituiti da</span><span class="sxs-lookup"><span data-stu-id="0d0a4-121">These consist of</span></span> 
    - <span data-ttu-id="0d0a4-122">Operazioni Q #: subroutine che agiscono sui registri Quantum e</span><span class="sxs-lookup"><span data-stu-id="0d0a4-122">Q# operations: subroutines acting on quantum registers, and</span></span> 
    - <span data-ttu-id="0d0a4-123">Funzioni Q #: subroutine classiche usate nell'algoritmo Quantum.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-123">Q# functions: classical subroutines used within the quantum algorithm.</span></span>
2. <span data-ttu-id="0d0a4-124">Il punto di ingresso usato per chiamare il programma Quantum e specificare il computer di destinazione in cui deve essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-124">The entry point used to call the quantum program and specify the target machine on which it should be run.</span></span>
    <span data-ttu-id="0d0a4-125">Questa operazione può essere eseguita direttamente dalla riga di comando o tramite un programma host scritto in un linguaggio di programmazione classico come Python o C#.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-125">This can be done directly from the command line, or through a host program written in a classical programming language like Python or C#.</span></span>
    <span data-ttu-id="0d0a4-126">Questa esercitazione include istruzioni per qualsiasi metodo preferito.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-126">This tutorial includes instructions for whichever method you prefer.</span></span>

## <a name="allocate-qubits-and-define-quantum-operations"></a><span data-ttu-id="0d0a4-127">Allocare qubits e definire operazioni Quantum</span><span class="sxs-lookup"><span data-stu-id="0d0a4-127">Allocate qubits and define quantum operations</span></span>

<span data-ttu-id="0d0a4-128">La prima parte di questa esercitazione consiste nel definire l'operazione Q # `Perform3qubitQFT` , che esegue la trasformazione Quantum Fourier su tre qubits.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-128">The first part of this tutorial consists of defining the Q# operation `Perform3qubitQFT`, which performs the quantum Fourier transform on three qubits.</span></span> 

<span data-ttu-id="0d0a4-129">Inoltre, si userà la [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) funzione per osservare il modo in cui il zero simulato del nostro sistema qubit evolve nell'intera operazione.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-129">In addition, we will use the [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) function to observe how the simulated wavefunction of our three qubit system evolves across the operation.</span></span>

<span data-ttu-id="0d0a4-130">Il primo passaggio consiste nel creare il progetto e il file Q #.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-130">The first step is creating your Q# project and file.</span></span>
<span data-ttu-id="0d0a4-131">I passaggi per questa operazione dipendono dall'ambiente che verrà usato per chiamare il programma ed è possibile trovare i dettagli nelle rispettive [guide di installazione](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="0d0a4-131">The steps for this depend on the environment you will use to call the program, and you can find the details in the respective [installation guides](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="0d0a4-132">Verranno illustrati in dettaglio i componenti del file, ma il codice è disponibile anche come blocco completo di seguito.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-132">We will walk you through the components of the file step-by-step, but the code is also available as a full block below.</span></span>

### <a name="namespaces-to-access-other-q-operations"></a><span data-ttu-id="0d0a4-133">Spazi dei nomi per accedere ad altre operazioni Q #</span><span class="sxs-lookup"><span data-stu-id="0d0a4-133">Namespaces to access other Q# operations</span></span>
<span data-ttu-id="0d0a4-134">All'interno del file viene innanzitutto definito lo spazio dei nomi al `NamespaceQFT` quale sarà possibile accedere dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-134">Inside the file, we first define the namespace `NamespaceQFT` which will be accessed by the compiler.</span></span>
<span data-ttu-id="0d0a4-135">Per poter usare le operazioni Q # esistenti, si aprono gli `Microsoft.Quantum.<>` spazi dei nomi pertinenti.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-135">For our operation to make use of existing Q# operations, we open the relevant `Microsoft.Quantum.<>` namespaces.</span></span>

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    // operations go here
}
```

### <a name="define-operations-with-arguments-and-returns"></a><span data-ttu-id="0d0a4-136">Definire operazioni con argomenti e restituzione</span><span class="sxs-lookup"><span data-stu-id="0d0a4-136">Define operations with arguments and returns</span></span>
<span data-ttu-id="0d0a4-137">Definire quindi l' `Perform3qubitQFT` operazione:</span><span class="sxs-lookup"><span data-stu-id="0d0a4-137">Next, we define the `Perform3qubitQFT` operation:</span></span>

```qsharp
    operation Perform3qubitQFT() : Unit {
        // do stuff
    }
```

<span data-ttu-id="0d0a4-138">Per il momento, l'operazione non accetta argomenti e non restituisce alcun elemento---in questo caso viene scritto che restituisce un `Unit` oggetto, che è simile a `void` in C# o a una tupla vuota, `Tuple[()]` , in Python.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-138">For now, the operation takes no arguments and does not return anything---in this case we write that it returns a `Unit` object, which is akin to `void` in C# or an empty tuple, `Tuple[()]`, in Python.</span></span>
<span data-ttu-id="0d0a4-139">In seguito verrà modificata per restituire una matrice di risultati di misurazione, a cui il punto `Unit` verrà sostituito da `Result[]` .</span><span class="sxs-lookup"><span data-stu-id="0d0a4-139">Later, we will modify it to return an array of measurement results, at which point `Unit` will be replaced by `Result[]`.</span></span> 

### <a name="allocate-qubits-with-using"></a><span data-ttu-id="0d0a4-140">Allocare qubits con`using`</span><span class="sxs-lookup"><span data-stu-id="0d0a4-140">Allocate qubits with `using`</span></span>
<span data-ttu-id="0d0a4-141">All'interno dell'operazione Q #, viene innanzitutto allocato un registro di tre qubits con l' `using` istruzione:</span><span class="sxs-lookup"><span data-stu-id="0d0a4-141">Within our Q# operation, we first allocate a register of three qubits with the `using` statement:</span></span>

```qsharp
        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

        }
```

<span data-ttu-id="0d0a4-142">Con `using` , i qubits vengono allocati automaticamente nello stato $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-142">With `using`, the qubits are automatically allocated in the $\ket{0}$ state.</span></span> <span data-ttu-id="0d0a4-143">Per verificarlo [`Message(<string>)`](xref:microsoft.quantum.intrinsic.message) , è possibile usare e [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) , che stampano una stringa e lo stato corrente del sistema nella console.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-143">We can verify this by using [`Message(<string>)`](xref:microsoft.quantum.intrinsic.message) and [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine), which print a string and the system's current state to the console.</span></span>

> [!NOTE]
> <span data-ttu-id="0d0a4-144">Le `Message(<string>)` `DumpMachine()` funzioni e ( [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) rispettivamente da e) vengono [`Microsoft.Quantum.Diagnostics`](xref:microsoft.quantum.diagnostics) stampate direttamente nella console.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-144">The `Message(<string>)` and `DumpMachine()` functions (from [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) and [`Microsoft.Quantum.Diagnostics`](xref:microsoft.quantum.diagnostics), respectively) both print directly to the console.</span></span> <span data-ttu-id="0d0a4-145">Analogamente a un calcolo quantistico reale, Q # non consente di accedere direttamente agli Stati qubit.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-145">Just like a real quantum computation, Q# does not allow us to directly access qubit states.</span></span>
> <span data-ttu-id="0d0a4-146">Tuttavia, come `DumpMachine` stampa lo stato corrente del computer di destinazione, può fornire informazioni utili per il debug e l'apprendimento quando viene usato insieme al simulatore di stato completo.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-146">However, as `DumpMachine` prints the target machine's current state, it can provide valuable insight for debugging and learning when used in conjunction with the full state simulator.</span></span>


### <a name="applying-single-qubit-and-controlled-gates"></a><span data-ttu-id="0d0a4-147">Applicazione di controlli Single-qubit e controlli</span><span class="sxs-lookup"><span data-stu-id="0d0a4-147">Applying single-qubit and controlled gates</span></span>

<span data-ttu-id="0d0a4-148">Si applicano quindi le attività di controllo che comprendono l'operazione stessa.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-148">Next, we apply the gates which comprise the operation itself.</span></span>
<span data-ttu-id="0d0a4-149">Q # contiene già molti controlli Quantum di base come operazioni nello [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) spazio dei nomi e non si tratta di un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-149">Q# already contains many basic quantum gates as operations in the [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) namespace, and these are no exception.</span></span> 

<span data-ttu-id="0d0a4-150">All'interno di un'operazione Q #, le istruzioni che richiamabili saranno ovviamente eseguite in ordine sequenziale.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-150">Within a Q# operation, the statements invoking callables will of course be executed in sequential order.</span></span>
<span data-ttu-id="0d0a4-151">Il primo Gate da applicare è quindi [`H`](xref:microsoft.quantum.intrinsic.h) (Hadamard) alla prima qubit:</span><span class="sxs-lookup"><span data-stu-id="0d0a4-151">Hence, the first gate to apply is the [`H`](xref:microsoft.quantum.intrinsic.h) (Hadamard) to the first qubit:</span></span>

<br/>
<img src="../media/qft_firstH.PNG" alt="Circuit diagram for three qubit QFT through first Hadamard" width="120">

<span data-ttu-id="0d0a4-152">Per applicare un'operazione a un qubit specifico da un registro (ovvero un singolo `Qubit` da una matrice `Qubit[]` ) si usa la notazione di indice standard.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-152">To apply an operation to a specific qubit from a register (i.e. a single `Qubit` from an array `Qubit[]`) we use standard index notation.</span></span>
<span data-ttu-id="0d0a4-153">Quindi, l'applicazione [`H`](xref:microsoft.quantum.intrinsic.h) di al primo qubit del registro `qs` assume il formato seguente:</span><span class="sxs-lookup"><span data-stu-id="0d0a4-153">So, applying the [`H`](xref:microsoft.quantum.intrinsic.h) to the first qubit of our register `qs` takes the form:</span></span>

```qsharp
            H(qs[0]);
```

<span data-ttu-id="0d0a4-154">Oltre ad applicare il `H` Gate (Hadamard) a singoli qubits, il circuito QFT è costituito principalmente da [`R1`](xref:microsoft.quantum.intrinsic.r1) rotazioni controllate.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-154">Besides applying the `H` (Hadamard) gate to individual qubits, the QFT circuit consists primarily of controlled [`R1`](xref:microsoft.quantum.intrinsic.r1) rotations.</span></span>
<span data-ttu-id="0d0a4-155">Un' `R1(θ, <qubit>)` operazione in generale lascia {0} invariato il componente $ \ket $ di qubit, applicando una rotazione di $e ^ {i\theta} $ al componente $ \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-155">An `R1(θ, <qubit>)` operation in general leaves the $\ket{0}$ component of the qubit unchanged, while applying a rotation of $e^{i\theta}$ to the $\ket{1}$ component.</span></span>

#### <a name="controlled-operations"></a><span data-ttu-id="0d0a4-156">Operazioni controllate</span><span class="sxs-lookup"><span data-stu-id="0d0a4-156">Controlled operations</span></span>

<span data-ttu-id="0d0a4-157">D # rende estremamente semplice condizionare l'esecuzione di un'operazione su uno o più controlli qubits.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-157">Q# makes it extremely easy to condition the execution of an operation upon one or multiple control qubits.</span></span>
<span data-ttu-id="0d0a4-158">In generale, si limita a anteporre la chiamata a `Controlled` e gli argomenti dell'operazione cambiano come segue:</span><span class="sxs-lookup"><span data-stu-id="0d0a4-158">In general, we merely preface the call with `Controlled`, and the operation arguments change as:</span></span>

 <span data-ttu-id="0d0a4-159">`Op(<normal args>)`$ per $ `Controlled Op([<control qubits>], (<normal args>))` .</span><span class="sxs-lookup"><span data-stu-id="0d0a4-159">`Op(<normal args>)` $\to$ `Controlled Op([<control qubits>], (<normal args>))`.</span></span>

<span data-ttu-id="0d0a4-160">Si noti che il controllo qubits deve essere fornito come matrice, anche se si tratta di un singolo qubit.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-160">Note that the control qubits must be provided as an array, even if it is a single qubit.</span></span>

<span data-ttu-id="0d0a4-161">Dopo la `H` , si noterà che i cancelli successivi sono le attività di `R1` controllo che agiscono sulla prima qubit (e controllate dal secondo/terzo):</span><span class="sxs-lookup"><span data-stu-id="0d0a4-161">After the `H`, we see that the next gates are the `R1` gates acting on the first qubit (and controlled by the second/third):</span></span>

<br/>
<img src="../media/qft_firstqubit.PNG" alt="Circuit diagram for three qubit QFT through first qubit" width="310">

<span data-ttu-id="0d0a4-162">Questi vengono chiamati con</span><span class="sxs-lookup"><span data-stu-id="0d0a4-162">We call these with</span></span>

```qsharp
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));
```

<span data-ttu-id="0d0a4-163">Si noti che viene usata la [`PI()`](xref:microsoft.quantum.math.pi) funzione dello [`Microsoft.Quantum.Math`](xref:microsoft.quantum.math) spazio dei nomi per definire le rotazioni in termini di pi greco radianti.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-163">Note that we use the [`PI()`](xref:microsoft.quantum.math.pi) function from the [`Microsoft.Quantum.Math`](xref:microsoft.quantum.math) namespace to define the rotations in terms of pi radians.</span></span>
<span data-ttu-id="0d0a4-164">Si divide inoltre per un `Double` (ad esempio `2.0` ) perché la divisione per un numero intero `2` genera un errore di tipo.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-164">Additionally, we divide by a `Double` (e.g. `2.0`) because dividing by an integer `2` would throw a type error.</span></span> 

> [!TIP]
> <span data-ttu-id="0d0a4-165">`R1(π/2)`e `R1(π/4)` sono equivalenti alle `S` `T` operazioni e (anche in `Microsoft.Quantum.Intrinsic` ).</span><span class="sxs-lookup"><span data-stu-id="0d0a4-165">`R1(π/2)` and `R1(π/4)` are equivalent to the `S` and `T` operations (also in `Microsoft.Quantum.Intrinsic`).</span></span>


<span data-ttu-id="0d0a4-166">Dopo aver applicato le `H` operazioni pertinenti e le rotazioni controllate al secondo e al terzo qubits:</span><span class="sxs-lookup"><span data-stu-id="0d0a4-166">After applying the relevant `H` operations and controlled rotations to the second and third qubits:</span></span>

```qsharp
            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);
```

<span data-ttu-id="0d0a4-167">è necessario applicare un controllo solo [`SWAP`](xref:microsoft.quantum.intrinsic.swap) per completare il circuito:</span><span class="sxs-lookup"><span data-stu-id="0d0a4-167">we need only apply a [`SWAP`](xref:microsoft.quantum.intrinsic.swap) gate to complete the circuit:</span></span>

```qsharp
            SWAP(qs[2], qs[0]);
```

<span data-ttu-id="0d0a4-168">Questa operazione è necessaria perché la natura della trasformazione Quantum Fourier restituisce l'qubits in ordine inverso, quindi gli scambi consentono una perfetta integrazione della subroutine in algoritmi di dimensioni maggiori.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-168">This is necessary because the nature of the quantum Fourier transform outputs the qubits in reverse order, so the swaps allow for seamless integration of the subroutine into larger algorithms.</span></span>

<span data-ttu-id="0d0a4-169">Di conseguenza, abbiamo terminato di scrivere le operazioni a livello di qubit della trasformazione Quantum Fourier nell'operazione Q #:</span><span class="sxs-lookup"><span data-stu-id="0d0a4-169">Hence we have finished writing the qubit-level operations of the quantum Fourier transform into our Q# operation:</span></span>

<img src="../media/qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

<span data-ttu-id="0d0a4-170">Tuttavia, non è possibile chiamarlo ancora un giorno.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-170">However, we can't call it a day just yet.</span></span>
<span data-ttu-id="0d0a4-171">I nostri qubits erano in stato $ \ket {0} $ al momento della loro assegnazione e, in modo analogo, in Q # avremmo dovuto lasciare gli stessi risultati (o meglio!).</span><span class="sxs-lookup"><span data-stu-id="0d0a4-171">Our qubits were in state $\ket{0}$ when we allocated them, and much like in life, in Q# we should leave things the same way we found them (or better!).</span></span>

### <a name="deallocate-qubits"></a><span data-ttu-id="0d0a4-172">Deallocare qubits</span><span class="sxs-lookup"><span data-stu-id="0d0a4-172">Deallocate qubits</span></span>

<span data-ttu-id="0d0a4-173">Viene chiamato [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) di nuovo per visualizzare lo stato di post-operazione e infine si applica [`ResetAll`](xref:microsoft.quantum.intrinsic.resetall) al registro qubit per reimpostare il qubits su $ \ket {0} $ prima di completare l'operazione:</span><span class="sxs-lookup"><span data-stu-id="0d0a4-173">We call [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) again to see the post-operation state, and finally apply [`ResetAll`](xref:microsoft.quantum.intrinsic.resetall) to the qubit register to reset our qubits to $\ket{0}$ before completing the operation:</span></span>

```qsharp
            Message("After:");
            DumpMachine();

            ResetAll(qs);
```

<span data-ttu-id="0d0a4-174">Per richiedere che tutti i qubits deallocati siano impostati in modo esplicito su $ \ket {0} $, è una funzionalità di base di Q #, perché consente ad altre operazioni di conoscerne lo stato esattamente quando iniziano a usare gli stessi qubits (una risorsa limitata).</span><span class="sxs-lookup"><span data-stu-id="0d0a4-174">Requiring that all deallocated qubits be explicitly set to $\ket{0}$ is a basic feature of Q#, as it allows other operations to know their state precisely when they begin using those same qubits (a scarce resource).</span></span>
<span data-ttu-id="0d0a4-175">Inoltre, ciò garantisce che non siano presenti altri qubits nel sistema.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-175">Additionally, this assures that they not be entangled with any other qubits in the system.</span></span>
<span data-ttu-id="0d0a4-176">Se la reimpostazione non viene eseguita alla fine di un `using` blocco di allocazione, verrà generato un errore di Runtime.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-176">If the reset is not performed at the end of a `using` allocation block, a runtime error will be thrown.</span></span>

<span data-ttu-id="0d0a4-177">Il file Q # completo dovrebbe ora essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="0d0a4-177">Your full Q# file should now look like this:</span></span>

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    operation Perform3qubitQFT() : Unit {

        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("After:");
            DumpMachine();

            ResetAll(qs);
        }
    }
}
```


<span data-ttu-id="0d0a4-178">Con il file Q # e l'operazione completata, il programma Quantum è pronto per essere chiamato e simulato.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-178">With the Q# file and operation complete, our quantum program is ready to be called and simulated.</span></span>

## <a name="execute-the-program"></a><span data-ttu-id="0d0a4-179">Esegui il programma</span><span class="sxs-lookup"><span data-stu-id="0d0a4-179">Execute the program</span></span>

<span data-ttu-id="0d0a4-180">Dopo aver definito l'operazione Q # in un `.qs` file, è ora necessario chiamare tale operazione e osservare i dati classici restituiti.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-180">Having defined our Q# operation in a `.qs` file, we now need to call that operation and observe any returned classical data.</span></span>
<span data-ttu-id="0d0a4-181">Per il momento, non viene restituito alcun elemento (tenere presente che l'operazione definita in precedenza restituisce `Unit` ), ma quando in seguito si modifica l'operazione Q # per restituire una matrice di risultati di misurazione (), si affronterà `Result[]` questo problema.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-181">For now, there isn't anything returned (recall that our operation defined above returns `Unit`), but when we later modify the Q# operation to return an array of measurement results (`Result[]`), we will address this.</span></span>

<span data-ttu-id="0d0a4-182">Anche se il programma Q # è onnipresente negli ambienti usati per chiamarlo, il modo in cui questa operazione sarà ovviamente variabile.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-182">While the Q# program is ubiquitous across the environments used to call it, the manner of doing so will of course vary.</span></span> <span data-ttu-id="0d0a4-183">Di conseguenza, è sufficiente seguire le istruzioni nella scheda corrispondente al programma di installazione: uso dell'applicazione della riga di comando Q # o uso di un programma host in Python o C#.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-183">As such, simply follow the instructions in the tab corresponding to your setup: working from the Q# command line application or using a host program in Python or C#.</span></span>

#### <a name="command-line"></a>[<span data-ttu-id="0d0a4-184">Riga di comando</span><span class="sxs-lookup"><span data-stu-id="0d0a4-184">Command line</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="0d0a4-185">L'esecuzione del programma Q # dalla riga di comando richiede solo una piccola modifica al file Q #.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-185">Running the Q# program from the command line requires only a small change to the Q# file.</span></span>

<span data-ttu-id="0d0a4-186">È sufficiente aggiungere `@EntryPoint()` a una riga che precede la definizione dell'operazione:</span><span class="sxs-lookup"><span data-stu-id="0d0a4-186">Simply add `@EntryPoint()` to a line preceding the operation definition:</span></span>

```qsharp
    @EntryPoint()
    operation Perform3qubitQFT() : Unit {
        // ...
```

<span data-ttu-id="0d0a4-187">Per eseguire il programma, aprire il terminale nella cartella del progetto e immettere</span><span class="sxs-lookup"><span data-stu-id="0d0a4-187">To run the program, open the terminal in the folder of your project and enter</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="0d0a4-188">Al momento dell'esecuzione, gli `Message` output e `DumpMachine` indicati di seguito vengono visualizzati nella console.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-188">Upon execution, you should see the `Message` and `DumpMachine` outputs below printed in your console.</span></span>


#### <a name="python"></a>[<span data-ttu-id="0d0a4-189">Python</span><span class="sxs-lookup"><span data-stu-id="0d0a4-189">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="0d0a4-190">Creare un file host Python: `host.py` .</span><span class="sxs-lookup"><span data-stu-id="0d0a4-190">Create a Python host file: `host.py`.</span></span>

<span data-ttu-id="0d0a4-191">Il file host viene creato nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="0d0a4-191">The host file is constructed as follows:</span></span> 
1. <span data-ttu-id="0d0a4-192">In primo luogo, viene importato il `qsharp` modulo, che registra il caricatore del modulo per l'interoperabilità Q #.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-192">First, we import the `qsharp` module, which registers the module loader for Q# interoperability.</span></span> 
    <span data-ttu-id="0d0a4-193">In questo modo gli spazi dei nomi Q # (ad esempio, `NamespaceQFT` definiti nel file q #) verranno visualizzati come moduli Python, da cui è possibile importare le operazioni q #.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-193">This allows Q# namespaces (e.g. the `NamespaceQFT` we defined in our Q# file) to appear as Python modules, from which we can import Q# operations.</span></span>
2. <span data-ttu-id="0d0a4-194">Importare quindi le operazioni Q # che verrà richiamata direttamente---in questo caso `Perform3qubitQFT` .</span><span class="sxs-lookup"><span data-stu-id="0d0a4-194">Then, import the Q# operations which we will directly invoke---in this case, `Perform3qubitQFT`.</span></span>
    <span data-ttu-id="0d0a4-195">È necessario importare solo il punto di ingresso in un programma Q #, ovvero _non_ operazioni come `H` e `R1` , che vengono chiamate da altre operazioni Q # ma mai dall'host classico.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-195">We need only import the entry point into a Q# program (i.e. _not_ operations like `H` and `R1`, which are called by other Q# operations but never by the classical host).</span></span>
3. <span data-ttu-id="0d0a4-196">Per simulare le operazioni o le funzioni Q #, usare il modulo `<Q#callable>.simulate(<args>)` per eseguirle nel `QuantumSimulator()` computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-196">In simulating Q# operations or functions, use the form `<Q#callable>.simulate(<args>)` to run them on the `QuantumSimulator()` target machine.</span></span> 

> [!NOTE]
> <span data-ttu-id="0d0a4-197">Se volevamo chiamare l'operazione su un computer diverso, ad esempio, useremo `ResourceEstimator()` semplicemente `<Q#callable>.estimate_resources(<args>)` .</span><span class="sxs-lookup"><span data-stu-id="0d0a4-197">If we wanted to call the operation on a different machine, for example the `ResourceEstimator()`, we would simply use `<Q#callable>.estimate_resources(<args>)`.</span></span>
> <span data-ttu-id="0d0a4-198">In generale, le operazioni Q # sono indipendenti dai computer in cui vengono eseguite, ma alcune funzionalità come `DumpMachine` potrebbero comportarsi in modo diverso.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-198">In general, Q# operations are agnostic to the machines on which they're run, but some features such as `DumpMachine` may behave differently.</span></span>

4. <span data-ttu-id="0d0a4-199">Quando si esegue la simulazione, la chiamata all'operazione restituirà i valori definiti nel file Q #.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-199">Upon performing the simulation, the operation call will return values as defined in the Q# file.</span></span>
    <span data-ttu-id="0d0a4-200">Per il momento non viene restituito alcun risultato, ma in un secondo momento verrà visualizzato un esempio di assegnazione ed elaborazione di questi valori.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-200">For now there is nothing returned, but later on we will see an example of assigning and processing these values.</span></span>
    <span data-ttu-id="0d0a4-201">Con i dati risultanti in mano e completamente classici, possiamo eseguire qualsiasi operazione.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-201">With the resultant data in our hands and totally classical, we can do whatever we'd like with it.</span></span>

<span data-ttu-id="0d0a4-202">Il `host.py` file completo dovrebbe essere il seguente:</span><span class="sxs-lookup"><span data-stu-id="0d0a4-202">Your full `host.py` file should be this:</span></span>

```python
import qsharp
from NamespaceQFT import Perform3qubitQFT

Perform3qubitQFT.simulate()
```

<span data-ttu-id="0d0a4-203">Eseguire il file Python e stamparlo nella console dovrebbero essere visualizzati gli `Message` output e `DumpMachine` seguenti.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-203">Run the Python file, and printed in your console you should see the `Message` and `DumpMachine` outputs below.</span></span> 


#### <a name="c"></a>[<span data-ttu-id="0d0a4-204">C#</span><span class="sxs-lookup"><span data-stu-id="0d0a4-204">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="0d0a4-205">Seguendo le stesse istruzioni disponibili nella [Guida all'installazione](xref:microsoft.quantum.install.cs), creare un file host C# e rinominarlo in `host.cs` .</span><span class="sxs-lookup"><span data-stu-id="0d0a4-205">Following the same instructions as in the [install guide](xref:microsoft.quantum.install.cs), create a C# host file, and rename it to `host.cs`.</span></span>

<span data-ttu-id="0d0a4-206">L'host C# è costituito da quattro parti:</span><span class="sxs-lookup"><span data-stu-id="0d0a4-206">The C# host has four parts:</span></span>
1. <span data-ttu-id="0d0a4-207">Costruzione di un simulatore quantistico.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-207">Construct a quantum simulator.</span></span>
    <span data-ttu-id="0d0a4-208">Nel codice riportato di seguito si tratta della variabile `qsim` .</span><span class="sxs-lookup"><span data-stu-id="0d0a4-208">In the code below, this is the variable `qsim`.</span></span>
2. <span data-ttu-id="0d0a4-209">Calcolo degli argomenti necessari per l'algoritmo quantistico.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-209">Compute any arguments required for the quantum algorithm.</span></span>
    <span data-ttu-id="0d0a4-210">Nessuno in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-210">There are none in this example.</span></span>
3. <span data-ttu-id="0d0a4-211">Esecuzione dell'algoritmo quantistico.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-211">Run the quantum algorithm.</span></span> 
    <span data-ttu-id="0d0a4-212">Ogni operazione Q# genera una classe C# con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-212">Each Q# operation generates a C# class with the same name.</span></span> 
    <span data-ttu-id="0d0a4-213">Questa classe contiene un metodo `Run` che esegue l'operazione in modalità **asincrona**.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-213">This class has a `Run` method that **asynchronously** executes the operation.</span></span>
    <span data-ttu-id="0d0a4-214">L'esecuzione è asincrona perché l'esecuzione nell'hardware effettivo sarà asincrona.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-214">The execution is asynchronous because execution on actual hardware will be asynchronous.</span></span> 
    <span data-ttu-id="0d0a4-215">Poiché il `Run` metodo è asincrono, viene chiamato il `Wait()` metodo. l'esecuzione viene bloccata fino al completamento dell'attività e il risultato viene restituito in modo sincrono.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-215">Because the `Run` method is asynchronous, we call the `Wait()` method; this blocks execution until the task completes and returns the result synchronously.</span></span> 
4. <span data-ttu-id="0d0a4-216">Elabora il risultato restituito dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-216">Process the returned result of the operation.</span></span>
    <span data-ttu-id="0d0a4-217">Per il momento, l'operazione non restituisce alcun risultato.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-217">For now, the operation returns nothing.</span></span>


```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                Perform3QubitQFT.Run(qsim).Wait();
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}

```
<span data-ttu-id="0d0a4-218">Eseguire l'applicazione e l'output deve corrispondere a quello riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-218">Run the application, and your output should match that below.</span></span>
<span data-ttu-id="0d0a4-219">Il programma verrà chiuso dopo aver premuto un tasto.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-219">The program will exit after you press a key.</span></span>
***

```Output
Initial state |000>:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
After:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
```

<span data-ttu-id="0d0a4-220">Quando viene chiamato sul simulatore di stato completo, `DumpMachine()` fornisce queste rappresentazioni mutliple del zero dello stato del quantum.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-220">When called on the full-state simulator, `DumpMachine()` provides these mutliple representations of the quantum state's wavefunction.</span></span> <span data-ttu-id="0d0a4-221">Gli stati possibili di un sistema $n $-qubit possono essere rappresentati da uno o più Stati di base del calcolo di $2 ^ n $, ognuno con un coefficiente complesso corrispondente (semplicemente un'ampiezza e una fase).</span><span class="sxs-lookup"><span data-stu-id="0d0a4-221">The possible states of an $n$-qubit system can be represented by $2^n$ computational basis states, each with a corresponding complex coefficient (simply an amplitude and a phase).</span></span>
<span data-ttu-id="0d0a4-222">Gli Stati di base di calcolo corrispondono a tutte le stringhe binarie possibili di lunghezza $n $---ovvero tutte le combinazioni possibili di qubit stati $ \ket {0} $ e $ \ket {1} $, dove ogni cifra binaria corrisponde a un singolo qubit.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-222">The computational basis states correspond to all the possible binary strings of length $n$---that is, all the possible combinations of qubit states $\ket{0}$ and $\ket{1}$, where each binary digit corresponds to an individual qubit.</span></span>

<span data-ttu-id="0d0a4-223">La prima riga fornisce un commento con gli ID dei qubits corrispondenti nell'ordine significativo.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-223">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="0d0a4-224">Qubit `2` è il "più significativo" significa semplicemente che nella rappresentazione binaria del vettore di stato base $ \ket{i} $ lo stato di qubit `2` corrisponde alla cifra più a sinistra.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-224">Qubit `2` being the "most significant" simply means that in the binary representation of basis state vector $\ket{i}$, the state of qubit `2` corresponds to the left-most digit.</span></span> <span data-ttu-id="0d0a4-225">Ad esempio, $ \ket {6} = \ket {110} $ include qubits `2` e `1` both in $ \ket {1} $ e qubit `0` in $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-225">For example, $\ket{6} = \ket{110}$ comprises qubits `2` and `1` both in $\ket{1}$ and qubit `0` in $\ket{0}$.</span></span>


<span data-ttu-id="0d0a4-226">Il resto delle righe descrive l'ampiezza di probabilità della misurazione del vettore di stato di base $ \ket{i} $ nei formati cartesiani e polari.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-226">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{i}$ in both Cartesian and polar formats.</span></span>
<span data-ttu-id="0d0a4-227">In dettaglio per la prima riga dello stato di input $ \ket {000} $:</span><span class="sxs-lookup"><span data-stu-id="0d0a4-227">In detail for the first row of our input state $\ket{000}$:</span></span>
* <span data-ttu-id="0d0a4-228">**`|0>:`** Questa riga corrisponde allo `0` stato di base computazionale (dato che la post-allocazione dello stato iniziale era $ \ket {000} $, ci si aspetterebbe che questo sia l'unico stato con l'ampiezza della probabilità a questo punto).</span><span class="sxs-lookup"><span data-stu-id="0d0a4-228">**`|0>:`** this row corresponds to the `0` computational basis state (given that our initial state post-allocation was $\ket{000}$, we would expect this to be the only state with probability amplitude at this point).</span></span>
* <span data-ttu-id="0d0a4-229">**`1.000000 +  0.000000 i`**: ampiezza della probabilità in formato cartesiano.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-229">**`1.000000 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="0d0a4-230">**` == `**: il `equal` segno separa entrambe le rappresentazioni equivalenti.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-230">**` == `**: the `equal` sign separates both equivalent representations.</span></span>
* <span data-ttu-id="0d0a4-231">**`********************`**: Rappresentazione grafica della grandezza, il numero di `*` è proporzionale alla probabilità di misurare questo vettore di stato.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-231">**`********************`**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span> 
* <span data-ttu-id="0d0a4-232">**`[ 1.000000 ]`**: valore numerico della grandezza</span><span class="sxs-lookup"><span data-stu-id="0d0a4-232">**`[ 1.000000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="0d0a4-233">**`    ---`**: Rappresentazione grafica della fase dell'ampiezza.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-233">**`    ---`**: A graphical representation of the amplitude's phase.</span></span>
* <span data-ttu-id="0d0a4-234">**`[ 0.0000 rad ]`**: valore numerico della fase (in radianti).</span><span class="sxs-lookup"><span data-stu-id="0d0a4-234">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="0d0a4-235">Sia la grandezza che la fase vengono visualizzate con una rappresentazione grafica.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-235">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="0d0a4-236">La rappresentazione di magnitude è semplice: Mostra una barra di `*` e maggiore è la probabilità, maggiore sarà la barra.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-236">The magnitude representation is straightforward: it shows a bar of `*`, and the higher the probability, the larger the bar will be.</span></span> <span data-ttu-id="0d0a4-237">Per la fase, vedere [testing and Debugging: dump functions](xref:microsoft.quantum.guide.testingdebugging#dump-functions) per le possibili rappresentazioni dei simboli basate sugli intervalli di angoli.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-237">For the phase, see [Testing and debugging: dump functions](xref:microsoft.quantum.guide.testingdebugging#dump-functions) for the possible symbol representations based on angle ranges.</span></span>


<span data-ttu-id="0d0a4-238">Quindi, l'output stampato indica che i nostri cancelli programmati hanno trasformato lo stato da</span><span class="sxs-lookup"><span data-stu-id="0d0a4-238">So, the printed output is illustrating that our programmed gates transformed our state from</span></span>

<span data-ttu-id="0d0a4-239">$ $ \ket{\psi} \_ {Initial} = \ket {000} $ $</span><span class="sxs-lookup"><span data-stu-id="0d0a4-239">$$ \ket{\psi}\_{initial} = \ket{000} $$</span></span>

<span data-ttu-id="0d0a4-240">to</span><span class="sxs-lookup"><span data-stu-id="0d0a4-240">to</span></span> 

<span data-ttu-id="0d0a4-241">$ $ \begin{align} \ket{\psi} \_ {Final} &= \frac {1} {\sqrt {8} } \left (\ket + {000} \ket {001} + \ket {010} + \ket {011} + \ket {100} + \ket {101} + \ket {110} + \ket {111} \right) \\ \\ &= \frac {1} {\sqrt{2 ^ n}} \sum \_ {j = 0} ^ {2 ^ n-1} \ket{j}, \end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="0d0a4-241">$$ \begin{align} \ket{\psi}\_{final} &= \frac{1}{\sqrt{8}} \left( \ket{000} + \ket{001} + \ket{010} + \ket{011} + \ket{100} + \ket{101} + \ket{110} + \ket{111}  \right) \\\\ &= \frac{1}{\sqrt{2^n}}\sum\_{j=0}^{2^n-1} \ket{j}, \end{align} $$</span></span>

<span data-ttu-id="0d0a4-242">Questo è esattamente il comportamento della trasformazione di Fourier qubit 3.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-242">which is precisely the behavior of the 3-qubit Fourier transform.</span></span> 

<span data-ttu-id="0d0a4-243">Per informazioni sul modo in cui sono interessati gli altri Stati di input, si consiglia di provare a eseguire le operazioni di qubit prima della trasformazione.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-243">If you are curious about how other input states are affected, we encourage you to play around with applying qubit operations before the transform.</span></span>

## <a name="adding-measurements"></a><span data-ttu-id="0d0a4-244">Aggiunta di misure</span><span class="sxs-lookup"><span data-stu-id="0d0a4-244">Adding measurements</span></span>

<span data-ttu-id="0d0a4-245">Sfortunatamente, una pietra miliare della meccanica quantistica indica che un sistema Quantum reale non può disporre di tale `DumpMachine` funzione.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-245">Unfortunately, a cornerstone of quantum mechanics tells us that a real quantum system cannot have such a `DumpMachine` function.</span></span> <span data-ttu-id="0d0a4-246">Al contrario, è necessario estrarre le informazioni attraverso le misurazioni, che in genere non solo forniscono lo stato quantum completo, ma possono anche modificare drasticamente il sistema stesso.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-246">Instead, we're forced to extract information through measurements, which in general not only fail to provide us the full quantum state, but can also drastically alter the system itself.</span></span>
<span data-ttu-id="0d0a4-247">Ci sono molti tipi di misurazioni Quantum, ma ci si concentrerà sulla più elementare: misurazioni proiezioni su un singolo qubits.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-247">There are many sorts of quantum measurements, but we will focus on the most basic: projective measurements on single qubits.</span></span>
<span data-ttu-id="0d0a4-248">Una volta eseguita la misurazione in base a una determinata base (ad esempio, la base di calcolo $ \{ \ket {0} , \ket {1} \} $), lo stato qubit viene proiettato sullo stato di base misurato---quindi eliminando eventuali superposizioni tra i due.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-248">Upon measurement in a given basis (e.g. the computational basis $ \{ \ket{0}, \ket{1} \} $), the qubit state is projected onto whichever basis state was measured---hence destroying any superposition between the two.</span></span>

<span data-ttu-id="0d0a4-249">Per implementare le misurazioni in un programma Q #, viene usata l' `M` operazione (from `Microsoft.Quantum.Intrinsic` ), che restituisce un `Result` tipo.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-249">To implement measurements within a Q# program, we use the `M` operation (from `Microsoft.Quantum.Intrinsic`), which returns a `Result` type.</span></span>

<span data-ttu-id="0d0a4-250">In primo luogo, l' `Perform3QubitQFT` operazione viene modificata per restituire una matrice di risultati di misurazione, `Result[]` , anziché `Unit` .</span><span class="sxs-lookup"><span data-stu-id="0d0a4-250">First, we modify our `Perform3QubitQFT` operation to return an array of measurement results, `Result[]`, instead of `Unit`.</span></span>

```qsharp
    operation Perform3QubitQFT() : Result[] {
```

#### <a name="define-and-initialize-result-array"></a><span data-ttu-id="0d0a4-251">Definire e inizializzare la `Result[]` matrice</span><span class="sxs-lookup"><span data-stu-id="0d0a4-251">Define and initialize `Result[]` array</span></span>

<span data-ttu-id="0d0a4-252">Prima di allocare anche qubits, ad esempio prima dell' `using` istruzione, viene dichiarata e associata la matrice di lunghezza 3 (una `Result` per ogni qubit):</span><span class="sxs-lookup"><span data-stu-id="0d0a4-252">Before even allocating qubits (i.e. before the `using` statement), we declare and bind this length-3 array (one `Result` for each qubit):</span></span> 

```qsharp
        mutable resultArray = new Result[3];
```

<span data-ttu-id="0d0a4-253">La `mutable` parola chiave prefacing `resultArray` consente la riassociazione della variabile in un secondo momento nel codice---ad esempio quando si aggiungono i risultati della misurazione.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-253">The `mutable` keyword prefacing `resultArray` allows the variable to be rebound later in the code---for example, when adding our measurement results.</span></span>

#### <a name="perform-measurements-in-a-for-loop-and-add-results-to-array"></a><span data-ttu-id="0d0a4-254">Eseguire misure in un `for` ciclo e aggiungere risultati alla matrice</span><span class="sxs-lookup"><span data-stu-id="0d0a4-254">Perform measurements in a `for` loop and add results to array</span></span>

<span data-ttu-id="0d0a4-255">Dopo le operazioni di trasformazione di Fourier all'interno del `using` blocco, inserire il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="0d0a4-255">After the Fourier transform operations inside the `using` block, insert the following code:</span></span>

```qsharp
            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }
```
<span data-ttu-id="0d0a4-256">La [`IndexRange`](xref:microsoft.quantum.arrays.indexrange) funzione chiamata su una matrice, ad esempio la matrice di qubits, `qs` restituisce un intervallo sugli indici della matrice.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-256">The [`IndexRange`](xref:microsoft.quantum.arrays.indexrange) function called on an array (e.g. our array of qubits, `qs`) returns a range over the indices of the array.</span></span> <span data-ttu-id="0d0a4-257">In questo esempio viene usato nel `for` ciclo per misurare in modo sequenziale ogni qubit usando l' `M(qs[i])` istruzione.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-257">Here, we use it in our `for` loop to sequentially measure each qubit using the `M(qs[i])` statement.</span></span>
<span data-ttu-id="0d0a4-258">Ogni tipo misurato `Result` ( `Zero` o `One` ) viene quindi aggiunto alla posizione di indice corrispondente in `resultArray` con un'istruzione Update-and-reassign.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-258">Each measured `Result` type (either `Zero` or `One`) is then added to the corresponding index position in `resultArray` with an update-and-reassign statement.</span></span>

> [!NOTE]
> <span data-ttu-id="0d0a4-259">La sintassi di questa istruzione è univoca per Q #, ma corrisponde alla riassegnazione della variabile simile `resultArray[i] <- M(qs[i])` visualizzata in altri linguaggi, ad esempio F # e R.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-259">The syntax of this statement is unique to Q#, but corresponds to the similar variable reassignment `resultArray[i] <- M(qs[i])` seen in other languages such as F# and R.</span></span>

<span data-ttu-id="0d0a4-260">La parola chiave `set` viene sempre utilizzata per riassegnare le variabili associato utilizzando `mutable` .</span><span class="sxs-lookup"><span data-stu-id="0d0a4-260">The keyword `set` is always used to reassign variables bound using `mutable`.</span></span>

#### <a name="return-resultarray"></a><span data-ttu-id="0d0a4-261">Ritorno`resultArray`</span><span class="sxs-lookup"><span data-stu-id="0d0a4-261">Return `resultArray`</span></span>

<span data-ttu-id="0d0a4-262">Con le tre qubits misurate e i risultati aggiunti a `resultArray` , è possibile reimpostare e deallocare il qubits come prima.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-262">With all three qubits measured and the results added to `resultArray`, we are safe to reset and deallocate the qubits as before.</span></span>
<span data-ttu-id="0d0a4-263">Dopo la `using` chiusura del blocco, inserire</span><span class="sxs-lookup"><span data-stu-id="0d0a4-263">After the `using` block's close, insert</span></span>

```qsharp
        return resultArray;
```
<span data-ttu-id="0d0a4-264">per restituire in definitiva l'output dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-264">to ultimately return the output of our operation.</span></span> 

### <a name="understanding-the-effects-of-measurement"></a><span data-ttu-id="0d0a4-265">Informazioni sugli effetti della misurazione</span><span class="sxs-lookup"><span data-stu-id="0d0a4-265">Understanding the effects of measurement</span></span>

<span data-ttu-id="0d0a4-266">Modificare la posizione delle `DumpMachine` funzioni in modo da restituire lo stato prima e dopo le misurazioni.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-266">Let's change the placement of our `DumpMachine` functions to output the state before and after the measurements.</span></span>
<span data-ttu-id="0d0a4-267">Il codice dell'operazione finale dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="0d0a4-267">The final operation code should look like:</span></span> 

```qsharp
    operation Perform3QubitQFT() : Result[] {

        mutable resultArray = new Result[3];

        using (qs = Qubit[3]) {

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("Before measurement: ");
            DumpMachine();

            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }

            Message("After measurement: ");
            DumpMachine();

            ResetAll(qs);
        }
        return resultArray;
    }
}
```

<span data-ttu-id="0d0a4-268">Se si sta lavorando dalla riga di comando, la matrice restituita verrà semplicemente stampata direttamente nella console alla fine dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-268">If you are working from the command line, the returned array will simply be printed directly to the console at the end of the execution.</span></span>
<span data-ttu-id="0d0a4-269">In caso contrario, aggiornare il programma host per elaborare la matrice restituita.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-269">Otherwise, update your host program to process the returned array.</span></span>

#### <a name="command-line"></a>[<span data-ttu-id="0d0a4-270">Riga di comando</span><span class="sxs-lookup"><span data-stu-id="0d0a4-270">Command line</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="0d0a4-271">Per comprendere meglio la matrice restituita che verrà stampata nella console, è possibile aggiungerne un'altra `Message` nel file Q # immediatamente prima dell' `return` istruzione:</span><span class="sxs-lookup"><span data-stu-id="0d0a4-271">To have more understanding of the returned array which will be printed in the console, we can add another `Message` in the Q# file just before the `return` statement:</span></span>

```qsharp
        Message("Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
        return resultArray;
```

<span data-ttu-id="0d0a4-272">Eseguire il progetto. l'output dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="0d0a4-272">Run the project, and your output should look similar to the following:</span></span>

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]
```

#### <a name="python"></a>[<span data-ttu-id="0d0a4-273">Python</span><span class="sxs-lookup"><span data-stu-id="0d0a4-273">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="0d0a4-274">Aggiornare il programma Python a quanto segue:</span><span class="sxs-lookup"><span data-stu-id="0d0a4-274">Update your Python program to the following:</span></span>

```python
import qsharp
from NamespaceQFT import Perform3QubitQFT

measurementResult = Perform3QubitQFT.simulate()
print("\n")
print("Measured post-QFT state: [qubit0, qubit1, qubit2]")
print(measurementResult)

# reversing order to show corresponding basis state in binary form
binaryCompBasisState = ""
for i in measurementResult:
    binaryCompBasisState = str(i) + binaryCompBasisState
print("Corresponding basis state in binary:")
print("|" + binaryCompBasisState + ">")
```

<span data-ttu-id="0d0a4-275">Eseguire il file. l'output dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="0d0a4-275">Run the file, and your output should look similar to the following:</span></span>

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[1, 1, 0]

Corresponding basis state in binary:
|011>
```

#### <a name="c"></a>[<span data-ttu-id="0d0a4-276">C#</span><span class="sxs-lookup"><span data-stu-id="0d0a4-276">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="0d0a4-277">Ora che l'operazione sta restituendo un risultato, sostituire la chiamata al metodo `Wait()` con il recupero della `Result` Proprietà.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-277">Now that our operation is returning a result, replace the method call `Wait()` with fetching the `Result` property.</span></span> <span data-ttu-id="0d0a4-278">Viene comunque eseguita la stessa sincronicità descritta in precedenza ed è possibile associare direttamente questo valore alla variabile `measurementResult` .</span><span class="sxs-lookup"><span data-stu-id="0d0a4-278">This still accomplishes the same synchronicity discussed earlier, and we can directly bind this value to the variable `measurementResult`.</span></span>

```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                var measurementResult = Perform3QubitQFT.Run(qsim).Result;
                System.Console.WriteLine(
                    $"Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
                System.Console.WriteLine(
                    measurementResult);

                // reversing order to show corresponding basis state in binary form
                string binaryCompBasisState = String.Empty;

                foreach (Result i in measurementResult)
                {
                    string iString = i.ToString();
                    binaryCompBasisState = iString + binaryCompBasisState;
                }
                binaryCompBasisState = "|" + binaryCompBasisState + ">";
                System.Console.WriteLine(
                    $"Corresponding basis state in binary:");
                System.Console.WriteLine(
                    binaryCompBasisState);
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}
```

<span data-ttu-id="0d0a4-279">Eseguire il progetto. l'output dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="0d0a4-279">Run the project, and your output should look similar to the following:</span></span>

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]

Corresponding basis state in binary:
|ZeroOneOne>

Press any key to continue...
```
***

<span data-ttu-id="0d0a4-280">Questo output illustra alcuni aspetti diversi:</span><span class="sxs-lookup"><span data-stu-id="0d0a4-280">This output illustrates a few different things:</span></span>
1. <span data-ttu-id="0d0a4-281">Se si confronta il risultato restituito con la pre-misurazione `DumpMachine` , è evidente che _non_ viene illustrata la sovrapposizione post-QFT rispetto agli Stati di base.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-281">Comparing the returned result to the pre-measurement `DumpMachine`, it clearly does _not_ illustrate the post-QFT superposition over basis states.</span></span>
    <span data-ttu-id="0d0a4-282">Una misura restituisce solo uno stato di base, con una probabilità determinata dall'ampiezza di tale stato nel zero del sistema.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-282">A measurement only returns a single basis state, with a probability determined by the amplitude of that state in the system's wavefunction.</span></span>
2. <span data-ttu-id="0d0a4-283">Dal post-misurazione `DumpMachine` si noterà che la misurazione _modifica_ lo stato stesso, proiettando l'oggetto dalla superposizione iniziale sugli stati di base allo stato di base singolo che corrisponde al valore misurato.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-283">From the post-measurement `DumpMachine`, we see that measurement _changes_ the state itself, projecting it from the initial superposition over basis states to the single basis state that corresponds to the measured value.</span></span>

<span data-ttu-id="0d0a4-284">Se dovessimo ripetere questa operazione più volte, le statistiche dei risultati iniziano a illustrare la superposizione ponderata uguale dello stato post-QFT che consente di ottenere un risultato casuale in ogni scatto.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-284">If we were to repeat this operation many times, we would see the result statistics begin to illustrate the equally weighted superposition of the post-QFT state that gives rise to a random result on each shot.</span></span>
<span data-ttu-id="0d0a4-285">_Tuttavia_, oltre a essere inefficienti e comunque imperfetti, questo produce comunque solo le ampiezze relative degli Stati di base, non le fasi relative tra di esse.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-285">_However_, besides being inefficient and still imperfect, this would nevertheless only reproduce the relative amplitudes of the basis states, not the relative phases between them.</span></span>
<span data-ttu-id="0d0a4-286">Quest'ultimo non è un problema in questo esempio, ma le fasi relative vengono visualizzate se si specifica un input più complesso per il QFT di $ \ket {000} $.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-286">The latter is not an issue in this example, but we would see relative phases appear if given a more complex input to the QFT than $\ket{000}$.</span></span>

#### <a name="partial-measurements"></a><span data-ttu-id="0d0a4-287">Misurazioni parziali</span><span class="sxs-lookup"><span data-stu-id="0d0a4-287">Partial measurements</span></span> 
<span data-ttu-id="0d0a4-288">Per esplorare il modo in cui la misurazione di un solo qubits del registro può influire sullo stato del sistema, provare ad aggiungere quanto segue all'interno del `for` ciclo, dopo la riga di misurazione:</span><span class="sxs-lookup"><span data-stu-id="0d0a4-288">To explore how measuring only some qubits of the register can affect the system's state, try adding the following inside the `for` loop, after the measurement line:</span></span>
```qsharp
                let iString = IntAsString(i);
                Message("After measurement of qubit " + iString + ":");
                DumpMachine();
```

<span data-ttu-id="0d0a4-289">Si noti che per accedere alla `IntAsString` funzione sarà necessario aggiungere</span><span class="sxs-lookup"><span data-stu-id="0d0a4-289">Note that to access the `IntAsString` function you will have to add</span></span> 
```qsharp
    open Microsoft.Quantum.Convert;
```
<span data-ttu-id="0d0a4-290">con il resto delle istruzioni dello spazio dei nomi `open` .</span><span class="sxs-lookup"><span data-stu-id="0d0a4-290">with the rest of the namespace `open` statements.</span></span>

<span data-ttu-id="0d0a4-291">Nell'output risultante verrà visualizzata la proiezione graduale negli spazi subspazi quando ogni qubit viene misurato.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-291">In the resulting output, you will see the gradual projection into subspaces as each qubit is measured.</span></span>


## <a name="use-the-q-libraries"></a><span data-ttu-id="0d0a4-292">Usare le librerie Q #</span><span class="sxs-lookup"><span data-stu-id="0d0a4-292">Use the Q# libraries</span></span>
<span data-ttu-id="0d0a4-293">Come indicato nell'introduzione, gran parte della potenza di Q # si basa sul fatto che consente di astrarre le preoccupazioni legate alla gestione dei singoli qubits.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-293">As we mentioned in the introduction, much of Q#'s power rests in the fact that it allows you to abstract-away the worries of dealing with individual qubits.</span></span>
<span data-ttu-id="0d0a4-294">Se invece si vuole sviluppare programmi Quantum applicabili a scalabilità completa, è preferibile sapere se un' `H` operazione viene eseguita prima o dopo una particolare rotazione rallenterà il problema.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-294">Indeed, if you want to develop full-scale, applicable quantum programs, worrying about whether an `H` operation goes before or after a particular rotation would only slow you down.</span></span> 

<span data-ttu-id="0d0a4-295">Le librerie Q # contengono l'operazione [QFT](xref:microsoft.quantum.canon.qft) , che è possibile eseguire e applicare solo per un numero qualsiasi di qubits.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-295">The Q# libraries contain the [QFT](xref:microsoft.quantum.canon.qft) operation, which you can simply take and apply for any number of qubits.</span></span>
<span data-ttu-id="0d0a4-296">Per provare, definire una nuova operazione nel file Q # con lo stesso contenuto di `Perform3QubitQFT` , ma con tutti gli elementi dal primo `H` al `SWAP` sostituito da due semplici righe:</span><span class="sxs-lookup"><span data-stu-id="0d0a4-296">To give it a try, define a new operation in your Q# file which has the same contents of `Perform3QubitQFT`, but with everything from the first `H` to the `SWAP` replaced by two easy lines:</span></span>
```qsharp
            let register = BigEndian(qs);    //from Microsoft.Quantum.Arithmetic
            QFT(register);                   //from Microsoft.Quantum.Canon
```
<span data-ttu-id="0d0a4-297">La prima riga crea semplicemente un' [`BigEndian`](xref:microsoft.quantum.arithmetic.bigendian) espressione della matrice allocata di qubits, `qs` , che è l'elemento che l'operazione [QFT](xref:microsoft.quantum.canon.qft) accetta come argomento.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-297">The first line simply creates a [`BigEndian`](xref:microsoft.quantum.arithmetic.bigendian) expression of the allocated array of qubits, `qs`, which is what the [QFT](xref:microsoft.quantum.canon.qft) operation takes as an argument.</span></span>
<span data-ttu-id="0d0a4-298">Corrisponde all'ordinamento dell'indice di qubits nel registro.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-298">This corresponds to index ordering of the qubits in the register.</span></span>

<span data-ttu-id="0d0a4-299">Per avere accesso a queste operazioni, aggiungere `open` istruzioni per i rispettivi spazi dei nomi all'inizio del file Q #:</span><span class="sxs-lookup"><span data-stu-id="0d0a4-299">To have access to these operations, add `open` statements for their respective namespaces at the beginning of the Q# file:</span></span>
```qsharp
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Arithmetic;
```

<span data-ttu-id="0d0a4-300">Modificare ora il programma host in modo da chiamare il nome della nuova operazione (ad esempio `PerformIntrinsicQFT` ) e conferire un vortice.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-300">Now, adjust your host program to call the name of your new operation (e.g. `PerformIntrinsicQFT`), and give it a whirl.</span></span>

<span data-ttu-id="0d0a4-301">Per visualizzare il vero vantaggio dell'uso delle operazioni della libreria Q #, modificare il numero di qubits in un valore diverso da `3` :</span><span class="sxs-lookup"><span data-stu-id="0d0a4-301">To see the real benefit of using the Q# library operations, change the number of qubits to something other than `3`:</span></span>
```qsharp
        mutable resultArray = new Result[4]; 

        using (qs = Qubit[4]) {
            //...
        }
```
<span data-ttu-id="0d0a4-302">È quindi possibile applicare il QFT appropriato per un determinato numero di qubits, senza doversi preoccupare del pasticcio di nuove `H` operazioni e rotazioni in ogni qubit.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-302">You can thus apply the proper QFT for any given number of qubits, without having to worry about the mess of new `H` operations and rotations on each qubit.</span></span>

<span data-ttu-id="0d0a4-303">Si noti che il simulatore Quantum impiega più tempo per l'esecuzione quando si aumenta il numero di qubits---precisamente il motivo per cui si cerca l'hardware Quantum reale.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-303">Note that the quantum simulator takes exponentially more time to run as you increase the number of qubits---precisely why we look forward to real quantum hardware!</span></span>













