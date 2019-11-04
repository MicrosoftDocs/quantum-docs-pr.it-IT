---
title: 'Modello di tipo Q # | Microsoft Docs'
description: 'Modello di tipo Q #'
author: QuantumWriter
uid: microsoft.quantum.language.type-model
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4e251053d1b8306bf8956314d8099e95c56bce55
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2019
ms.locfileid: "73184747"
---
# <a name="the-type-model"></a><span data-ttu-id="71922-103">Modello di tipo</span><span class="sxs-lookup"><span data-stu-id="71922-103">The Type Model</span></span>

<span data-ttu-id="71922-104">In questa sezione viene illustrato il modello di tipo Q # e viene descritta la sintassi per specificare e utilizzare i tipi.</span><span class="sxs-lookup"><span data-stu-id="71922-104">This section lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>
<span data-ttu-id="71922-105">Si noti che Q # è un linguaggio *fortemente tipizzato* , in modo che l'utilizzo accurato di questi tipi possa aiutare il compilatore a fornire garanzie complesse sui programmi Q # in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="71922-105">We note that Q# is a *strongly-typed* language, such that careful use of these types can help the compiler to provide strong guarantees about Q# programs at compile time.</span></span>

<span data-ttu-id="71922-106">Per garantire le migliori garanzie possibili, le conversioni tra i tipi in Q # devono essere esplicite usando chiamate a funzioni che esprimono tale conversione.</span><span class="sxs-lookup"><span data-stu-id="71922-106">In order to provide the strongest guarantees possible, conversions between types in Q# must be explicit using calls to functions which express that conversion.</span></span> <span data-ttu-id="71922-107">Una serie di funzioni di questo tipo viene fornita come parte dello spazio dei nomi <xref:microsoft.quantum.convert>.</span><span class="sxs-lookup"><span data-stu-id="71922-107">A variety of such functions are provided as a part of the <xref:microsoft.quantum.convert> namespace.</span></span>
<span data-ttu-id="71922-108">I cast ai tipi compatibili, invece, si verificano in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="71922-108">Upcasts to compatible types on the other hand happen implicitly.</span></span> 

<span data-ttu-id="71922-109">Q # fornisce entrambi i tipi primitivi, che possono essere usati direttamente e diversi modi per produrre nuovi tipi da altri tipi.</span><span class="sxs-lookup"><span data-stu-id="71922-109">Q# provides both primitive types, which can be used directly, and a variety of ways to produce new types from other types.</span></span>
<span data-ttu-id="71922-110">Ognuno viene descritto nella parte restante di questa sezione.</span><span class="sxs-lookup"><span data-stu-id="71922-110">We describe each in the rest of this section.</span></span>

## <a name="primitive-types"></a><span data-ttu-id="71922-111">Tipi primitivi</span><span class="sxs-lookup"><span data-stu-id="71922-111">Primitive Types</span></span>

<span data-ttu-id="71922-112">Il linguaggio Q # offre diversi *tipi primitivi*, da cui è possibile costruire altri tipi:</span><span class="sxs-lookup"><span data-stu-id="71922-112">The Q# language provides several *primitive types*, from which other types can be constructed:</span></span>

- <span data-ttu-id="71922-113">Il tipo di `Int` rappresenta un intero con segno a 64 bit, ad esempio: `2`, `107``-5`.</span><span class="sxs-lookup"><span data-stu-id="71922-113">The `Int` type represents a 64-bit signed integer, e.g.: `2`, `107`, `-5`.</span></span>
- <span data-ttu-id="71922-114">Il tipo di `BigInt` rappresenta un intero con segno di dimensione arbitraria, ad esempio `2L`, `107L``-5L`.</span><span class="sxs-lookup"><span data-stu-id="71922-114">The `BigInt` type represents a signed integer of arbitrary size, e.g. `2L`, `107L`, `-5L`.</span></span>
   <span data-ttu-id="71922-115">Questo tipo è basato su .NET <xref:System.Numerics.BigInteger></span><span class="sxs-lookup"><span data-stu-id="71922-115">This type is based on the .NET <xref:System.Numerics.BigInteger></span></span>
   <span data-ttu-id="71922-116">tipo.</span><span class="sxs-lookup"><span data-stu-id="71922-116">type.</span></span>
- <span data-ttu-id="71922-117">Il tipo di `Double` rappresenta un numero a virgola mobile a precisione doppia, ad esempio `0.0`, `-1.3``4e-7`.</span><span class="sxs-lookup"><span data-stu-id="71922-117">The `Double` type represents a double-precision floating-point number, e.g.: `0.0`, `-1.3`, `4e-7`.</span></span>
- <span data-ttu-id="71922-118">Il tipo di `Bool` rappresenta un valore booleano che può essere `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="71922-118">The `Bool` type represents a Boolean value which can either be `true` or `false`.</span></span>
- <span data-ttu-id="71922-119">Il tipo di `Qubit` rappresenta un bit Quantum o qubit.</span><span class="sxs-lookup"><span data-stu-id="71922-119">The `Qubit` type represents a quantum bit or qubit.</span></span>
   <span data-ttu-id="71922-120">`Qubit`s sono opachi per l'utente; l'unica operazione possibile, ad eccezione del passaggio a un'altra operazione, consiste nel testare l'identità (uguaglianza).</span><span class="sxs-lookup"><span data-stu-id="71922-120">`Qubit`s are opaque to the user; the only operation possible with them, other than passing them to another operation, is to test for identity (equality).</span></span>
   <span data-ttu-id="71922-121">Infine, le azioni su `Qubit`s vengono implementate chiamando istruzioni intrinseche su un processore quantico (o una simulazione).</span><span class="sxs-lookup"><span data-stu-id="71922-121">Ultimately, actions on `Qubit`s are implemented by calling intrinsic instructions on a quantum processor (or a simulation thereof).</span></span>
- <span data-ttu-id="71922-122">Il tipo di `Pauli` rappresenta uno dei quattro operatori Pauli a qubit singola.</span><span class="sxs-lookup"><span data-stu-id="71922-122">The `Pauli` type represents one of the four single-qubit Pauli operators.</span></span>
   <span data-ttu-id="71922-123">Questo tipo viene utilizzato per indicare l'operazione di base per le rotazioni e per specificare la misura osservabile.</span><span class="sxs-lookup"><span data-stu-id="71922-123">This type is used to denote the base operation for rotations and to specify the observable being measured.</span></span>
   <span data-ttu-id="71922-124">Si tratta di un tipo enumerato che dispone di quattro valori possibili: `PauliI`, `PauliX`, `PauliY`e `PauliZ`, che sono costanti di tipo `Pauli`.</span><span class="sxs-lookup"><span data-stu-id="71922-124">This is an enumerated type that has four possible values: `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, which are constants of type `Pauli`.</span></span>
- <span data-ttu-id="71922-125">Il tipo di `Result` rappresenta il risultato di una misura.</span><span class="sxs-lookup"><span data-stu-id="71922-125">The `Result` type represents the result of a measurement.</span></span>
   <span data-ttu-id="71922-126">Si tratta di un tipo enumerato con due valori possibili: `One` e `Zero`, che sono costanti di tipo `Result`.</span><span class="sxs-lookup"><span data-stu-id="71922-126">This is an enumerated type with two possible values: `One` and `Zero`, which are constants of type `Result`.</span></span>
   <span data-ttu-id="71922-127">`Zero` indica che è stato misurato il autovalore + 1; `One` indica il autovalore-1.</span><span class="sxs-lookup"><span data-stu-id="71922-127">`Zero` indicates that the +1 eigenvalue was measured; `One` indicates the -1 eigenvalue.</span></span>
- <span data-ttu-id="71922-128">Il tipo di `Range` rappresenta una sequenza di numeri interi, indicata da `start..step..stop`, in cui il passaggio indica che il passaggio è options.</span><span class="sxs-lookup"><span data-stu-id="71922-128">The `Range` type represents a sequence of integers, denoted by `start..step..stop`, where denoting the step is options.</span></span> 
   <span data-ttu-id="71922-129">`start .. stop` corrisponde a `start..1..stop`e, ad esempio, `1..2..7` rappresenta la sequenza $\{1, 3, 5, 7\}$.</span><span class="sxs-lookup"><span data-stu-id="71922-129">That is `start .. stop` corresponds to `start..1..stop`, and e.g. `1..2..7` represents the sequence $\{1, 3, 5, 7\}$.</span></span>
- <span data-ttu-id="71922-130">Il tipo di `String` è una sequenza di caratteri Unicode che è opaca per l'utente dopo la creazione.</span><span class="sxs-lookup"><span data-stu-id="71922-130">The `String` type is a sequence of Unicode characters that is opaque to the user once created.</span></span>
  <span data-ttu-id="71922-131">Questo tipo viene usato per segnalare i messaggi a un host classico nel caso di un evento di errore o di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="71922-131">This type is used to report messages to a classical host in the case of an error or diagnostic event.</span></span>
- <span data-ttu-id="71922-132">Il tipo di `Unit` è il tipo che consente un solo valore `()`.</span><span class="sxs-lookup"><span data-stu-id="71922-132">The `Unit` type is the type that allows only one value `()`.</span></span> 
  <span data-ttu-id="71922-133">Questo tipo viene usato per indicare che la funzione o l'operazione Q # non restituisce alcuna informazione.</span><span class="sxs-lookup"><span data-stu-id="71922-133">This type is used to indicate that Q# function or operation returns no information.</span></span> 

<span data-ttu-id="71922-134">Le costanti `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`e `Zero` sono tutti simboli riservati in Q #.</span><span class="sxs-lookup"><span data-stu-id="71922-134">The constants `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`, and `Zero` are all reserved symbols in Q#.</span></span>

## <a name="array-types"></a><span data-ttu-id="71922-135">Tipi di matrice</span><span class="sxs-lookup"><span data-stu-id="71922-135">Array Types</span></span>

<span data-ttu-id="71922-136">Dato qualsiasi `'T`di tipo Q # valido, esiste un tipo che rappresenta una matrice di valori di tipo `'T`.</span><span class="sxs-lookup"><span data-stu-id="71922-136">Given any valid Q# type `'T`, there is a type that represents an array of values of type `'T`.</span></span>
<span data-ttu-id="71922-137">Questo tipo di matrice è rappresentato come `'T[]`; ad esempio, `Qubit[]` o `Int[][]`.</span><span class="sxs-lookup"><span data-stu-id="71922-137">This array type is represented as `'T[]`; for example, `Qubit[]` or `Int[][]`.</span></span>
<span data-ttu-id="71922-138">Una raccolta di numeri interi, ad esempio, è indicata `Int[]`, mentre una matrice di matrici di valori `(Bool, Pauli)` è indicata `(Bool, Pauli)[][]`.</span><span class="sxs-lookup"><span data-stu-id="71922-138">For instance, a collection of integers is denoted `Int[]`, while an array of arrays of `(Bool, Pauli)` values is denoted `(Bool, Pauli)[][]`.</span></span>

<span data-ttu-id="71922-139">Nel secondo esempio si noti che questo rappresenta una matrice di matrici potenzialmente irregolare e non una matrice bidimensionale rettangolare.</span><span class="sxs-lookup"><span data-stu-id="71922-139">In the second example, note that this represents a potentially jagged array of arrays, and not a rectangular two-dimensional array.</span></span>
<span data-ttu-id="71922-140">Q # non fornisce il supporto per le matrici multidimensionali rettangolari.</span><span class="sxs-lookup"><span data-stu-id="71922-140">Q# does not provide support for rectangular multi-dimensional arrays.</span></span>

<span data-ttu-id="71922-141">È possibile scrivere un valore di matrice nel codice sorgente Q # usando le parentesi quadre attorno agli elementi di una matrice, come in `[PauliI, PauliX, PauliY, PauliZ]`.</span><span class="sxs-lookup"><span data-stu-id="71922-141">An array value can be written in Q# source code by using square brackets around the elements of an array, as in `[PauliI, PauliX, PauliY, PauliZ]`.</span></span>
<span data-ttu-id="71922-142">Il tipo di un valore letterale di matrice è determinato dal tipo di base comune di tutti gli elementi nella matrice.</span><span class="sxs-lookup"><span data-stu-id="71922-142">The type of an array literal is determined by the common base type of all items in the array.</span></span> 

> [!WARNING]
> <span data-ttu-id="71922-143">Gli elementi di una matrice non possono essere modificati dopo la creazione della matrice.</span><span class="sxs-lookup"><span data-stu-id="71922-143">The elements of an array cannot be changed after the array has been created.</span></span>
> <span data-ttu-id="71922-144">Per costruire una matrice modificata è possibile utilizzare le istruzioni Update-and-reassign e/o le espressioni di copia e aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="71922-144">Update-and-reassign statements and/or copy-and-update expressions can be used to construct a modified array.</span></span>

<span data-ttu-id="71922-145">In alternativa, è possibile creare una matrice dalle relative dimensioni usando la parola chiave `new`:</span><span class="sxs-lookup"><span data-stu-id="71922-145">Alternatively, an array can be created from its size using the `new` keyword:</span></span>

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

<span data-ttu-id="71922-146">In entrambi i casi, una volta costruita una matrice, è possibile usare la funzione Core `Length` per ottenere il numero di elementi come `Int`.</span><span class="sxs-lookup"><span data-stu-id="71922-146">In either case, once an array has been constructed, the core function `Length` can be used to obtain the number of elements as an `Int`.</span></span>
<span data-ttu-id="71922-147">Le matrici possono essere sottoposte a indicizzazione usando parentesi quadre, con indici di tipo `Int` o tipo `Range`, per ottenere singoli elementi o nuove matrici contenenti un subset degli elementi di una matrice.</span><span class="sxs-lookup"><span data-stu-id="71922-147">Arrays can be subscripted using square brackets, with subscripts either having type `Int` or type `Range`, to obtain either single elements or new arrays containing a subset of the elements of an array.</span></span>
<span data-ttu-id="71922-148">Gli indici delle matrici sono in base zero:</span><span class="sxs-lookup"><span data-stu-id="71922-148">The subscripts of arrays are zero-based:</span></span>

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a><span data-ttu-id="71922-149">Tipi di tupla</span><span class="sxs-lookup"><span data-stu-id="71922-149">Tuple Types</span></span>

<span data-ttu-id="71922-150">Dato zero o più tipi diversi `T0`, `T1`,... `Tn`, è possibile indicare un nuovo tipo di *tupla* come `(T0, T1, ..., Tn)`.</span><span class="sxs-lookup"><span data-stu-id="71922-150">Given zero or more different types `T0`, `T1`, ..., `Tn`, we can denote a new  *tuple type* as `(T0, T1, ..., Tn)`.</span></span>
<span data-ttu-id="71922-151">I tipi utilizzati per costruire un nuovo tipo di tupla possono essere Tuple, come in `(Int, (Qubit, Qubit))`.</span><span class="sxs-lookup"><span data-stu-id="71922-151">The types used to construct a new tuple type can themselves be tuples, as in `(Int, (Qubit, Qubit))`.</span></span>
<span data-ttu-id="71922-152">Tale annidamento è sempre finito, tuttavia, in quanto i tipi di tupla non possono in alcun caso contenere se stessi.</span><span class="sxs-lookup"><span data-stu-id="71922-152">Such nesting is always finite, however, as tuple types cannot under any circumstances contain themselves.</span></span>

<span data-ttu-id="71922-153">I valori del nuovo tipo di tupla sono Tuple costituite da sequenze di valori di ogni tipo nella tupla.</span><span class="sxs-lookup"><span data-stu-id="71922-153">Values of the new tuple type are tuples formed by sequences of values from each type in the tuple.</span></span>
<span data-ttu-id="71922-154">Ad esempio, `(3, false)` è una tupla il cui tipo è il tipo di tupla `(Int, Bool)`.</span><span class="sxs-lookup"><span data-stu-id="71922-154">For instance, `(3, false)` is a tuple whose type is the tuple type `(Int, Bool)`.</span></span>
<span data-ttu-id="71922-155">È possibile creare matrici di tuple, Tuple di matrici, Tuple di sottotuple e così via.</span><span class="sxs-lookup"><span data-stu-id="71922-155">It is possible to create arrays of tuples, tuples of arrays, tuples of sub-tuples, etc.</span></span>

<span data-ttu-id="71922-156">A partire da Q # 0,3, `Unit` è il nome del *tipo* della tupla vuota; `()` viene usato per il *valore*della tupla vuota.</span><span class="sxs-lookup"><span data-stu-id="71922-156">As of Q# 0.3, `Unit` is the name of the *type* of the empty tuple; `()` is used for the empty tuple *value*.</span></span>

<span data-ttu-id="71922-157">Le istanze di tupla non sono modificabili.</span><span class="sxs-lookup"><span data-stu-id="71922-157">Tuple instances are immutable.</span></span>
<span data-ttu-id="71922-158">Q # non fornisce un meccanismo per modificare il contenuto di una tupla una volta creata.</span><span class="sxs-lookup"><span data-stu-id="71922-158">Q# does not provide a mechanism to change the contents of a tuple once created.</span></span>

<span data-ttu-id="71922-159">Le tuple sono un concetto potente usato in Q # per raccogliere i valori in un unico valore, semplificando il passaggio.</span><span class="sxs-lookup"><span data-stu-id="71922-159">Tuples are a powerful concept used throughout Q# to collect values together into a single value, making it easier to pass them around.</span></span>
<span data-ttu-id="71922-160">In particolare, usando la notazione di tupla, possiamo esprimere che ogni operazione e Callable accetta esattamente un input e restituisce esattamente un output.</span><span class="sxs-lookup"><span data-stu-id="71922-160">In particular, using tuple notation, we can express that every operation and callable takes exactly one input and returns exactly one output.</span></span>

### <a name="singleton-tuple-equivalence"></a><span data-ttu-id="71922-161">Equivalenza della tupla singleton</span><span class="sxs-lookup"><span data-stu-id="71922-161">Singleton Tuple Equivalence</span></span>

<span data-ttu-id="71922-162">È possibile creare una tupla (a elemento singolo) singleton, `('T1)`, ad esempio `(5)` o `([1,2,3])`.</span><span class="sxs-lookup"><span data-stu-id="71922-162">It is possible to create a singleton (single-element) tuple, `('T1)`, such as `(5)` or `([1,2,3])`.</span></span>
<span data-ttu-id="71922-163">Tuttavia, Q # considera una tupla singleton come completamente equivalente a un valore del tipo racchiuso.</span><span class="sxs-lookup"><span data-stu-id="71922-163">However, Q# treats a singleton tuple as completely equivalent to a value of the enclosed type.</span></span>
<span data-ttu-id="71922-164">Ovvero, non esiste alcuna differenza tra `5` e `(5)`o tra `5` e `(((5)))`oppure tra `(5, (6))` e `(5, 6)`.</span><span class="sxs-lookup"><span data-stu-id="71922-164">That is, there is no difference between `5` and `(5)`, or between `5` and `(((5)))`, or between `(5, (6))` and `(5, 6)`.</span></span>

<span data-ttu-id="71922-165">Questa equivalenza si applica a tutti gli scopi, incluse le assegnazioni e le espressioni.</span><span class="sxs-lookup"><span data-stu-id="71922-165">This equivalence applies for all purposes, including assignment and expressions.</span></span>
<span data-ttu-id="71922-166">È altrettanto valido scrivere `(5)+3` come per scrivere `5+3`ed entrambe le espressioni restituiranno `8`.</span><span class="sxs-lookup"><span data-stu-id="71922-166">It is just as valid to write `(5)+3` as to write `5+3`, and both expressions will evaluate to `8`.</span></span>
<span data-ttu-id="71922-167">In particolare, ciò significa che un'operazione o una funzione la cui tupla di input o il tipo di tupla di output ha un campo può essere considerato come accettare un singolo argomento o restituire un singolo valore.</span><span class="sxs-lookup"><span data-stu-id="71922-167">In particular, this means that an operation or function whose input tuple or output tuple type has one field can be thought of as taking a single argument or returning a single value.</span></span>

<span data-ttu-id="71922-168">Si fa riferimento a questa proprietà come _equivalenza della tupla singleton_.</span><span class="sxs-lookup"><span data-stu-id="71922-168">We refer to this property as _singleton tuple equivalence_.</span></span>

## <a name="user-defined-types"></a><span data-ttu-id="71922-169">Tipi definiti dall'utente</span><span class="sxs-lookup"><span data-stu-id="71922-169">User-Defined Types</span></span>

<span data-ttu-id="71922-170">Un file Q # può definire un nuovo tipo denominato contenente un singolo valore di qualsiasi tipo valido.</span><span class="sxs-lookup"><span data-stu-id="71922-170">A Q# file may define a new named type containing a single value of any legal type.</span></span>
<span data-ttu-id="71922-171">Per qualsiasi tipo di tupla `T`, è possibile dichiarare un nuovo tipo definito dall'utente che è un sottotipo di `T` con l'istruzione `newtype`.</span><span class="sxs-lookup"><span data-stu-id="71922-171">For any tuple type `T`, we can declare a new user-defined type that is a subtype of `T` with the `newtype` statement.</span></span>
<span data-ttu-id="71922-172">Nello spazio dei nomi @"microsoft.quantum.canon", ad esempio, i numeri complessi sono definiti come tipo definito dall'utente:</span><span class="sxs-lookup"><span data-stu-id="71922-172">In the @"microsoft.quantum.canon" namespace, for instance, complex numbers are defined as a user-defined type:</span></span>

```qsharp
newtype Complex = (Double, Double);
```

<span data-ttu-id="71922-173">Questa istruzione crea un nuovo tipo con due elementi anonimi di tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="71922-173">This statement creates a new type with two anonymous items of type `Double`.</span></span>   
<span data-ttu-id="71922-174">A parte gli elementi anonimi, i tipi definiti dall'utente supportano anche gli elementi denominati a partire da Q # versione 0,7 o successiva.</span><span class="sxs-lookup"><span data-stu-id="71922-174">Aside from anonymous items, user defined types also support named items as of Q# version 0.7 or higher.</span></span> <span data-ttu-id="71922-175">Ad esempio, avremmo potuto denominare gli elementi `Re` per il valore Double che rappresenta la parte reale di un numero complesso e `Im` per la parte immaginaria:</span><span class="sxs-lookup"><span data-stu-id="71922-175">For example, we could have named the to items `Re` for the double representing the real part of a complex number and `Im` for the imaginary part:</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="71922-176">La denominazione di un elemento in un tipo definito dall'utente non implica che tutti gli elementi devono essere denominati. è supportata qualsiasi combinazione di elementi denominati e non denominati.</span><span class="sxs-lookup"><span data-stu-id="71922-176">Naming one item in a user defined type does not imply that all items need to be named - any combination of named and unnamed items is supported.</span></span> <span data-ttu-id="71922-177">Inoltre, gli elementi interni possono essere denominati.</span><span class="sxs-lookup"><span data-stu-id="71922-177">Furthermore, also inner items may be named.</span></span>
<span data-ttu-id="71922-178">Il tipo `Nested` come definito di seguito, ad esempio, ha un tipo sottostante `(Double, (Int, String))`, di cui solo l'elemento di tipo `Int` è denominato e tutti gli altri elementi sono anonimi.</span><span class="sxs-lookup"><span data-stu-id="71922-178">The type `Nested` as defined below for example has an underlying type `(Double, (Int, String))`, of which only the item of type `Int` is named and all other items are anonymous.</span></span> 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```
<span data-ttu-id="71922-179">Gli elementi denominati hanno il vantaggio di poter accedere direttamente tramite l'operatore di accesso `::`.</span><span class="sxs-lookup"><span data-stu-id="71922-179">Named items have the advantage that they can be accessed directly via the access operator `::`.</span></span> 

```qsharp
function Addition (c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

<span data-ttu-id="71922-180">Per accedere agli elementi anonimi, è necessario innanzitutto estrarre il valore di cui è stato eseguito il wrapped utilizzando l'operatore di suffisso `!`.</span><span class="sxs-lookup"><span data-stu-id="71922-180">In order to access anonymous items on the other hand, the wrapped value first needs to be extracted using the postfix operator `!`.</span></span>
<span data-ttu-id="71922-181">L'operatore "Unwrap", `!`, consente di estrarre il valore contenuto in un tipo definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="71922-181">The "unwrap" operator, `!`, allows to extract the value contained in a user defined type.</span></span>
<span data-ttu-id="71922-182">Il tipo di un'espressione "Unwrap" è il tipo sottostante del tipo definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="71922-182">The type of such an "unwrap" expression is the underlying type of the user defined type.</span></span> 

```qsharp
function PrintMsg (value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

<span data-ttu-id="71922-183">L'operatore Unwrap Annulla il wrapping di un solo livello di wrapping.</span><span class="sxs-lookup"><span data-stu-id="71922-183">The unwrap operator unwraps exactly one layer of wrapping.</span></span>
<span data-ttu-id="71922-184">È possibile utilizzare più operatori Unwrap per accedere a un valore con wrapping multiplo.</span><span class="sxs-lookup"><span data-stu-id="71922-184">Multiple unwrap operators may be used to access a multiply-wrapped value.</span></span>

<span data-ttu-id="71922-185">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="71922-185">For instance:</span></span>

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

<span data-ttu-id="71922-186">Per altri dettagli, vedere la sezione relativa alla [precedenza degli operatori](xref:microsoft.quantum.language.expressions#operator-precedence) e delle [espressioni Unwrap](xref:microsoft.quantum.language.expressions#unwrap-expressions) .</span><span class="sxs-lookup"><span data-stu-id="71922-186">Take a look at the section on [unwrap expressions](xref:microsoft.quantum.language.expressions#unwrap-expressions) and [operators precedence](xref:microsoft.quantum.language.expressions#operator-precedence) for more details.</span></span>

<span data-ttu-id="71922-187">I valori di un tipo definito dall'utente possono essere creati chiamando il costruttore del tipo corrispondente:</span><span class="sxs-lookup"><span data-stu-id="71922-187">Values of a user defined type can be created by calling the corresponding type constructor:</span></span>

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

<span data-ttu-id="71922-188">In alternativa, è possibile creare nuovi valori da quelli esistenti usando [le espressioni di copia e aggiornamento](xref:microsoft.quantum.language.expressions#copy-and-update-expressions).</span><span class="sxs-lookup"><span data-stu-id="71922-188">Alternatively, new values can be created from existing ones using [copy-and-update expressions](xref:microsoft.quantum.language.expressions#copy-and-update-expressions).</span></span> <span data-ttu-id="71922-189">Analogamente alle matrici, tali espressioni copiano tutti i valori degli elementi dell'espressione originale, ad eccezione degli elementi denominati specificati.</span><span class="sxs-lookup"><span data-stu-id="71922-189">Like for arrays, such expressions copy all item values of the original expression, with the exception of the specified named items.</span></span> <span data-ttu-id="71922-190">Per questi valori, i valori vengono impostati su quelli definiti sul lato destro dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="71922-190">For these the values are set to the ones defined on the right hand side of the expression.</span></span> <span data-ttu-id="71922-191">Tutti gli altri costrutti di linguaggio, come ad esempio le [istruzioni Update-and-reassign](xref:microsoft.quantum.language.statements#update-and-reassign-statement), disponibili per gli elementi della matrice esistono anche per gli elementi denominati nei tipi definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="71922-191">Any other language constructs, like for example [update-and-reassign statements](xref:microsoft.quantum.language.statements#update-and-reassign-statement), that are available for array items exist for named-items in user defined types as well.</span></span>

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

<span data-ttu-id="71922-192">I tipi definiti dall'utente possono essere usati ovunque sia possibile usare qualsiasi altro tipo.</span><span class="sxs-lookup"><span data-stu-id="71922-192">User-defined types may be used anywhere any other type may be used.</span></span>
<span data-ttu-id="71922-193">In particolare, è possibile definire una matrice di un tipo definito dall'utente e includere un tipo definito dall'utente come elemento di un tipo di tupla.</span><span class="sxs-lookup"><span data-stu-id="71922-193">In particular, it is possible to define an array of a user-defined type and to include a user-defined type as an element of a tuple type.</span></span>

<span data-ttu-id="71922-194">Non è possibile creare strutture di tipo ricorsivo.</span><span class="sxs-lookup"><span data-stu-id="71922-194">It is not possible to create recursive type structures.</span></span>
<span data-ttu-id="71922-195">Ovvero, il tipo che definisce un tipo definito dall'utente non può essere un tipo di tupla che include un elemento del tipo definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="71922-195">That is, the type that defines a user-defined type may not be a tuple type that includes an element of the user-defined type.</span></span>
<span data-ttu-id="71922-196">Più in generale, i tipi definiti dall'utente potrebbero non avere dipendenze cicliche tra loro, quindi il set di definizioni di tipi seguente non è valido:</span><span class="sxs-lookup"><span data-stu-id="71922-196">More generally, user-defined types may not have cyclic dependencies on each other, so the following set of type definitions would be illegal:</span></span>

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```

<span data-ttu-id="71922-197">Oltre a fornire alias brevi per i tipi di tupla potenzialmente complessi, un vantaggio significativo della definizione di tali tipi è che possono documentare lo scopo di un determinato valore.</span><span class="sxs-lookup"><span data-stu-id="71922-197">In addition to providing short aliases for potentially complicated tuple types, one significant advantage of defining such types is that they can document the intent of a particular value.</span></span>
<span data-ttu-id="71922-198">Tornando all'esempio di `Complex`, è possibile definire anche le coordinate polari 2D come tipo definito dall'utente:</span><span class="sxs-lookup"><span data-stu-id="71922-198">Returning to the example of `Complex`, one could have also defined 2D polar coordinates as a user-defined type:</span></span>

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

<span data-ttu-id="71922-199">Anche se sia `Complex` che `Polar` hanno entrambi un tipo sottostante `(Double, Double)`, i due tipi sono completamente incompatibili in Q #, riducendo al minimo il rischio di chiamare accidentalmente una funzione matematica complessa con coordinate polari e viceversa.</span><span class="sxs-lookup"><span data-stu-id="71922-199">Even though both `Complex` and `Polar` are both have an underlying type `(Double, Double)`, the two types are wholly incompatible in Q#, minimizing the risk of accidentally calling a complex math function with polar coordinates and vice versa.</span></span>
<span data-ttu-id="71922-200">In questo modo, i tipi definiti dall'utente hanno un ruolo simile a quello F# dei record in, ad esempio.</span><span class="sxs-lookup"><span data-stu-id="71922-200">In this way, user-defined types have a similar role as Records in F# for example.</span></span> 


## <a name="operation-and-function-types"></a><span data-ttu-id="71922-201">Tipi di operazioni e funzioni</span><span class="sxs-lookup"><span data-stu-id="71922-201">Operation and Function Types</span></span>

<span data-ttu-id="71922-202">Un' _operazione_ Q # è una subroutine Quantum.</span><span class="sxs-lookup"><span data-stu-id="71922-202">A Q# _operation_ is a quantum subroutine.</span></span>
<span data-ttu-id="71922-203">Ovvero una routine chiamabile che contiene operazioni Quantum.</span><span class="sxs-lookup"><span data-stu-id="71922-203">That is, it is a callable routine that contains quantum operations.</span></span>

<span data-ttu-id="71922-204">Una _funzione_ Q # è una subroutine classica usata all'interno di un algoritmo Quantum.</span><span class="sxs-lookup"><span data-stu-id="71922-204">A Q# _function_ is a classical subroutine used within a quantum algorithm.</span></span>
<span data-ttu-id="71922-205">Può contenere codice classico, ma nessuna operazione quantistica.</span><span class="sxs-lookup"><span data-stu-id="71922-205">It may contain classical code but no quantum operations.</span></span>
<span data-ttu-id="71922-206">In particolare, le funzioni non possono allocare o prendere in prestito qubits, né possono chiamare operazioni.</span><span class="sxs-lookup"><span data-stu-id="71922-206">Specifically, functions may not allocate or borrow qubits, nor may they call operations.</span></span>
<span data-ttu-id="71922-207">È tuttavia possibile passare le operazioni o qubits per l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="71922-207">It is possible, however, to pass them operations or qubits for processing.</span></span>
<span data-ttu-id="71922-208">Le funzioni sono quindi completamente deterministiche, nel senso che la chiamata con gli stessi argomenti genererà sempre lo stesso risultato.</span><span class="sxs-lookup"><span data-stu-id="71922-208">Functions are thus entirely deterministic in the sense that calling them with the same arguments will always produce the same result.</span></span> 

<span data-ttu-id="71922-209">Insieme, le operazioni e le funzioni vengono chiamate _Callable_.</span><span class="sxs-lookup"><span data-stu-id="71922-209">Together, operations and functions are called _callables_.</span></span>  <span data-ttu-id="71922-210">È possibile vedere alcuni [esempi](#examples) di questi esempi.</span><span class="sxs-lookup"><span data-stu-id="71922-210">You can see some [examples](#examples) of these below.</span></span>

<span data-ttu-id="71922-211">Tutti i chiamanti Q # sono considerati come input e restituiscono un singolo valore come output.</span><span class="sxs-lookup"><span data-stu-id="71922-211">All Q# callables are considered to take a single value as input and return a single value as output.</span></span>
<span data-ttu-id="71922-212">Sia i valori di input che quelli di output possono essere Tuple.</span><span class="sxs-lookup"><span data-stu-id="71922-212">Both the input and output values may be tuples.</span></span>
<span data-ttu-id="71922-213">Chiamabili senza risultato restituito `Unit`.</span><span class="sxs-lookup"><span data-stu-id="71922-213">Callables that have no result return `Unit`.</span></span>
<span data-ttu-id="71922-214">Le chiamabili senza input accettano la tupla vuota come input.</span><span class="sxs-lookup"><span data-stu-id="71922-214">Callables that have no input take the empty tuple as input.</span></span>

<span data-ttu-id="71922-215">Il tipo di base per qualsiasi chiamata chiamabile viene scritto come `('Tinput => 'Tresult)` o `('Tinput -> 'Tresult)`, in cui sia `'Tinput` che `'Tresult` sono tipi.</span><span class="sxs-lookup"><span data-stu-id="71922-215">The basic type for any callable is written as `('Tinput => 'Tresult)` or `('Tinput -> 'Tresult)`, where both `'Tinput` and `'Tresult` are types.</span></span>
<span data-ttu-id="71922-216">Il primo form, con `=>`, viene usato per le operazioni; secondo form, con `->`, per le funzioni.</span><span class="sxs-lookup"><span data-stu-id="71922-216">The first form, with `=>`, is used for operations; the second form, with `->`, for functions.</span></span>
<span data-ttu-id="71922-217">Ad esempio, `((Qubit, Pauli) => Result)` rappresenta la firma per una possibile operazione di misurazione a qubit singola.</span><span class="sxs-lookup"><span data-stu-id="71922-217">For example, `((Qubit, Pauli) => Result)` represents the signature for a possible single-qubit measurement operation.</span></span>

<span data-ttu-id="71922-218">I tipi di funzione sono completamente specificati dalla relativa firma.</span><span class="sxs-lookup"><span data-stu-id="71922-218">Function types are completely specified by their signature.</span></span>
<span data-ttu-id="71922-219">Ad esempio, una funzione che calcola il seno di un angolo avrà il tipo `(Double -> Double)`.</span><span class="sxs-lookup"><span data-stu-id="71922-219">For example, a function that computes the sine of an angle would have type `(Double -> Double)`.</span></span>

<span data-ttu-id="71922-220">Le operazioni, ma non le funzioni, hanno determinate _caratteristiche_ aggiuntive espresse come parte del tipo di operazione.</span><span class="sxs-lookup"><span data-stu-id="71922-220">Operations—but not functions—have certain additional _characteristics_ that are expressed as part of the operation type.</span></span> <span data-ttu-id="71922-221">Tali caratteristiche includono informazioni sul funtori supportato dall'operazione.</span><span class="sxs-lookup"><span data-stu-id="71922-221">Such characteristics include information about what functors the operation supports.</span></span>
<span data-ttu-id="71922-222">Funtori sono metaoperazioni che generano una specializzazione di un'operazione di base. vedere [funtori](#functors), di seguito.</span><span class="sxs-lookup"><span data-stu-id="71922-222">Functors are meta-operations that generate a specialization of a base operation; see [Functors](#functors), below.</span></span>

<span data-ttu-id="71922-223">I tipi di operazione sono specificati dal tipo di input, dal tipo di output e dalle relative caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="71922-223">Operation types are specified by the their input type, output type, and their characteristics.</span></span>    
<span data-ttu-id="71922-224">Per richiedere il supporto per il `Controlled` e/o l'`Adjoint` functore in un tipo di operazione, è necessario aggiungere un'annotazione che indichi le caratteristiche corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="71922-224">In order to require support for the `Controlled` and/or `Adjoint` functor in an operation type, we need to add an annotation indicating the corresponding characteristics.</span></span>
<span data-ttu-id="71922-225">Un'annotazione `is Ctl` ad esempio indica che l'operazione è controllabile.</span><span class="sxs-lookup"><span data-stu-id="71922-225">An annotation `is Ctl` for example indicates that the operation is controllable.</span></span> <span data-ttu-id="71922-226">Se si vuole richiedere che un'operazione di quel tipo supporti sia il `Adjoint` che il functore di `Controlled`, è possibile esprimere questo tipo di `(Qubit => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="71922-226">If we want to require that an operation of that type supports both the `Adjoint` and `Controlled` functor we can express this as `(Qubit => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="71922-227">Le caratteristiche dell'operazione utilizzate `Adj` e `Ctl` in modo rigoroso sono due set predefiniti di etichette, in cui ogni etichetta indica determinate caratteristiche dell'operazione, ad esempio il supporto per un particolare functore.</span><span class="sxs-lookup"><span data-stu-id="71922-227">The used operation characteristics `Adj` and `Ctl` strictly speaking are two pre-defined sets of labels, where each label indicates a particular operation characteristics like e.g. support for a particular functor.</span></span>
<span data-ttu-id="71922-228">Di conseguenza, `+` viene usato per indicare l'Unione di questi due set e viene usato `*` per indicare l'intersezione, ovvero le etichette comuni a entrambi i set.</span><span class="sxs-lookup"><span data-stu-id="71922-228">Hence, `+` is used to indicate the union of those two sets, and `*` is used to indicate the intersection - i.e. the labels that are common to both sets.</span></span>  

<span data-ttu-id="71922-229">Ad esempio, l'operazione di `X` di Pauli è di tipo `(Qubit => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="71922-229">For example, the Pauli `X` operation has type `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="71922-230">Un tipo di operazione che non supporta alcun funtori viene specificato solo dal tipo di input e di output, senza alcuna annotazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="71922-230">An operation type that does not support any functors is specified by its input and output type alone, with no additional annotation.</span></span>


### <a name="type-parameterized-functions-and-operations"></a><span data-ttu-id="71922-231">Funzioni e operazioni con parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="71922-231">Type-Parameterized Functions and Operations</span></span>

<span data-ttu-id="71922-232">I tipi chiamabili possono contenere parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="71922-232">Callable types may contain type parameters.</span></span>
<span data-ttu-id="71922-233">I parametri di tipo sono indicati da un simbolo preceduto da una virgoletta singola; ad esempio, `'A` è un parametro di tipo valido.</span><span class="sxs-lookup"><span data-stu-id="71922-233">Type parameters are indicated by a symbol prefixed by a single quote; for example, `'A` is a legal type parameter.</span></span>

<span data-ttu-id="71922-234">Un parametro di tipo può essere visualizzato più di una volta in un'unica firma.</span><span class="sxs-lookup"><span data-stu-id="71922-234">A type parameter may appear more than once in a single signature.</span></span>
<span data-ttu-id="71922-235">Ad esempio, una funzione che applica un'altra funzione a ogni elemento di una matrice e restituisce i risultati raccolti avrebbe la firma `(('A[], 'A->'A) -> 'A[])`.</span><span class="sxs-lookup"><span data-stu-id="71922-235">For example, a function that applies another function to each element of an array and returns the collected results would have signature `(('A[], 'A->'A) -> 'A[])`.</span></span>
<span data-ttu-id="71922-236">Analogamente, una funzione che restituisce la composizione di due operazioni potrebbe avere la firma `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span><span class="sxs-lookup"><span data-stu-id="71922-236">Similarly, a function that returns the composition of two operations might have signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span></span>

<span data-ttu-id="71922-237">Quando si richiama un oggetto chiamabile con parametri di tipo, tutti gli argomenti che hanno lo stesso parametro di tipo devono essere dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="71922-237">When invoking a type-parameterized callable, all arguments that have the same type parameter must be of the same type.</span></span>

<span data-ttu-id="71922-238">Q # non fornisce un meccanismo per vincolare i possibili tipi che possono essere sostituiti per un parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="71922-238">Q# does not provide a mechanism for constraining the possible types that might be substituted for a type parameter.</span></span>

### <a name="type-compatibility"></a><span data-ttu-id="71922-239">Compatibilità tra tipi</span><span class="sxs-lookup"><span data-stu-id="71922-239">Type Compatibility</span></span>

<span data-ttu-id="71922-240">Un'operazione con funtori aggiuntivi supportata può essere usata ovunque un'operazione con un numero di funtori inferiore ma è prevista la stessa firma.</span><span class="sxs-lookup"><span data-stu-id="71922-240">An operation with additional functors supported may be used anywhere an operation with fewer functors but the same signature is expected.</span></span>
<span data-ttu-id="71922-241">Ad esempio, un'operazione di tipo `(Qubit => Unit is Adj)` può essere utilizzata ovunque sia prevista un'operazione di tipo `(Qubit => Unit)`.</span><span class="sxs-lookup"><span data-stu-id="71922-241">For instance, an operation of type `(Qubit => Unit is Adj)` may be used anywhere an operation of type `(Qubit => Unit)` is expected.</span></span>

<span data-ttu-id="71922-242">Q # è covariante rispetto ai tipi restituiti richiamabili: un chiamabile che restituisce un tipo `'A` è compatibile con un oggetto chiamabile con lo stesso tipo di input e un tipo di risultato con cui `'A` è compatibile.</span><span class="sxs-lookup"><span data-stu-id="71922-242">Q# is covariant with respect to callable return types: a callable that returns a type `'A` is compatible with a callable with the same input type and a result type that `'A` is compatible with.</span></span>

<span data-ttu-id="71922-243">Q # è controvariante rispetto ai tipi di input: un oggetto chiamabile che accetta un tipo `'A` come input è compatibile con un oggetto chiamabile con lo stesso tipo di risultato e un tipo di input compatibile con `'A`.</span><span class="sxs-lookup"><span data-stu-id="71922-243">Q# is contravariant with respect to input types: a callable that takes a type `'A` as input is compatible with a callable with the same result type and an input type that is compatible with `'A`.</span></span>

<span data-ttu-id="71922-244">Ovvero, date le seguenti definizioni:</span><span class="sxs-lookup"><span data-stu-id="71922-244">That is, given the following definitions:</span></span>

```qsharp
operation Invertible (qs : Qubit[]) : Unit 
is Adj {...} 
operation Unitary (qs : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertibleWith (
   inner: (Qubit[] => Unit is Adj),
   outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith (
   inner: (Qubit[] => Unit is Adj + Ctl),
   outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

<span data-ttu-id="71922-245">sono soddisfatte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="71922-245">the following are true:</span></span>

- <span data-ttu-id="71922-246">Il `ConjugateInvertibleWith` di operazione può essere richiamato con un argomento `inner` di `Invertible` o `Unitary`.</span><span class="sxs-lookup"><span data-stu-id="71922-246">The operation `ConjugateInvertibleWith` may be invoked with an `inner` argument of either `Invertible` or `Unitary`.</span></span>
- <span data-ttu-id="71922-247">Il `ConjugateUnitaryWith` di operazione può essere richiamato con un argomento `inner` di `Unitary`, ma non `Invertible`.</span><span class="sxs-lookup"><span data-stu-id="71922-247">The operation `ConjugateUnitaryWith` may be invoked with an `inner` argument of `Unitary`, but not `Invertible`.</span></span>
- <span data-ttu-id="71922-248">Da `ConjugateInvertibleWith`può essere restituito un valore di tipo `(Qubit[] => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="71922-248">A value of type `(Qubit[] => Unit is Adj + Ctl)` may be returned from `ConjugateInvertibleWith`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71922-249">Q # 0,3 introduce una differenza significativa nel comportamento dei tipi definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="71922-249">Q# 0.3 introduces a significant difference in the behavior of user-defined types.</span></span>

<span data-ttu-id="71922-250">I tipi definiti dall'utente vengono considerati come una versione di cui è stato eseguito il wrapped del tipo sottostante, anziché come sottotipo.</span><span class="sxs-lookup"><span data-stu-id="71922-250">User-defined types are treated as a wrapped version of the underlying type, rather than as a subtype.</span></span>
<span data-ttu-id="71922-251">Ciò significa che un valore di un tipo definito dall'utente non può essere utilizzato quando è previsto un valore del tipo sottostante.</span><span class="sxs-lookup"><span data-stu-id="71922-251">This means that a value of a user-defined type is not usable where a value of the underlying type is expected.</span></span>

### <a name="functors"></a><span data-ttu-id="71922-252">Funtori</span><span class="sxs-lookup"><span data-stu-id="71922-252">Functors</span></span>

<span data-ttu-id="71922-253">Un functor in Q # è una factory che definisce una nuova operazione da un'altra operazione.</span><span class="sxs-lookup"><span data-stu-id="71922-253">A functor in Q# is a factory that defines a new operation from another operation.</span></span>
<span data-ttu-id="71922-254">Funtori hanno accesso all'implementazione dell'operazione di base quando si definisce l'implementazione della nuova operazione.</span><span class="sxs-lookup"><span data-stu-id="71922-254">Functors have access to the implementation of the base operation when defining the implementation of the new operation.</span></span>
<span data-ttu-id="71922-255">Funtori può quindi eseguire funzioni più complesse rispetto alle funzioni di livello superiore tradizionali.</span><span class="sxs-lookup"><span data-stu-id="71922-255">Thus, functors can perform more complex functions than traditional higher-level functions.</span></span>

<span data-ttu-id="71922-256">Funtori non dispone di una rappresentazione nel sistema di tipi Q #.</span><span class="sxs-lookup"><span data-stu-id="71922-256">Functors do not have a representation in the Q# type system.</span></span> <span data-ttu-id="71922-257">Attualmente non è possibile associarli a una variabile o passarli come argomenti.</span><span class="sxs-lookup"><span data-stu-id="71922-257">It is thus currently not possible to bind them to a variable or pass them as arguments.</span></span> 

<span data-ttu-id="71922-258">Un functor viene usato applicando l'oggetto a un'operazione, restituendo una nuova operazione.</span><span class="sxs-lookup"><span data-stu-id="71922-258">A functor is used by applying it to an operation, returning a new operation.</span></span>
<span data-ttu-id="71922-259">Ad esempio, l'operazione risultante dall'applicazione del `Adjoint` functore all'operazione `Y` viene scritta come `Adjoint Y`.</span><span class="sxs-lookup"><span data-stu-id="71922-259">For example, the operation that results from applying the `Adjoint` functor to the `Y` operation is written as `Adjoint Y`.</span></span>
<span data-ttu-id="71922-260">La nuova operazione può quindi essere richiamata come qualsiasi altra operazione.</span><span class="sxs-lookup"><span data-stu-id="71922-260">The new operation may then be invoked like any other operation.</span></span>
<span data-ttu-id="71922-261">Pertanto, `Adjoint Y(q1)` applica il functor adiacente all'operazione `Y` per generare una nuova operazione e applica tale nuova operazione al `q1`.</span><span class="sxs-lookup"><span data-stu-id="71922-261">Thus, `Adjoint Y(q1)` applies the Adjoint functor to the `Y` operation to generate a new operation, and applies that new operation to `q1`.</span></span>

<span data-ttu-id="71922-262">Allo stesso modo, `Controlled X(controls, target)` applica il functor controllato all'operazione `X` per generare una nuova operazione e applica tale nuova operazione a `controls` e `target`.</span><span class="sxs-lookup"><span data-stu-id="71922-262">Similarly, `Controlled X(controls, target)` applies the Controlled functor to the `X` operation to generate a new operation, and applies that new operation to `controls` and `target`.</span></span>

<span data-ttu-id="71922-263">I due funtori standard in Q # sono `Adjoint` e `Controlled`.</span><span class="sxs-lookup"><span data-stu-id="71922-263">The two standard functors in Q# are `Adjoint` and `Controlled`.</span></span>

#### <a name="adjoint"></a><span data-ttu-id="71922-264">Adjoint</span><span class="sxs-lookup"><span data-stu-id="71922-264">Adjoint</span></span>

<span data-ttu-id="71922-265">In quantum computing, il contiguo di un'operazione è la trasportazione complessa del coniugato dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="71922-265">In quantum computing, the adjoint of an operation is the complex conjugate transpose of the operation.</span></span>
<span data-ttu-id="71922-266">Per le operazioni che implementano un operatore unitario, l'elemento contiguo è l'inverso dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="71922-266">For operations that implement a unitary operator, the adjoint is the inverse of the operation.</span></span>
<span data-ttu-id="71922-267">Per un'operazione semplice che richiama solo una sequenza di altre operazioni Unite su un set di qubits, l'elemento contiguo può essere calcolato applicando gli elementi adiacenti delle sottooperazioni nello stesso qubits, nella sequenza inversa.</span><span class="sxs-lookup"><span data-stu-id="71922-267">For a simple operation that just invokes a sequence of other unitary operations on a set of qubits, the adjoint may be computed by applying the adjoints of the sub-operations on the same qubits, in the reverse sequence.</span></span>

<span data-ttu-id="71922-268">Data un'espressione di operazione, è possibile formare una nuova espressione di operazione usando il `Adjoint` functor.</span><span class="sxs-lookup"><span data-stu-id="71922-268">Given an operation expression, a new operation expression may be formed using the `Adjoint` functor.</span></span>
<span data-ttu-id="71922-269">Ad esempio, `Adjoint QFT` definisce il contiguo dell'operazione di `QFT`.</span><span class="sxs-lookup"><span data-stu-id="71922-269">For instance, `Adjoint QFT` designates the adjoint of the `QFT` operation.</span></span>
<span data-ttu-id="71922-270">La nuova operazione ha la stessa firma e il tipo dell'operazione di base.</span><span class="sxs-lookup"><span data-stu-id="71922-270">The new operation has the same signature and type as the base operation.</span></span>
<span data-ttu-id="71922-271">In particolare, la nuova operazione consente anche `Adjoint`e consentirà `Controlled` solo se è stata eseguita l'operazione di base.</span><span class="sxs-lookup"><span data-stu-id="71922-271">In particular, the new operation also allows `Adjoint`, and will allow `Controlled` if and only if the base operation did.</span></span>

<span data-ttu-id="71922-272">Il functor contiguo è il proprio inverso; ovvero, `Adjoint Adjoint Op` è sempre uguale `Op`.</span><span class="sxs-lookup"><span data-stu-id="71922-272">The Adjoint functor is its own inverse; that is, `Adjoint Adjoint Op` is always the same as `Op`.</span></span>

#### <a name="controlled"></a><span data-ttu-id="71922-273">Controllato</span><span class="sxs-lookup"><span data-stu-id="71922-273">Controlled</span></span>

<span data-ttu-id="71922-274">La versione controllata di un'operazione è una nuova operazione che applica efficacemente l'operazione di base solo se tutti i qubits di controllo si trovano in uno stato specificato.</span><span class="sxs-lookup"><span data-stu-id="71922-274">The controlled version of an operation is a new operation that effectively applies the base operation only if all of the control qubits are in a specified state.</span></span>
<span data-ttu-id="71922-275">Se il controllo qubits si trova in una posizione sovraposizionata, l'operazione di base viene applicata in modo coerente alla parte appropriata della superposizione.</span><span class="sxs-lookup"><span data-stu-id="71922-275">If the control qubits are in superposition, then the base operation is applied coherently to the appropriate part of the superposition.</span></span>
<span data-ttu-id="71922-276">In questo modo, le operazioni controllate vengono spesso usate per generare il groviglio.</span><span class="sxs-lookup"><span data-stu-id="71922-276">Thus, controlled operations are often used to generate entanglement.</span></span>

<span data-ttu-id="71922-277">In Q #, le versioni controllate accettano sempre una matrice di qubits di controllo e lo stato specificato è sempre per tutti i qubits del controllo in modo che siano nello stato del `One` computazionale (`PauliZ`), $ \ket{1}$.</span><span class="sxs-lookup"><span data-stu-id="71922-277">In Q#, controlled versions always take an array of control qubits, and the specified state is always for all of the control qubits to be in the computational (`PauliZ`) `One` state, $\ket{1}$.</span></span>
<span data-ttu-id="71922-278">Il controllo basato su altri Stati può essere ottenuto applicando l'operazione unitaria appropriata al controllo qubits prima dell'operazione controllata, quindi applicando gli inversi dell'operazione unitaria dopo l'operazione controllata.</span><span class="sxs-lookup"><span data-stu-id="71922-278">Controlling based on other states may be achieved by applying the appropriate unitary operation to the control qubits before the controlled operation, and then applying the inverses of the unitary operation after the controlled operation.</span></span>
<span data-ttu-id="71922-279">Se ad esempio si applica un'operazione `X` a un controllo qubit prima e dopo un'operazione controllata, l'operazione verrà controllata sullo stato `Zero` ($ \ket{0}$) per tale qubit; l'applicazione di un'operazione di `H` prima e dopo controllerà lo stato di `One` `PauliX`, ovvero-1 autovalore di Pauli X, $ \ket{-} \mathrel{: =} (\ket{0}-\ket{1})/\sqrt{2}$ anziché lo stato `PauliZ` `One`.</span><span class="sxs-lookup"><span data-stu-id="71922-279">For example, applying an `X` operation to a control qubit before and after a controlled operation will cause the operation to control on the `Zero` state ($\ket{0}$) for that qubit; applying an `H` operation before and after will control on the `PauliX` `One` state, that is -1 eigenvalue of Pauli X, $\ket{-} \mathrel{:=} (\ket{0} - \ket{1}) / \sqrt{2}$ rather than the `PauliZ` `One` state.</span></span>

<span data-ttu-id="71922-280">Data un'espressione di operazione, è possibile formare una nuova espressione di operazione usando il `Controlled` functor.</span><span class="sxs-lookup"><span data-stu-id="71922-280">Given an operation expression, a new operation expression may be formed using the `Controlled` functor.</span></span>
<span data-ttu-id="71922-281">La firma della nuova operazione si basa sulla firma dell'operazione originale.</span><span class="sxs-lookup"><span data-stu-id="71922-281">The signature of the new operation is based on the signature of the original operation.</span></span>
<span data-ttu-id="71922-282">Il tipo di risultato è lo stesso, ma il tipo di input è una tupla con due tuple con una matrice qubit che include i qubit del controllo come primo elemento e gli argomenti dell'operazione originale come secondo elemento.</span><span class="sxs-lookup"><span data-stu-id="71922-282">The result type is the same, but the input type is a two-tuple with a qubit array that holds the control qubit(s) as the first element and the arguments of the original operation as the second element.</span></span>
<span data-ttu-id="71922-283">La nuova operazione supporta `Controlled`e supporterà `Adjoint` solo se l'operazione originale è stata eseguita.</span><span class="sxs-lookup"><span data-stu-id="71922-283">The new operation supports `Controlled`, and will support `Adjoint` if and only if the original operation did.</span></span>

<span data-ttu-id="71922-284">Se l'operazione originale ha accettato un solo argomento, l'equivalenza della tupla singleton entrerà in gioco qui.</span><span class="sxs-lookup"><span data-stu-id="71922-284">If the original operation took only a single argument, then singleton tuple equivalence will come into play here.</span></span>
<span data-ttu-id="71922-285">Ad esempio, `Controlled X` è la versione controllata dell'operazione di `X`.</span><span class="sxs-lookup"><span data-stu-id="71922-285">For instance, `Controlled X` is the controlled version of the `X` operation.</span></span>
<span data-ttu-id="71922-286">`X` è di tipo `(Qubit => Unit is Adj + Ctl)`, quindi `Controlled X` è di tipo `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; a causa dell'equivalenza della tupla singleton, questo è lo stesso `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="71922-286">`X` has type `(Qubit => Unit is Adj + Ctl)`, so `Controlled X` has type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; because of singleton tuple equivalence, this is the same as `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="71922-287">Se l'operazione di base ha assunto diversi argomenti, ricordarsi di racchiudere tra parentesi gli argomenti corrispondenti della versione controllata dell'operazione per convertirli in una tupla.</span><span class="sxs-lookup"><span data-stu-id="71922-287">If the base operation took several arguments, remember to enclose the corresponding arguments of the controlled version of the operation in parentheses to convert them into a tuple.</span></span>
<span data-ttu-id="71922-288">Ad esempio, `Controlled Rz` è la versione controllata dell'operazione di `Rz`.</span><span class="sxs-lookup"><span data-stu-id="71922-288">For instance, `Controlled Rz` is the controlled version of the `Rz` operation.</span></span>
<span data-ttu-id="71922-289">`Rz` è di tipo `((Double, Qubit) => Unit is Adj + Ctl)`, quindi `Controlled Rz` ha il tipo `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="71922-289">`Rz` has type `((Double, Qubit) => Unit is Adj + Ctl)`, so `Controlled Rz` has type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="71922-290">Pertanto, `Controlled Rz(controls, (0.1, target))` sarebbe una chiamata valida di `Controlled Rz` (si notino le parentesi intorno `0.1, target`).</span><span class="sxs-lookup"><span data-stu-id="71922-290">Thus, `Controlled Rz(controls, (0.1, target))` would be a valid invocation of `Controlled Rz` (note the parentheses around `0.1, target`).</span></span>

<span data-ttu-id="71922-291">Come altro esempio, `CNOT(control, target)` può essere implementato come `Controlled X([control], target)`.</span><span class="sxs-lookup"><span data-stu-id="71922-291">As another example, `CNOT(control, target)` can be implemented as `Controlled X([control], target)`.</span></span> <span data-ttu-id="71922-292">Se una destinazione deve essere controllata da 2 Control qubits (CCNOT), è possibile usare `Controlled X([control1, control2], target)` istruzione.</span><span class="sxs-lookup"><span data-stu-id="71922-292">If a target should be controlled by 2 control qubits (CCNOT), we can use `Controlled X([control1, control2], target)` statement.</span></span>

### <a name="examples"></a><span data-ttu-id="71922-293">esempi</span><span class="sxs-lookup"><span data-stu-id="71922-293">Examples</span></span>

<span data-ttu-id="71922-294">Questo esempio di operazione Q # deriva dall'esempio di [misurazione](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/measurement) .</span><span class="sxs-lookup"><span data-stu-id="71922-294">This example of a Q# operation comes from the [Measurement](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/measurement) sample.</span></span> <span data-ttu-id="71922-295">All'interno delle operazioni, è possibile allocare qubits e usare operazioni Quantum su tali qubits, ad esempio `H` e `X`:</span><span class="sxs-lookup"><span data-stu-id="71922-295">Within operations, we can allocate qubits and use quantum operations on those qubits such as `H` and `X`:</span></span>

```qsharp
/// # Summary
/// Prepares a state and measures it in the Pauli-Z basis.
operation MeasureOneQubit () : Result {
        mutable result = Zero;

        using (qubit = Qubit()) { // Allocate a qubit
            H(qubit);               // Use a quantum operation on that qubit

            set result = M(qubit);      // Measure the qubit

            if (result == One) {    // Reset the qubit so that it can be released
                X(qubit);
            }

            return result;
        }
 }
```

<span data-ttu-id="71922-296">Questo esempio di una funzione deriva dall'esempio [PhaseEstimation](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation) .</span><span class="sxs-lookup"><span data-stu-id="71922-296">This example of a function comes from the [PhaseEstimation](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation) sample.</span></span> <span data-ttu-id="71922-297">Contiene codice puramente classico.</span><span class="sxs-lookup"><span data-stu-id="71922-297">It contains purely classical code.</span></span> <span data-ttu-id="71922-298">Si può notare che, a differenza dell'esempio precedente, non vengono allocati qubits e non vengono usate operazioni Quantum.</span><span class="sxs-lookup"><span data-stu-id="71922-298">You can see that, unlike the example above, no qubits are allocated, and no quantum operations are used.</span></span>


```qsharp
/// # Summary
/// Given two arrays, returns a new array that is the pointwise product
/// of each of the given arrays.
function MultiplyPointwise (left : Double[], right : Double[]) : Double[] {
    mutable product = new Double[Length(left)];

    for (idxElement in IndexRange(left)) {
        set product w/= idxElement <- left[idxElement] * right[idxElement];
    }
    return product;
}
```

<span data-ttu-id="71922-299">È anche possibile passare una funzione qubits per l'elaborazione, come in questo esempio dell'esempio [ReversibleLogicSynthesis](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/reversible-logic-synthesis) .</span><span class="sxs-lookup"><span data-stu-id="71922-299">It is also possible for a function to be passed qubits for processing, as in this example from the [ReversibleLogicSynthesis](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/reversible-logic-synthesis) sample.</span></span> <span data-ttu-id="71922-300">Qubits vengono passati alla funzione e usati per l'elaborazione, anche se in nessun momento gli Stati qubit sono stati modificati.</span><span class="sxs-lookup"><span data-stu-id="71922-300">Qubits are passed to the function and used for processing, although at no point are the qubit states themselves modified.</span></span>

```qsharp
/// # Summary
/// Translate MCT masks into multiple-controlled Toffoli gates (with single
/// targets).
function GateMasksToToffoliGates (qubits : Qubit[], masks : MCMTMask[]) : MCTGate[] {

    mutable result = new MCTGate[0];
    let n = Length(qubits);

    for (i in 0 .. Length(masks) - 1) {
        let (controls, targets) = (masks[i])!;
        let controlBits = IntegerBits(controls, n);
        let targetBits = IntegerBits(targets, n);
        let cQubits = Subarray(controlBits, qubits);
        let tQubits = Subarray(targetBits, qubits);

        for (target in tQubits) {
            set result += [MCTGate(cQubits, target)];
        }
    }

    return result;
}
```
