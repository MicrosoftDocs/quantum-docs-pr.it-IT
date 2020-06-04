---
title: 'Flusso di controllo in Q #'
description: Cicli, condizionali e così via
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
ms.openlocfilehash: 1f1b641563fe35879abeee32b4f0aeeb7001b1a0
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2020
ms.locfileid: "84326541"
---
# <a name="control-flow-in-q"></a><span data-ttu-id="dd249-103">Flusso di controllo in Q #</span><span class="sxs-lookup"><span data-stu-id="dd249-103">Control Flow in Q#</span></span>

<span data-ttu-id="dd249-104">All'interno di un'operazione o di una funzione, ogni istruzione viene eseguita in ordine, in modo analogo ai linguaggi classici imperativi più comuni.</span><span class="sxs-lookup"><span data-stu-id="dd249-104">Within an operation or function, each statement executes in order, similar to most common imperative classical languages.</span></span>
<span data-ttu-id="dd249-105">Questo flusso di controllo può tuttavia essere modificato in tre modi distinti:</span><span class="sxs-lookup"><span data-stu-id="dd249-105">This flow of control can be modified, however, in three distinct ways:</span></span>

- <span data-ttu-id="dd249-106">`if`istruzioni</span><span class="sxs-lookup"><span data-stu-id="dd249-106">`if` statements</span></span>
- <span data-ttu-id="dd249-107">`for`cicli</span><span class="sxs-lookup"><span data-stu-id="dd249-107">`for` loops</span></span>
- <span data-ttu-id="dd249-108">`repeat`-`until`cicli</span><span class="sxs-lookup"><span data-stu-id="dd249-108">`repeat`-`until` loops</span></span>

<span data-ttu-id="dd249-109">Il secondo argomento è rinviato a quanto [segue](#repeat-until-success-loop).</span><span class="sxs-lookup"><span data-stu-id="dd249-109">We defer discussion of the latter to further [below](#repeat-until-success-loop).</span></span>
<span data-ttu-id="dd249-110">I `if` `for` costrutti del flusso di controllo e, tuttavia, procedono in un senso familiare alla maggior parte dei linguaggi di programmazione classici.</span><span class="sxs-lookup"><span data-stu-id="dd249-110">The `if` and `for` control flow constructs, however, proceed in a familiar sense to most classical programming languages.</span></span>

<span data-ttu-id="dd249-111">In particolare, `for` `if` è possibile utilizzare cicli e istruzioni anche in operazioni per le quali le specializzazioni vengono generate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="dd249-111">Importantly, `for` loops and `if` statements can even be used in operations for which specializations are auto-generated.</span></span> <span data-ttu-id="dd249-112">In tal caso, l'oggetto adiacente di un `for` ciclo inverte la direzione e accetta il contiguo di ogni iterazione.</span><span class="sxs-lookup"><span data-stu-id="dd249-112">In that case the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="dd249-113">Segue il principio "Shoes-and-Socks": se si vuole annullare la messa a punto dei calzini e quindi delle scarpe, è necessario annullare le calzature e quindi annullare l'inserimento dei calzini.</span><span class="sxs-lookup"><span data-stu-id="dd249-113">This follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span>
<span data-ttu-id="dd249-114">Si tratta di un approccio decisamente meno efficace per provare a riportare i calzini quando si indossano ancora le scarpe.</span><span class="sxs-lookup"><span data-stu-id="dd249-114">It works decidedly less well to try and take your socks off while you're still wearing your shoes!</span></span>

## <a name="if-else-if-else"></a><span data-ttu-id="dd249-115">Se, else-if, else</span><span class="sxs-lookup"><span data-stu-id="dd249-115">If, Else-if, Else</span></span>

<span data-ttu-id="dd249-116">L' `if` istruzione supporta l'esecuzione condizionale.</span><span class="sxs-lookup"><span data-stu-id="dd249-116">The `if` statement supports conditional execution.</span></span>
<span data-ttu-id="dd249-117">È costituito dalla parola chiave, da una `if` parentesi aperta, da un' `(` espressione booleana, da una parentesi di chiusura `)` e da un blocco di istruzioni (il blocco _then_ ).</span><span class="sxs-lookup"><span data-stu-id="dd249-117">It consists of the keyword `if`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="dd249-118">Questo può essere seguito da un numero qualsiasi di clausole else-if, ciascuna delle quali è costituita dalla parola chiave, da una `elif` parentesi aperta, da un' `(` espressione booleana, da una parentesi di chiusura `)` e da un blocco di istruzioni (il blocco _else-if_ ).</span><span class="sxs-lookup"><span data-stu-id="dd249-118">This may be followed by any number of else-if clauses, each of which consists of the keyword `elif`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="dd249-119">Infine, l'istruzione può terminare facoltativamente con una clausola else, che è costituita dalla parola chiave `else` seguita da un altro blocco Statement (il blocco _else_ ).</span><span class="sxs-lookup"><span data-stu-id="dd249-119">Finally, the statement may optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>

<span data-ttu-id="dd249-120">La `if` condizione viene valutata e, se è true, il blocco then viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="dd249-120">The `if` condition is evaluated, and if it is true, the then block is executed.</span></span>
<span data-ttu-id="dd249-121">Se la condizione è false, viene valutata la prima condizione else-if; Se è true, il blocco else-if viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="dd249-121">If the condition is false, then the first else-if condition is evaluated; if it is true, that else-if block is executed.</span></span>
<span data-ttu-id="dd249-122">In caso contrario, viene testato il secondo blocco else-if, quindi il terzo e così via fino a quando non viene rilevata una clausola con una condizione true o non sono presenti altre clausole else-if.</span><span class="sxs-lookup"><span data-stu-id="dd249-122">Otherwise, the second else-if block is tested, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="dd249-123">Se la condizione if originale e tutte le clausole else-if restituiscono false, il blocco Else viene eseguito se ne è stato fornito uno.</span><span class="sxs-lookup"><span data-stu-id="dd249-123">If the original if condition and all else-if clauses evaluate to false, the else block is executed if one was provided.</span></span>

<span data-ttu-id="dd249-124">Si noti che qualsiasi blocco eseguito viene eseguito nel proprio ambito.</span><span class="sxs-lookup"><span data-stu-id="dd249-124">Note that whichever block is executed is executed in its own scope.</span></span>
<span data-ttu-id="dd249-125">Le associazioni eseguite all'interno di `if` un `elif` blocco, o `else` non sono visibili dopo la relativa fine.</span><span class="sxs-lookup"><span data-stu-id="dd249-125">Bindings made inside of an `if`, `elif`, or `else` block are not visible after its end.</span></span>

<span data-ttu-id="dd249-126">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="dd249-126">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
<span data-ttu-id="dd249-127">Oppure</span><span class="sxs-lookup"><span data-stu-id="dd249-127">or</span></span>
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

## <a name="for-loop"></a><span data-ttu-id="dd249-128">Ciclo For</span><span class="sxs-lookup"><span data-stu-id="dd249-128">For Loop</span></span>

<span data-ttu-id="dd249-129">L' `for` istruzione supporta l'iterazione su un intervallo di interi o su una matrice.</span><span class="sxs-lookup"><span data-stu-id="dd249-129">The `for` statement supports iteration over an integer range or over an array.</span></span>
<span data-ttu-id="dd249-130">L'istruzione è costituita dalla parola chiave, da una `for` parentesi aperta `(` , seguita da un simbolo o da una tupla di simboli, dalla parola chiave `in` , da un'espressione di tipo `Range` o matrice, da una parentesi di chiusura `)` e da un blocco di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="dd249-130">The statement consists of the keyword `for`, an open parenthesis `(`, followed by a symbol or symbol tuple, the keyword `in`, an expression of type `Range` or array, a close parenthesis `)`, and a statement block.</span></span>

<span data-ttu-id="dd249-131">Il blocco di istruzioni (il corpo del ciclo) viene eseguito ripetutamente con i simboli definiti (le variabili del ciclo) associati a ogni valore nell'intervallo o nella matrice.</span><span class="sxs-lookup"><span data-stu-id="dd249-131">The statement block (the body of the loop) is executed repeatedly, with the defined symbol(s) (the loop variable(s)) bound to each value in the range or array.</span></span>
<span data-ttu-id="dd249-132">Si noti che se l'espressione di intervallo restituisce un intervallo o una matrice vuota, il corpo non verrà eseguito affatto.</span><span class="sxs-lookup"><span data-stu-id="dd249-132">Note that if the range expression evaluates to an empty range or array, the body will not be executed at all.</span></span>
<span data-ttu-id="dd249-133">L'espressione viene valutata completamente prima dell'immissione del ciclo e non verrà modificata durante l'esecuzione del ciclo.</span><span class="sxs-lookup"><span data-stu-id="dd249-133">The expression is fully evaluated before entering the loop, and will not change while the loop is executing.</span></span>

<span data-ttu-id="dd249-134">La variabile del ciclo è associata a ogni ingresso al corpo del ciclo e non è associata alla fine del corpo.</span><span class="sxs-lookup"><span data-stu-id="dd249-134">The loop variable is bound at each entrance to the loop body, and unbound at the end of the body.</span></span>
<span data-ttu-id="dd249-135">In particolare, la variabile di ciclo non è associata dopo il completamento del ciclo for.</span><span class="sxs-lookup"><span data-stu-id="dd249-135">In particular, the loop variable is not bound after the for loop is completed.</span></span>
<span data-ttu-id="dd249-136">L'associazione dei simboli dichiarati non è modificabile e segue le stesse regole di altre associazioni variabili.</span><span class="sxs-lookup"><span data-stu-id="dd249-136">The binding of the declared symbol(s) is immutable and follows the same rules as other variable bindings.</span></span> 

<span data-ttu-id="dd249-137">Per alcuni esempi, supponendo che `qubits` sia un registro di qubits (ad esempio, di tipo `Qubit[]` ),</span><span class="sxs-lookup"><span data-stu-id="dd249-137">For some examples, supposing `qubits` is a register of qubits (i.e. of type `Qubit[]`),</span></span> 

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
<span data-ttu-id="dd249-138">Si noti che alla fine è stato utilizzato l'operatore Binary-Shift-Left Binary, `<<<` , i cui dettagli sono reperibili in [espressioni numeriche](xref:microsoft.quantum.guide.expressions#numeric-expressions)</span><span class="sxs-lookup"><span data-stu-id="dd249-138">Note that at the end we utilized the arithmetic-shift-left binary operator, `<<<`, details of which can be found at [Numeric Expressions](xref:microsoft.quantum.guide.expressions#numeric-expressions)</span></span>


## <a name="repeat-until-success-loop"></a><span data-ttu-id="dd249-139">Ciclo repeat-until-Success</span><span class="sxs-lookup"><span data-stu-id="dd249-139">Repeat-Until-Success Loop</span></span>

<span data-ttu-id="dd249-140">Il linguaggio Q # consente a un flusso di controllo classico di dipendere dai risultati della misurazione di qubits.</span><span class="sxs-lookup"><span data-stu-id="dd249-140">The Q# language allows classical control flow to depend on the results of measuring qubits.</span></span>
<span data-ttu-id="dd249-141">Questa funzionalità consente, a sua volta, di implementare potenti gadget probabilistici che possono ridurre il costo computazionale per l'implementazione di unitaries.</span><span class="sxs-lookup"><span data-stu-id="dd249-141">This capability in turn enables implementing powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span>
<span data-ttu-id="dd249-142">Ad esempio, è facile implementare i cosiddetti modelli di *ripetizione fino al successo* (UR) in Q #.</span><span class="sxs-lookup"><span data-stu-id="dd249-142">As an example, it is easy to implement so-called *Repeat-Until-Success* (RUS) patterns in Q#.</span></span>
<span data-ttu-id="dd249-143">Questi modelli di ur sono programmi probabilistici che hanno un basso costo *previsto* in termini di attività di controllo elementari, ma per il quale il costo effettivo dipende da un'esecuzione effettiva e da un effettivo interfoliazione delle diverse branche possibili.</span><span class="sxs-lookup"><span data-stu-id="dd249-143">These RUS patterns are probabilistic programs that have an *expected* low cost in terms of elementary gates, but for which the true cost depends on an actual run and an actual interleaving of various possible branchings.</span></span>

<span data-ttu-id="dd249-144">Per semplificare i modelli di ripetizione fino alla riuscita (UR), Q # supporta i costrutti</span><span class="sxs-lookup"><span data-stu-id="dd249-144">To facilitate Repeat-Until-Success (RUS) patterns, Q# supports the constructs</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression)
fixup {
    // do other stuff
}
```

<span data-ttu-id="dd249-145">dove `expression` è qualsiasi espressione valida che restituisce un valore di tipo `Bool` .</span><span class="sxs-lookup"><span data-stu-id="dd249-145">where `expression` is any valid expression that evaluates to a value of type `Bool`.</span></span>
<span data-ttu-id="dd249-146">Il corpo del ciclo viene eseguito, quindi la condizione viene valutata.</span><span class="sxs-lookup"><span data-stu-id="dd249-146">The loop body is executed, and then the condition is evaluated.</span></span>
<span data-ttu-id="dd249-147">Se la condizione è true, l'istruzione viene completata; in caso contrario, la correzione viene eseguita e l'istruzione viene eseguita di nuovo a partire dal corpo del ciclo.</span><span class="sxs-lookup"><span data-stu-id="dd249-147">If the condition is true, then the statement is completed; otherwise, the fixup is executed, and the statement is re-executed starting with the loop body.</span></span>

<span data-ttu-id="dd249-148">Tutte e tre le parti di un ciclo repeat/until (il corpo, il test e la correzione) vengono considerate come un singolo ambito *per ogni ripetizione*, quindi i simboli associati al corpo sono disponibili nel test e nella correzione.</span><span class="sxs-lookup"><span data-stu-id="dd249-148">All three portions of a repeat/until loop (the body, the test, and the fixup) are treated as a single scope *for each repetition*, so symbols that are bound in the body are available in the test and in the fixup.</span></span>
<span data-ttu-id="dd249-149">Il completamento dell'esecuzione della correzione termina tuttavia l'ambito dell'istruzione, in modo che le associazioni di simboli effettuate durante il corpo o la correzione non siano disponibili nelle ripetizioni successive.</span><span class="sxs-lookup"><span data-stu-id="dd249-149">However completing the execution of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="dd249-150">Inoltre, l' `fixup` istruzione è spesso utile ma non sempre necessaria.</span><span class="sxs-lookup"><span data-stu-id="dd249-150">Further, the `fixup` statement is often useful but not always necessary.</span></span>
<span data-ttu-id="dd249-151">Nei casi in cui non è necessario, il costrutto</span><span class="sxs-lookup"><span data-stu-id="dd249-151">In cases that it is not needed, the construct</span></span>
```qsharp
repeat {
    // do stuff
}
until (expression);
```
<span data-ttu-id="dd249-152">è anche un modello ur valido.</span><span class="sxs-lookup"><span data-stu-id="dd249-152">is also a valid RUS pattern.</span></span>

<span data-ttu-id="dd249-153">Nella parte inferiore della pagina vengono presentati alcuni [esempi di cicli ur](#repeat-until-success-examples).</span><span class="sxs-lookup"><span data-stu-id="dd249-153">At the bottom of this page we present some [examples of RUS loops](#repeat-until-success-examples).</span></span>

> [!TIP]   
> <span data-ttu-id="dd249-154">Evitare l'utilizzo di cicli repeat-until-Success all'interno di funzioni.</span><span class="sxs-lookup"><span data-stu-id="dd249-154">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="dd249-155">La funzionalità corrispondente viene fornita dai cicli while nelle funzioni.</span><span class="sxs-lookup"><span data-stu-id="dd249-155">The corresponding functionality is provided by while loops in functions.</span></span> 

## <a name="while-loop"></a><span data-ttu-id="dd249-156">Ciclo while</span><span class="sxs-lookup"><span data-stu-id="dd249-156">While Loop</span></span>

<span data-ttu-id="dd249-157">I modelli repeat-until-Success hanno una connotazione molto specifica del quantum.</span><span class="sxs-lookup"><span data-stu-id="dd249-157">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="dd249-158">Sono ampiamente usati in particolari classi di algoritmi quantistici, di conseguenza il costrutto di linguaggio dedicato in Q #.</span><span class="sxs-lookup"><span data-stu-id="dd249-158">They are widely used in particular classes of quantum algorithms -- hence the dedicated language construct in Q#.</span></span> <span data-ttu-id="dd249-159">Tuttavia, i cicli che si interrompono in base a una condizione e la cui lunghezza di esecuzione risultano pertanto sconosciuti in fase di compilazione devono essere gestiti con particolare attenzione in un runtime Quantum.</span><span class="sxs-lookup"><span data-stu-id="dd249-159">However, loops that break based on a condition and whose execution length is thus unknown at compile time need to be handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="dd249-160">Il loro utilizzo all'interno delle funzioni non è problematico, dal momento che contengono solo codice che verrà eseguito su hardware convenzionale (non Quantum).</span><span class="sxs-lookup"><span data-stu-id="dd249-160">Their use within functions on the other hand is unproblematic, since these only contain code that will be executed on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="dd249-161">Q # supporta pertanto l'utilizzo dei cicli while solo all'interno di funzioni.</span><span class="sxs-lookup"><span data-stu-id="dd249-161">Q# therefore supports to use of while loops within functions only.</span></span> <span data-ttu-id="dd249-162">Un' `while` istruzione è costituita dalla parola chiave, da una `while` parentesi aperta, da una `(` condizione (ovvero un'espressione booleana), da una parentesi di chiusura `)` e da un blocco di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="dd249-162">A `while` statement consists of the keyword `while`, an open parenthesis `(`, a condition (i.e. a Boolean expression), a close parenthesis `)`, and a statement block.</span></span>
<span data-ttu-id="dd249-163">Il blocco di istruzioni (il corpo del ciclo) viene eseguito finché la condizione restituisce `true` .</span><span class="sxs-lookup"><span data-stu-id="dd249-163">The statement block (the body of the loop) is executed as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```


## <a name="return-statement"></a><span data-ttu-id="dd249-164">Istruzione Return</span><span class="sxs-lookup"><span data-stu-id="dd249-164">Return Statement</span></span>

<span data-ttu-id="dd249-165">L'istruzione return termina l'esecuzione di un'operazione o di una funzione e restituisce un valore al chiamante.</span><span class="sxs-lookup"><span data-stu-id="dd249-165">The return statement ends execution of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="dd249-166">È costituito dalla parola chiave `return` , seguita da un'espressione del tipo appropriato e da un punto e virgola di terminazione.</span><span class="sxs-lookup"><span data-stu-id="dd249-166">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="dd249-167">Un oggetto chiamabile che restituisce una tupla vuota, `()` , non richiede un'istruzione return.</span><span class="sxs-lookup"><span data-stu-id="dd249-167">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
<span data-ttu-id="dd249-168">Se si desidera una prima uscita, è `return ()` possibile utilizzare in questo caso.</span><span class="sxs-lookup"><span data-stu-id="dd249-168">If an early exit is desired, `return ()` may be used in this case.</span></span>
<span data-ttu-id="dd249-169">Le Callable che restituiscono qualsiasi altro tipo richiedono un'istruzione return finale.</span><span class="sxs-lookup"><span data-stu-id="dd249-169">Callables that return any other type require a final return statement.</span></span>

<span data-ttu-id="dd249-170">Non esiste un numero massimo di istruzioni return all'interno di un'operazione.</span><span class="sxs-lookup"><span data-stu-id="dd249-170">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="dd249-171">Il compilatore può generare un avviso se le istruzioni seguono un'istruzione return all'interno di un blocco.</span><span class="sxs-lookup"><span data-stu-id="dd249-171">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

<span data-ttu-id="dd249-172">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="dd249-172">For example,</span></span>
```qsharp
return 1;
```
<span data-ttu-id="dd249-173">Oppure</span><span class="sxs-lookup"><span data-stu-id="dd249-173">or</span></span>
```qsharp
return ();
```
<span data-ttu-id="dd249-174">Oppure</span><span class="sxs-lookup"><span data-stu-id="dd249-174">or</span></span>
```qsharp
return (results, qubits);
```

## <a name="fail-statement"></a><span data-ttu-id="dd249-175">Istruzione Fail</span><span class="sxs-lookup"><span data-stu-id="dd249-175">Fail Statement</span></span>

<span data-ttu-id="dd249-176">L'istruzione Fail termina l'esecuzione di un'operazione e restituisce un valore di errore al chiamante.</span><span class="sxs-lookup"><span data-stu-id="dd249-176">The fail statement ends execution of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="dd249-177">È costituito dalla parola chiave `fail` , seguita da una stringa e da un punto e virgola di terminazione.</span><span class="sxs-lookup"><span data-stu-id="dd249-177">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="dd249-178">La stringa viene restituita al driver classico come messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="dd249-178">The string is returned to the classical driver as the error message.</span></span>

<span data-ttu-id="dd249-179">Non esiste alcuna restrizione sul numero di istruzioni fail in un'operazione.</span><span class="sxs-lookup"><span data-stu-id="dd249-179">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="dd249-180">Il compilatore può generare un avviso se le istruzioni seguono un'istruzione Fail all'interno di un blocco.</span><span class="sxs-lookup"><span data-stu-id="dd249-180">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="dd249-181">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="dd249-181">For example,</span></span>
```qsharp
fail $"Impossible state reached";
```
<span data-ttu-id="dd249-182">oppure, usando [stringhe interpolate](xref:microsoft.quantum.guide.expressions#interpolated-strings),</span><span class="sxs-lookup"><span data-stu-id="dd249-182">or, using [interpolated strings](xref:microsoft.quantum.guide.expressions#interpolated-strings),</span></span>
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a><span data-ttu-id="dd249-183">Esempi di ripetizione fino al completamento</span><span class="sxs-lookup"><span data-stu-id="dd249-183">Repeat-Until-Success Examples</span></span>

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a><span data-ttu-id="dd249-184">Modello ur per la rotazione di una singola qubit su un asse irrazionale</span><span class="sxs-lookup"><span data-stu-id="dd249-184">RUS pattern for single qubit rotation about an irrational axis</span></span> 

<span data-ttu-id="dd249-185">In un caso di utilizzo tipico, l'operazione Q # seguente implementa una rotazione intorno a un asse irrazionale di $ (I + 2i Z)/\sqrt {5} $ sulla sfera Bloch.</span><span class="sxs-lookup"><span data-stu-id="dd249-185">In a typical use case, the following Q# operation implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="dd249-186">Questa operazione viene eseguita usando un modello di ur noto:</span><span class="sxs-lookup"><span data-stu-id="dd249-186">This is accomplished by using a known RUS pattern:</span></span>

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

### <a name="rus-loop-with-mutable-variable-in-scope"></a><span data-ttu-id="dd249-187">Ciclo ur con variabile modificabile nell'ambito</span><span class="sxs-lookup"><span data-stu-id="dd249-187">RUS loop with mutable variable in scope</span></span>

<span data-ttu-id="dd249-188">Questo esempio illustra l'uso di una variabile modificabile `finished` che rientra nell'ambito dell'intero ciclo di ripetizione fino alla correzione e che viene inizializzata prima del ciclo e aggiornata nel passaggio di correzione.</span><span class="sxs-lookup"><span data-stu-id="dd249-188">This example shows the use of a mutable variable `finished` which is in scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

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

### <a name="rus-without-fixup"></a><span data-ttu-id="dd249-189">UR senza`fixup`</span><span class="sxs-lookup"><span data-stu-id="dd249-189">RUS without `fixup`</span></span>

<span data-ttu-id="dd249-190">Il codice seguente, ad esempio, è un circuito probabilistico che implementa un gate di rotazione importante $V _3 = (\boldone + 2 i Z)/\sqrt {5} $ usando le attività `H` di controllo e `T` .</span><span class="sxs-lookup"><span data-stu-id="dd249-190">For example, the following code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the `H` and `T` gates.</span></span>
<span data-ttu-id="dd249-191">Il ciclo termina in media le ripetizioni di $ \frac {8} {5} $.</span><span class="sxs-lookup"><span data-stu-id="dd249-191">The loop terminates in $\frac{8}{5}$ repetitions on average.</span></span>
<span data-ttu-id="dd249-192">Per informazioni dettagliate, vedere [*repeat-until-Success: scomposizione non deterministica di single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Papini e Svore, 2014).</span><span class="sxs-lookup"><span data-stu-id="dd249-192">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for more details.</span></span>

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

### <a name="rus-to-prepare-a-quantum-state"></a><span data-ttu-id="dd249-193">UR per preparare uno stato quantico</span><span class="sxs-lookup"><span data-stu-id="dd249-193">RUS to prepare a quantum state</span></span>

<span data-ttu-id="dd249-194">Infine, viene illustrato un esempio di modello ur per preparare uno stato quantico $ \frac {1} {\sqrt {3} } \left (\sqrt {2} \ket {0} + \ket {1} \right) $, a partire dallo stato $ \ket{+} $.</span><span class="sxs-lookup"><span data-stu-id="dd249-194">Finally, we show an example of a RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span>
<span data-ttu-id="dd249-195">Vedere anche l' [esempio di unit test fornito con la libreria standard](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span><span class="sxs-lookup"><span data-stu-id="dd249-195">See also the [unit testing sample provided with the standard library](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span></span>

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertProb(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertProb(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertProb(
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

<span data-ttu-id="dd249-196">Le caratteristiche programmatiche più importanti illustrate in questa operazione sono una parte più complessa `fixup` del ciclo, che include le operazioni Quantum e l'utilizzo di `AssertProb` istruzioni per verificare la probabilità di misurare lo stato del quantum in determinati punti specificati del programma.</span><span class="sxs-lookup"><span data-stu-id="dd249-196">Notable programmatic features shown in this operation are a more complex `fixup` part of the loop, which involves quantum operations, and the use of `AssertProb` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span>
<span data-ttu-id="dd249-197">Per ulteriori informazioni sulle operazioni e, vedere anche [test e debug](xref:microsoft.quantum.guide.testingdebugging) [`Assert`](xref:microsoft.quantum.intrinsic.assert) [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) .</span><span class="sxs-lookup"><span data-stu-id="dd249-197">See also [Testing and debugging](xref:microsoft.quantum.guide.testingdebugging) for more information about the [`Assert`](xref:microsoft.quantum.intrinsic.assert) and [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) operations.</span></span>


## <a name="next-steps"></a><span data-ttu-id="dd249-198">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="dd249-198">Next steps</span></span>

<span data-ttu-id="dd249-199">Informazioni sul [test e il debug](xref:microsoft.quantum.guide.testingdebugging) in Q #.</span><span class="sxs-lookup"><span data-stu-id="dd249-199">Learn about [Testing and Debugging](xref:microsoft.quantum.guide.testingdebugging) in Q#.</span></span>