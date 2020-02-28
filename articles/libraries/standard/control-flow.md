---
title: 'Controlli di flusso nel libararies standard Q #'
description: 'Informazioni sulle funzioni e sulle operazioni di controllo del flusso nella libreria Microsoft Q # standard.'
author: QuantumWriter
uid: microsoft.quantum.concepts.control-flow
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: b41b3edd7a3e3ac13dbda106a869f4cba8183600
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907172"
---
# <a name="higher-order-control-flow"></a><span data-ttu-id="c002b-103">Flusso di controllo di ordine superiore</span><span class="sxs-lookup"><span data-stu-id="c002b-103">Higher-Order Control Flow</span></span> #

<span data-ttu-id="c002b-104">Uno dei ruoli principali della libreria standard è quello di semplificare l'espressione di idee algoritmiche di alto livello come [programmi Quantum](https://en.wikipedia.org/wiki/Quantum_programming).</span><span class="sxs-lookup"><span data-stu-id="c002b-104">One of the primary roles of the standard library is to make it easier to express high-level algorithmic ideas as [quantum programs](https://en.wikipedia.org/wiki/Quantum_programming).</span></span>
<span data-ttu-id="c002b-105">In questo modo, il canone Q # offre un'ampia gamma di costrutti di controllo di flusso diversi, ognuno implementato usando un'applicazione parziale di funzioni e operazioni.</span><span class="sxs-lookup"><span data-stu-id="c002b-105">Thus, the Q# canon provides a variety of different flow control constructs, each implemented using partial application of functions and operations.</span></span>
<span data-ttu-id="c002b-106">Passando immediatamente ad esempio, si consideri il caso in cui si vuole creare una "CNOT Ladder" in un registro:</span><span class="sxs-lookup"><span data-stu-id="c002b-106">Jumping immediately into an example, consider the case in which one wants to construct a "CNOT ladder" on a register:</span></span>

```qsharp
let nQubits = Length(register);
CNOT(register[0], register[1]);
CNOT(register[1], register[2]);
// ...
CNOT(register[nQubits - 2], register[nQubits - 1]);
```

<span data-ttu-id="c002b-107">È possibile esprimere questo modello usando i cicli di iterazione e `for`:</span><span class="sxs-lookup"><span data-stu-id="c002b-107">We can express this pattern by using iteration and `for` loops:</span></span>

```qsharp
for (idxQubit in 0..nQubits - 2) {
    CNOT(register[idxQubit], register[idxQubit + 1]);
}
```

<span data-ttu-id="c002b-108">Espressa in termini di <xref:microsoft.quantum.canon.applytoeachca> e funzioni di manipolazione di matrici come <xref:microsoft.quantum.arrays.zip>, tuttavia, questo è molto più breve e più facile da leggere:</span><span class="sxs-lookup"><span data-stu-id="c002b-108">Expressed in terms of <xref:microsoft.quantum.canon.applytoeachca> and array manipulation functions such as <xref:microsoft.quantum.arrays.zip>, however, this is much shorter and easier to read:</span></span>

```qsharp
ApplyToEachCA(CNOT, Zip(register[0..nQubits - 2], register[1..nQubits - 1]));
```

<span data-ttu-id="c002b-109">Nella parte restante di questa sezione vengono forniti alcuni esempi di come usare le varie operazioni e funzioni di controllo di flusso fornite dal canonico per esprimere in modo compatto i programmi Quantum.</span><span class="sxs-lookup"><span data-stu-id="c002b-109">In the rest of this section, we will provide a number of examples of how to use the various flow control operations and functions provided by the canon to compactly express quantum programs.</span></span>

## <a name="applying-operations-and-functions-over-arrays-and-ranges"></a><span data-ttu-id="c002b-110">Applicazione di operazioni e funzioni su matrici e intervalli</span><span class="sxs-lookup"><span data-stu-id="c002b-110">Applying Operations and Functions over Arrays and Ranges</span></span> ##

<span data-ttu-id="c002b-111">Una delle astrazioni principali fornite da Canon è quella di iterazione.</span><span class="sxs-lookup"><span data-stu-id="c002b-111">One of the primary abstractions provided by the canon is that of iteration.</span></span>
<span data-ttu-id="c002b-112">Si consideri, ad esempio, un elemento unitario nel formato $U \otimes U \otimes \cdots \otimes U $ per un singolo qubit unitario $U $.</span><span class="sxs-lookup"><span data-stu-id="c002b-112">For instance, consider a unitary of the form $U \otimes U \otimes \cdots \otimes U$ for a single-qubit unitary $U$.</span></span>
<span data-ttu-id="c002b-113">In Q # è possibile usare <xref:microsoft.quantum.arrays.indexrange> per rappresentare questo come un ciclo di `for` su un registro:</span><span class="sxs-lookup"><span data-stu-id="c002b-113">In Q#, we might use <xref:microsoft.quantum.arrays.indexrange> to represent this as as a `for` loop over a register:</span></span>

```qsharp
/// # Summary
/// Applies $H$ to all qubits in a register.
operation ApplyHadamardToAll(
    register : Qubit[])
: Unit is Adj + Ctl {
    for (qubit in register) {
        H(qubit);
    }
}
```

<span data-ttu-id="c002b-114">È quindi possibile usare questa nuova operazione come `HAll(register)` per applicare $H \otimes H \otimes \cdots \otimes H $.</span><span class="sxs-lookup"><span data-stu-id="c002b-114">We can then use this new operation as `HAll(register)` to apply $H \otimes H \otimes \cdots \otimes H$.</span></span>

<span data-ttu-id="c002b-115">Si tratta tuttavia di un'operazione complessa, in particolare in un algoritmo di dimensioni maggiori.</span><span class="sxs-lookup"><span data-stu-id="c002b-115">This is cumbersome to do, however, especially in a larger algorithm.</span></span>
<span data-ttu-id="c002b-116">Questo approccio è inoltre specializzato per l'operazione specifica che si vuole applicare a ogni qubit.</span><span class="sxs-lookup"><span data-stu-id="c002b-116">Moreover, this approach is specialized to the particular operation that we wish to apply to each qubit.</span></span>
<span data-ttu-id="c002b-117">È possibile utilizzare il fatto che le operazioni siano di prima classe per esprimere questo concetto algoritmico in modo più esplicito:</span><span class="sxs-lookup"><span data-stu-id="c002b-117">We can use the fact that operations are first-class to express this algorithmic concept more explicitly:</span></span>

```qsharp
ApplyToEachCA(H, register);
```

<span data-ttu-id="c002b-118">Il suffisso `CA` indica che la chiamata a `ApplyToEach` è a sua volta adjointable e controllabile.</span><span class="sxs-lookup"><span data-stu-id="c002b-118">Here, the suffix `CA` indicates that the call to `ApplyToEach` is itself adjointable and controllable.</span></span>
<span data-ttu-id="c002b-119">Pertanto, se `U` supporta `Adjoint` e `Controlled`, le righe seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="c002b-119">Thus, if `U` supports `Adjoint` and `Controlled`, the following lines are equivalent:</span></span>

```qsharp
Adjoint ApplyToEachCA(U, register);
ApplyToEachCA(Adjoint U, register);
```

<span data-ttu-id="c002b-120">In particolare, ciò significa che le chiamate a `ApplyToEachCA` possono comparire in operazioni per le quali viene generata automaticamente una specializzazione contigua.</span><span class="sxs-lookup"><span data-stu-id="c002b-120">In particular, this means that calls to `ApplyToEachCA` can appear in operations for which an adjoint specialization is auto-generated.</span></span>
<span data-ttu-id="c002b-121">Analogamente, <xref:microsoft.quantum.canon.applytoeachindex> è utile per rappresentare i modelli del form `U(0, targets[0]); U(1, targets[1]); ...`e offre versioni per ogni combinazione di funtori supportata dal relativo input.</span><span class="sxs-lookup"><span data-stu-id="c002b-121">Similarly, <xref:microsoft.quantum.canon.applytoeachindex> is useful for representing patterns of the form `U(0, targets[0]); U(1, targets[1]); ...`, and offers versions for each combination of functors supported by its input.</span></span>

> [!TIP]
> <span data-ttu-id="c002b-122">`ApplyToEach` è parametrizzato con parametri di tipo in modo che possa essere utilizzato con operazioni che accettano input diversi da `Qubit`.</span><span class="sxs-lookup"><span data-stu-id="c002b-122">`ApplyToEach` is type-parameterized such that it can be used with operations that take inputs other than `Qubit`.</span></span>
> <span data-ttu-id="c002b-123">Si supponga, ad esempio, che `codeBlocks` sia una matrice di <xref:microsoft.quantum.errorcorrection.logicalregister> valori che devono essere ripristinati.</span><span class="sxs-lookup"><span data-stu-id="c002b-123">For example, suppose that `codeBlocks` is an array of <xref:microsoft.quantum.errorcorrection.logicalregister> values that need to be recovered.</span></span>
> <span data-ttu-id="c002b-124">Quindi `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` applicherà il codice di correzione degli errori `code` e la funzione di ripristino `recoveryFn` a ogni blocco in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="c002b-124">Then `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` will apply the error-correcting code `code` and recovery function `recoveryFn` to each block independently.</span></span>
> <span data-ttu-id="c002b-125">Questo vale anche per gli input classici: `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` applica una rotazione di $ \Pi/$2 circa $X $ seguito da una rotazione di $pi/$3 su $Y $.</span><span class="sxs-lookup"><span data-stu-id="c002b-125">This holds even for classical inputs: `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` will apply a rotation of $\pi / 2$ about $X$ followed by a rotation of $pi / 3$ about $Y$.</span></span>

<span data-ttu-id="c002b-126">Il canone Q # fornisce anche il supporto per modelli di enumerazione classici noti alla programmazione funzionale.</span><span class="sxs-lookup"><span data-stu-id="c002b-126">The Q# canon also provides support for classical enumeration patterns familiar to functional programming.</span></span>
<span data-ttu-id="c002b-127">Ad esempio, <xref:microsoft.quantum.arrays.fold> implementa il pattern $f (f (f (s\_{\Text{Initial}}, x\_0), x\_1), \dots) $ per ridurre una funzione in un elenco.</span><span class="sxs-lookup"><span data-stu-id="c002b-127">For instance, <xref:microsoft.quantum.arrays.fold> implements the pattern $f(f(f(s\_{\text{initial}}, x\_0), x\_1), \dots)$ for reducing a function over a list.</span></span>
<span data-ttu-id="c002b-128">Questo modello può essere utilizzato per implementare somme, prodotti, minima, Maxima e altre funzioni di questo tipo:</span><span class="sxs-lookup"><span data-stu-id="c002b-128">This pattern can be used to implement sums, products, minima, maxima and other such functions:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
function Plus(a : Int, b : Int) : Int { return a + b; }
function Sum(xs : Int[]) {
    return Fold(Sum, 0, xs);
}
```

<span data-ttu-id="c002b-129">Analogamente, è possibile usare funzioni come <xref:microsoft.quantum.arrays.mapped> e <xref:microsoft.quantum.arrays.mappedbyindex> per esprimere i concetti di programmazione funzionale in Q #.</span><span class="sxs-lookup"><span data-stu-id="c002b-129">Similarly, functions like <xref:microsoft.quantum.arrays.mapped> and <xref:microsoft.quantum.arrays.mappedbyindex> can be used to express functional programming concepts in Q#.</span></span>

## <a name="composing-operations-and-functions"></a><span data-ttu-id="c002b-130">Composizione di operazioni e funzioni</span><span class="sxs-lookup"><span data-stu-id="c002b-130">Composing Operations and Functions</span></span> ##

<span data-ttu-id="c002b-131">I costrutti del flusso di controllo offerti dalla Canon accettano operazioni e funzioni come input, in modo che sia utile poter comporre diverse operazioni o funzioni in un singolo chiamabile.</span><span class="sxs-lookup"><span data-stu-id="c002b-131">The control flow constructs offered by the canon take operations and functions as their inputs, such that it is helpful to be able to compose several operations or functions into a single callable.</span></span>
<span data-ttu-id="c002b-132">Ad esempio, il modello $UVU ^ {\dagger} $ è molto comune nella programmazione quantistica, in modo che il canone fornisca l'operazione <xref:microsoft.quantum.canon.applywith> come un'astrazione per questo modello.</span><span class="sxs-lookup"><span data-stu-id="c002b-132">For instance, the pattern $UVU^{\dagger}$ is extremely common in quantum programming, such that the canon provides the operation <xref:microsoft.quantum.canon.applywith> as an abstraction for this pattern.</span></span>
<span data-ttu-id="c002b-133">Questa astrazione consente anche un Compliation più efficiente nei circuiti, perché `Controlled` agire sulla sequenza `U(qubit); V(qubit); Adjoint U(qubit);` non deve agire su ogni `U`.</span><span class="sxs-lookup"><span data-stu-id="c002b-133">This abstraction also allows for more efficient compliation into circuits, as `Controlled` acting on the sequence `U(qubit); V(qubit); Adjoint U(qubit);` does not need to act on each `U`.</span></span>
<span data-ttu-id="c002b-134">Per verificarlo, consentire a $c (U) $ di essere l'unitario che rappresenta `Controlled U([control], target)` e lasciare che $c (V) $ venga definito nello stesso modo.</span><span class="sxs-lookup"><span data-stu-id="c002b-134">To see this, let $c(U)$ be the unitary representing `Controlled U([control], target)` and let $c(V)$ be defined in the same way.</span></span>
<span data-ttu-id="c002b-135">Quindi, per uno stato arbitrario $ \ket{\psi} $, \begin{align} c (U) c (V) c (U) ^ \dagger \ket{1} \otimes \ket{\psi} & = \ket{1} \otimes (UVU ^ {\dagger} \ket{\psi}) \\\\ & = (\boldone \otimes U) (c (V)) (\boldone \otimes U ^ \dagger) \ket{1} \otimes \ket{\psi}.</span><span class="sxs-lookup"><span data-stu-id="c002b-135">Then for an arbitrary state $\ket{\psi}$, \begin{align} c(U) c(V) c(U)^\dagger \ket{1} \otimes \ket{\psi} & = \ket{1} \otimes (UVU^{\dagger} \ket{\psi}) \\\\ & = (\boldone \otimes U) (c(V)) (\boldone \otimes U^\dagger) \ket{1} \otimes \ket{\psi}.</span></span>
<span data-ttu-id="c002b-136">\end{align} in base alla definizione di `Controlled`.</span><span class="sxs-lookup"><span data-stu-id="c002b-136">\end{align} by the definition of `Controlled`.</span></span>
<span data-ttu-id="c002b-137">D'altra parte, \begin{align} c (U) c (V) c (U) ^ \dagger \ket{0} \otimes \ket{\psi} & = \ket{0} \otimes \ket{\psi} \\\\ & = \ket{0} \otimes (UU ^ \dagger \ket{\psi}) \\\\ & = (\boldone \otimes U) (c (V)) (\boldone \otimes U ^ \dagger) \ket{0} \otimes \ket{\psi}.</span><span class="sxs-lookup"><span data-stu-id="c002b-137">On the other hand, \begin{align} c(U) c(V) c(U)^\dagger \ket{0} \otimes \ket{\psi} & = \ket{0} \otimes \ket{\psi} \\\\ & = \ket{0} \otimes (UU^\dagger \ket{\psi}) \\\\ & = (\boldone \otimes U) (c(V)) (\boldone \otimes U^\dagger) \ket{0} \otimes \ket{\psi}.</span></span>
<span data-ttu-id="c002b-138">\end{align} per linearità, possiamo concludere che è possibile fattorizzare $U $ out in questo modo per tutti gli Stati di input.</span><span class="sxs-lookup"><span data-stu-id="c002b-138">\end{align} By linearity, we can conclude that we can factor $U$ out in this way for all input states.</span></span>
<span data-ttu-id="c002b-139">Ovvero $c (UVU ^ \dagger) = U c (V) U ^ \dagger $.</span><span class="sxs-lookup"><span data-stu-id="c002b-139">That is, $c(UVU^\dagger) = U c(V) U^\dagger$.</span></span>
<span data-ttu-id="c002b-140">Poiché le operazioni di controllo possono risultare costose in generale, l'uso di varianti controllate come `WithC` e `WithCA` può ridurre il numero di funtori di controllo che devono essere applicati.</span><span class="sxs-lookup"><span data-stu-id="c002b-140">Since controlling operations can be expensive in general, using controlled variants such as `WithC` and `WithCA` can help reduce the number of control functors that need to be applied.</span></span>

> [!NOTE]
> <span data-ttu-id="c002b-141">Un'altra conseguenza del factoring di $U $ è che non è necessario neanche capire come applicare il `Controlled` functor a `U`.</span><span class="sxs-lookup"><span data-stu-id="c002b-141">One other consequence of factoring out $U$ is that we need not even know how to apply the `Controlled` functor to `U`.</span></span>
> <span data-ttu-id="c002b-142">`ApplyWithCA` ha pertanto una firma più debole rispetto a quanto previsto:</span><span class="sxs-lookup"><span data-stu-id="c002b-142">`ApplyWithCA` therefore has a weaker signature than might be expected:</span></span>
> ```qsharp
> ApplyWithCA<'T> : (('T => Unit is Adj),
>     ('T => Unit is Adj + Ctl), 'T) => Unit
> ```

<span data-ttu-id="c002b-143">Analogamente, <xref:microsoft.quantum.canon.bound> genera operazioni che applicano a sua volta una sequenza di altre operazioni.</span><span class="sxs-lookup"><span data-stu-id="c002b-143">Similarly, <xref:microsoft.quantum.canon.bound> produces operations which apply a sequence of other operations in turn.</span></span>
<span data-ttu-id="c002b-144">Ad esempio, gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="c002b-144">For instance, the following are equivalent:</span></span>

```qsharp
H(qubit); X(qubit);
Bound([H, X], qubit);
```

<span data-ttu-id="c002b-145">La combinazione con i modelli di iterazione può rendere questa operazione particolarmente utile:</span><span class="sxs-lookup"><span data-stu-id="c002b-145">Combining with iteration patterns can make this especially useful:</span></span>

```qsharp
// Bracket the quantum Fourier transform with $XH$ on each qubit.
ApplyWith(ApplyToEach(Bound([H, X]), _), QFT, _);
```

### <a name="time-ordered-composition"></a><span data-ttu-id="c002b-146">Composizione Time-ordered</span><span class="sxs-lookup"><span data-stu-id="c002b-146">Time-Ordered Composition</span></span> ###

<span data-ttu-id="c002b-147">Possiamo continuare a usare il controllo di flusso in termini di funzioni di applicazione e classiche parziali ed è possibile modellare concetti quantistici anche piuttosto sofisticati in termini di controllo di flusso classico.</span><span class="sxs-lookup"><span data-stu-id="c002b-147">We can go still further by thinking of flow control in terms of partial application and classical functions, and can model even fairly sophisticated quantum concepts in terms of classical flow control.</span></span>
<span data-ttu-id="c002b-148">Questa analogia viene resa precisa dal riconoscimento che gli operatori unitari corrispondono esattamente agli effetti collaterali delle operazioni di chiamata, in modo che qualsiasi scomposizione di operatori unitari in termini di altri operatori unitari corrisponda alla costruzione di una particolare sequenza di chiamata per subroutine classiche che emettono istruzioni per agire come operatori unitari specifici.</span><span class="sxs-lookup"><span data-stu-id="c002b-148">This analogy is made precise by the recognition that unitary operators correspond exactly to the side effects of calling operations, such that any decomposition of unitary operators in terms of other unitary operators corresponds to constructing a particular calling sequence for classical subroutines which emit instructions to act as particular unitary operators.</span></span>
<span data-ttu-id="c002b-149">In questa visualizzazione, `Bound` è esattamente la rappresentazione del prodotto Matrix, dal momento che `Bound([A, B])(target)` è equivalente a `A(target); B(target);`, che a sua volta è la sequenza chiamante corrispondente a $BA $.</span><span class="sxs-lookup"><span data-stu-id="c002b-149">Under this view, `Bound` is precisely the representation of the matrix product, since `Bound([A, B])(target)` is equivalent to `A(target); B(target);`, which in turn is the calling sequence corresponding to $BA$.</span></span>

<span data-ttu-id="c002b-150">Un esempio più sofisticato è l' [espansione Trotter-Suzuki](https://arxiv.org/abs/math-ph/0506007v1).</span><span class="sxs-lookup"><span data-stu-id="c002b-150">A more sophisticated example is the [Trotter–Suzuki expansion](https://arxiv.org/abs/math-ph/0506007v1).</span></span>
<span data-ttu-id="c002b-151">Come illustrato nella sezione relativa alla rappresentazione dinamica del generatore di [strutture di dati](xref:microsoft.quantum.libraries.data-structures), l'espansione Trotter-Suzuki fornisce un modo particolarmente utile per esprimere esponenziali matrici.</span><span class="sxs-lookup"><span data-stu-id="c002b-151">As discussed in the Dynamical Generator Representation section of [data structures](xref:microsoft.quantum.libraries.data-structures), the Trotter–Suzuki expansion provides a particularly useful way of expressing matrix exponentials.</span></span>
<span data-ttu-id="c002b-152">Ad esempio, l'applicazione dell'espansione con l'ordine più basso produce che per tutti gli operatori $A $ e $B $ tale che $A = A ^ \dagger $ e $B = B ^ \dagger $, \begin{align} \tag{★} \label{EQ: Trotter-Suzuki-0} \exp (i [A + B] t) = \ lim_ {n\to\infty} \left (\exp (i A t/n) \exp (i B t/n) \right) ^ n.</span><span class="sxs-lookup"><span data-stu-id="c002b-152">For instance, applying the expansion at its lowest order yields that for any operators $A$ and $B$ such that $A = A^\dagger$ and $B = B^\dagger$, \begin{align} \tag{★} \label{eq:trotter-suzuki-0} \exp(i [A + B] t) = \lim_{n\to\infty} \left(\exp(i A t / n) \exp(i B t / n)\right)^n.</span></span>
<span data-ttu-id="c002b-153">\end{align} colloquialmente, questo afferma che è possibile evolvere approssimativamente uno stato in $A + B $, in alternativa in $A $ e $B $ alone.</span><span class="sxs-lookup"><span data-stu-id="c002b-153">\end{align} Colloquially, this says that we can approximately evolve a state under $A + B$ by alternately evolving under $A$ and $B$ alone.</span></span>
<span data-ttu-id="c002b-154">Se l'evoluzione viene rappresentata in $A $ da un'operazione `A : (Double, Qubit[]) => Unit` applicabile $e ^ {i t A} $, la rappresentazione dell'espansione Trotter – Suzuki in termini di ridisposizione delle sequenze di chiamata diventa chiara.</span><span class="sxs-lookup"><span data-stu-id="c002b-154">If we represent evolution under $A$ by an operation `A : (Double, Qubit[]) => Unit` that applies $e^{i t A}$, then the representation of the Trotter–Suzuki expansion in terms of rearranging calling sequences becomes clear.</span></span>
<span data-ttu-id="c002b-155">In concreto, data un'operazione `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` in modo che `A = U(0, _, _)` e `B = U(1, _, _)`, è possibile definire una nuova operazione che rappresenta l'integrale di `U` al momento $t $ generando sequenze nel form</span><span class="sxs-lookup"><span data-stu-id="c002b-155">Concretely, given an operation `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` such that `A = U(0, _, _)` and `B = U(1, _, _)`, we can define a new operation representing the integral of `U` at time $t$ by generating sequences of the form</span></span>

```qsharp
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
// ...
```

<span data-ttu-id="c002b-156">A questo punto, è ora possibile ragionare sull'espansione Trotter-Suzuki *senza riferimento ai meccanismi Quantum*.</span><span class="sxs-lookup"><span data-stu-id="c002b-156">At this point, we can now reason about the Trotter–Suzuki expansion *without reference to quantum mechanics at all*.</span></span>
<span data-ttu-id="c002b-157">L'espansione è effettivamente un modello di iterazione molto particolare motivato da $ \eqref{EQ: Trotter-Suzuki-0} $.</span><span class="sxs-lookup"><span data-stu-id="c002b-157">The expansion is effectively a very particular iteration pattern motivated by $\eqref{eq:trotter-suzuki-0}$.</span></span>
<span data-ttu-id="c002b-158">Questo modello di iterazione viene implementato da <xref:microsoft.quantum.canon.decomposeintotimestepsca>:</span><span class="sxs-lookup"><span data-stu-id="c002b-158">This iteration pattern is implemented by <xref:microsoft.quantum.canon.decomposeintotimestepsca>:</span></span>

```qsharp
// The 2 indicates how many terms we need to decompose,
// while the 1 indicates that we are using the
// first-order Trotter–Suzuki decomposoition.
DecomposeIntoTimeStepsCA((2, U), 1);
```

<span data-ttu-id="c002b-159">La firma di `DecomposeIntoTimeStepsCA` segue un modello comune in Q #, in cui le raccolte di cui è possibile eseguire il backup in base a matrici o a un elemento che calcola gli elementi in tempo reale sono rappresentate da tuple i cui primi elementi sono `Int` valori che ne indicano le lunghezze.</span><span class="sxs-lookup"><span data-stu-id="c002b-159">The signature of `DecomposeIntoTimeStepsCA` follows a common pattern in Q#, where collections that may be backed either by arrays or by something which compute elements on the fly are represented by tuples whose first elements are `Int` values indicating their lengths.</span></span>

## <a name="putting-it-together-controlling-operations"></a><span data-ttu-id="c002b-160">Inserimento insieme: controllo delle operazioni</span><span class="sxs-lookup"><span data-stu-id="c002b-160">Putting it Together: Controlling Operations</span></span> ##

<span data-ttu-id="c002b-161">Infine, la Canon si basa sul `Controlled` functor fornendo modi aggiuntivi per condizionare le operazioni quantistiche.</span><span class="sxs-lookup"><span data-stu-id="c002b-161">Finally, the canon builds on the `Controlled` functor by providing additional ways to condition quantum operations.</span></span>
<span data-ttu-id="c002b-162">Si tratta di una situazione comune, soprattutto in aritmetica quantistica, per condizionare le operazioni su stati di base computazionali diversi da $ \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="c002b-162">It is common, especially in quantum arithmetic, to condition operations on computational basis states other than $\ket{0\cdots 0}$.</span></span>
<span data-ttu-id="c002b-163">Utilizzando le operazioni e le funzioni di controllo introdotte in precedenza, è possibile utilizzare più condizioni di Quantum generali in un'unica istruzione.</span><span class="sxs-lookup"><span data-stu-id="c002b-163">Using the control operations and functions introduced above, we can more general quantum conditions in a single statement.</span></span>
<span data-ttu-id="c002b-164">Passiamo ora a come <xref:microsoft.quantum.canon.controlledonbitstring> (parametri di tipo sans), quindi suddividiamo le parti una alla volta.</span><span class="sxs-lookup"><span data-stu-id="c002b-164">Let's jump in to how <xref:microsoft.quantum.canon.controlledonbitstring> does it (sans type parameters), then we'll break down the pieces one by one.</span></span>
<span data-ttu-id="c002b-165">La prima cosa da fare è definire un'operazione che esegue effettivamente il pesante carico di implementazione del controllo sugli stati di base di calcolo arbitrari.</span><span class="sxs-lookup"><span data-stu-id="c002b-165">The first thing we'll need to do is to define an operation which actually does the heavy lifting of implementing the control on arbitrary computational basis states.</span></span>
<span data-ttu-id="c002b-166">Questa operazione, tuttavia, non viene chiamata direttamente, quindi si aggiunge `_` all'inizio del nome per indicare che si tratta di un'implementazione di un altro costrutto altrove.</span><span class="sxs-lookup"><span data-stu-id="c002b-166">We won't call this operation directly, however, and so we add `_` to the beginning of the name to indicate that it's an implementation of another construct elsewhere.</span></span>

```qsharp
operation _ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl),
    controlRegister : Qubit[],
    targetRegister: Qubit[])
: Unit is Adj + Ctl
```

<span data-ttu-id="c002b-167">Si noti che si accetta una stringa di bit, rappresentata come matrice di `Bool`, che verrà usata per specificare il condizionamento che si vuole applicare all'operazione `oracle` fornita.</span><span class="sxs-lookup"><span data-stu-id="c002b-167">Note that we take a string of bits, represented as a `Bool` array, that we use to specify the conditioning that we want to apply to the operation `oracle` that we are given.</span></span>
<span data-ttu-id="c002b-168">Poiché questa operazione esegue effettivamente direttamente l'applicazione, è necessario anche prendere i registri di controllo e di destinazione, entrambi rappresentati come `Qubit[]`.</span><span class="sxs-lookup"><span data-stu-id="c002b-168">Since this operation actually does the application directly, we also need to take the control and target registers, both represented here as `Qubit[]`.</span></span>

<span data-ttu-id="c002b-169">Si noti quindi che il controllo sullo stato di base di calcolo $ \ket{\vec{s}} = \ket{s\_0 s\_1 \dots s\_{n-1}} $ per una stringa di bit $ \vec{s} $ può essere realizzato trasformando $ \ket{\vec{s}} $ in $ \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="c002b-169">Next, we note that controlling on the computational basis state $\ket{\vec{s}} = \ket{s\_0 s\_1 \dots s\_{n - 1}}$ for a bit string $\vec{s}$ can be realized by transforming $\ket{\vec{s}}$ into $\ket{0\cdots 0}$.</span></span>
<span data-ttu-id="c002b-170">In particolare, $ \ket{\vec{s}} = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="c002b-170">In particular, $\ket{\vec{s}} = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}} \ket{0\cdots 0}$.</span></span>
<span data-ttu-id="c002b-171">Poiché $X ^ {\dagger} = X $, significa che $ \ket{0\dots 0} = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} \ket{\vec{s}} $.</span><span class="sxs-lookup"><span data-stu-id="c002b-171">Since $X^{\dagger} = X$, this implies that $\ket{0\dots 0} = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}} \ket{\vec{s}}$.</span></span>
<span data-ttu-id="c002b-172">È quindi possibile applicare $P = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} $, applicare `Controlled oracle`e trasformare nuovamente in $ \vec{s} $.</span><span class="sxs-lookup"><span data-stu-id="c002b-172">Thus, we can apply $P = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}}$, apply `Controlled oracle`, and transform back to $\vec{s}$.</span></span>
<span data-ttu-id="c002b-173">Questa costruzione è esattamente `ApplyWith`, quindi scriviamo il corpo della nuova operazione di conseguenza:</span><span class="sxs-lookup"><span data-stu-id="c002b-173">This construction is precisely `ApplyWith`, so we write the body of our new operation accordingly:</span></span>

```qsharp
{
    ApplyWithCA(
        ApplyPauliFromBitString(PauliX, false, bits, _),
        (Controlled oracle)(_, targetRegister),
        controlRegister
    );
}
```

<span data-ttu-id="c002b-174">In questo esempio è stato usato <xref:microsoft.quantum.canon.applypaulifrombitstring> per applicare $P $, applicando parzialmente la destinazione per l'uso con `ApplyWith`.</span><span class="sxs-lookup"><span data-stu-id="c002b-174">Here, we have used <xref:microsoft.quantum.canon.applypaulifrombitstring> to apply $P$, partially applying over its target for use with `ApplyWith`.</span></span>
<span data-ttu-id="c002b-175">Si noti, tuttavia, che è necessario trasformare il registro di *controllo* nel modulo desiderato, in modo da applicare parzialmente l'operazione interna `(Controlled oracle)` sulla *destinazione*.</span><span class="sxs-lookup"><span data-stu-id="c002b-175">Note, however, that we need to transform the *control* register to our desired form, so we partially apply the inner operation `(Controlled oracle)` on the *target*.</span></span>
<span data-ttu-id="c002b-176">In questo modo si lascia `ApplyWith` agire per racchiudere il registro di controllo con $P $, esattamente come si desidera.</span><span class="sxs-lookup"><span data-stu-id="c002b-176">This leaves `ApplyWith` acting to bracket the control register with $P$, exactly as we desired.</span></span>

<span data-ttu-id="c002b-177">A questo punto, è possibile eseguire questa operazione, ma in qualche modo non è in grado di soddisfare la nuova operazione, ad esempio l'applicazione del `Controlled` functor.</span><span class="sxs-lookup"><span data-stu-id="c002b-177">At this point, we could be done, but it is somehow unsatisfying that our new operation does not "feel" like applying the `Controlled` functor.</span></span>
<span data-ttu-id="c002b-178">In questo modo, si termina la definizione del nuovo concetto di flusso di controllo scrivendo una funzione che accetta l'oggetto Oracle da controllare e che restituisce una nuova operazione.</span><span class="sxs-lookup"><span data-stu-id="c002b-178">Thus, we finish defining our new control flow concept by writing a function that takes the oracle to be controlled and that returns a new operation.</span></span>
<span data-ttu-id="c002b-179">In questo modo, la nuova funzione ha un aspetto molto simile a `Controlled`, illustrando che è possibile definire facilmente nuovi costrutti di flusso di controllo con Q # e la Canon insieme:</span><span class="sxs-lookup"><span data-stu-id="c002b-179">In this way, our new function looks and feels very much like `Controlled`, illustrating that we can easily define powerful new control flow constructs using Q# and the canon together:</span></span>

```qsharp
function ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl))
: ((Qubit[], Qubit[]) => Unit is Adj + Ctl) {
    return _ControlledOnBitString(bits, oracle, _, _);
}
```
