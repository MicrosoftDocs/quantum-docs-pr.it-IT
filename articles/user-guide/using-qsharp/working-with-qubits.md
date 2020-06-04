---
title: Uso dei qubit
description: Descrizione riempimento
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
ms.openlocfilehash: 0deb0729a88c49798f32a22a943b935d383c570b
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327544"
---
# <a name="working-with-qubits"></a><span data-ttu-id="54fdd-103">Uso dei qubit</span><span class="sxs-lookup"><span data-stu-id="54fdd-103">Working with qubits</span></span>

<span data-ttu-id="54fdd-104">Avendo visto una serie di diverse parti del linguaggio Q #, è possibile passare al suo interno e vedere come usare qubits.</span><span class="sxs-lookup"><span data-stu-id="54fdd-104">Having now seen a variety of different parts of the Q# language, let us get into the thick of it and see how to use qubits themselves.</span></span>

<span data-ttu-id="54fdd-105">Si noti che nessuna di queste istruzioni è consentita all'interno del corpo di una funzione.</span><span class="sxs-lookup"><span data-stu-id="54fdd-105">Note that none of these statements are allowed within the body of a function.</span></span>
<span data-ttu-id="54fdd-106">Sono valide solo all'interno delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="54fdd-106">They are only valid within operations.</span></span>

## <a name="allocating-qubits"></a><span data-ttu-id="54fdd-107">Allocazione di qubits</span><span class="sxs-lookup"><span data-stu-id="54fdd-107">Allocating Qubits</span></span>

### <a name="clean-qubits"></a><span data-ttu-id="54fdd-108">Pulisci qubits</span><span class="sxs-lookup"><span data-stu-id="54fdd-108">Clean qubits</span></span>

<span data-ttu-id="54fdd-109">L' `using` istruzione viene utilizzata per *allocare* nuovi qubits da utilizzare durante un blocco di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="54fdd-109">The `using` statement is used to *allocate* new qubits for use during a statement block.</span></span>

<span data-ttu-id="54fdd-110">L'istruzione è costituita dalla parola chiave `using` , seguita da una parentesi aperta `(` , un'associazione, una parentesi di chiusura `)` e il blocco di istruzioni all'interno del quale sarà disponibile qubits.</span><span class="sxs-lookup"><span data-stu-id="54fdd-110">The statement consists of the keyword `using`, followed by an open parenthesis `(`, a binding, a close parenthesis `)`, and the statement block within which the qubits will be available.</span></span>
<span data-ttu-id="54fdd-111">Il binding segue lo stesso modello delle `let` istruzioni, ovvero un singolo simbolo o una tupla di simboli, seguito da un segno di uguale `=` e da un singolo valore o da una tupla corrispondente di *inizializzatori*.</span><span class="sxs-lookup"><span data-stu-id="54fdd-111">The binding follows the same pattern as `let` statements: either a single symbol or a tuple of symbols, followed by an equals sign `=`, and either a single value or a matching tuple of *initializers*.</span></span>

<span data-ttu-id="54fdd-112">Gli inizializzatori sono disponibili per un singolo qubit, indicato come `Qubit()` o una matrice di qubits, `Qubit[n]` , dove `n` è un' `Int` espressione.</span><span class="sxs-lookup"><span data-stu-id="54fdd-112">Initializers are available either for a single qubit, indicated as `Qubit()`, or an array of qubits, `Qubit[n]`, where `n` is an `Int` expression.</span></span>
<span data-ttu-id="54fdd-113">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="54fdd-113">For example,</span></span>

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```

<span data-ttu-id="54fdd-114">Tutti i qubits allocati in questo modo iniziano con lo stato $ \ket {0} $. nell'esempio precedente, `register` è quindi nello stato $ \ket = \ket \otimes \ket \otimes \cdots \otimes {00000} {0} {0} \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="54fdd-114">Any qubits allocated in this way start off in the $\ket{0}$ state; in the example above, `register` is thus in the state $\ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span></span>
<span data-ttu-id="54fdd-115">Alla fine del `using` blocco, qualsiasi qubits allocato dal blocco viene immediatamente deallocato e non può essere usato ulteriormente.</span><span class="sxs-lookup"><span data-stu-id="54fdd-115">At the end of the `using` block, any qubits allocated by that block are immediately deallocated and cannot be used further.</span></span>

> [!WARNING]
> <span data-ttu-id="54fdd-116">I computer di destinazione si aspettano che qubits si trovino nello stato $ \ket {0} $ immediatamente prima della deallocazione, in modo che possano essere riutilizzati e offerti ad altri `using` blocchi per l'allocazione.</span><span class="sxs-lookup"><span data-stu-id="54fdd-116">Target machines expect that qubits are in the $\ket{0}$ state immediately before deallocation, so that they can be reused and offered to other `using` blocks for allocation.</span></span>
> <span data-ttu-id="54fdd-117">Quando possibile, usare le operazioni unitarie per restituire qualsiasi qubits allocato a $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="54fdd-117">Whenever possible, use unitary operations to return any allocated qubits to $\ket{0}$.</span></span>
> <span data-ttu-id="54fdd-118">Se necessario, l' @"microsoft.quantum.intrinsic.reset" operazione può essere usata per misurare un qubit e per usare il risultato della misurazione per garantire che il qubit misurato venga restituito a $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="54fdd-118">If need be, the @"microsoft.quantum.intrinsic.reset" operation can be used to measure a qubit instead, and to use that measurement result to ensure that the measured qubit is returned to $\ket{0}$.</span></span> <span data-ttu-id="54fdd-119">Una misura di questo tipo eliminerà eventuali problemi con i restanti qubits e può quindi influisca sul calcolo.</span><span class="sxs-lookup"><span data-stu-id="54fdd-119">Such a measurement will destroy any entanglement with the remaining qubits and can thus impact the computation.</span></span>


### <a name="borrowed-qubits"></a><span data-ttu-id="54fdd-120">Qubits preso in prestito</span><span class="sxs-lookup"><span data-stu-id="54fdd-120">Borrowed Qubits</span></span>

<span data-ttu-id="54fdd-121">L' `borrowing` istruzione viene usata per rendere qubits disponibili per l'uso temporaneo, che non devono essere in uno stato specifico.</span><span class="sxs-lookup"><span data-stu-id="54fdd-121">The `borrowing` statement is used to make qubits available for temporary use, which do not need be in a specific state.</span></span>

<span data-ttu-id="54fdd-122">Il meccanismo di prestito consente l'allocazione di qubits che può essere usata come spazio scratch durante un calcolo.</span><span class="sxs-lookup"><span data-stu-id="54fdd-122">The borrowing mechanism allows the allocation of qubits that can be used as scratch space during a computation.</span></span>
<span data-ttu-id="54fdd-123">Questi qubits in genere non sono in uno stato pulito, ovvero non vengono necessariamente inizializzati in uno stato noto, ad esempio $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="54fdd-123">These qubits are generally not in a clean state, i.e., they are not necessarily initialized in a known state such as $\ket{0}$.</span></span>
<span data-ttu-id="54fdd-124">Queste sono spesso denominate qubits "Dirty" perché il loro stato è sconosciuto e può anche essere aggrovigliato con altre parti della memoria del computer Quantum.</span><span class="sxs-lookup"><span data-stu-id="54fdd-124">These are often referred to as "dirty" qubits because their state is unknown and can even be entangled with other parts of the quantum computer's memory.</span></span>

<span data-ttu-id="54fdd-125">L'associazione segue lo stesso modello e le stesse regole di un' `using` istruzione.</span><span class="sxs-lookup"><span data-stu-id="54fdd-125">The binding follows the same pattern and rules as the one in a `using` statement.</span></span>
<span data-ttu-id="54fdd-126">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="54fdd-126">For example,</span></span>
```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```
<span data-ttu-id="54fdd-127">I qubits presi in prestito sono in uno stato sconosciuto e non rientrano nell'ambito alla fine del blocco di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="54fdd-127">The borrowed qubits are in an unknown state and go out of scope at the end of the statement block.</span></span>
<span data-ttu-id="54fdd-128">Il mutuatario si impegna a lasciare il qubits nello stesso stato in cui si trovavano quando sono state prese in prestito, ovvero il proprio stato all'inizio e alla fine del blocco di istruzioni deve essere lo stesso.</span><span class="sxs-lookup"><span data-stu-id="54fdd-128">The borrower commits to leaving the qubits in the same state they were in when they were borrowed,  i.e. their state at the beginning and at the end of the statement block is expected to be the same.</span></span>
<span data-ttu-id="54fdd-129">Questo stato in particolare non è necessariamente uno stato classico, in modo che nella maggior parte dei casi gli ambiti in prestito non contengano misurazioni.</span><span class="sxs-lookup"><span data-stu-id="54fdd-129">This state in particular is not necessarily a classical state, such that in most cases, borrowing scopes should not contain measurements.</span></span> 

<span data-ttu-id="54fdd-130">Quando si prendono in prestito qubits, il sistema tenterà innanzitutto di compilare la richiesta da qubits in uso, ma non è possibile accedervi durante il corpo dell' `borrowing` istruzione.</span><span class="sxs-lookup"><span data-stu-id="54fdd-130">When borrowing qubits, the system will first try to fill the request from qubits that are in use but that are not accessed during the body of the `borrowing` statement.</span></span>
<span data-ttu-id="54fdd-131">Se il qubits non è sufficiente, verrà allocato il nuovo qubits per completare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="54fdd-131">If there aren't enough such qubits, then it will allocate new qubits to complete the request.</span></span>


<span data-ttu-id="54fdd-132">Tra i casi d'uso noti dei qubits Dirty sono implementazioni di controlli CNOT multicontrollati che richiedono solo pochi qubits e implementazioni di incrementatori.</span><span class="sxs-lookup"><span data-stu-id="54fdd-132">Among the known use cases of dirty qubits are implementations of multi-controlled CNOT gates that require only very few qubits and implementation of incrementers.</span></span>
<span data-ttu-id="54fdd-133">Vedere l' [esempio di qubits in prestito](#borrowing-qubits-example) seguente per vedere un esempio di uso in Q # o il factoring della carta con la funzionalità di [*qubits 2n + 2 con moltiplicazione modulare basata su Toffoli*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler e Svore 2017) per un algoritmo che utilizza qubits in prestito.</span><span class="sxs-lookup"><span data-stu-id="54fdd-133">See the [Borrowing Qubits Example](#borrowing-qubits-example) below to see an example of their use in Q#, or the paper [*Factoring using 2n+2 qubits with Toffoli based modular multiplication*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler, and Svore 2017) for an algorithm which utilizes borrowed qubits.</span></span>


## <a name="intrinsic-operations"></a><span data-ttu-id="54fdd-134">Operazioni intrinseche</span><span class="sxs-lookup"><span data-stu-id="54fdd-134">Intrinsic Operations</span></span>

<span data-ttu-id="54fdd-135">Una volta allocato, un qubit può quindi essere passato a funzioni e operazioni.</span><span class="sxs-lookup"><span data-stu-id="54fdd-135">Once allocated, a qubit can then be passed to functions and operations.</span></span>
<span data-ttu-id="54fdd-136">In un certo senso, questo è tutto ciò che può fare un programma Q # con un qubit, in quanto le azioni che è possibile eseguire sono tutte definite come operazioni.</span><span class="sxs-lookup"><span data-stu-id="54fdd-136">In some sense, this is all that a Q# program can do with a qubit, as the actions that can be taken are all defined as operations.</span></span>
<span data-ttu-id="54fdd-137">Queste operazioni verranno visualizzate in modo più dettagliato nelle [operazioni e funzioni intrinseche](xref:microsoft.quantum.libraries.standard.prelude), ma per il momento si menzioneranno alcune operazioni utili che possono essere usate per interagire con qubits.</span><span class="sxs-lookup"><span data-stu-id="54fdd-137">We will see these operations in more detail in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), but for now, we mention a few useful operations that can be used to interact with qubits.</span></span>

<span data-ttu-id="54fdd-138">In primo luogo, gli operatori di Pauli Single-qubit $X $, $Y $ e $Z $ sono rappresentati in Q # dalle operazioni intrinseche `X` , `Y` e `Z` , ognuno dei quali è di tipo `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="54fdd-138">First, the single-qubit Pauli operators $X$, $Y$, and $Z$ are represented in Q# by the intrinsic operations `X`, `Y`, and `Z`, each of which has type `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="54fdd-139">Come descritto in [operazioni e funzioni intrinseche](xref:microsoft.quantum.libraries.standard.prelude), è possibile pensare a $X $ e, di conseguenza, `X` come operazione di capovolgimento di bit o non di controllo.</span><span class="sxs-lookup"><span data-stu-id="54fdd-139">As described in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), we can think of $X$ and hence of `X` as a bit-flip operation or NOT gate.</span></span>
<span data-ttu-id="54fdd-140">L' `X` operazione consente di preparare gli Stati del form $ \ket{s_0 s_1 \dots S_n} $ per una stringa di bit classica $s $:</span><span class="sxs-lookup"><span data-stu-id="54fdd-140">The `X` operation lets us prepare states of the form $\ket{s_0 s_1 \dots s_n}$ for some classical bit string $s$:</span></span>

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
> <span data-ttu-id="54fdd-141">In un secondo momento, verrà illustrato come scrivere questa operazione in modo più compatto che non richiede il controllo di flusso manuale.</span><span class="sxs-lookup"><span data-stu-id="54fdd-141">Later, we will see more compact ways of writing this operation that do not require manual flow control.</span></span>

<span data-ttu-id="54fdd-142">È anche possibile preparare gli Stati, ad esempio $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ e $ \ket {-} = \left (\ket {0} -\ket {1} \right)/\sqrt {2} $ usando la trasformazione Hadamard $H $, rappresentata in Q # dall'operazione intrinseca `H : (Qubit => Unit is Adj + Ctl)` :</span><span class="sxs-lookup"><span data-stu-id="54fdd-142">We can also prepare states such as $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ and $\ket{-} = \left(\ket{0} - \ket{1}\right) / \sqrt{2}$ by using the Hadamard transform $H$, which is represented in Q# by the intrinsic operation `H : (Qubit => Unit is Adj + Ctl)`:</span></span>

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

## <a name="measurements"></a><span data-ttu-id="54fdd-143">Misurazioni</span><span class="sxs-lookup"><span data-stu-id="54fdd-143">Measurements</span></span>

<span data-ttu-id="54fdd-144">Utilizzando l' `Measure` operazione, che è un'operazione intrinseca non unitaria incorporata, è possibile estrarre le informazioni classiche da un oggetto di tipo `Qubit` e assegnare un valore classico come risultato, che ha un tipo riservato `Result` , che indica che il risultato non è più uno stato quantum.</span><span class="sxs-lookup"><span data-stu-id="54fdd-144">Using the `Measure` operation, which is a built-in intrinsic non-unitary operation, we can extract classical information from an object of type `Qubit` and assign a classical value as a result, which has a reserved type `Result`, indicating that the result is no longer a quantum state.</span></span>
<span data-ttu-id="54fdd-145">L'input per `Measure` è un asse di Pauli sulla sfera Bloch, rappresentato da un valore di tipo `Pauli` (ad esempio `PauliX` ) e un valore di tipo `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="54fdd-145">The input to `Measure` is a Pauli axis on the Bloch sphere, represented by a value of type `Pauli` (for instance `PauliX`) and an value of type `Qubit`.</span></span>

<span data-ttu-id="54fdd-146">Un esempio semplice è l'operazione seguente, che alloca un qubit nello stato $ \ket {0} $, quindi applica un'operazione Hadamard `H` e misura il risultato in `PauliZ` base a.</span><span class="sxs-lookup"><span data-stu-id="54fdd-146">A simple example is the following operation, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

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

<span data-ttu-id="54fdd-147">Un esempio leggermente più complesso viene fornito dalla seguente operazione, che restituisce il valore booleano `true` se tutti qubits in un registro di tipo `Qubit[]` si trovano nello stato zero se misurato in base a Pauli specificato e che restituisce in `false` caso contrario.</span><span class="sxs-lookup"><span data-stu-id="54fdd-147">A slightly more complicated example is given by the following operation, which returns the Boolean value `true` if all qubits in a register of type `Qubit[]` are in the state zero when measured in a specified Pauli basis, and which returns `false` otherwise.</span></span>

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

## <a name="borrowing-qubits-example"></a><span data-ttu-id="54fdd-148">Esempio di qubits in prestito</span><span class="sxs-lookup"><span data-stu-id="54fdd-148">Borrowing Qubits Example</span></span>

<span data-ttu-id="54fdd-149">In Canon sono disponibili esempi che usano la `borrowing` parola chiave, ad esempio la funzione `MultiControlledXBorrow` definita di seguito.</span><span class="sxs-lookup"><span data-stu-id="54fdd-149">In the canon there are examples that use the `borrowing` keyword, for instance the function `MultiControlledXBorrow` defined below.</span></span>
<span data-ttu-id="54fdd-150">Se `controls` denota il qubits di controllo che deve essere aggiunto a un' `X` operazione, viene aggiunta una quantità complessiva di `Length(controls)-2` ancillas Dirty da questa implementazione.</span><span class="sxs-lookup"><span data-stu-id="54fdd-150">If `controls` denotes the control qubits that should be added to an `X` operation, then an overall of `Length(controls)-2` many dirty ancillas will be added by this implementation.</span></span>

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

<span data-ttu-id="54fdd-151">Si noti che l'utilizzo estensivo del `With` combinatore---nel formato applicabile per le operazioni che supportano contigut, ad esempio `WithA` ---è stato creato in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="54fdd-151">Note that extensive use of the `With` combinator---in its form that is applicable for operations that support adjoint, i.e., `WithA`---was made in this example.</span></span>
<span data-ttu-id="54fdd-152">Si tratta di uno stile di programmazione efficace, perché l'aggiunta del controllo alle strutture che coinvolgono `With` propaga il controllo solo all'operazione interna.</span><span class="sxs-lookup"><span data-stu-id="54fdd-152">This is good programming style, because adding control to structures involving `With` propagates control only to the inner operation.</span></span>
<span data-ttu-id="54fdd-153">Si noti inoltre che qui, oltre alla `body` dell'operazione, un'implementazione del `controlled` corpo dell'operazione è stata fornita in modo esplicito, anziché ricorrere a un' `controlled auto` istruzione.</span><span class="sxs-lookup"><span data-stu-id="54fdd-153">Further, note that here in addition to the `body` of the operation, an implementation of the `controlled` body of the operation was explicitly provided, rather than resorting to a `controlled auto` statement.</span></span>
<span data-ttu-id="54fdd-154">Il motivo è che la struttura del circuito illustra come aggiungere facilmente ulteriori controlli, che risulta vantaggioso rispetto all'aggiunta di un controllo a ogni singolo controllo nella `body` .</span><span class="sxs-lookup"><span data-stu-id="54fdd-154">The reason for this is that we know from the structure of the circuit how to easily add further controls which is beneficial compared to adding control to each and every individual gate in the `body`.</span></span> 

<span data-ttu-id="54fdd-155">È istruttivo confrontare questo codice con un'altra funzione Canon, `MultiControlledXClean` ottenendo allo stesso tempo lo stesso obiettivo di implementare un'operazione a controllo multiplo, `X` che usa diversi qubits puliti usando il `using` meccanismo.</span><span class="sxs-lookup"><span data-stu-id="54fdd-155">It is instructive to compare this code with another canon function `MultiControlledXClean` which achieves the same goal of implementing a multiply-controlled `X` operation, however, which uses several clean qubits using the `using` mechanism.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="54fdd-156">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="54fdd-156">Next steps</span></span>

<span data-ttu-id="54fdd-157">Informazioni sul [flusso di controllo](xref:microsoft.quantum.guide.controlflow) in Q #.</span><span class="sxs-lookup"><span data-stu-id="54fdd-157">Learn about [Control Flow](xref:microsoft.quantum.guide.controlflow) in Q#.</span></span>