---
title: Flusso di controllo in Q#
description: Cicli, condizionali e così via
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
no-loc:
- Q#
- $$v
ms.openlocfilehash: e8c873868d6f697fc90b23a38c11f35e46b40c4f
ms.sourcegitcommit: 8256ff463eb9319f1933820a36c0838cf1e024e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2020
ms.locfileid: "90759663"
---
# <a name="control-flow-in-no-locq"></a><span data-ttu-id="8ee4a-103">Flusso di controllo in Q#</span><span class="sxs-lookup"><span data-stu-id="8ee4a-103">Control flow in Q#</span></span>

<span data-ttu-id="8ee4a-104">All'interno di un'operazione o di una funzione, ogni istruzione viene eseguita in ordine, in modo analogo ad altri linguaggi classici imperativi comuni.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-104">Within an operation or function, each statement runs in order, similar to other common imperative classical languages.</span></span>
<span data-ttu-id="8ee4a-105">Tuttavia, è possibile modificare il flusso di controllo in tre modi distinti:</span><span class="sxs-lookup"><span data-stu-id="8ee4a-105">However, you can modify the flow of control in three distinct ways:</span></span>

* <span data-ttu-id="8ee4a-106">`if` istruzioni</span><span class="sxs-lookup"><span data-stu-id="8ee4a-106">`if` statements</span></span>
* <span data-ttu-id="8ee4a-107">`for` cicli</span><span class="sxs-lookup"><span data-stu-id="8ee4a-107">`for` loops</span></span>
* <span data-ttu-id="8ee4a-108">`repeat-until-success` cicli</span><span class="sxs-lookup"><span data-stu-id="8ee4a-108">`repeat-until-success` loops</span></span>

<span data-ttu-id="8ee4a-109">I `if` `for` costrutti del flusso di controllo e procedono in un senso familiare alla maggior parte dei linguaggi di programmazione classici.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-109">The `if` and `for` control flow constructs proceed in a familiar sense to most classical programming languages.</span></span> <span data-ttu-id="8ee4a-110">[`Repeat-until-success`](#repeat-until-success-loop) i cicli sono descritti più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-110">[`Repeat-until-success`](#repeat-until-success-loop) loops are discussed later in this article.</span></span>

<span data-ttu-id="8ee4a-111">In particolare, `for` `if` è possibile usare cicli e istruzioni in operazioni per le quali le [specializzazioni](xref:microsoft.quantum.guide.operationsfunctions) vengono generate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-111">Importantly, `for` loops and `if` statements can be used in operations for which [specializations](xref:microsoft.quantum.guide.operationsfunctions) are auto-generated.</span></span> <span data-ttu-id="8ee4a-112">In questo scenario, il contiguo di un `for` ciclo inverte la direzione e accetta il contiguo di ogni iterazione.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-112">In that scenario, the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="8ee4a-113">Questa azione segue il principio "Shoes-and-Socks": se si vuole annullare la messa a punto dei calzini e quindi delle scarpe, è necessario annullare le calzature e quindi annullare l'inserimento sui calzini.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-113">This action follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span> 

## <a name="if-else-if-else"></a><span data-ttu-id="8ee4a-114">Se, else-if, else</span><span class="sxs-lookup"><span data-stu-id="8ee4a-114">If, Else-if, Else</span></span>

<span data-ttu-id="8ee4a-115">L' `if` istruzione supporta l'esecuzione condizionale.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-115">The `if` statement supports conditional execution.</span></span>
<span data-ttu-id="8ee4a-116">È costituito dalla parola chiave `if` , da un'espressione booleana tra parentesi e da un blocco di istruzioni (il blocco _then_ ).</span><span class="sxs-lookup"><span data-stu-id="8ee4a-116">It consists of the keyword `if`, a Boolean expression in parentheses, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="8ee4a-117">Facoltativamente, è possibile seguire qualsiasi numero di clausole else-if, ciascuna delle quali è costituita dalla parola chiave `elif` , da un'espressione booleana tra parentesi e da un blocco di istruzioni (il blocco _else-if_ ).</span><span class="sxs-lookup"><span data-stu-id="8ee4a-117">Optionally, any number of else-if clauses can follow, each of which consists of the keyword `elif`, a Boolean expression in parentheses, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="8ee4a-118">Infine, l'istruzione può terminare facoltativamente con una clausola else, che è costituita dalla parola chiave `else` seguita da un altro blocco Statement (il blocco _else_ ).</span><span class="sxs-lookup"><span data-stu-id="8ee4a-118">Finally, the statement can optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>

<span data-ttu-id="8ee4a-119">La `if` condizione viene valutata e, se è *true*, il blocco *then* viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-119">The `if` condition is evaluated, and if it is *true*, the *then* block is run.</span></span>
<span data-ttu-id="8ee4a-120">Se la condizione è *false*, viene valutata la prima condizione else-if; Se è true, viene eseguito il blocco *else-if* .</span><span class="sxs-lookup"><span data-stu-id="8ee4a-120">If the condition is *false*, then the first else-if condition is evaluated; if that is true, then the *else-if* block is run.</span></span>
<span data-ttu-id="8ee4a-121">In caso contrario, il secondo blocco Else-If restituisce, quindi il terzo e così via fino a quando non viene rilevata una clausola con una condizione true o non sono presenti altre clausole else-if.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-121">Otherwise, the second else-if block evaluates, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="8ee4a-122">Se la condizione originale *if* e tutte le clausole else-if restituiscono *false*, viene eseguito il blocco *else* , se specificato.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-122">If the original *if* condition and all the else-if clauses evaluate to *false*, the *else* block is run, if provided.</span></span>

<span data-ttu-id="8ee4a-123">Si noti che qualunque blocco viene eseguito, viene eseguito all'interno del proprio ambito.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-123">Note that whichever block runs, it runs within its own scope.</span></span>
<span data-ttu-id="8ee4a-124">Le associazioni eseguite all'interno di `if` un `elif` blocco, o `else` non sono visibili al termine del blocco.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-124">Bindings made inside of an `if`, `elif`, or `else` block are not visible after the block ends.</span></span>

<span data-ttu-id="8ee4a-125">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="8ee4a-125">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
<span data-ttu-id="8ee4a-126">oppure</span><span class="sxs-lookup"><span data-stu-id="8ee4a-126">or</span></span>
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

## <a name="for-loop"></a><span data-ttu-id="8ee4a-127">Ciclo for</span><span class="sxs-lookup"><span data-stu-id="8ee4a-127">For loop</span></span>

<span data-ttu-id="8ee4a-128">L' `for` istruzione supporta l'iterazione su un intervallo di interi o una matrice.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-128">The `for` statement supports iteration over an integer range or an array.</span></span>
<span data-ttu-id="8ee4a-129">L'istruzione è costituita dalla parola chiave `for` , seguita da un simbolo o da una tupla di simboli, la parola chiave `in` e un'espressione di tipo `Range` o matrice, tutte racchiuse tra parentesi e un blocco di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-129">The statement consists of the keyword `for`, followed by a symbol or symbol tuple, the keyword `in`, and an expression of type `Range` or array, all in parentheses, and a statement block.</span></span>

<span data-ttu-id="8ee4a-130">Il blocco di istruzioni (il corpo del ciclo) viene eseguito ripetutamente, con il simbolo definito (la variabile del ciclo) associato a ogni valore nell'intervallo o nella matrice.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-130">The statement block (the body of the loop) runs repeatedly, with the defined symbol (the loop variable) bound to each value in the range or array.</span></span>
<span data-ttu-id="8ee4a-131">Si noti che se l'espressione di intervallo restituisce un intervallo o una matrice vuota, il corpo non viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-131">Note that if the range expression evaluates to an empty range or array, the body does not run at all.</span></span>
<span data-ttu-id="8ee4a-132">L'espressione viene valutata completamente prima dell'immissione del ciclo e non cambia durante l'esecuzione del ciclo.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-132">The expression is fully evaluated before entering the loop, and does not change while the loop is executing.</span></span>

<span data-ttu-id="8ee4a-133">La variabile di ciclo viene associata a ogni ingresso al corpo del ciclo e non è associata alla fine del corpo.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-133">The loop variable is bound at each entrance to the loop body, and is unbound at the end of the body.</span></span>
<span data-ttu-id="8ee4a-134">La variabile di ciclo non è associata dopo il completamento del ciclo for.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-134">The loop variable is not bound after the for loop is completed.</span></span>
<span data-ttu-id="8ee4a-135">Il binding della variabile del ciclo non è modificabile e segue le stesse regole di altre associazioni variabili.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-135">The binding of the loop variable is immutable and follows the same rules as other variable bindings.</span></span> 

<span data-ttu-id="8ee4a-136">In questi esempi, `qubits` è un registro di qubits (ad esempio, di tipo `Qubit[]` ),</span><span class="sxs-lookup"><span data-stu-id="8ee4a-136">In these examples, `qubits` is a register of qubits (i.e. of type `Qubit[]`),</span></span> 

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

<span data-ttu-id="8ee4a-137">Si noti che alla fine è stato usato l'operatore binario di spostamento a sinistra aritmetico `<<<` .</span><span class="sxs-lookup"><span data-stu-id="8ee4a-137">Note that at the end, we utilized the arithmetic-shift-left binary operator, `<<<`.</span></span> <span data-ttu-id="8ee4a-138">Per altre informazioni, vedere [espressioni numeriche](xref:microsoft.quantum.guide.expressions#numeric-expressions).</span><span class="sxs-lookup"><span data-stu-id="8ee4a-138">For more information, see [Numeric Expressions](xref:microsoft.quantum.guide.expressions#numeric-expressions).</span></span>

## <a name="repeat-until-success-loop"></a><span data-ttu-id="8ee4a-139">Ciclo repeat-until-Success</span><span class="sxs-lookup"><span data-stu-id="8ee4a-139">Repeat-until-success loop</span></span>

<span data-ttu-id="8ee4a-140">Il Q# linguaggio consente a un flusso di controllo classico di dipendere dai risultati della misurazione di qubits.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-140">The Q# language allows classical control flow to depend on the results of measuring qubits.</span></span>
<span data-ttu-id="8ee4a-141">Questa funzionalità consente, a sua volta, di implementare potenti gadget probabilistici che possono ridurre il costo computazionale per l'implementazione di unitaries.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-141">This capability, in turn, enables implementing powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span>
<span data-ttu-id="8ee4a-142">Esempi di questo sono i modelli di *ripetizione fino alla riuscita* (UR) in Q# .</span><span class="sxs-lookup"><span data-stu-id="8ee4a-142">Examples of this are the *repeat-until-success* (RUS) patterns in Q#.</span></span>
<span data-ttu-id="8ee4a-143">Questi modelli di ur sono programmi probabilistici che hanno un costo basso *previsto* in termini di controlli elementari; il costo sostenuto dipende dall'esecuzione effettiva e dall'interfoliazione di più Branch possibili.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-143">These RUS patterns are probabilistic programs that have an *expected* low cost in terms of elementary gates; the incurred cost depends on the actual run and the interleaving of the multiple possible branchings.</span></span>

<span data-ttu-id="8ee4a-144">Per semplificare i modelli di ripetizione fino al completamento (UR), Q# supporta i costrutti</span><span class="sxs-lookup"><span data-stu-id="8ee4a-144">To facilitate repeat-until-success (RUS) patterns, Q# supports the constructs</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression)
fixup {
    // do other stuff
}
```

<span data-ttu-id="8ee4a-145">dove `expression` è qualsiasi espressione valida che restituisce un valore di tipo `Bool` .</span><span class="sxs-lookup"><span data-stu-id="8ee4a-145">where `expression` is any valid expression that evaluates to a value of type `Bool`.</span></span>
<span data-ttu-id="8ee4a-146">Il corpo del ciclo viene eseguito, quindi la condizione viene valutata.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-146">The loop body runs, and then the condition is evaluated.</span></span>
<span data-ttu-id="8ee4a-147">Se la condizione è true, l'istruzione viene completata; in caso contrario, la correzione viene eseguita e l'istruzione viene eseguita nuovamente, a partire dal corpo del ciclo.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-147">If the condition is true, then the statement is completed; otherwise, the fixup runs, and the statement runs again, starting with the loop body.</span></span>

<span data-ttu-id="8ee4a-148">Tutte e tre le parti di un ciclo UR (il corpo, il test e la correzione) vengono trattate come un singolo ambito *per ogni ripetizione*, quindi i simboli associati al corpo sono disponibili sia nel test che nella correzione.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-148">All three portions of an RUS loop (the body, the test, and the fixup) are treated as a single scope *for each repetition*, so symbols that are bound in the body are available in both the test and the fixup.</span></span>
<span data-ttu-id="8ee4a-149">Tuttavia, il completamento dell'esecuzione della correzione termina l'ambito dell'istruzione, in modo che le associazioni di simboli effettuate durante il corpo o la correzione non siano disponibili nelle ripetizioni successive.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-149">However, completing the execution of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="8ee4a-150">Inoltre, l' `fixup` istruzione è spesso utile ma non sempre necessaria.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-150">Further, the `fixup` statement is often useful but not always necessary.</span></span>
<span data-ttu-id="8ee4a-151">Nei casi in cui non è necessario, il costrutto</span><span class="sxs-lookup"><span data-stu-id="8ee4a-151">In cases that it is not needed, the construct</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression);
```

<span data-ttu-id="8ee4a-152">è anche un modello ur valido.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-152">is also a valid RUS pattern.</span></span>

<span data-ttu-id="8ee4a-153">Per altri esempi e dettagli, vedere [esempi di ripetizione fino al](#repeat-until-success-examples) completamento in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-153">For more examples and details, see [Repeat-until-success examples](#repeat-until-success-examples) in this article.</span></span>

> [!TIP]   
> <span data-ttu-id="8ee4a-154">Evitare l'utilizzo di cicli repeat-until-Success all'interno di funzioni.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-154">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="8ee4a-155">Usare i cicli *while* per fornire la funzionalità corrispondente all'interno di funzioni.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-155">Use *while* loops to provide the corresponding functionality inside functions.</span></span> 

## <a name="while-loop"></a><span data-ttu-id="8ee4a-156">Ciclo while</span><span class="sxs-lookup"><span data-stu-id="8ee4a-156">While loop</span></span>

<span data-ttu-id="8ee4a-157">I modelli repeat-until-Success hanno una connotazione molto specifica del quantum.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-157">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="8ee4a-158">Sono ampiamente usati in particolari classi di algoritmi quantistici, quindi il costrutto di linguaggio dedicato in Q# .</span><span class="sxs-lookup"><span data-stu-id="8ee4a-158">They are widely used in particular classes of quantum algorithms - hence the dedicated language construct in Q#.</span></span> <span data-ttu-id="8ee4a-159">Tuttavia, i cicli che si interrompono in base a una condizione e la cui lunghezza di esecuzione è sconosciuta in fase di compilazione, vengono gestiti con particolare attenzione in un runtime Quantum.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-159">However, loops that break based on a condition and whose execution length is thus unknown at compile-time, are handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="8ee4a-160">Tuttavia, l'uso all'interno delle funzioni non è problematico perché questi cicli contengono solo codice eseguito su hardware convenzionale (non Quantum).</span><span class="sxs-lookup"><span data-stu-id="8ee4a-160">However, their use within functions is unproblematic since these loops only contain code that runs on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="8ee4a-161">Q#, pertanto, supporta l'utilizzo di cicli while solo all'interno di funzioni.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-161">Q#, therefore, supports to use of while loops within functions only.</span></span> <span data-ttu-id="8ee4a-162">Un' `while` istruzione è costituita dalla parola chiave `while` , da un'espressione booleana tra parentesi e da un blocco di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-162">A `while` statement consists of the keyword `while`, a Boolean expression in parentheses, and a statement block.</span></span>
<span data-ttu-id="8ee4a-163">Il blocco di istruzioni (il corpo del ciclo) viene eseguito fino a quando la condizione restituisce `true` .</span><span class="sxs-lookup"><span data-stu-id="8ee4a-163">The statement block (the body of the loop) runs as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

## <a name="return-statement"></a><span data-ttu-id="8ee4a-164">Istruzione Return</span><span class="sxs-lookup"><span data-stu-id="8ee4a-164">Return Statement</span></span>

<span data-ttu-id="8ee4a-165">L'istruzione return termina l'esecuzione di un'operazione o di una funzione e restituisce un valore al chiamante.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-165">The return statement ends the run of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="8ee4a-166">È costituito dalla parola chiave `return` , seguita da un'espressione del tipo appropriato e da un punto e virgola di terminazione.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-166">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="8ee4a-167">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="8ee4a-167">For example,</span></span>
```qsharp
return 1;
```
<span data-ttu-id="8ee4a-168">oppure</span><span class="sxs-lookup"><span data-stu-id="8ee4a-168">or</span></span>
```qsharp
return (results, qubits);
```

* <span data-ttu-id="8ee4a-169">Un oggetto chiamabile che restituisce una tupla vuota, `()` , non richiede un'istruzione return.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-169">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
* <span data-ttu-id="8ee4a-170">Per specificare una prima uscita dall'operazione o dalla funzione, usare `return ();` .</span><span class="sxs-lookup"><span data-stu-id="8ee4a-170">To specify an early exit from the operation or function, use `return ();`.</span></span>
<span data-ttu-id="8ee4a-171">Le Callable che restituiscono qualsiasi altro tipo richiedono un'istruzione return finale.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-171">Callables that return any other type require a final return statement.</span></span>
* <span data-ttu-id="8ee4a-172">Non esiste un numero massimo di istruzioni return all'interno di un'operazione.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-172">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="8ee4a-173">Il compilatore può generare un avviso se le istruzioni seguono un'istruzione return all'interno di un blocco.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-173">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

   
## <a name="fail-statement"></a><span data-ttu-id="8ee4a-174">Istruzione Fail</span><span class="sxs-lookup"><span data-stu-id="8ee4a-174">Fail statement</span></span>

<span data-ttu-id="8ee4a-175">L'istruzione Fail termina l'esecuzione di un'operazione e restituisce un valore di errore al chiamante.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-175">The fail statement ends the run of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="8ee4a-176">È costituito dalla parola chiave `fail` , seguita da una stringa e da un punto e virgola di terminazione.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-176">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="8ee4a-177">L'istruzione restituisce la stringa al driver classico come messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-177">The statement returns the string to the classical driver as the error message.</span></span>

<span data-ttu-id="8ee4a-178">Non esiste alcuna restrizione sul numero di istruzioni fail in un'operazione.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-178">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="8ee4a-179">Il compilatore può generare un avviso se le istruzioni seguono un'istruzione Fail all'interno di un blocco.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-179">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="8ee4a-180">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="8ee4a-180">For example,</span></span>

```qsharp
fail $"Impossible state reached";
```
<span data-ttu-id="8ee4a-181">oppure, usando [stringhe interpolate](xref:microsoft.quantum.guide.expressions#interpolated-strings),</span><span class="sxs-lookup"><span data-stu-id="8ee4a-181">or, using [interpolated strings](xref:microsoft.quantum.guide.expressions#interpolated-strings),</span></span>
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a><span data-ttu-id="8ee4a-182">Esempi di ripetizione fino al completamento</span><span class="sxs-lookup"><span data-stu-id="8ee4a-182">Repeat-until-success examples</span></span>

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a><span data-ttu-id="8ee4a-183">Modello ur per la rotazione a qubit singolo su un asse irrazionale</span><span class="sxs-lookup"><span data-stu-id="8ee4a-183">RUS pattern for single-qubit rotation about an irrational axis</span></span> 

<span data-ttu-id="8ee4a-184">In un caso di utilizzo tipico, l' Q# operazione seguente implementa una rotazione intorno a un asse irrazionale di $ (I + 2i Z)/\sqrt {5} $ sulla sfera Bloch.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-184">In a typical use case, the following Q# operation implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="8ee4a-185">L'implementazione usa un modello di ur noto:</span><span class="sxs-lookup"><span data-stu-id="8ee4a-185">The implementation uses a known RUS pattern:</span></span>

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

### <a name="rus-loop-with-a-mutable-variable-in-scope"></a><span data-ttu-id="8ee4a-186">Ciclo ur con una variabile modificabile nell'ambito</span><span class="sxs-lookup"><span data-stu-id="8ee4a-186">RUS loop with a mutable variable in scope</span></span>

<span data-ttu-id="8ee4a-187">Questo esempio illustra l'uso di una variabile modificabile, `finished` , che rientra nell'ambito dell'intero ciclo di ripetizione fino alla correzione e che viene inizializzato prima del ciclo e aggiornato nel passaggio di correzione.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-187">This example shows the use of a mutable variable, `finished`, which is within the scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

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

### <a name="rus-without-fixup"></a><span data-ttu-id="8ee4a-188">UR senza `fixup`</span><span class="sxs-lookup"><span data-stu-id="8ee4a-188">RUS without `fixup`</span></span>

<span data-ttu-id="8ee4a-189">Questo esempio mostra un ciclo UR senza il passaggio di correzione.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-189">This example shows an RUS loop without the fixup step.</span></span> <span data-ttu-id="8ee4a-190">Il codice è un circuito probabilistico che implementa un gate di rotazione importante $V _3 = (\boldone + 2 i Z)/\sqrt {5} $ usando le attività `H` di controllo e `T` .</span><span class="sxs-lookup"><span data-stu-id="8ee4a-190">The code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the `H` and `T` gates.</span></span>
<span data-ttu-id="8ee4a-191">Il ciclo termina in media le ripetizioni di $ \frac {8} {5} $.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-191">The loop terminates in $\frac{8}{5}$ repetitions on average.</span></span>
<span data-ttu-id="8ee4a-192">Per informazioni dettagliate, vedere [*repeat-until-Success: scomposizione non deterministica di single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Papini e Svore, 2014).</span><span class="sxs-lookup"><span data-stu-id="8ee4a-192">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for more details.</span></span>

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

### <a name="rus-to-prepare-a-quantum-state"></a><span data-ttu-id="8ee4a-193">UR per preparare uno stato quantico</span><span class="sxs-lookup"><span data-stu-id="8ee4a-193">RUS to prepare a quantum state</span></span>

<span data-ttu-id="8ee4a-194">Infine, di seguito è riportato un esempio di modello ur per preparare uno stato quantico $ \frac {1} {\sqrt {3} } \left (\sqrt {2} \ket {0} + \ket {1} \right) $, a partire dallo stato $ \ket{+} $.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-194">Finally, here is an example of an RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span>

<span data-ttu-id="8ee4a-195">Le funzionalità a livello di codice indicate in questa operazione sono:</span><span class="sxs-lookup"><span data-stu-id="8ee4a-195">Notable programmatic features shown in this operation are:</span></span>

* <span data-ttu-id="8ee4a-196">Parte più complessa `fixup` del ciclo, che implica operazioni Quantum.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-196">A more complex `fixup` part of the loop, which involves quantum operations.</span></span> 
* <span data-ttu-id="8ee4a-197">Utilizzo di `AssertMeasurementProbability` istruzioni per verificare la probabilità di misurare lo stato del quantum in determinati punti specificati del programma.</span><span class="sxs-lookup"><span data-stu-id="8ee4a-197">The use of `AssertMeasurementProbability` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span>

<span data-ttu-id="8ee4a-198">Per ulteriori informazioni sulle [`AssertMeasurement`](xref:microsoft.quantum.diagnostics.assertmeasurement) operazioni e [`AssertMeasurementProbability`](xref:microsoft.quantum.diagnostics.assertmeasurementprobability) , vedere [testing and Debugging](xref:microsoft.quantum.guide.testingdebugging).</span><span class="sxs-lookup"><span data-stu-id="8ee4a-198">For more information about the [`AssertMeasurement`](xref:microsoft.quantum.diagnostics.assertmeasurement) and [`AssertMeasurementProbability`](xref:microsoft.quantum.diagnostics.assertmeasurementprobability) operations, see [Testing and debugging](xref:microsoft.quantum.guide.testingdebugging).</span></span>

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

<span data-ttu-id="8ee4a-199">Per ulteriori informazioni, vedere [l'esempio di unit test fornito con la libreria standard](https://github.com/microsoft/Quantum/blob/main/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span><span class="sxs-lookup"><span data-stu-id="8ee4a-199">For more information, see [unit testing sample provided with the standard library](https://github.com/microsoft/Quantum/blob/main/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span></span>

## <a name="next-steps"></a><span data-ttu-id="8ee4a-200">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="8ee4a-200">Next steps</span></span>

<span data-ttu-id="8ee4a-201">Informazioni sul [test e il debug](xref:microsoft.quantum.guide.testingdebugging) in Q# .</span><span class="sxs-lookup"><span data-stu-id="8ee4a-201">Learn about [Testing and Debugging](xref:microsoft.quantum.guide.testingdebugging) in Q#.</span></span>
