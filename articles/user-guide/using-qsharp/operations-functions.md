---
title: 'Operazioni e funzioni in Q #'
description: Come definire e chiamare operazioni e funzioni, nonché le specializzazioni delle operazioni controllate e contigue.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
ms.openlocfilehash: 9e924b973c4f22a59dd862df3f4f0d70278a1b4e
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327799"
---
# <a name="operations-and-functions-in-q"></a><span data-ttu-id="103d7-103">Operazioni e funzioni in Q #</span><span class="sxs-lookup"><span data-stu-id="103d7-103">Operations and Functions in Q#</span></span>

## <a name="defining-new-operations"></a><span data-ttu-id="103d7-104">Definizione di nuove operazioni</span><span class="sxs-lookup"><span data-stu-id="103d7-104">Defining New Operations</span></span>

<span data-ttu-id="103d7-105">Le operazioni sono il nucleo di Q #.</span><span class="sxs-lookup"><span data-stu-id="103d7-105">Operations are the core of Q#.</span></span>
<span data-ttu-id="103d7-106">Una volta dichiarate, possono essere chiamate da applicazioni .NET classiche, ad esempio usando un simulatore o altre operazioni all'interno di Q #.</span><span class="sxs-lookup"><span data-stu-id="103d7-106">Once declared, they can either be called from classical .NET applications, e.g., using a simulator, or by other operations within Q#.</span></span>
<span data-ttu-id="103d7-107">Ogni operazione definita in Q # può quindi chiamare un numero qualsiasi di altre operazioni, incluse le operazioni intrinseche predefinite definite dal linguaggio.</span><span class="sxs-lookup"><span data-stu-id="103d7-107">Each operation defined in Q# may then call any number of other operations, including the built-in intrinsic operations defined by the language.</span></span> <span data-ttu-id="103d7-108">Il modo specifico in cui vengono definite queste operazioni intrinseche dipende dal computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="103d7-108">The particular way in which these intrinsic operations are defined depends on the target machine.</span></span>
<span data-ttu-id="103d7-109">Quando viene compilata, ogni operazione viene rappresentata come tipo di classe .NET che può essere fornita ai computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="103d7-109">When compiled, each operation is represented as a .NET class type that can be provided to target machines.</span></span>

<span data-ttu-id="103d7-110">Ogni file di origine Q # può definire un numero qualsiasi di operazioni.</span><span class="sxs-lookup"><span data-stu-id="103d7-110">Each Q# source file may define any number of operations.</span></span>
<span data-ttu-id="103d7-111">I nomi delle operazioni devono essere univoci all'interno di uno spazio dei nomi e non possono entrare in conflitto con i nomi di tipo o</span><span class="sxs-lookup"><span data-stu-id="103d7-111">Operation names must be unique within a namespace and may not conflict with type or function names.</span></span>

<span data-ttu-id="103d7-112">Una dichiarazione di operazione è costituita dalla parola chiave `operation` , seguita dal simbolo che rappresenta il nome dell'operazione, una tupla di identificatori tipizzati che definisce gli argomenti per l'operazione, due punti `:` , un'annotazione di tipo che descrive il tipo di risultato dell'operazione, facoltativamente un'annotazione con le caratteristiche dell'operazione, una parentesi graffa aperta `{` , il corpo della dichiarazione dell'operazione e una `}`</span><span class="sxs-lookup"><span data-stu-id="103d7-112">An operation declaration consists of the keyword `operation`, followed by the symbol that is the operation's name, a typed identifier tuple that defines the arguments to the operation, a colon `:`, a type annotation that describes the operation's result type, optionally an annotation with the operation characteristics, an open brace `{`, the body of the operation declaration, and a final closing brace `}`.</span></span>

<span data-ttu-id="103d7-113">Ogni operazione accetta un input, produce un output e specifica l'implementazione per una o più specializzazioni delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="103d7-113">Each operation takes an input, produces an output, and specifies the implementation for one or more operation specializations.</span></span>
<span data-ttu-id="103d7-114">Le specializzazioni possibili e le relative modalità di definizione/chiamata sono descritte in dettaglio più avanti.</span><span class="sxs-lookup"><span data-stu-id="103d7-114">The possible specializations, and how to define/call them, are detailed further below.</span></span>
<span data-ttu-id="103d7-115">Per il momento, si consideri l'operazione seguente, che definisce solo una specializzazione del corpo predefinita e accetta un solo qubit come input, quindi chiama l'operazione incorporata <xref:microsoft.quantum.intrinsic.x> su tale input:</span><span class="sxs-lookup"><span data-stu-id="103d7-115">For now, consider the following operation, which defines only a default body specialization and takes a single qubit as its input, then calls the built-in <xref:microsoft.quantum.intrinsic.x> operation on that input:</span></span>

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

<span data-ttu-id="103d7-116">La parola chiave `operation` inizia la definizione dell'operazione ed è seguita dal nome; in questo caso, `BitFlip` .</span><span class="sxs-lookup"><span data-stu-id="103d7-116">The keyword `operation` begins the operation definition, and is followed by the name; here, `BitFlip`.</span></span>
<span data-ttu-id="103d7-117">Successivamente, il tipo di input viene definito come `Qubit` , insieme a un nome `target` per fare riferimento all'input all'interno della nuova operazione.</span><span class="sxs-lookup"><span data-stu-id="103d7-117">Next, the type of the input is defined as `Qubit`, along with a name `target` for referring to the input within the new operation.</span></span>
<span data-ttu-id="103d7-118">Analogamente, `Unit` definisce che l'output dell'operazione è vuoto.</span><span class="sxs-lookup"><span data-stu-id="103d7-118">Similarly, the `Unit` defines that the operation's output is empty.</span></span>
<span data-ttu-id="103d7-119">Viene usato in modo analogo a `void` in C# e altri linguaggi imperativi ed è equivalente a `unit` in F # e altri linguaggi funzionali.</span><span class="sxs-lookup"><span data-stu-id="103d7-119">This is used similarly to `void` in C# and other imperative languages, and is equivalent to `unit` in F# and other functional languages.</span></span>

<span data-ttu-id="103d7-120">Le operazioni possono inoltre restituire tipi più interessanti rispetto a `Unit` .</span><span class="sxs-lookup"><span data-stu-id="103d7-120">Operations can also return more interesting types than `Unit`.</span></span>
<span data-ttu-id="103d7-121">Ad esempio, l' <xref:microsoft.quantum.intrinsic.m> operazione restituisce un output di tipo `Result` , che rappresenta l'esecuzione di una misurazione.</span><span class="sxs-lookup"><span data-stu-id="103d7-121">For instance, the <xref:microsoft.quantum.intrinsic.m> operation returns an output of type `Result`, representing having performed a measurement.</span></span> <span data-ttu-id="103d7-122">È possibile passare l'output da un'operazione a un'altra operazione o usarlo con la `let` parola chiave per definire una nuova variabile.</span><span class="sxs-lookup"><span data-stu-id="103d7-122">We can either pass the output from an operation to another operation, or can use it with the `let` keyword to define a new variable.</span></span>

<span data-ttu-id="103d7-123">Questo consente la rappresentazione di calcoli classici che interagiscono con le operazioni Quantum a un livello basso, ad esempio nella [codifica superdensa](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding):</span><span class="sxs-lookup"><span data-stu-id="103d7-123">This allows for representing classical computation that interacts with quantum operations at a low level, such as in [superdense coding](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding):</span></span>

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

> [!NOTE]
> <span data-ttu-id="103d7-124">Ogni operazione in Q # accetta esattamente un input e restituisce esattamente un output.</span><span class="sxs-lookup"><span data-stu-id="103d7-124">Each operation in Q# takes exactly one input and returns exactly one output.</span></span>
> <span data-ttu-id="103d7-125">Più input e output vengono quindi rappresentati utilizzando *Tuple*, che raccolgono più valori in un singolo valore.</span><span class="sxs-lookup"><span data-stu-id="103d7-125">Multiple inputs and outputs are then represented using *tuples*, which collect multiple values together into a single value.</span></span>
> <span data-ttu-id="103d7-126">In modo informale, diciamo che Q # è un linguaggio "tuple-in-out".</span><span class="sxs-lookup"><span data-stu-id="103d7-126">Informally, we say that Q# is a "tuple-in tuple-out" language.</span></span>
> <span data-ttu-id="103d7-127">Seguendo questo concetto, `()` deve quindi essere letto come tupla "vuota", che ha il tipo `Unit` .</span><span class="sxs-lookup"><span data-stu-id="103d7-127">Following this concept, `()` should then be read as the "empty" tuple, which has the type `Unit`.</span></span>


## <a name="controlled-and-adjoint-operations"></a><span data-ttu-id="103d7-128">Operazioni controllate e adiacenti</span><span class="sxs-lookup"><span data-stu-id="103d7-128">Controlled and Adjoint Operations</span></span>

<span data-ttu-id="103d7-129">Se un'operazione implementa una trasformazione unitaria, come nel caso di molte operazioni in Q #, è possibile definire il modo in cui l'operazione agisce quando *adjointed* o *controllato*.</span><span class="sxs-lookup"><span data-stu-id="103d7-129">If an operation implements a unitary transformation, as is the case for many operations in Q#, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span> <span data-ttu-id="103d7-130">Una specializzazione *contigua* di un'operazione specifica il modo in cui il "inverso" dell'operazione agisce, mentre una specializzazione *controllata* specifica il modo in cui un'operazione agisce quando l'applicazione è condizionata allo stato di un particolare registro Quantum.</span><span class="sxs-lookup"><span data-stu-id="103d7-130">An *adjoint* specialization of an operation specifies how the "inverse" of the operation acts, while a *controlled* specialization specifies how an operation acts when its application is conditioned on the state of a particular quantum register.</span></span>

<span data-ttu-id="103d7-131">Gli elementi adiacenti delle operazioni Quantum sono cruciali per molti aspetti del quantum computing.</span><span class="sxs-lookup"><span data-stu-id="103d7-131">Adjoints of quantum operations are crucial to many aspects of quantum computing.</span></span> <span data-ttu-id="103d7-132">Più avanti, nella sezione [coniugazioni](#conjugations) , si troverà una situazione di questo tipo, descritta insieme a una tecnica di programmazione Q # utile.</span><span class="sxs-lookup"><span data-stu-id="103d7-132">Further below, in the [Conjugations](#conjugations) section, you will find one such situation discussed alongside a useful Q# programming technique.</span></span>

<span data-ttu-id="103d7-133">La versione controllata di un'operazione è una nuova operazione che applica efficacemente l'operazione di base solo se tutti i qubits di controllo si trovano in uno stato specificato.</span><span class="sxs-lookup"><span data-stu-id="103d7-133">The controlled version of an operation is a new operation that effectively applies the base operation only if all of the control qubits are in a specified state.</span></span>
<span data-ttu-id="103d7-134">Se il controllo qubits si trova in una posizione sovraposizionata, l'operazione di base viene applicata in modo coerente alla parte appropriata della superposizione.</span><span class="sxs-lookup"><span data-stu-id="103d7-134">If the control qubits are in superposition, then the base operation is applied coherently to the appropriate part of the superposition.</span></span>
<span data-ttu-id="103d7-135">In questo modo, le operazioni controllate vengono spesso usate per generare il groviglio.</span><span class="sxs-lookup"><span data-stu-id="103d7-135">Thus, controlled operations are often used to generate entanglement.</span></span>

<span data-ttu-id="103d7-136">Naturalmente è possibile che esista anche una specializzazione *contigua controllata* , specificando l'applicazione controllata di un'operazione contigua.</span><span class="sxs-lookup"><span data-stu-id="103d7-136">Naturally, a *controlled adjoint* specialization could exist as well, specifying the controlled application of an operation's adjoint.</span></span>

> [!NOTE]
> <span data-ttu-id="103d7-137">Se $U $ è la trasformazione unitaria implementata da un'operazione `U` , `Adjoint U` rappresenta la trasformazione unitaria $U ^ \dagger $, che è la trasforma coniugale complessa.</span><span class="sxs-lookup"><span data-stu-id="103d7-137">If $U$ is the unitary transformation implemented by an operation `U`, then `Adjoint U` represents the unitary transformation $U^\dagger$, which is the complex conjugate transpose.</span></span>
> <span data-ttu-id="103d7-138">Se successivamente si applica un'operazione e il relativo contiguo a uno stato lascia lo stato invariato, come illustrato dal fatto che $UU ^ \dagger = U ^ \dagger U = \ID $, la matrice di identità.</span><span class="sxs-lookup"><span data-stu-id="103d7-138">Successively applying an operation and then its adjoint to a state leaves the state unchanged, as illustrated by the fact that $UU^\dagger = U^\dagger U = \id$, the identity matrix.</span></span>
> <span data-ttu-id="103d7-139">La rappresentazione unitaria di un'operazione controllata è leggermente più sfumata, ma è possibile trovare altre informazioni sui [concetti di quantum computing: più qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span><span class="sxs-lookup"><span data-stu-id="103d7-139">The unitary representation of a controlled operation is slightly more nuanced, but you can find more details at [Quantum computing concepts: multiple qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span></span>

<span data-ttu-id="103d7-140">La sezione seguente descrive come chiamare queste varie specializzazioni nel codice Q #.</span><span class="sxs-lookup"><span data-stu-id="103d7-140">The following section describes how to call these various specializations in your Q# code.</span></span>
<span data-ttu-id="103d7-141">Di seguito viene illustrato in dettaglio come definire le operazioni per supportarle.</span><span class="sxs-lookup"><span data-stu-id="103d7-141">Below, we detail how to define operations to support them.</span></span>

### <a name="calling-operation-specializations"></a><span data-ttu-id="103d7-142">Specializzazioni delle operazioni di chiamata</span><span class="sxs-lookup"><span data-stu-id="103d7-142">Calling operation specializations</span></span>

<span data-ttu-id="103d7-143">Un *functor* in Q # è una factory che definisce una nuova operazione da un'altra operazione.</span><span class="sxs-lookup"><span data-stu-id="103d7-143">A *functor* in Q# is a factory that defines a new operation from another operation.</span></span>
<span data-ttu-id="103d7-144">I due funtori standard in Q # sono `Adjoint` e `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="103d7-144">The two standard functors in Q# are `Adjoint` and `Controlled`.</span></span>

<span data-ttu-id="103d7-145">Funtori hanno accesso all'implementazione dell'operazione di base quando si definisce l'implementazione della nuova operazione.</span><span class="sxs-lookup"><span data-stu-id="103d7-145">Functors have access to the implementation of the base operation when defining the implementation of the new operation.</span></span>
<span data-ttu-id="103d7-146">Funtori può quindi eseguire funzioni più complesse rispetto alle funzioni di livello superiore tradizionali.</span><span class="sxs-lookup"><span data-stu-id="103d7-146">Thus, functors can perform more complex functions than traditional higher-level functions.</span></span> <span data-ttu-id="103d7-147">Funtori non dispone di una rappresentazione nel sistema di tipi Q #.</span><span class="sxs-lookup"><span data-stu-id="103d7-147">Functors do not have a representation in the Q# type system.</span></span> <span data-ttu-id="103d7-148">Attualmente non è possibile associarli a una variabile o passarli come argomenti.</span><span class="sxs-lookup"><span data-stu-id="103d7-148">It is thus currently not possible to bind them to a variable or pass them as arguments.</span></span> 

<span data-ttu-id="103d7-149">Un functor viene usato applicando l'oggetto a un'operazione, restituendo una nuova operazione.</span><span class="sxs-lookup"><span data-stu-id="103d7-149">A functor is used by applying it to an operation, returning a new operation.</span></span>
<span data-ttu-id="103d7-150">Ad esempio, l'operazione risultante dall'applicazione del `Adjoint` functore all' `Y` operazione viene scritta come `Adjoint Y` .</span><span class="sxs-lookup"><span data-stu-id="103d7-150">For example, the operation that results from applying the `Adjoint` functor to the `Y` operation is written as `Adjoint Y`.</span></span>
<span data-ttu-id="103d7-151">La nuova operazione può quindi essere richiamata come qualsiasi altra operazione.</span><span class="sxs-lookup"><span data-stu-id="103d7-151">The new operation may then be invoked like any other operation.</span></span>
<span data-ttu-id="103d7-152">Per eseguire un'operazione per supportare l'applicazione di `Adjoint` e/o `Controlled` funtori, il tipo restituito deve necessariamente essere `Unit` .</span><span class="sxs-lookup"><span data-stu-id="103d7-152">For an operation to support application of the `Adjoint` and/or `Controlled` functors, its return type necessarily needs to be `Unit`.</span></span> 

#### <a name="adjoint-functor"></a><span data-ttu-id="103d7-153">`Adjoint`funtore</span><span class="sxs-lookup"><span data-stu-id="103d7-153">`Adjoint` functor</span></span>

<span data-ttu-id="103d7-154">Applica quindi `Adjoint Y(q1)` il functor adiacente all' `Y` operazione per generare una nuova operazione e applica tale nuova operazione a `q1` .</span><span class="sxs-lookup"><span data-stu-id="103d7-154">Thus, `Adjoint Y(q1)` applies the Adjoint functor to the `Y` operation to generate a new operation, and applies that new operation to `q1`.</span></span>
<span data-ttu-id="103d7-155">La nuova operazione ha la stessa firma e il tipo dell'operazione di base `Y` .</span><span class="sxs-lookup"><span data-stu-id="103d7-155">The new operation has the same signature and type as the base operation `Y`.</span></span>
<span data-ttu-id="103d7-156">In particolare, la nuova operazione consente inoltre `Adjoint` e consentirà `Controlled` solo se è stata eseguita l'operazione di base.</span><span class="sxs-lookup"><span data-stu-id="103d7-156">In particular, the new operation also allows `Adjoint`, and will allow `Controlled` if and only if the base operation did.</span></span>
<span data-ttu-id="103d7-157">Il functor contiguo è il proprio inverso; ovvero `Adjoint Adjoint Op` è sempre uguale a `Op` .</span><span class="sxs-lookup"><span data-stu-id="103d7-157">The Adjoint functor is its own inverse; that is, `Adjoint Adjoint Op` is always the same as `Op`.</span></span>

#### <a name="controlled-functor"></a><span data-ttu-id="103d7-158">`Controlled`funtore</span><span class="sxs-lookup"><span data-stu-id="103d7-158">`Controlled` functor</span></span>

<span data-ttu-id="103d7-159">Analogamente, `Controlled X(controls, target)` applica il functor controllato all' `X` operazione per generare una nuova operazione e applica tale nuova operazione a `controls` e `target` .</span><span class="sxs-lookup"><span data-stu-id="103d7-159">Similarly, `Controlled X(controls, target)` applies the Controlled functor to the `X` operation to generate a new operation, and applies that new operation to `controls` and `target`.</span></span>

> [!NOTE]
> <span data-ttu-id="103d7-160">In Q # le versioni controllate accettano sempre una matrice di qubits di controllo e lo stato specificato è sempre per tutti i qubits di controllo nello stato computazionale ( `PauliZ` ) `One` , $ \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="103d7-160">In Q#, controlled versions always take an array of control qubits, and the specified state is always for all of the control qubits to be in the computational (`PauliZ`) `One` state, $\ket{1}$.</span></span>
> <span data-ttu-id="103d7-161">Il controllo basato su altri Stati può essere ottenuto applicando l'operazione unitaria appropriata al controllo qubits prima dell'operazione controllata, quindi applicando gli inversi dell'operazione unitaria dopo l'operazione controllata.</span><span class="sxs-lookup"><span data-stu-id="103d7-161">Controlling based on other states may be achieved by applying the appropriate unitary operation to the control qubits before the controlled operation, and then applying the inverses of the unitary operation after the controlled operation.</span></span>
> <span data-ttu-id="103d7-162">Se, ad esempio, si applica un'operazione `X` a un controllo qubit prima e dopo un'operazione controllata, l'operazione Controlla lo `Zero` stato ($ \ket {0} $) per tale qubit; l'applicazione di un' `H` operazione prima e dopo controlla lo stato `PauliX` `One` , ovvero-1 autovalore di Pauli X, $ \ket {-} \mathrel{: =} (\ket {0} -\ket {1} )/\sqrt {2} $ anziché lo `PauliZ` `One` stato.</span><span class="sxs-lookup"><span data-stu-id="103d7-162">For example, applying an `X` operation to a control qubit before and after a controlled operation will cause the operation to control on the `Zero` state ($\ket{0}$) for that qubit; applying an `H` operation before and after will control on the `PauliX` `One` state, that is -1 eigenvalue of Pauli X, $\ket{-} \mathrel{:=} (\ket{0} - \ket{1}) / \sqrt{2}$ rather than the `PauliZ` `One` state.</span></span>

<span data-ttu-id="103d7-163">Data un'espressione di operazione, è possibile formare una nuova espressione di operazione usando il `Controlled` functor.</span><span class="sxs-lookup"><span data-stu-id="103d7-163">Given an operation expression, a new operation expression may be formed using the `Controlled` functor.</span></span>
<span data-ttu-id="103d7-164">La firma della nuova operazione si basa sulla firma dell'operazione originale.</span><span class="sxs-lookup"><span data-stu-id="103d7-164">The signature of the new operation is based on the signature of the original operation.</span></span>
<span data-ttu-id="103d7-165">Il tipo di risultato è lo stesso, ma il tipo di input è una tupla con due tuple con una matrice qubit che include i qubit del controllo come primo elemento e gli argomenti dell'operazione originale come secondo elemento.</span><span class="sxs-lookup"><span data-stu-id="103d7-165">The result type is the same, but the input type is a two-tuple with a qubit array that holds the control qubit(s) as the first element and the arguments of the original operation as the second element.</span></span>
<span data-ttu-id="103d7-166">La nuova operazione supporta `Controlled` e supporterà solo se è `Adjoint` stata eseguita l'operazione originale.</span><span class="sxs-lookup"><span data-stu-id="103d7-166">The new operation supports `Controlled`, and will support `Adjoint` if and only if the original operation did.</span></span>

<span data-ttu-id="103d7-167">Se l'operazione originale ha accettato un solo argomento, l'equivalenza della tupla singleton entrerà in gioco qui.</span><span class="sxs-lookup"><span data-stu-id="103d7-167">If the original operation took only a single argument, then singleton tuple equivalence will come into play here.</span></span>
<span data-ttu-id="103d7-168">Ad esempio, `Controlled X` è la versione controllata dell' `X` operazione.</span><span class="sxs-lookup"><span data-stu-id="103d7-168">For instance, `Controlled X` is the controlled version of the `X` operation.</span></span> 
<span data-ttu-id="103d7-169">`X`il tipo è `(Qubit => Unit is Adj + Ctl)` , quindi `Controlled X` è di tipo, a `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` causa dell'equivalenza della tupla singleton, equivale a `((Qubit[], Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="103d7-169">`X` has type `(Qubit => Unit is Adj + Ctl)`, so `Controlled X` has type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; because of singleton tuple equivalence, this is the same as `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="103d7-170">Se l'operazione di base ha assunto diversi argomenti, ricordarsi di racchiudere tra parentesi gli argomenti corrispondenti della versione controllata dell'operazione per convertirli in una tupla.</span><span class="sxs-lookup"><span data-stu-id="103d7-170">If the base operation took several arguments, remember to enclose the corresponding arguments of the controlled version of the operation in parentheses to convert them into a tuple.</span></span>
<span data-ttu-id="103d7-171">Ad esempio, `Controlled Rz` è la versione controllata dell' `Rz` operazione.</span><span class="sxs-lookup"><span data-stu-id="103d7-171">For instance, `Controlled Rz` is the controlled version of the `Rz` operation.</span></span> 
<span data-ttu-id="103d7-172">`Rz`dispone del tipo `((Double, Qubit) => Unit is Adj + Ctl)` , pertanto `Controlled Rz` è di tipo `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="103d7-172">`Rz` has type `((Double, Qubit) => Unit is Adj + Ctl)`, so `Controlled Rz` has type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="103d7-173">Quindi, `Controlled Rz(controls, (0.1, target))` sarebbe una chiamata valida di `Controlled Rz` (si notino le parentesi `0.1, target` ).</span><span class="sxs-lookup"><span data-stu-id="103d7-173">Thus, `Controlled Rz(controls, (0.1, target))` would be a valid invocation of `Controlled Rz` (note the parentheses around `0.1, target`).</span></span>

<span data-ttu-id="103d7-174">Un altro esempio `CNOT(control, target)` può essere implementato come `Controlled X([control], target)` .</span><span class="sxs-lookup"><span data-stu-id="103d7-174">As another example, `CNOT(control, target)` can be implemented as `Controlled X([control], target)`.</span></span> <span data-ttu-id="103d7-175">Se una destinazione deve essere controllata da 2 Control qubits (CCNOT), è possibile usare l' `Controlled X([control1, control2], target)` istruzione.</span><span class="sxs-lookup"><span data-stu-id="103d7-175">If a target should be controlled by 2 control qubits (CCNOT), we can use `Controlled X([control1, control2], target)` statement.</span></span>

#### `Controlled Adjoint` 

<span data-ttu-id="103d7-176">Il `Controlled` e il `Adjoint` funtori commute, quindi non esiste alcuna differenza tra l'applicazione di `Controlled Adjoint Op` o `Adjoint Controlled Op` .</span><span class="sxs-lookup"><span data-stu-id="103d7-176">The `Controlled` and `Adjoint` functors commute, so there is no difference between applying `Controlled Adjoint Op` or `Adjoint Controlled Op`.</span></span>


## <a name="defining-controlled-and-adjoint-implementations"></a><span data-ttu-id="103d7-177">Definizione di implementazioni controllate e adiacenti</span><span class="sxs-lookup"><span data-stu-id="103d7-177">Defining Controlled and Adjoint Implementations</span></span>

<span data-ttu-id="103d7-178">Nei primi esempi di dichiarazione di operazione precedenti, le operazioni `BitFlip` e `DecodeSuperdense` sono state definite rispettivamente con le firme `(Qubit => Unit)` e `((Qubit, Qubit) => (Result, Result))` .</span><span class="sxs-lookup"><span data-stu-id="103d7-178">In the first operation declaration examples above, the operations `BitFlip` and `DecodeSuperdense` were defined with signatures `(Qubit => Unit)` and `((Qubit, Qubit) => (Result, Result))`, respectively.</span></span>
<span data-ttu-id="103d7-179">Come `DecodeSuperdense` include le misurazioni, non è un'operazione unitaria e pertanto non è possibile che esistano specializzazioni controllate e non contigue (richiamare il requisito correlato restituito da tale operazione `Unit` ).</span><span class="sxs-lookup"><span data-stu-id="103d7-179">As `DecodeSuperdense` includes measurements, it is not a unitary operation, and therefore neither controlled not adjoint specializations could exist (recall the related requirement that such an operation return `Unit`).</span></span>
<span data-ttu-id="103d7-180">Tuttavia, poiché `BitFlip` esegue semplicemente l'operazione unitaria <xref:microsoft.quantum.intrinsic.x> , è possibile che sia stata definita con entrambe le specializzazioni.</span><span class="sxs-lookup"><span data-stu-id="103d7-180">However, as `BitFlip` simply performs the unitary <xref:microsoft.quantum.intrinsic.x> operation, we could have defined it with both specializations.</span></span>

<span data-ttu-id="103d7-181">In questo articolo viene illustrato in dettaglio come includere l'esistenza di specializzazioni nelle dichiarazioni di operazione Q #, offrendo quindi la possibilità di chiamare insieme a `Adjoint` e/o `Controlled` funtori.</span><span class="sxs-lookup"><span data-stu-id="103d7-181">Here, we detail how to include the existence of specializations in your Q# operation declarations, hence giving them the ability to called in conjunction with the `Adjoint` and/or `Controlled` functors.</span></span>
<span data-ttu-id="103d7-182">Di [seguito](#circumstances-for-validly-defining-specializations)vengono descritte alcune situazioni in cui è valido o non è valido per dichiarare determinate specializzazioni.</span><span class="sxs-lookup"><span data-stu-id="103d7-182">Further [below](#circumstances-for-validly-defining-specializations), we describe some of the situations in which it is either valid or not valid to declare certain specializations.</span></span>

<span data-ttu-id="103d7-183">Le caratteristiche dell'operazione definiscono i tipi di funtori che possono essere applicati all'operazione dichiarata e l'effetto che hanno.</span><span class="sxs-lookup"><span data-stu-id="103d7-183">Operation characteristics define what kinds of functors can be applied to the declared operation, and what effect they have.</span></span> <span data-ttu-id="103d7-184">L'esistenza di queste specializzazioni può essere dichiarata come parte della firma dell'operazione, in particolare tramite un'annotazione con le caratteristiche dell'operazione, ovvero `is Adj` , `is Ctl` o `is Adj + Ctl` .</span><span class="sxs-lookup"><span data-stu-id="103d7-184">The existence of these specializations can be declared as part of the operation signature, specifically through an annotation with the operation characteristics: either `is Adj`, `is Ctl`, or `is Adj + Ctl`.</span></span>
<span data-ttu-id="103d7-185">L'implementazione effettiva di ogni specializzazione può essere definita in modo *implicito* o *esplicito* .</span><span class="sxs-lookup"><span data-stu-id="103d7-185">The actual implementation of each specialization can either be *implicitly* or *explicitly* defined.</span></span>

### <a name="implicitly-specifying-implementations"></a><span data-ttu-id="103d7-186">Specifica delle implementazioni in modo implicito</span><span class="sxs-lookup"><span data-stu-id="103d7-186">Implicitly specifying implementations</span></span>

<span data-ttu-id="103d7-187">In questo caso, il corpo della dichiarazione dell'operazione è costituito esclusivamente dall'implementazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="103d7-187">In this case, the body of the operation declaration consists solely of the default implementation.</span></span> <span data-ttu-id="103d7-188">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="103d7-188">For example:</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```
<span data-ttu-id="103d7-189">In questo caso, l'implementazione corrispondente per ogni specializzazione dichiarata in modo implicito viene generata automaticamente dal compilatore, da eseguire se `Adjoint` `Controlled` vengono usati o funtori.</span><span class="sxs-lookup"><span data-stu-id="103d7-189">Here, the corresponding implementation for each such implicitly declared specialization is automatically generated by the compiler, to be performed if the `Adjoint` or `Controlled` functors are used.</span></span>

<span data-ttu-id="103d7-190">Pertanto, una chiamata di `Adjoint PrepareEntangledPair` provocherebbe il compilatore che implementa il contiguo di `CNOT` e quindi il contiguo di `H` .</span><span class="sxs-lookup"><span data-stu-id="103d7-190">So, a call of `Adjoint PrepareEntangledPair` would result in the compiler implementing the adjoint of `CNOT` and then the adjoint of `H`.</span></span>
<span data-ttu-id="103d7-191">Queste singole operazioni sono entrambe autocontigue, pertanto l'operazione risultante `Adjoint PrepareEntangledPair` sarebbe semplicemente costituita dall'applicazione `CNOT(here, there)` e quindi da `H(here)` .</span><span class="sxs-lookup"><span data-stu-id="103d7-191">These individual operations are both self-adjoint, so the resulting `Adjoint PrepareEntangledPair` operation would simply consist of applying `CNOT(here, there)` and then `H(here)`.</span></span>
<span data-ttu-id="103d7-192">È quindi possibile usarlo per scrivere l' `DecodeSuperdense` esempio precedente in modo più compatto, usando il contiguo di `PrepareEntangledPair` per trasformare lo stato incastrato di nuovo in una coppia non impigliata di qubits:</span><span class="sxs-lookup"><span data-stu-id="103d7-192">Hence we can use this to write the `DecodeSuperdense` example above more compactly, by using the adjoint of `PrepareEntangledPair` to transform the entangled state back into an unentangled pair of qubits:</span></span>

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

<span data-ttu-id="103d7-193">L'annotazione con le caratteristiche dell'operazione nella dichiarazione è utile per garantire che il compilatore generi automaticamente altre specializzazioni in base all'implementazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="103d7-193">The annotation with the operation characteristics in the declaration is useful to ensure that the compiler auto-generates other specializations based on the default implementation.</span></span> 

<span data-ttu-id="103d7-194">Quando si progettano operazioni da usare con funtori, è necessario considerare alcune importanti limitazioni.</span><span class="sxs-lookup"><span data-stu-id="103d7-194">There are a number of important limitations to consider when designing operations for use with functors.</span></span>
<span data-ttu-id="103d7-195">In modo più critico, le specializzazioni per un'operazione che usa il valore di output di qualsiasi altra operazione *non possono* essere generate automaticamente dal compilatore, perché è ambiguo come riordinare le istruzioni in tale operazione per ottenere lo stesso effetto.</span><span class="sxs-lookup"><span data-stu-id="103d7-195">Most critically, specializations for an operation that uses the output value of any other operation *cannot* be auto-generated by the compiler, as it is ambiguous how to reorder the statements in such an operation to obtain the same effect.</span></span>

<span data-ttu-id="103d7-196">Pertanto, è spesso utile specificare in modo esplicito le varie implementazioni.</span><span class="sxs-lookup"><span data-stu-id="103d7-196">Therefore, it is often useful to explicitly specify the various implementations.</span></span>

### <a name="explicitly-specifying-implementations"></a><span data-ttu-id="103d7-197">Specifica delle implementazioni in modo esplicito</span><span class="sxs-lookup"><span data-stu-id="103d7-197">Explicitly specifying implementations</span></span>

<span data-ttu-id="103d7-198">Nel caso in cui l'implementazione non possa essere generata dal compilatore, può essere specificata in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="103d7-198">In the case where the implementation cannot be generated by the compiler, it can be explicitly specified.</span></span> <span data-ttu-id="103d7-199">Tali dichiarazioni di specializzazione esplicita possono essere costituite da una *direttiva di generazione* adatta o da un'implementazione definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="103d7-199">Such explicit specialization declarations can consist of a suitable *generation directive* or a user-defined implementation.</span></span>
<span data-ttu-id="103d7-200">Qui viene fornita la gamma completa di possibilità, con esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="103d7-200">Here we provide the full range of possibilities, with examples following below.</span></span>


#### <a name="explicit-specialization-declarations"></a><span data-ttu-id="103d7-201">Dichiarazioni di specializzazione esplicite</span><span class="sxs-lookup"><span data-stu-id="103d7-201">Explicit specialization declarations</span></span>

<span data-ttu-id="103d7-202">Le operazioni Q # possono contenere le seguenti dichiarazioni di specializzazione esplicite:</span><span class="sxs-lookup"><span data-stu-id="103d7-202">Q# operations may contain the following explicit specialization declarations:</span></span>

- <span data-ttu-id="103d7-203">La `body` specializzazione specifica l'implementazione dell'operazione senza funtori applicata.</span><span class="sxs-lookup"><span data-stu-id="103d7-203">The `body` specialization specifies the implementation of the operation with no functors applied.</span></span>
- <span data-ttu-id="103d7-204">La `adjoint` specializzazione specifica l'implementazione dell'operazione con il `Adjoint` functor applicato.</span><span class="sxs-lookup"><span data-stu-id="103d7-204">The `adjoint` specialization specifies the implementation of the operation with the `Adjoint` functor applied.</span></span>
- <span data-ttu-id="103d7-205">La `controlled` specializzazione specifica l'implementazione dell'operazione con il `Controlled` functor applicato.</span><span class="sxs-lookup"><span data-stu-id="103d7-205">The `controlled` specialization specifies the implementation of the operation with the `Controlled` functor applied.</span></span>
- <span data-ttu-id="103d7-206">La `controlled adjoint` specializzazione specifica l'implementazione dell'operazione con `Adjoint` e `Controlled` funtori applicati.</span><span class="sxs-lookup"><span data-stu-id="103d7-206">The `controlled adjoint` specialization specifies the implementation of the operation with both the `Adjoint` and `Controlled` functors applied.</span></span>
  <span data-ttu-id="103d7-207">Questa specializzazione può anche essere denominata `adjoint controlled` , dal momento che i due funtori del commutatore.</span><span class="sxs-lookup"><span data-stu-id="103d7-207">This specialization can also be named `adjoint controlled`, since the two functors commute.</span></span>


<span data-ttu-id="103d7-208">Una specializzazione di operazione è costituita dal tag di specializzazione, ad esempio `body` , o e `adjoint` così via, seguito da uno dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="103d7-208">An operation specialization consists of the specialization tag (e.g. `body`, or `adjoint`, etc.) followed by one of:</span></span>

- <span data-ttu-id="103d7-209">Dichiarazione esplicita, come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="103d7-209">An explicit declaration as described below.</span></span>
- <span data-ttu-id="103d7-210">*Direttiva* che indica al compilatore *come* generare la specializzazione, una tra le seguenti:</span><span class="sxs-lookup"><span data-stu-id="103d7-210">A *directive* that tells the compiler *how* to generate the specialization, one of:</span></span>
  - <span data-ttu-id="103d7-211">`intrinsic`, che indica che la specializzazione viene fornita dal computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="103d7-211">`intrinsic`, which indicates that the specialization is provided by the target machine.</span></span>
  - <span data-ttu-id="103d7-212">`distribute`, che può essere usato con le `controlled` `controlled adjoint` specializzazioni e.</span><span class="sxs-lookup"><span data-stu-id="103d7-212">`distribute`, which may be used with the `controlled` and `controlled adjoint` specializations.</span></span>
    <span data-ttu-id="103d7-213">Se usato con `controlled` , indica che il compilatore deve calcolare la specializzazione applicando `Controlled` a tutte le operazioni nell'oggetto `body` .</span><span class="sxs-lookup"><span data-stu-id="103d7-213">When used with `controlled`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `body`.</span></span>
    <span data-ttu-id="103d7-214">Se usato con `controlled adjoint` , indica che il compilatore deve calcolare la specializzazione applicando `Controlled` a tutte le operazioni nella `adjoint` specializzazione.</span><span class="sxs-lookup"><span data-stu-id="103d7-214">When used with `controlled adjoint`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `adjoint` specialization.</span></span>
  - <span data-ttu-id="103d7-215">`invert`, che indica che il compilatore deve calcolare la `adjoint` specializzazione invertendo l'oggetto `body` , ad esempio invertendo l'ordine delle operazioni e applicando il contiguo a ognuno di essi.</span><span class="sxs-lookup"><span data-stu-id="103d7-215">`invert`, which indicates that the compiler should compute the `adjoint` specialization by inverting the `body`, i.e. reversing the order of operations and applying the adjoint to each one.</span></span>
    <span data-ttu-id="103d7-216">Se usato con `adjoint controlled` , indica che il compilatore deve calcolare la specializzazione invertendo la `controlled` specializzazione.</span><span class="sxs-lookup"><span data-stu-id="103d7-216">When used with `adjoint controlled`, this indicates that the compiler should compute the specialization by inverting the `controlled` specialization.</span></span>
  - <span data-ttu-id="103d7-217">`self`, per indicare che la specializzazione contigua è uguale alla `body` specializzazione.</span><span class="sxs-lookup"><span data-stu-id="103d7-217">`self`, to indicate that the adjoint specialization is the the same as the `body` specialization.</span></span>
    <span data-ttu-id="103d7-218">Questo è valido per le `adjoint` `adjoint controlled` specializzazioni e.</span><span class="sxs-lookup"><span data-stu-id="103d7-218">This is legal for the `adjoint` and `adjoint controlled` specializations.</span></span>
    <span data-ttu-id="103d7-219">Per `adjoint controlled` , `self` implica che la `adjoint controlled` specializzazione corrisponde alla `controlled` specializzazione.</span><span class="sxs-lookup"><span data-stu-id="103d7-219">For `adjoint controlled`, `self` implies that the `adjoint controlled` specialization is the same as the `controlled` specialization.</span></span>
  - <span data-ttu-id="103d7-220">`auto`, per indicare che il compilatore deve selezionare una direttiva appropriata da applicare.</span><span class="sxs-lookup"><span data-stu-id="103d7-220">`auto`, to indicate that the compiler should select an appropriate directive to apply.</span></span>
    <span data-ttu-id="103d7-221">`auto`non può essere usato per la `body` specializzazione.</span><span class="sxs-lookup"><span data-stu-id="103d7-221">`auto` may not be used for the `body` specialization.</span></span>

<span data-ttu-id="103d7-222">Tutte le direttive e richiedono un punto e virgola `auto` di chiusura `;` .</span><span class="sxs-lookup"><span data-stu-id="103d7-222">The directives and `auto` all require a closing semi-colon `;`.</span></span>
<span data-ttu-id="103d7-223">La `auto` direttiva viene risolta nella direttiva di generazione seguente se viene fornita una dichiarazione esplicita di `body` :</span><span class="sxs-lookup"><span data-stu-id="103d7-223">The `auto` directive resolves to the following generation directive if an explicit declaration of the `body` is provided:</span></span>

- <span data-ttu-id="103d7-224">La `adjoint` specializzazione viene generata in base alla direttiva `invert` .</span><span class="sxs-lookup"><span data-stu-id="103d7-224">The `adjoint` specialization is generated according to the directive `invert`.</span></span>
- <span data-ttu-id="103d7-225">La `controlled` specializzazione viene generata in base alla direttiva `distribute` .</span><span class="sxs-lookup"><span data-stu-id="103d7-225">The `controlled` specialization is generated according to the directive `distribute`.</span></span>
- <span data-ttu-id="103d7-226">La `adjoint controlled` specializzazione viene generata in base alla direttiva `invert` se viene fornita una dichiarazione esplicita per `controlled` , ma non una per `adjoint` e `distribute` in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="103d7-226">The `adjoint controlled` specialization is generated according to the directive `invert` if an explicit declaration for `controlled` is given but not one for `adjoint`, and `distribute` otherwise.</span></span>

> [!TIP]   
> <span data-ttu-id="103d7-227">Se un'operazione è autonoma, specificare in modo esplicito la specializzazione contigua o controllata tramite la direttiva `self` di generazione per consentire al compilatore di utilizzare tali informazioni a scopo di ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="103d7-227">If an operation is self-adjoint, explicitly specify either the adjoint or the controlled adjoint specialization via the generation directive `self` to allow the compiler to make use of that information for optimization purposes.</span></span>

<span data-ttu-id="103d7-228">Una dichiarazione di specializzazione contenente un'implementazione definita dall'utente è costituita da una tupla di argomenti seguita da un blocco di istruzioni con il codice Q # che implementa la specializzazione.</span><span class="sxs-lookup"><span data-stu-id="103d7-228">A specialization declaration containing a user defined implementation consists of an argument tuple followed by a statement block with the Q# code that implements the specialization.</span></span>
<span data-ttu-id="103d7-229">Nell'elenco di argomenti, `...` viene usato per rappresentare gli argomenti dichiarati per l'intera operazione.</span><span class="sxs-lookup"><span data-stu-id="103d7-229">In the argument list, `...` is used to represent the arguments declared for the operation as a whole.</span></span>
<span data-ttu-id="103d7-230">Per `body` e `adjoint` , l'elenco di argomenti deve essere sempre `(...)` ; per `controlled` e `adjoint controlled` , l'elenco di argomenti deve essere un simbolo che rappresenta la matrice di qubits del controllo, seguito da `...` , racchiuso tra parentesi, ad esempio `(controls,...)` .</span><span class="sxs-lookup"><span data-stu-id="103d7-230">For `body` and `adjoint`, the argument list should always be `(...)`; for `controlled` and `adjoint controlled`, the argument list should be a symbol that represents the array of control qubits, followed by `...`, enclosed in parentheses; for example, `(controls,...)`.</span></span>

### <a name="examples"></a><span data-ttu-id="103d7-231">Esempi</span><span class="sxs-lookup"><span data-stu-id="103d7-231">Examples</span></span>

<span data-ttu-id="103d7-232">Una dichiarazione di operazione potrebbe essere semplice come la seguente, che definisce l'operazione di Pauli X primitiva:</span><span class="sxs-lookup"><span data-stu-id="103d7-232">An operation declaration might be as simple as the following, which defines the primitive Pauli X operation:</span></span>

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```
<span data-ttu-id="103d7-233">Si noti che il contiguo dell'operazione di Pauli X viene definito con la direttiva, `self` perché per definizione `X` è il proprio inverso.</span><span class="sxs-lookup"><span data-stu-id="103d7-233">Note that the adjoint of the Pauli X operation is defined with the directive `self` because by definition `X` is its own inverse.</span></span>

<span data-ttu-id="103d7-234">Il codice `PrepareEntangledPair` riportato sopra, ad esempio, è equivalente al codice riportato di seguito contenente dichiarazioni di specializzazione esplicite:</span><span class="sxs-lookup"><span data-stu-id="103d7-234">The code in `PrepareEntangledPair` above for example is equivalent to the code below containing explicit specialization declarations:</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
<span data-ttu-id="103d7-235">La parola chiave `auto` indica che il compilatore deve determinare come generare l'implementazione della specializzazione.</span><span class="sxs-lookup"><span data-stu-id="103d7-235">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>

#### <a name="user-defined-specialization-implementation"></a><span data-ttu-id="103d7-236">Implementazione della specializzazione definita dall'utente</span><span class="sxs-lookup"><span data-stu-id="103d7-236">User-defined specialization implementation</span></span>

<span data-ttu-id="103d7-237">Se il compilatore non è in grado di generare automaticamente l'implementazione per una determinata specializzazione o se è possibile fornire un'implementazione più efficiente, l'implementazione può anche essere definita manualmente.</span><span class="sxs-lookup"><span data-stu-id="103d7-237">If the compiler cannot generate the implementation for a certain specialization automatically, or if a more efficient implementation can be given, then the implementation may also be manually defined.</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
<span data-ttu-id="103d7-238">Nell'esempio precedente, `adjoint invert;` indica che la specializzazione contigua deve essere generata invertendo l'implementazione del corpo e `controlled adjoint invert;` indica che la specializzazione contigua controllata deve essere generata invertendo l'implementazione specificata della specializzazione controllata.</span><span class="sxs-lookup"><span data-stu-id="103d7-238">In the example above, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="103d7-239">Se una o più specializzazioni oltre al corpo predefinito devono essere dichiarate in modo esplicito, l'implementazione del corpo predefinito deve essere racchiusa anche in una dichiarazione di specializzazione adatta:</span><span class="sxs-lookup"><span data-stu-id="103d7-239">If one or more specializations besides the default body need to be explicitly declared, then the implementation for the default body needs to be wrapped into a suitable specialization declaration as well:</span></span>

```qsharp
operation CountOnes(qubits: Qubit[]) : Int {

    body (...) // default body specialization
    {
        mutable n = 0;
        for (qubit in qubits) {
            set n += M(q) == One ? 1 | 0;
        }
        return n;
    }

    ...
```

### <a name="circumstances-for-validly-defining-specializations"></a><span data-ttu-id="103d7-240">Circostanze per la definizione valida delle specializzazioni</span><span class="sxs-lookup"><span data-stu-id="103d7-240">Circumstances for validly defining specializations</span></span>

#### <a name="operation-declarations-with-adjointcontrolled"></a><span data-ttu-id="103d7-241">Dichiarazioni di operazione con contiguo/controllato</span><span class="sxs-lookup"><span data-stu-id="103d7-241">Operation declarations with adjoint/controlled</span></span>

<span data-ttu-id="103d7-242">È lecito specificare un'operazione senza versioni contigue o controllate.</span><span class="sxs-lookup"><span data-stu-id="103d7-242">It is legal to specify an operation with no adjoint or controlled versions.</span></span> <span data-ttu-id="103d7-243">Ad esempio, le operazioni di misurazione non hanno nessuno, perché non sono invertibili o controllabili.</span><span class="sxs-lookup"><span data-stu-id="103d7-243">For instance, measurement operations have neither, because they are not invertible or controllable.</span></span>

<span data-ttu-id="103d7-244">Un'operazione supporta `Adjoint` e/o `Controlled` funtori se la relativa dichiarazione contiene una dichiarazione implicita o esplicita delle rispettive specializzazioni.</span><span class="sxs-lookup"><span data-stu-id="103d7-244">An operation supports the `Adjoint` and/or `Controlled` functors if its declaration contains an implicit or explicit declaration of the respective specializations.</span></span>

<span data-ttu-id="103d7-245">Una specializzazione annullata o controllata dichiarata in modo esplicito implica l'esistenza di una specializzazione contigua/controllata.</span><span class="sxs-lookup"><span data-stu-id="103d7-245">An explicitly declared adjoint/controlled specialization implies the existence of an adjoint/controlled specialization.</span></span> 

<span data-ttu-id="103d7-246">Per un'operazione il cui corpo contiene cicli di ripetizione fino al completamento, istruzioni set, misure, istruzioni return o chiamate ad altre operazioni che non supportano il `Adjoint` functor, la generazione automatica di una specializzazione contigua che segue la `invert` `auto` direttiva o non è possibile.</span><span class="sxs-lookup"><span data-stu-id="103d7-246">For an operation whose body contains repeat-until-success loops, set statements, measurements, return statements, or calls to other operations that do not support the `Adjoint` functor, auto-generating an adjoint specialization following the `invert` or `auto` directive is not possible.</span></span>

<span data-ttu-id="103d7-247">Per un'operazione il cui corpo contiene chiamate ad altre operazioni che non supportano il `Controlled` functor, non è possibile generare automaticamente una specializzazione controllata che segue la `distribute` `auto` direttiva o.</span><span class="sxs-lookup"><span data-stu-id="103d7-247">For an operation whose body contains calls to other operations that does not support the `Controlled` functor, auto-generating a controlled specialization following the `distribute` or `auto` directive is not possible.</span></span>

#### <a name="controlled-adjoint"></a><span data-ttu-id="103d7-248">Contiguo controllato</span><span class="sxs-lookup"><span data-stu-id="103d7-248">Controlled Adjoint</span></span>

<span data-ttu-id="103d7-249">La versione controllata contigua di un'operazione specifica il modo in cui viene implementata una versione controllata da Quantum del contiguo dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="103d7-249">The controlled adjoint version of an operation specifies how a quantum-controlled version of the adjoint of the operation is implemented.</span></span>
<span data-ttu-id="103d7-250">È lecito specificare un'operazione senza una versione controllata contigua. ad esempio, le operazioni di misurazione non hanno una versione controllata contigua, perché non sono controllabili né invertibili.</span><span class="sxs-lookup"><span data-stu-id="103d7-250">It is legal to specify an operation with no controlled adjoint version; for instance, measurement operations have no controlled adjoint version because they are neither controllable nor invertible.</span></span>

<span data-ttu-id="103d7-251">Una specializzazione contigua controllata per un'operazione deve esistere solo se sono presenti sia una specializzazione contigua che una specializzazione controllata.</span><span class="sxs-lookup"><span data-stu-id="103d7-251">A controlled adjoint specialization for an operation needs to exist if and only if both an adjoint and a controlled specialization exist.</span></span> <span data-ttu-id="103d7-252">In tal caso, viene dedotta l'esistenza della specializzazione contigua controllata e una specializzazione appropriata viene generata dal compilatore se nessuna implementazione è stata definita in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="103d7-252">In that case, the existence of the controlled adjoint specialization is inferred and an appropriate specialization is generated by the compiler if no implementation has been defined explicitly.</span></span> 

<span data-ttu-id="103d7-253">Per un'operazione il cui corpo contiene chiamate ad altre operazioni che non dispongono di una versione controllata contigua, la generazione automatica di una specializzazione contigua che segue la `invert` `distribute` direttiva, o `auto` non è possibile.</span><span class="sxs-lookup"><span data-stu-id="103d7-253">For an operation whose body contains calls to other operations that do not have a controlled adjoint version, auto-generating an adjoint specialization following the `invert`, `distribute` or `auto` directive is not possible.</span></span>


### <a name="type-compatibility"></a><span data-ttu-id="103d7-254">Compatibilità tra tipi</span><span class="sxs-lookup"><span data-stu-id="103d7-254">Type Compatibility</span></span>

<span data-ttu-id="103d7-255">Un'operazione con funtori aggiuntivi supportata può essere usata ovunque un'operazione con un numero di funtori inferiore ma è prevista la stessa firma.</span><span class="sxs-lookup"><span data-stu-id="103d7-255">An operation with additional functors supported may be used anywhere an operation with fewer functors but the same signature is expected.</span></span>
<span data-ttu-id="103d7-256">Ad esempio, un'operazione di tipo `(Qubit => Unit is Adj)` può essere utilizzata ovunque sia prevista un'operazione di tipo `(Qubit => Unit)` .</span><span class="sxs-lookup"><span data-stu-id="103d7-256">For instance, an operation of type `(Qubit => Unit is Adj)` may be used anywhere an operation of type `(Qubit => Unit)` is expected.</span></span>

<span data-ttu-id="103d7-257">Q # è *covariante* rispetto ai tipi restituiti richiamabili: un oggetto chiamabile che restituisce un tipo `'A` è compatibile con un oggetto chiamabile con lo stesso tipo di input e un tipo di risultato `'A` compatibile con.</span><span class="sxs-lookup"><span data-stu-id="103d7-257">Q# is *covariant* with respect to callable return types: a callable that returns a type `'A` is compatible with a callable with the same input type and a result type that `'A` is compatible with.</span></span>

<span data-ttu-id="103d7-258">Q # è *controvariante* rispetto ai tipi di input: un oggetto chiamabile che accetta un tipo `'A` come input è compatibile con un oggetto chiamabile con lo stesso tipo di risultato e un tipo di input compatibile con `'A` .</span><span class="sxs-lookup"><span data-stu-id="103d7-258">Q# is *contravariant* with respect to input types: a callable that takes a type `'A` as input is compatible with a callable with the same result type and an input type that is compatible with `'A`.</span></span>

<span data-ttu-id="103d7-259">Ovvero, date le seguenti definizioni:</span><span class="sxs-lookup"><span data-stu-id="103d7-259">That is, given the following definitions:</span></span>

```qsharp
operation Invert(qubits : Qubit[]) : Unit 
is Adj {...} 

operation ApplyUnitary(qubits : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertWith(
    inner : (Qubit[] => Unit is Adj),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith(
    inner : (Qubit[] => Unit is Adj + Ctl),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

<span data-ttu-id="103d7-260">sono soddisfatte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="103d7-260">the following are true:</span></span>

- <span data-ttu-id="103d7-261">La funzione `ConjugateInvertWith` può essere richiamata con un `inner` argomento di `Invert` o `ApplyUnitary` .</span><span class="sxs-lookup"><span data-stu-id="103d7-261">The function `ConjugateInvertWith` may be invoked with an `inner` argument of either `Invert` or `ApplyUnitary`.</span></span>
- <span data-ttu-id="103d7-262">La funzione `ConjugateUnitaryWith` può essere richiamata con un `inner` argomento di `ApplyUnitary` , ma non `Invert` .</span><span class="sxs-lookup"><span data-stu-id="103d7-262">The function `ConjugateUnitaryWith` may be invoked with an `inner` argument of `ApplyUnitary`, but not `Invert`.</span></span>
- <span data-ttu-id="103d7-263">Un valore di tipo `(Qubit[] => Unit is Adj + Ctl)` può essere restituito da `ConjugateInvertWith` .</span><span class="sxs-lookup"><span data-stu-id="103d7-263">A value of type `(Qubit[] => Unit is Adj + Ctl)` may be returned from `ConjugateInvertWith`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="103d7-264">Q # 0,3 ha introdotto una differenza significativa nel comportamento dei tipi definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="103d7-264">Q# 0.3 introduced a significant difference in the behavior of user-defined types.</span></span>

<span data-ttu-id="103d7-265">I tipi definiti dall'utente vengono considerati come una versione di cui è stato eseguito il wrapped del tipo sottostante, anziché come sottotipo.</span><span class="sxs-lookup"><span data-stu-id="103d7-265">User-defined types are treated as a wrapped version of the underlying type, rather than as a subtype.</span></span>
<span data-ttu-id="103d7-266">Ciò significa che un valore di un tipo definito dall'utente non può essere utilizzato quando è previsto un valore del tipo sottostante.</span><span class="sxs-lookup"><span data-stu-id="103d7-266">This means that a value of a user-defined type is not usable where a value of the underlying type is expected.</span></span>


### <a name="conjugations"></a><span data-ttu-id="103d7-267">Coniugazioni</span><span class="sxs-lookup"><span data-stu-id="103d7-267">Conjugations</span></span>

<span data-ttu-id="103d7-268">A differenza dei bit classici, il rilascio della memoria quantistica è leggermente più coinvolto, perché la reimpostazione cieca di qubits può avere effetti indesiderati sul calcolo rimanente se il qubits è ancora stato impigliato.</span><span class="sxs-lookup"><span data-stu-id="103d7-268">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="103d7-269">Questa operazione può essere evitata eseguendo correttamente i calcoli eseguiti prima di rilasciare la memoria.</span><span class="sxs-lookup"><span data-stu-id="103d7-269">This can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="103d7-270">Un modello comune in quantum computing è quindi il seguente:</span><span class="sxs-lookup"><span data-stu-id="103d7-270">A common pattern in quantum computing is hence the following:</span></span> 

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    outerOperation(target);
    innerOperation(target);
    Adjoint outerOperation(target);
}
```

<span data-ttu-id="103d7-271">A partire dalla versione 0,9, è supportata un'istruzione di coniugazione che implementa la trasformazione precedente.</span><span class="sxs-lookup"><span data-stu-id="103d7-271">Starting with our 0.9 release, we support a conjugation statement that implements the transformation above.</span></span> <span data-ttu-id="103d7-272">Utilizzando tale istruzione, `ApplyWith` è possibile implementare l'operazione nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="103d7-272">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    within{ 
        outerOperation(target);
    }
    apply {
        innerOperation(target);
    }
}
```
<span data-ttu-id="103d7-273">Tale istruzione di coniugazione, ovviamente, diventa molto più utile se la trasformazione esterna e interna non è immediatamente disponibile come operazione, ma è più semplice da descrivere da un blocco composto da diverse istruzioni.</span><span class="sxs-lookup"><span data-stu-id="103d7-273">Such a conjugation statement obviously becomes far more useful if the outer and inner transformation are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="103d7-274">La trasformazione inversa per le istruzioni definite nel blocco interno viene generata automaticamente dal compilatore ed eseguita al termine del blocco Apply.</span><span class="sxs-lookup"><span data-stu-id="103d7-274">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and executed after the apply-block completes.</span></span>
<span data-ttu-id="103d7-275">Poiché le variabili modificabili usate come parte del blocco all'interno non possono essere riassociati nel blocco Apply, la trasformazione generata è sicuramente l'elemento contiguo del calcolo nel blocco all'interno.</span><span class="sxs-lookup"><span data-stu-id="103d7-275">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 


## <a name="defining-new-functions"></a><span data-ttu-id="103d7-276">Definizione di nuove funzioni</span><span class="sxs-lookup"><span data-stu-id="103d7-276">Defining New Functions</span></span>

<span data-ttu-id="103d7-277">Le funzioni sono puramente deterministiche, ovvero routine classiche in Q #, diverse dalle operazioni in quanto non possono avere effetti oltre il calcolo di un valore di output.</span><span class="sxs-lookup"><span data-stu-id="103d7-277">Functions are purely deterministic, classical routines in Q#, which are distinct from operations in that they are not allowed to have any effects beyond calculating an output value.</span></span>
<span data-ttu-id="103d7-278">In particolare, le funzioni non possono chiamare operazioni; agire, allocare o prendere in prestito qubits; numeri casuali di esempio; o altrimenti dipendono dallo stato oltre il valore di input per una funzione.</span><span class="sxs-lookup"><span data-stu-id="103d7-278">In particular, functions cannot call operations; act on, allocate, or borrow qubits; sample random numbers; or otherwise depend on state beyond the input value to a function.</span></span>
<span data-ttu-id="103d7-279">Di conseguenza, le funzioni Q # sono *pure*, in quanto eseguono sempre il mapping degli stessi valori di input agli stessi valori di output.</span><span class="sxs-lookup"><span data-stu-id="103d7-279">As a consequence, Q# functions are *pure*, in that they always map the same input values to the same output values.</span></span>
<span data-ttu-id="103d7-280">Ciò consente al compilatore Q # di riordinare in modo sicuro come e quando le funzioni vengono chiamate quando si generano specializzazioni delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="103d7-280">This allows the Q# compiler to safely reorder how and when functions are called when generating operation specializations.</span></span>

<span data-ttu-id="103d7-281">Ogni file di origine Q # può definire un numero qualsiasi di funzioni.</span><span class="sxs-lookup"><span data-stu-id="103d7-281">Each Q# source file may define any number of functions.</span></span>
<span data-ttu-id="103d7-282">I nomi di funzione devono essere univoci all'interno di uno spazio dei nomi e non possono entrare in conflitto con i nomi di operazione o</span><span class="sxs-lookup"><span data-stu-id="103d7-282">Function names must be unique within a namespace and may not conflict with operation or type names.</span></span>

<span data-ttu-id="103d7-283">La definizione di una funzione funziona in modo analogo alla definizione di un'operazione, ad eccezione del fatto che non è possibile definire alcuna specializzazioni contigua o controllata per una funzione.</span><span class="sxs-lookup"><span data-stu-id="103d7-283">Defining a function works similarly to defining an operation, except that no adjoint or controlled specializations can be defined for a function.</span></span>
<span data-ttu-id="103d7-284">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="103d7-284">For instance:</span></span>

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```

<span data-ttu-id="103d7-285">Oppure</span><span class="sxs-lookup"><span data-stu-id="103d7-285">or</span></span> 

```qsharp
function DotProduct(a : Double[], b : Double[]) : Double {
    if (Length(a) != Length(b)) {
        fail "Arrays are not compatible";
    }

    mutable accum = 0.0;
    for (i in 0..Length(a)-1) {
        set accum += a[i] * b[i];
    }
    return accum;
}
```

### <a name="classical-logic-in-functions--good"></a><span data-ttu-id="103d7-286">Logica classica nelle funzioni = = corretta</span><span class="sxs-lookup"><span data-stu-id="103d7-286">Classical logic in functions == good</span></span>

<span data-ttu-id="103d7-287">Quando è possibile eseguire questa operazione, è utile scrivere la logica classica in termini di funzioni anziché di operazioni, in modo che possa essere usata più facilmente all'interno di operazioni.</span><span class="sxs-lookup"><span data-stu-id="103d7-287">Whenever it is possible to do so, it is helpful to write out classical logic in terms of functions rather than operations, so that it can be more readily used from within operations.</span></span>
<span data-ttu-id="103d7-288">Se ad esempio è stata scritta la `Square` dichiarazione precedente come *operazione*, il compilatore non sarebbe stato in grado di garantire che la chiamata con lo stesso input produrrebbe sempre gli stessi output.</span><span class="sxs-lookup"><span data-stu-id="103d7-288">For example, if we had written the `Square` declaration above as an *operation*, then the compiler would not have been able to guarantee that calling it with the same input would consistently produce the same outputs.</span></span>

<span data-ttu-id="103d7-289">Per sottolineare la differenza tra funzioni e operazioni, prendere in considerazione il problema di campionamento classico di un numero casuale da un'operazione Q #:</span><span class="sxs-lookup"><span data-stu-id="103d7-289">To underscore the difference between functions and operations, consider the problem of classically sampling a random number from within a Q# operation:</span></span>

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

<span data-ttu-id="103d7-290">Ogni volta che `U` viene chiamato, avrà un'azione diversa su `target` .</span><span class="sxs-lookup"><span data-stu-id="103d7-290">Each time that `U` is called, it will have a different action on `target`.</span></span>
<span data-ttu-id="103d7-291">In particolare, il compilatore non è in grado di garantire che se è stata aggiunta una `adjoint auto` dichiarazione di specializzazione a `U` , `U(target); Adjoint U(target);` funge da identità, ovvero come no-op.</span><span class="sxs-lookup"><span data-stu-id="103d7-291">In particular, the compiler cannot guarantee that if we added an `adjoint auto` specialization declaration to `U`, then `U(target); Adjoint U(target);` acts as identity (that is, as a no-op).</span></span>
<span data-ttu-id="103d7-292">In questo modo si viola la definizione del contiguo che è stato osservato in [vettori e matrici](xref:microsoft.quantum.concepts.vectors), in modo che la possibilità di generare automaticamente una specializzazione contigua in un'operazione in cui è stata chiamata l'operazione <xref:microsoft.quantum.math.randomreal> interrompa le garanzie fornite dal compilatore. <xref:microsoft.quantum.math.randomreal> è un'operazione per la quale non esiste alcuna versione contigua o controllata.</span><span class="sxs-lookup"><span data-stu-id="103d7-292">This violates the definition of the adjoint that we saw in [Vectors and Matrices](xref:microsoft.quantum.concepts.vectors), such that allowing to auto-generate an adjoint specialization in an operation where we have called the operation <xref:microsoft.quantum.math.randomreal> would break the guarantees provided by the compiler; <xref:microsoft.quantum.math.randomreal> is an operation for which no adjoint or controlled version exists.</span></span>

<span data-ttu-id="103d7-293">D'altra parte, consentire le chiamate di funzione come `Square` è sicuro, in quanto è possibile garantire che il compilatore debba solo conservare l'input per garantire la `Square` stabilità dell'output.</span><span class="sxs-lookup"><span data-stu-id="103d7-293">On the other hand, allowing function calls such as `Square` is safe, in that the compiler can be assured that it only needs to preserve the input to `Square` in order to keep its output stable.</span></span>
<span data-ttu-id="103d7-294">In questo modo, l'isolamento della logica classica più possibile in funzioni semplifica il riutilizzo di tale logica in altre funzioni e operazioni.</span><span class="sxs-lookup"><span data-stu-id="103d7-294">Thus, isolating as much classical logic as possible into functions makes it easy to reuse that logic in other functions and operations alike.</span></span>


## <a name="generic-type-parameterized-callables"></a><span data-ttu-id="103d7-295">Chiamabili generici (con parametri di tipo)</span><span class="sxs-lookup"><span data-stu-id="103d7-295">Generic (Type-Parameterized) Callables</span></span>

<span data-ttu-id="103d7-296">Molte funzioni e operazioni che è possibile definire non si basano molto sui tipi di input, ma usano solo i tipi in modo implicito tramite un'altra funzione o un'altra operazione.</span><span class="sxs-lookup"><span data-stu-id="103d7-296">Many functions and operations that we might wish to define do not actually heavily rely on the types of their inputs, but rather only implicitly use their types via some other function or operation.</span></span>
<span data-ttu-id="103d7-297">Si consideri, ad esempio, il concetto di *mappa* comune a molti linguaggi funzionali; Data una funzione $f (x) $ e una raccolta di valori $ \{ X_1, x_2, \dots, x_n \} $, map restituisce una nuova raccolta $ \{ f (X_1), f (x_2), \dots, f (x_n) \} $.</span><span class="sxs-lookup"><span data-stu-id="103d7-297">For example, consider the *map* concept common to many functional languages; given a function $f(x)$ and a collection of values $\{x_1, x_2, \dots, x_n\}$, map returns a new collection $\{f(x_1), f(x_2), \dots, f(x_n)\}$.</span></span>
<span data-ttu-id="103d7-298">Per implementarlo in Q #, è possibile sfruttare le funzioni che sono la prima classe.</span><span class="sxs-lookup"><span data-stu-id="103d7-298">To implement this in Q#, we can take advantage of that functions are first class.</span></span>
<span data-ttu-id="103d7-299">Viene ora illustrato un esempio rapido di `Map` utilizzo di ★ come segnaposto, mentre è possibile individuare i tipi necessari.</span><span class="sxs-lookup"><span data-stu-id="103d7-299">Let's write out a quick example of `Map`, using ★ as a placeholder while we figure out what types we need.</span></span>

```qsharp
function Map(fn : (★ -> ★), values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="103d7-300">Nota Questa funzione è molto simile indipendentemente dai tipi effettivi sostituiti.</span><span class="sxs-lookup"><span data-stu-id="103d7-300">Note this function looks very much the same no matter what actual types we substitute in.</span></span>
<span data-ttu-id="103d7-301">Un mapping da Integer a Paulis, ad esempio, ha un aspetto molto simile a quello di una mappa dai numeri a virgola mobile a stringhe:</span><span class="sxs-lookup"><span data-stu-id="103d7-301">A map from integers to Paulis, for instance, looks much the same as a map from floating-point numbers to strings:</span></span>

```qsharp
function MapIntsToPaulis(fn : (Int -> Pauli), values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : (Double -> String), values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="103d7-302">In linea di principio, è possibile scrivere una versione di `Map` per ogni coppia di tipi incontrata, ma in questo caso è stata introdotta una serie di problemi.</span><span class="sxs-lookup"><span data-stu-id="103d7-302">In principle, we could write a version of `Map` for every pair of types that we encounter, but this introduces a number of difficulties.</span></span>
<span data-ttu-id="103d7-303">Se ad esempio si rileva un bug in `Map` , è necessario assicurarsi che la correzione venga applicata in modo uniforme in tutte le versioni di `Map` .</span><span class="sxs-lookup"><span data-stu-id="103d7-303">For instance, if we find a bug in `Map`, then we must ensure that the fix is applied uniformly across all versions of `Map`.</span></span>
<span data-ttu-id="103d7-304">Inoltre, se si costruisce una nuova tupla o un tipo definito dall'utente, ora è necessario creare anche un nuovo oggetto `Map` da usare con il nuovo tipo.</span><span class="sxs-lookup"><span data-stu-id="103d7-304">Moreover, if we construct a new tuple or UDT, then we must now also construct a new `Map` to go along with the new type.</span></span>
<span data-ttu-id="103d7-305">Sebbene si tratti di un numero ridotto di funzioni di questo tipo, quando si raccolgono più funzioni con lo stesso formato di `Map` , il costo dell'introduzione di nuovi tipi diventa ingiustificatamente grande nell'ordine piuttosto breve.</span><span class="sxs-lookup"><span data-stu-id="103d7-305">While this is tractable for a small number of such functions, as we collect more and more functions of the same form as `Map`, the cost of introducing new types becomes unreasonably large in fairly short order.</span></span>

<span data-ttu-id="103d7-306">Gran parte di questa difficoltà, tuttavia, dal momento che non è stato fornito il compilatore, le informazioni necessarie per riconoscere il modo in cui sono correlate le diverse versioni di `Map` .</span><span class="sxs-lookup"><span data-stu-id="103d7-306">Much of this difficulty results, however, from that the we have not given the compiler the information it needs to recognize how the different versions of `Map` are related.</span></span>
<span data-ttu-id="103d7-307">In realtà, il compilatore si vuole trattare `Map` come un tipo di funzione matematica dai *tipi* q # alle funzioni q #.</span><span class="sxs-lookup"><span data-stu-id="103d7-307">Effectively, we want the compiler to treat `Map` as some kind of mathematical function from Q# *types* to Q# functions.</span></span>

<span data-ttu-id="103d7-308">Questa nozione viene formalizzata consentendo a funzioni e operazioni di avere *parametri di tipo*, nonché i parametri di tupla ordinari.</span><span class="sxs-lookup"><span data-stu-id="103d7-308">This notion is formalized by allowing functions and operations to have *type parameters*, as well as their ordinary tuple parameters.</span></span>
<span data-ttu-id="103d7-309">Negli esempi precedenti si desidera considerare `Map` come avere parametri di tipo `Int, Pauli` nel primo caso e `Double, String` nel secondo caso.</span><span class="sxs-lookup"><span data-stu-id="103d7-309">In the examples above, we wish to think of `Map` as having type parameters `Int, Pauli` in the first case and `Double, String` in the second case.</span></span>
<span data-ttu-id="103d7-310">Nella maggior parte dei casi, questi parametri di tipo possono essere usati come se fossero tipi normali: si usano valori di parametri di tipo per creare matrici e tuple, chiamare funzioni e operazioni e assegnare a variabili ordinarie o modificabili.</span><span class="sxs-lookup"><span data-stu-id="103d7-310">For the most part, these type parameters can then be used as though they were ordinary types: we use values of type parameters to make arrays and tuples, call functions and operations, and assign to ordinary or mutable variables.</span></span>

> [!NOTE]
> <span data-ttu-id="103d7-311">Il caso più estremo della dipendenza indiretta è quello di qubits, in cui un programma Q # non può basarsi direttamente sulla struttura del `Qubit` tipo, ma **deve** passare tali tipi ad altre operazioni e funzioni.</span><span class="sxs-lookup"><span data-stu-id="103d7-311">The most extreme case of indirect dependence is that of qubits, where a Q# program cannot directly rely on the structure of the `Qubit` type, but **must** pass such types to other operations and functions.</span></span>

<span data-ttu-id="103d7-312">Tornando all'esempio precedente, è possibile vedere che è necessario `Map` disporre di parametri di tipo, uno per rappresentare l'input `fn` e uno per rappresentare l'output da `fn` .</span><span class="sxs-lookup"><span data-stu-id="103d7-312">Returning to the example above, then, we can see that we need `Map` to have type parameters, one to represent the input to `fn` and one to represent the output from `fn`.</span></span>
<span data-ttu-id="103d7-313">In Q # questo viene scritto aggiungendo parentesi angolari (ovvero `<>` , non i Brake $ \braket {} $!) dopo il nome di una funzione o di un'operazione nella relativa dichiarazione e elencando ogni parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="103d7-313">In Q#, this is written by adding angle brackets (that's `<>`, not brakets $\braket{}$!) after the name of a function or operation in its declaration, and by listing each type parameter.</span></span>
<span data-ttu-id="103d7-314">Il nome di ogni parametro di tipo deve iniziare con un segno di indicizzazione `'` , a indicare che si tratta di un parametro di tipo e non di un tipo ordinario (noto anche come tipo *concreto* ).</span><span class="sxs-lookup"><span data-stu-id="103d7-314">The name of each type parameter must start with a tick `'`, indicating that it is a type parameter and not a ordinary type (also known as a *concrete* type).</span></span>
<span data-ttu-id="103d7-315">Per `Map` , scriviamo quindi:</span><span class="sxs-lookup"><span data-stu-id="103d7-315">For `Map`, we thus write:</span></span>

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="103d7-316">Si noti che la definizione di `Map<'Input, 'Output>` ha un aspetto molto simile a quello delle versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="103d7-316">Note that the definition of `Map<'Input, 'Output>` looks extremely similar to the versions we wrote out before.</span></span>
<span data-ttu-id="103d7-317">L'unica differenza consiste nel fatto che il compilatore è stato informato in modo esplicito che `Map` non dipende direttamente da quali `'Input` e `'Output` sono, ma funziona per due tipi utilizzandoli indirettamente tramite `fn` .</span><span class="sxs-lookup"><span data-stu-id="103d7-317">The only difference is that we have explicitly informed the compiler that `Map` doesn't directly depend on what `'Input` and `'Output` are, but works for any two types by using them indirectly through `fn`.</span></span>
<span data-ttu-id="103d7-318">Una volta definito `Map<'Input, 'Output>` in questo modo, è possibile chiamarlo come se fosse una funzione ordinaria:</span><span class="sxs-lookup"><span data-stu-id="103d7-318">Once we have defined `Map<'Input, 'Output>` in this way, we can call it as though it was an ordinary function:</span></span>

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> <span data-ttu-id="103d7-319">La scrittura di funzioni e funzioni generiche è un'unica posizione in cui "tuple-in tuple-out" è un modo utile per considerare le funzioni e le operazioni Q #.</span><span class="sxs-lookup"><span data-stu-id="103d7-319">Writing generic functions and operations is one place where "tuple-in tuple-out" is a very useful way to think about Q# functions and operations.</span></span>
> <span data-ttu-id="103d7-320">Poiché ogni funzione accetta esattamente un input e restituisce esattamente un output, un input di tipo `'T -> 'U` corrisponde a *qualsiasi* funzione Q #.</span><span class="sxs-lookup"><span data-stu-id="103d7-320">Since every function takes exactly one input and returns exactly one output, an input of type `'T -> 'U` matches *any* Q# function whatsoever.</span></span>
> <span data-ttu-id="103d7-321">Analogamente, qualsiasi operazione può essere passata a un input di tipo `'T => 'U` .</span><span class="sxs-lookup"><span data-stu-id="103d7-321">Similarly, any operation can be passed to an input of type `'T => 'U`.</span></span>

<span data-ttu-id="103d7-322">Come secondo esempio, si consideri la necessità di scrivere una funzione che restituisce la composizione di altre due funzioni:</span><span class="sxs-lookup"><span data-stu-id="103d7-322">As a second example, consider the challenge of writing a function that returns the composition of two other functions:</span></span>

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="103d7-323">In questo caso, è necessario specificare esattamente cosa `A` , `B` e `C` sono, di conseguenza la limitazione dell'utilità della nuova `Compose` funzione.</span><span class="sxs-lookup"><span data-stu-id="103d7-323">Here, we must specify exactly what `A`, `B`, and `C` are, hence severely limiting the utility of our new `Compose` function.</span></span>
<span data-ttu-id="103d7-324">Dopo tutto, `Compose` dipende solo da `A` , `B` e `C` *tramite* `innerFn` e `outerFn` .</span><span class="sxs-lookup"><span data-stu-id="103d7-324">After all, `Compose` only depends on `A`, `B`, and `C` *via* `innerFn` and `outerFn`.</span></span>
<span data-ttu-id="103d7-325">In alternativa, è possibile aggiungere parametri di tipo a `Compose` che indicano che funziona per *qualsiasi* `A` , `B` e `C` , purché questi parametri corrispondano a quelli previsti da `innerFn` e `outerFn` :</span><span class="sxs-lookup"><span data-stu-id="103d7-325">As an alternative, then, we can add type parameters to `Compose` that indicate that it works for *any* `A`, `B`, and `C`, so long as these parameters match those expected by `innerFn` and `outerFn`:</span></span>

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="103d7-326">Le librerie standard Q # forniscono una serie di operazioni e funzioni con parametri di tipo per semplificare l'espressione del flusso di controllo di ordine superiore.</span><span class="sxs-lookup"><span data-stu-id="103d7-326">The Q# standard libraries provide a range of such type-parameterized operations and functions to make higher-order control flow easier to express.</span></span>
<span data-ttu-id="103d7-327">Questi argomenti sono illustrati più avanti nella [Guida alla libreria standard Q #](xref:microsoft.quantum.libraries.standard.intro).</span><span class="sxs-lookup"><span data-stu-id="103d7-327">These are discussed further in the [Q# standard library guide](xref:microsoft.quantum.libraries.standard.intro).</span></span>


## <a name="callables-as-first-class-values"></a><span data-ttu-id="103d7-328">Chiamabili come valori di prima classe</span><span class="sxs-lookup"><span data-stu-id="103d7-328">Callables as First-Class Values</span></span>

<span data-ttu-id="103d7-329">Una tecnica critica per ragionare sul flusso di controllo e la logica classica con funzioni anziché operazioni consiste nell'usare le operazioni e le funzioni in Q # sono di *prima classe*.</span><span class="sxs-lookup"><span data-stu-id="103d7-329">One critical technique for reasoning about control flow and classical logic using functions rather than operations is to utilize that operations and functions in Q# are *first-class*.</span></span>
<span data-ttu-id="103d7-330">Ovvero ciascuno dei quali è il linguaggio di propria scelta.</span><span class="sxs-lookup"><span data-stu-id="103d7-330">That is, they are each values in the language in their own right.</span></span>
<span data-ttu-id="103d7-331">Ad esempio, di seguito è riportato un codice Q # perfettamente valido, se poco indiretto:</span><span class="sxs-lookup"><span data-stu-id="103d7-331">For instance, the following is perfectly valid Q# code, if a little indirect:</span></span>

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

<span data-ttu-id="103d7-332">Il valore della variabile `ourH` nel frammento di codice precedente è quindi l'operazione <xref:microsoft.quantum.intrinsic.h> , in modo che sia possibile chiamare tale valore come qualsiasi altra operazione.</span><span class="sxs-lookup"><span data-stu-id="103d7-332">The value of the variable `ourH` in the snippet above is then the operation <xref:microsoft.quantum.intrinsic.h>, such that we can call that value like any other operation.</span></span>
<span data-ttu-id="103d7-333">In questo modo è possibile scrivere operazioni che accettano operazioni come parte dell'input, formando concetti di flusso di controllo di ordine superiore.</span><span class="sxs-lookup"><span data-stu-id="103d7-333">This allows us to write operations that take operations as a part of their input, forming higher-order control flow concepts.</span></span>
<span data-ttu-id="103d7-334">Si supponga, ad esempio, di voler "quadrare" un'operazione applicando due volte lo stesso qubit di destinazione.</span><span class="sxs-lookup"><span data-stu-id="103d7-334">For instance, we could imagine wanting to "square" an operation by applying it twice to the same target qubit.</span></span>

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a><span data-ttu-id="103d7-335">Restituzione di operazioni da una funzione</span><span class="sxs-lookup"><span data-stu-id="103d7-335">Returning operations from a function</span></span>

<span data-ttu-id="103d7-336">Si evidenzia che è anche possibile restituire le operazioni come parte degli output, in modo da poter isolare alcuni tipi di logica condizionale classica come una funzione classica che restituisce una descrizione di un programma Quantum sotto forma di operazione.</span><span class="sxs-lookup"><span data-stu-id="103d7-336">We emphasize that we can also return operations as a part of outputs, such that we can isolate some kinds of classical conditional logic as a classical function which returns a description of a quantum program in the form of an operation.</span></span>
<span data-ttu-id="103d7-337">Come esempio semplice, si consideri l'esempio di Teleporting, in cui la parte che riceve un messaggio classico a due bit deve usare il messaggio per decodificare i qubit nello stato di teleporte appropriato.</span><span class="sxs-lookup"><span data-stu-id="103d7-337">As a simple example, consider the teleportation example, in which the party receiving a two-bit classical message needs to use the message to decode their qubit into the proper teleported state.</span></span>
<span data-ttu-id="103d7-338">È possibile scrivere questo risultato in termini di funzione che accetta i due bit classici e restituisce l'operazione di decodifica corretta.</span><span class="sxs-lookup"><span data-stu-id="103d7-338">We could write this in terms of a function that takes those two classical bits and returns the proper decoding operation.</span></span>

```qsharp
function TeleporationDecoderForMessage(hereBit : Result, thereBit : Result)
: (Qubit => Unit is Adj + Ctl) {

    if (hereBit == Zero && thereBit == Zero) {
        return I;
    } elif (hereBit == One && thereBit == Zero) {
        return X;
    } elif (hereBit == Zero && thereBit == One) {
        return Z;
    } else {
        return Y;
    }
}
```

<span data-ttu-id="103d7-339">Questa nuova funzione è effettivamente una funzione, in quanto se viene chiamata con gli stessi valori di `hereBit` e `thereBit` , viene sempre restituita la stessa operazione.</span><span class="sxs-lookup"><span data-stu-id="103d7-339">This new function is indeed a function, in that if we call it with the same values of `hereBit` and `thereBit`, we will always get back the same operation.</span></span>
<span data-ttu-id="103d7-340">Pertanto, il decodificatore può essere eseguito in modo sicuro all'interno di operazioni senza dover ragionare sul modo in cui la logica di decodifica interagisce con le definizioni delle diverse specializzazioni delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="103d7-340">Thus, the decoder can be safely run inside operations without having to reason about how the decoding logic interacts with the definitions of the different operation specializations.</span></span>
<span data-ttu-id="103d7-341">Ovvero è stata isolata la logica classica all'interno di una funzione, garantendo al compilatore che la chiamata di funzione possa essere riordinata con impuneità purché l'input venga mantenuto.</span><span class="sxs-lookup"><span data-stu-id="103d7-341">That is, we have isolated the classical logic inside a function, guaranteeing to the compiler that the function call can be reordered with impunity so long as the input is preserved.</span></span>


## <a name="partial-application"></a><span data-ttu-id="103d7-342">Applicazione parziale</span><span class="sxs-lookup"><span data-stu-id="103d7-342">Partial Application</span></span>

<span data-ttu-id="103d7-343">È possibile eseguire molte altre operazioni con funzioni che restituiscono operazioni usando un' *applicazione parziale*, in cui è possibile fornire una o più parti dell'input a una funzione o a un'operazione senza chiamarla effettivamente.</span><span class="sxs-lookup"><span data-stu-id="103d7-343">We can do significantly more with functions that return operations by using *partial application*, in which we can provide one or more parts of the input to a function or operation without actually calling it.</span></span> <span data-ttu-id="103d7-344">Ad esempio, richiamando l' `ApplyTwice` esempio precedente, è possibile indicare che non si vuole specificare, immediatamente, a quale qubit deve essere applicata l'operazione di input:</span><span class="sxs-lookup"><span data-stu-id="103d7-344">For example, recalling the `ApplyTwice` example above, we can indicate that we don't want to specify, right away, to which qubit the input operation should apply:</span></span>

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

<span data-ttu-id="103d7-345">In questo caso, la variabile locale `twiceOp` contiene l'operazione parzialmente applicata `ApplyTwice(op, _)` , in cui le parti dell'input che non sono state ancora specificate sono indicate `_` da.</span><span class="sxs-lookup"><span data-stu-id="103d7-345">In this case, the local variable `twiceOp` holds the partially applied operation `ApplyTwice(op, _)`, where parts of the input that have not yet been specified are indicated by `_`.</span></span>
<span data-ttu-id="103d7-346">Quando si chiama effettivamente `twiceOp` nella riga successiva, viene passato come input all'operazione parzialmente applicata tutte le parti rimanenti dell'input per l'operazione originale.</span><span class="sxs-lookup"><span data-stu-id="103d7-346">When we actually call `twiceOp` in the next line, we pass as input to the partially applied operation all of the remaining parts of the input to the original operation.</span></span>
<span data-ttu-id="103d7-347">Pertanto, il frammento di codice precedente è effettivamente identico alla chiamata `ApplyTwice(op, target)` diretta, salvo per il fatto che è stata introdotta una nuova variabile locale che consente di ritardare la chiamata fornendo alcune parti dell'input.</span><span class="sxs-lookup"><span data-stu-id="103d7-347">Thus, the above snippet is effectively identical to having called `ApplyTwice(op, target)` directly, save for that we have introduced a new local variable that allows us to delay the call while providing some parts of the input.</span></span>

<span data-ttu-id="103d7-348">Poiché un'operazione che è stata applicata parzialmente non viene effettivamente chiamata fino a quando non è stato fornito l'intero input, è possibile applicare parzialmente in modo sicuro le operazioni anche dalle funzioni.</span><span class="sxs-lookup"><span data-stu-id="103d7-348">Since an operation that has been partially applied is not actually called until its entire input has been provided, we can safely partially apply operations even from within functions.</span></span>

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

<span data-ttu-id="103d7-349">In linea di base, la logica classica in `SquareOperation` potrebbe essere stata molto più complessa, ma è ancora isolata dal resto di un'operazione garantita dal fatto che il compilatore possa offrire informazioni sulle funzioni.</span><span class="sxs-lookup"><span data-stu-id="103d7-349">In principle, the classical logic within `SquareOperation` could have been much more involved, but it is still isolated from the rest of an operation by the guarantees that the compiler can offer about functions.</span></span>
<span data-ttu-id="103d7-350">Questo approccio verrà usato in tutta la libreria standard Q # per esprimere il flusso di controllo classico in modo da poter essere usato facilmente nei programmi Quantum.</span><span class="sxs-lookup"><span data-stu-id="103d7-350">This approach will be used throughout the Q# standard library for expressing classical control flow in a way that can be readily used within quantum programs.</span></span>


## <a name="recursion"></a><span data-ttu-id="103d7-351">Ricorsione</span><span class="sxs-lookup"><span data-stu-id="103d7-351">Recursion</span></span>

<span data-ttu-id="103d7-352">D # i chiamabili possono essere ricorsivi direttamente o indirettamente.</span><span class="sxs-lookup"><span data-stu-id="103d7-352">Q# callables are allowed to be directly or indirectly recursive.</span></span>
<span data-ttu-id="103d7-353">Ovvero, un'operazione o una funzione può chiamare se stessa oppure può chiamare un altro oggetto chiamabile che chiama direttamente o indirettamente l'operazione chiamabile.</span><span class="sxs-lookup"><span data-stu-id="103d7-353">That is, an operation or function may call itself, or it may call another callable that directly or indirectly calls the callable operation.</span></span>

<span data-ttu-id="103d7-354">Sono tuttavia disponibili due commenti importanti sull'utilizzo della ricorsione:</span><span class="sxs-lookup"><span data-stu-id="103d7-354">There are two important comments about the use of recursion, however:</span></span>

- <span data-ttu-id="103d7-355">L'uso della ricorsione nelle operazioni potrebbe interferire con determinate ottimizzazioni.</span><span class="sxs-lookup"><span data-stu-id="103d7-355">The use of recursion in operations is likely to interfere with certain optimizations.</span></span>
  <span data-ttu-id="103d7-356">Questo può avere un notevole effetto sul tempo di esecuzione dell'algoritmo.</span><span class="sxs-lookup"><span data-stu-id="103d7-356">This may have a substantial impact on the execution time of the algorithm.</span></span>
- <span data-ttu-id="103d7-357">Quando si esegue su un dispositivo Quantum effettivo, lo spazio dello stack può essere limitato e pertanto la ricorsione profonda può causare un errore di Runtime.</span><span class="sxs-lookup"><span data-stu-id="103d7-357">When executing on an actual quantum device, stack space may be limited, and so deep recursion may lead to a runtime error.</span></span>
  <span data-ttu-id="103d7-358">In particolare, il compilatore e il runtime Q # non identificano e ottimizzano la ricorsione Tail.</span><span class="sxs-lookup"><span data-stu-id="103d7-358">In particular, the Q# compiler and runtime do not identify and optimize tail recursion.</span></span>

## <a name="next-steps"></a><span data-ttu-id="103d7-359">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="103d7-359">Next steps</span></span>

<span data-ttu-id="103d7-360">Informazioni sulle [variabili](xref:microsoft.quantum.guide.variables) in Q #.</span><span class="sxs-lookup"><span data-stu-id="103d7-360">Learn about [Variables](xref:microsoft.quantum.guide.variables) in Q#.</span></span>