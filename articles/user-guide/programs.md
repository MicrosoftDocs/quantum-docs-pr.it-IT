---
title: 'Q # Introduzione'
description: 'Introduzione rapida ai programmi Quantum in Q #'
author: beheim
ms.author: beheim
ms.date: 11/08/2020
ms.topic: article
uid: microsoft.quantum.guide.programs
ms.openlocfilehash: 975bcda5e0042406b465a83f17f1d2d3f5a1ec4f
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96233978"
---
# <a name="q-quantum-programming-language"></a><span data-ttu-id="b7861-103">Linguaggio di programmazione Quantum Q #</span><span class="sxs-lookup"><span data-stu-id="b7861-103">Q# Quantum Programming Language</span></span>

<span data-ttu-id="b7861-104">Tutto ciò che è necessario sapere sul linguaggio di programmazione Q # è illustrato in dettaglio nella [Guida del linguaggio q #](xref:microsoft.quantum.qsharp.index).</span><span class="sxs-lookup"><span data-stu-id="b7861-104">Everything you need to know about the Q# programming language is detailed in the [Q# language guide](xref:microsoft.quantum.qsharp.index).</span></span> <span data-ttu-id="b7861-105">Come qualsiasi altra cosa, il [processo di progettazione del linguaggio](https://github.com/microsoft/qsharp-language#q-language-and-core-libraries-design) è open source e i contributi sono benvenuti.</span><span class="sxs-lookup"><span data-stu-id="b7861-105">Like anything else, our [language design process](https://github.com/microsoft/qsharp-language#q-language-and-core-libraries-design) is open source and we welcome contributions.</span></span>
<span data-ttu-id="b7861-106">Per informazioni più dettagliate sulle fondamenta e la motivazione alla base di Q #, vedere [perché è necessario q #?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).</span><span class="sxs-lookup"><span data-stu-id="b7861-106">For more background about the foundations and motivation behind Q#, see [Why do we need Q#?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).</span></span>  
<span data-ttu-id="b7861-107">Q # viene fornito come parte del quantum Development Kit (QDK) per una rapida panoramica, vedere [che cos'è QDK?](xref:microsoft.quantum.overview.q-sharp).</span><span class="sxs-lookup"><span data-stu-id="b7861-107">Q# is shipped as part of the Quantum Development Kit (QDK) For a quick overview, check out [What is the QDK?](xref:microsoft.quantum.overview.q-sharp).</span></span> 

## <a name="what-is-a-quantum-program"></a><span data-ttu-id="b7861-108">Che cos'è un programma Quantum?</span><span class="sxs-lookup"><span data-stu-id="b7861-108">What is a quantum program?</span></span>

<span data-ttu-id="b7861-109">Un programma quantum può essere considerato come un particolare set di subroutine classiche che, quando chiamato, eseguono un calcolo interagendo con un sistema quantico; un programma scritto in Q # non modella direttamente lo stato del quantum, bensì descrive il modo in cui un computer di controllo classico interagisce con qubits.</span><span class="sxs-lookup"><span data-stu-id="b7861-109">A quantum program can be seen as a particular set of classical subroutines which, when called, perform a computation by interacting with a quantum system; a program written in Q# does not directly model the quantum state, but rather describes how a classical control computer interacts with qubits.</span></span>
<span data-ttu-id="b7861-110">Ciò consente di essere completamente agnostico sullo stato del *Quantum anche in ogni computer di destinazione* , che potrebbe avere interpretazioni diverse a seconda del computer.</span><span class="sxs-lookup"><span data-stu-id="b7861-110">This allows us to be entirely agnostic about what a quantum state even *is* on each target machine, which might have different interpretations depending on the machine.</span></span> 

<span data-ttu-id="b7861-111">Una conseguenza importante è che Q # non è in grado di analizzare nello stato di un qubit o di altre proprietà di Quantum Mechanics direttamente, il che garantisce che un programma Q # possa essere eseguito fisicamente su un computer Quantum.</span><span class="sxs-lookup"><span data-stu-id="b7861-111">An important consequence of that is that Q# has no ability to introspect into the state of a qubit or other properties of quantum mechanics directly, which guarantees that a Q# program can be physically executed on a quantum computer.</span></span>
<span data-ttu-id="b7861-112">Al contrario, un programma può chiamare operazioni come [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) per estrarre le informazioni classiche da un qubit.</span><span class="sxs-lookup"><span data-stu-id="b7861-112">Instead, a program can call operations such as [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) to extract classical information from a qubit.</span></span>

<span data-ttu-id="b7861-113">Una volta allocato, un qubit può essere passato a operazioni e funzioni, denominate anche *Callable*.</span><span class="sxs-lookup"><span data-stu-id="b7861-113">Once allocated, a qubit can be passed to operations and functions, also referred to as *callables*.</span></span> <span data-ttu-id="b7861-114">In un certo senso, questo è tutto ciò che può fare un programma Q # con un qubit. Tutte le azioni dirette sullo stato di una qubit sono tutte definite da chiamabili *intrinseci* , ad esempio e, ad [`X`](xref:Microsoft.Quantum.Intrinsic.X) [`H`](xref:Microsoft.Quantum.Intrinsic.H) esempio Callable le cui implementazioni non sono definite in Q # ma sono invece definite dal computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="b7861-114">In some sense, this is all that a Q# program can do with a qubit; Any direct actions on state of a qubit are all defined by *intrinsic* callables such as [`X`](xref:Microsoft.Quantum.Intrinsic.X) and [`H`](xref:Microsoft.Quantum.Intrinsic.H) - i.e. callables whose implementations are not defined within Q# but are instead defined by the target machine.</span></span> <span data-ttu-id="b7861-115">Le operazioni effettivamente eseguite dal computer di *destinazione vengono usate* solo per eseguire il programma Q # specifico.</span><span class="sxs-lookup"><span data-stu-id="b7861-115">What these operations actually *do* is only made concrete by the target machine we use to run the particular Q# program.</span></span>

<span data-ttu-id="b7861-116">Ad esempio, se si esegue il programma nel [simulatore a stato completo](xref:microsoft.quantum.machines.full-state-simulator), il simulatore esegue le operazioni matematiche corrispondenti al sistema Quantum simulato.</span><span class="sxs-lookup"><span data-stu-id="b7861-116">For example, if running the program on our [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), the simulator performs the corresponding mathematical operations to the simulated quantum system.</span></span>
<span data-ttu-id="b7861-117">Tuttavia, guardando il futuro, quando il computer di destinazione è un computer Quantum reale, la chiamata di tali operazioni in Q # indirizza il computer Quantum a eseguire le operazioni *effettive* corrispondenti sul sistema Quantum *reale* , ad esempio gli impulsi laser temporizzati.</span><span class="sxs-lookup"><span data-stu-id="b7861-117">But looking toward the future, when the target machine is a real quantum computer, calling such operations in Q# will direct the quantum computer to perform the corresponding *real* operations on the *real* quantum system (e.g. precisely timed laser pulses).</span></span>

<span data-ttu-id="b7861-118">Un programma Q # ricombina queste operazioni in base a quanto definito da un computer di destinazione per creare nuove operazioni di livello superiore per esprimere il calcolo quantistico.</span><span class="sxs-lookup"><span data-stu-id="b7861-118">A Q# program recombines these operations as defined by a target machine to create new, higher-level operations to express quantum computation.</span></span>
<span data-ttu-id="b7861-119">In questo modo, Q # rende più semplice esprimere gli algoritmi quantistici e Quantum sottostanti alla logica, oltre a essere generali rispetto alla struttura di un computer o di un simulatore di destinazione.</span><span class="sxs-lookup"><span data-stu-id="b7861-119">In this way, Q# makes it easy to express the logic underlying quantum and hybrid quantum–classical algorithms, while also being general with respect to the structure of a target machine or simulator.</span></span>

<span data-ttu-id="b7861-120">Un semplice esempio è il programma seguente, che alloca un qubit nello stato $ \ket {0} $, quindi applica un'operazione Hadamard `H` e misura il risultato in `PauliZ` base a.</span><span class="sxs-lookup"><span data-stu-id="b7861-120">A simple example is the following program, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

```qsharp
@EntryPoint()
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now we measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // we reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, we return the result of the measurement.
        return result;
    }
}
```

<span data-ttu-id="b7861-121">I [Kata di Quantum](https://github.com/microsoft/QuantumKatas#introduction) forniscono una corretta introduzione ai [concetti relativi al quantum computing](https://github.com/microsoft/QuantumKatas#quantum-computing-concepts-qubits-and-gates) , ad esempio le operazioni Quantum comuni e come manipolare qubits.</span><span class="sxs-lookup"><span data-stu-id="b7861-121">Our [Quantum Katas](https://github.com/microsoft/QuantumKatas#introduction) give a good introduction on [Quantum Computing Concepts](https://github.com/microsoft/QuantumKatas#quantum-computing-concepts-qubits-and-gates) such as common quantum operations and how to manipulate qubits.</span></span> <span data-ttu-id="b7861-122">Altri esempi sono disponibili anche in [operazioni e funzioni intrinseche](xref:microsoft.quantum.libraries.standard.prelude).</span><span class="sxs-lookup"><span data-stu-id="b7861-122">More examples can also be found in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude).</span></span>



