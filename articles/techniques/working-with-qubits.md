---
title: Uso di qubits
description: 'Uso delle tecniche qubits-Q #'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.qubits
ms.openlocfilehash: dc6db93dadc37534aece9624fe516125d919f8cd
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76819995"
---
# <a name="working-with-qubits"></a><span data-ttu-id="f3995-103">Uso di qubits</span><span class="sxs-lookup"><span data-stu-id="f3995-103">Working with Qubits</span></span>

<span data-ttu-id="f3995-104">Avendo visto una serie di diverse parti del linguaggio Q #, è possibile passare al suo interno e vedere come usare qubits.</span><span class="sxs-lookup"><span data-stu-id="f3995-104">Having now seen a variety of different parts of the Q# language, let us get into the thick of it and see how to use qubits themselves.</span></span>

## <a name="allocating-qubits"></a><span data-ttu-id="f3995-105">Allocazione di qubits</span><span class="sxs-lookup"><span data-stu-id="f3995-105">Allocating Qubits</span></span>

<span data-ttu-id="f3995-106">Per prima cosa, per ottenere un qubit che è possibile usare in Q #, viene *allocato* qubits in un blocco `using`:</span><span class="sxs-lookup"><span data-stu-id="f3995-106">First, to obtain a qubit that we can use in Q#, we *allocate* qubits within a `using` block:</span></span>

```qsharp
using (register = Qubit[5]) {
    // Do stuff...
}
```

<span data-ttu-id="f3995-107">Tutti i qubits allocati in questo modo iniziano con lo stato $ \ket{0}$; Nell'esempio precedente `register` si trova quindi nello stato $ \ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="f3995-107">Any qubits allocated in this way start off in the $\ket{0}$ state; in the example above, `register` is thus in the state $\ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span></span>
<span data-ttu-id="f3995-108">Alla fine del blocco `using`, qualsiasi qubits allocato da tale blocco viene immediatamente deallocato e non può essere usato ulteriormente.</span><span class="sxs-lookup"><span data-stu-id="f3995-108">At the end of the `using` block, any qubits allocated by that block are immediately deallocated and cannot be used further.</span></span>

> [!WARNING]
> <span data-ttu-id="f3995-109">I computer di destinazione si aspettano che qubits si trovino nello stato $ \ket{0}$ immediatamente prima della deallocazione, in modo che possano essere riutilizzati e offerti ad altri blocchi `using` per l'allocazione.</span><span class="sxs-lookup"><span data-stu-id="f3995-109">Target machines expect that qubits are in the $\ket{0}$ state immediately before deallocation, so that they can be reused and offered to other `using` blocks for allocation.</span></span>
> <span data-ttu-id="f3995-110">Quando possibile, usare le operazioni unitarie per restituire i qubits allocati a $ \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="f3995-110">Whenever possible, use unitary operations to return any allocated qubits to $\ket{0}$.</span></span>
> <span data-ttu-id="f3995-111">Se necessario, è possibile utilizzare l'operazione @"microsoft.quantum.intrinsic.reset" per misurare un qubit e utilizzare tale risultato per garantire che il valore di qubit misurato venga restituito a $ \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="f3995-111">If need be, the @"microsoft.quantum.intrinsic.reset" operation can be used to measure a qubit instead, and to use that measurement result to ensure that the measured qubit is returned to $\ket{0}$.</span></span> <span data-ttu-id="f3995-112">Una misura di questo tipo eliminerà eventuali problemi con i restanti qubits e può quindi influisca sul calcolo.</span><span class="sxs-lookup"><span data-stu-id="f3995-112">Such a measurement will destroy any entanglement with the remaining qubits and can thus impact the computation.</span></span>

## <a name="intrinsic-operations"></a><span data-ttu-id="f3995-113">Operazioni intrinseche</span><span class="sxs-lookup"><span data-stu-id="f3995-113">Intrinsic Operations</span></span>

<span data-ttu-id="f3995-114">Una volta allocato, un qubit può quindi essere passato a funzioni e operazioni.</span><span class="sxs-lookup"><span data-stu-id="f3995-114">Once allocated, a qubit can then be passed to functions and operations.</span></span>
<span data-ttu-id="f3995-115">In un certo senso, questo è tutto ciò che può fare un programma Q # con un qubit, in quanto le azioni che è possibile eseguire sono tutte definite come operazioni.</span><span class="sxs-lookup"><span data-stu-id="f3995-115">In some sense, this is all that a Q# program can do with a qubit, as the actions that can be taken are all defined as operations.</span></span>
<span data-ttu-id="f3995-116">Queste operazioni verranno visualizzate in modo più dettagliato nelle [operazioni e funzioni intrinseche](xref:microsoft.quantum.libraries.standard.prelude), ma per il momento si menzioneranno alcune operazioni utili che possono essere usate per interagire con qubits.</span><span class="sxs-lookup"><span data-stu-id="f3995-116">We will see these operations in more detail in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), but for now, we mention a few useful operations that can be used to interact with qubits.</span></span>

<span data-ttu-id="f3995-117">In primo luogo, gli operatori di Pauli Single-qubit $X $, $Y $ e $Z $ sono rappresentati in Q # dalle operazioni intrinseche `X`, `Y`e `Z`, ognuno dei quali ha un tipo `(Qubit => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="f3995-117">First, the single-qubit Pauli operators $X$, $Y$, and $Z$ are represented in Q# by the intrinsic operations `X`, `Y`, and `Z`, each of which has type `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="f3995-118">Come descritto in [operazioni e funzioni intrinseche](xref:microsoft.quantum.libraries.standard.prelude), è possibile pensare a $X $ e quindi di `X` come operazione di capovolgimento di bit o non di controllo.</span><span class="sxs-lookup"><span data-stu-id="f3995-118">As described in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), we can think of $X$ and hence of `X` as a bit-flip operation or NOT gate.</span></span>
<span data-ttu-id="f3995-119">L'operazione di `X` consente di preparare gli Stati nel formato $ \ket{s_0 s_1 \dots s_n} $ per una stringa di bit classica $s $:</span><span class="sxs-lookup"><span data-stu-id="f3995-119">The `X` operation lets us prepare states of the form $\ket{s_0 s_1 \dots s_n}$ for some classical bit string $s$:</span></span>

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

operation RunExample() : Unit {
    using (register = Qubit[8]) {
        PrepareBitString(
            [true, true, false, false, true, false, false, true],
            register
        );
        // At this point, register now has the state |11001001〉.
        // Resetting the qubits will allow us to deallocate them properly.
        ResetAll(register);
    }
}
```

> [!TIP]
> <span data-ttu-id="f3995-120">In un secondo momento, verrà illustrato come scrivere questa operazione in modo più compatto che non richiede il controllo di flusso manuale.</span><span class="sxs-lookup"><span data-stu-id="f3995-120">Later, we will see more compact ways of writing this operation that do not require manual flow control.</span></span>

<span data-ttu-id="f3995-121">È inoltre possibile preparare gli Stati, ad esempio $ \ket{+} = \left (\ket{0} + \ket{1}\right)/\sqrt{2}$ e $ \ket{-} = \left (\ket{0}-\ket{1}\right)/\sqrt{2}$ utilizzando la trasformazione Hadamard $H $, che è rappresentata in Q # dall'operazione intrinseca `H : (Qubit => Unit is Adj + Ctl)`:</span><span class="sxs-lookup"><span data-stu-id="f3995-121">We can also prepare states such as $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ and $\ket{-} = \left(\ket{0} - \ket{1}\right) / \sqrt{2}$ by using the Hadamard transform $H$, which is represented in Q# by the intrinsic operation `H : (Qubit => Unit is Adj + Ctl)`:</span></span>

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

## <a name="measurements"></a><span data-ttu-id="f3995-122">Misurazioni</span><span class="sxs-lookup"><span data-stu-id="f3995-122">Measurements</span></span>

<span data-ttu-id="f3995-123">Utilizzando l'operazione di `Measure`, che è un'operazione intrinseca non unitaria incorporata, è possibile estrarre le informazioni classiche da un oggetto di tipo `Qubit` e assegnare un valore classico come risultato, che ha un tipo riservato `Result`, a indicare che il risultato non è più uno stato quantum.</span><span class="sxs-lookup"><span data-stu-id="f3995-123">Using the `Measure` operation, which is a built-in intrinsic non-unitary operation, we can extract classical information from an object of type `Qubit` and assign a classical value as a result, which has a reserved type `Result`, indicating that the result is no longer a quantum state.</span></span>
<span data-ttu-id="f3995-124">L'input per `Measure` è un asse di Pauli nella sfera Bloch, rappresentato da un valore di tipo `Pauli` (ad esempio `PauliX`) e un valore di tipo `Qubit`.</span><span class="sxs-lookup"><span data-stu-id="f3995-124">The input to `Measure` is a Pauli axis on the Bloch sphere, represented by a value of type `Pauli` (for instance `PauliX`) and an value of type `Qubit`.</span></span>

<span data-ttu-id="f3995-125">Un esempio semplice è l'operazione seguente, che alloca un qubit nello stato $ \ket{0}$, quindi applica un'operazione Hadamard `H` e misura il risultato nella `PauliZ` base.</span><span class="sxs-lookup"><span data-stu-id="f3995-125">A simple example is the following operation, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

```qsharp
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

<span data-ttu-id="f3995-126">Un esempio leggermente più complesso viene fornito dalla seguente operazione, che restituisce il valore booleano `true` se tutti i qubits in un registro di tipo `Qubit[]` sono nello stato zero se misurato in base a Pauli specificato e che restituisce `false` in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="f3995-126">A slightly more complicated example is given by the following operation, which returns the Boolean value `true` if all qubits in a register of type `Qubit[]` are in the state zero when measured in a specified Pauli basis, and which returns `false` otherwise.</span></span>

```qsharp
operation MeasureIfAllQubitsAreZero(qubits : Qubit[], pauli : Pauli) : Bool {
    mutable value = true;
    for (qubit in qubits) {
        if (Measure([pauli], [qubit]) == One) {
            set value = false;
        }
    }
    return value;
}
```

<span data-ttu-id="f3995-127">Il linguaggio Q # consente a un flusso di controllo classico di dipendere dai risultati della misurazione di qubits.</span><span class="sxs-lookup"><span data-stu-id="f3995-127">The Q# language allows classical control flow to depend on the results of measuring qubits.</span></span>
<span data-ttu-id="f3995-128">Questa funzionalità consente, a sua volta, di implementare potenti gadget probabilistici che possono ridurre il costo computazionale per l'implementazione di unitaries.</span><span class="sxs-lookup"><span data-stu-id="f3995-128">This capability in turn enables implementing powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span>
<span data-ttu-id="f3995-129">Ad esempio, è facile implementare i cosiddetti modelli di *ripetizione fino al successo* (UR) in Q #.</span><span class="sxs-lookup"><span data-stu-id="f3995-129">As an example, it is easy to implement so-called *Repeat-Until-Success* (RUS) patterns in Q#.</span></span>
<span data-ttu-id="f3995-130">Questi modelli di ur sono programmi probabilistici che hanno un basso costo *previsto* in termini di attività di controllo elementari, ma per il quale il costo effettivo dipende da un'esecuzione effettiva e da un effettivo interfoliazione delle diverse branche possibili.</span><span class="sxs-lookup"><span data-stu-id="f3995-130">These RUS patterns are probabilistic programs that have an *expected* low cost in terms of elementary gates, but for which the true cost depends on an actual run and an actual interleaving of various possible branchings.</span></span>

<span data-ttu-id="f3995-131">Per semplificare i modelli di ripetizione fino alla riuscita (UR), Q # supporta il costrutto</span><span class="sxs-lookup"><span data-stu-id="f3995-131">To facilitate Repeat-Until-Success (RUS) patterns, Q# supports the construct</span></span>

```qsharp
repeat {
    statementBlock1
}
until (expression)
fixup {
    statementBlock2
}
```

<span data-ttu-id="f3995-132">dove `statementBlock1` e `statementBlock2` sono zero o più istruzioni Q # e `expression` qualsiasi espressione valida che restituisca un valore di tipo `Bool`.</span><span class="sxs-lookup"><span data-stu-id="f3995-132">where `statementBlock1` and `statementBlock2` are zero or more Q# statements, and `expression` any valid expression that evaluates to a value of type `Bool`.</span></span>
<span data-ttu-id="f3995-133">In un caso di utilizzo tipico, l'operazione Q # seguente implementa una rotazione intorno a un asse irrazionale di $ (I + 2i Z)/\sqrt{5}$ nella sfera Bloch.</span><span class="sxs-lookup"><span data-stu-id="f3995-133">In a typical use case, the following Q# operation implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="f3995-134">Questa operazione viene eseguita usando un modello di ur noto:</span><span class="sxs-lookup"><span data-stu-id="f3995-134">This is accomplished by using a known RUS pattern:</span></span>

```qsharp
operation ApplyVRotationUsingRUS(qubit : Qubit) : Unit {
    using (controls = Qubit[2]) {
        ApplyToEachA(H, controls);
        mutable finished = false;
        repeat {
            Controlled X(controls, qubit);
            S(qubit);
            Controlled X(controls, qubit);
            Z(qubit);
        }
        until (finished)
        fixup {
            if (MeasureIfAllQubitsAreZero(controls, PauliX)) {
                set finished = true;
            }
        }
    }
}
```

<span data-ttu-id="f3995-135">Questo esempio illustra l'uso di una variabile modificabile `finished` che rientra nell'ambito dell'intero ciclo di ripetizione fino alla correzione e che viene inizializzato prima del ciclo e aggiornato nel passaggio di correzione.</span><span class="sxs-lookup"><span data-stu-id="f3995-135">This example shows the use of a mutable variable `finished` which is in scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

<span data-ttu-id="f3995-136">Infine, viene illustrato un esempio di modello ur per preparare uno stato quantico $ \frac{1}{\sqrt{3}} \left (\sqrt{2}\ket{0}+ \ket{1}\right) $, a partire dallo stato $ \ket{+} $.</span><span class="sxs-lookup"><span data-stu-id="f3995-136">Finally, we show an example of a RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span>
<span data-ttu-id="f3995-137">Vedere anche l' [esempio di unit test fornito con la libreria standard](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span><span class="sxs-lookup"><span data-stu-id="f3995-137">See also the [unit testing sample provided with the standard library](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span></span>

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+⟩ state.
            AssertProb(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+⟩ state", 1e-10 );
            AssertProb(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+⟩ state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+⟩ state on the auxiliary qubit
            // is 3/4.
            AssertProb(
                [PauliX], [auxiliary], Zero, 3. / 4.,
                "Error: the probability to measure |+⟩ in the first
                auxiliary must be 3/4",
                1e-10);

            // If we get the measurement outcome Zero, we prepare the
            // required state.
            let outcome = Measure([PauliX], [auxiliary]);
        }
        until (outcome == Zero)
        fixup {
            // Bring the auxiliary and target qubits back to |+⟩ state.
            if (outcome == One) {
                Z(auxiliary);
                X(target);
                H(target);
            }
        }
        // Return the auxiliary qubit back to the Zero state.
        H(auxiliary);
    }
}
```

<span data-ttu-id="f3995-138">Le caratteristiche programmatiche più importanti illustrate in questa operazione sono un `fixup` più complesso del ciclo, che implica operazioni Quantum e l'utilizzo di istruzioni `AssertProb` per verificare la probabilità di misurare lo stato del quantum in determinati punti specificati del programma.</span><span class="sxs-lookup"><span data-stu-id="f3995-138">Notable programmatic features shown in this operation are a more complex `fixup` part of the loop, which involves quantum operations, and the use of `AssertProb` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span>
<span data-ttu-id="f3995-139">Per ulteriori informazioni sulle operazioni di [`Assert`](xref:microsoft.quantum.intrinsic.assert) e [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) , vedere anche [test e debug](xref:microsoft.quantum.techniques.testing-and-debugging) .</span><span class="sxs-lookup"><span data-stu-id="f3995-139">See also [Testing and debugging](xref:microsoft.quantum.techniques.testing-and-debugging) for more information about the [`Assert`](xref:microsoft.quantum.intrinsic.assert) and [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) operations.</span></span>
