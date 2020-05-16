---
title: 'Variabili in Q #'
description: Descrizione riempimento
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.variables
ms.openlocfilehash: 407b4ff3570816eb7bdc323a5c5b77dac2d951af
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430901"
---
# <a name="variables-in-q"></a><span data-ttu-id="1070b-103">Variabili in Q #</span><span class="sxs-lookup"><span data-stu-id="1070b-103">Variables in Q#</span></span>

<span data-ttu-id="1070b-104">Q # distingue tra simboli modificabili e non modificabili o "Variables", che sono associati o assegnati a espressioni.</span><span class="sxs-lookup"><span data-stu-id="1070b-104">Q# distinguishes between mutable and immutable symbols, or "variables", which are bound/assigned to expressions.</span></span>
<span data-ttu-id="1070b-105">In generale, l'uso di simboli non modificabili è consigliato perché consente al compilatore di eseguire altre ottimizzazioni.</span><span class="sxs-lookup"><span data-stu-id="1070b-105">In general, the use of immutable symbols is encouraged because it allows the compiler to perform more optimizations.</span></span>

<span data-ttu-id="1070b-106">Il lato sinistro di un'associazione è costituito da una tupla di simboli e dalla parte destra di un'espressione.</span><span class="sxs-lookup"><span data-stu-id="1070b-106">The left-hand-side of a binding consists of a symbol tuple, and the right hand side of an expression.</span></span>

## <a name="immutable-variables"></a><span data-ttu-id="1070b-107">Variabili non modificabili</span><span class="sxs-lookup"><span data-stu-id="1070b-107">Immutable Variables</span></span>

<span data-ttu-id="1070b-108">Un valore di qualsiasi tipo in Q # può essere assegnato a una variabile per il riutilizzo all'interno di un'operazione o funzione tramite la `let` parola chiave.</span><span class="sxs-lookup"><span data-stu-id="1070b-108">A value of any type in Q# can be assigned to a variable for reuse within an operation or function by using the `let` keyword.</span></span>

<span data-ttu-id="1070b-109">Un'associazione non modificabile è costituita dalla parola chiave `let` , seguita da un simbolo o da una tupla di simboli, un segno di uguale `=` , un'espressione a cui associare i simboli e un punto e virgola di terminazione.</span><span class="sxs-lookup"><span data-stu-id="1070b-109">An immutable binding consists of the keyword `let`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>

<span data-ttu-id="1070b-110">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1070b-110">For instance:</span></span>

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

<span data-ttu-id="1070b-111">Questa operazione assegna una matrice specifica di operatori Pauli al nome della variabile (o "symbol"), `measurementOperator` .</span><span class="sxs-lookup"><span data-stu-id="1070b-111">This assigns a particular array of Pauli operators to the variable name (or "symbol"), `measurementOperator`.</span></span>

> [!NOTE]
> <span data-ttu-id="1070b-112">Non è stato necessario specificare in modo esplicito il tipo della nuova variabile, poiché l'espressione sul lato destro dell' `let` istruzione non è ambigua e il tipo viene dedotto dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="1070b-112">We did not need to explicitly specify the type of our new variable, as the expression on the right-hand side of the `let` statement is unambiguous and the type is inferred by the compiler.</span></span> 

<span data-ttu-id="1070b-113">Le variabili definite utilizzando `let` non sono *modificabili*, ovvero una volta definito, non possono più essere modificate in alcun modo.</span><span class="sxs-lookup"><span data-stu-id="1070b-113">Variables defined using `let` are *immutable*, meaning that once it has been defined, it can no longer be changed in any way.</span></span>
<span data-ttu-id="1070b-114">Questo consente diverse ottimizzazioni utili, inclusa l'ottimizzazione della logica classica che agisce sulle variabili da riordinare per l'applicazione della `Adjoint` variante di un'operazione.</span><span class="sxs-lookup"><span data-stu-id="1070b-114">This allows for several beneficial optimizations, including optimization of the classical logic acting on variables to be reordered for applying the `Adjoint` variant of an operation.</span></span>

## <a name="mutable-variables"></a><span data-ttu-id="1070b-115">Variabili modificabili</span><span class="sxs-lookup"><span data-stu-id="1070b-115">Mutable Variables</span></span>

<span data-ttu-id="1070b-116">In alternativa alla creazione di una variabile con `let` , la `mutable` parola chiave creerà una variabile modificabile che *può* essere riassociata dopo che è stata creata inizialmente con la `set` parola chiave.</span><span class="sxs-lookup"><span data-stu-id="1070b-116">As an alternative to creating a variable with `let`, the `mutable` keyword will create a mutable variable that *can* be re-bound after it is initially created by using the `set` keyword.</span></span>

<span data-ttu-id="1070b-117">I simboli dichiarati e associati come parte di un' `mutable` istruzione possono essere riassociati a un valore diverso in un secondo momento nel codice.</span><span class="sxs-lookup"><span data-stu-id="1070b-117">Symbols declared and bound as part of a `mutable` statement may be rebound to a different value later in the code.</span></span> <span data-ttu-id="1070b-118">Se un simbolo viene riassociato in un secondo momento nel codice, il relativo tipo non viene modificato e il nuovo valore associato deve essere compatibile con quel tipo.</span><span class="sxs-lookup"><span data-stu-id="1070b-118">If a symbol is rebound later in the code, its type does not change, and the newly bound value needs to be compatible with that type.</span></span>

### <a name="rebinding-of-mutable-symbols"></a><span data-ttu-id="1070b-119">Riassociazione di simboli modificabili</span><span class="sxs-lookup"><span data-stu-id="1070b-119">Rebinding of Mutable Symbols</span></span>

<span data-ttu-id="1070b-120">Una variabile modificabile può essere riassociata usando un' `set` istruzione.</span><span class="sxs-lookup"><span data-stu-id="1070b-120">A mutable variable may be rebound using a `set` statement.</span></span>
<span data-ttu-id="1070b-121">Tale riassociazione è costituita dalla parola chiave `set` , seguita da un simbolo o da una tupla di simboli, un segno di uguale `=` , un'espressione per riassociare i simboli a e un punto e virgola di terminazione.</span><span class="sxs-lookup"><span data-stu-id="1070b-121">Such a rebinding consists of the keyword `set`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to rebind the symbol(s) to, and a terminating semicolon.</span></span>

<span data-ttu-id="1070b-122">Di seguito vengono forniti alcuni esempi possibili di tecniche di riassociazione delle istruzioni</span><span class="sxs-lookup"><span data-stu-id="1070b-122">Here, we provide some possible examples of rebinding statement techniques</span></span>

### <a name="apply-and-reassign-statements"></a><span data-ttu-id="1070b-123">Istruzioni Apply-and-reassign</span><span class="sxs-lookup"><span data-stu-id="1070b-123">Apply-and-Reassign Statements</span></span>

<span data-ttu-id="1070b-124">Un particolare tipo di `set` istruzione a cui si fa riferimento come istruzione *Apply-and-reassign* fornisce un modo pratico per la concatenazione se il lato destro è costituito dall'applicazione di un operatore binario e il risultato deve essere riassociato all'argomento a sinistra per l'operatore.</span><span class="sxs-lookup"><span data-stu-id="1070b-124">A particular kind of `set`-statement we refer to as an *apply-and-reassign* statement provides a convenient way of concatenation if the right hand side consists of the application of a binary operator and the result is to be rebound to the left argument to the operator.</span></span> <span data-ttu-id="1070b-125">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="1070b-125">For example,</span></span>
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
<span data-ttu-id="1070b-126">incrementa il valore del contatore `counter` in ogni iterazione del `for` ciclo.</span><span class="sxs-lookup"><span data-stu-id="1070b-126">increments the value of the counter `counter` in each iteration of the `for` loop.</span></span> <span data-ttu-id="1070b-127">Il codice precedente è equivalente a</span><span class="sxs-lookup"><span data-stu-id="1070b-127">The code above is equivalent to</span></span> 
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```

<span data-ttu-id="1070b-128">Sono disponibili istruzioni simili per tutti gli operatori binari in cui il tipo della parte sinistra corrisponde al tipo di espressione.</span><span class="sxs-lookup"><span data-stu-id="1070b-128">Similar statements are available for all binary operators in which the type of the left-hand-side matches the expression type.</span></span> <span data-ttu-id="1070b-129">In questo modo, ad esempio, viene fornito un modo pratico per accumulare i valori.</span><span class="sxs-lookup"><span data-stu-id="1070b-129">This provides for example a convenient way to accumulate values.</span></span>

<span data-ttu-id="1070b-130">Ad esempio, supponendo che `qubits` sia un regsiter di qubits:</span><span class="sxs-lookup"><span data-stu-id="1070b-130">For example, supposing `qubits` is a regsiter of qubits:</span></span>
```qsharp
mutable results = new Result[0];   // results is an empty array of type Result[]
for (q in qubits) {
    set results += [M(q)];         // concatenate the outcome from measuring q to the existing array
    // ...
}
...                                // results contains the measurement outcomes from the whole register
```

### <a name="update-and-reassign-statements"></a><span data-ttu-id="1070b-131">Istruzioni Update e reassign</span><span class="sxs-lookup"><span data-stu-id="1070b-131">Update-and-Reassign Statements</span></span>

<span data-ttu-id="1070b-132">Esiste una concatenazione simile per le [espressioni di copia e aggiornamento](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) sul lato destro.</span><span class="sxs-lookup"><span data-stu-id="1070b-132">A similar concatenation exists for [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) on the right-hand-side.</span></span>
<span data-ttu-id="1070b-133">Per *gli elementi denominati* nei tipi definiti dall'utente e per *gli elementi della matrice*sono disponibili *le istruzioni Update e reassign* corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="1070b-133">Correspondingly, *update-and-reassign* statements exist for *named items* in user-defined types as well as for *array items*.</span></span>  

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

<span data-ttu-id="1070b-134">Nel caso di matrici, [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) nelle librerie standard sono disponibili gli strumenti necessari per molte esigenze comuni di inizializzazione e manipolazione degli array, evitando così di dover aggiornare gli elementi della matrice in primo luogo.</span><span class="sxs-lookup"><span data-stu-id="1070b-134">In the case of arrays, [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) in our standard libraries provides the necessary tools for many common array initialization and manipulation needs, and thus help avoid having to update array items in the first place.</span></span> 

<span data-ttu-id="1070b-135">Le istruzioni Update-and-reassign forniscono un'alternativa se necessario:</span><span class="sxs-lookup"><span data-stu-id="1070b-135">Update-and-reassign statements provide an alternative if needed:</span></span>

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

<span data-ttu-id="1070b-136">Utilizzando gli strumenti di libreria per le matrici disponibili in [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) , è possibile, ad esempio, definire con facilità una funzione che restituisce una matrice di Paulis in cui Pauli at index `i` accetta il valore specificato e tutte le altre voci sono l'identità.</span><span class="sxs-lookup"><span data-stu-id="1070b-136">Using the library tools for arrays provided in [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays), we can, for example, easily define a function that returns an array of Paulis where the Pauli at index `i` takes the given value and all other entries are the identity.</span></span>

<span data-ttu-id="1070b-137">Di seguito sono riportate due definizioni di una funzione di questo tipo, il secondo sfruttando gli strumenti a disposizione.</span><span class="sxs-lookup"><span data-stu-id="1070b-137">Here are two definitions of such a function, with the second taking advantage of the tools at our disposal.</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];             // initialize pauliArray of given length
    for (index in 0 .. length - 1) {                    // iterate over the integers in the length range
        set pauliArray w/= index <-                     // change the value at index to input pauli or PauliI
            index == location ? pauli | PauliI;         // cond. expression evaluating to pauli or PauliI dep. on whether index==location
    }    
    return pauliArray;
}
```

<span data-ttu-id="1070b-138">Anziché scorrere ogni indice nella matrice e impostarlo in modo condizionale su `PauliI` o, è `Pauli` invece possibile utilizzare `ConstantArray` da [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) per creare una matrice di `PauliI` e quindi restituire semplicemente un'espressione di copia e aggiornamento in cui è stato modificato il valore specifico in corrispondenza dell'indice `location` :</span><span class="sxs-lookup"><span data-stu-id="1070b-138">Instead of iterating over each index in the array, and conditionally setting it to `PauliI` or `Pauli`, we can instead use `ConstantArray` from [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) to create an array of `PauliI`'s, and then simply returning a copy-and-update expression in which we've changed the specifc value at index `location`:</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

## <a name="tuple-deconstruction"></a><span data-ttu-id="1070b-139">Decostruzione di Tuple</span><span class="sxs-lookup"><span data-stu-id="1070b-139">Tuple Deconstruction</span></span>

<span data-ttu-id="1070b-140">Oltre a assegnare una singola variabile, le `let` `mutable` parole chiave e---o in realtà qualsiasi altro costrutto di binding, ad esempio `set` (descritto di seguito)---consente anche di decomprimere il contenuto di un [tipo di tupla](xref:microsoft.quantum.guide.types#tuple-types).</span><span class="sxs-lookup"><span data-stu-id="1070b-140">In addition to assigning a single variable, the `let` and `mutable` keywords---or in fact any other binding construct, such as `set` (described below)---also allow for unpacking the contents of a [tuple type](xref:microsoft.quantum.guide.types#tuple-types).</span></span>
<span data-ttu-id="1070b-141">Un'assegnazione di questo form è detta *decostruzione* degli elementi di tale tupla.</span><span class="sxs-lookup"><span data-stu-id="1070b-141">An assignment of this form is said to *deconstruct* the elements of that tuple.</span></span>

<span data-ttu-id="1070b-142">Se il lato destro dell'associazione è una tupla, la tupla può essere decostruita al momento dell'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="1070b-142">If the right-hand side of the binding is a tuple, then that tuple may be deconstructed upon assignment.</span></span>
<span data-ttu-id="1070b-143">Tali decostruzioni possono coinvolgere Tuple nidificate e qualsiasi decostruzione completa o parziale è valida purché la forma della tupla sulla parte destra sia compatibile con la forma della tupla di simboli.</span><span class="sxs-lookup"><span data-stu-id="1070b-143">Such deconstructions may involve nested tuples, and any full or partial deconstruction is valid as long as the shape of the tuple on the right hand side is compatible with the shape of the symbol tuple.</span></span>

<span data-ttu-id="1070b-144">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1070b-144">For example:</span></span>

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

## <a name="binding-scopes"></a><span data-ttu-id="1070b-145">Ambiti di associazione</span><span class="sxs-lookup"><span data-stu-id="1070b-145">Binding Scopes</span></span>

<span data-ttu-id="1070b-146">In generale, le associazioni di simboli non rientrano nell'ambito e diventano inattive alla fine del blocco di istruzioni in cui si verificano.</span><span class="sxs-lookup"><span data-stu-id="1070b-146">In general, symbol bindings go out of scope and become inoperative at the end of the statement block they occur in.</span></span>
<span data-ttu-id="1070b-147">Sono previste due eccezioni a questa regola:</span><span class="sxs-lookup"><span data-stu-id="1070b-147">There are two exceptions to this rule:</span></span>

- <span data-ttu-id="1070b-148">Il binding della variabile del ciclo di un `for` ciclo è nell'ambito per il corpo del ciclo for, ma non dopo la fine del ciclo.</span><span class="sxs-lookup"><span data-stu-id="1070b-148">The binding of the loop variable of a `for` loop is in scope for the body of the for loop, but not after the end of the loop.</span></span>
- <span data-ttu-id="1070b-149">Tutte e tre le parti di un `repeat` / `until` ciclo (il corpo, il test e la correzione) vengono trattate come un singolo ambito, quindi i simboli associati nel corpo sono disponibili nel test e nella correzione.</span><span class="sxs-lookup"><span data-stu-id="1070b-149">All three portions of a `repeat`/`until` loop (the body, the test, and the fixup) are treated as a single scope, so symbols that are bound in the body are available in the test and in the fixup.</span></span>

<span data-ttu-id="1070b-150">Per entrambi i tipi di cicli, ognuno passa attraverso il ciclo viene eseguito nel proprio ambito, quindi le associazioni da un passaggio precedente non sono disponibili in un passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="1070b-150">For both types of loops, each pass through the loop executes in its own scope, so bindings from an earlier pass are not available in a later pass.</span></span>
<span data-ttu-id="1070b-151">I dettagli su questi cicli sono disponibili nel [flusso di controllo](xref:microsoft.quantum.guide.controlflow).</span><span class="sxs-lookup"><span data-stu-id="1070b-151">Details on these loops can be found at [Control Flow](xref:microsoft.quantum.guide.controlflow).</span></span>

<span data-ttu-id="1070b-152">Le associazioni di simboli dei blocchi esterni vengono ereditate da blocchi interni.</span><span class="sxs-lookup"><span data-stu-id="1070b-152">Symbol bindings from outer blocks are inherited by inner blocks.</span></span>
<span data-ttu-id="1070b-153">Un simbolo può essere associato una sola volta per blocco; non è consentito definire un simbolo con lo stesso nome di un altro simbolo incluso nell'ambito (Nessuna ombreggiatura).</span><span class="sxs-lookup"><span data-stu-id="1070b-153">A symbol may only be bound once per block; it is illegal to define a symbol with the same name as another symbol that is within scope (no "shadowing").</span></span>
<span data-ttu-id="1070b-154">Le sequenze seguenti sarebbero valide:</span><span class="sxs-lookup"><span data-stu-id="1070b-154">The following sequences would be legal:</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

<span data-ttu-id="1070b-155">e</span><span class="sxs-lookup"><span data-stu-id="1070b-155">and</span></span>

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

<span data-ttu-id="1070b-156">Ma non è valido:</span><span class="sxs-lookup"><span data-stu-id="1070b-156">But this would be illegal:</span></span>

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

<span data-ttu-id="1070b-157">come:</span><span class="sxs-lookup"><span data-stu-id="1070b-157">as would:</span></span>

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="whats-next"></a><span data-ttu-id="1070b-158">Operazioni successive</span><span class="sxs-lookup"><span data-stu-id="1070b-158">What's Next?</span></span>
<span data-ttu-id="1070b-159">Informazioni sull' [uso di qubits](xref:microsoft.quantum.guide.qubits) in Q #.</span><span class="sxs-lookup"><span data-stu-id="1070b-159">Learn about [Working With Qubits](xref:microsoft.quantum.guide.qubits) in Q#.</span></span>