---
title: Manuale dell'utente di Q#
description: Panoramica dello scopo e del contenuto del Manuale dell'utente
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4fae2949bdcab0c3735b40ef029d70bf7ea3fb9f
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869631"
---
# <a name="the-no-locq-user-guide"></a><span data-ttu-id="d163e-103">Manuale dell'utente di Q#</span><span class="sxs-lookup"><span data-stu-id="d163e-103">The Q# User Guide</span></span>

<span data-ttu-id="d163e-104">Benvenuti nel Manuale dell'utente di Q#.</span><span class="sxs-lookup"><span data-stu-id="d163e-104">Welcome to the Q# User Guide!</span></span> 

<span data-ttu-id="d163e-105">Nei vari argomenti di questa guida vengono illustrati in dettaglio i concetti di base del linguaggio Q# e vengono fornite tutte le informazioni necessarie per la scrittura di programmi quantistici.</span><span class="sxs-lookup"><span data-stu-id="d163e-105">In the different topics of this guide, we detail the core concepts of the Q# language and all the information you need to write quantum programs.</span></span>

## <a name="user-guide-contents"></a><span data-ttu-id="d163e-106">Sommario del Manuale dell'utente</span><span class="sxs-lookup"><span data-stu-id="d163e-106">User Guide Contents</span></span>

- <span data-ttu-id="d163e-107">[Nozioni di base su Q#](xref:microsoft.quantum.guide.basics): offre una panoramica introduttiva dello scopo e delle funzionalità del linguaggio di programmazione Q#.</span><span class="sxs-lookup"><span data-stu-id="d163e-107">[Q# Basics](xref:microsoft.quantum.guide.basics): An introductory overview of the purpose and functionality of the Q# programming language.</span></span> 

- <span data-ttu-id="d163e-108">[Modalità di esecuzione di programmi Q#](xref:microsoft.quantum.guide.host-programs): descrive come viene eseguito un programma Q# e fornisce una panoramica dei diversi modi in cui è possibile chiamarlo, ovvero dalla riga di comando, nei notebook di Jupyter Q# o da un programma host classico scritto in Python o in un linguaggio .NET.</span><span class="sxs-lookup"><span data-stu-id="d163e-108">[Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs): describes how a Q# program is executed, and provides an overview of the various ways you can call the program: from the command line, in Q# Jupyter Notebooks, or from a classical host program written in Python or a .NET language.</span></span>

### <a name="no-locq-language"></a><span data-ttu-id="d163e-109">Linguaggio Q#</span><span class="sxs-lookup"><span data-stu-id="d163e-109">Q# Language</span></span>

- <span data-ttu-id="d163e-110">[Tipi in Q#](xref:microsoft.quantum.guide.types): definisce il modello di tipo Q# e descrive la sintassi per specificare e usare i tipi.</span><span class="sxs-lookup"><span data-stu-id="d163e-110">[Types in Q#](xref:microsoft.quantum.guide.types): Lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>

- <span data-ttu-id="d163e-111">[Espressioni di tipo](xref:microsoft.quantum.guide.expressions): illustra in dettaglio come specificare, fare riferimento, combinare e operare su valori di ogni tipo in Q#.</span><span class="sxs-lookup"><span data-stu-id="d163e-111">[Type Expressions](xref:microsoft.quantum.guide.expressions): Details how to specify, reference, combine, and operate on values of each type in Q#.</span></span> 

### <a name="using-no-locq"></a><span data-ttu-id="d163e-112">Uso di Q#</span><span class="sxs-lookup"><span data-stu-id="d163e-112">Using Q#</span></span>

- <span data-ttu-id="d163e-113">[Struttura dei file Q#](xref:microsoft.quantum.guide.filestructure): illustra la struttura e la sintassi di un file Q# con estensione `*.qs`.</span><span class="sxs-lookup"><span data-stu-id="d163e-113">[Q# File Structure](xref:microsoft.quantum.guide.filestructure): Describes the structure and syntax of a `*.qs` Q# file.</span></span>

- <span data-ttu-id="d163e-114">[Operazioni e funzioni](xref:microsoft.quantum.guide.operationsfunctions): illustra in dettaglio i due tipi chiamabili del linguaggio Q#, ovvero le *operazioni*, che includono l'azione sui registri qubit, e le *funzioni*, che operano esclusivamente con le informazioni classiche.</span><span class="sxs-lookup"><span data-stu-id="d163e-114">[Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions): Details the two callable types of the Q# language: *operations*, which include action on qubit registers, and *functions*, which strictly work with classical information.</span></span> 
    <span data-ttu-id="d163e-115">In questo articolo viene illustrato come definirli e chiamarli e vengono descritte le versioni controllata e contigua delle operazioni quantistiche.</span><span class="sxs-lookup"><span data-stu-id="d163e-115">Here you see how to define and call them, including the adjoint and controlled versions of quantum operations.</span></span>

- <span data-ttu-id="d163e-116">[Variabili](xref:microsoft.quantum.guide.variables): descrive il ruolo delle variabili nei programmi Q# e spiega come sfruttarle in modo efficace.</span><span class="sxs-lookup"><span data-stu-id="d163e-116">[Variables](xref:microsoft.quantum.guide.variables): Describes the role of variables within Q# programs and how to leverage them effectively.</span></span> 
    <span data-ttu-id="d163e-117">Include, ad esempio, informazioni sugli ambiti di associazione, nonché sulla differenza tra variabili modificabili e non modificabili e su come assegnarle o riassegnarle.</span><span class="sxs-lookup"><span data-stu-id="d163e-117">For example, you can find information about binding scopes, as well as the difference between immutable and mutable variables and how to assign or re-assign them.</span></span>

- <span data-ttu-id="d163e-118">[Uso dei qubit](xref:microsoft.quantum.guide.qubits): descrive le funzionalità di Q# usate per risolvere singoli qubit e sistemi di qubit, in particolare, come allocarli, eseguire operazioni su di essi e come misurarli.</span><span class="sxs-lookup"><span data-stu-id="d163e-118">[Working with qubits](xref:microsoft.quantum.guide.qubits): Describes the features of Q# used to address individual qubits and systems of qubits, specifically, allocating them, performing operations on them, and measuring them.</span></span> 

- <span data-ttu-id="d163e-119">[Flusso di controllo](xref:microsoft.quantum.guide.controlflow): descrive in dettaglio i modelli di flusso di controllo di programmazione disponibili in Q#, che include numerose tecniche standard (ad esempio esecuzione condizionale, cicli for, cicli while e così via), nonché il modello "ripetizione fino al completamento" specifico del calcolo quantistico.</span><span class="sxs-lookup"><span data-stu-id="d163e-119">[Control Flow](xref:microsoft.quantum.guide.controlflow): Details the programming control flow patterns available in Q#, which includes many standard techniques (such as conditional execution, for loops, while loops) as well as the quantum-specific "Repeat-Until-Success" pattern.</span></span>

- <span data-ttu-id="d163e-120">[Test e debug](xref:microsoft.quantum.guide.testingdebugging): illustra in dettaglio alcune tecniche per assicurarsi che il codice esegua le operazioni previste.</span><span class="sxs-lookup"><span data-stu-id="d163e-120">[Testing and debugging](xref:microsoft.quantum.guide.testingdebugging): Details some techniques for making sure your code is doing what it is supposed to do.</span></span> 
    <span data-ttu-id="d163e-121">A causa dell'opacità generale delle informazioni sul calcolo quantistico, il debug di un programma quantistico può richiedere tecniche specializzate.</span><span class="sxs-lookup"><span data-stu-id="d163e-121">Due to the general opacity of quantum information, debugging a quantum program can require specialized techniques.</span></span> 
    <span data-ttu-id="d163e-122">Fortunatamente, Q# supporta molte delle tecniche di debug classiche già note ai programmatori, oltre a quelle specifiche del calcolo quantistico.</span><span class="sxs-lookup"><span data-stu-id="d163e-122">Fortunately, Q# supports many of the classical debugging techniques programmers are familiar with, as well as those that are quantum-specific.</span></span> <span data-ttu-id="d163e-123">Ad esempio, la creazione ed esecuzione di unit test in Q#, l'incorporamento di *asserzioni* su valori e probabilità nel codice e le funzioni `Dump` che restituiscono gli stati dei computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d163e-123">These include creating and running unit tests in Q#, embedding *assertions* on values and probabilities in your code, and the `Dump` functions which output the states of target machines.</span></span> 
    <span data-ttu-id="d163e-124">Quest'ultima tecnica può essere usata insieme al simulatore di stato completo per eseguire il debug di determinate parti dei calcoli aggirando alcuni limiti del calcolo quantistico, ad esempio il [teorema di no-cloning](xref:microsoft.quantum.concepts.pauli).</span><span class="sxs-lookup"><span data-stu-id="d163e-124">The latter can be used alongside our full-state simulator to debug certain parts of computations by skirting some quantum limitations, for example, the [no-cloning theorem](xref:microsoft.quantum.concepts.pauli).</span></span>

### <a name="quantum-simulators-and-resource-estimators"></a><span data-ttu-id="d163e-125">Simulatori quantistici e strumenti di stima delle risorse</span><span class="sxs-lookup"><span data-stu-id="d163e-125">Quantum Simulators and Resource Estimators</span></span>

- <span data-ttu-id="d163e-126">[Simulatori quantistici e applicazioni host](xref:microsoft.quantum.machines): offre una panoramica dei diversi simulatori disponibili e illustra il modello di esecuzione generico tra i programmi host e i computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d163e-126">[Quantum simulators and host applications](xref:microsoft.quantum.machines): An overview of the different simulators available, as well as the general execution model between host programs and target machines.</span></span>

- <span data-ttu-id="d163e-127">[Simulatore di stato completo](xref:microsoft.quantum.machines.full-state-simulator): computer di destinazione che simula lo stato quantistico completo.</span><span class="sxs-lookup"><span data-stu-id="d163e-127">[Full state simulator](xref:microsoft.quantum.machines.full-state-simulator): The target machine which simulates the full quantum state.</span></span> <span data-ttu-id="d163e-128">Utile per l'esecuzione completa o il debug di programmi di scala ridotta (meno di alcune decine di qubit).</span><span class="sxs-lookup"><span data-stu-id="d163e-128">Useful for fully executing or debugging smaller-scale programs (less than a few dozen qubits)</span></span>

- <span data-ttu-id="d163e-129">[Stima delle risorse](xref:microsoft.quantum.machines.resources-estimator): stima le risorse necessarie per eseguire un'istanza specifica di un'operazione Q# in un computer quantistico.</span><span class="sxs-lookup"><span data-stu-id="d163e-129">[Resources estimator](xref:microsoft.quantum.machines.resources-estimator): Estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>

- <span data-ttu-id="d163e-130">[Simulatore di traccia](xref:microsoft.quantum.machines.qc-trace-simulator.intro): esegue un programma quantistico senza simulare effettivamente lo stato di un computer quantistico, di conseguenza può eseguire programmi quantistici che usano migliaia di qubit.</span><span class="sxs-lookup"><span data-stu-id="d163e-130">[Trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro): Executes a quantum program without actually simulating the state of a quantum computer, and therefore can execute quantum programs that use thousands of qubits.</span></span> <span data-ttu-id="d163e-131">Utile per il debug di codice classico in un programma quantistico, nonché per la stima delle risorse necessarie.</span><span class="sxs-lookup"><span data-stu-id="d163e-131">Useful for debugging classical code within a quantum program, as well as estimating resources required.</span></span>

- <span data-ttu-id="d163e-132">[Simulatore di Toffoli](xref:microsoft.quantum.machines.toffoli-simulator): simulatore quantistico per scopi specifici che può essere usato con milioni di qubit, ma solo per i programmi con un set limitato di operazioni quantistiche, ovvero X, CNOT e X multi-controllate.</span><span class="sxs-lookup"><span data-stu-id="d163e-132">[Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator): A special-purpose quantum simulator that can be used with millions of qubits, but only for programs with a restricted set of quantum operations - X, CNOT, and multi-controlled X.</span></span>

### <a name="quick-reference-pages"></a><span data-ttu-id="d163e-133">Pagine di riferimento rapido</span><span class="sxs-lookup"><span data-stu-id="d163e-133">Quick Reference Pages</span></span>

- <span data-ttu-id="d163e-134">[Comandi magic di IQ#](xref:microsoft.quantum.guide.quickref.iqsharp): Pagina di riferimento rapido per i comandi magic di IQ# nei notebook di Jupyter Q#.</span><span class="sxs-lookup"><span data-stu-id="d163e-134">[IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp): Quick reference page for IQ# magic commands within Q# Jupyter Notebooks.</span></span>
