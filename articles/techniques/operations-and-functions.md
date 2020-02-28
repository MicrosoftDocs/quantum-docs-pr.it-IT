---
title: 'Operazioni e funzioni Q #'
description: 'Informazioni sulle operazioni e sulle funzioni di Q # e su come vengono applicate in un programma Quantum.'
uid: microsoft.quantum.techniques.opsandfunctions
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 43f0cf2da192a607e514d0c7de57a9bdd067faf7
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907665"
---
# <a name="q-operations-and-functions"></a><span data-ttu-id="d8c60-103">Operazioni e funzioni Q #</span><span class="sxs-lookup"><span data-stu-id="d8c60-103">Q# Operations and Functions</span></span>

<span data-ttu-id="d8c60-104">I programmi Q # sono costituiti da una o più *operazioni* che descrivono gli effetti collaterali delle operazioni Quantum possono avere sui dati quantistici e una o più *funzioni* che consentono modifiche ai dati classici.</span><span class="sxs-lookup"><span data-stu-id="d8c60-104">Q# programs consist of one or more *operations* that describe side effects quantum operations can have on quantum data, and one or more *functions* that allow modifications to classical data.</span></span> <span data-ttu-id="d8c60-105">Diversamente dalle operazioni, le funzioni vengono usate per descrivere il comportamento puramente classico e non hanno effetti oltre al calcolo dei valori di output classici.</span><span class="sxs-lookup"><span data-stu-id="d8c60-105">In contrast to operations, functions are used to describe purely classical behavior and do not have any effects besides computing classical output values.</span></span>

<span data-ttu-id="d8c60-106">Ogni operazione definita in Q # può quindi chiamare un numero qualsiasi di altre operazioni, incluse le operazioni intrinseche predefinite definite dal linguaggio.</span><span class="sxs-lookup"><span data-stu-id="d8c60-106">Each operation defined in Q# may then call any number of other operations, including the built-in intrinsic operations defined by the language.</span></span> <span data-ttu-id="d8c60-107">Il modo specifico in cui vengono definite queste operazioni intrinseche dipende dal computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d8c60-107">The particular way in which these intrinsic operations are defined depends on the target machine.</span></span> <span data-ttu-id="d8c60-108">Quando viene compilata, ogni operazione viene rappresentata come tipo di classe .NET che può essere fornita ai computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d8c60-108">When compiled, each operation is represented as a .NET class type that can be provided to target machines.</span></span>

## <a name="defining-new-operations"></a><span data-ttu-id="d8c60-109">Definizione di nuove operazioni</span><span class="sxs-lookup"><span data-stu-id="d8c60-109">Defining New Operations</span></span>

<span data-ttu-id="d8c60-110">Come descritto in precedenza, il blocco predefinito più elementare di un programma Quantum scritto in Q # è un' *operazione*che può essere chiamata da applicazioni .NET classiche, ad esempio usando un simulatore o altre operazioni all'interno di q #.</span><span class="sxs-lookup"><span data-stu-id="d8c60-110">As described above, the most basic building block of a quantum program written in Q# is an *operation*, which can either be called from classical .NET applications, e.g., using a simulator, or by other operations within Q#.</span></span>
<span data-ttu-id="d8c60-111">Ogni operazione accetta un input, produce un output e specifica l'implementazione per una o più specializzazioni delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="d8c60-111">Each operation takes an input, produces an output, and specifies the implementation for one or more operation specializations.</span></span>
<span data-ttu-id="d8c60-112">Ad esempio, l'operazione seguente definisce solo una specializzazione del corpo predefinita e accetta un solo qubit come input, quindi chiama l'operazione incorporata `X` su tale input:</span><span class="sxs-lookup"><span data-stu-id="d8c60-112">For instance, the following operation defines only a default body specialization and takes a single qubit as its input, then calls the built-in `X` operation on that input:</span></span>

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

<span data-ttu-id="d8c60-113">La parola chiave `operation` inizia la definizione dell'operazione ed è seguita dal nome; `BitFlip`.</span><span class="sxs-lookup"><span data-stu-id="d8c60-113">The keyword `operation` begins the operation definition, and is followed by the name; here, `BitFlip`.</span></span>
<span data-ttu-id="d8c60-114">Successivamente, il tipo di input viene definito come `Qubit`, insieme a un nome `target` per fare riferimento all'input all'interno della nuova operazione.</span><span class="sxs-lookup"><span data-stu-id="d8c60-114">Next, the type of the input is defined as `Qubit`, along with a name `target` for referring to the input within the new operation.</span></span>
<span data-ttu-id="d8c60-115">Analogamente, il `Unit` definisce che l'output dell'operazione è vuoto.</span><span class="sxs-lookup"><span data-stu-id="d8c60-115">Similarly, the `Unit` defines that the operation's output is empty.</span></span>
<span data-ttu-id="d8c60-116">Viene usato in modo analogo a C# `void` in e altri linguaggi imperativi ed è equivalente F# a `unit` in e altri linguaggi funzionali.</span><span class="sxs-lookup"><span data-stu-id="d8c60-116">This is used similarly to `void` in C# and other imperative languages, and is equivalent to `unit` in F# and other functional languages.</span></span>

> [!NOTE]
> <span data-ttu-id="d8c60-117">Questo aspetto verrà esaminato in dettaglio più avanti, ma ogni operazione in Q # accetta esattamente un input e restituisce esattamente un output.</span><span class="sxs-lookup"><span data-stu-id="d8c60-117">We will explore this in more detail below, but each operation in Q# takes exactly one input and returns exactly one output.</span></span>
> <span data-ttu-id="d8c60-118">Più input e output vengono quindi rappresentati utilizzando *Tuple*, che raccolgono più valori in un singolo valore.</span><span class="sxs-lookup"><span data-stu-id="d8c60-118">Multiple inputs and outputs are then represented using *tuples*, which collect multiple values together into a single value.</span></span>
> <span data-ttu-id="d8c60-119">In modo informale, diciamo che Q # è un linguaggio "tuple-in-out".</span><span class="sxs-lookup"><span data-stu-id="d8c60-119">Informally, we say that Q# is a "tuple-in tuple-out" language.</span></span>
> <span data-ttu-id="d8c60-120">Seguendo questo concetto, `()` deve quindi essere letto come tupla "vuota", che ha il tipo `Unit`.</span><span class="sxs-lookup"><span data-stu-id="d8c60-120">Following this concept, `()` should then be read as the "empty" tuple, which has the type `Unit`.</span></span>

<span data-ttu-id="d8c60-121">All'interno della nuova operazione, l'implementazione può essere specificata direttamente nella dichiarazione se è necessario specificare in modo esplicito solo l'implementazione della specializzazione del corpo predefinita.</span><span class="sxs-lookup"><span data-stu-id="d8c60-121">Within the new operation, the implementation can be specified directly within the declaration if only the implementation of the default body specialization needs to be specified explicitly.</span></span> <span data-ttu-id="d8c60-122">Inoltre, è possibile definire le implementazioni di, ad esempio, una o più operazioni di `functor`, come elaborato di seguito.</span><span class="sxs-lookup"><span data-stu-id="d8c60-122">Additionally, it is possible to define the implementations of, for example, one or more `functor` operations, as elaborated below.</span></span> <span data-ttu-id="d8c60-123">Nell'esempio precedente, l'unica istruzione consiste nel chiamare l'operazione Q # incorporata <xref:microsoft.quantum.intrinsic.x>.</span><span class="sxs-lookup"><span data-stu-id="d8c60-123">In the example above, the only statement is to call the built-in Q# operation <xref:microsoft.quantum.intrinsic.x>.</span></span>

<span data-ttu-id="d8c60-124">Le operazioni possono inoltre restituire tipi più interessanti rispetto a `Unit`.</span><span class="sxs-lookup"><span data-stu-id="d8c60-124">Operations can also return more interesting types than `Unit`.</span></span>
<span data-ttu-id="d8c60-125">Ad esempio, l'operazione <xref:microsoft.quantum.intrinsic.m> restituisce un output di tipo `Result`, che rappresenta l'esecuzione di una misurazione.</span><span class="sxs-lookup"><span data-stu-id="d8c60-125">For instance, the <xref:microsoft.quantum.intrinsic.m> operation returns an output of type `Result`, representing having performed a measurement.</span></span> <span data-ttu-id="d8c60-126">È possibile passare l'output di un'operazione a un'altra operazione oppure utilizzarlo con la parola chiave `let` per definire una nuova variabile.</span><span class="sxs-lookup"><span data-stu-id="d8c60-126">We can either pass the output from an operation to another operation, or can use it with the `let` keyword to define a new variable.</span></span>
<!-- Link to UID for superdense conceptual and example documentation. -->
<span data-ttu-id="d8c60-127">Questo consente la rappresentazione di calcoli classici che interagiscono con le operazioni Quantum a un livello basso, ad esempio nella codifica superdensa:</span><span class="sxs-lookup"><span data-stu-id="d8c60-127">This allows for representing classical computation that interacts with quantum operations at a low level, such as in superdense coding:</span></span>

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```
### <a name="functors-adjoint-and-controlled"></a><span data-ttu-id="d8c60-128">Funtori, contigut e controllato</span><span class="sxs-lookup"><span data-stu-id="d8c60-128">Functors, adjoint and controlled</span></span>
<span data-ttu-id="d8c60-129">Se un'operazione implementa una trasformazione unitaria, è possibile definire il modo in cui l'operazione agisce quando *adjointed* o *controllata*.</span><span class="sxs-lookup"><span data-stu-id="d8c60-129">If an operation implements a unitary transformation, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span> <span data-ttu-id="d8c60-130">Una specializzazione contigua di un'operazione specifica il modo in cui agisce quando viene eseguita in ordine inverso, mentre una specializzazione controllata specifica il modo in cui un'operazione viene applicata quando viene applicato condizionato allo stato di un registro quantico.</span><span class="sxs-lookup"><span data-stu-id="d8c60-130">An adjoint specialization of an operation specifies how it acts when run in reverse, while a controlled specialization specifies how an operation acts when applied conditioned on the state of a quantum register.</span></span>
<span data-ttu-id="d8c60-131">L'esistenza di queste specializzazioni può essere dichiarata come parte della firma dell'operazione: `is Adj + Ctl` nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="d8c60-131">The existence of these specializations can be declared as part of the operation signature: `is Adj + Ctl` in the following example.</span></span> <span data-ttu-id="d8c60-132">L'implementazione corrispondente per ogni specializzazione dichiarata in modo implicito viene quindi generata dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="d8c60-132">The corresponding implementation for each such implicitly declared specialization is then generated by the compiler.</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

> [!NOTE]
> <span data-ttu-id="d8c60-133">Molte operazioni in Q # rappresentano i cancelli unitari.</span><span class="sxs-lookup"><span data-stu-id="d8c60-133">Many operations in Q# represent unitary gates.</span></span>
> <span data-ttu-id="d8c60-134">Se $U $ è il controllo unitario rappresentato da un'operazione `U`, `Adjoint U` rappresenta il controllo dell'unità $U ^ \dagger $.</span><span class="sxs-lookup"><span data-stu-id="d8c60-134">If $U$ is the unitary gate represented by an operation `U`, then `Adjoint U` represents the unitary gate $U^\dagger$.</span></span>

<span data-ttu-id="d8c60-135">Nel caso in cui l'implementazione non possa essere generata dal compilatore, può essere specificata in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="d8c60-135">In the case where the implementation cannot be generated by the compiler, it can be explicitly specified.</span></span> <span data-ttu-id="d8c60-136">Tali dichiarazioni di specializzazione esplicita possono essere costituite da una direttiva di generazione adatta o da un'implementazione definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="d8c60-136">Such explicit specialization declarations can consist of a suitable generation directive or a user defined implementation.</span></span> <span data-ttu-id="d8c60-137">Il codice nell'`PrepareEntangledPair` precedente, ad esempio, equivale al codice riportato di seguito contenente dichiarazioni di specializzazione esplicite:</span><span class="sxs-lookup"><span data-stu-id="d8c60-137">The code in `PrepareEntangledPair` above for example is equivalent to the code below containing explicit specialization declarations:</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
<span data-ttu-id="d8c60-138">La parola chiave `auto` indica che il compilatore deve determinare come generare l'implementazione della specializzazione.</span><span class="sxs-lookup"><span data-stu-id="d8c60-138">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>
<span data-ttu-id="d8c60-139">Se il compilatore non è in grado di generare automaticamente l'implementazione per una determinata specializzazione o se è possibile fornire un'implementazione più efficiente, l'implementazione può anche essere definita manualmente.</span><span class="sxs-lookup"><span data-stu-id="d8c60-139">If the compiler cannot generate the implementation for a certain specialization automatically, or if a more efficient implementation can be given, then the implementation may also be manually defined.</span></span>

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
<span data-ttu-id="d8c60-140">Nell'esempio precedente, `adjoint invert;` indica che la specializzazione contigua deve essere generata invertendo l'implementazione del corpo e `controlled adjoint invert;` indica che la specializzazione contigua controllata deve essere generata invertendo l'implementazione specificata della specializzazione controllata.</span><span class="sxs-lookup"><span data-stu-id="d8c60-140">In the example above, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="d8c60-141">In un [flusso di controllo di ordine superiore](xref:microsoft.quantum.concepts.control-flow)si vedranno altri esempi.</span><span class="sxs-lookup"><span data-stu-id="d8c60-141">We will see more examples of this in [Higher-Order Control Flow](xref:microsoft.quantum.concepts.control-flow).</span></span>

<span data-ttu-id="d8c60-142">Per chiamare una specializzazione di un'operazione, usare le parole chiave `Adjoint` o `Controlled`.</span><span class="sxs-lookup"><span data-stu-id="d8c60-142">To call a specialization of an operation, use the `Adjoint` or `Controlled` keywords.</span></span>
<span data-ttu-id="d8c60-143">Ad esempio, l'esempio di codifica di superdense sopra riportato può essere scritto in modo più compatto usando il `PrepareEntangledPair` contiguo per trasformare lo stato inserito di nuovo in una coppia non impigliata di qubits:</span><span class="sxs-lookup"><span data-stu-id="d8c60-143">For example, the superdense coding example above can be written more compactly by using the adjoint of `PrepareEntangledPair` to transform the entangled state back into an unentangled pair of qubits:</span></span>

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

<span data-ttu-id="d8c60-144">Quando si progettano operazioni da usare con funtori, è necessario considerare alcune importanti limitazioni.</span><span class="sxs-lookup"><span data-stu-id="d8c60-144">There are a number of important limitations to consider when designing operations for use with functors.</span></span>
<span data-ttu-id="d8c60-145">In modo più critico, le specializzazioni per un'operazione che usa il valore di output di qualsiasi altra operazione non possono essere generate automaticamente dal compilatore, perché è ambiguo come riordinare le istruzioni in tale operazione per ottenere lo stesso effetto.</span><span class="sxs-lookup"><span data-stu-id="d8c60-145">Most critically, specializations for an operation that uses the output value of any other operation cannot be auto-generated by the compiler, as it is ambiguous how to reorder the statements in such an operation to obtain the same effect.</span></span>


## <a name="defining-new-functions"></a><span data-ttu-id="d8c60-146">Definizione di nuove funzioni</span><span class="sxs-lookup"><span data-stu-id="d8c60-146">Defining New Functions</span></span>

<span data-ttu-id="d8c60-147">Q # consente inoltre di definire *funzioni*, che sono distinte dalle operazioni in quanto non possono avere effetti oltre il calcolo di un valore di output.</span><span class="sxs-lookup"><span data-stu-id="d8c60-147">Q# also allows for defining *functions*, which are distinct from operations in that they are not allowed to have any effects beyond calculating an output value.</span></span>
<span data-ttu-id="d8c60-148">In particolare, le funzioni non possono chiamare operazioni, agire su qubits, numeri casuali di esempio o in altro modo dipendono dallo stato oltre il valore di input per una funzione.</span><span class="sxs-lookup"><span data-stu-id="d8c60-148">In particular, functions cannot call operations, act on qubits, sample random numbers, or otherwise depend on state beyond the input value to a function.</span></span>
<span data-ttu-id="d8c60-149">Di conseguenza, le funzioni Q # sono *pure*, in quanto eseguono sempre il mapping degli stessi valori di input agli stessi valori di output.</span><span class="sxs-lookup"><span data-stu-id="d8c60-149">As a consequence, Q# functions are *pure*, in that they always map the same input values to the same output values.</span></span>
<span data-ttu-id="d8c60-150">Ciò consente al compilatore Q # di riordinare in modo sicuro come e quando le funzioni vengono chiamate quando si generano specializzazioni delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="d8c60-150">This allows the Q# compiler to safely reorder how and when functions are called when generating operation specializations.</span></span>

<span data-ttu-id="d8c60-151">La definizione di una funzione funziona in modo analogo alla definizione di un'operazione, ad eccezione del fatto che non è possibile definire alcuna specializzazioni contigua o controllata per una funzione.</span><span class="sxs-lookup"><span data-stu-id="d8c60-151">Defining a function works similarly to defining an operation, except that no adjoint or controlled specializations can be defined for a function.</span></span>
<span data-ttu-id="d8c60-152">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d8c60-152">For instance:</span></span>

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```
<span data-ttu-id="d8c60-153">Quando è possibile eseguire questa operazione, è utile scrivere la logica classica in termini di funzioni anziché di operazioni, in modo che possa essere usata più facilmente all'interno di operazioni.</span><span class="sxs-lookup"><span data-stu-id="d8c60-153">Whenever it is possible to do so, it is helpful to write out classical logic in terms of functions rather than operations, so that it can be more readily used from within operations.</span></span>
<span data-ttu-id="d8c60-154">Se, ad esempio, è stato scritto `Square` come operazione, il compilatore non sarebbe stato in grado di garantire che la chiamata con lo stesso input produrrebbe sempre gli stessi output.</span><span class="sxs-lookup"><span data-stu-id="d8c60-154">If we had written `Square` as an operation, for example, then the compiler would not have been able to guarantee that calling it with the same input would consistently produce the same outputs.</span></span>

<span data-ttu-id="d8c60-155">Per sottolineare la differenza tra funzioni e operazioni, prendere in considerazione il problema di campionamento classico di un numero casuale da un'operazione Q #:</span><span class="sxs-lookup"><span data-stu-id="d8c60-155">To underscore the difference between functions and operations, consider the problem of classically sampling a random number from within a Q# operation:</span></span>

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

<span data-ttu-id="d8c60-156">Ogni volta che viene chiamato `U`, avrà un'azione diversa su `target`.</span><span class="sxs-lookup"><span data-stu-id="d8c60-156">Each time that `U` is called, it will have a different action on `target`.</span></span>
<span data-ttu-id="d8c60-157">In particolare, il compilatore non può garantire che se è stato aggiunto un `adjoint auto` dichiarazione di specializzazione per `U`, `U(target); Adjoint U(target);` funge da identità, ovvero come no-op.</span><span class="sxs-lookup"><span data-stu-id="d8c60-157">In particular, the compiler cannot guarantee that if we added an `adjoint auto` specialization declaration to `U`, then `U(target); Adjoint U(target);` acts as identity (that is, as a no-op).</span></span>
<span data-ttu-id="d8c60-158">In questo modo si viola la definizione del contiguo che abbiamo visto in [vettori e matrici](xref:microsoft.quantum.concepts.vectors), in modo da consentire a di generare automaticamente una specializzazione contigua in un'operazione in cui è stata chiamata l'operazione <xref:microsoft.quantum.math.randomreal> comporterebbe la violazione delle garanzie fornite dal compilatore. <xref:microsoft.quantum.math.randomreal> è un'operazione per la quale non esiste alcuna versione contigua o controllata.</span><span class="sxs-lookup"><span data-stu-id="d8c60-158">This violates the definition of the adjoint that we saw in [Vectors and Matrices](xref:microsoft.quantum.concepts.vectors), such that allowing to auto-generate an adjoint specialization in an operation where we have called the operation <xref:microsoft.quantum.math.randomreal> would break the guarantees provided by the compiler; <xref:microsoft.quantum.math.randomreal> is an operation for which no adjoint or controlled version exists.</span></span>

<span data-ttu-id="d8c60-159">D'altra parte, consentire le chiamate di funzione, ad esempio `Square` è sicuro, in quanto è possibile garantire che il compilatore debba solo mantenere l'input per `Square` per mantenere stabile l'output.</span><span class="sxs-lookup"><span data-stu-id="d8c60-159">On the other hand, allowing function calls such as `Square` is safe, in that the compiler can be assured that it only needs to preserve the input to `Square` in order to keep its output stable.</span></span>
<span data-ttu-id="d8c60-160">In questo modo, l'isolamento della logica classica più possibile in funzioni semplifica il riutilizzo di tale logica in altre funzioni e operazioni.</span><span class="sxs-lookup"><span data-stu-id="d8c60-160">Thus, isolating as much classical logic as possible into functions makes it easy to reuse that logic in other functions and operations alike.</span></span>

## <a name="control-flow"></a><span data-ttu-id="d8c60-161">Flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="d8c60-161">Control Flow</span></span>

<span data-ttu-id="d8c60-162">All'interno di un'operazione o di una funzione, ogni istruzione viene eseguita in ordine, in modo analogo ai linguaggi classici imperativi più comuni.</span><span class="sxs-lookup"><span data-stu-id="d8c60-162">Within an operation or function, each statement executes in order, similar to most common imperative classical languages.</span></span>
<span data-ttu-id="d8c60-163">Questo flusso di controllo può tuttavia essere modificato in tre modi distinti:</span><span class="sxs-lookup"><span data-stu-id="d8c60-163">This flow of control can be modified, however, in three distinct ways:</span></span>

- <span data-ttu-id="d8c60-164">Istruzioni `if`</span><span class="sxs-lookup"><span data-stu-id="d8c60-164">`if` Statements</span></span>
- <span data-ttu-id="d8c60-165">Cicli di `for`</span><span class="sxs-lookup"><span data-stu-id="d8c60-165">`for` Loops</span></span>
- <span data-ttu-id="d8c60-166">`repeat`-cicli `until`</span><span class="sxs-lookup"><span data-stu-id="d8c60-166">`repeat`-`until` Loops</span></span>

<span data-ttu-id="d8c60-167">Si rinvia la discussione di quest'ultima fino a quando non si discute la [ripetizione fino al completamento dei circuiti (UR)](xref:microsoft.quantum.techniques.qubits#measurements) .</span><span class="sxs-lookup"><span data-stu-id="d8c60-167">We defer discussion of the latter until we discuss [Repeat Until Success (RUS)](xref:microsoft.quantum.techniques.qubits#measurements) circuits.</span></span>
<span data-ttu-id="d8c60-168">I costrutti del flusso di controllo `if` e `for`, tuttavia, procedono in un senso familiare alla maggior parte dei linguaggi di programmazione classici.</span><span class="sxs-lookup"><span data-stu-id="d8c60-168">The `if` and `for` control flow constructs, however, proceed in a familiar sense to most classical programming languages.</span></span>
<span data-ttu-id="d8c60-169">In particolare, un'istruzione `if` può assumere una condizione, può essere seguita da una o più istruzioni `elif` e può terminare con un `else`:</span><span class="sxs-lookup"><span data-stu-id="d8c60-169">In particular, an `if` statement can take a condition, may be followed by one or more `elif` statements, and may end with an `else`:</span></span>

```qsharp
if (pauli == PauliX) {
    X(qubit);
} elif (pauli == PauliY) {
    Y(qubit);
} elif (pauli == PauliZ) {
    Z(qubit);
} else {
    fail "Cannot use PauliI here.";
}
```

<span data-ttu-id="d8c60-170">Analogamente, i cicli di `for` indicano l'iterazione su un intervallo di numeri interi o sugli elementi di una matrice:</span><span class="sxs-lookup"><span data-stu-id="d8c60-170">Similarly, `for` loops indicate iteration over a range of integers or over the elements of an array:</span></span>

```qsharp
for (idxQubit in 0..nQubits - 1) {
    // Do something to idxQubit...
}
```

<span data-ttu-id="d8c60-171">In particolare, è possibile usare i cicli di `for` e le istruzioni `if` anche nelle operazioni per le quali le specializzazioni vengono generate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d8c60-171">Importantly, `for` loops and `if` statements can even be used in operations for which specializations are auto-generated.</span></span> <span data-ttu-id="d8c60-172">In tal caso, il contiguo di un ciclo di `for` inverte la direzione e accetta il contiguo di ogni iterazione.</span><span class="sxs-lookup"><span data-stu-id="d8c60-172">In that case the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="d8c60-173">Segue il principio "Shoes-and-Socks": se si vuole annullare la messa a punto dei calzini e quindi delle scarpe, è necessario annullare le calzature e quindi annullare l'inserimento dei calzini.</span><span class="sxs-lookup"><span data-stu-id="d8c60-173">This follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span>
<span data-ttu-id="d8c60-174">Si tratta di un approccio decisamente meno efficace per provare a riportare i calzini quando si indossano ancora le scarpe.</span><span class="sxs-lookup"><span data-stu-id="d8c60-174">It works decidedly less well to try and take your socks off while you're still wearing your shoes!</span></span>

## <a name="operations-and-functions-as-first-class-values"></a><span data-ttu-id="d8c60-175">Operazioni e funzioni come valori di prima classe</span><span class="sxs-lookup"><span data-stu-id="d8c60-175">Operations and Functions as First-Class Values</span></span>

<span data-ttu-id="d8c60-176">Una tecnica critica per ragionare sul flusso di controllo e la logica classica con funzioni anziché operazioni consiste nell'usare le operazioni e le funzioni in Q # sono di *prima classe*.</span><span class="sxs-lookup"><span data-stu-id="d8c60-176">One critical technique for reasoning about control flow and classical logic using functions rather than operations is to utilize that operations and functions in Q# are *first-class*.</span></span>
<span data-ttu-id="d8c60-177">Ovvero ciascuno dei quali è il linguaggio di propria scelta.</span><span class="sxs-lookup"><span data-stu-id="d8c60-177">That is, they are each values in the language in their own right.</span></span>
<span data-ttu-id="d8c60-178">Ad esempio, di seguito è riportato un codice Q # perfettamente valido, se poco indiretto:</span><span class="sxs-lookup"><span data-stu-id="d8c60-178">For instance, the following is perfectly valid Q# code, if a little indirect:</span></span>

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

<span data-ttu-id="d8c60-179">Il valore della variabile `ourH` nel frammento di codice precedente è quindi l'operazione <xref:microsoft.quantum.intrinsic.h>, in modo che sia possibile chiamare tale valore come qualsiasi altra operazione.</span><span class="sxs-lookup"><span data-stu-id="d8c60-179">The value of the variable `ourH` in the snippet above is then the operation <xref:microsoft.quantum.intrinsic.h>, such that we can call that value like any other operation.</span></span>
<span data-ttu-id="d8c60-180">In questo modo è possibile scrivere operazioni che accettano operazioni come parte dell'input, formando concetti di flusso di controllo di ordine superiore.</span><span class="sxs-lookup"><span data-stu-id="d8c60-180">This allows us to write operations that take operations as a part of their input, forming higher-order control flow concepts.</span></span>
<span data-ttu-id="d8c60-181">Si supponga, ad esempio, di voler "quadrare" un'operazione applicando due volte lo stesso qubit di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d8c60-181">For instance, we could imagine wanting to "square" an operation by applying it twice to the same target qubit.</span></span>

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

<span data-ttu-id="d8c60-182">In questo esempio, la freccia `=>` visualizzata nel tipo `(Qubit => Unit)` indica che il campo di input `op` è un'operazione che accetta come input il tipo `Qubit` e produce una tupla vuota come output.</span><span class="sxs-lookup"><span data-stu-id="d8c60-182">In this example, the `=>` arrow that appears in the type `(Qubit => Unit)` denotes that the input field `op` is an operation which takes as its input the type `Qubit` and produces an empty tuple as its output.</span></span>
<span data-ttu-id="d8c60-183">Vengono inoltre specificate le caratteristiche del tipo di operazione, che contengono le informazioni su quali funtori sono supportate.</span><span class="sxs-lookup"><span data-stu-id="d8c60-183">Additionally we specify the characteristics of that operation type, which contain the information about which functors are supported.</span></span>
<span data-ttu-id="d8c60-184">Un'operazione di tipo `(Qubit => Unit)` non supporta né il `Adjoint` né il functore `Controlled`.</span><span class="sxs-lookup"><span data-stu-id="d8c60-184">An operation of type `(Qubit => Unit)` supports neither the `Adjoint` nor the `Controlled` functor.</span></span> <span data-ttu-id="d8c60-185">Se si vuole indicare che un'operazione di tale tipo deve supportare, ad esempio, il `Adjoint` functor, è necessario dichiararlo come adjointable.</span><span class="sxs-lookup"><span data-stu-id="d8c60-185">If we want to indicate that an operation of that type has to support e.g. the `Adjoint` functor, we have to declare it as being adjointable.</span></span> <span data-ttu-id="d8c60-186">Questa operazione viene eseguita utilizzando l'annotazione `is Adj` al tipo.</span><span class="sxs-lookup"><span data-stu-id="d8c60-186">This is done by using the annotation `is Adj` to the type.</span></span> <span data-ttu-id="d8c60-187">Analogamente, `(Qubit => Unit is Ctl)` indica che un'operazione di tale tipo supporta il functor `Controlled`.</span><span class="sxs-lookup"><span data-stu-id="d8c60-187">Similarly, `(Qubit => Unit is Ctl)` denotes that an operation of that type supports the `Controlled` functor.</span></span> <span data-ttu-id="d8c60-188">Questa operazione verrà ulteriormente esaminata quando si discutono i [tipi in Q #](xref:microsoft.quantum.language.type-model) più in generale.</span><span class="sxs-lookup"><span data-stu-id="d8c60-188">We will explore this further when we discuss [types in Q#](xref:microsoft.quantum.language.type-model) more generally.</span></span>

<span data-ttu-id="d8c60-189">Per il momento, viene evidenziato che è anche possibile restituire le operazioni come parte degli output, in modo da poter isolare alcuni tipi di logica condizionale classica come una funzione classica che restituisce una descrizione di un programma Quantum sotto forma di operazione.</span><span class="sxs-lookup"><span data-stu-id="d8c60-189">For now, we emphasize that we can also return operations as a part of outputs, such that we can isolate some kinds of classical conditional logic as a classical function which returns a description of a quantum program in the form of an operation.</span></span>
<span data-ttu-id="d8c60-190">Come esempio semplice, si consideri l'esempio di Teleporting, in cui la parte che riceve un messaggio classico a due bit deve usare il messaggio per decodificare i qubit nello stato di teleporte appropriato.</span><span class="sxs-lookup"><span data-stu-id="d8c60-190">As a simple example, consider the teleportation example, in which the party receiving a two-bit classical message needs to use the message to decode their qubit into the proper teleported state.</span></span>
<span data-ttu-id="d8c60-191">È possibile scrivere questo risultato in termini di funzione che accetta i due bit classici e restituisce l'operazione di decodifica corretta.</span><span class="sxs-lookup"><span data-stu-id="d8c60-191">We could write this in terms of a function that takes those two classical bits and returns the proper decoding operation.</span></span>

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

<span data-ttu-id="d8c60-192">Questa nuova funzione è effettivamente una funzione, in quanto se viene chiamata con gli stessi valori di `hereBit` e `thereBit`, verrà sempre restituita la stessa operazione.</span><span class="sxs-lookup"><span data-stu-id="d8c60-192">This new function is indeed a function, in that if we call it with the same values of `hereBit` and `thereBit`, we will always get back the same operation.</span></span>
<span data-ttu-id="d8c60-193">Pertanto, il decodificatore può essere eseguito in modo sicuro all'interno di operazioni senza dover ragionare sul modo in cui la logica di decodifica interagisce con le definizioni delle diverse specializzazioni delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="d8c60-193">Thus, the decoder can be safely run inside operations without having to reason about how the decoding logic interacts with the definitions of the different operation specializations.</span></span>
<span data-ttu-id="d8c60-194">Ovvero è stata isolata la logica classica all'interno di una funzione, garantendo al compilatore che la chiamata di funzione possa essere riordinata con impuneità purché l'input venga mantenuto.</span><span class="sxs-lookup"><span data-stu-id="d8c60-194">That is, we have isolated the classical logic inside a function, guaranteeing to the compiler that the function call can be reordered with impunity so long as the input is preserved.</span></span>

<span data-ttu-id="d8c60-195">È anche possibile considerare le funzioni come valori di prima classe, come si vedrà in modo più dettagliato quando si discutono [le operazioni e i tipi di funzione](#operations-and-functions-as-first-class-values).</span><span class="sxs-lookup"><span data-stu-id="d8c60-195">We can also treat functions as first-class values, as we will see in more detail when we discuss [operations and function types](#operations-and-functions-as-first-class-values).</span></span>

## <a name="partially-applying-operations-and-functions"></a><span data-ttu-id="d8c60-196">Applicazione parziale di operazioni e funzioni</span><span class="sxs-lookup"><span data-stu-id="d8c60-196">Partially Applying Operations and Functions</span></span>

<span data-ttu-id="d8c60-197">È possibile eseguire molte altre operazioni con funzioni che restituiscono operazioni usando un' *applicazione parziale*, in cui è possibile fornire una o più parti dell'input a una funzione o a un'operazione senza chiamarla effettivamente.</span><span class="sxs-lookup"><span data-stu-id="d8c60-197">We can do significantly more with functions that return operations by using *partial application*, in which we can provide one or more parts of the input to a function or operation without actually calling it.</span></span> <span data-ttu-id="d8c60-198">Ad esempio, richiamando il `ApplyTwice` esempio precedente, è possibile indicare che non si vuole specificare, immediatamente, a quale qubit deve essere applicata l'operazione di input:</span><span class="sxs-lookup"><span data-stu-id="d8c60-198">For example, recalling the `ApplyTwice` example above, we can indicate that we don't want to specify, right away, to which qubit the input operation should apply:</span></span>

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

<span data-ttu-id="d8c60-199">In questo caso, la variabile locale `twiceOp` contiene l'operazione parzialmente applicata `ApplyTwice(op, _)`, in cui le parti dell'input che non sono state ancora specificate sono indicate da `_`.</span><span class="sxs-lookup"><span data-stu-id="d8c60-199">In this case, the local variable `twiceOp` holds the partially applied operation `ApplyTwice(op, _)`, where parts of the input that have not yet been specified are indicated by `_`.</span></span>
<span data-ttu-id="d8c60-200">Quando si chiama effettivamente `twiceOp` nella riga successiva, viene passato come input all'operazione parzialmente applicata tutte le parti rimanenti dell'input per l'operazione originale.</span><span class="sxs-lookup"><span data-stu-id="d8c60-200">When we actually call `twiceOp` in the next line, we pass as input to the partially applied operation all of the remaining parts of the input to the original operation.</span></span>
<span data-ttu-id="d8c60-201">Di conseguenza, il frammento di codice precedente è effettivamente identico a avere chiamato `ApplyTwice(op, target)` direttamente, salvo per il fatto che è stata introdotta una nuova variabile locale che ci permette di ritardare la chiamata, fornendo alcune parti dell'input.</span><span class="sxs-lookup"><span data-stu-id="d8c60-201">Thus, the above snippet is effectively identical to having called `ApplyTwice(op, target)` directly, save for that we have introduced a new local variable that allows us to delay the call while providing some parts of the input.</span></span>

<span data-ttu-id="d8c60-202">Poiché un'operazione che è stata applicata parzialmente non viene effettivamente chiamata fino a quando non è stato fornito l'intero input, è possibile applicare parzialmente in modo sicuro le operazioni anche dalle funzioni.</span><span class="sxs-lookup"><span data-stu-id="d8c60-202">Since an operation that has been partially applied is not actually called until its entire input has been provided, we can safely partially apply operations even from within functions.</span></span>

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

<span data-ttu-id="d8c60-203">In linea di base, la logica classica all'interno di `SquareOperation` potrebbe essere stata molto più complessa, ma è ancora isolata dal resto di un'operazione garantita dal fatto che il compilatore possa offrire informazioni sulle funzioni.</span><span class="sxs-lookup"><span data-stu-id="d8c60-203">In principle, the classical logic within `SquareOperation` could have been much more involved, but it is still isolated from the rest of an operation by the guarantees that the compiler can offer about functions.</span></span>
<span data-ttu-id="d8c60-204">Questo approccio verrà usato in tutta la libreria standard Q # per esprimere il flusso di controllo classico in modo da poter essere usato facilmente nei programmi Quantum.</span><span class="sxs-lookup"><span data-stu-id="d8c60-204">This approach will be used throughout the Q# standard library for expressing classical control flow in a way that can be readily used within quantum programs.</span></span>
