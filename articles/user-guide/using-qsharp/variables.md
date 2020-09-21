---
title: Variabili in Q#
description: Informazioni su come usare variabili diverse in Q#
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.variables
no-loc:
- Q#
- $$v
ms.openlocfilehash: bb87f36d3c9b7df195f64e85151e833d494ea945
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835877"
---
# <a name="variables-in-no-locq"></a><span data-ttu-id="4f531-103">Variabili in Q#</span><span class="sxs-lookup"><span data-stu-id="4f531-103">Variables in Q#</span></span>

<span data-ttu-id="4f531-104">Q# consente di distinguere tra simboli modificabili e non modificabili oppure *variabili*, associate/assegnate a espressioni.</span><span class="sxs-lookup"><span data-stu-id="4f531-104">Q# distinguishes between mutable and immutable symbols, or *variables*, which are bound/assigned to expressions.</span></span>
<span data-ttu-id="4f531-105">In generale, l'uso di simboli non modificabili è consigliato perché consente al compilatore di eseguire altre ottimizzazioni.</span><span class="sxs-lookup"><span data-stu-id="4f531-105">In general, the use of immutable symbols is encouraged because it allows the compiler to perform more optimizations.</span></span>

<span data-ttu-id="4f531-106">Il lato sinistro di un'associazione è costituito da una tupla di simboli e dal lato destro di un'espressione.</span><span class="sxs-lookup"><span data-stu-id="4f531-106">The left-hand-side of a binding consists of a symbol tuple and the right-hand side of an expression.</span></span>

## <a name="immutable-variables"></a><span data-ttu-id="4f531-107">Variabili non modificabili</span><span class="sxs-lookup"><span data-stu-id="4f531-107">Immutable Variables</span></span>

<span data-ttu-id="4f531-108">È possibile assegnare un valore di qualsiasi tipo in Q# a una variabile per riutilizzarlo all'interno di un'operazione o funzione tramite la `let` parola chiave.</span><span class="sxs-lookup"><span data-stu-id="4f531-108">You can assign a value of any type in Q# to a variable for reuse within an operation or function by using the `let` keyword.</span></span> 

<span data-ttu-id="4f531-109">Un'associazione non modificabile è costituita dalla parola chiave `let` , seguita da un simbolo o da una tupla di simboli, un segno di uguale `=` , un'espressione a cui associare i simboli e un punto e virgola di terminazione.</span><span class="sxs-lookup"><span data-stu-id="4f531-109">An immutable binding consists of the keyword `let`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>

<span data-ttu-id="4f531-110">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4f531-110">For instance:</span></span>

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

<span data-ttu-id="4f531-111">Questa operazione assegna una matrice specifica di operatori Pauli al nome della variabile (o "symbol"), `measurementOperator` .</span><span class="sxs-lookup"><span data-stu-id="4f531-111">This assigns a particular array of Pauli operators to the variable name (or "symbol"), `measurementOperator`.</span></span>

> [!NOTE]
> <span data-ttu-id="4f531-112">Nell'esempio precedente non è necessario specificare in modo esplicito il tipo della nuova variabile, poiché l'espressione sul lato destro dell' `let` istruzione non è ambigua e il compilatore deduce il tipo corretto.</span><span class="sxs-lookup"><span data-stu-id="4f531-112">In the previous example, there is no need to explicitly specify the type of the new variable, as the expression on the right-hand side of the `let` statement is unambiguous, and the compiler infers the correct type.</span></span> 

<span data-ttu-id="4f531-113">Le variabili definite usando non `let` sono *modificabili*, ovvero una volta definita, non è più possibile modificarla in alcun modo.</span><span class="sxs-lookup"><span data-stu-id="4f531-113">Variables defined using `let` are *immutable*, meaning that once you define it, you can no longer change it in any way.</span></span>
<span data-ttu-id="4f531-114">Questo consente diverse ottimizzazioni utili, inclusa l'ottimizzazione della logica classica che agisce sulle variabili da riordinare per l'applicazione della `Adjoint` variante di un'operazione.</span><span class="sxs-lookup"><span data-stu-id="4f531-114">This allows for several beneficial optimizations, including optimization of the classical logic that acts on variables to be reordered for applying the `Adjoint` variant of an operation.</span></span>

## <a name="mutable-variables"></a><span data-ttu-id="4f531-115">Variabili modificabili</span><span class="sxs-lookup"><span data-stu-id="4f531-115">Mutable Variables</span></span>

<span data-ttu-id="4f531-116">In alternativa alla creazione di una variabile con `let` , la `mutable` parola chiave crea una variabile modificabile che *può* essere riassociata dopo che è stata creata inizialmente con la `set` parola chiave.</span><span class="sxs-lookup"><span data-stu-id="4f531-116">As an alternative to creating a variable with `let`, the `mutable` keyword creates a mutable variable that *can* be rebound after it is initially created by using the `set` keyword.</span></span>

<span data-ttu-id="4f531-117">È possibile riassociare i simboli dichiarati e associati come parte di un' `mutable` istruzione a un valore diverso in un secondo momento nel codice.</span><span class="sxs-lookup"><span data-stu-id="4f531-117">You can rebind symbols declared and bound as part of a `mutable` statement to a different value later in the code.</span></span> <span data-ttu-id="4f531-118">Se un simbolo viene riassociato in un secondo momento nel codice, il relativo tipo non viene modificato e il nuovo valore associato deve essere compatibile con tale tipo.</span><span class="sxs-lookup"><span data-stu-id="4f531-118">If a symbol is rebound later in the code, its type does not change, and the newly bound value must be compatible with that type.</span></span>

### <a name="rebinding-of-mutable-symbols"></a><span data-ttu-id="4f531-119">Riassociazione di simboli modificabili</span><span class="sxs-lookup"><span data-stu-id="4f531-119">Rebinding of Mutable Symbols</span></span>

<span data-ttu-id="4f531-120">È possibile riassociare una variabile modificabile usando un' `set` istruzione.</span><span class="sxs-lookup"><span data-stu-id="4f531-120">You can rebind a mutable variable using a `set` statement.</span></span>
<span data-ttu-id="4f531-121">Tale riassociazione è costituita dalla parola chiave `set` , seguita da un simbolo o da una tupla di simboli, un segno di uguale `=` , un'espressione per riassociare i simboli a e un punto e virgola di terminazione.</span><span class="sxs-lookup"><span data-stu-id="4f531-121">Such a rebinding consists of the keyword `set`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to rebind the symbol(s) to, and a terminating semicolon.</span></span>

<span data-ttu-id="4f531-122">Di seguito sono riportati alcuni esempi di tecniche di riassociazione delle istruzioni.</span><span class="sxs-lookup"><span data-stu-id="4f531-122">The following are some examples of rebinding statement techniques.</span></span>

#### <a name="apply-and-reassign-statements"></a><span data-ttu-id="4f531-123">Istruzioni Apply-and-reassign</span><span class="sxs-lookup"><span data-stu-id="4f531-123">Apply-and-Reassign Statements</span></span>

<span data-ttu-id="4f531-124">Un particolare tipo di `set` istruzione, l'istruzione *Apply-and-reassign* , fornisce un modo pratico per la concatenazione se il lato destro è costituito dall'applicazione di un operatore binario e il risultato deve essere riassociato all'argomento a sinistra per l'operatore.</span><span class="sxs-lookup"><span data-stu-id="4f531-124">A particular kind of `set`-statement, the *apply-and-reassign* statement, provides a convenient way of concatenation if the right-hand side consists of the application of a binary operator, and the result is to be rebound to the left argument to the operator.</span></span> <span data-ttu-id="4f531-125">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="4f531-125">For example,</span></span>

```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
<span data-ttu-id="4f531-126">incrementa il valore del contatore `counter` in ogni iterazione del `for` ciclo.</span><span class="sxs-lookup"><span data-stu-id="4f531-126">increments the value of the counter `counter` in each iteration of the `for` loop.</span></span> <span data-ttu-id="4f531-127">Il codice precedente è equivalente a</span><span class="sxs-lookup"><span data-stu-id="4f531-127">The previous code is equivalent to</span></span> 

```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```

<span data-ttu-id="4f531-128">Sono disponibili istruzioni simili per tutti gli operatori binari in cui il tipo della parte sinistra corrisponde al tipo di espressione.</span><span class="sxs-lookup"><span data-stu-id="4f531-128">Similar statements are available for all binary operators in which the type of the left-hand side matches the expression type.</span></span> <span data-ttu-id="4f531-129">Queste istruzioni costituiscono un modo pratico per accumulare i valori.</span><span class="sxs-lookup"><span data-stu-id="4f531-129">These statements provide a convenient way to accumulate values.</span></span>

<span data-ttu-id="4f531-130">Si supponga, ad esempio, che `qubits` sia un registro di qubits:</span><span class="sxs-lookup"><span data-stu-id="4f531-130">For example, supposing `qubits` is a register of qubits:</span></span>
```qsharp
mutable results = new Result[0];   // results is an empty array of type Result[]
for (q in qubits) {
    set results += [M(q)];         // concatenate the outcome from measuring q to the existing array
    // ...
}
...                                // results contains the measurement outcomes from the whole register
```

#### <a name="update-and-reassign-statements"></a><span data-ttu-id="4f531-131">Istruzioni Update e reassign</span><span class="sxs-lookup"><span data-stu-id="4f531-131">Update-and-Reassign Statements</span></span>

<span data-ttu-id="4f531-132">Esiste una concatenazione simile per le [espressioni di copia e aggiornamento](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) sul lato destro.</span><span class="sxs-lookup"><span data-stu-id="4f531-132">A similar concatenation exists for [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) on the right-hand side.</span></span>
<span data-ttu-id="4f531-133">Per *gli elementi denominati* nei tipi definiti dall'utente e per *gli elementi della matrice*sono disponibili *le istruzioni Update e reassign* corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="4f531-133">Correspondingly, *update-and-reassign* statements exist for *named items* in user-defined types as well as for *array items*.</span></span>  

```qsharp
newtype Complex = (Re : Double, Im : Double);

function ComplexSum(reals : Double[], ims : Double[]) : Complex[] {
    mutable res = Complex(0.,0.);

    for (r in reals) {
        set res w/= Re <- res::Re + r; // update-and-reassign statement
    }
    for (i in ims) {
        set res w/= Im <- res::Im + i; // update-and-reassign statement
    }
    return res;
}
```

<span data-ttu-id="4f531-134">Nel caso di matrici, [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) nella Q# libreria standard sono disponibili gli strumenti necessari per molte esigenze comuni di inizializzazione e manipolazione degli array e, di conseguenza, evita di dover aggiornare gli elementi della matrice in primo luogo.</span><span class="sxs-lookup"><span data-stu-id="4f531-134">In the case of arrays, [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) in the Q# standard library provides the necessary tools for many common array initialization and manipulation needs, and thus helps avoid having to update array items in the first place.</span></span> 

<span data-ttu-id="4f531-135">Le istruzioni Update-and-reassign forniscono un'alternativa se necessario:</span><span class="sxs-lookup"><span data-stu-id="4f531-135">Update-and-reassign statements provide an alternative if needed:</span></span>

```qsharp
operation GenerateRandomInts(max : Int, nSamples : Int) : Int[] {
    mutable samples = new Double[0];
    for (i in 1 .. nSamples) {
        set samples += [RandomInt(max)];
    }
    return samples;
}

operation SampleUniformDistrbution(nSamples : Int, nSteps : Int) : Double[] {
    let normalization = 1. / IntAsDouble(nSteps);
    mutable samples = GenerateRandomInts(nSteps, nSamples);
    
    for (i in IndexRange(samples) {
        let value = IntAsDouble(samples[i]);
        set samples w/= i <- normalization * value; // update-and-reassign statement
    }
}

```

<span data-ttu-id="4f531-136">Utilizzando gli strumenti di libreria per le matrici disponibili in [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) , è possibile, ad esempio, definire facilmente una funzione che restituisce una matrice di `Pauli` tipi in cui l'elemento in corrispondenza dell'indice `i` accetta un `Pauli` valore specificato e tutte le altre voci sono l'identità ( `PauliI` ).</span><span class="sxs-lookup"><span data-stu-id="4f531-136">Using the library tools for arrays provided in [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays), you can, for example, easily define a function that returns an array of `Pauli` types where the element at index `i` takes a given `Pauli` value, and all other entries are the identity (`PauliI`).</span></span>

<span data-ttu-id="4f531-137">Di seguito sono riportate due definizioni di una funzione di questo tipo, il secondo sfruttando gli strumenti a disposizione.</span><span class="sxs-lookup"><span data-stu-id="4f531-137">Here are two definitions of such a function, with the second taking advantage of the tools at our disposal.</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];             // initialize pauliArray of given length
    for (index in 0 .. length - 1) {                    // iterate over the integers in the length range
        set pauliArray w/= index <-                     // change the value at index to input pauli or PauliI
            index == location ? pauli | PauliI;         // cond. expression evaluating to pauli if index==location and PauliI if not
    }    
    return pauliArray;
}
```

<span data-ttu-id="4f531-138">Anziché scorrere ogni indice nella matrice e impostarlo in modo condizionale su `PauliI` o sul dato `pauli` , è invece possibile utilizzare `ConstantArray` da [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) per creare una matrice di `PauliI` tipi e quindi restituire semplicemente un'espressione di copia e aggiornamento in cui è stato modificato il valore specifico in corrispondenza dell'indice `location` :</span><span class="sxs-lookup"><span data-stu-id="4f531-138">Instead of iterating over each index in the array, and conditionally setting it to `PauliI` or the given `pauli`, you can instead use `ConstantArray` from [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) to create an array of `PauliI` types, and then simply return a copy-and-update expression in which you've changed the specific value at index `location`:</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

## <a name="tuple-deconstruction"></a><span data-ttu-id="4f531-139">Decostruzione di Tuple</span><span class="sxs-lookup"><span data-stu-id="4f531-139">Tuple Deconstruction</span></span>

<span data-ttu-id="4f531-140">Oltre ad assegnare una singola variabile, è possibile usare le `let` `mutable` parole chiave e o qualsiasi altro costrutto di associazione, ad esempio `set` -per decomprimere il contenuto di un [tipo di tupla](xref:microsoft.quantum.guide.types#tuple-types).</span><span class="sxs-lookup"><span data-stu-id="4f531-140">In addition to assigning a single variable, you can use the `let` and `mutable` keywords - or any other binding construct, such as `set` - to unpack the contents of a [tuple type](xref:microsoft.quantum.guide.types#tuple-types).</span></span>
<span data-ttu-id="4f531-141">Un'assegnazione di questo form è detta *decostruzione* degli elementi di tale tupla.</span><span class="sxs-lookup"><span data-stu-id="4f531-141">An assignment of this form is said to *deconstruct* the elements of that tuple.</span></span>

<span data-ttu-id="4f531-142">Se il lato destro dell'associazione è una tupla, è possibile decostruire tale tupla al momento dell'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="4f531-142">If the right-hand side of the binding is a tuple, then you can deconstruct that tuple upon assignment.</span></span>
<span data-ttu-id="4f531-143">Tali decostruzioni possono coinvolgere Tuple nidificate e qualsiasi decostruzione completa o parziale è valida purché la forma della tupla sul lato destro sia compatibile con la forma della tupla di simboli.</span><span class="sxs-lookup"><span data-stu-id="4f531-143">Such deconstructions can involve nested tuples, and any full or partial deconstruction is valid as long as the shape of the tuple on the right-hand side is compatible with the shape of the symbol tuple.</span></span>

<span data-ttu-id="4f531-144">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4f531-144">For example:</span></span>

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

## <a name="binding-scopes"></a><span data-ttu-id="4f531-145">Ambiti di associazione</span><span class="sxs-lookup"><span data-stu-id="4f531-145">Binding Scopes</span></span>

<span data-ttu-id="4f531-146">In generale, le associazioni di simboli non rientrano nell'ambito e diventano inattive alla fine del blocco di istruzioni in cui si verificano.</span><span class="sxs-lookup"><span data-stu-id="4f531-146">In general, symbol bindings go out of scope and become inoperative at the end of the statement block they occur in.</span></span>
<span data-ttu-id="4f531-147">Sono previste due eccezioni a questa regola:</span><span class="sxs-lookup"><span data-stu-id="4f531-147">There are two exceptions to this rule:</span></span>

- <span data-ttu-id="4f531-148">Il binding della variabile del ciclo di un `for` ciclo è nell'ambito per il corpo del ciclo for, ma non dopo la fine del ciclo.</span><span class="sxs-lookup"><span data-stu-id="4f531-148">The binding of the loop variable of a `for` loop is in scope for the body of the for loop, but not after the end of the loop.</span></span>
- <span data-ttu-id="4f531-149">Tutte e tre le parti di un `repeat` / `until` ciclo (il corpo, il test e la correzione) fungono da singolo ambito, quindi i simboli associati al corpo sono disponibili nel test e nella correzione.</span><span class="sxs-lookup"><span data-stu-id="4f531-149">All three portions of a `repeat`/`until` loop (the body, the test, and the fixup) act as a single scope, so symbols that are bound in the body are available in the test and the fixup.</span></span>

<span data-ttu-id="4f531-150">Per entrambi i tipi di cicli, ognuno passa attraverso il ciclo viene eseguito nel proprio ambito, quindi le associazioni da un passaggio precedente non sono disponibili in un passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="4f531-150">For both types of loops, each pass through the loop runs in its own scope, so bindings from an earlier pass are not available in a later pass.</span></span>
<span data-ttu-id="4f531-151">Per altre informazioni su questi cicli, vedere [flusso di controllo](xref:microsoft.quantum.guide.controlflow).</span><span class="sxs-lookup"><span data-stu-id="4f531-151">For more information on these loops, see [Control Flow](xref:microsoft.quantum.guide.controlflow).</span></span>

<span data-ttu-id="4f531-152">I blocchi interni ereditano associazioni di simboli da blocchi esterni.</span><span class="sxs-lookup"><span data-stu-id="4f531-152">Inner blocks inherit symbol bindings from outer blocks.</span></span>
<span data-ttu-id="4f531-153">È possibile associare un simbolo una sola volta per ogni blocco; non è consentito definire un simbolo con lo stesso nome di un altro simbolo incluso nell'ambito (Nessuna ombreggiatura).</span><span class="sxs-lookup"><span data-stu-id="4f531-153">You can only bind a symbol once per block; it is illegal to define a symbol with the same name as another symbol that is within scope (no "shadowing").</span></span>
<span data-ttu-id="4f531-154">Le sequenze seguenti sono valide:</span><span class="sxs-lookup"><span data-stu-id="4f531-154">The following sequences are legal:</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

<span data-ttu-id="4f531-155">e</span><span class="sxs-lookup"><span data-stu-id="4f531-155">and</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
} else {
    ...
    let n = 8;
    ...             // n is 8
}
...                 // n is not bound to a value
```

<span data-ttu-id="4f531-156">Ma non è valido:</span><span class="sxs-lookup"><span data-stu-id="4f531-156">But this would be illegal:</span></span>

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

<span data-ttu-id="4f531-157">come:</span><span class="sxs-lookup"><span data-stu-id="4f531-157">as would:</span></span>

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="next-steps"></a><span data-ttu-id="4f531-158">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="4f531-158">Next steps</span></span>

<span data-ttu-id="4f531-159">Informazioni sull' [uso di qubits](xref:microsoft.quantum.guide.qubits) in Q# .</span><span class="sxs-lookup"><span data-stu-id="4f531-159">Learn about [Working With Qubits](xref:microsoft.quantum.guide.qubits) in Q#.</span></span>