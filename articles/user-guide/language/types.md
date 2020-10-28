---
title: 'Tipi in :::no-loc(Q#):::'
description: 'Informazioni sui diversi tipi usati nel linguaggio di :::no-loc(Q#)::: programmazione.'
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: 349138984387cc564cca18ea09c7bf161524b0b6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691611"
---
# <a name="types-in-no-locq"></a><span data-ttu-id="58018-103">Tipi in :::no-loc(Q#):::</span><span class="sxs-lookup"><span data-stu-id="58018-103">Types in :::no-loc(Q#):::</span></span>

<span data-ttu-id="58018-104">Questo articolo descrive il :::no-loc(Q#)::: modello di tipo e la sintassi per specificare e usare i tipi.</span><span class="sxs-lookup"><span data-stu-id="58018-104">This article describes the :::no-loc(Q#)::: type model and the syntax for specifying and working with types.</span></span> <span data-ttu-id="58018-105">Per informazioni dettagliate su come creare e usare espressioni di questi tipi, vedere [espressioni di tipo](xref:microsoft.quantum.guide.expressions).</span><span class="sxs-lookup"><span data-stu-id="58018-105">For details on how to create and operate on expressions of these types, see [Type Expressions](xref:microsoft.quantum.guide.expressions).</span></span>

<span data-ttu-id="58018-106">Si noti che :::no-loc(Q#)::: è un linguaggio *fortemente tipizzato* , in modo che l'utilizzo accurato di questi tipi possa aiutare il compilatore a fornire garanzie complesse sui :::no-loc(Q#)::: programmi in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="58018-106">We note that :::no-loc(Q#)::: is a *strongly-typed* language, such that careful use of these types can help the compiler to provide strong guarantees about :::no-loc(Q#)::: programs at compile time.</span></span>
<span data-ttu-id="58018-107">Per garantire le migliori garanzie possibili, le conversioni tra i tipi in :::no-loc(Q#)::: devono essere esplicite mediante chiamate a funzioni che esprimono tale conversione.</span><span class="sxs-lookup"><span data-stu-id="58018-107">To provide the strongest guarantees possible, conversions between types in :::no-loc(Q#)::: must be explicit using calls to functions which express that conversion.</span></span> 
<span data-ttu-id="58018-108">:::no-loc(Q#)::: fornisce una varietà di funzioni di questo tipo come parte dello <xref:Microsoft.Quantum.Convert> spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="58018-108">:::no-loc(Q#)::: provides a variety of such functions as a part of the <xref:Microsoft.Quantum.Convert> namespace.</span></span>
<span data-ttu-id="58018-109">I cast ai tipi compatibili, d'altra parte, si verificano in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="58018-109">Upcasts to compatible types, on the other hand, happen implicitly.</span></span> 

<span data-ttu-id="58018-110">:::no-loc(Q#)::: fornisce entrambi i tipi primitivi, che vengono usati direttamente e diversi modi per produrre nuovi tipi da altri tipi.</span><span class="sxs-lookup"><span data-stu-id="58018-110">:::no-loc(Q#)::: provides both primitive types, which are used directly, and a variety of ways to produce new types from other types.</span></span>
<span data-ttu-id="58018-111">Ognuno viene descritto nella parte restante di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="58018-111">We describe each in the rest of this article.</span></span>

## <a name="primitive-types"></a><span data-ttu-id="58018-112">Tipi primitivi</span><span class="sxs-lookup"><span data-stu-id="58018-112">Primitive Types</span></span>

<span data-ttu-id="58018-113">Il :::no-loc(Q#)::: linguaggio fornisce i *tipi primitivi* seguenti, che possono essere usati direttamente nei :::no-loc(Q#)::: programmi.</span><span class="sxs-lookup"><span data-stu-id="58018-113">The :::no-loc(Q#)::: language provides the following *primitive types* , all of which you can use directly in :::no-loc(Q#)::: programs.</span></span> <span data-ttu-id="58018-114">È anche possibile usare questi tipi primitivi per costruire nuovi tipi.</span><span class="sxs-lookup"><span data-stu-id="58018-114">You can also use these primitive types to construct new types.</span></span>

- <span data-ttu-id="58018-115">Il `Int` tipo rappresenta un intero con segno a 64 bit, ad esempio,,, `2` `107` `-5` .</span><span class="sxs-lookup"><span data-stu-id="58018-115">The `Int` type represents a 64-bit signed integer, for example, `2`, `107`, `-5`.</span></span>
- <span data-ttu-id="58018-116">Il `BigInt` tipo rappresenta un intero con segno di dimensione arbitraria, ad esempio,, `2L` `107L` `-5L` .</span><span class="sxs-lookup"><span data-stu-id="58018-116">The `BigInt` type represents a signed integer of arbitrary size, for example, `2L`, `107L`, `-5L`.</span></span>
   <span data-ttu-id="58018-117">Questo tipo è basato su .NET <xref:System.Numerics.BigInteger></span><span class="sxs-lookup"><span data-stu-id="58018-117">This type is based on the .NET <xref:System.Numerics.BigInteger></span></span>
   <span data-ttu-id="58018-118">tipo.</span><span class="sxs-lookup"><span data-stu-id="58018-118">type.</span></span>

- <span data-ttu-id="58018-119">Il `Double` tipo rappresenta un numero a virgola mobile a precisione doppia, ad esempio,, `0.0` `-1.3` `4e-7` .</span><span class="sxs-lookup"><span data-stu-id="58018-119">The `Double` type represents a double-precision floating-point number, for example, `0.0`, `-1.3`, `4e-7`.</span></span>
- <span data-ttu-id="58018-120">Il `Bool` tipo rappresenta un valore booleano di `true` o `false` .</span><span class="sxs-lookup"><span data-stu-id="58018-120">The `Bool` type represents a Boolean value of either `true` or `false`.</span></span>
- <span data-ttu-id="58018-121">Il `Range` tipo rappresenta una sequenza di numeri interi, identificati da `start..step..stop` , in cui la denotazione del passaggio è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="58018-121">The `Range` type represents a sequence of integers, denoted by `start..step..stop`, where denoting the step is optional.</span></span> 
   <span data-ttu-id="58018-122">Ad esempio, `start .. stop` corrisponde a `start..1..stop` e `1..2..7` rappresenta la sequenza $ \{ 1, 3, 5, 7 \} $.</span><span class="sxs-lookup"><span data-stu-id="58018-122">For example, `start .. stop` corresponds to `start..1..stop`, and `1..2..7` represents the sequence $\{1, 3, 5, 7\}$.</span></span>
- <span data-ttu-id="58018-123">Il `String` tipo è una sequenza di caratteri Unicode che è opaca per l'utente dopo la creazione.</span><span class="sxs-lookup"><span data-stu-id="58018-123">The `String` type is a sequence of Unicode characters that is opaque to the user once created.</span></span>
  <span data-ttu-id="58018-124">Usare il `string` tipo per segnalare i messaggi a un host classico nel caso di un evento di errore o di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="58018-124">Use the `string` type to report messages to a classical host in the case of an error or diagnostic event.</span></span>
- <span data-ttu-id="58018-125">Il `Unit` tipo può avere un solo valore, `()` .</span><span class="sxs-lookup"><span data-stu-id="58018-125">The `Unit` type can have only one value, `()`.</span></span> 
  <span data-ttu-id="58018-126">Utilizzare questo tipo per indicare che una :::no-loc(Q#)::: funzione o un'operazione non restituisce alcuna informazione.</span><span class="sxs-lookup"><span data-stu-id="58018-126">Use this type to indicate that a :::no-loc(Q#)::: function or operation returns no information.</span></span> 
- <span data-ttu-id="58018-127">Il `Qubit` tipo rappresenta un bit Quantum o qubit.</span><span class="sxs-lookup"><span data-stu-id="58018-127">The `Qubit` type represents a quantum bit or qubit.</span></span>
   <span data-ttu-id="58018-128">`Qubit`i sono opachi per l'utente.</span><span class="sxs-lookup"><span data-stu-id="58018-128">`Qubit`s are opaque to the user.</span></span> <span data-ttu-id="58018-129">L'unica operazione possibile, ad eccezione del passaggio a un'altra operazione, consiste nel testare l'identità (uguaglianza).</span><span class="sxs-lookup"><span data-stu-id="58018-129">The only operation possible with them, other than passing them to another operation, is to test for identity (equality).</span></span>
   <span data-ttu-id="58018-130">Infine, si implementano le azioni su `Qubit` s chiamando istruzioni intrinseche su un processore Quantum (o un simulatore Quantum).</span><span class="sxs-lookup"><span data-stu-id="58018-130">Ultimately, you implement actions on `Qubit`s by calling intrinsic instructions on a quantum processor (or a quantum simulator).</span></span>
- <span data-ttu-id="58018-131">Il `Pauli` tipo rappresenta uno dei quattro operatori Pauli a qubit singola.</span><span class="sxs-lookup"><span data-stu-id="58018-131">The `Pauli` type represents one of the four single-qubit Pauli operators.</span></span>
   <span data-ttu-id="58018-132">Utilizzare questo tipo per indicare l'operazione di base per le rotazioni e per specificare la misura osservabile.</span><span class="sxs-lookup"><span data-stu-id="58018-132">Use this type to denote the base operation for rotations and to specify the observable being measured.</span></span>
   <span data-ttu-id="58018-133">Si tratta di un tipo enumerato che dispone di quattro valori possibili: `PauliI` , `PauliX` , `PauliY` e `PauliZ` , che sono costanti di tipo `Pauli` .</span><span class="sxs-lookup"><span data-stu-id="58018-133">It is an enumerated type that has four possible values: `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, which are constants of type `Pauli`.</span></span>
- <span data-ttu-id="58018-134">Il `Result` tipo rappresenta il risultato di una misura.</span><span class="sxs-lookup"><span data-stu-id="58018-134">The `Result` type represents the result of a measurement.</span></span>
   <span data-ttu-id="58018-135">Si tratta di un tipo enumerato con due valori possibili: `One` e `Zero` , che sono costanti di tipo `Result` .</span><span class="sxs-lookup"><span data-stu-id="58018-135">It is an enumerated type with two possible values: `One` and `Zero`, which are constants of type `Result`.</span></span>
   <span data-ttu-id="58018-136">`Zero` indica che è stato misurato il autovalore + 1; `One` indica che è stato misurato-1 autovalore.</span><span class="sxs-lookup"><span data-stu-id="58018-136">`Zero` indicates that the +1 eigenvalue was measured; `One` indicates the -1 eigenvalue was measured.</span></span>

<span data-ttu-id="58018-137">Le costanti,,,,,, `true` `false` `PauliI` `PauliX` `PauliY` `PauliZ` `One` e `Zero` sono tutti simboli riservati in :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="58018-137">The constants `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`, and `Zero` are all reserved symbols in :::no-loc(Q#):::.</span></span>

## <a name="array-types"></a><span data-ttu-id="58018-138">Tipi di matrici</span><span class="sxs-lookup"><span data-stu-id="58018-138">Array Types</span></span>

* <span data-ttu-id="58018-139">Per qualsiasi :::no-loc(Q#)::: tipo valido, esiste un tipo che rappresenta una matrice di valori di quel tipo.</span><span class="sxs-lookup"><span data-stu-id="58018-139">For any valid :::no-loc(Q#)::: type, there is a type that represents an array of values of that type.</span></span>
    <span data-ttu-id="58018-140">Ad esempio, `Qubit[]` e `(Bool, Pauli)[]` rappresentano matrici di `Qubit` valori e `(Bool, Pauli)` valori di tupla.</span><span class="sxs-lookup"><span data-stu-id="58018-140">For example, `Qubit[]` and `(Bool, Pauli)[]` represent arrays of `Qubit` values and `(Bool, Pauli)` tuple values.</span></span>

* <span data-ttu-id="58018-141">È anche valida una matrice di matrici.</span><span class="sxs-lookup"><span data-stu-id="58018-141">An array of arrays is also valid.</span></span> <span data-ttu-id="58018-142">Espandendo l'esempio precedente, viene indicata una matrice di `(Bool, Pauli)` matrici `(Bool, Pauli)[][]` .</span><span class="sxs-lookup"><span data-stu-id="58018-142">Expanding on the previous example, an array of `(Bool, Pauli)` arrays is denoted `(Bool, Pauli)[][]`.</span></span>

> [!NOTE] 
> <span data-ttu-id="58018-143">Questo esempio, `(Bool, Pauli)[][]` , rappresenta una matrice di matrici potenzialmente irregolare e non una matrice bidimensionale rettangolare.</span><span class="sxs-lookup"><span data-stu-id="58018-143">This example, `(Bool, Pauli)[][]`, represents a potentially jagged array of arrays and not a rectangular two-dimensional array.</span></span> <span data-ttu-id="58018-144">:::no-loc(Q#)::: non supporta matrici multidimensionali rettangolari.</span><span class="sxs-lookup"><span data-stu-id="58018-144">:::no-loc(Q#)::: does not support rectangular multi-dimensional arrays.</span></span>

* <span data-ttu-id="58018-145">È possibile scrivere un valore di matrice nel :::no-loc(Q#)::: codice sorgente usando le parentesi quadre intorno agli elementi di una matrice, come in `[PauliI, PauliX, PauliY, PauliZ]` .</span><span class="sxs-lookup"><span data-stu-id="58018-145">An array value can be written in :::no-loc(Q#)::: source code by using square brackets around the elements of an array, as in `[PauliI, PauliX, PauliY, PauliZ]`.</span></span>
<span data-ttu-id="58018-146">Il tipo di base comune di tutti gli elementi nella matrice determina il tipo di un valore letterale di matrice.</span><span class="sxs-lookup"><span data-stu-id="58018-146">The common base type of all items in the array determines the type of an array literal.</span></span> <span data-ttu-id="58018-147">Di conseguenza, la costruzione di una matrice con elementi che non dispongono di un tipo di base comune genera un errore.</span><span class="sxs-lookup"><span data-stu-id="58018-147">Hence, constructing an array with elements that have no common base type raises an error.</span></span>  
<span data-ttu-id="58018-148">Per un esempio, vedere [matrici di chiamabili](xref:microsoft.quantum.guide.expressions#arrays-of-callables).</span><span class="sxs-lookup"><span data-stu-id="58018-148">For an example, see [arrays of callables](xref:microsoft.quantum.guide.expressions#arrays-of-callables).</span></span>

    > [!WARNING]
    > <span data-ttu-id="58018-149">Una volta creati, gli elementi di una matrice non possono essere modificati.</span><span class="sxs-lookup"><span data-stu-id="58018-149">Once created, the elements of an array cannot be changed.</span></span>
    > <span data-ttu-id="58018-150">Per costruire una matrice modificata, usare [le istruzioni Update-and-reassign](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) oppure [le espressioni di copia e aggiornamento](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span><span class="sxs-lookup"><span data-stu-id="58018-150">To construct a modified array, use [update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) or [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span></span>

* <span data-ttu-id="58018-151">In alternativa, è possibile creare una matrice dalle relative dimensioni usando la `new` parola chiave:</span><span class="sxs-lookup"><span data-stu-id="58018-151">Alternatively, an array can be created from its size using the `new` keyword:</span></span>

    ```qsharp
    let zeros = new Int[13];
    // you can also use new for creating empty arrays:
    let emptyRegister = new Qubit[0];
    ```

* <span data-ttu-id="58018-152">Usare la funzione Core `Length` per ottenere il numero di elementi da una matrice come `Int` .</span><span class="sxs-lookup"><span data-stu-id="58018-152">Use the core function `Length` to obtain the number of elements from an array as an `Int`.</span></span>
* <span data-ttu-id="58018-153">Le matrici possono essere sottoposte a indicizzazione per ottenere singoli elementi o nuove matrici contenenti un subset degli elementi di una matrice.</span><span class="sxs-lookup"><span data-stu-id="58018-153">Arrays can be subscripted to obtain either single elements or new arrays containing a subset of the elements of an array.</span></span>
<span data-ttu-id="58018-154">Gli indici delle matrici sono in base zero e devono essere di tipo `Int` o di tipo `Range` :</span><span class="sxs-lookup"><span data-stu-id="58018-154">The subscripts of arrays are zero-based and must be type `Int` or type `Range`:</span></span>

    ```qsharp
    let arr = [10, 11, 36, 49];
    let ten = arr[0]; // 10
    let odds = arr[1..2..4]; // [11, 49]
    ```

## <a name="tuple-types"></a><span data-ttu-id="58018-155">Tipi di tupla</span><span class="sxs-lookup"><span data-stu-id="58018-155">Tuple Types</span></span>

<span data-ttu-id="58018-156">Le tuple sono un concetto potente usato :::no-loc(Q#)::: per raccogliere i valori in un unico valore, rendendolo più semplice da passare.</span><span class="sxs-lookup"><span data-stu-id="58018-156">Tuples are a powerful concept used throughout :::no-loc(Q#)::: to collect values together into a single value, making it easier to pass them around.</span></span>
<span data-ttu-id="58018-157">In particolare, usando la notazione di tupla, è possibile esprimere che ogni operazione e Callable accetta esattamente un input e restituisce esattamente un output.</span><span class="sxs-lookup"><span data-stu-id="58018-157">In particular, using tuple notation, you can express that every operation and callable takes exactly one input and returns exactly one output.</span></span>

* <span data-ttu-id="58018-158">Dato zero o più tipi diversi `T0` ,,... `T1` , `Tn` , è possibile indicare un nuovo  *tipo di tupla* come `(T0, T1, ..., Tn)` .</span><span class="sxs-lookup"><span data-stu-id="58018-158">Given zero or more different types `T0`, `T1`, ..., `Tn`, you can denote a new  *tuple type* as `(T0, T1, ..., Tn)`.</span></span>
<span data-ttu-id="58018-159">I tipi utilizzati per costruire un nuovo tipo di tupla possono essere Tuple, come in `(Int, (Qubit, Qubit))` .</span><span class="sxs-lookup"><span data-stu-id="58018-159">The types used to construct a new tuple type can themselves be tuples, as in `(Int, (Qubit, Qubit))`.</span></span>
<span data-ttu-id="58018-160">Tale annidamento è sempre finito, tuttavia, in quanto i tipi di tupla non possono in alcun caso contenere se stessi.</span><span class="sxs-lookup"><span data-stu-id="58018-160">Such nesting is always finite, however, as tuple types cannot under any circumstances contain themselves.</span></span>

* <span data-ttu-id="58018-161">I valori del nuovo tipo di tupla sono Tuple costituite da sequenze di valori di ogni tipo nella tupla.</span><span class="sxs-lookup"><span data-stu-id="58018-161">The values of the new tuple type are tuples formed by sequences of values from each type in the tuple.</span></span>
<span data-ttu-id="58018-162">Ad esempio, `(3, false)` è una tupla il cui tipo è il tipo di tupla `(Int, Bool)` .</span><span class="sxs-lookup"><span data-stu-id="58018-162">For example, `(3, false)` is a tuple whose type is the tuple type `(Int, Bool)`.</span></span>
<span data-ttu-id="58018-163">È possibile creare matrici di tuple, Tuple di matrici, Tuple di sottotuple e così via.</span><span class="sxs-lookup"><span data-stu-id="58018-163">It is possible to create arrays of tuples, tuples of arrays, tuples of sub-tuples, and so on.</span></span>

* <span data-ttu-id="58018-164">A partire da :::no-loc(Q#)::: 0,3, `Unit` è il nome del *tipo* della tupla vuota `()` . viene usato per il *valore* della tupla vuota.</span><span class="sxs-lookup"><span data-stu-id="58018-164">As of :::no-loc(Q#)::: 0.3, `Unit` is the name of the *type* of the empty tuple; `()` is used for the *value* of the empty tuple.</span></span>

* <span data-ttu-id="58018-165">Le istanze di tupla non sono modificabili.</span><span class="sxs-lookup"><span data-stu-id="58018-165">Tuple instances are immutable.</span></span>
<span data-ttu-id="58018-166">:::no-loc(Q#)::: non fornisce un meccanismo per modificare il contenuto di una tupla una volta creata.</span><span class="sxs-lookup"><span data-stu-id="58018-166">:::no-loc(Q#)::: does not provide a mechanism to change the contents of a tuple once created.</span></span>



### <a name="singleton-tuple-equivalence"></a><span data-ttu-id="58018-167">Equivalenza della tupla singleton</span><span class="sxs-lookup"><span data-stu-id="58018-167">Singleton Tuple Equivalence</span></span>

<span data-ttu-id="58018-168">È possibile creare una tupla Singleton (elemento singolo) `('T1)` , ad esempio `(5)` o `([1,2,3])` .</span><span class="sxs-lookup"><span data-stu-id="58018-168">It is possible to create a singleton (single-element) tuple `('T1)`, such as `(5)` or `([1,2,3])`.</span></span>
<span data-ttu-id="58018-169">Tuttavia, :::no-loc(Q#)::: tratta una tupla singleton come equivalente a un valore del tipo racchiuso.</span><span class="sxs-lookup"><span data-stu-id="58018-169">However, :::no-loc(Q#)::: treats a singleton tuple as equivalent to a value of the enclosed type.</span></span>
<span data-ttu-id="58018-170">Ovvero, non esiste alcuna differenza tra `5` e `(5)` , o tra `5` e `(((5)))` o tra `(5, (6))` e `(5, 6)` .</span><span class="sxs-lookup"><span data-stu-id="58018-170">That is, there is no difference between `5` and `(5)`, or between `5` and `(((5)))`, or between `(5, (6))` and `(5, 6)`.</span></span>
<span data-ttu-id="58018-171">È altrettanto valido scrivere `(5)+3` così come è scrivere `5+3` . entrambe le espressioni restituiscono `8` .</span><span class="sxs-lookup"><span data-stu-id="58018-171">It is just as valid to write `(5)+3` as it is to write `5+3`; both expressions evaluate to `8`.</span></span>

<span data-ttu-id="58018-172">Questa equivalenza si applica a tutti gli scopi, incluse le assegnazioni e le espressioni.</span><span class="sxs-lookup"><span data-stu-id="58018-172">This equivalence applies for all purposes, including assignment and expressions.</span></span>
<span data-ttu-id="58018-173">Dato qualsiasi espressione, la stessa espressione racchiusa tra parentesi è un'espressione dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="58018-173">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="58018-174">Ad esempio, `(7)` è un'espressione di tipo `Int` , `([1,2,3])` è un'espressione di tipo `Int[]` e `((1,2))` è un'espressione di tipo `(Int, Int)` .</span><span class="sxs-lookup"><span data-stu-id="58018-174">For example, `(7)` is an expression of type `Int`, `([1,2,3])` is an expression of type `Int[]`, and `((1,2))` is an expression of type `(Int, Int)`.</span></span>

<span data-ttu-id="58018-175">In particolare, ciò significa che è possibile visualizzare un'operazione o una funzione il cui tipo di tupla di input o di tupla di output ha un campo che accetta un singolo argomento o restituisce un singolo valore.</span><span class="sxs-lookup"><span data-stu-id="58018-175">In particular, this means that you can view an operation or function whose input tuple or output tuple type has one field as taking a single argument or returning a single value.</span></span>

<span data-ttu-id="58018-176">Si fa riferimento a questa proprietà come _equivalenza della tupla singleton_ .</span><span class="sxs-lookup"><span data-stu-id="58018-176">We refer to this property as _singleton tuple equivalence_ .</span></span>


## <a name="user-defined-types"></a><span data-ttu-id="58018-177">Tipi definiti dall'utente</span><span class="sxs-lookup"><span data-stu-id="58018-177">User-Defined Types</span></span>

<span data-ttu-id="58018-178">Una dichiarazione del tipo definito dall'utente è costituita dalla parola chiave `newtype` , seguita dal nome del tipo definito dall'utente, da `=` , da una specifica del tipo valida e da un punto e virgola di terminazione.</span><span class="sxs-lookup"><span data-stu-id="58018-178">A user-defined type declaration consists of the keyword `newtype`, followed by the name of the user-defined type, an `=`, a valid type specification, and a terminating semicolon.</span></span>

<span data-ttu-id="58018-179">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="58018-179">For example:</span></span>

```qsharp
newtype PairOfInts = (Int, Int);
```
    
* <span data-ttu-id="58018-180">Ogni :::no-loc(Q#)::: file di origine può dichiarare un numero qualsiasi di tipi definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="58018-180">Each :::no-loc(Q#)::: source file may declare any number of user-defined types.</span></span>
* <span data-ttu-id="58018-181">I nomi dei tipi devono essere univoci all'interno di uno spazio dei nomi e non possono entrare in conflitto con i nomi di funzione e</span><span class="sxs-lookup"><span data-stu-id="58018-181">Type names must be unique within a namespace and may not conflict with operation and function names.</span></span>
* <span data-ttu-id="58018-182">I tipi definiti dall'utente sono distinti, anche se i tipi di base sono identici.</span><span class="sxs-lookup"><span data-stu-id="58018-182">User-defined types are distinct, even if the base types are identical.</span></span>
<span data-ttu-id="58018-183">In particolare, non viene eseguita alcuna conversione automatica tra i valori di due tipi definiti dall'utente, anche se i tipi sottostanti sono identici.</span><span class="sxs-lookup"><span data-stu-id="58018-183">In particular, there is no automatic conversion between the values of two user-defined types, even if the underlying types are identical.</span></span>

### <a name="named-vs-anonymous-items"></a><span data-ttu-id="58018-184">Elementi denominati e anonimi</span><span class="sxs-lookup"><span data-stu-id="58018-184">Named vs. anonymous items</span></span>

<span data-ttu-id="58018-185">Un :::no-loc(Q#)::: file può definire un nuovo tipo denominato contenente un singolo valore di qualsiasi tipo valido.</span><span class="sxs-lookup"><span data-stu-id="58018-185">A :::no-loc(Q#)::: file may define a new named type containing a single value of any legal type.</span></span>
<span data-ttu-id="58018-186">Per qualsiasi tipo di tupla `T` , è possibile dichiarare un nuovo tipo definito dall'utente che è un sottotipo di `T` con l' `newtype` istruzione.</span><span class="sxs-lookup"><span data-stu-id="58018-186">For any tuple type `T`, you can declare a new user-defined type that is a subtype of `T` with the `newtype` statement.</span></span>
<span data-ttu-id="58018-187">Nello @"microsoft.quantum.math" spazio dei nomi, ad esempio, i numeri complessi sono definiti come tipo definito dall'utente:</span><span class="sxs-lookup"><span data-stu-id="58018-187">In the @"microsoft.quantum.math" namespace, for example, complex numbers are defined as a user-defined type:</span></span>

```qsharp
newtype Complex = (Double, Double);
```
<span data-ttu-id="58018-188">Questa istruzione crea un nuovo tipo con due elementi anonimi di tipo `Double` .</span><span class="sxs-lookup"><span data-stu-id="58018-188">This statement creates a new type with two anonymous items of type `Double`.</span></span>   

<span data-ttu-id="58018-189">A parte gli elementi anonimi, i tipi definiti dall'utente supportano anche *gli elementi denominati* a partire dalla :::no-loc(Q#)::: versione 0,7 o successiva.</span><span class="sxs-lookup"><span data-stu-id="58018-189">Aside from anonymous items, user-defined types also support *named items* as of :::no-loc(Q#)::: version 0.7 or higher.</span></span> <span data-ttu-id="58018-190">È ad esempio possibile denominare gli elementi per `Real` il valore Double che rappresenta la parte reale di un numero complesso e `Imag` per la parte immaginaria:</span><span class="sxs-lookup"><span data-stu-id="58018-190">For example, you could name the items to `Real` for the double representing the real part of a complex number and `Imag` for the imaginary part:</span></span> 

```qsharp
newtype Complex = (Real : Double, Imag : Double);
```
<span data-ttu-id="58018-191">La denominazione di un elemento in un tipo definito dall'utente non implica che tutti gli elementi devono essere denominati. sono supportate tutte le combinazioni di elementi denominati e senza nome.</span><span class="sxs-lookup"><span data-stu-id="58018-191">Naming one item in a user-defined type does not imply that all items need to be named - any combination of named and unnamed items is supported.</span></span> <span data-ttu-id="58018-192">Inoltre, gli elementi interni possono anche essere denominati.</span><span class="sxs-lookup"><span data-stu-id="58018-192">Furthermore, inner items may also be named.</span></span>
<span data-ttu-id="58018-193">Il tipo `Nested` , come definito di seguito, ad esempio, ha un tipo sottostante `(Double, (Int, String))` , di cui solo l'elemento di tipo `Int` è denominato e tutti gli altri elementi sono anonimi.</span><span class="sxs-lookup"><span data-stu-id="58018-193">The type `Nested`, as defined below for example, has an underlying type `(Double, (Int, String))`, of which only the item of type `Int` is named, and all other items are anonymous.</span></span> 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

<span data-ttu-id="58018-194">Gli elementi denominati hanno il vantaggio di poter accedere direttamente tramite l' *operatore di accesso* `::` .</span><span class="sxs-lookup"><span data-stu-id="58018-194">Named items have the advantage that they can be accessed directly via the *access operator* `::`.</span></span> 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Real + c2::Real, c1::Imag + c2::Imag);
}
```

<span data-ttu-id="58018-195">Oltre a fornire alias brevi per i tipi di tupla potenzialmente complessi, un vantaggio significativo della definizione di tali tipi è che possono documentare lo scopo di un determinato valore.</span><span class="sxs-lookup"><span data-stu-id="58018-195">In addition to providing short aliases for potentially complicated tuple types, a significant advantage of defining such types is that they can document the intent of a particular value.</span></span>
<span data-ttu-id="58018-196">Tornando all'esempio di `Complex` , è possibile che sia stata definita anche una coordinata polare rappresentazione come tipo definito dall'utente:</span><span class="sxs-lookup"><span data-stu-id="58018-196">Returning to the example of `Complex`, one could have also defined a polar coordinate represenation as a user-defined type:</span></span>

```qsharp
newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```

<span data-ttu-id="58018-197">Anche se entrambi `Complex` `ComplexPolar` i tipi e hanno entrambi un tipo sottostante `(Double, Double)` , i due tipi sono completamente incompatibili in :::no-loc(Q#)::: , riducendo al minimo il rischio di chiamare accidentalmente una funzione matematica complessa con coordinate polari e viceversa.</span><span class="sxs-lookup"><span data-stu-id="58018-197">Even though both `Complex` and `ComplexPolar` both have an underlying type `(Double, Double)`, the two types are wholly incompatible in :::no-loc(Q#):::, minimizing the risk of accidentally calling a complex math function with polar coordinates and vice versa.</span></span>

#### <a name="access-anonymous-items-with-the-unwrap-operator"></a><span data-ttu-id="58018-198">Accedere a elementi anonimi con l'operatore Unwrap</span><span class="sxs-lookup"><span data-stu-id="58018-198">Access anonymous items with the unwrap operator</span></span>

<span data-ttu-id="58018-199">Per accedere agli elementi anonimi, estrarre innanzitutto il valore di cui è stato eseguito il wrapped usando l'operatore Postfix `!` .</span><span class="sxs-lookup"><span data-stu-id="58018-199">To access anonymous items, first extract the wrapped value using the postfix operator `!`.</span></span>
<span data-ttu-id="58018-200">Con l'operatore "Unwrap", `!` è possibile estrarre il valore contenuto in un tipo definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="58018-200">With the "unwrap" operator, `!`, you can extract the value contained in a user-defined type.</span></span>
<span data-ttu-id="58018-201">Il tipo di un'espressione "Unwrap" è il tipo sottostante del tipo definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="58018-201">The type of such an "unwrap" expression is the underlying type of the user-defined type.</span></span> 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

<span data-ttu-id="58018-202">Un singolo operatore Unwrap Annulla il wrapping di un livello di wrapping.</span><span class="sxs-lookup"><span data-stu-id="58018-202">A single unwrap operator unwraps one layer of wrapping.</span></span> <span data-ttu-id="58018-203">Usare più operatori Unwrap per accedere a un valore con wrapping multiplo.</span><span class="sxs-lookup"><span data-stu-id="58018-203">Use multiple unwrap operators to access a multiply-wrapped value.</span></span>

<span data-ttu-id="58018-204">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="58018-204">For example:</span></span>

```qsharp
newtype WrappedInt = Int;
newtype DoublyWrappedInt = WrappedInt;

...
    let x = DoublyWrappedInt(WrappedInt(6));
    let y = x!;       // y is WrappedInt(6)
    let z = x!!;      // z is 6
    let a = x + 5;    // This is an error, a DoublyWrappedInt isn't an Int
    let b = x! + 5;   // Also an error
    let c = x!! + 5;  // This is valid, c will be 11
...
```

<span data-ttu-id="58018-205">Per ulteriori informazioni sull'operatore Unwrap, vedere [espressioni di tipo in :::no-loc(Q#)::: ](xref:microsoft.quantum.guide.expressions).</span><span class="sxs-lookup"><span data-stu-id="58018-205">For more details on the unwrap operator, see [Type Expressions in :::no-loc(Q#):::](xref:microsoft.quantum.guide.expressions).</span></span>

### <a name="creating-values-of-user-defined-types"></a><span data-ttu-id="58018-206">Creazione di valori di tipi definiti dall'utente</span><span class="sxs-lookup"><span data-stu-id="58018-206">Creating values of user-defined types</span></span>

<span data-ttu-id="58018-207">Creare valori di un tipo definito dall'utente chiamando il costruttore del tipo corrispondente:</span><span class="sxs-lookup"><span data-stu-id="58018-207">Create values of a user-defined type by calling the corresponding type constructor:</span></span>

```qsharp
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

<span data-ttu-id="58018-208">In alternativa, è possibile creare nuovi valori da quelli esistenti usando [le espressioni di copia e aggiornamento](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span><span class="sxs-lookup"><span data-stu-id="58018-208">Alternatively, you can create new values from existing ones using [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span></span> <span data-ttu-id="58018-209">Analogamente a quanto avviene con le matrici, le espressioni di copia e aggiornamento copiano tutti i valori degli elementi dell'espressione originale, ad eccezione degli elementi denominati specificati.</span><span class="sxs-lookup"><span data-stu-id="58018-209">Just as they do with arrays, copy-and-update expressions copy all item values of the original expression, except for the specified named items.</span></span> <span data-ttu-id="58018-210">Per queste eccezioni, i valori di questi elementi sono i valori definiti sul lato destro dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="58018-210">For these exceptions, the values of these items are the values defined on the right-hand side of the expression.</span></span> <span data-ttu-id="58018-211">Tutti gli altri costrutti di linguaggio disponibili per gli elementi della matrice, ad esempio le [istruzioni Update e reassign](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), esistono anche per gli elementi denominati nei tipi definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="58018-211">Any other language constructs that are available for array items, for example [update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), exist for named-items in user-defined types as well.</span></span>

```qsharp
newtype ComplexArray = (Count : Int, Data : Complex[]);

function AsComplexArray (data : Double[]) : ComplexArray {

    mutable res = ComplexArray(0, new Complex[0]);
    for (item in data) {
        set res w/= Data <- res::Data + [Complex(item, 0.)]; // update-and-reassign statement
    }
    return res w/ Count <- Length(res::Data); // returning a copy-and-update expression
}
```

* <span data-ttu-id="58018-212">È possibile usare i tipi definiti dall'utente in qualsiasi punto in cui si usano altri tipi.</span><span class="sxs-lookup"><span data-stu-id="58018-212">You can use user-defined types anywhere you use any other types.</span></span>
<span data-ttu-id="58018-213">In particolare, è possibile definire una matrice di un tipo definito dall'utente e includere un tipo definito dall'utente come elemento di un tipo di tupla.</span><span class="sxs-lookup"><span data-stu-id="58018-213">In particular, it is possible to define an array of a user-defined type and to include a user-defined type as an element of a tuple type.</span></span>

* <span data-ttu-id="58018-214">Non è possibile creare strutture di tipo ricorsivo.</span><span class="sxs-lookup"><span data-stu-id="58018-214">It is not possible to create recursive type structures.</span></span>
<span data-ttu-id="58018-215">Ovvero, il tipo che definisce un tipo definito dall'utente non può essere un tipo di tupla che include un elemento del tipo definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="58018-215">That is, the type that defines a user-defined type cannot be a tuple type that includes an element of the user-defined type.</span></span>
<span data-ttu-id="58018-216">Più in generale, i tipi definiti dall'utente potrebbero non avere dipendenze cicliche tra loro, quindi il set di definizioni di tipo seguente non è valido:</span><span class="sxs-lookup"><span data-stu-id="58018-216">More generally, user-defined types may not have cyclic dependencies on each other, so the following set of type definitions are invalid:</span></span>

    ```qsharp
    newtype TypeA = (Int, TypeB);
    newtype TypeB = (Double, TypeC);
    newtype TypeC = (TypeA, Range);
    ```


## <a name="operation-and-function-types"></a><span data-ttu-id="58018-217">Tipi di operazioni e funzioni</span><span class="sxs-lookup"><span data-stu-id="58018-217">Operation and Function Types</span></span>

<span data-ttu-id="58018-218">Dati i tipi `'Tinput` e `'Tresult` :</span><span class="sxs-lookup"><span data-stu-id="58018-218">Given the types `'Tinput` and `'Tresult`:</span></span>

* <span data-ttu-id="58018-219">`('Tinput => 'Tresult)` è il tipo di base per qualsiasi *operazione* , ad esempio `((Qubit, Pauli) => Result)` .</span><span class="sxs-lookup"><span data-stu-id="58018-219">`('Tinput => 'Tresult)` is the basic type for any *operation* , for example `((Qubit, Pauli) => Result)`.</span></span>
* <span data-ttu-id="58018-220">`('Tinput -> 'Tresult)` è il tipo di base per qualsiasi *funzione* , ad esempio `(Int -> Int)` .</span><span class="sxs-lookup"><span data-stu-id="58018-220">`('Tinput -> 'Tresult)` is the basic type for any *function* , for example `(Int -> Int)`.</span></span> 

<span data-ttu-id="58018-221">Questi sono detti *firma* dell'oggetto chiamabile.</span><span class="sxs-lookup"><span data-stu-id="58018-221">These are called the *signature* of the callable.</span></span>

* <span data-ttu-id="58018-222">Tutte le :::no-loc(Q#)::: Callable accettano un singolo valore come input e restituiscono un singolo valore come output.</span><span class="sxs-lookup"><span data-stu-id="58018-222">All :::no-loc(Q#)::: callables take a single value as input and return a single value as output.</span></span>
* <span data-ttu-id="58018-223">È possibile utilizzare le tuple per i valori di input e di output.</span><span class="sxs-lookup"><span data-stu-id="58018-223">You can use tuples for both the input and output values.</span></span>
* <span data-ttu-id="58018-224">Chiamabili senza risultato, restituiscono `Unit` .</span><span class="sxs-lookup"><span data-stu-id="58018-224">Callables that have no result, return `Unit`.</span></span>
* <span data-ttu-id="58018-225">Le chiamabili senza input accettano la tupla vuota come input.</span><span class="sxs-lookup"><span data-stu-id="58018-225">Callables that have no input take the empty tuple as input.</span></span>

### <a name="functors"></a><span data-ttu-id="58018-226">Funtori</span><span class="sxs-lookup"><span data-stu-id="58018-226">Functors</span></span>

<span data-ttu-id="58018-227">I tipi di *funzione* sono completamente specificati dalla relativa firma.</span><span class="sxs-lookup"><span data-stu-id="58018-227">*Function* types are completely specified by their signature.</span></span> <span data-ttu-id="58018-228">Ad esempio, una funzione che calcola il seno di un angolo avrebbe il tipo `(Double -> Double)` .</span><span class="sxs-lookup"><span data-stu-id="58018-228">For example, a function that computes the sine of an angle would have type `(Double -> Double)`.</span></span> 

<span data-ttu-id="58018-229">*Le operazioni* hanno determinate caratteristiche aggiuntive espresse come parte del tipo di operazione.</span><span class="sxs-lookup"><span data-stu-id="58018-229">*Operations* have certain additional characteristics that are expressed as part of the operation type.</span></span> <span data-ttu-id="58018-230">Tali caratteristiche includono le informazioni sul *funtori* supportato dall'operazione.</span><span class="sxs-lookup"><span data-stu-id="58018-230">Such characteristics include information about which *functors* the operation supports.</span></span>
<span data-ttu-id="58018-231">Se, ad esempio, l'esecuzione dell'operazione si basa sullo stato di altri qubits, deve supportare il `Controlled` functor; se l'operazione ha un inverso, deve supportare il `Adjoint` functor.</span><span class="sxs-lookup"><span data-stu-id="58018-231">For example, if the running of the operation relies on the state of other qubits, then it should support the `Controlled` functor; if the operation has an inverse, then it should support the `Adjoint` functor.</span></span>

> [!NOTE]
> <span data-ttu-id="58018-232">Questo articolo illustra solo il modo in cui funtori modifica la firma dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="58018-232">This article only discuss how functors alter the operation signature.</span></span> <span data-ttu-id="58018-233">Per ulteriori informazioni su funtori e sulle operazioni, vedere [operazioni e funzioni :::no-loc(Q#)::: in ](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="58018-233">For more details about functors and operations, see [Operations and Functions in :::no-loc(Q#):::](xref:microsoft.quantum.guide.operationsfunctions).</span></span> 

<span data-ttu-id="58018-234">Per richiedere il supporto per `Controlled` e/o `Adjoint` functor in un tipo di operazione, è necessario aggiungere un'annotazione che indichi le caratteristiche corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="58018-234">To require support for the `Controlled` and/or `Adjoint` functor in an operation type, you need to add an annotation indicating the corresponding characteristics.</span></span>
<span data-ttu-id="58018-235">L'annotazione `is Ctl` , ad esempio, `(Qubit => Unit is Ctl)` indica che l'operazione è controllabile.</span><span class="sxs-lookup"><span data-stu-id="58018-235">The annotation `is Ctl` (for example, `(Qubit => Unit is Ctl)`) indicates that the operation is controllable.</span></span> <span data-ttu-id="58018-236">Ovvero, la relativa esecuzione si basa sullo stato di un altro qubit o qubits.</span><span class="sxs-lookup"><span data-stu-id="58018-236">That is, its run relies on the state of another qubit or qubits.</span></span> <span data-ttu-id="58018-237">Analogamente, l'annotazione `is Adj` indica che l'operazione ha un contiguo, ovvero può essere "invertito" in modo che l'applicazione successiva di un'operazione e quindi il relativo contiguo a uno stato lasci lo stato invariato.</span><span class="sxs-lookup"><span data-stu-id="58018-237">Similarly, the annotation `is Adj` indicates that the operation has an adjoint, that is, it can be "inverted" such that successively applying an operation and then its adjoint to a state leaves the state unchanged.</span></span> 

<span data-ttu-id="58018-238">Se si vuole richiedere che un'operazione di quel tipo supporti sia il `Adjoint` `Controlled` functor che l'espressione `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="58018-238">If you want to require that an operation of that type supports both the `Adjoint` and `Controlled` functor you can express this as `(Qubit => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="58018-239">L'operazione di Pauli incorporata, ad esempio, <xref:Microsoft.Quantum.Intrinsic.X> è di tipo `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="58018-239">For example, the built-in Pauli <xref:Microsoft.Quantum.Intrinsic.X> operation has type `(Qubit => Unit is Adj + Ctl)`.</span></span> 

<span data-ttu-id="58018-240">Un tipo di operazione che non supporta alcun funtori viene specificato solo dal tipo di input e di output, senza alcuna annotazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="58018-240">An operation type that does not support any functors is specified by its input and output type alone, with no additional annotation.</span></span>

### <a name="type-parameterized-functions-and-operations"></a><span data-ttu-id="58018-241">Funzioni e operazioni Type-Parameterized</span><span class="sxs-lookup"><span data-stu-id="58018-241">Type-Parameterized Functions and Operations</span></span>

<span data-ttu-id="58018-242">I tipi chiamabili possono contenere *parametri di tipo* .</span><span class="sxs-lookup"><span data-stu-id="58018-242">Callable types may contain *type parameters* .</span></span>
<span data-ttu-id="58018-243">Usare un simbolo preceduto da una virgoletta singola per indicare un parametro di tipo; ad esempio, `'A` è un parametro di tipo valido.</span><span class="sxs-lookup"><span data-stu-id="58018-243">Use a symbol prefixed by a single quote to indicated a type parameter; for example, `'A` is a legal type parameter.</span></span>
<span data-ttu-id="58018-244">Per ulteriori informazioni e dettagli su come definire le funzioni chiamabili con parametri di tipo, vedere [operazioni e :::no-loc(Q#)::: funzioni in ](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables).</span><span class="sxs-lookup"><span data-stu-id="58018-244">For more information and details on how to define type-parameterized callables, see [Operations and Functions in :::no-loc(Q#):::](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables).</span></span>

<span data-ttu-id="58018-245">Un parametro di tipo può essere visualizzato più di una volta in un'unica firma.</span><span class="sxs-lookup"><span data-stu-id="58018-245">A type parameter may appear more than once in a single signature.</span></span>
<span data-ttu-id="58018-246">Ad esempio, una funzione che applica un'altra funzione a ogni elemento di una matrice e restituisce la firma dei risultati raccolti `(('A[], 'A->'A) -> 'A[])` .</span><span class="sxs-lookup"><span data-stu-id="58018-246">For example, a function that applies another function to each element of an array and returns the collected results has the signature `(('A[], 'A->'A) -> 'A[])`.</span></span>
<span data-ttu-id="58018-247">Analogamente, una funzione che restituisce la composizione di due operazioni dispone della firma `((('A=>'B), ('B=>'C)) -> ('A=>'C))` .</span><span class="sxs-lookup"><span data-stu-id="58018-247">Similarly, a function that returns the composition of two operations has the signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span></span>

<span data-ttu-id="58018-248">Quando si richiama un oggetto chiamabile con parametri di tipo, tutti gli argomenti che hanno lo stesso parametro di tipo devono essere dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="58018-248">When you invoke a type-parameterized callable, all arguments that have the same type parameter must be of the same type.</span></span>

<span data-ttu-id="58018-249">:::no-loc(Q#)::: non fornisce un meccanismo per vincolare i possibili tipi che possono essere sostituiti da un utente per un parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="58018-249">:::no-loc(Q#)::: does not provide a mechanism for constraining the possible types that a user might substitute for a type parameter.</span></span>

## <a name="next-steps"></a><span data-ttu-id="58018-250">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="58018-250">Next steps</span></span>

<span data-ttu-id="58018-251">Ora che sono stati visualizzati tutti i tipi che includono il :::no-loc(Q#)::: linguaggio, vedere [espressioni di tipo in :::no-loc(Q#)::: ](xref:microsoft.quantum.guide.expressions) per informazioni su come creare e modificare le espressioni di questi diversi tipi.</span><span class="sxs-lookup"><span data-stu-id="58018-251">Now that you've seen all the types which comprise the :::no-loc(Q#)::: language, see [Type Expressions in :::no-loc(Q#):::](xref:microsoft.quantum.guide.expressions) to learn how to create and manipulate expressions of these various types.</span></span>
