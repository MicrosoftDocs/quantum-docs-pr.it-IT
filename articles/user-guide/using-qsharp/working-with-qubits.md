---
title: Uso dei qubit
description: Descrizione riempimento
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
ms.openlocfilehash: 1655d18ab9d8638ad356e6fb90994b5c1fd76a25
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2020
ms.locfileid: "85885300"
---
# <a name="working-with-qubits"></a><span data-ttu-id="29e0b-103">Uso dei qubit</span><span class="sxs-lookup"><span data-stu-id="29e0b-103">Working with qubits</span></span>

<span data-ttu-id="29e0b-104">Qubits sono l'oggetto fondamentale delle informazioni in quantum computing.</span><span class="sxs-lookup"><span data-stu-id="29e0b-104">Qubits are the fundamental object of information in quantum computing.</span></span> <span data-ttu-id="29e0b-105">Per un'introduzione generale a qubits, vedere [informazioni sul quantum computing](xref:microsoft.quantum.overview.understanding)e approfondimento sulla relativa rappresentazione matematica, vedere [qubit](xref:microsoft.quantum.concepts.qubit).</span><span class="sxs-lookup"><span data-stu-id="29e0b-105">For a general introduction to qubits, see [Understanding quantum computing](xref:microsoft.quantum.overview.understanding), and to dive deeper into their mathematical representation, see [The Qubit](xref:microsoft.quantum.concepts.qubit).</span></span> 

<span data-ttu-id="29e0b-106">Questo articolo illustra come usare e usare qubits in un programma Q #.</span><span class="sxs-lookup"><span data-stu-id="29e0b-106">This article explores how to use and work with qubits in a Q# program.</span></span> 

> [!IMPORTANT]
><span data-ttu-id="29e0b-107">Nessuna delle istruzioni descritte in questo articolo è valida all'interno del corpo di una funzione.</span><span class="sxs-lookup"><span data-stu-id="29e0b-107">None of the statements discussed in this article are valid within the body of a function.</span></span> <span data-ttu-id="29e0b-108">Sono valide solo all'interno delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="29e0b-108">They are only valid within operations.</span></span>

## <a name="allocating-qubits"></a><span data-ttu-id="29e0b-109">Allocazione di qubits</span><span class="sxs-lookup"><span data-stu-id="29e0b-109">Allocating Qubits</span></span>

<span data-ttu-id="29e0b-110">Poiché i qubits fisici rappresentano una risorsa preziosa in un computer Quantum, parte del processo del compilatore consiste nel verificare che vengano usati nel modo più efficiente possibile.</span><span class="sxs-lookup"><span data-stu-id="29e0b-110">Because physical qubits are a precious resource in a quantum computer, part of the compiler's job is to make sure they are being used as efficiently as possible.</span></span>
<span data-ttu-id="29e0b-111">Di conseguenza, è necessario indicare a Q # di *allocare* qubits per l'uso in un blocco di istruzioni specifico.</span><span class="sxs-lookup"><span data-stu-id="29e0b-111">As such, you need to tell Q# to *allocate* qubits for use within a particular statement block.</span></span>
<span data-ttu-id="29e0b-112">È possibile allocare qubits come singolo qubit o come matrice di qubits, noto come *Registro*.</span><span class="sxs-lookup"><span data-stu-id="29e0b-112">You can allocate qubits as a single qubit, or as an array of qubits, known as a *register*.</span></span> 

### <a name="clean-qubits"></a><span data-ttu-id="29e0b-113">Pulisci qubits</span><span class="sxs-lookup"><span data-stu-id="29e0b-113">Clean qubits</span></span>

<span data-ttu-id="29e0b-114">Utilizzare l' `using` istruzione per allocare nuovi qubits da utilizzare durante un blocco di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="29e0b-114">Use the `using` statement to allocate new qubits for use during a statement block.</span></span>

<span data-ttu-id="29e0b-115">L'istruzione è costituita dalla parola chiave `using` , seguita da un'associazione racchiusa tra parentesi `( )` e dal blocco di istruzioni all'interno del quale sono disponibili i qubits.</span><span class="sxs-lookup"><span data-stu-id="29e0b-115">The statement consists of the keyword `using`, followed by a binding enclosed in parentheses `( )` and the statement block within which the qubits are available.</span></span>
<span data-ttu-id="29e0b-116">Il binding segue lo stesso modello delle `let` istruzioni, ovvero un singolo simbolo o una tupla di simboli, seguito da un segno di uguale `=` e da un singolo valore o da una tupla corrispondente di *inizializzatori*.</span><span class="sxs-lookup"><span data-stu-id="29e0b-116">The binding follows the same pattern as `let` statements: either a single symbol or a tuple of symbols, followed by an equals sign `=`, and either a single value or a matching tuple of *initializers*.</span></span>

<span data-ttu-id="29e0b-117">Gli inizializzatori sono disponibili per un singolo qubit, indicato come `Qubit()` o una matrice di qubits, `Qubit[n]` , dove `n` è un' `Int` espressione.</span><span class="sxs-lookup"><span data-stu-id="29e0b-117">Initializers are available either for a single qubit, indicated as `Qubit()`, or an array of qubits, `Qubit[n]`, where `n` is an `Int` expression.</span></span>
<span data-ttu-id="29e0b-118">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="29e0b-118">For example,</span></span>

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```

<span data-ttu-id="29e0b-119">Tutti i qubits allocati in questo modo iniziano con lo stato $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="29e0b-119">Any qubits allocated in this way start off in the $\ket{0}$ state.</span></span> <span data-ttu-id="29e0b-120">Nell'esempio precedente, quindi, `auxiliary` è un singolo qubit nello stato $ \ket {0} $ e `register` si trova nello stato Five-qubit $ \ket {00000} = \ket \otimes {0} {0} \ket \otimes \cdots \otimes \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="29e0b-120">Thus in the previous example, `auxiliary` is a single qubit in the state $\ket{0}$, and `register` is in the five-qubit state $\ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span></span>
<span data-ttu-id="29e0b-121">Alla fine del `using` blocco, qualsiasi qubits allocato dal blocco viene immediatamente deallocato e non può essere usato ulteriormente.</span><span class="sxs-lookup"><span data-stu-id="29e0b-121">At the end of the `using` block, any qubits allocated by that block are immediately deallocated and cannot be used further.</span></span>

> [!WARNING]
> <span data-ttu-id="29e0b-122">I computer di destinazione possono riutilizzare qubits deallocati e offrirli ad altri `using` blocchi per l'allocazione.</span><span class="sxs-lookup"><span data-stu-id="29e0b-122">Target machines can reuse deallocated qubits and offer them to other `using` blocks for allocation.</span></span> <span data-ttu-id="29e0b-123">Di conseguenza, il computer di destinazione prevede che qubits si trovino nello stato $ \ket {0} $ immediatamente prima della deallocazione.</span><span class="sxs-lookup"><span data-stu-id="29e0b-123">As such, the target machine expects that qubits are in the $\ket{0}$ state immediately before deallocation.</span></span>
> <span data-ttu-id="29e0b-124">Quando possibile, usare le operazioni unitarie per restituire qualsiasi qubits allocato a $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="29e0b-124">Whenever possible, use unitary operations to return any allocated qubits to $\ket{0}$.</span></span>
> <span data-ttu-id="29e0b-125">Se necessario, è possibile usare l' @"microsoft.quantum.intrinsic.reset" operazione, che restituisce il valore di qubit a $ \ket {0} $ misurando ed eseguendo in modo condizionale un'operazione in base al risultato.</span><span class="sxs-lookup"><span data-stu-id="29e0b-125">If need be, you can use the @"microsoft.quantum.intrinsic.reset" operation, which returns the qubit to $\ket{0}$ by measuring it and conditionally performing an operation based on the result.</span></span> <span data-ttu-id="29e0b-126">Tale misurazione elimina qualsiasi groviglio con i restanti qubits e può quindi influisca sul calcolo.</span><span class="sxs-lookup"><span data-stu-id="29e0b-126">Such a measurement destroys any entanglement with the remaining qubits and can thus impact the computation.</span></span>


### <a name="borrowed-qubits"></a><span data-ttu-id="29e0b-127">Qubits preso in prestito</span><span class="sxs-lookup"><span data-stu-id="29e0b-127">Borrowed Qubits</span></span>

<span data-ttu-id="29e0b-128">Usare l' `borrowing` istruzione per allocare qubits per l'uso temporaneo, che non devono essere in uno stato specifico.</span><span class="sxs-lookup"><span data-stu-id="29e0b-128">Use the `borrowing` statement to allocate qubits for temporary use, which do not need to be in a specific state.</span></span>

<span data-ttu-id="29e0b-129">Durante un calcolo, è possibile usare qubits in prestito come spazio scratch.</span><span class="sxs-lookup"><span data-stu-id="29e0b-129">You can use borrowed qubits as scratch space during a computation.</span></span>
<span data-ttu-id="29e0b-130">Questi qubits in genere non sono in uno stato pulito, ovvero non vengono necessariamente inizializzati in uno stato noto, ad esempio $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="29e0b-130">These qubits are generally not in a clean state, that is, they are not necessarily initialized in a known state such as $\ket{0}$.</span></span>
<span data-ttu-id="29e0b-131">Queste sono spesso denominate qubits "Dirty" perché il loro stato è sconosciuto e può anche essere aggrovigliato con altre parti della memoria del computer Quantum.</span><span class="sxs-lookup"><span data-stu-id="29e0b-131">These are often referred to as "dirty" qubits because their state is unknown and can even be entangled with other parts of the quantum computer's memory.</span></span>

<span data-ttu-id="29e0b-132">L'associazione segue lo stesso modello e le stesse regole dell' `using` istruzione.</span><span class="sxs-lookup"><span data-stu-id="29e0b-132">The binding follows the same pattern and rules as the `using` statement.</span></span>
<span data-ttu-id="29e0b-133">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="29e0b-133">For example,</span></span>
```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```
<span data-ttu-id="29e0b-134">I qubits presi in prestito sono in uno stato sconosciuto e non rientrano nell'ambito alla fine del blocco di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="29e0b-134">The borrowed qubits are in an unknown state and go out of scope at the end of the statement block.</span></span>
<span data-ttu-id="29e0b-135">Il mutuatario si impegna a lasciare il qubits nello stesso stato in cui si trovava al momento del prestito; ovvero, il loro stato all'inizio e alla fine del blocco di istruzioni deve essere lo stesso.</span><span class="sxs-lookup"><span data-stu-id="29e0b-135">The borrower commits to leaving the qubits in the same state they were in when they borrowed them; that is, their state at the beginning and the end of the statement block should be the same.</span></span>
<span data-ttu-id="29e0b-136">Poiché questo stato non è necessariamente uno stato classico, nella maggior parte dei casi gli ambiti in prestito non devono contenere misurazioni.</span><span class="sxs-lookup"><span data-stu-id="29e0b-136">Because this state is not necessarily a classical state, in most cases borrowing scopes should not contain measurements.</span></span> 

<span data-ttu-id="29e0b-137">Quando si prende in prestito qubits, il sistema tenta innanzitutto di compilare la richiesta da qubits in uso, ma non è possibile accedervi durante il corpo dell' `borrowing` istruzione.</span><span class="sxs-lookup"><span data-stu-id="29e0b-137">When borrowing qubits, the system first tries to fill the request from qubits that are in use but not accessed during the body of the `borrowing` statement.</span></span>
<span data-ttu-id="29e0b-138">Se il qubits non è sufficiente, viene allocato il nuovo qubits per completare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="29e0b-138">If there aren't enough such qubits, then it allocates new qubits to complete the request.</span></span>

<span data-ttu-id="29e0b-139">Tra i casi d'uso noti dei qubits Dirty sono implementazioni di controlli CNOT multicontrollati che richiedono solo pochi qubits e implementazioni di incrementatori.</span><span class="sxs-lookup"><span data-stu-id="29e0b-139">Among the known use cases of dirty qubits are implementations of multi-controlled CNOT gates that require only very few qubits and implementation of incrementers.</span></span>
<span data-ttu-id="29e0b-140">Per un esempio di uso in Q #, vedere l' [esempio relativo a borrowing qubits](#borrowing-qubits-example) in questo articolo o il [*factoring della carta che usa 2n + 2 qubits con moltiplicazione modulare basata su Toffoli*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler e Svore 2017) per un algoritmo che usa qubits in prestito.</span><span class="sxs-lookup"><span data-stu-id="29e0b-140">For an example of their use in Q#, see [Borrowing Qubits Example](#borrowing-qubits-example) in this article, or the paper [*Factoring using 2n+2 qubits with Toffoli based modular multiplication*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler, and Svore 2017) for an algorithm which utilizes borrowed qubits.</span></span>

## <a name="intrinsic-operations"></a><span data-ttu-id="29e0b-141">Operazioni intrinseche</span><span class="sxs-lookup"><span data-stu-id="29e0b-141">Intrinsic Operations</span></span>

<span data-ttu-id="29e0b-142">Una volta allocato, è possibile passare un qubit a funzioni e operazioni.</span><span class="sxs-lookup"><span data-stu-id="29e0b-142">Once allocated, you can pass a qubit to functions and operations.</span></span>
<span data-ttu-id="29e0b-143">In un certo senso, questo è tutto ciò che può fare un programma Q # con un qubit, in quanto le azioni che è possibile eseguire sono tutte definite come operazioni.</span><span class="sxs-lookup"><span data-stu-id="29e0b-143">In some sense, this is all that a Q# program can do with a qubit, as the actions that can be taken are all defined as operations.</span></span>

<span data-ttu-id="29e0b-144">Questo articolo illustra alcune utili operazioni Q # che è possibile usare per interagire con qubits.</span><span class="sxs-lookup"><span data-stu-id="29e0b-144">This article discusses a few useful Q# operations that you can use to interact with qubits.</span></span>
<span data-ttu-id="29e0b-145">Per informazioni più dettagliate su queste e altre, vedere [operazioni e funzioni intrinseche](xref:microsoft.quantum.libraries.standard.prelude).</span><span class="sxs-lookup"><span data-stu-id="29e0b-145">For more detail about these and others, see [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude).</span></span> 

<span data-ttu-id="29e0b-146">In primo luogo, gli operatori di Pauli Single-qubit $X $, $Y $ e $Z $ sono rappresentati in Q # dalle operazioni intrinseche [`X`](xref:microsoft.quantum.intrinsic.x) , [`Y`](xref:microsoft.quantum.intrinsic.y) e [`Z`](xref:microsoft.quantum.intrinsic.z) , ognuno dei quali è di tipo `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="29e0b-146">First, the single-qubit Pauli operators $X$, $Y$, and $Z$ are represented in Q# by the intrinsic operations [`X`](xref:microsoft.quantum.intrinsic.x), [`Y`](xref:microsoft.quantum.intrinsic.y), and [`Z`](xref:microsoft.quantum.intrinsic.z), each of which has type `(Qubit => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="29e0b-147">Come descritto in [operazioni e funzioni intrinseche](xref:microsoft.quantum.libraries.standard.prelude), si pensi a $X $ e quindi a `X` un'operazione di capovolgimento di bit o non di controllo.</span><span class="sxs-lookup"><span data-stu-id="29e0b-147">As described in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), think of $X$ and hence of `X` as a bit-flip operation or NOT gate.</span></span>
<span data-ttu-id="29e0b-148">È possibile usare l' `X` operazione per preparare gli Stati nel formato $ \ket{s_0 s_1 \dots S_n} $ per una stringa di bit classica $s $:</span><span class="sxs-lookup"><span data-stu-id="29e0b-148">You can use the `X` operation to prepare states of the form $\ket{s_0 s_1 \dots s_n}$ for some classical bit string $s$:</span></span>

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
        // Remember to reset the qubits before deallocation:
        ResetAll(register);
    }
}
```

> [!TIP]
> <span data-ttu-id="29e0b-149">In un secondo momento, verrà illustrato come scrivere questa operazione in modo più compatto che non richiede un flusso di controllo manuale.</span><span class="sxs-lookup"><span data-stu-id="29e0b-149">Later, you will see more compact ways of writing this operation that do not require manual control flow.</span></span>

<span data-ttu-id="29e0b-150">È inoltre possibile preparare Stati quali $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ e $ \ket {-} = \left (\ket {0} -\ket {1} \right)/\sqrt $ utilizzando {2} la trasformazione Hadamard $H $, che è rappresentata in Q # dall'operazione intrinseca [`H`](xref:microsoft.quantum.intrinsic.h) (anche di tipo (qubit => unità è ADJ + CTL)'):</span><span class="sxs-lookup"><span data-stu-id="29e0b-150">You can also prepare states such as $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ and $\ket{-} = \left(\ket{0} - \ket{1}\right) / \sqrt{2}$ by using the Hadamard transform $H$, which is represented in Q# by the intrinsic operation [`H`](xref:microsoft.quantum.intrinsic.h) (also of type (Qubit => Unit is Adj + Ctl)\`):</span></span>

```qsharp
operation PreparePlusMinusState(bitstring : Bool[], register : Qubit[]) : Unit {
    // First, get a computational basis state of the form
    // |s_0 s_1 ... s_n〉 by using PrepareBitString in the earlier example.
    PrepareBitString(bitstring, register);
    // Next, use that |+〉 = H|0〉 and |-〉 = H|1〉 to
    // prepare the desired state.
    for (idxQubit in IndexRange(register)) {
        H(register[idxQubit]);
    }
}
```

## <a name="measurements"></a><span data-ttu-id="29e0b-151">Misurazioni</span><span class="sxs-lookup"><span data-stu-id="29e0b-151">Measurements</span></span>

<span data-ttu-id="29e0b-152">Le misurazioni dei singoli qubits possono essere eseguite in basi diverse, ciascuna rappresentata da un asse di Pauli nella [sfera Bloch](xref:microsoft.quantum.glossary#bloch-sphere).</span><span class="sxs-lookup"><span data-stu-id="29e0b-152">Measurements of individual qubits can be performed in different bases, each represented by a Pauli axis on the [Bloch sphere](xref:microsoft.quantum.glossary#bloch-sphere).</span></span>
<span data-ttu-id="29e0b-153">La base *computazionale* si riferisce alla `PauliZ` base ed è la base più comune utilizzata per la misurazione.</span><span class="sxs-lookup"><span data-stu-id="29e0b-153">The *computational basis* refers to the `PauliZ` basis, and is the most common basis used for measurement.</span></span>

### <a name="measure-a-single-qubit-in-the-pauliz-basis"></a><span data-ttu-id="29e0b-154">Misurare un singolo qubit di `PauliZ` base</span><span class="sxs-lookup"><span data-stu-id="29e0b-154">Measure a single qubit in the `PauliZ` basis</span></span>

<span data-ttu-id="29e0b-155">Usare l' [`M`](xref:microsoft.quantum.intrinsic.m) operazione, che è un'operazione intrinseca non unitaria incorporata, per misurare un singolo qubit di `PauliZ` base e assegnare un valore classico al risultato.</span><span class="sxs-lookup"><span data-stu-id="29e0b-155">Use the [`M`](xref:microsoft.quantum.intrinsic.m) operation, which is a built-in intrinsic non-unitary operation, to measure a single qubit in the `PauliZ` basis and assign a classical value to the result.</span></span>
<span data-ttu-id="29e0b-156">`M`dispone di un tipo restituito riservato, `Result` , che può assumere solo valori `Zero` o `One` corrispondenti agli stati misurati $ \ket {0} $ o $ \ket {1} $, a indicare che il risultato non è più uno stato quantum.</span><span class="sxs-lookup"><span data-stu-id="29e0b-156">`M` has a reserved return type, `Result`, which can only take values `Zero` or `One` corresponding to the measured states $\ket{0}$ or $\ket{1}$ - indicating that the result is no longer a quantum state.</span></span>

<span data-ttu-id="29e0b-157">Un esempio semplice è l'operazione seguente, che alloca un qubit nello stato $ \ket {0} $, quindi applica un'operazione Hadamard `H` e misura il risultato in `PauliZ` base a.</span><span class="sxs-lookup"><span data-stu-id="29e0b-157">A simple example is the following operation, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

```qsharp
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // Apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, return the result of the measurement.
        return result;
    }
}
```

### <a name="measure-one-or-more-qubits-in-specific-bases"></a><span data-ttu-id="29e0b-158">Misurare uno o più qubits in basi specifiche</span><span class="sxs-lookup"><span data-stu-id="29e0b-158">Measure one or more qubits in specific bases</span></span>

<span data-ttu-id="29e0b-159">Per misurare una matrice di uno o più qubits in basi specifiche, è possibile usare l' [`Measure`](xref:microsoft.quantum.intrinsic.measure) operazione.</span><span class="sxs-lookup"><span data-stu-id="29e0b-159">To measure an array of one or more qubits in specific bases, you can use the [`Measure`](xref:microsoft.quantum.intrinsic.measure) operation.</span></span>

<span data-ttu-id="29e0b-160">Gli input per `Measure` sono una matrice di `Pauli` tipi (ad esempio, `[PauliX, PauliZ, PauliZ]` ) e una matrice di qubits.</span><span class="sxs-lookup"><span data-stu-id="29e0b-160">The inputs to `Measure` are an array of `Pauli` types (for example, `[PauliX, PauliZ, PauliZ]`) and an array of qubits.</span></span>

<span data-ttu-id="29e0b-161">Un esempio leggermente più complesso viene fornito dalla seguente operazione, che restituisce il valore booleano `true` se tutti qubits in un registro di tipo `Qubit[]` si trovano nello stato zero se misurato in base a Pauli specificato e che restituisce in `false` caso contrario.</span><span class="sxs-lookup"><span data-stu-id="29e0b-161">A slightly more complicated example is given by the following operation, which returns the Boolean value `true` if all qubits in a register of type `Qubit[]` are in the state zero when measured in a specified Pauli basis, and which returns `false` otherwise.</span></span>

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

<span data-ttu-id="29e0b-162">Si noti che questo esempio viene ancora eseguito solo `Measure` su singoli qubits uno alla volta, ma è possibile estendere l'operazione in misurazioni congiunte su più qubits.</span><span class="sxs-lookup"><span data-stu-id="29e0b-162">Note that this example still only performs `Measure` on individual qubits one at a time, but the operation can be extended to joint measurements on multiple qubits.</span></span>

## <a name="borrowing-qubits-example"></a><span data-ttu-id="29e0b-163">Esempio di qubits in prestito</span><span class="sxs-lookup"><span data-stu-id="29e0b-163">Borrowing Qubits Example</span></span>

<span data-ttu-id="29e0b-164">Sono disponibili esempi nella canonica che usano la `borrowing` parola chiave, ad esempio la funzione seguente `MultiControlledXBorrow` .</span><span class="sxs-lookup"><span data-stu-id="29e0b-164">There are examples in the canon that use the `borrowing` keyword, such as the following function `MultiControlledXBorrow`.</span></span> <span data-ttu-id="29e0b-165">Se `controls` denota il qubits di controllo da aggiungere a un' `X` operazione, il numero di [ancillas](xref:microsoft.quantum.glossary#ancilla) Dirty aggiunto da questa implementazione è `Length(controls)-2` .</span><span class="sxs-lookup"><span data-stu-id="29e0b-165">If `controls` denotes the control qubits to add to an `X` operation, then the number of dirty [ancillas](xref:microsoft.quantum.glossary#ancilla) added by this implementation is `Length(controls)-2`.</span></span>

```qsharp
operation MultiControlledXBorrow ( controls : Qubit[] , target : Qubit ) : Unit
is Adj + Ctl {

    body (...) {
        ... // skipping some case handling here
        let numberOfDirtyQubits = numberOfControls - 2;
        borrowing( dirtyQubits = Qubit[ numberOfDirtyQubits ] ) {

            let allQubits = [ target ] + dirtyQubits + controls;
            let lastDirtyQubit = numberOfDirtyQubits;
            let totalNumberOfQubits = Length(allQubits);

            let outerOperation1 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 1, 1, 0, numberOfDirtyQubits , _ );
            
            let innerOperation = 
                CCNOTByIndex(
                    totalNumberOfQubits - 1, totalNumberOfQubits - 2, lastDirtyQubit, _ );
            
            WithA(outerOperation1, innerOperation, allQubits);
            
            let outerOperation2 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 2, 2, 1, numberOfDirtyQubits - 1 , _ );
            
            WithA(outerOperation2, innerOperation, allQubits);
        }
    }

    controlled(extraControls, ...) {
        MultiControlledXBorrow( extraControls + controls, target );
    }
}
```

<span data-ttu-id="29e0b-166">Si noti che in questo esempio è stato usato l'uso estensivo di `With` Combinator, nel formato applicabile per le operazioni che supportano il tipo adiacente, ad esempio `WithA` .</span><span class="sxs-lookup"><span data-stu-id="29e0b-166">Note that this example used extensive use of the `With` combinator, in its form that is applicable for operations that support adjoint, for example, `WithA`.</span></span>
<span data-ttu-id="29e0b-167">Si tratta di uno stile di programmazione efficace, perché l'aggiunta del controllo alle strutture che coinvolgono `With` propaga il controllo solo all'operazione interna.</span><span class="sxs-lookup"><span data-stu-id="29e0b-167">This is good programming style, because adding control to structures involving `With` propagates control only to the inner operation.</span></span>
<span data-ttu-id="29e0b-168">Si noti inoltre che, oltre all'oggetto `body` dell'operazione, un'implementazione del `controlled` corpo dell'operazione è stata fornita in modo esplicito, anziché ricorrere a un' `controlled auto` istruzione.</span><span class="sxs-lookup"><span data-stu-id="29e0b-168">Also note that, in addition to the `body` of the operation, an implementation of the `controlled` body of the operation was explicitly provided, rather than resorting to a `controlled auto` statement.</span></span>
<span data-ttu-id="29e0b-169">Questo è il motivo per cui, a causa della struttura del circuito, è facile aggiungere altri controlli, il che risulta vantaggioso rispetto all'aggiunta di un controllo a ogni gate in `body` .</span><span class="sxs-lookup"><span data-stu-id="29e0b-169">The reason for this is that, because of the structure of the circuit, it is easy to add further controls, which is beneficial compared to adding control to each gate in the `body`.</span></span> 

<span data-ttu-id="29e0b-170">È istruttivo confrontare questo codice con un'altra funzione Canon, `MultiControlledXClean` ottenendo allo stesso tempo lo stesso obiettivo di implementare un'operazione a controllo multiplo, `X` che usa diversi qubits puliti usando il `using` meccanismo.</span><span class="sxs-lookup"><span data-stu-id="29e0b-170">It is instructive to compare this code with another canon function `MultiControlledXClean` which achieves the same goal of implementing a multiply-controlled `X` operation, however, which uses several clean qubits using the `using` mechanism.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="29e0b-171">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="29e0b-171">Next steps</span></span>

<span data-ttu-id="29e0b-172">Informazioni sul [flusso di controllo](xref:microsoft.quantum.guide.controlflow) in Q #.</span><span class="sxs-lookup"><span data-stu-id="29e0b-172">Learn about [Control Flow](xref:microsoft.quantum.guide.controlflow) in Q#.</span></span>