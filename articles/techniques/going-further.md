---
title: 'Approfondimenti con le tecniche di Q #'
description: 'Esplorare gli argomenti avanzati in Q #, ad esempio la creazione di funzioni generiche e il prestito di qubits.'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.going-further
ms.openlocfilehash: 46ebf544c1d6e56f152a06d06151305fa972011a
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906900"
---
# <a name="going-further"></a><span data-ttu-id="fbe58-103">Più avanti</span><span class="sxs-lookup"><span data-stu-id="fbe58-103">Going Further</span></span> #

<span data-ttu-id="fbe58-104">Ora che si è appreso come scrivere programmi Quantum interessanti in Q #, questa sezione approfondisce ulteriormente introducendo alcuni argomenti più avanzati che dovrebbero risultare utili.</span><span class="sxs-lookup"><span data-stu-id="fbe58-104">Now that you've seen how to write interesting quantum programs in Q#, this section goes further by introducing a few more advanced topics that should prove useful going forward.</span></span>


## <a name="generic-operations-and-functions"></a><span data-ttu-id="fbe58-105">Operazioni e funzioni generiche</span><span class="sxs-lookup"><span data-stu-id="fbe58-105">Generic Operations and Functions</span></span> ##

> [!TIP]
> <span data-ttu-id="fbe58-106">Questa sezione presuppone una certa familiarità con i [Generics C#in ](https://docs.microsoft.com/dotnet/csharp/programming-guide/generics/introduction-to-generics), i [ F#generics in ](https://docs.microsoft.com/dotnet/fsharp/language-reference/generics/), [ C++ i modelli](https://docs.microsoft.com/cpp/cpp/templates-cpp)o approcci simili alla metaprogrammazione in altri linguaggi.</span><span class="sxs-lookup"><span data-stu-id="fbe58-106">This section assumes some basic familiarity with [generics in C#](https://docs.microsoft.com/dotnet/csharp/programming-guide/generics/introduction-to-generics), [generics in F#](https://docs.microsoft.com/dotnet/fsharp/language-reference/generics/), [C++ templates](https://docs.microsoft.com/cpp/cpp/templates-cpp), or similar approaches to metaprogramming in other languages.</span></span>

<span data-ttu-id="fbe58-107">Molte funzioni e operazioni che è possibile definire non si basano molto sui tipi di input, ma usano solo i tipi in modo implicito tramite un'altra funzione o un'altra operazione.</span><span class="sxs-lookup"><span data-stu-id="fbe58-107">Many functions and operations that we might wish to define do not actually heavily rely on the types of their inputs, but rather only implicitly use their types via some other function or operation.</span></span>
<span data-ttu-id="fbe58-108">Si consideri, ad esempio, il concetto di *mappa* comune a molti linguaggi funzionali; Data una funzione $f (x) $ e una raccolta di valori $\{x_1, x_2, \dots, x_n\}$, map restituisce una nuova raccolta $\{f (X_1), f (x_2), \dots, f (x_n)\}$.</span><span class="sxs-lookup"><span data-stu-id="fbe58-108">For example, consider the *map* concept common to many functional languages; given a function $f(x)$ and a collection of values $\{x_1, x_2, \dots, x_n\}$, map returns a new collection $\{f(x_1), f(x_2), \dots, f(x_n)\}$.</span></span>
<span data-ttu-id="fbe58-109">Per implementarlo in Q #, è possibile sfruttare le funzioni che sono la prima classe.</span><span class="sxs-lookup"><span data-stu-id="fbe58-109">To implement this in Q#, we can take advantage of that functions are first class.</span></span>
<span data-ttu-id="fbe58-110">Viene ora illustrato un esempio rapido di `Map`, usando ★ come segnaposto, mentre è possibile individuare i tipi necessari.</span><span class="sxs-lookup"><span data-stu-id="fbe58-110">Let's write out a quick example of `Map`, using ★ as a placeholder while we figure out what types we need.</span></span>

```qsharp
function Map(fn : (★ -> ★), values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="fbe58-111">Nota Questa funzione è molto simile indipendentemente dai tipi effettivi sostituiti.</span><span class="sxs-lookup"><span data-stu-id="fbe58-111">Note this function looks very much the same no matter what actual types we substitute in.</span></span>
<span data-ttu-id="fbe58-112">Un mapping da Integer a Paulis, ad esempio, ha un aspetto molto simile a quello di una mappa dai numeri a virgola mobile a stringhe:</span><span class="sxs-lookup"><span data-stu-id="fbe58-112">A map from integers to Paulis, for instance, looks much the same as a map from floating-point numbers to strings:</span></span>

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

<span data-ttu-id="fbe58-113">In linea di principio, è possibile scrivere una versione di `Map` per ogni coppia di tipi che si verificano, ma in questo caso è stata introdotta una serie di problemi.</span><span class="sxs-lookup"><span data-stu-id="fbe58-113">In principle, we could write a version of `Map` for every pair of types that we encounter, but this introduces a number of difficulties.</span></span>
<span data-ttu-id="fbe58-114">Se, ad esempio, si trova un bug in `Map`, è necessario assicurarsi che la correzione venga applicata in modo uniforme in tutte le versioni di `Map`.</span><span class="sxs-lookup"><span data-stu-id="fbe58-114">For instance, if we find a bug in `Map`, then we must ensure that the fix is applied uniformly across all versions of `Map`.</span></span>
<span data-ttu-id="fbe58-115">Inoltre, se si costruisce una nuova tupla o un tipo definito dall'utente, è ora necessario costruire anche un nuovo `Map` per procedere con il nuovo tipo.</span><span class="sxs-lookup"><span data-stu-id="fbe58-115">Moreover, if we construct a new tuple or UDT, then we must now also construct a new `Map` to go along with the new type.</span></span>
<span data-ttu-id="fbe58-116">Sebbene si tratti di un numero ridotto di funzioni di questo tipo, quando si raccolgono più funzioni dello stesso tipo di `Map`, il costo dell'introduzione di nuovi tipi diventa ingiustificatamente grande in ordine piuttosto breve.</span><span class="sxs-lookup"><span data-stu-id="fbe58-116">While this is tractable for a small number of such functions, as we collect more and more functions of the same form as `Map`, the cost of introducing new types becomes unreasonably large in fairly short order.</span></span>

<span data-ttu-id="fbe58-117">Gran parte di questa difficoltà, tuttavia, dal momento che non è stato fornito al compilatore le informazioni necessarie per riconoscere il modo in cui le diverse versioni di `Map` sono correlate.</span><span class="sxs-lookup"><span data-stu-id="fbe58-117">Much of this difficulty results, however, from that the we have not given the compiler the information it needs to recognize how the different versions of `Map` are related.</span></span>
<span data-ttu-id="fbe58-118">In realtà, si vuole che il compilatore tratti `Map` come un tipo di funzione matematica dai *tipi* q # alle funzioni q #.</span><span class="sxs-lookup"><span data-stu-id="fbe58-118">Effectively, we want the compiler to treat `Map` as some kind of mathematical function from Q# *types* to Q# functions.</span></span>
<span data-ttu-id="fbe58-119">Questa nozione viene formalizzata consentendo a funzioni e operazioni di avere *parametri di tipo*, nonché i parametri di tupla ordinari.</span><span class="sxs-lookup"><span data-stu-id="fbe58-119">This notion is formalized by allowing functions and operations to have *type parameters*, as well as their ordinary tuple parameters.</span></span>
<span data-ttu-id="fbe58-120">Negli esempi precedenti si desidera considerare `Map` come avere parametri di tipo `Int, Pauli` nel primo caso e `Double, String` nel secondo caso.</span><span class="sxs-lookup"><span data-stu-id="fbe58-120">In the examples above, we wish to think of `Map` as having type parameters `Int, Pauli` in the first case and `Double, String` in the second case.</span></span>
<span data-ttu-id="fbe58-121">Nella maggior parte dei casi, questi parametri di tipo possono essere usati come se fossero tipi normali: si usano valori di parametri di tipo per creare matrici e tuple, chiamare funzioni e operazioni e assegnare a variabili ordinarie o modificabili.</span><span class="sxs-lookup"><span data-stu-id="fbe58-121">For the most part, these type parameters can then be used as though they were ordinary types: we use values of type parameters to make arrays and tuples, call functions and operations, and assign to ordinary or mutable variables.</span></span>

> [!NOTE]
> <span data-ttu-id="fbe58-122">Il caso più estremo della dipendenza indiretta è quello di qubits, in cui un programma Q # non può basarsi direttamente sulla struttura del tipo di `Qubit`, ma **deve** passare tali tipi ad altre operazioni e funzioni.</span><span class="sxs-lookup"><span data-stu-id="fbe58-122">The most extreme case of indirect dependence is that of qubits, where a Q# program cannot directly rely on the structure of the `Qubit` type, but **must** pass such types to other operations and functions.</span></span>

<span data-ttu-id="fbe58-123">Tornando all'esempio precedente, si noterà che è necessario `Map` disporre di parametri di tipo, uno per rappresentare l'input per `fn` e uno per rappresentare l'output da `fn`.</span><span class="sxs-lookup"><span data-stu-id="fbe58-123">Returning to the example above, then, we can see that we need `Map` to have type parameters, one to represent the input to `fn` and one to represent the output from `fn`.</span></span>
<span data-ttu-id="fbe58-124">In Q # questa operazione viene scritta aggiungendo parentesi angolari (`<>`, non i Brake $ \braket{}$!) dopo il nome di una funzione o di un'operazione nella relativa dichiarazione e elencando ogni parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="fbe58-124">In Q#, this is written by adding angle brackets (that's `<>`, not brakets $\braket{}$!) after the name of a function or operation in its declaration, and by listing each type parameter.</span></span>
<span data-ttu-id="fbe58-125">Il nome di ogni parametro di tipo deve iniziare con un segno di `'`, a indicare che si tratta di un parametro di tipo e non di un tipo ordinario (noto anche come tipo *concreto* ).</span><span class="sxs-lookup"><span data-stu-id="fbe58-125">The name of each type parameter must start with a tick `'`, indicating that it is a type parameter and not a ordinary type (also known as a *concrete* type).</span></span>
<span data-ttu-id="fbe58-126">Per `Map`, scriviamo quindi:</span><span class="sxs-lookup"><span data-stu-id="fbe58-126">For `Map`, we thus write:</span></span>

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="fbe58-127">Si noti che la definizione di `Map<'Input, 'Output>` ha un aspetto molto simile a quello delle versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="fbe58-127">Note that the definition of `Map<'Input, 'Output>` looks extremely similar to the versions we wrote out before.</span></span>
<span data-ttu-id="fbe58-128">L'unica differenza consiste nel fatto che il compilatore è stato informato in modo esplicito che `Map` non dipende direttamente da quali `'Input` e `'Output` sono, ma funziona per i due tipi usando indirettamente tramite `fn`.</span><span class="sxs-lookup"><span data-stu-id="fbe58-128">The only difference is that we have explicitly informed the compiler that `Map` doesn't directly depend on what `'Input` and `'Output` are, but works for any two types by using them indirectly through `fn`.</span></span>
<span data-ttu-id="fbe58-129">Una volta definito `Map<'Input, 'Output>` in questo modo, è possibile chiamarlo come se fosse una funzione ordinaria:</span><span class="sxs-lookup"><span data-stu-id="fbe58-129">Once we have defined `Map<'Input, 'Output>` in this way, we can call it as though it was an ordinary function:</span></span>

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> <span data-ttu-id="fbe58-130">La scrittura di funzioni e funzioni generiche è un'unica posizione in cui "tuple-in tuple-out" è un modo utile per considerare le funzioni e le operazioni Q #.</span><span class="sxs-lookup"><span data-stu-id="fbe58-130">Writing generic functions and operations is one place where "tuple-in tuple-out" is a very useful way to think about Q# functions and operations.</span></span>
> <span data-ttu-id="fbe58-131">Poiché ogni funzione accetta esattamente un input e restituisce esattamente un output, un input di tipo `'T -> 'U` corrisponde a *qualsiasi* funzione Q #.</span><span class="sxs-lookup"><span data-stu-id="fbe58-131">Since every function takes exactly one input and returns exactly one output, an input of type `'T -> 'U` matches *any* Q# function whatsoever.</span></span>
> <span data-ttu-id="fbe58-132">Analogamente, qualsiasi operazione può essere passata a un input di tipo `'T => 'U`.</span><span class="sxs-lookup"><span data-stu-id="fbe58-132">Similarly, any operation can be passed to an input of type `'T => 'U`.</span></span>

<span data-ttu-id="fbe58-133">Come secondo esempio, si consideri la necessità di scrivere una funzione che restituisce la composizione di altre due funzioni:</span><span class="sxs-lookup"><span data-stu-id="fbe58-133">As a second example, consider the challenge of writing a function that returns the composition of two other functions:</span></span>

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="fbe58-134">In questo caso, è necessario specificare esattamente quali `A`, `B`e `C` sono, di conseguenza la limitazione dell'utilità della nuova funzione `Compose`.</span><span class="sxs-lookup"><span data-stu-id="fbe58-134">Here, we must specify exactly what `A`, `B`, and `C` are, hence severely limiting the utility of our new `Compose` function.</span></span>
<span data-ttu-id="fbe58-135">Dopotutto, `Compose` dipende solo da `A`, `B`e `C` *tramite* `innerFn` e `outerFn`.</span><span class="sxs-lookup"><span data-stu-id="fbe58-135">After all, `Compose` only depends on `A`, `B`, and `C` *via* `innerFn` and `outerFn`.</span></span>
<span data-ttu-id="fbe58-136">In alternativa, è possibile aggiungere parametri di tipo a `Compose` che indichino che funziona per *qualsiasi* `A`, `B`e `C`, purché questi parametri corrispondano a quelli previsti da `innerFn` e `outerFn`:</span><span class="sxs-lookup"><span data-stu-id="fbe58-136">As an alternative, then, we can add type parameters to `Compose` that indicate that it works for *any* `A`, `B`, and `C`, so long as these parameters match those expected by `innerFn` and `outerFn`:</span></span>

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="fbe58-137">Le librerie standard Q # forniscono una serie di operazioni e funzioni con parametri di tipo per semplificare l'espressione del flusso di controllo di ordine superiore.</span><span class="sxs-lookup"><span data-stu-id="fbe58-137">The Q# standard libraries provide a range of such type-parameterized operations and functions to make higher-order control flow easier to express.</span></span>
<span data-ttu-id="fbe58-138">Questi argomenti sono illustrati più avanti nella [Guida alla libreria standard Q #](xref:microsoft.quantum.libraries.standard.intro).</span><span class="sxs-lookup"><span data-stu-id="fbe58-138">These are discussed further in the [Q# standard library guide](xref:microsoft.quantum.libraries.standard.intro).</span></span>

## <a name="borrowing-qubits"></a><span data-ttu-id="fbe58-139">Prestito di qubits</span><span class="sxs-lookup"><span data-stu-id="fbe58-139">Borrowing Qubits</span></span> ##

<span data-ttu-id="fbe58-140">Il meccanismo di prestito consente l'allocazione di qubits che può essere usata come spazio scratch durante un calcolo.</span><span class="sxs-lookup"><span data-stu-id="fbe58-140">The borrowing mechanism allows the allocation of qubits that can be used as scratch space during a computation.</span></span> <span data-ttu-id="fbe58-141">Questi qubits in genere non sono in uno stato pulito, ovvero non vengono necessariamente inizializzati in uno stato noto, ad esempio $ \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="fbe58-141">These qubits are generally not in a clean state, i.e., they are not necessarily initialized in a known state such as $\ket{0}$.</span></span> <span data-ttu-id="fbe58-142">Si parla anche di qubits "Dirty", perché il loro stato è sconosciuto e può anche essere correlato ad altre parti della memoria del computer Quantum.</span><span class="sxs-lookup"><span data-stu-id="fbe58-142">One also speaks of "dirty" qubits as their state is unknown and can even be entangled with other parts of the quantum computer's memory.</span></span> <span data-ttu-id="fbe58-143">Tra i casi d'uso noti dei qubits Dirty sono implementazioni di controlli CNOT multicontrollati che richiedono solo pochi qubits e implementazioni di incrementatori.</span><span class="sxs-lookup"><span data-stu-id="fbe58-143">Among the known use cases of dirty qubits are implementations of multi-controlled CNOT gates that require only very few qubits and implementation of incrementers.</span></span>

<span data-ttu-id="fbe58-144">In Canon sono disponibili esempi che usano la parola chiave `borrowing`, ad esempio la funzione `MultiControlledXBorrow` definita di seguito.</span><span class="sxs-lookup"><span data-stu-id="fbe58-144">In the canon there are examples that use the `borrowing` keyword, for instance the function `MultiControlledXBorrow` defined below.</span></span>
<span data-ttu-id="fbe58-145">Se `controls` indica il qubits di controllo che deve essere aggiunto a un'operazione di `X`, in questa implementazione viene aggiunto un valore complessivo di `Length(controls)-2` molti ancillas Dirty.</span><span class="sxs-lookup"><span data-stu-id="fbe58-145">If `controls` denotes the control qubits that should be added to an `X` operation, then an overall of `Length(controls)-2` many dirty ancillas will be added by this implementation.</span></span>

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

<span data-ttu-id="fbe58-146">Si noti che l'uso estensivo di `With` combinatore---nel formato applicabile per le operazioni che supportano contigut, ad esempio `WithA`---è stato creato in questo esempio, che è uno stile di programmazione valido, come l'aggiunta di un controllo alle strutture che coinvolgono `With` solo la propagazione del controllo all'operazione interna.</span><span class="sxs-lookup"><span data-stu-id="fbe58-146">Note that extensive use of the `With` combinator---in its form that is applicable for operations that support adjoint, i.e., `WithA`---was made in this example which is good programming style as adding control to structures involving `With` only propagates control to the inner operation.</span></span> <span data-ttu-id="fbe58-147">Si noti inoltre che qui, oltre all'`body` dell'operazione è stata fornita in modo esplicito un'implementazione del corpo `controlled` dell'operazione anziché ricorrere a un'istruzione `controlled auto`.</span><span class="sxs-lookup"><span data-stu-id="fbe58-147">Further note that here in addition to the `body` of the operation an implementation of the `controlled` body of the operation was explicitly provided, rather than resorting to a `controlled auto` statement.</span></span> <span data-ttu-id="fbe58-148">Il motivo è che la struttura del circuito illustra come aggiungere facilmente ulteriori controlli, che risulta vantaggioso rispetto all'aggiunta di un controllo a ogni singolo controllo nella `body`.</span><span class="sxs-lookup"><span data-stu-id="fbe58-148">The reason for this is that we know from the structure of the circuit how to easily add further controls which is beneficial compared to adding control to each and every individual gate in the `body`.</span></span> 

<span data-ttu-id="fbe58-149">È istruttivo confrontare questo codice con un'altra funzione Canon `MultiControlledXClean` che raggiunga lo stesso obiettivo dell'implementazione di un'operazione di `X` controllata da Multiply, che usa diversi qubits puliti usando il meccanismo di `using`.</span><span class="sxs-lookup"><span data-stu-id="fbe58-149">It is instructive to compare this code with another canon function `MultiControlledXClean` which achieves the same goal of implementing a multiply-controlled `X` operation, however, which uses several clean qubits using the `using` mechanism.</span></span> 
