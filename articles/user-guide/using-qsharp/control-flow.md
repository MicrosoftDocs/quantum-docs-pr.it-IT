---
title: 'Flusso di controllo in :::no-loc(Q#):::'
description: Cicli, condizionali e così via
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: eca37202e5fe9b48dcfdec4eeb4ba6cafaac8723
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691085"
---
# <a name="control-flow-in-no-locq"></a><span data-ttu-id="a746e-103">Flusso di controllo in :::no-loc(Q#):::</span><span class="sxs-lookup"><span data-stu-id="a746e-103">Control flow in :::no-loc(Q#):::</span></span>

<span data-ttu-id="a746e-104">All'interno di un'operazione o di una funzione, ogni istruzione viene eseguita in ordine, in modo analogo ad altri linguaggi classici imperativi comuni.</span><span class="sxs-lookup"><span data-stu-id="a746e-104">Within an operation or function, each statement runs in order, similar to other common imperative classical languages.</span></span>
<span data-ttu-id="a746e-105">Tuttavia, è possibile modificare il flusso di controllo in tre modi distinti:</span><span class="sxs-lookup"><span data-stu-id="a746e-105">However, you can modify the flow of control in three distinct ways:</span></span>

* <span data-ttu-id="a746e-106">`if` istruzioni</span><span class="sxs-lookup"><span data-stu-id="a746e-106">`if` statements</span></span>
* <span data-ttu-id="a746e-107">`for` cicli</span><span class="sxs-lookup"><span data-stu-id="a746e-107">`for` loops</span></span>
* <span data-ttu-id="a746e-108">`repeat-until-success` cicli</span><span class="sxs-lookup"><span data-stu-id="a746e-108">`repeat-until-success` loops</span></span>
* <span data-ttu-id="a746e-109">coniugazioni ( `apply-within` istruzioni)</span><span class="sxs-lookup"><span data-stu-id="a746e-109">conjugations (`apply-within` statements)</span></span>

<span data-ttu-id="a746e-110">I `if` `for` costrutti del flusso di controllo e procedono in un senso familiare alla maggior parte dei linguaggi di programmazione classici.</span><span class="sxs-lookup"><span data-stu-id="a746e-110">The `if` and `for` control flow constructs proceed in a familiar sense to most classical programming languages.</span></span> <span data-ttu-id="a746e-111">[`Repeat-until-success`](#repeat-until-success-loop) i cicli e le [coniugazioni](#conjugations) sono descritti più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="a746e-111">[`Repeat-until-success`](#repeat-until-success-loop) loops and [conjugations](#conjugations) are discussed later in this article.</span></span>

<span data-ttu-id="a746e-112">In particolare, `for` `if` è possibile usare cicli e istruzioni in operazioni per le quali le [specializzazioni](xref:microsoft.quantum.guide.operationsfunctions) vengono generate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a746e-112">Importantly, `for` loops and `if` statements can be used in operations for which [specializations](xref:microsoft.quantum.guide.operationsfunctions) are auto-generated.</span></span> <span data-ttu-id="a746e-113">In questo scenario, il contiguo di un `for` ciclo inverte la direzione e accetta il contiguo di ogni iterazione.</span><span class="sxs-lookup"><span data-stu-id="a746e-113">In that scenario, the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="a746e-114">Questa azione segue il principio "Shoes-and-Socks": se si vuole annullare la messa a punto dei calzini e quindi delle scarpe, è necessario annullare le calzature e quindi annullare l'inserimento sui calzini.</span><span class="sxs-lookup"><span data-stu-id="a746e-114">This action follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span> 

## <a name="if-else-if-else"></a><span data-ttu-id="a746e-115">Se, else-if, else</span><span class="sxs-lookup"><span data-stu-id="a746e-115">If, Else-if, Else</span></span>

<span data-ttu-id="a746e-116">L' `if` istruzione supporta l'elaborazione condizionale.</span><span class="sxs-lookup"><span data-stu-id="a746e-116">The `if` statement supports conditional processing.</span></span>
<span data-ttu-id="a746e-117">È costituito dalla parola chiave `if` , da un'espressione booleana tra parentesi e da un blocco di istruzioni (il blocco _then_ ).</span><span class="sxs-lookup"><span data-stu-id="a746e-117">It consists of the keyword `if`, a Boolean expression in parentheses, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="a746e-118">Facoltativamente, è possibile seguire qualsiasi numero di clausole else-if, ciascuna delle quali è costituita dalla parola chiave `elif` , da un'espressione booleana tra parentesi e da un blocco di istruzioni (il blocco _else-if_ ).</span><span class="sxs-lookup"><span data-stu-id="a746e-118">Optionally, any number of else-if clauses can follow, each of which consists of the keyword `elif`, a Boolean expression in parentheses, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="a746e-119">Infine, l'istruzione può terminare facoltativamente con una clausola else, che è costituita dalla parola chiave `else` seguita da un altro blocco Statement (il blocco _else_ ).</span><span class="sxs-lookup"><span data-stu-id="a746e-119">Finally, the statement can optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>

<span data-ttu-id="a746e-120">La `if` condizione viene valutata e, se è *true* , il blocco *then* viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="a746e-120">The `if` condition is evaluated, and if it is *true* , the *then* block is run.</span></span>
<span data-ttu-id="a746e-121">Se la condizione è *false* , viene valutata la prima condizione else-if; Se è true, viene eseguito il blocco *else-if* .</span><span class="sxs-lookup"><span data-stu-id="a746e-121">If the condition is *false* , then the first else-if condition is evaluated; if that is true, then the *else-if* block is run.</span></span>
<span data-ttu-id="a746e-122">In caso contrario, il secondo blocco Else-If restituisce, quindi il terzo e così via fino a quando non viene rilevata una clausola con una condizione true o non sono presenti altre clausole else-if.</span><span class="sxs-lookup"><span data-stu-id="a746e-122">Otherwise, the second else-if block evaluates, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="a746e-123">Se la condizione originale *if* e tutte le clausole else-if restituiscono *false* , viene eseguito il blocco *else* , se specificato.</span><span class="sxs-lookup"><span data-stu-id="a746e-123">If the original *if* condition and all the else-if clauses evaluate to *false* , the *else* block is run, if provided.</span></span>

<span data-ttu-id="a746e-124">Si noti che qualunque blocco viene eseguito, viene eseguito all'interno del proprio ambito.</span><span class="sxs-lookup"><span data-stu-id="a746e-124">Note that whichever block runs, it runs within its own scope.</span></span>
<span data-ttu-id="a746e-125">Le associazioni eseguite all'interno di `if` un `elif` blocco, o `else` non sono visibili al termine del blocco.</span><span class="sxs-lookup"><span data-stu-id="a746e-125">Bindings made inside of an `if`, `elif`, or `else` block are not visible after the block ends.</span></span>

<span data-ttu-id="a746e-126">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="a746e-126">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
<span data-ttu-id="a746e-127">oppure</span><span class="sxs-lookup"><span data-stu-id="a746e-127">or</span></span>
```qsharp
if (i == 1) {
    X(target);
    let n = 1;
} elif (i == 2) {
    Y(target);
    let m = n + 1; // would cause an error, because n is no longer bound
} else {
    Z(target);
}
```

## <a name="for-loop"></a><span data-ttu-id="a746e-128">Ciclo For</span><span class="sxs-lookup"><span data-stu-id="a746e-128">For loop</span></span>

<span data-ttu-id="a746e-129">L' `for` istruzione supporta l'iterazione su un intervallo di interi o una matrice.</span><span class="sxs-lookup"><span data-stu-id="a746e-129">The `for` statement supports iteration over an integer range or an array.</span></span>
<span data-ttu-id="a746e-130">L'istruzione è costituita dalla parola chiave `for` , seguita da un simbolo o da una tupla di simboli, la parola chiave `in` e un'espressione di tipo `Range` o matrice, tutte racchiuse tra parentesi e un blocco di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="a746e-130">The statement consists of the keyword `for`, followed by a symbol or symbol tuple, the keyword `in`, and an expression of type `Range` or array, all in parentheses, and a statement block.</span></span>

<span data-ttu-id="a746e-131">Il blocco di istruzioni (il corpo del ciclo) viene eseguito ripetutamente, con il simbolo definito (la variabile del ciclo) associato a ogni valore nell'intervallo o nella matrice.</span><span class="sxs-lookup"><span data-stu-id="a746e-131">The statement block (the body of the loop) runs repeatedly, with the defined symbol (the loop variable) bound to each value in the range or array.</span></span>
<span data-ttu-id="a746e-132">Si noti che se l'espressione di intervallo restituisce un intervallo o una matrice vuota, il corpo non viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="a746e-132">Note that if the range expression evaluates to an empty range or array, the body does not run at all.</span></span>
<span data-ttu-id="a746e-133">L'espressione viene valutata completamente prima dell'immissione del ciclo e non cambia mentre il ciclo è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a746e-133">The expression is fully evaluated before entering the loop, and does not change while the loop is running.</span></span>

<span data-ttu-id="a746e-134">La variabile di ciclo viene associata a ogni ingresso al corpo del ciclo e non è associata alla fine del corpo.</span><span class="sxs-lookup"><span data-stu-id="a746e-134">The loop variable is bound at each entrance to the loop body, and is unbound at the end of the body.</span></span>
<span data-ttu-id="a746e-135">La variabile di ciclo non è associata dopo il completamento del ciclo for.</span><span class="sxs-lookup"><span data-stu-id="a746e-135">The loop variable is not bound after the for loop is completed.</span></span>
<span data-ttu-id="a746e-136">Il binding della variabile del ciclo non è modificabile e segue le stesse regole di altre associazioni variabili.</span><span class="sxs-lookup"><span data-stu-id="a746e-136">The binding of the loop variable is immutable and follows the same rules as other variable bindings.</span></span> 

<span data-ttu-id="a746e-137">In questi esempi, `qubits` è un registro di qubits (ad esempio, di tipo `Qubit[]` ),</span><span class="sxs-lookup"><span data-stu-id="a746e-137">In these examples, `qubits` is a register of qubits (i.e. of type `Qubit[]`),</span></span> 

```qsharp
// ...
for (qubit in qubits) {  // iterate over each qubit value in the array qubits
    H(qubit);
}
// 'qubit' is no longer bound

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {  // iterates over the integers in the Range 0 .. (Length(qubits) - 1)
    set results w/= index <- (index, M(qubits[index])); // measure each qubit, updates the tuple value in the results array that at index 
}

mutable accumulated = 0;
for ((index, measured) in results) { // iterates over the tuple values in results
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```

<span data-ttu-id="a746e-138">Si noti che alla fine è stato usato l'operatore binario di spostamento a sinistra aritmetico `<<<` .</span><span class="sxs-lookup"><span data-stu-id="a746e-138">Note that at the end, we utilized the arithmetic-shift-left binary operator, `<<<`.</span></span> <span data-ttu-id="a746e-139">Per altre informazioni, vedere [espressioni numeriche](xref:microsoft.quantum.guide.expressions#numeric-expressions).</span><span class="sxs-lookup"><span data-stu-id="a746e-139">For more information, see [Numeric Expressions](xref:microsoft.quantum.guide.expressions#numeric-expressions).</span></span>

## <a name="repeat-until-success-loop"></a><span data-ttu-id="a746e-140">Ciclo repeat-until-Success</span><span class="sxs-lookup"><span data-stu-id="a746e-140">Repeat-until-success loop</span></span>

<span data-ttu-id="a746e-141">Il :::no-loc(Q#)::: linguaggio consente a un flusso di controllo classico di dipendere dai risultati della misurazione di qubits.</span><span class="sxs-lookup"><span data-stu-id="a746e-141">The :::no-loc(Q#)::: language allows classical control flow to depend on the results of measuring qubits.</span></span>
<span data-ttu-id="a746e-142">Questa funzionalità consente, a sua volta, di implementare potenti gadget probabilistici che possono ridurre il costo computazionale per l'implementazione di unitaries.</span><span class="sxs-lookup"><span data-stu-id="a746e-142">This capability, in turn, enables implementing powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span>
<span data-ttu-id="a746e-143">Esempi di questo sono i modelli di *ripetizione fino alla riuscita* (UR) in :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="a746e-143">Examples of this are the *repeat-until-success* (RUS) patterns in :::no-loc(Q#):::.</span></span>
<span data-ttu-id="a746e-144">Questi modelli di ur sono programmi probabilistici che hanno un costo basso *previsto* in termini di controlli elementari; il costo sostenuto dipende dall'esecuzione effettiva e dall'interfoliazione di più Branch possibili.</span><span class="sxs-lookup"><span data-stu-id="a746e-144">These RUS patterns are probabilistic programs that have an *expected* low cost in terms of elementary gates; the incurred cost depends on the actual run and the interleaving of the multiple possible branchings.</span></span>

<span data-ttu-id="a746e-145">Per semplificare i modelli di ripetizione fino al completamento (UR), :::no-loc(Q#)::: supporta i costrutti</span><span class="sxs-lookup"><span data-stu-id="a746e-145">To facilitate repeat-until-success (RUS) patterns, :::no-loc(Q#)::: supports the constructs</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression)
fixup {
    // do other stuff
}
```

<span data-ttu-id="a746e-146">dove `expression` è qualsiasi espressione valida che restituisce un valore di tipo `Bool` .</span><span class="sxs-lookup"><span data-stu-id="a746e-146">where `expression` is any valid expression that evaluates to a value of type `Bool`.</span></span>
<span data-ttu-id="a746e-147">Il corpo del ciclo viene eseguito, quindi la condizione viene valutata.</span><span class="sxs-lookup"><span data-stu-id="a746e-147">The loop body runs, and then the condition is evaluated.</span></span>
<span data-ttu-id="a746e-148">Se la condizione è true, l'istruzione viene completata; in caso contrario, la correzione viene eseguita e l'istruzione viene eseguita nuovamente, a partire dal corpo del ciclo.</span><span class="sxs-lookup"><span data-stu-id="a746e-148">If the condition is true, then the statement is completed; otherwise, the fixup runs, and the statement runs again, starting with the loop body.</span></span>

<span data-ttu-id="a746e-149">Tutte e tre le parti di un ciclo UR (il corpo, il test e la correzione) vengono trattate come un singolo ambito *per ogni ripetizione* , quindi i simboli associati al corpo sono disponibili sia nel test che nella correzione.</span><span class="sxs-lookup"><span data-stu-id="a746e-149">All three portions of an RUS loop (the body, the test, and the fixup) are treated as a single scope *for each repetition* , so symbols that are bound in the body are available in both the test and the fixup.</span></span>
<span data-ttu-id="a746e-150">Tuttavia, il completamento dell'esecuzione della correzione termina l'ambito dell'istruzione, in modo che le associazioni di simboli effettuate durante il corpo o la correzione non siano disponibili nelle ripetizioni successive.</span><span class="sxs-lookup"><span data-stu-id="a746e-150">However, completing the run of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="a746e-151">Inoltre, l' `fixup` istruzione è spesso utile ma non sempre necessaria.</span><span class="sxs-lookup"><span data-stu-id="a746e-151">Further, the `fixup` statement is often useful but not always necessary.</span></span>
<span data-ttu-id="a746e-152">Nei casi in cui non è necessario, il costrutto</span><span class="sxs-lookup"><span data-stu-id="a746e-152">In cases that it is not needed, the construct</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression);
```

<span data-ttu-id="a746e-153">è anche un modello ur valido.</span><span class="sxs-lookup"><span data-stu-id="a746e-153">is also a valid RUS pattern.</span></span>

<span data-ttu-id="a746e-154">Per altri esempi e dettagli, vedere [esempi di ripetizione fino al](#repeat-until-success-examples) completamento in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="a746e-154">For more examples and details, see [Repeat-until-success examples](#repeat-until-success-examples) in this article.</span></span>

> [!TIP]   
> <span data-ttu-id="a746e-155">Evitare l'utilizzo di cicli repeat-until-Success all'interno di funzioni.</span><span class="sxs-lookup"><span data-stu-id="a746e-155">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="a746e-156">Usare i cicli *while* per fornire la funzionalità corrispondente all'interno di funzioni.</span><span class="sxs-lookup"><span data-stu-id="a746e-156">Use *while* loops to provide the corresponding functionality inside functions.</span></span> 

## <a name="while-loop"></a><span data-ttu-id="a746e-157">Ciclo while</span><span class="sxs-lookup"><span data-stu-id="a746e-157">While loop</span></span>

<span data-ttu-id="a746e-158">I modelli repeat-until-Success hanno una connotazione molto specifica del quantum.</span><span class="sxs-lookup"><span data-stu-id="a746e-158">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="a746e-159">Sono ampiamente usati in particolari classi di algoritmi quantistici, quindi il costrutto di linguaggio dedicato in :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="a746e-159">They are widely used in particular classes of quantum algorithms - hence the dedicated language construct in :::no-loc(Q#):::.</span></span> <span data-ttu-id="a746e-160">Tuttavia, i cicli che si interrompono in base a una condizione e la cui lunghezza di esecuzione è sconosciuta in fase di compilazione, vengono gestiti con particolare attenzione in un runtime Quantum.</span><span class="sxs-lookup"><span data-stu-id="a746e-160">However, loops that break based on a condition and whose run length is thus unknown at compile-time, are handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="a746e-161">Tuttavia, l'uso all'interno delle funzioni non è problematico perché questi cicli contengono solo codice eseguito su hardware convenzionale (non Quantum).</span><span class="sxs-lookup"><span data-stu-id="a746e-161">However, their use within functions is unproblematic since these loops only contain code that runs on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="a746e-162">:::no-loc(Q#):::, pertanto, supporta l'utilizzo di cicli while solo all'interno di funzioni.</span><span class="sxs-lookup"><span data-stu-id="a746e-162">:::no-loc(Q#):::, therefore, supports to use of while loops within functions only.</span></span>
<span data-ttu-id="a746e-163">Un' `while` istruzione è costituita dalla parola chiave `while` , da un'espressione booleana tra parentesi e da un blocco di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="a746e-163">A `while` statement consists of the keyword `while`, a Boolean expression in parentheses, and a statement block.</span></span>
<span data-ttu-id="a746e-164">Il blocco di istruzioni (il corpo del ciclo) viene eseguito fino a quando la condizione restituisce `true` .</span><span class="sxs-lookup"><span data-stu-id="a746e-164">The statement block (the body of the loop) runs as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

## <a name="conjugations"></a><span data-ttu-id="a746e-165">Coniugazioni</span><span class="sxs-lookup"><span data-stu-id="a746e-165">Conjugations</span></span>

<span data-ttu-id="a746e-166">A differenza dei bit classici, il rilascio della memoria quantistica è leggermente più coinvolto, perché la reimpostazione cieca di qubits può avere effetti indesiderati sul calcolo rimanente se il qubits è ancora stato impigliato.</span><span class="sxs-lookup"><span data-stu-id="a746e-166">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="a746e-167">Questi effetti possono essere evitati eseguendo correttamente l'operazione di calcolo prima di rilasciare la memoria.</span><span class="sxs-lookup"><span data-stu-id="a746e-167">These effects can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="a746e-168">Un modello comune in quantum computing è quindi il seguente:</span><span class="sxs-lookup"><span data-stu-id="a746e-168">A common pattern in quantum computing is hence the following:</span></span> 

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

<span data-ttu-id="a746e-169">:::no-loc(Q#)::: supporta un'istruzione di coniugazione che implementa la trasformazione precedente.</span><span class="sxs-lookup"><span data-stu-id="a746e-169">:::no-loc(Q#)::: supports a conjugation statement that implements the preceding transformation.</span></span> <span data-ttu-id="a746e-170">Utilizzando tale istruzione, `ApplyWith` è possibile implementare l'operazione nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="a746e-170">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

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
<span data-ttu-id="a746e-171">Una tale istruzione di coniugazione diventa utile se le trasformazioni esterne e interne non sono immediatamente disponibili come operazioni, ma sono più convenienti da descrivere da un blocco composto da diverse istruzioni.</span><span class="sxs-lookup"><span data-stu-id="a746e-171">Such a conjugation statement becomes useful if the outer and inner transformations are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="a746e-172">La trasformazione inversa per le istruzioni definite nel blocco interno viene generata automaticamente dal compilatore e viene eseguita al termine del blocco Apply.</span><span class="sxs-lookup"><span data-stu-id="a746e-172">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and run after the apply-block completes.</span></span>
<span data-ttu-id="a746e-173">Poiché le variabili modificabili usate come parte del blocco all'interno non possono essere riassociati nel blocco Apply, la trasformazione generata è sicuramente l'elemento contiguo del calcolo nel blocco all'interno.</span><span class="sxs-lookup"><span data-stu-id="a746e-173">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 

## <a name="return-statement"></a><span data-ttu-id="a746e-174">Istruzione Return</span><span class="sxs-lookup"><span data-stu-id="a746e-174">Return Statement</span></span>

<span data-ttu-id="a746e-175">L'istruzione return termina l'esecuzione di un'operazione o di una funzione e restituisce un valore al chiamante.</span><span class="sxs-lookup"><span data-stu-id="a746e-175">The return statement ends the run of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="a746e-176">È costituito dalla parola chiave `return` , seguita da un'espressione del tipo appropriato e da un punto e virgola di terminazione.</span><span class="sxs-lookup"><span data-stu-id="a746e-176">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="a746e-177">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="a746e-177">For example,</span></span>
```qsharp
return 1;
```
<span data-ttu-id="a746e-178">oppure</span><span class="sxs-lookup"><span data-stu-id="a746e-178">or</span></span>
```qsharp
return (results, qubits);
```

* <span data-ttu-id="a746e-179">Un oggetto chiamabile che restituisce una tupla vuota, `()` , non richiede un'istruzione return.</span><span class="sxs-lookup"><span data-stu-id="a746e-179">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
* <span data-ttu-id="a746e-180">Per specificare una prima uscita dall'operazione o dalla funzione, usare `return ();` .</span><span class="sxs-lookup"><span data-stu-id="a746e-180">To specify an early exit from the operation or function, use `return ();`.</span></span>
<span data-ttu-id="a746e-181">Le Callable che restituiscono qualsiasi altro tipo richiedono un'istruzione return finale.</span><span class="sxs-lookup"><span data-stu-id="a746e-181">Callables that return any other type require a final return statement.</span></span>
* <span data-ttu-id="a746e-182">Non esiste un numero massimo di istruzioni return all'interno di un'operazione.</span><span class="sxs-lookup"><span data-stu-id="a746e-182">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="a746e-183">Il compilatore può generare un avviso se le istruzioni seguono un'istruzione return all'interno di un blocco.</span><span class="sxs-lookup"><span data-stu-id="a746e-183">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

   
## <a name="fail-statement"></a><span data-ttu-id="a746e-184">Istruzione Fail</span><span class="sxs-lookup"><span data-stu-id="a746e-184">Fail statement</span></span>

<span data-ttu-id="a746e-185">L'istruzione Fail termina l'esecuzione di un'operazione e restituisce un valore di errore al chiamante.</span><span class="sxs-lookup"><span data-stu-id="a746e-185">The fail statement ends the run of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="a746e-186">È costituito dalla parola chiave `fail` , seguita da una stringa e da un punto e virgola di terminazione.</span><span class="sxs-lookup"><span data-stu-id="a746e-186">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="a746e-187">L'istruzione restituisce la stringa al driver classico come messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="a746e-187">The statement returns the string to the classical driver as the error message.</span></span>

<span data-ttu-id="a746e-188">Non esiste alcuna restrizione sul numero di istruzioni fail in un'operazione.</span><span class="sxs-lookup"><span data-stu-id="a746e-188">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="a746e-189">Il compilatore può generare un avviso se le istruzioni seguono un'istruzione Fail all'interno di un blocco.</span><span class="sxs-lookup"><span data-stu-id="a746e-189">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="a746e-190">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="a746e-190">For example,</span></span>

```qsharp
fail $"Impossible state reached";
```
<span data-ttu-id="a746e-191">oppure, usando [stringhe interpolate](xref:microsoft.quantum.guide.expressions#interpolated-strings),</span><span class="sxs-lookup"><span data-stu-id="a746e-191">or, using [interpolated strings](xref:microsoft.quantum.guide.expressions#interpolated-strings),</span></span>
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a><span data-ttu-id="a746e-192">Esempi di ripetizione fino al completamento</span><span class="sxs-lookup"><span data-stu-id="a746e-192">Repeat-until-success examples</span></span>

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a><span data-ttu-id="a746e-193">Modello ur per la rotazione a qubit singolo su un asse irrazionale</span><span class="sxs-lookup"><span data-stu-id="a746e-193">RUS pattern for single-qubit rotation about an irrational axis</span></span> 

<span data-ttu-id="a746e-194">In un caso di utilizzo tipico, l' :::no-loc(Q#)::: operazione seguente implementa una rotazione intorno a un asse irrazionale di $ (I + 2i Z)/\sqrt {5} $ sulla sfera Bloch.</span><span class="sxs-lookup"><span data-stu-id="a746e-194">In a typical use case, the following :::no-loc(Q#)::: operation implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="a746e-195">L'implementazione usa un modello di ur noto:</span><span class="sxs-lookup"><span data-stu-id="a746e-195">The implementation uses a known RUS pattern:</span></span>

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

### <a name="rus-loop-with-a-mutable-variable-in-scope"></a><span data-ttu-id="a746e-196">Ciclo ur con una variabile modificabile nell'ambito</span><span class="sxs-lookup"><span data-stu-id="a746e-196">RUS loop with a mutable variable in scope</span></span>

<span data-ttu-id="a746e-197">Questo esempio illustra l'uso di una variabile modificabile, `finished` , che rientra nell'ambito dell'intero ciclo di ripetizione fino alla correzione e che viene inizializzato prima del ciclo e aggiornato nel passaggio di correzione.</span><span class="sxs-lookup"><span data-stu-id="a746e-197">This example shows the use of a mutable variable, `finished`, which is within the scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

```qsharp
mutable iter = 1;
repeat {
    ProbabilisticCircuit(qubits);
    let success = ComputeSuccessIndicator(qubits);
}
until (success || iter > maxIter)
fixup {
    iter += 1;
    ComputeCorrection(qubits);
}
```

### <a name="rus-without-fixup"></a><span data-ttu-id="a746e-198">UR senza `fixup`</span><span class="sxs-lookup"><span data-stu-id="a746e-198">RUS without `fixup`</span></span>

<span data-ttu-id="a746e-199">Questo esempio mostra un ciclo UR senza il passaggio di correzione.</span><span class="sxs-lookup"><span data-stu-id="a746e-199">This example shows an RUS loop without the fixup step.</span></span> <span data-ttu-id="a746e-200">Il codice è un circuito probabilistico che implementa un gate di rotazione importante $V _3 = (\boldone + 2 i Z)/\sqrt {5} $ usando le attività `H` di controllo e `T` .</span><span class="sxs-lookup"><span data-stu-id="a746e-200">The code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the `H` and `T` gates.</span></span>
<span data-ttu-id="a746e-201">Il ciclo termina in media le ripetizioni di $ \frac {8} {5} $.</span><span class="sxs-lookup"><span data-stu-id="a746e-201">The loop terminates in $\frac{8}{5}$ repetitions on average.</span></span>
<span data-ttu-id="a746e-202">Per informazioni dettagliate, vedere [*repeat-until-Success: scomposizione non deterministica di single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Papini e Svore, 2014).</span><span class="sxs-lookup"><span data-stu-id="a746e-202">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for more details.</span></span>

```qsharp
using (qubit = Qubit()) {
    repeat {
        H(qubit);
        T(qubit);
        CNOT(target, qubit);
        H(qubit);
        Adjoint T(qubit);
        H(qubit);
        T(qubit);
        H(qubit);
        CNOT(target, qubit);
        T(qubit);
        Z(target);
        H(qubit);
        let result = M(qubit);
    } until (result == Zero);
}
```

### <a name="rus-to-prepare-a-quantum-state"></a><span data-ttu-id="a746e-203">UR per preparare uno stato quantico</span><span class="sxs-lookup"><span data-stu-id="a746e-203">RUS to prepare a quantum state</span></span>

<span data-ttu-id="a746e-204">Infine, di seguito è riportato un esempio di modello ur per preparare uno stato quantico $ \frac {1} {\sqrt {3} } \left (\sqrt {2} \ket {0} + \ket {1} \right) $, a partire dallo stato $ \ket{+} $.</span><span class="sxs-lookup"><span data-stu-id="a746e-204">Finally, here is an example of an RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span>

<span data-ttu-id="a746e-205">Le funzionalità a livello di codice indicate in questa operazione sono:</span><span class="sxs-lookup"><span data-stu-id="a746e-205">Notable programmatic features shown in this operation are:</span></span>

* <span data-ttu-id="a746e-206">Parte più complessa `fixup` del ciclo, che implica operazioni Quantum.</span><span class="sxs-lookup"><span data-stu-id="a746e-206">A more complex `fixup` part of the loop, which involves quantum operations.</span></span> 
* <span data-ttu-id="a746e-207">Utilizzo di `AssertMeasurementProbability` istruzioni per verificare la probabilità di misurare lo stato del quantum in determinati punti specificati del programma.</span><span class="sxs-lookup"><span data-stu-id="a746e-207">The use of `AssertMeasurementProbability` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span>

<span data-ttu-id="a746e-208">Per ulteriori informazioni sulle [`AssertMeasurement`](xref:Microsoft.Quantum.Diagnostics.assertmeasurement) operazioni e [`AssertMeasurementProbability`](xref:Microsoft.Quantum.Diagnostics.assertmeasurementprobability) , vedere [testing and Debugging](xref:microsoft.quantum.guide.testingdebugging).</span><span class="sxs-lookup"><span data-stu-id="a746e-208">For more information about the [`AssertMeasurement`](xref:Microsoft.Quantum.Diagnostics.assertmeasurement) and [`AssertMeasurementProbability`](xref:Microsoft.Quantum.Diagnostics.assertmeasurementprobability) operations, see [Testing and debugging](xref:microsoft.quantum.guide.testingdebugging).</span></span>

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertMeasurementProbability(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertMeasurementProbability(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertMeasurementProbability(
                [PauliX], [auxiliary], Zero, 3. / 4.,
                "Error: the probability to measure |+> in the first
                auxiliary must be 3/4",
                1e-10);

            // If we get the measurement outcome Zero, we prepare the
            // required state.
            let outcome = Measure([PauliX], [auxiliary]);
        }
        until (outcome == Zero)
        fixup {
            // Bring the auxiliary and target qubits back to |+> state.
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

<span data-ttu-id="a746e-209">Per ulteriori informazioni, vedere [l'esempio di unit test fornito con la libreria standard](https://github.com/microsoft/Quantum/blob/main/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span><span class="sxs-lookup"><span data-stu-id="a746e-209">For more information, see [unit testing sample provided with the standard library](https://github.com/microsoft/Quantum/blob/main/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span></span>

## <a name="next-steps"></a><span data-ttu-id="a746e-210">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="a746e-210">Next steps</span></span>

<span data-ttu-id="a746e-211">Informazioni sul [test e il debug](xref:microsoft.quantum.guide.testingdebugging) in :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="a746e-211">Learn about [Testing and Debugging](xref:microsoft.quantum.guide.testingdebugging) in :::no-loc(Q#):::.</span></span>
