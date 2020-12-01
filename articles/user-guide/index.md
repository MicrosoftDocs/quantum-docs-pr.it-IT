---
title: Manuale dell'utente di Q#
description: Panoramica dello scopo e del contenuto del Manuale dell'utente
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
no-loc:
- Q#
- $$v
ms.openlocfilehash: 979e468cc743bd9125eaba0b71f794977c914447
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231758"
---
# <a name="the-no-locq-user-guide"></a><span data-ttu-id="db5f1-103">Manuale dell'utente di Q#</span><span class="sxs-lookup"><span data-stu-id="db5f1-103">The Q# User Guide</span></span>

<span data-ttu-id="db5f1-104">Benvenuti nel Manuale dell'utente di Q#.</span><span class="sxs-lookup"><span data-stu-id="db5f1-104">Welcome to the Q# User Guide!</span></span> 

<span data-ttu-id="db5f1-105">Nei vari argomenti di questa guida vengono presentate alcune informazioni di base per lo sviluppo di programmi quantistici con Q#.</span><span class="sxs-lookup"><span data-stu-id="db5f1-105">In the different topics of this guide, we introduce some of the basics for developing quantum programs using Q#.</span></span>

<span data-ttu-id="db5f1-106">Per le specifiche complete e la documentazione del linguaggio di programmazione quantistico Q#, vedere la [guida al linguaggio Q#](xref:microsoft.quantum.qsharp.index).</span><span class="sxs-lookup"><span data-stu-id="db5f1-106">We refer to the [Q# language guide](xref:microsoft.quantum.qsharp.index) for a full specification and documentation of the Q# quantum programming language.</span></span> 

## <a name="user-guide-contents"></a><span data-ttu-id="db5f1-107">Sommario del Manuale dell'utente</span><span class="sxs-lookup"><span data-stu-id="db5f1-107">User Guide Contents</span></span>

- <span data-ttu-id="db5f1-108">[Programmi Q#](xref:microsoft.quantum.guide.programs): una breve introduzione ai programmi quantistici in Q#.</span><span class="sxs-lookup"><span data-stu-id="db5f1-108">[Q# programs](xref:microsoft.quantum.guide.programs): An quick introduction to quantum programs in Q#.</span></span> 

- <span data-ttu-id="db5f1-109">[Modalità di esecuzione di programmi Q#](xref:microsoft.quantum.guide.host-programs): descrive come viene eseguito un programma Q# e fornisce una panoramica dei diversi modi in cui è possibile chiamarlo, ovvero dalla riga di comando, nei notebook di Jupyter Q# o da un programma host classico scritto in Python o in un linguaggio .NET.</span><span class="sxs-lookup"><span data-stu-id="db5f1-109">[Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs): describes how a Q# program is run, and provides an overview of the various ways you can call the program: from the command line, in Q# Jupyter Notebooks, or from a classical host program written in Python or a .NET language.</span></span>

- <span data-ttu-id="db5f1-110">[Test e debug](xref:microsoft.quantum.guide.testingdebugging): illustra in dettaglio alcune tecniche per assicurarsi che il codice esegua le operazioni previste.</span><span class="sxs-lookup"><span data-stu-id="db5f1-110">[Testing and debugging](xref:microsoft.quantum.guide.testingdebugging): Details some techniques for making sure your code is doing what it is supposed to do.</span></span> 
    <span data-ttu-id="db5f1-111">A causa dell'opacità generale delle informazioni sul calcolo quantistico, il debug di un programma quantistico può richiedere tecniche specializzate.</span><span class="sxs-lookup"><span data-stu-id="db5f1-111">Due to the general opacity of quantum information, debugging a quantum program can require specialized techniques.</span></span> 
    <span data-ttu-id="db5f1-112">Fortunatamente, Q# supporta molte delle tecniche di debug classiche già note ai programmatori, oltre a quelle specifiche del calcolo quantistico.</span><span class="sxs-lookup"><span data-stu-id="db5f1-112">Fortunately, Q# supports many of the classical debugging techniques programmers are familiar with, as well as those that are quantum-specific.</span></span> <span data-ttu-id="db5f1-113">Ad esempio, la creazione ed esecuzione di unit test in Q#, l'incorporamento di *asserzioni* su valori e probabilità nel codice e le funzioni `Dump` che restituiscono gli stati dei computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="db5f1-113">These include creating and running unit tests in Q#, embedding *assertions* on values and probabilities in your code, and the `Dump` functions which output the states of target machines.</span></span> 
    <span data-ttu-id="db5f1-114">Quest'ultima tecnica può essere usata insieme al simulatore di stato completo per eseguire il debug di determinate parti dei calcoli aggirando alcuni limiti del calcolo quantistico, ad esempio il [teorema di no-cloning](xref:microsoft.quantum.concepts.pauli).</span><span class="sxs-lookup"><span data-stu-id="db5f1-114">The latter can be used alongside our full-state simulator to debug certain parts of computations by skirting some quantum limitations, for example, the [no-cloning theorem](xref:microsoft.quantum.concepts.pauli).</span></span>

### <a name="quantum-simulators-and-resource-estimators"></a><span data-ttu-id="db5f1-115">Simulatori quantistici e strumenti di stima delle risorse</span><span class="sxs-lookup"><span data-stu-id="db5f1-115">Quantum Simulators and Resource Estimators</span></span>

- <span data-ttu-id="db5f1-116">[Simulatori quantistici e applicazioni host](xref:microsoft.quantum.machines): una panoramica dei diversi simulatori disponibili, oltre che dell'interazione tra programmi host e computer di destinazione per l'esecuzione di programmi Q#.</span><span class="sxs-lookup"><span data-stu-id="db5f1-116">[Quantum simulators and host applications](xref:microsoft.quantum.machines): An overview of the different simulators available, as well of how host programs and target machines work together to run Q# programs.</span></span>

- <span data-ttu-id="db5f1-117">[Simulatore di stato completo](xref:microsoft.quantum.machines.full-state-simulator): computer di destinazione che simula lo stato quantistico completo.</span><span class="sxs-lookup"><span data-stu-id="db5f1-117">[Full state simulator](xref:microsoft.quantum.machines.full-state-simulator): The target machine which simulates the full quantum state.</span></span> <span data-ttu-id="db5f1-118">Utile per l'esecuzione completa o il debug di programmi su scala ridotta (meno di alcune decine di qubit)</span><span class="sxs-lookup"><span data-stu-id="db5f1-118">Useful for fully running or debugging smaller-scale programs (less than a few dozen qubits)</span></span>

- <span data-ttu-id="db5f1-119">[Stima delle risorse](xref:microsoft.quantum.machines.resources-estimator): stima le risorse necessarie per eseguire un'istanza specifica di un'operazione Q# in un computer quantistico.</span><span class="sxs-lookup"><span data-stu-id="db5f1-119">[Resources estimator](xref:microsoft.quantum.machines.resources-estimator): Estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>

- <span data-ttu-id="db5f1-120">[Simulatore di traccia](xref:microsoft.quantum.machines.qc-trace-simulator.intro): esegue un programma quantistico senza simulare effettivamente lo stato di un computer quantistico e di conseguenza può eseguire programmi quantistici che usano migliaia di qubit.</span><span class="sxs-lookup"><span data-stu-id="db5f1-120">[Trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro): Runs a quantum program without actually simulating the state of a quantum computer, and therefore can run quantum programs that use thousands of qubits.</span></span> <span data-ttu-id="db5f1-121">Utile per il debug di codice classico in un programma quantistico, nonché per la stima delle risorse necessarie.</span><span class="sxs-lookup"><span data-stu-id="db5f1-121">Useful for debugging classical code within a quantum program, as well as estimating resources required.</span></span>

- <span data-ttu-id="db5f1-122">[Simulatore di Toffoli](xref:microsoft.quantum.machines.toffoli-simulator): simulatore quantistico per scopi specifici che può essere usato con milioni di qubit, ma solo per i programmi con un set limitato di operazioni quantistiche, ovvero X, CNOT e X multi-controllate.</span><span class="sxs-lookup"><span data-stu-id="db5f1-122">[Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator): A special-purpose quantum simulator that can be used with millions of qubits, but only for programs with a restricted set of quantum operations - X, CNOT, and multi-controlled X.</span></span>

### <a name="quick-reference-pages"></a><span data-ttu-id="db5f1-123">Pagine di riferimento rapido</span><span class="sxs-lookup"><span data-stu-id="db5f1-123">Quick Reference Pages</span></span>

- <span data-ttu-id="db5f1-124">[Comandi magic di IQ#](xref:microsoft.quantum.guide.quickref.iqsharp): Pagina di riferimento rapido per i comandi magic di IQ# nei notebook di Jupyter Q#.</span><span class="sxs-lookup"><span data-stu-id="db5f1-124">[IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp): Quick reference page for IQ# magic commands within Q# Jupyter Notebooks.</span></span>
