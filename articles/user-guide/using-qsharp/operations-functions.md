---
title: Operazioni e funzioni in Q#
description: Come definire e chiamare operazioni e funzioni, nonché le specializzazioni delle operazioni controllate e contigue.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
no-loc:
- Q#
- $$v
ms.openlocfilehash: c2ce999ea2a0fe7204f402fedb4cd3a3c15bd44b
ms.sourcegitcommit: 8256ff463eb9319f1933820a36c0838cf1e024e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2020
ms.locfileid: "90759425"
---
# <a name="operations-and-functions-in-no-locq"></a><span data-ttu-id="faf6e-103">Operazioni e funzioni in Q#</span><span class="sxs-lookup"><span data-stu-id="faf6e-103">Operations and Functions in Q#</span></span>

## <a name="defining-new-operations"></a><span data-ttu-id="faf6e-104">Definizione di nuove operazioni</span><span class="sxs-lookup"><span data-stu-id="faf6e-104">Defining New Operations</span></span>

<span data-ttu-id="faf6e-105">Le operazioni sono le principali di Q# .</span><span class="sxs-lookup"><span data-stu-id="faf6e-105">Operations are the core of Q#.</span></span>
<span data-ttu-id="faf6e-106">Una volta dichiarate, possono essere chiamate da applicazioni .NET classiche, ad esempio usando un simulatore o altre operazioni all'interno di Q# .</span><span class="sxs-lookup"><span data-stu-id="faf6e-106">Once declared, they can either be called from classical .NET applications, for example, using a simulator or by other operations within Q#.</span></span>
<span data-ttu-id="faf6e-107">Ogni operazione definita in Q# può chiamare un numero qualsiasi di altre operazioni, incluse le operazioni intrinseche predefinite definite dal linguaggio.</span><span class="sxs-lookup"><span data-stu-id="faf6e-107">Each operation defined in Q# can call any number of other operations, including the built-in intrinsic operations defined by the language.</span></span> <span data-ttu-id="faf6e-108">Il modo specifico in cui Q# definisce queste operazioni intrinseche dipende dal computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="faf6e-108">The particular way in which Q# defines these intrinsic operations depends on the target machine.</span></span>
<span data-ttu-id="faf6e-109">Quando viene compilata, ogni operazione viene rappresentata come tipo di classe .NET che può essere fornita ai computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="faf6e-109">When compiled, each operation is represented as a .NET class type that can be provided to target machines.</span></span>

<span data-ttu-id="faf6e-110">Ogni Q# file di origine può definire un numero qualsiasi di operazioni.</span><span class="sxs-lookup"><span data-stu-id="faf6e-110">Each Q# source file can define any number of operations.</span></span>
<span data-ttu-id="faf6e-111">I nomi delle operazioni devono essere univoci all'interno di uno spazio dei nomi e non possono entrare in conflitto con i nomi di tipo o</span><span class="sxs-lookup"><span data-stu-id="faf6e-111">Operation names must be unique within a namespace and can not conflict with type or function names.</span></span>

<span data-ttu-id="faf6e-112">Una dichiarazione di operazione è costituita dalla parola chiave `operation` , seguita dal simbolo che rappresenta il nome dell'operazione, una tupla di identificatori tipizzati che definisce gli argomenti per l'operazione, i due punti `:` , un'annotazione di tipo che descrive il tipo di risultato dell'operazione, facoltativamente un'annotazione con le caratteristiche dell'operazione, una parentesi graffa aperta e quindi il corpo della dichiarazione dell'operazione `{ }`</span><span class="sxs-lookup"><span data-stu-id="faf6e-112">An operation declaration consists of the keyword `operation`, followed by the symbol that is the operation's name, a typed identifier tuple that defines the arguments to the operation, a colon `:`, a type annotation that describes the operation's result type, optionally an annotation with the operation characteristics, an open brace, and then the body of the operation declaration, enclosed in braces `{ }`.</span></span>

<span data-ttu-id="faf6e-113">Ogni operazione accetta un input, produce un output e specifica l'implementazione per una o più specializzazioni delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="faf6e-113">Each operation takes an input, produces an output, and specifies the implementation for one or more operation specializations.</span></span>
<span data-ttu-id="faf6e-114">Le possibili specializzazioni e come definirle e chiamarle sono descritte in dettaglio nelle diverse sezioni di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="faf6e-114">The possible specializations, and how to define and call them, are detailed in the different sections of this article.</span></span>
<span data-ttu-id="faf6e-115">Per il momento, si consideri l'operazione seguente, che definisce solo una specializzazione del corpo predefinita e accetta un solo qubit come input, quindi chiama l'operazione incorporata <xref:microsoft.quantum.intrinsic.x> su tale input:</span><span class="sxs-lookup"><span data-stu-id="faf6e-115">For now, consider the following operation, which defines only a default body specialization and takes a single qubit as its input, then calls the built-in <xref:microsoft.quantum.intrinsic.x> operation on that input:</span></span>

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

<span data-ttu-id="faf6e-116">La parola chiave `operation` inizia la definizione dell'operazione, seguita dal nome; qui, `BitFlip` .</span><span class="sxs-lookup"><span data-stu-id="faf6e-116">The keyword `operation` begins the operation definition, followed by the name; here, `BitFlip`.</span></span>
<span data-ttu-id="faf6e-117">Successivamente, il tipo di input viene definito ( `Qubit` ), insieme a un nome, `target` , per fare riferimento all'input all'interno della nuova operazione.</span><span class="sxs-lookup"><span data-stu-id="faf6e-117">Next, the type of input is defined (`Qubit`), along with a name, `target`, for referring to the input within the new operation.</span></span>
<span data-ttu-id="faf6e-118">Infine, `Unit` definisce che l'output dell'operazione è vuoto.</span><span class="sxs-lookup"><span data-stu-id="faf6e-118">Lastly, `Unit` defines that the operation's output is empty.</span></span>
<span data-ttu-id="faf6e-119">`Unit` viene usato in modo analogo a `void` in C# e altri linguaggi imperativi ed è equivalente a `unit` in F # e altri linguaggi funzionali.</span><span class="sxs-lookup"><span data-stu-id="faf6e-119">`Unit` is used similarly to `void` in C# and other imperative languages and is equivalent to `unit` in F# and other functional languages.</span></span>

<span data-ttu-id="faf6e-120">Le operazioni possono inoltre restituire tipi più interessanti rispetto a `Unit` .</span><span class="sxs-lookup"><span data-stu-id="faf6e-120">Operations can also return more interesting types than `Unit`.</span></span>
<span data-ttu-id="faf6e-121">Ad esempio, l' <xref:microsoft.quantum.intrinsic.m> operazione restituisce un output di tipo `Result` , che rappresenta l'esecuzione di una misurazione.</span><span class="sxs-lookup"><span data-stu-id="faf6e-121">For instance, the <xref:microsoft.quantum.intrinsic.m> operation returns an output of type `Result`, representing having performed a measurement.</span></span>  <span data-ttu-id="faf6e-122">È possibile passarla da un'operazione a un'altra operazione o usarla con la `let` parola chiave per definire una nuova variabile.</span><span class="sxs-lookup"><span data-stu-id="faf6e-122">You can pass it from an operation to another operation or use it with the `let` keyword to define a new variable.</span></span>

<span data-ttu-id="faf6e-123">Questo approccio consente di rappresentare calcoli classici che interagiscono con le operazioni Quantum a un livello basso, ad esempio nella [codifica superdensa](https://github.com/microsoft/QuantumKatas/tree/main/SuperdenseCoding):</span><span class="sxs-lookup"><span data-stu-id="faf6e-123">This approach allows for representing classical computation that interacts with quantum operations at a low level, such as in [superdense coding](https://github.com/microsoft/QuantumKatas/tree/main/SuperdenseCoding):</span></span>

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
> <span data-ttu-id="faf6e-124">Ogni operazione in Q# accetta esattamente un input e restituisce esattamente un output.</span><span class="sxs-lookup"><span data-stu-id="faf6e-124">Each operation in Q# takes exactly one input and returns exactly one output.</span></span>
> <span data-ttu-id="faf6e-125">Più input e output sono rappresentati mediante *Tuple*, che raccolgono più valori insieme in un singolo valore.</span><span class="sxs-lookup"><span data-stu-id="faf6e-125">Multiple inputs and outputs are represented using *tuples*, which collect multiple values together into a single value.</span></span>
> <span data-ttu-id="faf6e-126">In questo senso, Q# è una lingua "tuple-in-out".</span><span class="sxs-lookup"><span data-stu-id="faf6e-126">In this regard, Q# is a "tuple-in tuple-out" language.</span></span>
> <span data-ttu-id="faf6e-127">Seguendo questo concetto, un set di parentesi vuote, `()` , deve essere letto come tupla "vuota", che ha il tipo `Unit` .</span><span class="sxs-lookup"><span data-stu-id="faf6e-127">Following this concept, a set of empty parentheses, `()`, should then be read as the "empty" tuple, which has the type `Unit`.</span></span>

## <a name="controlled-and-adjoint-operations"></a><span data-ttu-id="faf6e-128">Operazioni controllate e adiacenti</span><span class="sxs-lookup"><span data-stu-id="faf6e-128">Controlled and Adjoint Operations</span></span>

<span data-ttu-id="faf6e-129">Se un'operazione implementa una trasformazione unitaria, come nel caso di molte operazioni in Q# , è possibile definire il modo in cui l'operazione agisce quando *adjointed* o *controllato*.</span><span class="sxs-lookup"><span data-stu-id="faf6e-129">If an operation implements a unitary transformation, as is the case for many operations in Q#, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span> <span data-ttu-id="faf6e-130">Una specializzazione *contigua* di un'operazione specifica il modo in cui il "inverso" dell'operazione agisce, mentre una specializzazione *controllata* specifica il modo in cui un'operazione agisce quando l'applicazione è condizionata allo stato di un particolare registro Quantum.</span><span class="sxs-lookup"><span data-stu-id="faf6e-130">An *adjoint* specialization of an operation specifies how the "inverse" of the operation acts, while a *controlled* specialization specifies how an operation acts when its application is conditioned on the state of a particular quantum register.</span></span>

<span data-ttu-id="faf6e-131">Gli elementi adiacenti delle operazioni Quantum sono cruciali per molti aspetti del quantum computing.</span><span class="sxs-lookup"><span data-stu-id="faf6e-131">Adjoints of quantum operations are crucial to many aspects of quantum computing.</span></span> <span data-ttu-id="faf6e-132">Per un esempio di una situazione di questo tipo descritta insieme a una Q# tecnica di programmazione utile, vedere [coniugazioni](#conjugations) in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="faf6e-132">For an example of one such situation discussed alongside a useful Q# programming technique, see [Conjugations](#conjugations) in this article.</span></span> 

<span data-ttu-id="faf6e-133">La versione controllata di un'operazione è una nuova operazione che applica efficacemente l'operazione di base solo se tutti i qubits di controllo si trovano in uno stato specificato.</span><span class="sxs-lookup"><span data-stu-id="faf6e-133">The controlled version of an operation is a new operation that effectively applies the base operation only if all of the control qubits are in a specified state.</span></span>
<span data-ttu-id="faf6e-134">Se il controllo qubits si trova in una posizione sovraposizionata, l'operazione di base viene applicata in modo coerente alla parte appropriata della superposizione.</span><span class="sxs-lookup"><span data-stu-id="faf6e-134">If the control qubits are in superposition, then the base operation is applied coherently to the appropriate part of the superposition.</span></span>
<span data-ttu-id="faf6e-135">In questo modo, le operazioni controllate vengono spesso usate per generare il groviglio.</span><span class="sxs-lookup"><span data-stu-id="faf6e-135">Thus, controlled operations are often used to generate entanglement.</span></span>

<span data-ttu-id="faf6e-136">Naturalmente è possibile che esista anche una specializzazione *contigua controllata* , specificando l'applicazione controllata di un'operazione contigua.</span><span class="sxs-lookup"><span data-stu-id="faf6e-136">Naturally, a *controlled adjoint* specialization could exist as well, specifying the controlled application of an operation's adjoint.</span></span>

> [!NOTE]
> <span data-ttu-id="faf6e-137">Se $U $ è la trasformazione unitaria implementata da un'operazione `U` , `Adjoint U` rappresenta la trasformazione unitaria $U ^ \dagger $, che è la trasforma coniugale complessa.</span><span class="sxs-lookup"><span data-stu-id="faf6e-137">If $U$ is the unitary transformation implemented by an operation `U`, then `Adjoint U` represents the unitary transformation $U^\dagger$, which is the complex conjugate transpose.</span></span>
> <span data-ttu-id="faf6e-138">Se successivamente si applica un'operazione e il relativo contiguo a uno stato lascia lo stato invariato, come illustrato dal fatto che $UU ^ \dagger = U ^ \dagger U = \ID $, la matrice di identità.</span><span class="sxs-lookup"><span data-stu-id="faf6e-138">Successively applying an operation and then its adjoint to a state leaves the state unchanged, as illustrated by the fact that $UU^\dagger = U^\dagger U = \id$, the identity matrix.</span></span>
> <span data-ttu-id="faf6e-139">La rappresentazione unitaria di un'operazione controllata è leggermente più sfumata, ma è possibile trovare altre informazioni sui [concetti di quantum computing: più qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span><span class="sxs-lookup"><span data-stu-id="faf6e-139">The unitary representation of a controlled operation is slightly more nuanced, but you can find more details at [Quantum computing concepts: multiple qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span></span>

<span data-ttu-id="faf6e-140">Nella sezione seguente viene descritto come chiamare queste varie specializzazioni nel Q# codice e come definire le operazioni per supportarle.</span><span class="sxs-lookup"><span data-stu-id="faf6e-140">The following section describes how to call these various specializations in your Q# code, and how to define operations to support them.</span></span>

### <a name="calling-operation-specializations"></a><span data-ttu-id="faf6e-141">Specializzazioni delle operazioni di chiamata</span><span class="sxs-lookup"><span data-stu-id="faf6e-141">Calling operation specializations</span></span>

<span data-ttu-id="faf6e-142">Un *functor* in Q# è una factory che definisce una nuova operazione da un'altra operazione.</span><span class="sxs-lookup"><span data-stu-id="faf6e-142">A *functor* in Q# is a factory that defines a new operation from another operation.</span></span>
<span data-ttu-id="faf6e-143">I due funtori standard in Q# sono `Adjoint` e `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="faf6e-143">The two standard functors in Q# are `Adjoint` and `Controlled`.</span></span>

<span data-ttu-id="faf6e-144">Funtori hanno accesso all'implementazione dell'operazione di base quando si definisce l'implementazione della nuova operazione.</span><span class="sxs-lookup"><span data-stu-id="faf6e-144">Functors have access to the implementation of the base operation when defining the implementation of the new operation.</span></span>
<span data-ttu-id="faf6e-145">Funtori può quindi eseguire funzioni più complesse rispetto alle funzioni di livello superiore tradizionali.</span><span class="sxs-lookup"><span data-stu-id="faf6e-145">Thus, functors can perform more complex functions than traditional higher-level functions.</span></span> <span data-ttu-id="faf6e-146">Funtori non dispone di una rappresentazione nel Q# sistema di tipi.</span><span class="sxs-lookup"><span data-stu-id="faf6e-146">Functors do not have a representation in the Q# type system.</span></span> <span data-ttu-id="faf6e-147">Attualmente non è possibile associarli a una variabile o passarli come argomenti.</span><span class="sxs-lookup"><span data-stu-id="faf6e-147">It is thus currently not possible to bind them to a variable or pass them as arguments.</span></span> 

<span data-ttu-id="faf6e-148">Usare un functor applicando questo oggetto a un'operazione che restituisce una nuova operazione.</span><span class="sxs-lookup"><span data-stu-id="faf6e-148">Use a functor by applying it to an operation, which returns a new operation.</span></span>
<span data-ttu-id="faf6e-149">Se, ad esempio, `Adjoint` si applica il functor all'operazione, viene `Y` restituita la nuova operazione `Adjoint Y` .</span><span class="sxs-lookup"><span data-stu-id="faf6e-149">For example, applying the `Adjoint` functor to the `Y` operation returns the new operation `Adjoint Y`.</span></span> <span data-ttu-id="faf6e-150">È possibile richiamare la nuova operazione come qualsiasi altra operazione.</span><span class="sxs-lookup"><span data-stu-id="faf6e-150">You can invoke the new operation like any other operation.</span></span>
<span data-ttu-id="faf6e-151">Per eseguire un'operazione per supportare l'applicazione di `Adjoint` o `Controlled` funtori, il tipo restituito deve necessariamente essere `Unit` .</span><span class="sxs-lookup"><span data-stu-id="faf6e-151">For an operation to support the application of the `Adjoint` or `Controlled` functors, its return type necessarily needs to be `Unit`.</span></span> 

#### <a name="adjoint-functor"></a><span data-ttu-id="faf6e-152">`Adjoint` funtore</span><span class="sxs-lookup"><span data-stu-id="faf6e-152">`Adjoint` functor</span></span>

<span data-ttu-id="faf6e-153">In questo modo, `Adjoint Y(q1)` applica il `Adjoint` functor all' `Y` operazione per generare una nuova operazione e applica tale nuova operazione a `q1` .</span><span class="sxs-lookup"><span data-stu-id="faf6e-153">Thus, `Adjoint Y(q1)` applies the `Adjoint` functor to the `Y` operation to generate a new operation, and applies that new operation to `q1`.</span></span>
<span data-ttu-id="faf6e-154">La nuova operazione ha la stessa firma e il tipo dell'operazione di base `Y` .</span><span class="sxs-lookup"><span data-stu-id="faf6e-154">The new operation has the same signature and type as the base operation `Y`.</span></span>
<span data-ttu-id="faf6e-155">In particolare, la nuova operazione supporta inoltre `Adjoint` e supporta solo se è `Controlled` stata eseguita l'operazione di base.</span><span class="sxs-lookup"><span data-stu-id="faf6e-155">In particular, the new operation also supports `Adjoint`, and supports `Controlled` if and only if the base operation did.</span></span>
<span data-ttu-id="faf6e-156">Il `Adjoint` functor è il proprio inverso, ovvero `Adjoint Adjoint Op` è sempre uguale a `Op` .</span><span class="sxs-lookup"><span data-stu-id="faf6e-156">The `Adjoint` functor is its own inverse; that is, `Adjoint Adjoint Op` is always the same as `Op`.</span></span>

#### <a name="controlled-functor"></a><span data-ttu-id="faf6e-157">`Controlled` funtore</span><span class="sxs-lookup"><span data-stu-id="faf6e-157">`Controlled` functor</span></span>

<span data-ttu-id="faf6e-158">Analogamente, `Controlled X(controls, target)` applica il `Controlled` functor all' `X` operazione per generare una nuova operazione e applica tale nuova operazione a `controls` e `target` .</span><span class="sxs-lookup"><span data-stu-id="faf6e-158">Similarly, `Controlled X(controls, target)` applies the `Controlled` functor to the `X` operation to generate a new operation, and applies that new operation to `controls` and `target`.</span></span>

> [!NOTE]
> <span data-ttu-id="faf6e-159">In Q# le versioni controllate accettano sempre una matrice di qubits di controllo e il controllo è sempre basato su tutti i qubits di controllo che si trova nello stato computazionale ( `PauliZ` ) `One` , $ \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="faf6e-159">In Q#, controlled versions always take an array of control qubits, and the controlling is always based on all of the control qubits being in the computational (`PauliZ`) `One` state, $\ket{1}$.</span></span>
> <span data-ttu-id="faf6e-160">Il controllo basato su altri Stati viene ottenuto applicando l'operazione unitaria appropriata al controllo qubits prima dell'operazione controllata, quindi applicando gli inversi dell'operazione unitaria dopo l'operazione controllata.</span><span class="sxs-lookup"><span data-stu-id="faf6e-160">Controlling based on other states is achieved by applying the appropriate unitary operation to the control qubits before the controlled operation, and then applying the inverses of the unitary operation after the controlled operation.</span></span>
> <span data-ttu-id="faf6e-161">Ad esempio, se si applica un'operazione `X` a un controllo qubit prima e dopo un'operazione controllata, l'operazione Controlla lo `Zero` stato ($ \ket {0} $) per tale qubit; applicando un' `H` operazione prima e dopo i controlli sullo `PauliX` `One` stato, ovvero-1 autovalore di Pauli X, $ \ket {-} \mathrel{: =} (\ket {0} -\ket {1} )/\sqrt {2} $ anziché lo `PauliZ` `One` stato.</span><span class="sxs-lookup"><span data-stu-id="faf6e-161">For example, applying an `X` operation to a control qubit before and after a controlled operation causes the operation to control on the `Zero` state ($\ket{0}$) for that qubit; applying an `H` operation before and after controls on the `PauliX` `One` state, that is -1 eigenvalue of Pauli X, $\ket{-} \mathrel{:=} (\ket{0} - \ket{1}) / \sqrt{2}$ rather than the `PauliZ` `One` state.</span></span>

<span data-ttu-id="faf6e-162">Data un'espressione di operazione, è possibile creare una nuova espressione di operazione usando il `Controlled` functore.</span><span class="sxs-lookup"><span data-stu-id="faf6e-162">Given an operation expression, you can form a new operation expression by using the `Controlled` functor.</span></span>
<span data-ttu-id="faf6e-163">La firma della nuova operazione si basa sulla firma dell'operazione originale.</span><span class="sxs-lookup"><span data-stu-id="faf6e-163">The signature of the new operation is based on the signature of the original operation.</span></span>
<span data-ttu-id="faf6e-164">Il tipo di risultato è lo stesso, ma il tipo di input è una tupla con due tuple con una matrice qubit che include i qubit del controllo come primo elemento e gli argomenti dell'operazione originale come secondo elemento.</span><span class="sxs-lookup"><span data-stu-id="faf6e-164">The result type is the same, but the input type is a two-tuple with a qubit array that holds the control qubit(s) as the first element and the arguments of the original operation as the second element.</span></span>
<span data-ttu-id="faf6e-165">La nuova operazione supporta `Controlled` e supporterà solo se è `Adjoint` stata eseguita l'operazione originale.</span><span class="sxs-lookup"><span data-stu-id="faf6e-165">The new operation supports `Controlled`, and will support `Adjoint` if and only if the original operation did.</span></span>

<span data-ttu-id="faf6e-166">Se l'operazione originale ha accettato un solo argomento, l' [equivalenza della tupla singleton](xref:microsoft.quantum.guide.types) entra in gioco qui.</span><span class="sxs-lookup"><span data-stu-id="faf6e-166">If the original operation took only a single argument, then [singleton tuple equivalence](xref:microsoft.quantum.guide.types) comes into play here.</span></span>
<span data-ttu-id="faf6e-167">Ad esempio, `Controlled X` è la versione controllata dell' `X` operazione.</span><span class="sxs-lookup"><span data-stu-id="faf6e-167">For instance, `Controlled X` is the controlled version of the `X` operation.</span></span> 
<span data-ttu-id="faf6e-168">`X` il tipo è `(Qubit => Unit is Adj + Ctl)` , quindi `Controlled X` è di tipo, a `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` causa dell'equivalenza della tupla singleton, equivale a `((Qubit[], Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="faf6e-168">`X` has type `(Qubit => Unit is Adj + Ctl)`, so `Controlled X` has type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; because of singleton tuple equivalence, this is the same as `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="faf6e-169">Se l'operazione di base ha assunto diversi argomenti, ricordarsi di racchiudere tra parentesi gli argomenti corrispondenti della versione controllata dell'operazione per convertirli in una tupla.</span><span class="sxs-lookup"><span data-stu-id="faf6e-169">If the base operation took several arguments, remember to enclose the corresponding arguments of the controlled version of the operation in parentheses to convert them into a tuple.</span></span>
<span data-ttu-id="faf6e-170">Ad esempio, `Controlled Rz` è la versione controllata dell' `Rz` operazione.</span><span class="sxs-lookup"><span data-stu-id="faf6e-170">For instance, `Controlled Rz` is the controlled version of the `Rz` operation.</span></span> 
<span data-ttu-id="faf6e-171">`Rz` dispone del tipo `((Double, Qubit) => Unit is Adj + Ctl)` , pertanto `Controlled Rz` è di tipo `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="faf6e-171">`Rz` has type `((Double, Qubit) => Unit is Adj + Ctl)`, so `Controlled Rz` has type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="faf6e-172">Quindi, `Controlled Rz(controls, (0.1, target))` sarebbe una chiamata valida di `Controlled Rz` (si notino le parentesi `0.1, target` ).</span><span class="sxs-lookup"><span data-stu-id="faf6e-172">Thus, `Controlled Rz(controls, (0.1, target))` would be a valid invocation of `Controlled Rz` (note the parentheses around `0.1, target`).</span></span>

<span data-ttu-id="faf6e-173">Un altro esempio `CNOT(control, target)` può essere implementato come `Controlled X([control], target)` .</span><span class="sxs-lookup"><span data-stu-id="faf6e-173">As another example, `CNOT(control, target)` can be implemented as `Controlled X([control], target)`.</span></span> <span data-ttu-id="faf6e-174">Se una destinazione deve essere controllata da due controlli qubits (CCNOT), usare un' `Controlled X([control1, control2], target)` istruzione.</span><span class="sxs-lookup"><span data-stu-id="faf6e-174">If a target should be controlled by two control qubits (CCNOT), use a `Controlled X([control1, control2], target)` statement.</span></span>

#### `Controlled Adjoint` 

<span data-ttu-id="faf6e-175">Il `Controlled` e il `Adjoint` funtori commute, quindi non esiste alcuna differenza tra l'applicazione di `Controlled Adjoint Op` o `Adjoint Controlled Op` .</span><span class="sxs-lookup"><span data-stu-id="faf6e-175">The `Controlled` and `Adjoint` functors commute, so there is no difference between applying `Controlled Adjoint Op` or `Adjoint Controlled Op`.</span></span>


## <a name="defining-controlled-and-adjoint-implementations"></a><span data-ttu-id="faf6e-176">Definizione di implementazioni controllate e adiacenti</span><span class="sxs-lookup"><span data-stu-id="faf6e-176">Defining Controlled and Adjoint Implementations</span></span>

<span data-ttu-id="faf6e-177">Nella prima dichiarazione di operazione degli esempi precedenti, le operazioni `BitFlip` e `DecodeSuperdense` sono state definite rispettivamente con le firme `(Qubit => Unit)` e `((Qubit, Qubit) => (Result, Result))` .</span><span class="sxs-lookup"><span data-stu-id="faf6e-177">In the first operation declaration in the previous examples, the operations `BitFlip` and `DecodeSuperdense` were defined with signatures `(Qubit => Unit)` and `((Qubit, Qubit) => (Result, Result))`, respectively.</span></span>
<span data-ttu-id="faf6e-178">Come `DecodeSuperdense` include le misurazioni, non è un'operazione unitaria e pertanto non è possibile che esistano specializzazioni controllate e non contigue (richiamare il requisito correlato restituito da tale operazione `Unit` ).</span><span class="sxs-lookup"><span data-stu-id="faf6e-178">As `DecodeSuperdense` includes measurements, it is not a unitary operation, and therefore neither controlled not adjoint specializations could exist (recall the related requirement that such an operation return `Unit`).</span></span>
<span data-ttu-id="faf6e-179">Tuttavia, poiché `BitFlip` esegue semplicemente l'operazione unitaria <xref:microsoft.quantum.intrinsic.x> , è possibile che sia stata definita con entrambe le specializzazioni.</span><span class="sxs-lookup"><span data-stu-id="faf6e-179">However, as `BitFlip` simply performs the unitary <xref:microsoft.quantum.intrinsic.x> operation, you could have defined it with both specializations.</span></span>

<span data-ttu-id="faf6e-180">In questa sezione viene illustrato in dettaglio come includere l'esistenza di specializzazioni nelle Q# dichiarazioni di operazione, offrendo quindi la possibilità di chiamare insieme a `Adjoint` o `Controlled` funtori.</span><span class="sxs-lookup"><span data-stu-id="faf6e-180">This section details how to include the existence of specializations in your Q# operation declarations, hence giving them the ability to called in conjunction with the `Adjoint` or `Controlled` functors.</span></span>
<span data-ttu-id="faf6e-181">Per ulteriori informazioni su alcune delle situazioni in cui è valido o non è valido per dichiarare determinate specializzazioni, vedere [circostanze per la definizione valida delle specializzazioni](#circumstances-for-validly-defining-specializations) in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="faf6e-181">For more information about some of the situations in which it is either valid or not valid to declare certain specializations, see [Circumstances for validly defining specializations](#circumstances-for-validly-defining-specializations) in this article.</span></span>

<span data-ttu-id="faf6e-182">Le caratteristiche dell'operazione definiscono i tipi di funtori che è possibile applicare all'operazione dichiarata e l'effetto di questi ultimi.</span><span class="sxs-lookup"><span data-stu-id="faf6e-182">Operation characteristics define what kinds of functors you can apply to the declared operation, and what effect they have.</span></span> <span data-ttu-id="faf6e-183">L'esistenza di queste specializzazioni può essere dichiarata come parte della firma dell'operazione, in particolare tramite un'annotazione con le caratteristiche dell'operazione, ovvero `is Adj` , `is Ctl` o `is Adj + Ctl` .</span><span class="sxs-lookup"><span data-stu-id="faf6e-183">The existence of these specializations can be declared as part of the operation signature, specifically through an annotation with the operation characteristics: either `is Adj`, `is Ctl`, or `is Adj + Ctl`.</span></span>
<span data-ttu-id="faf6e-184">L'implementazione effettiva di ogni specializzazione può essere definita in modo *implicito* o *esplicito* .</span><span class="sxs-lookup"><span data-stu-id="faf6e-184">The actual implementation of each specialization can either be *implicitly* or *explicitly* defined.</span></span>

### <a name="implicitly-specifying-implementations"></a><span data-ttu-id="faf6e-185">Specifica delle implementazioni in modo implicito</span><span class="sxs-lookup"><span data-stu-id="faf6e-185">Implicitly specifying implementations</span></span>

<span data-ttu-id="faf6e-186">In questo caso, il corpo della dichiarazione dell'operazione è costituito esclusivamente dall'implementazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="faf6e-186">In this case, the body of the operation declaration consists solely of the default implementation.</span></span> <span data-ttu-id="faf6e-187">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="faf6e-187">For example:</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```
<span data-ttu-id="faf6e-188">In questo caso, l'implementazione corrispondente per ogni specializzazione dichiarata in modo implicito viene generata automaticamente dal compilatore, da eseguire se `Adjoint` `Controlled` vengono usati o funtori.</span><span class="sxs-lookup"><span data-stu-id="faf6e-188">Here, the corresponding implementation for each such implicitly declared specialization is automatically generated by the compiler, to be performed if the `Adjoint` or `Controlled` functors are used.</span></span>

<span data-ttu-id="faf6e-189">Pertanto, una chiamata di `Adjoint PrepareEntangledPair` provocherebbe il compilatore che implementa il contiguo di `CNOT` e quindi il contiguo di `H` .</span><span class="sxs-lookup"><span data-stu-id="faf6e-189">So, a call of `Adjoint PrepareEntangledPair` would result in the compiler implementing the adjoint of `CNOT` and then the adjoint of `H`.</span></span>
<span data-ttu-id="faf6e-190">Queste singole operazioni sono entrambe autocontigue, pertanto l'operazione risultante `Adjoint PrepareEntangledPair` sarebbe semplicemente costituita dall'applicazione `CNOT(here, there)` e quindi da `H(here)` .</span><span class="sxs-lookup"><span data-stu-id="faf6e-190">These individual operations are both self-adjoint, so the resulting `Adjoint PrepareEntangledPair` operation would simply consist of applying `CNOT(here, there)` and then `H(here)`.</span></span>
<span data-ttu-id="faf6e-191">Di conseguenza, è possibile usare questo valore per scrivere nell' `DecodeSuperdense` esempio precedente in modo più compatto, usando il contiguo di `PrepareEntangledPair` per trasformare lo stato incastrato di nuovo in una coppia non impigliata di qubits:</span><span class="sxs-lookup"><span data-stu-id="faf6e-191">Hence you can use this to write the `DecodeSuperdense` in the previous example more compactly, by using the adjoint of `PrepareEntangledPair` to transform the entangled state back into an unentangled pair of qubits:</span></span>

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

<span data-ttu-id="faf6e-192">L'annotazione con le caratteristiche dell'operazione nella dichiarazione è utile per garantire che il compilatore generi automaticamente altre specializzazioni in base all'implementazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="faf6e-192">The annotation with the operation characteristics in the declaration is useful to ensure that the compiler auto-generates other specializations based on the default implementation.</span></span> 

<span data-ttu-id="faf6e-193">Quando si progettano operazioni da usare con funtori, è necessario considerare alcune importanti limitazioni.</span><span class="sxs-lookup"><span data-stu-id="faf6e-193">There are several important limitations to consider when designing operations for use with functors.</span></span>
<span data-ttu-id="faf6e-194">In modo più critico, le specializzazioni per un'operazione che usa il valore di output di qualsiasi altra operazione *non possono* essere generate automaticamente dal compilatore, perché è ambiguo come riordinare le istruzioni in tale operazione per ottenere lo stesso effetto.</span><span class="sxs-lookup"><span data-stu-id="faf6e-194">Most critically, specializations for an operation that uses the output value of any other operation *cannot* be auto-generated by the compiler, as it is ambiguous how to reorder the statements in such an operation to obtain the same effect.</span></span>

<span data-ttu-id="faf6e-195">Pertanto, è spesso utile specificare in modo esplicito le varie implementazioni.</span><span class="sxs-lookup"><span data-stu-id="faf6e-195">Therefore, it is often useful to explicitly specify the various implementations.</span></span>

### <a name="explicitly-specifying-implementations"></a><span data-ttu-id="faf6e-196">Specifica delle implementazioni in modo esplicito</span><span class="sxs-lookup"><span data-stu-id="faf6e-196">Explicitly specifying implementations</span></span>

<span data-ttu-id="faf6e-197">Nel caso in cui il compilatore non sia in grado di generare l'implementazione, è possibile specificarlo in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="faf6e-197">In the case where the compiler cannot generate the implementation, you can specify it explicitly.</span></span> <span data-ttu-id="faf6e-198">Tali dichiarazioni di specializzazione esplicita possono essere costituite da una *direttiva di generazione* adatta o da un'implementazione definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="faf6e-198">Such explicit specialization declarations can consist of a suitable *generation directive* or a user-defined implementation.</span></span>
<span data-ttu-id="faf6e-199">Di seguito è riportata la gamma completa di possibilità, con alcuni esempi di specializzazione esplicita.</span><span class="sxs-lookup"><span data-stu-id="faf6e-199">Following are the full range of possibilities, with some examples of explicit specialization.</span></span> 


#### <a name="explicit-specialization-declarations"></a><span data-ttu-id="faf6e-200">Dichiarazioni di specializzazione esplicite</span><span class="sxs-lookup"><span data-stu-id="faf6e-200">Explicit specialization declarations</span></span>

<span data-ttu-id="faf6e-201">Q# le operazioni possono contenere le seguenti dichiarazioni di specializzazione esplicite:</span><span class="sxs-lookup"><span data-stu-id="faf6e-201">Q# operations can contain the following explicit specialization declarations:</span></span>

- <span data-ttu-id="faf6e-202">La `body` specializzazione specifica l'implementazione dell'operazione senza funtori applicata.</span><span class="sxs-lookup"><span data-stu-id="faf6e-202">The `body` specialization specifies the implementation of the operation with no functors applied.</span></span>
- <span data-ttu-id="faf6e-203">La `adjoint` specializzazione specifica l'implementazione dell'operazione con il `Adjoint` functor applicato.</span><span class="sxs-lookup"><span data-stu-id="faf6e-203">The `adjoint` specialization specifies the implementation of the operation with the `Adjoint` functor applied.</span></span>
- <span data-ttu-id="faf6e-204">La `controlled` specializzazione specifica l'implementazione dell'operazione con il `Controlled` functor applicato.</span><span class="sxs-lookup"><span data-stu-id="faf6e-204">The `controlled` specialization specifies the implementation of the operation with the `Controlled` functor applied.</span></span>
- <span data-ttu-id="faf6e-205">La `controlled adjoint` specializzazione specifica l'implementazione dell'operazione con `Adjoint` e `Controlled` funtori applicati.</span><span class="sxs-lookup"><span data-stu-id="faf6e-205">The `controlled adjoint` specialization specifies the implementation of the operation with both the `Adjoint` and `Controlled` functors applied.</span></span>
  <span data-ttu-id="faf6e-206">Questa specializzazione può anche essere denominata `adjoint controlled` , dal momento che i due funtori del commutatore.</span><span class="sxs-lookup"><span data-stu-id="faf6e-206">This specialization can also be named `adjoint controlled`, since the two functors commute.</span></span>


<span data-ttu-id="faf6e-207">Una specializzazione di operazione è costituita dal tag di specializzazione, ad esempio `body` o, `adjoint` seguito da uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="faf6e-207">An operation specialization consists of the specialization tag (for example, `body` or `adjoint`) followed by one of:</span></span>

- <span data-ttu-id="faf6e-208">Dichiarazione esplicita come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="faf6e-208">An explicit declaration as described in the following.</span></span>
- <span data-ttu-id="faf6e-209">*Direttiva* che indica al compilatore *come* generare la specializzazione, una tra le seguenti:</span><span class="sxs-lookup"><span data-stu-id="faf6e-209">A *directive* that tells the compiler *how* to generate the specialization, one of:</span></span>
  - <span data-ttu-id="faf6e-210">`intrinsic`, che indica che il computer di destinazione fornisce la specializzazione.</span><span class="sxs-lookup"><span data-stu-id="faf6e-210">`intrinsic`, which indicates that the target machine provides the specialization.</span></span>
  - <span data-ttu-id="faf6e-211">`distribute`, usato con le `controlled` `controlled adjoint` specializzazioni e.</span><span class="sxs-lookup"><span data-stu-id="faf6e-211">`distribute`, used with the `controlled` and `controlled adjoint` specializations.</span></span>
    <span data-ttu-id="faf6e-212">Se usato con `controlled` , indica che il compilatore deve calcolare la specializzazione applicando `Controlled` a tutte le operazioni nell'oggetto `body` .</span><span class="sxs-lookup"><span data-stu-id="faf6e-212">When used with `controlled`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `body`.</span></span>
    <span data-ttu-id="faf6e-213">Se usato con `controlled adjoint` , indica che il compilatore deve calcolare la specializzazione applicando `Controlled` a tutte le operazioni nella `adjoint` specializzazione.</span><span class="sxs-lookup"><span data-stu-id="faf6e-213">When used with `controlled adjoint`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `adjoint` specialization.</span></span>
  - <span data-ttu-id="faf6e-214">`invert`, che indica che il compilatore deve calcolare la `adjoint` specializzazione invertendo `body` , ad esempio, invertendo l'ordine delle operazioni e applicando il contiguo a ognuno di essi.</span><span class="sxs-lookup"><span data-stu-id="faf6e-214">`invert`, which indicates that the compiler should compute the `adjoint` specialization by inverting the `body`, for example, reversing the order of operations and applying the adjoint to each one.</span></span>
    <span data-ttu-id="faf6e-215">Se usato con `adjoint controlled` , indica che il compilatore deve calcolare la specializzazione invertendo la `controlled` specializzazione.</span><span class="sxs-lookup"><span data-stu-id="faf6e-215">When used with `adjoint controlled`, this indicates that the compiler should compute the specialization by inverting the `controlled` specialization.</span></span>
  - <span data-ttu-id="faf6e-216">`self`, per indicare che la specializzazione contigua è uguale alla `body` specializzazione.</span><span class="sxs-lookup"><span data-stu-id="faf6e-216">`self`, to indicate that the adjoint specialization is the same as the `body` specialization.</span></span>
    <span data-ttu-id="faf6e-217">`self`L'utilizzo di è valido per le `adjoint` `adjoint controlled` specializzazioni e.</span><span class="sxs-lookup"><span data-stu-id="faf6e-217">Using `self` is legal for the `adjoint` and `adjoint controlled` specializations.</span></span>
    <span data-ttu-id="faf6e-218">Per `adjoint controlled` , `self` implica che la `adjoint controlled` specializzazione corrisponde alla `controlled` specializzazione.</span><span class="sxs-lookup"><span data-stu-id="faf6e-218">For `adjoint controlled`, `self` implies that the `adjoint controlled` specialization is the same as the `controlled` specialization.</span></span>
  - <span data-ttu-id="faf6e-219">`auto`, per indicare che il compilatore deve selezionare una direttiva appropriata da applicare.</span><span class="sxs-lookup"><span data-stu-id="faf6e-219">`auto`, to indicate that the compiler should select an appropriate directive to apply.</span></span>
    <span data-ttu-id="faf6e-220">Non è possibile usare `auto` per la `body` specializzazione.</span><span class="sxs-lookup"><span data-stu-id="faf6e-220">You cannot use`auto` for the `body` specialization.</span></span>

<span data-ttu-id="faf6e-221">Tutte le direttive e richiedono un punto e virgola `auto` di chiusura `;` .</span><span class="sxs-lookup"><span data-stu-id="faf6e-221">The directives and `auto` all require a closing semi-colon `;`.</span></span>
<span data-ttu-id="faf6e-222">La `auto` direttiva viene risolta nella seguente direttiva generata se viene fornita una dichiarazione esplicita di `body` :</span><span class="sxs-lookup"><span data-stu-id="faf6e-222">The `auto` directive resolves to the following generated directive if an explicit declaration of the `body` is provided:</span></span>

- <span data-ttu-id="faf6e-223">La `adjoint` specializzazione viene generata in base alla direttiva `invert` .</span><span class="sxs-lookup"><span data-stu-id="faf6e-223">The `adjoint` specialization generates according to the directive `invert`.</span></span>
- <span data-ttu-id="faf6e-224">La `controlled` specializzazione viene generata in base alla direttiva `distribute` .</span><span class="sxs-lookup"><span data-stu-id="faf6e-224">The `controlled` specialization generates according to the directive `distribute`.</span></span>
- <span data-ttu-id="faf6e-225">La `adjoint controlled` specializzazione viene generata in base alla direttiva `invert` se viene fornita una dichiarazione esplicita per `controlled` , ma non una per `adjoint` e `distribute` in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="faf6e-225">The `adjoint controlled` specialization  generates according to the directive `invert` if an explicit declaration for `controlled` is given but not one for `adjoint`, and `distribute` otherwise.</span></span>

> [!TIP]   
> <span data-ttu-id="faf6e-226">Se un'operazione è autonoma, specificare in modo esplicito la specializzazione contigua o controllata tramite la direttiva `self` di generazione per consentire al compilatore di utilizzare tali informazioni a scopo di ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="faf6e-226">If an operation is self-adjoint, explicitly specify either the adjoint or the controlled adjoint specialization via the generation directive `self` to allow the compiler to make use of that information for optimization purposes.</span></span>

<span data-ttu-id="faf6e-227">Una dichiarazione di specializzazione contenente un'implementazione definita dall'utente è costituita da una tupla di argomenti seguita da un blocco di istruzioni con il Q# codice che implementa la specializzazione.</span><span class="sxs-lookup"><span data-stu-id="faf6e-227">A specialization declaration containing a user-defined implementation consists of an argument tuple followed by a statement block with the Q# code that implements the specialization.</span></span>
<span data-ttu-id="faf6e-228">Nell'elenco di argomenti, `...` viene usato per rappresentare gli argomenti dichiarati per l'intera operazione.</span><span class="sxs-lookup"><span data-stu-id="faf6e-228">In the argument list, `...` is used to represent the arguments declared for the operation as a whole.</span></span>
<span data-ttu-id="faf6e-229">Per `body` e `adjoint` , l'elenco di argomenti deve essere sempre `(...)` ; per `controlled` e `adjoint controlled` , l'elenco di argomenti deve essere un simbolo che rappresenta la matrice di qubits del controllo, seguito da `...` , racchiuso tra parentesi, ad esempio `(controls,...)` .</span><span class="sxs-lookup"><span data-stu-id="faf6e-229">For `body` and `adjoint`, the argument list should always be `(...)`; for `controlled` and `adjoint controlled`, the argument list should be a symbol that represents the array of control qubits, followed by `...`, enclosed in parentheses; for example, `(controls,...)`.</span></span>

### <a name="examples"></a><span data-ttu-id="faf6e-230">Esempio</span><span class="sxs-lookup"><span data-stu-id="faf6e-230">Examples</span></span>

<span data-ttu-id="faf6e-231">Una dichiarazione di operazione potrebbe essere semplice come la seguente, che definisce l'operazione di Pauli X primitiva:</span><span class="sxs-lookup"><span data-stu-id="faf6e-231">An operation declaration might be as simple as the following, which defines the primitive Pauli X operation:</span></span>

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```
<span data-ttu-id="faf6e-232">Si noti che il contiguo dell'operazione di Pauli X viene definito con la direttiva, `self` perché per definizione `X` è il proprio inverso.</span><span class="sxs-lookup"><span data-stu-id="faf6e-232">Note that the adjoint of the Pauli X operation is defined with the directive `self` because by definition `X` is its own inverse.</span></span>

<span data-ttu-id="faf6e-233">Nell'esempio precedente `PrepareEntangledPair` , il codice è equivalente al codice seguente che contiene dichiarazioni di specializzazione esplicite:</span><span class="sxs-lookup"><span data-stu-id="faf6e-233">In the earlier `PrepareEntangledPair` example, the code is equivalent to the following code containing explicit specialization declarations:</span></span> 

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
<span data-ttu-id="faf6e-234">La parola chiave `auto` indica che il compilatore deve determinare come generare l'implementazione della specializzazione.</span><span class="sxs-lookup"><span data-stu-id="faf6e-234">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>

#### <a name="user-defined-specialization-implementation"></a><span data-ttu-id="faf6e-235">Implementazione della specializzazione definita dall'utente</span><span class="sxs-lookup"><span data-stu-id="faf6e-235">User-defined specialization implementation</span></span>

<span data-ttu-id="faf6e-236">Se il compilatore non è in grado di generare automaticamente l'implementazione per una determinata specializzazione o se è possibile fornire un'implementazione più efficiente, è possibile definire manualmente l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="faf6e-236">If the compiler cannot generate the implementation for a certain specialization automatically, or if a more efficient implementation can be given, then you can manually define the implementation.</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user-defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
<span data-ttu-id="faf6e-237">Nell'esempio precedente, `adjoint invert;` indica che la specializzazione contigua deve essere generata invertendo l'implementazione del corpo e `controlled adjoint invert;` indica che la specializzazione di aggiunta controllata deve essere generata invertendo l'implementazione specificata della specializzazione controllata.</span><span class="sxs-lookup"><span data-stu-id="faf6e-237">In the previous example, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="faf6e-238">Se una o più specializzazioni oltre al corpo predefinito devono essere dichiarate in modo esplicito, l'implementazione del corpo predefinito deve essere racchiusa anche in una dichiarazione di specializzazione adatta:</span><span class="sxs-lookup"><span data-stu-id="faf6e-238">If one or more specializations besides the default body need to be explicitly declared, then the implementation for the default body needs to be wrapped into a suitable specialization declaration as well:</span></span>

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

### <a name="circumstances-for-validly-defining-specializations"></a><span data-ttu-id="faf6e-239">Circostanze per la definizione valida delle specializzazioni</span><span class="sxs-lookup"><span data-stu-id="faf6e-239">Circumstances for validly defining specializations</span></span>

#### <a name="operation-declarations-with-adjointcontrolled"></a><span data-ttu-id="faf6e-240">Dichiarazioni di operazione con contiguo/controllato</span><span class="sxs-lookup"><span data-stu-id="faf6e-240">Operation declarations with adjoint/controlled</span></span>

<span data-ttu-id="faf6e-241">È lecito specificare un'operazione senza versioni contigue o controllate.</span><span class="sxs-lookup"><span data-stu-id="faf6e-241">It is legal to specify an operation with no adjoint or controlled versions.</span></span> <span data-ttu-id="faf6e-242">Ad esempio, le operazioni di misurazione non hanno nessuno perché non sono invertibili o controllabili.</span><span class="sxs-lookup"><span data-stu-id="faf6e-242">For instance, measurement operations have neither because they are not invertible or controllable.</span></span>

<span data-ttu-id="faf6e-243">Un'operazione supporta `Adjoint` e `Controlled` funtori se la relativa dichiarazione contiene una dichiarazione implicita o esplicita delle rispettive specializzazioni.</span><span class="sxs-lookup"><span data-stu-id="faf6e-243">An operation supports the `Adjoint` and `Controlled` functors if its declaration contains an implicit or explicit declaration of the respective specializations.</span></span>

<span data-ttu-id="faf6e-244">Una specializzazione annullata o controllata dichiarata in modo esplicito implica l'esistenza di una specializzazione contigua/controllata.</span><span class="sxs-lookup"><span data-stu-id="faf6e-244">An explicitly declared adjoint/controlled specialization implies the existence of an adjoint/controlled specialization.</span></span> 

<span data-ttu-id="faf6e-245">Per un'operazione il cui corpo contiene cicli di ripetizione fino al completamento, istruzioni set, misure, istruzioni return o chiamate ad altre operazioni che non supportano il `Adjoint` functor, la generazione automatica di una specializzazione contigua che segue la `invert` `auto` direttiva o non è possibile.</span><span class="sxs-lookup"><span data-stu-id="faf6e-245">For an operation whose body contains repeat-until-success loops, set statements, measurements, return statements, or calls to other operations that do not support the `Adjoint` functor, auto-generating an adjoint specialization following the `invert` or `auto` directive is not possible.</span></span>

<span data-ttu-id="faf6e-246">Per un'operazione il cui corpo contiene chiamate ad altre operazioni che non supportano il `Controlled` functor, non è possibile generare automaticamente una specializzazione controllata che segue la `distribute` `auto` direttiva o.</span><span class="sxs-lookup"><span data-stu-id="faf6e-246">For an operation whose body contains calls to other operations that do not support the `Controlled` functor, auto-generating a controlled specialization following the `distribute` or `auto` directive is not possible.</span></span>

#### <a name="controlled-adjoint"></a><span data-ttu-id="faf6e-247">Contiguo controllato</span><span class="sxs-lookup"><span data-stu-id="faf6e-247">Controlled Adjoint</span></span>

<span data-ttu-id="faf6e-248">La versione controllata contigua di un'operazione specifica come implementare una versione controllata dal quantum dell'operazione contigua.</span><span class="sxs-lookup"><span data-stu-id="faf6e-248">The controlled adjoint version of an operation specifies how to implement a quantum-controlled version of the adjoint of the operation.</span></span>
<span data-ttu-id="faf6e-249">È lecito specificare un'operazione senza una versione controllata contigua. ad esempio, le operazioni di misurazione non hanno una versione controllata contigua, perché non sono controllabili né invertibili.</span><span class="sxs-lookup"><span data-stu-id="faf6e-249">It is legal to specify an operation with no controlled adjoint version; for instance, measurement operations have no controlled adjoint version because they are neither controllable nor invertible.</span></span>

<span data-ttu-id="faf6e-250">Una specializzazione contigua controllata per un'operazione deve esistere solo se sono presenti sia una specializzazione contigua che una specializzazione controllata.</span><span class="sxs-lookup"><span data-stu-id="faf6e-250">A controlled adjoint specialization for an operation needs to exist if and only if both an adjoint and a controlled specialization exist.</span></span> <span data-ttu-id="faf6e-251">In tal caso, viene dedotta l'esistenza della specializzazione contigua controllata.</span><span class="sxs-lookup"><span data-stu-id="faf6e-251">In that case, the existence of the controlled adjoint specialization is inferred.</span></span> <span data-ttu-id="faf6e-252">Se nessuna implementazione viene definita in modo esplicito, la compilazione genera una specializzazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="faf6e-252">If no implementation is explicitly defined, the compile generates an appropriate specialization.</span></span>

<span data-ttu-id="faf6e-253">Per un'operazione il cui corpo contiene chiamate ad altre operazioni che non dispongono di una versione controllata contigua, la generazione automatica di una specializzazione contigua che segue la `invert` `distribute` direttiva, o `auto` non è possibile.</span><span class="sxs-lookup"><span data-stu-id="faf6e-253">For an operation whose body contains calls to other operations that do not have a controlled adjoint version, auto-generating an adjoint specialization following the `invert`, `distribute`, or `auto` directive is not possible.</span></span>


### <a name="type-compatibility"></a><span data-ttu-id="faf6e-254">Compatibilità tra tipi</span><span class="sxs-lookup"><span data-stu-id="faf6e-254">Type Compatibility</span></span>

<span data-ttu-id="faf6e-255">Usare un'operazione con funtori aggiuntivi supportata ovunque si usi un'operazione con un numero minore di funtori ma la stessa firma.</span><span class="sxs-lookup"><span data-stu-id="faf6e-255">Use an operation with additional functors supported anywhere you use an operation with fewer functors but the same signature.</span></span> <span data-ttu-id="faf6e-256">Ad esempio, usare un'operazione di tipo `(Qubit => Unit is Adj)` ovunque si usi un'operazione di tipo `(Qubit => Unit)` .</span><span class="sxs-lookup"><span data-stu-id="faf6e-256">For instance, use an operation of type `(Qubit => Unit is Adj)` anywhere you use an operation of type `(Qubit => Unit)`.</span></span>

<span data-ttu-id="faf6e-257">Q# è *covariante* rispetto ai tipi restituiti richiamabili: un oggetto chiamabile che restituisce un tipo `'A` è compatibile con un oggetto chiamabile con lo stesso tipo di input e un tipo di risultato compatibile con `'A` .</span><span class="sxs-lookup"><span data-stu-id="faf6e-257">Q# is *covariant* with respect to callable return types: a callable that returns a type `'A` is compatible with a callable with the same input type and a result type that is compatible with `'A` .</span></span>

<span data-ttu-id="faf6e-258">Q# è *controvariante* rispetto ai tipi di input: un oggetto chiamabile che accetta un tipo `'A` come input è compatibile con un oggetto chiamabile con lo stesso tipo di risultato e un tipo di input compatibile con `'A` .</span><span class="sxs-lookup"><span data-stu-id="faf6e-258">Q# is *contravariant* with respect to input types: a callable that takes a type `'A` as input is compatible with a callable with the same result type and an input type that is compatible with `'A`.</span></span>

<span data-ttu-id="faf6e-259">Ovvero, date le seguenti definizioni,</span><span class="sxs-lookup"><span data-stu-id="faf6e-259">That is, given the following definitions,</span></span>

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

<span data-ttu-id="faf6e-260">Si può</span><span class="sxs-lookup"><span data-stu-id="faf6e-260">you can</span></span>

- <span data-ttu-id="faf6e-261">Richiamare la funzione `ConjugateInvertWith` con un `inner` argomento di `Invert` o `ApplyUnitary` .</span><span class="sxs-lookup"><span data-stu-id="faf6e-261">Invoke the function `ConjugateInvertWith` with an `inner` argument of either `Invert` or `ApplyUnitary`.</span></span>
- <span data-ttu-id="faf6e-262">Richiamare la funzione `ConjugateUnitaryWith` con un `inner` argomento di `ApplyUnitary` , ma non `Invert` .</span><span class="sxs-lookup"><span data-stu-id="faf6e-262">Invoke the function `ConjugateUnitaryWith` with an `inner` argument of `ApplyUnitary`, but not `Invert`.</span></span>
- <span data-ttu-id="faf6e-263">Restituisce un valore di tipo `(Qubit[] => Unit is Adj + Ctl)` da `ConjugateInvertWith` .</span><span class="sxs-lookup"><span data-stu-id="faf6e-263">Return a value of type `(Qubit[] => Unit is Adj + Ctl)` from `ConjugateInvertWith`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="faf6e-264">Q# 0,3 ha introdotto una differenza significativa nel comportamento dei tipi definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="faf6e-264">Q# 0.3 introduced a significant difference in the behavior of user-defined types.</span></span>

<span data-ttu-id="faf6e-265">I tipi definiti dall'utente vengono considerati come una versione di cui è stato eseguito il wrapped del tipo sottostante, anziché come sottotipo.</span><span class="sxs-lookup"><span data-stu-id="faf6e-265">User-defined types are treated as a wrapped version of the underlying type, rather than as a subtype.</span></span>
<span data-ttu-id="faf6e-266">Ciò significa che un valore di un tipo definito dall'utente non può essere utilizzato quando si prevede che un valore del tipo sottostante sia.</span><span class="sxs-lookup"><span data-stu-id="faf6e-266">This means that a value of a user-defined type is not usable where you expect a value of the underlying type is.</span></span>


### <a name="conjugations"></a><span data-ttu-id="faf6e-267">Coniugazioni</span><span class="sxs-lookup"><span data-stu-id="faf6e-267">Conjugations</span></span>

<span data-ttu-id="faf6e-268">A differenza dei bit classici, il rilascio della memoria quantistica è leggermente più coinvolto, perché la reimpostazione cieca di qubits può avere effetti indesiderati sul calcolo rimanente se il qubits è ancora stato impigliato.</span><span class="sxs-lookup"><span data-stu-id="faf6e-268">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="faf6e-269">Questi effetti possono essere evitati eseguendo correttamente l'operazione di calcolo prima di rilasciare la memoria.</span><span class="sxs-lookup"><span data-stu-id="faf6e-269">These effects can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="faf6e-270">Un modello comune in quantum computing è quindi il seguente:</span><span class="sxs-lookup"><span data-stu-id="faf6e-270">A common pattern in quantum computing is hence the following:</span></span> 

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

<span data-ttu-id="faf6e-271">A partire dalla versione 0,9, Q# supporta un'istruzione di coniugazione che implementa la trasformazione precedente.</span><span class="sxs-lookup"><span data-stu-id="faf6e-271">Starting with our 0.9 release, Q# supports a conjugation statement that implements the preceding transformation.</span></span> <span data-ttu-id="faf6e-272">Utilizzando tale istruzione, `ApplyWith` è possibile implementare l'operazione nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="faf6e-272">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

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
<span data-ttu-id="faf6e-273">Una tale istruzione di coniugazione diventa molto più utile se le trasformazioni esterne e interne non sono immediatamente disponibili come operazioni, ma sono più convenienti da descrivere da un blocco composto da diverse istruzioni.</span><span class="sxs-lookup"><span data-stu-id="faf6e-273">Such a conjugation statement becomes far more useful if the outer and inner transformations are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="faf6e-274">La trasformazione inversa per le istruzioni definite nel blocco interno viene generata automaticamente dal compilatore e viene eseguita al termine del blocco Apply.</span><span class="sxs-lookup"><span data-stu-id="faf6e-274">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and run after the apply-block completes.</span></span>
<span data-ttu-id="faf6e-275">Poiché le variabili modificabili usate come parte del blocco all'interno non possono essere riassociati nel blocco Apply, la trasformazione generata è sicuramente l'elemento contiguo del calcolo nel blocco all'interno.</span><span class="sxs-lookup"><span data-stu-id="faf6e-275">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 


## <a name="defining-new-functions"></a><span data-ttu-id="faf6e-276">Definizione di nuove funzioni</span><span class="sxs-lookup"><span data-stu-id="faf6e-276">Defining New Functions</span></span>

<span data-ttu-id="faf6e-277">Le funzioni sono puramente deterministiche, le routine classiche in Q# , che sono distinte dalle operazioni in quanto non possono avere effetti oltre il calcolo di un valore di output.</span><span class="sxs-lookup"><span data-stu-id="faf6e-277">Functions are purely deterministic, classical routines in Q#, which are distinct from operations in that they are not allowed to have any effects beyond calculating an output value.</span></span>
<span data-ttu-id="faf6e-278">In particolare, le funzioni non possono chiamare operazioni; agire, allocare o prendere in prestito qubits; numeri casuali di esempio; o altrimenti dipendono dallo stato oltre il valore di input per una funzione.</span><span class="sxs-lookup"><span data-stu-id="faf6e-278">In particular, functions cannot call operations; act on, allocate, or borrow qubits; sample random numbers; or otherwise depend on state beyond the input value to a function.</span></span>
<span data-ttu-id="faf6e-279">Di conseguenza, Q# le funzioni sono *pure*, in quanto eseguono sempre il mapping degli stessi valori di input agli stessi valori di output.</span><span class="sxs-lookup"><span data-stu-id="faf6e-279">As a consequence, Q# functions are *pure*, in that they always map the same input values to the same output values.</span></span>
<span data-ttu-id="faf6e-280">Questo comportamento consente al Q# compilatore di riordinare in modo sicuro come e quando chiamare le funzioni durante la generazione delle specializzazioni delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="faf6e-280">This behavior allows the Q# compiler to safely reorder how and when to call functions when generating operation specializations.</span></span>

<span data-ttu-id="faf6e-281">Ogni Q# file di origine può definire un numero qualsiasi di funzioni.</span><span class="sxs-lookup"><span data-stu-id="faf6e-281">Each Q# source file can define any number of functions.</span></span>
<span data-ttu-id="faf6e-282">I nomi di funzione devono essere univoci all'interno di uno spazio dei nomi e non possono entrare in conflitto con i nomi delle operazioni</span><span class="sxs-lookup"><span data-stu-id="faf6e-282">Function names must be unique within a namespace and cannot conflict with operation or type names.</span></span>

<span data-ttu-id="faf6e-283">La definizione di una funzione funziona in modo analogo alla definizione di un'operazione, ad eccezione del fatto che non è possibile definire alcuna specializzazioni contigua o controllata per una funzione.</span><span class="sxs-lookup"><span data-stu-id="faf6e-283">Defining a function works similarly to defining an operation, except that no adjoint or controlled specializations can be defined for a function.</span></span>
<span data-ttu-id="faf6e-284">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="faf6e-284">For instance:</span></span>

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```

<span data-ttu-id="faf6e-285">oppure</span><span class="sxs-lookup"><span data-stu-id="faf6e-285">or</span></span> 

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

### <a name="classical-logic-in-functions--good"></a><span data-ttu-id="faf6e-286">Logica classica nelle funzioni = = corretta</span><span class="sxs-lookup"><span data-stu-id="faf6e-286">Classical logic in functions == good</span></span>

<span data-ttu-id="faf6e-287">Quando è possibile eseguire questa operazione, è utile scrivere la logica classica in termini di funzioni anziché di operazioni, in modo che le operazioni possano utilizzarlo più facilmente.</span><span class="sxs-lookup"><span data-stu-id="faf6e-287">Whenever it is possible to do so, it is helpful to write out classical logic in terms of functions rather than operations so that operations can more readily use it.</span></span> <span data-ttu-id="faf6e-288">Se, ad esempio, la dichiarazione precedente è stata scritta `Square` come *operazione*, il compilatore non sarebbe stato in grado di garantire che la chiamata con lo stesso input produrrebbe sempre gli stessi output.</span><span class="sxs-lookup"><span data-stu-id="faf6e-288">For example, if you had written the earlier `Square` declaration as an *operation*, then the compiler would not have been able to guarantee that calling it with the same input would consistently produce the same outputs.</span></span>

<span data-ttu-id="faf6e-289">Per sottolineare la differenza tra funzioni e operazioni, prendere in considerazione il problema di campionamento classico di un numero casuale da un' Q# operazione:</span><span class="sxs-lookup"><span data-stu-id="faf6e-289">To underscore the difference between functions and operations, consider the problem of classically sampling a random number from within a Q# operation:</span></span>

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

<span data-ttu-id="faf6e-290">Ogni volta che `U` viene chiamato, ha un'azione diversa su `target` .</span><span class="sxs-lookup"><span data-stu-id="faf6e-290">Each time that `U` is called, it has a different action on `target`.</span></span>
<span data-ttu-id="faf6e-291">In particolare, il compilatore non può garantire che se si aggiunge una `adjoint auto` dichiarazione di specializzazione a `U` , `U(target); Adjoint U(target);` funge da identità (ovvero come no-op).</span><span class="sxs-lookup"><span data-stu-id="faf6e-291">In particular, the compiler cannot guarantee that if you add an `adjoint auto` specialization declaration to `U`, then `U(target); Adjoint U(target);` acts as identity (that is, as a no-op).</span></span>
<span data-ttu-id="faf6e-292">In questo modo viene violata la definizione dell'oggetto adiacente definito in [vettori e matrici](xref:microsoft.quantum.concepts.vectors), in modo che il compilatore possa generare automaticamente una specializzazione contigua in un'operazione in cui si chiama l'operazione <xref:microsoft.quantum.math.randomreal> interrompe le garanzie fornite dal compilatore. <xref:microsoft.quantum.math.randomreal> è un'operazione per la quale non esiste alcuna versione contigua o controllata.</span><span class="sxs-lookup"><span data-stu-id="faf6e-292">This violates the definition of the adjoint defined in [Vectors and Matrices](xref:microsoft.quantum.concepts.vectors), such that allowing the compiler to auto-generate an adjoint specialization in an operation where you call the operation <xref:microsoft.quantum.math.randomreal> would break the guarantees provided by the compiler; <xref:microsoft.quantum.math.randomreal> is an operation for which no adjoint or controlled version exists.</span></span>

<span data-ttu-id="faf6e-293">D'altra parte, consentire le chiamate di funzione come `Square` è sicuro e assicura al compilatore che deve conservare solo l'input per `Square` mantenerne l'output stabile.</span><span class="sxs-lookup"><span data-stu-id="faf6e-293">On the other hand, allowing function calls such as `Square` is safe, and assures the compiler that it only needs to preserve the input to `Square` to keep its output stable.</span></span>
<span data-ttu-id="faf6e-294">In questo modo, l'isolamento della logica classica più possibile in funzioni semplifica il riutilizzo di tale logica in altre funzioni e operazioni.</span><span class="sxs-lookup"><span data-stu-id="faf6e-294">Thus, isolating as much classical logic as possible into functions makes it easy to reuse that logic in other functions and operations alike.</span></span>


## <a name="generic-type-parameterized-callables"></a><span data-ttu-id="faf6e-295">Chiamabili generici (con parametri di tipo)</span><span class="sxs-lookup"><span data-stu-id="faf6e-295">Generic (Type-Parameterized) Callables</span></span>

<span data-ttu-id="faf6e-296">Molte funzioni e operazioni che è possibile definire non si basano molto sui tipi di input, ma usano solo i tipi in modo implicito tramite un'altra funzione o un'altra operazione.</span><span class="sxs-lookup"><span data-stu-id="faf6e-296">Many functions and operations that you might wish to define do not actually heavily rely on the types of their inputs, but rather only implicitly use their types via some other function or operation.</span></span>
<span data-ttu-id="faf6e-297">Si consideri, ad esempio, il concetto di *mappa* comune a molti linguaggi funzionali; Data una funzione $f (x) $ e una raccolta di valori $ \{ X_1, x_2, \dots, x_n \} $, map restituisce una nuova raccolta $ \{ f (X_1), f (x_2), \dots, f (x_n) \} $.</span><span class="sxs-lookup"><span data-stu-id="faf6e-297">For example, consider the *map* concept common to many functional languages; given a function $f(x)$ and a collection of values $\{x_1, x_2, \dots, x_n\}$, map returns a new collection $\{f(x_1), f(x_2), \dots, f(x_n)\}$.</span></span>
<span data-ttu-id="faf6e-298">Per implementare questo in Q# , sfruttare il fatto che le funzioni sono la prima classe.</span><span class="sxs-lookup"><span data-stu-id="faf6e-298">To implement this in Q#, take advantage of the fact that functions are first class.</span></span>
<span data-ttu-id="faf6e-299">Di seguito è riportato un esempio di `Map` utilizzo di `T` come segnaposto per individuare i tipi necessari.</span><span class="sxs-lookup"><span data-stu-id="faf6e-299">Here is a quick example of `Map`, using `T` as a placeholder while you figure out what types you need.</span></span>

```qsharp
function Map(fn : (T -> T), values : T[]) : T[] {
    mutable mappedValues = new T[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="faf6e-300">Si noti che questa funzione è molto simile, indipendentemente dai tipi effettivi in cui si sostituisce.</span><span class="sxs-lookup"><span data-stu-id="faf6e-300">Note that this function looks very much the same no matter what actual types you substitute in.</span></span>
<span data-ttu-id="faf6e-301">Un mapping da Integer a Paulis, ad esempio, ha un aspetto molto simile a quello di una mappa dai numeri a virgola mobile a stringhe:</span><span class="sxs-lookup"><span data-stu-id="faf6e-301">A map from integers to Paulis, for instance, looks much the same as a map from floating-point numbers to strings:</span></span>

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

<span data-ttu-id="faf6e-302">In linea di principio, è possibile scrivere una versione di `Map` per ogni coppia di tipi riscontrati, ma in questo caso sono state introdotte diverse difficoltà.</span><span class="sxs-lookup"><span data-stu-id="faf6e-302">In principle, you could write a version of `Map` for every pair of types that you encounter, but this introduces several difficulties.</span></span>
<span data-ttu-id="faf6e-303">Se ad esempio si individua un bug in `Map` , è necessario assicurarsi che la correzione venga applicata in modo uniforme in tutte le versioni di `Map` .</span><span class="sxs-lookup"><span data-stu-id="faf6e-303">For instance, if you find a bug in `Map`, then you must ensure that the fix is applied uniformly across all versions of `Map`.</span></span>
<span data-ttu-id="faf6e-304">Inoltre, se si costruisce una nuova tupla o un tipo definito dall'utente, è necessario creare anche un nuovo oggetto `Map` da usare con il nuovo tipo.</span><span class="sxs-lookup"><span data-stu-id="faf6e-304">Moreover, if you construct a new tuple or UDT, then you must now also construct a new `Map` to go along with the new type.</span></span>
<span data-ttu-id="faf6e-305">Sebbene si tratti di un numero ridotto di funzioni di questo tipo, quando si raccolgono più funzioni con lo stesso formato di `Map` , il costo dell'introduzione di nuovi tipi diventa ingiustificatamente grande nell'ordine piuttosto breve.</span><span class="sxs-lookup"><span data-stu-id="faf6e-305">While this is tractable for a small number of such functions, as you collect more and more functions of the same form as `Map`, the cost of introducing new types becomes unreasonably large in fairly short order.</span></span>

<span data-ttu-id="faf6e-306">Tuttavia, gran parte di questa difficoltà deriva dal fatto che non è stato dato al compilatore le informazioni necessarie per riconoscere il modo in cui sono correlate le diverse versioni di `Map` .</span><span class="sxs-lookup"><span data-stu-id="faf6e-306">However, much of this difficulty results from the fact that you have not given the compiler the information it needs to recognize how the different versions of `Map` are related.</span></span>
<span data-ttu-id="faf6e-307">In effetti, si vuole che il compilatore tratti `Map` come un tipo di funzione matematica dai Q# *tipi* alle Q# funzioni.</span><span class="sxs-lookup"><span data-stu-id="faf6e-307">Effectively, you want the compiler to treat `Map` as some kind of mathematical function from Q# *types* to Q# functions.</span></span>

<span data-ttu-id="faf6e-308">Q# formalizza questa nozione consentendo a funzioni e operazioni di avere *parametri di tipo*, nonché i parametri di tupla ordinari.</span><span class="sxs-lookup"><span data-stu-id="faf6e-308">Q# formalizes this notion by allowing functions and operations to have *type parameters*, as well as their ordinary tuple parameters.</span></span>
<span data-ttu-id="faf6e-309">Negli esempi precedenti si desidera considerare `Map` come avere parametri di tipo `Int, Pauli` nel primo caso e `Double, String` nel secondo caso.</span><span class="sxs-lookup"><span data-stu-id="faf6e-309">In the previous examples, you wish to think of `Map` as having type parameters `Int, Pauli` in the first case and `Double, String` in the second case.</span></span>
<span data-ttu-id="faf6e-310">Per la maggior parte, usare questi parametri di tipo come se fossero tipi normali.</span><span class="sxs-lookup"><span data-stu-id="faf6e-310">For the most part, use these type parameters as though they were ordinary types.</span></span> <span data-ttu-id="faf6e-311">Usare i valori dei parametri di tipo per creare matrici e tuple, chiamare funzioni e operazioni e assegnare a variabili ordinarie o modificabili.</span><span class="sxs-lookup"><span data-stu-id="faf6e-311">Use values of type parameters to make arrays and tuples, call functions and operations, and assign to ordinary or mutable variables.</span></span>

> [!NOTE]
> <span data-ttu-id="faf6e-312">Il caso più estremo della dipendenza indiretta è quello di qubits, in cui un Q# programma non può basarsi direttamente sulla struttura del `Qubit` tipo, ma **deve** passare tali tipi ad altre operazioni e funzioni.</span><span class="sxs-lookup"><span data-stu-id="faf6e-312">The most extreme case of indirect dependence is that of qubits, where a Q# program cannot directly rely on the structure of the `Qubit` type but **must** pass such types to other operations and functions.</span></span>

<span data-ttu-id="faf6e-313">Tornando all'esempio precedente, si noterà che `Map` deve avere parametri di tipo, uno per rappresentare l'input `fn` e uno per rappresentare l'output da `fn` .</span><span class="sxs-lookup"><span data-stu-id="faf6e-313">Returning to the earlier example, then, you see that `Map` needs to have type parameters, one to represent the input to `fn` and one to represent the output from `fn`.</span></span>
<span data-ttu-id="faf6e-314">In Q# , questo viene scritto aggiungendo parentesi angolari (ovvero `<>` non i Brake $ \braket {} $!) dopo il nome di una funzione o di un'operazione nella relativa dichiarazione e elencando ogni parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="faf6e-314">In Q#, this is written by adding angle brackets (that's `<>`, not brakets $\braket{}$!) after the name of a function or operation in its declaration, and by listing each type parameter.</span></span>
<span data-ttu-id="faf6e-315">Il nome di ogni parametro di tipo deve iniziare con un segno di indicizzazione `'` , a indicare che si tratta di un parametro di tipo e non di un tipo ordinario (noto anche come tipo *concreto* ).</span><span class="sxs-lookup"><span data-stu-id="faf6e-315">The name of each type parameter must start with a tick `'`, indicating that it is a type parameter and not a ordinary type (also known as a *concrete* type).</span></span>
<span data-ttu-id="faf6e-316">Viene quindi `Map` scritto:</span><span class="sxs-lookup"><span data-stu-id="faf6e-316">Thus, `Map`, is written:</span></span>

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="faf6e-317">Si noti che la definizione di ha un `Map<'Input, 'Output>` aspetto molto simile a quello delle versioni di previoius.</span><span class="sxs-lookup"><span data-stu-id="faf6e-317">Note that the definition of `Map<'Input, 'Output>` looks extremely similar to the previoius versions.</span></span>
<span data-ttu-id="faf6e-318">L'unica differenza consiste nel fatto che il compilatore è stato informato in modo esplicito che `Map` non dipende direttamente da quali `'Input` e `'Output` sono, ma funziona per due tipi utilizzandoli indirettamente tramite `fn` .</span><span class="sxs-lookup"><span data-stu-id="faf6e-318">The only difference is that you have explicitly informed the compiler that `Map` doesn't directly depend on what `'Input` and `'Output` are, but works for any two types by using them indirectly through `fn`.</span></span>
<span data-ttu-id="faf6e-319">Una volta definito `Map<'Input, 'Output>` in questo modo, è possibile chiamarlo come se fosse una funzione ordinaria:</span><span class="sxs-lookup"><span data-stu-id="faf6e-319">Once you have defined `Map<'Input, 'Output>` in this way, you can call it as though it was an ordinary function:</span></span>

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> <span data-ttu-id="faf6e-320">La scrittura di funzioni e funzioni generiche è un'unica posizione in cui "tuple-in tuple-out" è un modo molto utile per considerare Q# funzioni e operazioni.</span><span class="sxs-lookup"><span data-stu-id="faf6e-320">Writing generic functions and operations is one place where "tuple-in tuple-out" is a very useful way to think about Q# functions and operations.</span></span>
> <span data-ttu-id="faf6e-321">Poiché ogni funzione accetta esattamente un input e restituisce esattamente un output, un input di tipo `'T -> 'U` corrisponde a *qualsiasi* Q# funzione.</span><span class="sxs-lookup"><span data-stu-id="faf6e-321">Since every function takes exactly one input and returns exactly one output, an input of type `'T -> 'U` matches *any* Q# function whatsoever.</span></span>
> <span data-ttu-id="faf6e-322">Analogamente, è possibile passare qualsiasi operazione a un input di tipo `'T => 'U` .</span><span class="sxs-lookup"><span data-stu-id="faf6e-322">Similarly, you can pass any operation to an input of type `'T => 'U`.</span></span>

<span data-ttu-id="faf6e-323">Come secondo esempio, si consideri la necessità di scrivere una funzione che restituisce la composizione di altre due funzioni:</span><span class="sxs-lookup"><span data-stu-id="faf6e-323">As a second example, consider the challenge of writing a function that returns the composition of two other functions:</span></span>

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="faf6e-324">In questo caso, è necessario specificare esattamente cosa `A` , `B` e `C` sono, di conseguenza la limitazione dell'utilità della nuova `Compose` funzione.</span><span class="sxs-lookup"><span data-stu-id="faf6e-324">Here, you must specify exactly what `A`, `B`, and `C` are, hence severely limiting the utility of our new `Compose` function.</span></span>
<span data-ttu-id="faf6e-325">Dopo tutto, `Compose` dipende solo da `A` , `B` e `C` *tramite* `innerFn` e `outerFn` .</span><span class="sxs-lookup"><span data-stu-id="faf6e-325">After all, `Compose` only depends on `A`, `B`, and `C` *via* `innerFn` and `outerFn`.</span></span>
<span data-ttu-id="faf6e-326">In alternativa, è possibile aggiungere parametri di tipo a `Compose` che indicano che funziona per *qualsiasi* `A` , `B` e `C` , purché questi parametri corrispondano a quelli previsti da `innerFn` e `outerFn` :</span><span class="sxs-lookup"><span data-stu-id="faf6e-326">As an alternative, then, you can add type parameters to `Compose` that indicate that it works for *any* `A`, `B`, and `C`, so long as these parameters match those expected by `innerFn` and `outerFn`:</span></span>

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="faf6e-327">Le Q# librerie standard forniscono una serie di operazioni e funzioni con parametri di tipo per semplificare l'espressione del flusso di controllo di ordine superiore.</span><span class="sxs-lookup"><span data-stu-id="faf6e-327">The Q# standard libraries provide a range of such type-parameterized operations and functions to make higher-order control flow easier to express.</span></span>
<span data-ttu-id="faf6e-328">Questi argomenti sono illustrati più avanti nella [ Q# Guida alla libreria standard](xref:microsoft.quantum.libraries.standard.intro).</span><span class="sxs-lookup"><span data-stu-id="faf6e-328">These are discussed further in the [Q# standard library guide](xref:microsoft.quantum.libraries.standard.intro).</span></span>


## <a name="callables-as-first-class-values"></a><span data-ttu-id="faf6e-329">Chiamabili come valori di prima classe</span><span class="sxs-lookup"><span data-stu-id="faf6e-329">Callables as First-Class Values</span></span>

<span data-ttu-id="faf6e-330">Una tecnica critica per ragionare sul flusso di controllo e la logica classica con funzioni anziché operazioni consiste nell'utilizzare le operazioni e le funzioni in Q# sono di *prima classe*.</span><span class="sxs-lookup"><span data-stu-id="faf6e-330">One critical technique for reasoning about control flow and classical logic using functions rather than operations is to utilize that operations and functions in Q# are *first-class*.</span></span>
<span data-ttu-id="faf6e-331">Ovvero ciascuno dei quali è il linguaggio di propria scelta.</span><span class="sxs-lookup"><span data-stu-id="faf6e-331">That is, they are each values in the language in their own right.</span></span>
<span data-ttu-id="faf6e-332">Il codice seguente, ad esempio, è perfettamente valido Q# , se poco indiretto:</span><span class="sxs-lookup"><span data-stu-id="faf6e-332">For instance, the following is perfectly valid Q# code, if a little indirect:</span></span>

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

<span data-ttu-id="faf6e-333">Il valore della variabile `ourH` nel frammento di codice precedente è quindi l'operazione <xref:microsoft.quantum.intrinsic.h> , in modo che sia possibile chiamare tale valore come qualsiasi altra operazione.</span><span class="sxs-lookup"><span data-stu-id="faf6e-333">The value of the variable `ourH` in the previous snippet is then the operation <xref:microsoft.quantum.intrinsic.h>, such that you can call that value like any other operation.</span></span>
<span data-ttu-id="faf6e-334">Con questa possibilità, è possibile scrivere operazioni che accettano operazioni come parte dell'input, formando concetti di flusso di controllo di ordine superiore.</span><span class="sxs-lookup"><span data-stu-id="faf6e-334">With this ability, you can write operations that take operations as a part of their input, forming higher-order control flow concepts.</span></span>
<span data-ttu-id="faf6e-335">Si supponga, ad esempio, di voler "quadrare" un'operazione applicando due volte lo stesso qubit di destinazione.</span><span class="sxs-lookup"><span data-stu-id="faf6e-335">For instance, you could imagine wanting to "square" an operation by applying it twice to the same target qubit.</span></span>

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a><span data-ttu-id="faf6e-336">Restituzione di operazioni da una funzione</span><span class="sxs-lookup"><span data-stu-id="faf6e-336">Returning operations from a function</span></span>

<span data-ttu-id="faf6e-337">È importante sottolineare che è anche possibile restituire le operazioni come parte degli output, in modo da poter isolare alcuni tipi di logica condizionale classica come funzione classica, che restituisce una descrizione di un programma Quantum sotto forma di operazione.</span><span class="sxs-lookup"><span data-stu-id="faf6e-337">It's important to emphasize that you can also return operations as a part of outputs, such that you can isolate some kinds of classical conditional logic as a classical function, which returns a description of a quantum program in the form of an operation.</span></span>
<span data-ttu-id="faf6e-338">Come esempio semplice, si consideri l'esempio di Teleporting, in cui la parte che riceve un messaggio classico a due bit deve usare il messaggio per decodificare i qubit nello stato di teleporte appropriato.</span><span class="sxs-lookup"><span data-stu-id="faf6e-338">As a simple example, consider the teleportation example, in which the party receiving a two-bit classical message needs to use the message to decode their qubit into the proper teleported state.</span></span>
<span data-ttu-id="faf6e-339">È possibile scrivere questo valore in termini di funzione che accetta i due bit classici e restituisce l'operazione di decodifica corretta.</span><span class="sxs-lookup"><span data-stu-id="faf6e-339">You could write this in terms of a function that takes those two classical bits and returns the proper decoding operation.</span></span>

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

<span data-ttu-id="faf6e-340">Questa nuova funzione è effettivamente una funzione, in quanto se viene chiamata con gli stessi valori di `hereBit` e `thereBit` , viene sempre restituita la stessa operazione.</span><span class="sxs-lookup"><span data-stu-id="faf6e-340">This new function is indeed a function, in that if you call it with the same values of `hereBit` and `thereBit`, you always get back the same operation.</span></span>
<span data-ttu-id="faf6e-341">Pertanto, il decodificatore può essere eseguito in modo sicuro all'interno di operazioni senza dover ragionare sul modo in cui la logica di decodifica interagisce con le definizioni delle diverse specializzazioni delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="faf6e-341">Thus, the decoder can safely run inside operations without having to reason about how the decoding logic interacts with the definitions of the different operation specializations.</span></span>
<span data-ttu-id="faf6e-342">Ovvero, la logica classica all'interno di una funzione è isolata, garantendo al compilatore che la chiamata di funzione possa essere riordinata con impuneità purché l'input venga mantenuto.</span><span class="sxs-lookup"><span data-stu-id="faf6e-342">That is, the classical logic inside a function is isolated, guaranteeing to the compiler that the function call can be reordered with impunity so long as the input is preserved.</span></span>


## <a name="partial-application"></a><span data-ttu-id="faf6e-343">Applicazione parziale</span><span class="sxs-lookup"><span data-stu-id="faf6e-343">Partial Application</span></span>

<span data-ttu-id="faf6e-344">È possibile eseguire molte altre operazioni con funzioni che restituiscono operazioni usando un' *applicazione parziale*, in cui è possibile fornire una o più parti dell'input a una funzione o a un'operazione senza chiamarla effettivamente.</span><span class="sxs-lookup"><span data-stu-id="faf6e-344">You can do significantly more with functions that return operations by using *partial application*, in which you provide one or more parts of the input to a function or operation without actually calling it.</span></span> <span data-ttu-id="faf6e-345">Nell'esempio precedente `ApplyTwice` , è possibile indicare che non si desidera specificare, immediatamente, a quale qubit deve essere applicata l'operazione di input:</span><span class="sxs-lookup"><span data-stu-id="faf6e-345">In the earlier `ApplyTwice` example, you can indicate that you don't want to specify, right away, to which qubit the input operation should apply:</span></span>

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

<span data-ttu-id="faf6e-346">In questo caso, la variabile locale `twiceOp` contiene l'operazione parzialmente applicata `ApplyTwice(op, _)` , dove `_` indica parti dell'input che non sono state ancora specificate.</span><span class="sxs-lookup"><span data-stu-id="faf6e-346">In this case, the local variable `twiceOp` holds the partially applied operation `ApplyTwice(op, _)`, where `_` indicates parts of the input that have not yet been specified.</span></span>
<span data-ttu-id="faf6e-347">Quando si chiama `twiceOp` nella riga successiva, viene passato come input all'operazione parzialmente applicata tutte le parti rimanenti dell'input per l'operazione originale.</span><span class="sxs-lookup"><span data-stu-id="faf6e-347">When you call `twiceOp` in the next line, you pass as input to the partially applied operation all of the remaining parts of the input to the original operation.</span></span>
<span data-ttu-id="faf6e-348">Pertanto, il frammento di codice precedente è effettivamente identico alla chiamata `ApplyTwice(op, target)` diretta, salvo per il fatto che è stata introdotta una nuova variabile locale, in modo che sia possibile ritardare la chiamata fornendo alcune parti dell'input.</span><span class="sxs-lookup"><span data-stu-id="faf6e-348">Thus, the previous snippet is effectively identical to having called `ApplyTwice(op, target)` directly, save for that you have introduced a new local variable so you can delay the call while providing some parts of the input.</span></span>

<span data-ttu-id="faf6e-349">Poiché un'operazione che è stata applicata parzialmente non viene effettivamente chiamata fino a quando non viene fornito l'intero input, è possibile applicare parzialmente le operazioni anche all'interno di funzioni.</span><span class="sxs-lookup"><span data-stu-id="faf6e-349">Since an operation that has been partially applied is not actually called until its entire input has been provided, you can safely partially apply operations even from within functions.</span></span>

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

<span data-ttu-id="faf6e-350">In linea di base, la logica classica in `SquareOperation` potrebbe essere stata molto più complessa, ma è ancora isolata dal resto di un'operazione garantita dal fatto che il compilatore possa offrire informazioni sulle funzioni.</span><span class="sxs-lookup"><span data-stu-id="faf6e-350">In principle, the classical logic within `SquareOperation` could have been much more involved, but it is still isolated from the rest of an operation by the guarantees that the compiler can offer about functions.</span></span> <span data-ttu-id="faf6e-351">La Q# libreria standard usa questo approccio per esprimere il flusso di controllo classico in modo che i programmi Quantum possano usare facilmente.</span><span class="sxs-lookup"><span data-stu-id="faf6e-351">The Q# standard library uses this approach throughout for expressing classical control flow in a way that quantum programs can readily use.</span></span>


## <a name="recursion"></a><span data-ttu-id="faf6e-352">Ricorsione</span><span class="sxs-lookup"><span data-stu-id="faf6e-352">Recursion</span></span>

<span data-ttu-id="faf6e-353">Q# le chiamabili possono essere ricorsivi direttamente o indirettamente.</span><span class="sxs-lookup"><span data-stu-id="faf6e-353">Q# callables are allowed to be directly or indirectly recursive.</span></span>
<span data-ttu-id="faf6e-354">Ovvero un'operazione o una funzione può chiamare se stessa oppure può chiamare un altro oggetto chiamabile che chiama direttamente o indirettamente l'operazione chiamabile.</span><span class="sxs-lookup"><span data-stu-id="faf6e-354">That is, an operation or function can call itself, or it can call another callable that directly or indirectly calls the callable operation.</span></span>

<span data-ttu-id="faf6e-355">Sono tuttavia disponibili due commenti importanti sull'utilizzo della ricorsione:</span><span class="sxs-lookup"><span data-stu-id="faf6e-355">There are two important comments about the use of recursion, however:</span></span>

- <span data-ttu-id="faf6e-356">L'uso della ricorsione nelle operazioni potrebbe interferire con determinate ottimizzazioni.</span><span class="sxs-lookup"><span data-stu-id="faf6e-356">The use of recursion in operations is likely to interfere with certain optimizations.</span></span>
  <span data-ttu-id="faf6e-357">Questa interferenza può avere un notevole effetto sul tempo di esecuzione dell'algoritmo.</span><span class="sxs-lookup"><span data-stu-id="faf6e-357">This interference can have a substantial impact on the execution time of the algorithm.</span></span>
- <span data-ttu-id="faf6e-358">Quando viene eseguito in un dispositivo Quantum effettivo, lo spazio dello stack potrebbe essere limitato e quindi la ricorsione profonda può causare un errore di Runtime.</span><span class="sxs-lookup"><span data-stu-id="faf6e-358">When running on an actual quantum device, stack space might be limited, and so deep recursion can lead to a runtime error.</span></span>
  <span data-ttu-id="faf6e-359">In particolare, il Q# compilatore e il runtime non identificano e ottimizzano la ricorsione Tail.</span><span class="sxs-lookup"><span data-stu-id="faf6e-359">In particular, the Q# compiler and runtime do not identify and optimize tail recursion.</span></span>

## <a name="next-steps"></a><span data-ttu-id="faf6e-360">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="faf6e-360">Next steps</span></span>

<span data-ttu-id="faf6e-361">Informazioni sulle [variabili](xref:microsoft.quantum.guide.variables) in Q# .</span><span class="sxs-lookup"><span data-stu-id="faf6e-361">Learn about [Variables](xref:microsoft.quantum.guide.variables) in Q#.</span></span>