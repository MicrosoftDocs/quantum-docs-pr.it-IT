---
title: Utilizzo di qubits | Microsoft Docs
description: Uso di qubits
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.qubits
ms.openlocfilehash: d1a8ccc9423a9a04e12bc98e3783790232b2f5d8
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183472"
---
# <a name="working-with-qubits"></a><span data-ttu-id="1fbd2-103">Uso di qubits</span><span class="sxs-lookup"><span data-stu-id="1fbd2-103">Working with Qubits</span></span> #

<span data-ttu-id="1fbd2-104">Avendo visto una serie di diverse parti del linguaggio Q #, è possibile passare al suo interno e vedere come usare qubits.</span><span class="sxs-lookup"><span data-stu-id="1fbd2-104">Having now seen a variety of different parts of the Q# language, let us get into the thick of it and see how to use qubits themselves.</span></span>

## <a name="allocating-qubits"></a><span data-ttu-id="1fbd2-105">Allocazione di qubits</span><span class="sxs-lookup"><span data-stu-id="1fbd2-105">Allocating Qubits</span></span> ##

<span data-ttu-id="1fbd2-106">Per prima cosa, per ottenere un qubit che è possibile usare in Q #, viene *allocato* qubits in un blocco `using`:</span><span class="sxs-lookup"><span data-stu-id="1fbd2-106">First, to obtain a qubit that we can use in Q#, we *allocate* qubits within a `using` block:</span></span>

```qsharp
using (register = Qubit[5]) {
    // Do stuff...
}
```

<span data-ttu-id="1fbd2-107">Tutti i qubits allocati in questo modo iniziano con lo stato $ \ket{0}$; Nell'esempio precedente `register` si trova quindi nello stato $ \ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="1fbd2-107">Any qubits allocated in this way start off in the $\ket{0}$ state; in the example above, `register` is thus in the state $\ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span></span>
<span data-ttu-id="1fbd2-108">Alla fine del blocco `using`, qualsiasi qubits allocato da tale blocco viene immediatamente deallocato e non può essere usato ulteriormente.</span><span class="sxs-lookup"><span data-stu-id="1fbd2-108">At the end of the `using` block, any qubits allocated by that block are immediately deallocated and cannot be used further.</span></span>

> [!WARNING]
> <span data-ttu-id="1fbd2-109">I computer di destinazione si aspettano che qubits si trovino nello stato $ \ket{0}$ immediatamente prima della deallocazione, in modo che possano essere riutilizzati e offerti ad altri blocchi `using` per l'allocazione.</span><span class="sxs-lookup"><span data-stu-id="1fbd2-109">Target machines expect that qubits are in the $\ket{0}$ state immediately before deallocation, so that they can be reused and offered to other `using` blocks for allocation.</span></span>
> <span data-ttu-id="1fbd2-110">Quando possibile, usare le operazioni unitarie per restituire i qubits allocati a $ \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="1fbd2-110">Whenever possible, use unitary operations to return any allocated qubits to $\ket{0}$.</span></span>
> <span data-ttu-id="1fbd2-111">Se necessario, è possibile utilizzare l'operazione @"microsoft.quantum.intrinsic.reset" per misurare un qubit e utilizzare tale risultato per garantire che il valore di qubit misurato venga restituito a $ \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="1fbd2-111">If need be, the @"microsoft.quantum.intrinsic.reset" operation can be used to measure a qubit instead, and to use that measurement result to ensure that the measured qubit is returned to $\ket{0}$.</span></span> <span data-ttu-id="1fbd2-112">Una misura di questo tipo eliminerà eventuali problemi con i restanti qubits e può quindi influisca sul calcolo.</span><span class="sxs-lookup"><span data-stu-id="1fbd2-112">Such a measurement will destroy any entanglement with the remaining qubits and can thus impact the computation.</span></span> 

## <a name="intrinsic-operations"></a><span data-ttu-id="1fbd2-113">Operazioni intrinseche</span><span class="sxs-lookup"><span data-stu-id="1fbd2-113">Intrinsic Operations</span></span> ##

<span data-ttu-id="1fbd2-114">Una volta allocato, un qubit può quindi essere passato a funzioni e operazioni.</span><span class="sxs-lookup"><span data-stu-id="1fbd2-114">Once allocated, a qubit can then be passed to functions and operations.</span></span>
<span data-ttu-id="1fbd2-115">In un certo senso, questo è tutto ciò che può fare un programma Q # con un qubit, in quanto le azioni che è possibile eseguire sono tutte definite come operazioni.</span><span class="sxs-lookup"><span data-stu-id="1fbd2-115">In some sense, this is all that a Q# program can do with a qubit, as the actions that can be taken are all defined as operations.</span></span>
<span data-ttu-id="1fbd2-116">Queste operazioni verranno visualizzate in modo più dettagliato nelle [operazioni e funzioni intrinseche](xref:microsoft.quantum.libraries.standard.prelude), ma per il momento si menzioneranno alcune operazioni utili che possono essere usate per interagire con qubits.</span><span class="sxs-lookup"><span data-stu-id="1fbd2-116">We will see these operations in more detail in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), but for now, we mention a few useful operations that can be used to interact with qubits.</span></span>

<span data-ttu-id="1fbd2-117">In primo luogo, gli operatori di Pauli Single-qubit $X $, $Y $ e $Z $ sono rappresentati in Q # dalle operazioni intrinseche `X`, `Y`e `Z`, ognuno dei quali ha un tipo `(Qubit => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="1fbd2-117">First, the single-qubit Pauli operators $X$, $Y$, and $Z$ are represented in Q# by the intrinsic operations `X`, `Y`, and `Z`, each of which has type `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="1fbd2-118">Come descritto in [operazioni e funzioni intrinseche](xref:microsoft.quantum.libraries.standard.prelude), è possibile pensare a $X $ e quindi di `X` come operazione di capovolgimento di bit o non di controllo.</span><span class="sxs-lookup"><span data-stu-id="1fbd2-118">As described in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), we can think of $X$ and hence of `X` as a bit-flip operation or NOT gate.</span></span>
<span data-ttu-id="1fbd2-119">In questo modo è possibile preparare gli Stati del form $ \ket{s_0 s_1 \dots S_n} $ per una stringa di bit classica $s $:</span><span class="sxs-lookup"><span data-stu-id="1fbd2-119">This lets us prepare states of the form $\ket{s_0 s_1 \dots s_n}$ for some classical bit string $s$:</span></span>

```qsharp
operation PrepareBitString(bitstring : Bool[], register : Qubit[]) : Unit 
is Adj + Ctl {

    let nQubits = Length(register);
    for (idxQubit in 0..nQubits - 1) {
        if (bitstring[idxQubit]) {
            X(register[idxQubit]);
        }
    }
}

operation Example() : Unit {

    using (register = Qubit[8]) {
        PrepareBitString(
            [true, true, false, false, true, false, false, true],
            register
        );
        // At this point, register now has the state |11001001〉.
    }
}
```

> [!TIP]
> <span data-ttu-id="1fbd2-120">In un secondo momento, verrà illustrato come scrivere questa operazione in modo più compatto che non richiede il controllo di flusso manuale.</span><span class="sxs-lookup"><span data-stu-id="1fbd2-120">Later, we will see more compact ways of writing this operation that do not require manual flow control.</span></span>

<span data-ttu-id="1fbd2-121">È inoltre possibile preparare gli Stati, ad esempio $ \ket{+} = \left (\ket{0} + \ket{1}\right)/\sqrt{2}$ e $ \ket{-} = \left (\ket{0}-\ket{1}\right)/\sqrt{2}$ utilizzando la trasformazione Hadamard $H $ , rappresentato in Q # dall'operazione intrinseca `H : (Qubit => Unit is Adj + Ctl)`:</span><span class="sxs-lookup"><span data-stu-id="1fbd2-121">We can also prepare states such as $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ and $\ket{-} = \left(\ket{0} - \ket{1}\right) / \sqrt{2}$ by using the Hadamard transform $H$, which is represented in Q# by the intrinsic operation `H : (Qubit => Unit is Adj + Ctl)`:</span></span>

```qsharp
operation PreparePlusMinusState(bitstring : Bool[], register : Qubit[]) : Unit {

    // First, get a computational basis state of the form
    // |s_0 s_1 ... s_n〉 by using PrepareBitString, above.
    PrepareBitString(bitstring, register);
    // Next, we use that |+〉 = H|0〉 and |-〉 = H|1〉 to
    // prepare the state we want.
    for (idxQubit in IndexRange(register)) {
        H(register[idxQubit]);
    }
}
```

## <a name="measurements"></a><span data-ttu-id="1fbd2-122">Measurements (Misure)</span><span class="sxs-lookup"><span data-stu-id="1fbd2-122">Measurements</span></span> ##

<span data-ttu-id="1fbd2-123">Utilizzando l'operazione di `Measure`, ovvero un'operazione intrinseca non unitaria incorporata, è possibile estrarre le informazioni classiche da un oggetto di tipo `Qubit` e assegnare un valore classico come risultato, che ha un tipo riservato `Result`, a indicare che il risultato è no. più uno stato quantum.</span><span class="sxs-lookup"><span data-stu-id="1fbd2-123">Using the `Measure` operation, which is a built in intrinsic non-unitary operation, we can extract classical information from an object of type `Qubit` and assign a classical value as a result, which has a reserved type `Result`, indicating that the result is no longer a quantum state.</span></span> <span data-ttu-id="1fbd2-124">L'input per `Measure` è un asse di Pauli nella sfera Bloch, rappresentato da un oggetto di tipo `Pauli` (ad esempio, per `PauliX`di istanza) e da un oggetto di tipo `Qubit`.</span><span class="sxs-lookup"><span data-stu-id="1fbd2-124">The input to `Measure` is a Pauli axis on the Bloch sphere, represented by an object of type `Pauli` (i.e., for instance `PauliX`) and an object of type `Qubit`.</span></span> 

<span data-ttu-id="1fbd2-125">Un esempio semplice è l'operazione seguente che crea un qubit nello stato $ \ket{0}$, quindi applica una ``H`` Gate di Hadamard e quindi misura il risultato in base `PauliZ`.</span><span class="sxs-lookup"><span data-stu-id="1fbd2-125">A simple example is the following operation which creates one qubit in the $\ket{0}$ state, then applies a Hadamard gate ``H`` to it and then measures the result in the `PauliZ` basis.</span></span> 

```qsharp
operation MeasurementOneQubit () : Result {

    // The following using block creates a fresh qubit and initializes it 
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby creating the 
        // state 1/sqrt(2)(|0〉+|1〉). 
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

<span data-ttu-id="1fbd2-126">Un esempio leggermente più complesso è fornito dall'operazione seguente che restituisce il valore booleano `true` se tutti i qubits in un registro di tipo `Qubit[]` sono nello stato zero, se misurato in base a Pauli specificato e `false` in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="1fbd2-126">A slightly more complicated example is given by the following operation which returns the Boolean value `true` if all qubits in a register of type `Qubit[]` are in the state zero, when measured in a specified Pauli basis and `false` otherwise.</span></span> 

```qsharp
operation AllMeasurementsZero (qs : Qubit[], pauli : Pauli) : Bool {

    mutable value = true;
    for (q in qs) {
        if ( Measure([pauli], [q]) == One ) {
            set value = false;
        }
    }
    return value;
}
```

<span data-ttu-id="1fbd2-127">Il linguaggio Q # consente le dipendenze del flusso di controllo classico sui risultati di misurazione di qubits.</span><span class="sxs-lookup"><span data-stu-id="1fbd2-127">The Q# language allows dependencies of classical control flow on measurement results of qubits.</span></span> <span data-ttu-id="1fbd2-128">Questo consente a sua volta di implementare potenti gadget probabilistici che possono ridurre il costo computazionale per l'implementazione di unitaries.</span><span class="sxs-lookup"><span data-stu-id="1fbd2-128">This in turn enables to implement powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span> <span data-ttu-id="1fbd2-129">Ad esempio, è facile implementare la cosiddetta *ripetizione fino al successo* in Q #, ovvero circuiti probabilistici che hanno un costo basso *previsto* in termini di controllo elementare, ma per il quale il costo effettivo dipende da un'esecuzione effettiva e da un vero e proprio interfoliazione di diversi rami possibili.</span><span class="sxs-lookup"><span data-stu-id="1fbd2-129">As an example, it is easy to implement so-called *Repeat-Until-Success* in Q# which are probabilistic circuits that have an *expected* low cost in terms of elementary gates, but for which the true cost depends on an actual run and an actual interleaving of various possible branchings.</span></span> 

<span data-ttu-id="1fbd2-130">Per semplificare i modelli di ripetizione fino alla riuscita (UR), Q # supporta il costrutto</span><span class="sxs-lookup"><span data-stu-id="1fbd2-130">To facilitate Repeat-Until-Success (RUS) patterns, Q# supports the construct</span></span>
```qsharp
repeat {
    statementBlock1 
}
until (expression)
fixup {
    statementBlock2
}
```
<span data-ttu-id="1fbd2-131">dove `statementBlock1` e `statementBlock2` sono zero o più istruzioni Q # e `expression` qualsiasi espressione valida che restituisca un valore di tipo `Bool`.</span><span class="sxs-lookup"><span data-stu-id="1fbd2-131">where `statementBlock1` and `statementBlock2` are zero or more Q# statements, and `expression` any valid expression that evaluates to a value of type `Bool`.</span></span> <span data-ttu-id="1fbd2-132">In un caso di utilizzo tipico, il circuito seguente implementa una rotazione intorno a un asse irrazionale di $ (I + 2i Z)/\sqrt{5}$ nella sfera Bloch.</span><span class="sxs-lookup"><span data-stu-id="1fbd2-132">In a typical use case, the following circuit implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="1fbd2-133">Questa operazione viene eseguita usando un modello di ur noto:</span><span class="sxs-lookup"><span data-stu-id="1fbd2-133">This is accomplished by using a known RUS pattern:</span></span> 

```qsharp
operation RUScircuit (qubit : Qubit) : Unit {

    using(ancillas = Qubit[2]) {
        ApplyToEachA(H, ancillas);
        mutable finished = false;
        repeat {
            Controlled X(ancillas, qubit);
            S(qubit);
            Controlled X(ancillas, qubit);
            Z(qubit);
        }
        until(finished)
        fixup {
            if AllMeasurementsZero(ancillas, Xpauli) {
                set finished = true;
            }
        }
    }
}
```

<span data-ttu-id="1fbd2-134">Questo esempio illustra l'uso di una variabile modificabile `finished` che rientra nell'ambito dell'intero ciclo di ripetizione fino alla correzione e che viene inizializzato prima del ciclo e aggiornato nel passaggio di correzione.</span><span class="sxs-lookup"><span data-stu-id="1fbd2-134">This example shows the use of a mutable variable `finished` which is in scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

<span data-ttu-id="1fbd2-135">Infine, viene illustrato un esempio di modello ur per preparare uno stato quantico $ \frac{1}{\sqrt{3}} \left (\sqrt{2}\ket{0}+ \ket{1}\right) $, a partire dallo stato $ \ket{+} $.</span><span class="sxs-lookup"><span data-stu-id="1fbd2-135">Finally, we show an example of a RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span> <span data-ttu-id="1fbd2-136">Vedere anche l' [esempio di unit test fornito con la libreria standard](https://github.com/Microsoft/Quantum/blob/master/Samples/src/UnitTesting/RepeatUntilSuccessCircuits.qs):</span><span class="sxs-lookup"><span data-stu-id="1fbd2-136">See also the [unit testing sample provided with the standard library](https://github.com/Microsoft/Quantum/blob/master/Samples/src/UnitTesting/RepeatUntilSuccessCircuits.qs):</span></span> 

```qsharp
operation RepeatUntilSuccessStatePreparation( target : Qubit ) : Unit {

    using( ancilla = Qubit() ) {
        H(ancilla);
        repeat {
            // We expect target and ancilla qubit to be in |+⟩ state.
            AssertProb( 
                [PauliX], [target], Zero, 1.0, 
                "target qubit should be in the |+⟩ state", 1e-10 );
            AssertProb( 
                [PauliX], [ancilla], Zero, 1.0,
                "ancilla qubit should be in the |+⟩ state", 1e-10 );
                
            Adjoint T(ancilla);
            CNOT(target, ancilla);
            T(ancilla);

            // The probability of measuring |+⟩ state on ancilla is 3/4.
            AssertProb( 
                [PauliX], [ancilla], Zero, 3. / 4., 
                "Error: the probability to measure |+⟩ in the first 
                ancilla must be 3/4",
                1e-10);

            // If we get measurement outcome Zero, we prepare the required state 
            let outcome = Measure([PauliX], [ancilla]);
        }
        until( outcome == Zero )
        fixup {
            // Bring ancilla and target back to |+⟩ state
            if( outcome == One ) {
                Z(ancilla);
                X(target);
                H(target);
            }
        }
        // Return ancilla back to Zero state
        H(ancilla);
    }
}
```
 
<span data-ttu-id="1fbd2-137">Le caratteristiche programmatiche più importanti illustrate in questa operazione sono un `fixup` più complesso del ciclo che prevede operazioni Quantum e l'uso di istruzioni `AssertProb` per verificare la probabilità di misurare lo stato del quantum in determinati punti specificati nel programma.</span><span class="sxs-lookup"><span data-stu-id="1fbd2-137">Notable programmatic features shown in this operation are a more complex `fixup` part of the loop which involves quantum operations, and the use of `AssertProb` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span> <span data-ttu-id="1fbd2-138">Per ulteriori informazioni sulle istruzioni `Assert` e `AssertProb`, vedere anche [test e debug](xref:microsoft.quantum.techniques.testing-and-debugging) .</span><span class="sxs-lookup"><span data-stu-id="1fbd2-138">See also [Testing and debugging](xref:microsoft.quantum.techniques.testing-and-debugging) for more information about `Assert` and `AssertProb` statements.</span></span> 
