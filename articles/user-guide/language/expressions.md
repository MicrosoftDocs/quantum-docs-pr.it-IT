---
title: 'Espressioni in Q#'
description: 'Informazioni su come specificare, fare riferimento e combinare costanti, variabili, operatori, operazioni e funzioni come espressioni in Q# .'
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: e95a7cb9b74136ef9a6f51b4bbc32d1d93c43a0d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691603"
---
# <a name="expressions-in-no-locq"></a><span data-ttu-id="4c8c8-103">Espressioni in Q#</span><span class="sxs-lookup"><span data-stu-id="4c8c8-103">Expressions in Q#</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="4c8c8-104">Espressioni numeriche</span><span class="sxs-lookup"><span data-stu-id="4c8c8-104">Numeric Expressions</span></span>

<span data-ttu-id="4c8c8-105">Le espressioni numeriche sono espressioni di tipo `Int` , `BigInt` o `Double` .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-105">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="4c8c8-106">Ovvero sono numeri interi o a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-106">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="4c8c8-107">`Int` i valori letterali in Q# sono scritti come una sequenza di cifre.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-107">`Int` literals in Q# are written as a sequence of digits.</span></span>
<span data-ttu-id="4c8c8-108">Gli Integer esadecimali e binari sono supportati e scritti rispettivamente con un `0x` `0b` prefisso e.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-108">Hexadecimal and binary integers are supported and written with a `0x` and `0b` prefix, respectively.</span></span>

<span data-ttu-id="4c8c8-109">`BigInt` i valori letterali in Q# hanno un `l` `L` suffisso o finale.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-109">`BigInt` literals in Q# have a trailing `l` or `L` suffix.</span></span>
<span data-ttu-id="4c8c8-110">I Big Integer esadecimali sono supportati e scritti con un prefisso "0x".</span><span class="sxs-lookup"><span data-stu-id="4c8c8-110">Hexadecimal big integers are supported and written with a "0x" prefix.</span></span>
<span data-ttu-id="4c8c8-111">Di conseguenza, di seguito sono riportati tutti gli utilizzi validi dei `BigInt` valori letterali:</span><span class="sxs-lookup"><span data-stu-id="4c8c8-111">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="4c8c8-112">`Double` i valori letterali in Q# sono numeri a virgola mobile scritti con cifre decimali.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-112">`Double` literals in Q# are floating-point numbers written using decimal digits.</span></span>
<span data-ttu-id="4c8c8-113">Possono essere scritti con o senza un separatore decimale, `.` o una parte esponenziale indicata con "e" o "e" (dopo il quale sono validi solo un possibile segno negativo e cifre decimali).</span><span class="sxs-lookup"><span data-stu-id="4c8c8-113">They can be written with or without a decimal point, `.`, or an exponential part indicated with 'e' or 'E' (after which only a possible negative sign and decimal digits are valid).</span></span>
<span data-ttu-id="4c8c8-114">I valori letterali validi sono i seguenti `Double` : `0.0` , `1.2e5` , `1e-5` .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-114">The following are valid `Double` literals: `0.0`, `1.2e5`, `1e-5`.</span></span>

<span data-ttu-id="4c8c8-115">Data un'espressione di matrice di qualsiasi tipo di elemento, è possibile formare un' `Int` espressione usando la [`Length`](xref:Microsoft.Quantum.Core.Length) funzione predefinita, con l'espressione di matrice racchiusa tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-115">Given an array expression of any element type, you can form an `Int` expression using the [`Length`](xref:Microsoft.Quantum.Core.Length) built-in function, with the array expression enclosed in parentheses.</span></span>
<span data-ttu-id="4c8c8-116">Se, ad esempio, `a` è associato a una matrice, `Length(a)` sarà un'espressione Integer.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-116">For example, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="4c8c8-117">Se `b` è una matrice di matrici di numeri interi, `Int[][]` , `Length(b)` è il numero di sottomatrici in `b` e `Length(b[1])` è il numero di numeri interi nella seconda sottomatrice di `b` .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-117">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="4c8c8-118">Date due espressioni numeriche dello stesso tipo, gli operatori binari `+` , `-` , `*` e `/` possono essere usati per formare una nuova espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-118">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="4c8c8-119">Il tipo della nuova espressione corrisponde ai tipi delle espressioni costituenti.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-119">The type of the new expression is the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="4c8c8-120">Date due espressioni Integer, usare l'operatore binario `^` (Power) per formare una nuova espressione Integer.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-120">Given two integer expressions, use the binary operator `^` (power) to form a new integer expression.</span></span>
<span data-ttu-id="4c8c8-121">Analogamente, è anche possibile usare `^` con due espressioni doppie per formare una nuova espressione doppia.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-121">Similarly, you can also use `^` with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="4c8c8-122">Infine, è possibile usare `^` con un Big Integer a sinistra e un numero intero a destra per formare una nuova espressione di tipo Integer grande.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-122">Finally, you can use `^` with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="4c8c8-123">In questo caso, il secondo parametro deve adattarsi a 32 bit; in caso contrario, viene generato un errore di Runtime.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-123">In this case, the second parameter must fit into 32 bits; if not, it raises a runtime error.</span></span>

<span data-ttu-id="4c8c8-124">Date due espressioni Integer o Big Integer, formano una nuova espressione Integer o Big Integer usando gli `%` operatori (modulo), `&&&` (and bit per bit), `|||` (OR bit per bit) o `^^^` (XOR bit per bit).</span><span class="sxs-lookup"><span data-stu-id="4c8c8-124">Given two integer or big integer expressions, form a new integer or big integer expression using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="4c8c8-125">Data un'espressione Integer o Big Integer a sinistra e un'espressione Integer a destra, usare gli `<<<` operatori (spostamento aritmetico a sinistra) o `>>>` (spostamento a destra aritmetico) per creare una nuova espressione con lo stesso tipo dell'espressione di sinistra.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-125">Given either an integer or big integer expression on the left, and an integer expression on the right, use the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="4c8c8-126">Il secondo parametro (l'importo dello spostamento) per l'operazione di spostamento deve essere maggiore o uguale a zero; il comportamento per gli importi di spostamento negativi non è definito.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-126">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="4c8c8-127">L'importo dello spostamento per entrambe le operazioni di spostamento deve rientrare anche in 32 bit; in caso contrario, viene generato un errore di Runtime.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-127">The shift amount for either shift operation must also fit into 32 bits; if not, it raises a runtime error.</span></span>
<span data-ttu-id="4c8c8-128">Se il numero spostato è un numero intero, l'importo dello spostamento viene interpretato, `mod 64` ovvero uno spostamento di 1 e uno spostamento di 65 hanno lo stesso effetto.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-128">If the number shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="4c8c8-129">Per i valori integer e Big Integer, i turni sono aritmetici.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-129">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="4c8c8-130">Se si sposta un valore negativo, viene restituito un numero negativo, a sinistra o a destra.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-130">Shifting a negative value either left or right results in a negative number.</span></span>
<span data-ttu-id="4c8c8-131">Ovvero, lo spostamento di un passaggio verso sinistra o a destra è uguale alla moltiplicazione o alla divisione per 2, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-131">That is, shifting one step to the left or right is the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="4c8c8-132">La divisione Integer e il modulo Integer seguono lo stesso comportamento per i numeri negativi in C#.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-132">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span> <span data-ttu-id="4c8c8-133">Ovvero, `a % b` ha sempre lo stesso segno di `a` ed è `b * (a / b) + a % b` sempre uguale a `a` .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-133">That is, `a % b` always has the same sign as `a`, and `b * (a / b) + a % b` always equals `a`.</span></span> <span data-ttu-id="4c8c8-134">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4c8c8-134">For example:</span></span>

|`A` | `B` | `A / B` | `A % B`|
|:---------:|:----------:|:---------:|:---------:|
| <span data-ttu-id="4c8c8-135">5</span><span class="sxs-lookup"><span data-stu-id="4c8c8-135">5</span></span> | <span data-ttu-id="4c8c8-136">2</span><span class="sxs-lookup"><span data-stu-id="4c8c8-136">2</span></span> | <span data-ttu-id="4c8c8-137">2</span><span class="sxs-lookup"><span data-stu-id="4c8c8-137">2</span></span> | <span data-ttu-id="4c8c8-138">1</span><span class="sxs-lookup"><span data-stu-id="4c8c8-138">1</span></span> |
| <span data-ttu-id="4c8c8-139">5</span><span class="sxs-lookup"><span data-stu-id="4c8c8-139">5</span></span> | <span data-ttu-id="4c8c8-140">-2</span><span class="sxs-lookup"><span data-stu-id="4c8c8-140">-2</span></span> | <span data-ttu-id="4c8c8-141">-2</span><span class="sxs-lookup"><span data-stu-id="4c8c8-141">-2</span></span> | <span data-ttu-id="4c8c8-142">1</span><span class="sxs-lookup"><span data-stu-id="4c8c8-142">1</span></span> |
| <span data-ttu-id="4c8c8-143">-5</span><span class="sxs-lookup"><span data-stu-id="4c8c8-143">-5</span></span> | <span data-ttu-id="4c8c8-144">2</span><span class="sxs-lookup"><span data-stu-id="4c8c8-144">2</span></span> | <span data-ttu-id="4c8c8-145">-2</span><span class="sxs-lookup"><span data-stu-id="4c8c8-145">-2</span></span> | <span data-ttu-id="4c8c8-146">-1</span><span class="sxs-lookup"><span data-stu-id="4c8c8-146">-1</span></span> |
| <span data-ttu-id="4c8c8-147">-5</span><span class="sxs-lookup"><span data-stu-id="4c8c8-147">-5</span></span> | <span data-ttu-id="4c8c8-148">-2</span><span class="sxs-lookup"><span data-stu-id="4c8c8-148">-2</span></span> | <span data-ttu-id="4c8c8-149">2</span><span class="sxs-lookup"><span data-stu-id="4c8c8-149">2</span></span> | <span data-ttu-id="4c8c8-150">-1</span><span class="sxs-lookup"><span data-stu-id="4c8c8-150">-1</span></span> |

<span data-ttu-id="4c8c8-151">Le operazioni di divisione e modulo di tipo Big Integer funzionano allo stesso modo.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-151">Big integer division and modulus operations work the same way.</span></span>

<span data-ttu-id="4c8c8-152">Dato qualsiasi espressione numerica, è possibile creare una nuova espressione usando l' `-` operatore unario.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-152">Given any numeric expression, you can form a new expression using the `-` unary operator.</span></span>
<span data-ttu-id="4c8c8-153">La nuova espressione è dello stesso tipo dell'espressione costituente.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-153">The new expression is the same type as the constituent expression.</span></span>

<span data-ttu-id="4c8c8-154">Dato qualsiasi espressione Integer o Big Integer, è possibile creare una nuova espressione dello stesso tipo utilizzando l' `~~~` operatore unario (complemento bit per bit).</span><span class="sxs-lookup"><span data-stu-id="4c8c8-154">Given any integer or big integer expression, you can form a new expression of the same type using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="4c8c8-155">Espressioni booleane</span><span class="sxs-lookup"><span data-stu-id="4c8c8-155">Boolean Expressions</span></span>

<span data-ttu-id="4c8c8-156">I due `Bool` valori letterali sono `true` e `false` .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-156">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="4c8c8-157">Date due espressioni dello stesso tipo primitivo, gli `==` `!=` operatori binari e possono essere usati per costruire un' `Bool` espressione.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-157">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="4c8c8-158">L'espressione è true se le due espressioni sono uguali e false in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-158">The expression is true if the two expressions are equal and false if not.</span></span>

<span data-ttu-id="4c8c8-159">I valori dei tipi definiti dall'utente non possono essere confrontati, ma è possibile confrontare solo i valori di cui non è stato eseguito il wrapper.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-159">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="4c8c8-160">Ad esempio, usando l'operatore "Unwrap" `!` (illustrato in dettaglio nei [tipi in Q# ](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span><span class="sxs-lookup"><span data-stu-id="4c8c8-160">For example, using the "unwrap" operator `!` (explained in detail at [Types in Q#](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="4c8c8-161">Il confronto di uguaglianza per `Qubit` i valori è uguaglianza di identità, ovvero se le due espressioni identificano lo stesso qubit.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-161">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="4c8c8-162">Gli Stati dei due qubits non vengono confrontati, accessibili, misurati o modificati da questo confronto.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-162">The states of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="4c8c8-163">Il confronto di uguaglianza per `Double` i valori può essere fuorviante a causa degli effetti dell'arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-163">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="4c8c8-164">Ad esempio, `49.0 * (1.0/49.0) != 1.0`</span><span class="sxs-lookup"><span data-stu-id="4c8c8-164">For example, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="4c8c8-165">Date due espressioni numeriche, gli operatori binari `>` , `<` , `>=` e `<=` possono essere usati per costruire una nuova espressione booleana che è true se la prima espressione è rispettivamente maggiore di, minore di, maggiore o uguale a o minore o uguale alla seconda espressione.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-165">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="4c8c8-166">Date due espressioni booleane, usare l' `and` operatore binario per costruire una nuova espressione booleana che è true se entrambe le espressioni sono true.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-166">Given any two Boolean expressions, use the `and` binary operator to construct a new Boolean expression that is true if both of the two expressions are true.</span></span> <span data-ttu-id="4c8c8-167">Analogamente, l'utilizzo dell' `or` operatore crea un'espressione che è true se una delle due espressioni è true.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-167">Likewise, using the `or` operator creates an expression that is true if either of the two expressions is true.</span></span>

<span data-ttu-id="4c8c8-168">Dato qualsiasi espressione booleana, l' `not` operatore unario può essere usato per costruire una nuova espressione booleana che è true se l'espressione costituente è false.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-168">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="4c8c8-169">Espressioni stringa</span><span class="sxs-lookup"><span data-stu-id="4c8c8-169">String expressions</span></span>

<span data-ttu-id="4c8c8-170">Q# consente di usare le stringhe nell' `fail` istruzione (illustrate in [flusso di controllo](xref:microsoft.quantum.guide.controlflow#fail-statement)) e nella [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) funzione standard.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-170">Q# allows strings to be used in the `fail` statement (explained in [Control Flow](xref:microsoft.quantum.guide.controlflow#fail-statement)) and in the [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) standard function.</span></span> <span data-ttu-id="4c8c8-171">Il comportamento specifico di quest'ultimo dipende dal simulatore usato, ma in genere scrive un messaggio nella console host quando viene chiamato durante un Q# programma.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-171">The specific behavior of the latter depends on the simulator used but typically writes a message to the host console when called during a Q# program.</span></span>

<span data-ttu-id="4c8c8-172">Le stringhe in Q# sono valori letterali o stringhe interpolate.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-172">Strings in Q# are either literals or interpolated strings.</span></span>

<span data-ttu-id="4c8c8-173">I valori letterali stringa sono simili a valori letterali stringa semplici nella maggior parte dei linguaggi, ovvero una sequenza di caratteri Unicode racchiusi tra virgolette doppie `" "` .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-173">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double-quotes `" "`.</span></span>
<span data-ttu-id="4c8c8-174">All'interno di una stringa, usare il carattere barra rovesciata `\` per eseguire l'escape di un carattere di virgolette doppie ( `\"` ) o per inserire una nuova riga ( `\n` ), un ritorno a capo ( `\r` ) o una tabulazione ( `\t` ).</span><span class="sxs-lookup"><span data-stu-id="4c8c8-174">Inside of a string, use the backslash character `\` to escape a double-quote character (`\"`), or to insert a new-line ( `\n` ), a carriage return (`\r`), or a tab (`\t`).</span></span>
<span data-ttu-id="4c8c8-175">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4c8c8-175">For example:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a><span data-ttu-id="4c8c8-176">Stringhe interpolate</span><span class="sxs-lookup"><span data-stu-id="4c8c8-176">Interpolated strings</span></span>

<span data-ttu-id="4c8c8-177">La Q# sintassi per l'interpolazione di stringhe è un subset della sintassi C#.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-177">The Q# syntax for string interpolations is a subset of the C# syntax.</span></span> <span data-ttu-id="4c8c8-178">Di seguito sono riportati i punti chiave che riguardano Q# :</span><span class="sxs-lookup"><span data-stu-id="4c8c8-178">Following are the key points as they pertain to Q#:</span></span>

* <span data-ttu-id="4c8c8-179">Per identificare un valore letterale stringa come stringa interpolata, anteporre a questa il simbolo `$`.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-179">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span> <span data-ttu-id="4c8c8-180">Non può essere presente alcuno spazio vuoto tra `$` e `"` che avvia un valore letterale stringa.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-180">There can be no white space between the `$` and the `"` that starts a string literal.</span></span>

* <span data-ttu-id="4c8c8-181">Di seguito è riportato un esempio di base [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) che usa la funzione per scrivere il risultato di una misurazione nella console, insieme ad altre Q# espressioni.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-181">The following is a basic example using the [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) function to write the result of a measurement to the console, alongside other Q# expressions.</span></span>

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```

* <span data-ttu-id="4c8c8-182">Q#In una stringa interpolata può essere presente qualsiasi espressione valida.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-182">Any valid Q# expression may appear in an interpolated string.</span></span>

* <span data-ttu-id="4c8c8-183">Le espressioni all'interno di una stringa interpolata seguono la Q# sintassi, non la sintassi C#.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-183">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span> <span data-ttu-id="4c8c8-184">La differenza più importante è che non Q# supporta le stringhe interpolate Verbatim (a più righe).</span><span class="sxs-lookup"><span data-stu-id="4c8c8-184">The most notable distinction is that Q# does not support verbatim (multi-line) interpolated strings.</span></span>

<span data-ttu-id="4c8c8-185">Per altri dettagli sulla sintassi di C#, vedere [*stringhe interpolate*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span><span class="sxs-lookup"><span data-stu-id="4c8c8-185">For more details about the C# syntax, see [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span></span>

## <a name="range-expressions"></a><span data-ttu-id="4c8c8-186">Espressioni di intervallo</span><span class="sxs-lookup"><span data-stu-id="4c8c8-186">Range Expressions</span></span>

<span data-ttu-id="4c8c8-187">Date le tre `Int` espressioni `start` , `step` , e `stop` , l'espressione `start .. step .. stop` è un'espressione di intervallo il cui primo elemento è, il secondo elemento è, il `start` `start+step` terzo elemento è `start+step+step` e così via, fino a quando non viene superato `stop` .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-187">Given any three `Int` expressions `start`, `step`, and `stop`, the expression `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, and so on, until you pass `stop`.</span></span>
<span data-ttu-id="4c8c8-188">Un intervallo può essere vuoto se, ad esempio, `step` è positivo e `stop < start` .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-188">A range may be empty if, for example, `step` is positive and `stop < start`.</span></span>

<span data-ttu-id="4c8c8-189">L'intervallo è incluso a entrambe le estremità.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-189">The range is inclusive at both ends.</span></span> <span data-ttu-id="4c8c8-190">Ovvero, se la differenza tra `start` e `stop` è un multiplo Integer di `step` , l'ultimo elemento dell'intervallo sarà `stop` .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-190">That is, if the difference between `start` and `stop` is an integer multiple of `step`, the last element of the range will be `stop`.</span></span>

<span data-ttu-id="4c8c8-191">Date due `Int` espressioni qualsiasi `start` e `stop` , l'espressione `start .. stop` è un'espressione di intervallo uguale a `start .. 1 .. stop` .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-191">Given any two `Int` expressions `start` and `stop`, the expression `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="4c8c8-192">Si noti che il valore implicito `step` è + 1 anche se `stop` è minore di `start` ; in tal caso, l'intervallo è vuoto.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-192">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="4c8c8-193">Alcuni intervalli di esempio sono:</span><span class="sxs-lookup"><span data-stu-id="4c8c8-193">Some example ranges are:</span></span>

- <span data-ttu-id="4c8c8-194">`1..3` è l'intervallo 1, 2, 3.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-194">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="4c8c8-195">`2..2..5` è l'intervallo 2, 4.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-195">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="4c8c8-196">`2..2..6` è l'intervallo 2, 4, 6.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-196">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="4c8c8-197">`6..-2..2` è l'intervallo 6, 4, 2.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-197">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="4c8c8-198">`2..1` intervallo vuoto.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-198">`2..1` is the empty range.</span></span>
- <span data-ttu-id="4c8c8-199">`2..6..7` è l'intervallo 2.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-199">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="4c8c8-200">`2..2..1` intervallo vuoto.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-200">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="4c8c8-201">`1..-1..2` intervallo vuoto.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-201">`1..-1..2` is the empty range.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="4c8c8-202">Espressioni qubit</span><span class="sxs-lookup"><span data-stu-id="4c8c8-202">Qubit Expressions</span></span>

<span data-ttu-id="4c8c8-203">Le uniche `Qubit` espressioni sono simboli associati a `Qubit` valori o elementi di matrice di `Qubit` matrici.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-203">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="4c8c8-204">Nessun `Qubit` valore letterale.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-204">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="4c8c8-205">Espressioni di Pauli</span><span class="sxs-lookup"><span data-stu-id="4c8c8-205">Pauli Expressions</span></span>

<span data-ttu-id="4c8c8-206">I quattro `Pauli` valori, `PauliI` , `PauliX` , `PauliY` e `PauliZ` , sono tutte espressioni valide `Pauli` .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-206">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="4c8c8-207">A parte questo, le uniche `Pauli` espressioni sono i simboli associati a `Pauli` valori o elementi di matrice di `Pauli` matrici.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-207">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="4c8c8-208">Espressioni risultato</span><span class="sxs-lookup"><span data-stu-id="4c8c8-208">Result Expressions</span></span>

<span data-ttu-id="4c8c8-209">I due `Result` valori, `One` e `Zero` , sono `Result` espressioni valide.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-209">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="4c8c8-210">A parte questo, le uniche `Result` espressioni sono i simboli associati a `Result` valori o elementi di matrice di `Result` matrici.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-210">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="4c8c8-211">In particolare, si noti che `One` non è uguale al numero intero `1` e non esiste alcuna conversione diretta tra di essi.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-211">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="4c8c8-212">Lo stesso vale per `Zero` e `0` .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-212">The same is true for `Zero` and `0`.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="4c8c8-213">Espressioni di tupla</span><span class="sxs-lookup"><span data-stu-id="4c8c8-213">Tuple Expressions</span></span>

<span data-ttu-id="4c8c8-214">Un valore letterale di tupla è una sequenza di espressioni di elemento del tipo appropriato, separate da virgole, racchiuse tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-214">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in parentheses.</span></span>
<span data-ttu-id="4c8c8-215">Ad esempio, `(1, One)` è un' `(Int, Result)` espressione.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-215">For example, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="4c8c8-216">Ad eccezione dei valori letterali, le uniche espressioni di tupla sono simboli associati a valori di tupla, elementi di matrice di matrici di tuple e chiamate chiamabili che restituiscono Tuple.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-216">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="4c8c8-217">Espressioni di tipo User-Defined</span><span class="sxs-lookup"><span data-stu-id="4c8c8-217">User-Defined Type Expressions</span></span>

<span data-ttu-id="4c8c8-218">Un valore letterale di un tipo definito dall'utente è costituito dal nome del tipo seguito da un valore letterale di tupla del tipo di tupla di base del tipo.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-218">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="4c8c8-219">Se, ad esempio, `IntPair` è un tipo definito dall'utente basato su `(Int, Int)` , `IntPair(2, 3)` è un valore letterale valido di tale tipo.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-219">For example, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2, 3)` is a valid literal of that type.</span></span>

<span data-ttu-id="4c8c8-220">Ad eccezione dei valori letterali, le uniche espressioni di un tipo definito dall'utente sono i simboli associati a valori di quel tipo, gli elementi di matrice delle matrici di quel tipo e le chiamate richiamabili che restituiscono quel tipo.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-220">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="4c8c8-221">Espressioni Unwrap</span><span class="sxs-lookup"><span data-stu-id="4c8c8-221">Unwrap Expressions</span></span>

<span data-ttu-id="4c8c8-222">In Q# l'operatore Unwrap è un punto esclamativo finale `!` .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-222">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="4c8c8-223">Se, ad esempio, `IntPair` è un tipo definito dall'utente con il tipo sottostante `(Int, Int)` ed `s` è una variabile con valore `IntPair(2, 3)` , `s!` sarà `(2, 3)` .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-223">For example, if `IntPair` is a user-defined type with the underlying type `(Int, Int)` and `s` is a variable with value `IntPair(2, 3)`, then `s!` is `(2, 3)`.</span></span>

<span data-ttu-id="4c8c8-224">Per i tipi definiti dall'utente definiti in termini di altri tipi definiti dall'utente, è possibile ripetere l'operatore Unwrap.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-224">For user-defined types defined in terms of other user-defined types, you can repeat the unwrap operator.</span></span> <span data-ttu-id="4c8c8-225">Ad esempio, `s!!` indica il valore con doppia incapsulamento di `s` .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-225">For example, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="4c8c8-226">Se, pertanto, `WrappedPair` è un tipo definito dall'utente con tipo sottostante `IntPair` e `t` è una variabile con valore `WrappedPair(IntPair(1,2))` , `t!!` è `(1,2)` .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-226">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` is `(1,2)`.</span></span>

<span data-ttu-id="4c8c8-227">L' `!` operatore ha una precedenza più alta rispetto a tutti gli altri operatori diversi da `[]` per l'indicizzazione e il sezionamento di matrici.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-227">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="4c8c8-228">`!` e si `[]` associano in modo posizionale, ovvero `a[i]![3]` viene letto come `((a[i])!)[3]` : prendere l' `i` elemento th di, annullare il `a` wrapping e quindi ottenere il terzo elemento del valore di cui non è stato eseguito il wrapping (che deve essere una matrice).</span><span class="sxs-lookup"><span data-stu-id="4c8c8-228">`!` and `[]` bind positionally; that is, `a[i]![3]` is read as `((a[i])!)[3]`: take the `i`th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="4c8c8-229">La precedenza dell' `!` operatore ha un effetto che potrebbe non essere ovvio.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-229">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="4c8c8-230">Se una funzione o un'operazione restituisce un valore che viene quindi sottoposto a wrapping, la funzione o la chiamata dell'operazione deve essere racchiusa tra parentesi in modo che la tupla dell'argomento venga associata alla chiamata anziché all'annullamento del wrapping.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-230">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="4c8c8-231">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4c8c8-231">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="4c8c8-232">Espressioni di matrice</span><span class="sxs-lookup"><span data-stu-id="4c8c8-232">Array Expressions</span></span>

<span data-ttu-id="4c8c8-233">Un valore letterale di matrice è una sequenza di una o più espressioni di elementi, separate da virgole, racchiuse tra parentesi quadre `[]` .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-233">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in square brackets `[]`.</span></span>
<span data-ttu-id="4c8c8-234">Tutti gli elementi devono essere compatibili con lo stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-234">All elements must be compatible with the same type.</span></span>

<span data-ttu-id="4c8c8-235">Date due matrici dello stesso tipo, usare l' `+` operatore binario per formare una nuova matrice che corrisponde alla concatenazione delle due matrici.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-235">Given two arrays of the same type, use the binary `+` operator to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="4c8c8-236">Ad esempio, `[1,2,3] + [4,5,6]` = `[1,2,3,4,5,6]`.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-236">For example, `[1,2,3] + [4,5,6]` = `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="4c8c8-237">Creazione di matrici</span><span class="sxs-lookup"><span data-stu-id="4c8c8-237">Array Creation</span></span>

<span data-ttu-id="4c8c8-238">Dato un tipo e un' `Int` espressione, usare l' `new` operatore per allocare una nuova matrice della dimensione specificata.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-238">Given a type and an `Int` expression, use the `new` operator to allocate a new array of the given size.</span></span>
<span data-ttu-id="4c8c8-239">Ad esempio, `new Int[i + 1]` alloca una nuova `Int` matrice con `i + 1` gli elementi.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-239">For example, `new Int[i + 1]` allocates a new `Int` array with `i + 1` elements.</span></span>

<span data-ttu-id="4c8c8-240">I valori letterali di matrice vuoti, ad esempio `[]` , non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-240">Empty array literals, such as `[]`, are not allowed.</span></span>
<span data-ttu-id="4c8c8-241">È invece possibile creare una matrice di lunghezza zero usando `new T[0]` , dove `T` è un segnaposto per un tipo appropriato.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-241">Instead, you can create an array of length zero by using `new T[0]`, where `T` is a placeholder for a suitable type.</span></span>

<span data-ttu-id="4c8c8-242">Gli elementi di una nuova matrice vengono inizializzati su un valore predefinito dipendente dal tipo.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-242">The elements of a new array initialize to a type-dependent default value.</span></span>
<span data-ttu-id="4c8c8-243">Nella maggior parte dei casi, si tratta di una variante di zero.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-243">In most cases, this is some variation of zero.</span></span>

<span data-ttu-id="4c8c8-244">Per qubits e callable, che sono riferimenti a entità, non esiste un valore predefinito ragionevole.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-244">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="4c8c8-245">Pertanto, per questi tipi, il valore predefinito è un riferimento non valido che non è possibile utilizzare senza causare un errore di runtime, simile a un riferimento null in linguaggi come C# o Java.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-245">Thus, for these types, the default is an invalid reference that you cannot use without causing a runtime error, similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="4c8c8-246">Prima di poter usare i relativi elementi in modo sicuro, è necessario inizializzare le matrici contenenti qubits o Callable con valori non predefiniti.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-246">Arrays containing qubits or callables must be initialized with non-default values before you can use their elements safely.</span></span> <span data-ttu-id="4c8c8-247">Per le routine di inizializzazione appropriate, vedere <xref:Microsoft.Quantum.Arrays> .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-247">For suitable initialization routines, see <xref:Microsoft.Quantum.Arrays>.</span></span>

<span data-ttu-id="4c8c8-248">I valori predefiniti per ogni tipo sono:</span><span class="sxs-lookup"><span data-stu-id="4c8c8-248">The default values for each type are:</span></span>

<span data-ttu-id="4c8c8-249">Type</span><span class="sxs-lookup"><span data-stu-id="4c8c8-249">Type</span></span> | <span data-ttu-id="4c8c8-250">Predefinito</span><span class="sxs-lookup"><span data-stu-id="4c8c8-250">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="4c8c8-251">_Qubit non valido_</span><span class="sxs-lookup"><span data-stu-id="4c8c8-251">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="4c8c8-252">Intervallo vuoto, `1..1..0`</span><span class="sxs-lookup"><span data-stu-id="4c8c8-252">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="4c8c8-253">_chiamabile non valido_</span><span class="sxs-lookup"><span data-stu-id="4c8c8-253">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="4c8c8-254">I tipi di tupla inizializzano elemento per elemento.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-254">Tuple types initialize element-by-element.</span></span>


### <a name="array-elements"></a><span data-ttu-id="4c8c8-255">Elementi di matrice</span><span class="sxs-lookup"><span data-stu-id="4c8c8-255">Array Elements</span></span>

<span data-ttu-id="4c8c8-256">Data un'espressione di matrice e un' `Int` espressione, formano una nuova espressione usando l'operatore di elemento della matrice `[]` .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-256">Given an array expression and an `Int` expression, form a new expression using the array element operator `[]`.</span></span>
<span data-ttu-id="4c8c8-257">La nuova espressione è dello stesso tipo del tipo di elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-257">The new expression is the same type as the element type of the array.</span></span>
<span data-ttu-id="4c8c8-258">Ad esempio, se `a` è associato a una matrice di tipo `Double` , `a[4]` è un' `Double` espressione.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-258">For example, if `a` is bound to an array of type `Double`, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="4c8c8-259">Se l'espressione di matrice non è un identificatore semplice, è necessario racchiuderla tra parentesi per selezionare un elemento.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-259">If the array expression is not a simple identifier, you must enclose it in parentheses to select an element.</span></span>
<span data-ttu-id="4c8c8-260">Se, ad esempio, `a` e `b` sono entrambe matrici di tipo `Int` , un elemento della concatenazione viene espresso come:</span><span class="sxs-lookup"><span data-stu-id="4c8c8-260">For example, if `a` and `b` are both arrays of type `Int`, an element from the concatenation is expressed as:</span></span>

```qsharp
(a + b)[13]
```

<span data-ttu-id="4c8c8-261">Tutte le matrici in Q# sono in base zero.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-261">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="4c8c8-262">Ovvero il primo elemento di una matrice `a` è sempre `a[0]` .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-262">That is, the first element of an array `a` is always `a[0]`.</span></span>


### <a name="array-slices"></a><span data-ttu-id="4c8c8-263">Sezioni di matrici</span><span class="sxs-lookup"><span data-stu-id="4c8c8-263">Array Slices</span></span>

<span data-ttu-id="4c8c8-264">Data un'espressione di matrice e un' `Range` espressione, formano una nuova espressione usando l'operatore di sezionamento della matrice `[ ]` .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-264">Given an array expression and a `Range` expression, form a new expression using the array slice operator `[ ]`.</span></span>
<span data-ttu-id="4c8c8-265">La nuova espressione è dello stesso tipo della matrice e contiene gli elementi della matrice indicizzati dagli elementi dell'oggetto `Range` , nell'ordine definito da `Range` .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-265">The new expression is the same type as the array and contains the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="4c8c8-266">Se, ad esempio, `a` è associato a una matrice di tipo `Double` , `a[3..-1..0]` è un' `Double[]` espressione che contiene i primi quattro elementi di, `a` ma in ordine inverso come appaiono in `a` .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-266">For example, if `a` is bound to an array of type `Double`, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="4c8c8-267">Se `Range` è vuoto, la sezione della matrice risultante è di lunghezza zero.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-267">If the `Range` is empty, then the resulting array slice is zero length.</span></span>

<span data-ttu-id="4c8c8-268">Come per fare riferimento agli elementi della matrice, se l'espressione di matrice non è un identificatore semplice, è necessario racchiuderla tra parentesi per sezionarla.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-268">Just as with referencing array elements, if the array expression is not a simple identifier, you must enclose it in parentheses to slice it.</span></span>
<span data-ttu-id="4c8c8-269">Se, ad esempio, `a` e `b` sono entrambe matrici di tipo `Int` , una sezione della concatenazione viene espressa come:</span><span class="sxs-lookup"><span data-stu-id="4c8c8-269">For example, if `a` and `b` are both arrays of type `Int`, a slice from the concatenation is expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a><span data-ttu-id="4c8c8-270">Valori di inizio/fine dedotti</span><span class="sxs-lookup"><span data-stu-id="4c8c8-270">Inferred start/end values</span></span>

<span data-ttu-id="4c8c8-271">A partire dalla [versione 0,8](xref:microsoft.quantum.relnotes), sono supportate le espressioni contestuali per il sezionamento dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-271">Starting with our [0.8 release](xref:microsoft.quantum.relnotes), we support contextual expressions for range slicing.</span></span> <span data-ttu-id="4c8c8-272">In particolare, è possibile omettere i valori di inizio e di fine dell'intervallo nel contesto di un'espressione di sezionamento dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-272">In particular, you may omit range start and end values in the context of a range slicing expression.</span></span> <span data-ttu-id="4c8c8-273">In tal caso, il compilatore applica le regole seguenti per dedurre i delimitatori previsti per l'intervallo:</span><span class="sxs-lookup"><span data-stu-id="4c8c8-273">In that case, the compiler applies the following rules to infer the intended delimiters for the range:</span></span>

* <span data-ttu-id="4c8c8-274">Se il valore *iniziale* dell'intervallo viene omesso, il valore di inizio derivato</span><span class="sxs-lookup"><span data-stu-id="4c8c8-274">If the range *start* value is omitted, then the inferred start value</span></span>
  * <span data-ttu-id="4c8c8-275">è zero se non è specificato alcun passaggio oppure il passaggio specificato è positivo.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-275">is zero if no step is specified or the specified step is positive.</span></span>  
  * <span data-ttu-id="4c8c8-276">lunghezza della matrice sezionata meno uno se il passaggio specificato è negativo.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-276">is the length of the sliced array minus one if the specified step is negative.</span></span>

* <span data-ttu-id="4c8c8-277">Se il valore *finale* dell'intervallo viene omesso, il valore di fine derivato</span><span class="sxs-lookup"><span data-stu-id="4c8c8-277">If the range *end* value is omitted, then the inferred end value</span></span>
  * <span data-ttu-id="4c8c8-278">lunghezza della matrice sezionata meno uno se non viene specificato alcun passaggio oppure il passaggio specificato è positivo.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-278">is the length of the sliced array minus one if no step is specified or the specified step is positive.</span></span>
  * <span data-ttu-id="4c8c8-279">è zero se il passaggio specificato è negativo.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-279">is zero if the specified step is negative.</span></span>

<span data-ttu-id="4c8c8-280">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4c8c8-280">Some examples are:</span></span>

```qsharp
let arr = [1,2,3,4,5,6];
let slice1  = arr[3...];      // slice1 is [4,5,6];
let slice2  = arr[0..2...];   // slice2 is [1,3,5];
let slice3  = arr[...2];      // slice3 is [1,2,3];
let slice4  = arr[...2..3];   // slice4 is [1,3];
let slice5  = arr[...2...];   // slice5 is [1,3,5];
let slice7  = arr[4..-2...];  // slice7 is [5,3,1];
let slice8  = arr[...-1..3];  // slice8 is [6,5,4];
let slice9  = arr[...-1...];  // slice9 is [6,5,4,3,2,1];
let slice10 = arr[...];       // slice10 is [1,2,3,4,5,6];
```

### <a name="copy-and-update-expressions"></a><span data-ttu-id="4c8c8-281">Espressioni di copia e aggiornamento</span><span class="sxs-lookup"><span data-stu-id="4c8c8-281">Copy-and-Update Expressions</span></span>

<span data-ttu-id="4c8c8-282">Poiché tutti i Q# tipi sono tipi di valore (con qubits che accetta un ruolo particolare), viene creata formalmente una "copia" quando un valore viene associato a un simbolo o quando un simbolo viene riassociato.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-282">Since all Q# types are value types (with the qubits taking a somewhat special role), formally a "copy" is created when a value is bound to a symbol or when a symbol is rebound.</span></span> <span data-ttu-id="4c8c8-283">Ovvero, il comportamento di Q# è identico a quello di una copia creata utilizzando un operatore di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-283">That is to say, the behavior of Q# is the same as if a copy were created using an assignment operator.</span></span> 

<span data-ttu-id="4c8c8-284">Naturalmente, in pratica, solo le parti rilevanti vengono ricreate in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-284">Of course, in practice, only the relevant pieces are recreated as needed.</span></span> <span data-ttu-id="4c8c8-285">Ciò influiscono sulla modalità di copia delle matrici perché non è possibile aggiornare gli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-285">This affects how you copy arrays because it is not possible to update array items.</span></span> <span data-ttu-id="4c8c8-286">Per modificare una matrice esistente, è necessario sfruttare un meccanismo di *copia e aggiornamento* .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-286">To modify an existing array requires leveraging a *copy-and-update* mechanism.</span></span>

<span data-ttu-id="4c8c8-287">È possibile creare una nuova matrice da una matrice esistente tramite espressioni di *copia e aggiornamento* , che usano gli operatori `w/` e `<-` .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-287">You can create a new array from an existing array via *copy-and-update* expressions, which use the operators `w/` and `<-`.</span></span>
<span data-ttu-id="4c8c8-288">Un'espressione di copia e aggiornamento è un'espressione nel formato, in `expression1 w/ expression2 <- expression3` cui</span><span class="sxs-lookup"><span data-stu-id="4c8c8-288">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where</span></span>

* <span data-ttu-id="4c8c8-289">`expression1` deve essere `T[]` di tipo per un tipo `T` .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-289">`expression1` must be type `T[]` for some type `T`.</span></span>
* <span data-ttu-id="4c8c8-290">`expression2` definisce gli indici nella matrice specificata in `expression1` da modificare.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-290">`expression2` defines which indices in the array specified in `expression1` to modify.</span></span> <span data-ttu-id="4c8c8-291">`expression2` deve essere di tipo `Int` o `Range` .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-291">`expression2` must be either type `Int` or type `Range`.</span></span>
* <span data-ttu-id="4c8c8-292">`expression3` valore o valori utilizzati per aggiornare gli elementi in, in `expression1` base agli indici specificati in `expression2` .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-292">`expression3` is the value(s) used to update elements in `expression1`, based on the indices specified in `expression2`.</span></span> <span data-ttu-id="4c8c8-293">Se `expression2` è `Int` di tipo, `expression3` deve essere di tipo `T` .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-293">If `expression2` is type `Int`, `expression3` must be type `T`.</span></span> <span data-ttu-id="4c8c8-294">Se `expression2` è `Range` di tipo, `expression3` deve essere di tipo `T[]` .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-294">If `expression2` is type `Range`, `expression3` must be type `T[]`.</span></span>

<span data-ttu-id="4c8c8-295">L'espressione Copy-and-Update, ad esempio, `arr w/ idx <- value` costruisce una nuova matrice con tutti gli elementi impostati sugli elementi corrispondenti in `arr` , ad eccezione degli elementi specificati da `idx` , che viene impostato sul valore/i in `value` .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-295">For example, the copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding elements in `arr`, except for the element(s) specified by `idx`, which is set to the value(s) in `value`.</span></span> 

<span data-ttu-id="4c8c8-296">Dato che `arr` contiene la matrice `[0,1,2,3]` ,</span><span class="sxs-lookup"><span data-stu-id="4c8c8-296">Given `arr` contains the array `[0,1,2,3]`, then</span></span> 

- <span data-ttu-id="4c8c8-297">`arr w/ 0 <- 10` è la matrice `[10,1,2,3]` .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-297">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="4c8c8-298">`arr w/ 2 <- 10` è la matrice `[0,1,10,3]` .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-298">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="4c8c8-299">`arr w/ 0..2..3 <- [10,12]` è la matrice `[10,1,12,3]` .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-299">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

#### <a name="copy-and-update-expressions-for-named-items"></a><span data-ttu-id="4c8c8-300">Espressioni di copia e aggiornamento per gli elementi denominati</span><span class="sxs-lookup"><span data-stu-id="4c8c8-300">Copy-and-update expressions for named items</span></span>

<span data-ttu-id="4c8c8-301">Sono presenti espressioni simili per gli elementi denominati in tipi definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-301">Similar expressions exist for named items in user-defined types.</span></span> 

<span data-ttu-id="4c8c8-302">Si consideri ad esempio il tipo</span><span class="sxs-lookup"><span data-stu-id="4c8c8-302">For example, consider the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="4c8c8-303">Se `c` contiene il valore di tipo `Complex(1., -1.)` , `c w/ Re <- 0.` è un'espressione di tipo `Complex` che restituisce `Complex(0., -1.)` .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-303">If `c` contains the value of type `Complex(1., -1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0., -1.)`.</span></span>

### <a name="jagged-arrays"></a><span data-ttu-id="4c8c8-304">Matrici irregolari</span><span class="sxs-lookup"><span data-stu-id="4c8c8-304">Jagged Arrays</span></span>

<span data-ttu-id="4c8c8-305">Una matrice di matrici, talvolta denominata "matrice di matrici", è una matrice i cui elementi sono matrici.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-305">A jagged array, sometimes called an "array of arrays," is an array whose elements are arrays.</span></span>
<span data-ttu-id="4c8c8-306">Gli elementi di una matrice irregolare possono avere dimensioni diverse.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-306">The elements of a jagged array can be of different sizes.</span></span>
<span data-ttu-id="4c8c8-307">Nell'esempio seguente viene illustrato come dichiarare e inizializzare una matrice di matrici che rappresenta una tabella di moltiplicazione.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-307">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

```qsharp
let N = 4;
mutable multiplicationTable = new Int[][N];
for (i in 1..N) {
    mutable row = new Int[i];
    for (j in 1..i) {
        set row w/= j-1 <- i * j;
    }
    set multiplicationTable w/= i-1 <- row;
}
```

### <a name="arrays-of-callables"></a><span data-ttu-id="4c8c8-308">Matrici di chiamabili</span><span class="sxs-lookup"><span data-stu-id="4c8c8-308">Arrays of callables</span></span> 

<span data-ttu-id="4c8c8-309">È anche possibile creare una matrice di chiamabili.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-309">You can also create an array of callables.</span></span>

* <span data-ttu-id="4c8c8-310">Se il tipo di elemento comune è un'operazione o un tipo di funzione, tutti gli elementi devono avere gli stessi tipi di input e di output.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-310">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
* <span data-ttu-id="4c8c8-311">Il tipo di elemento della matrice supporta qualsiasi [funtori](xref:microsoft.quantum.guide.operationsfunctions) supportato da tutti gli elementi.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-311">The element type of the array supports any [functors](xref:microsoft.quantum.guide.operationsfunctions) that are supported by all of the elements.</span></span>
<span data-ttu-id="4c8c8-312">Ad esempio, se `Op1` , `Op2` e `Op3` sono tutte `Qubit[] => Unit` operazioni, ma supporta, supporta `Op1` e supporta `Adjoint` `Op2` `Controlled` `Op3` entrambi:</span><span class="sxs-lookup"><span data-stu-id="4c8c8-312">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit` operations, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>
  * <span data-ttu-id="4c8c8-313">`[Op1, Op2]` è una matrice di `(Qubit[] => Unit)` operazioni.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-313">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
  * <span data-ttu-id="4c8c8-314">`[Op1, Op3]` è una matrice di `(Qubit[] => Unit is Adj)` operazioni.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-314">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
  * <span data-ttu-id="4c8c8-315">`[Op2, Op3]` è una matrice di `(Qubit[] => Unit is Ctl)` operazioni.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-315">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="4c8c8-316">Tuttavia, mentre le operazioni `(Qubit[] => Unit is Adj)` e  `(Qubit[] => Unit is Ctl)` hanno il tipo di base comune di `(Qubit[] => Unit)` , le *matrici* di queste operazioni non condividono un tipo di base comune.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-316">However, while the operations `(Qubit[] => Unit is Adj)` and  `(Qubit[] => Unit is Ctl)` have the common base type of `(Qubit[] => Unit)`, *arrays* of these operations do not share a common base type.</span></span>

<span data-ttu-id="4c8c8-317">Al momento, ad esempio, `[[Op1], [Op2]]` genera un errore perché tenta di creare una matrice dei due tipi di matrice incompatibili `(Qubit[] => Unit is Adj)[]` e `(Qubit[] => Unit is Ctl)[]` .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-317">For example, `[[Op1], [Op2]]` would currently raise an error because it attempts to create an array of the two incompatible array types `(Qubit[] => Unit is Adj)[]` and `(Qubit[] => Unit is Ctl)[]`.</span></span>

<span data-ttu-id="4c8c8-318">Per ulteriori informazioni sulle richiamabili, vedere [espressioni richiamabili](#callable-expressions) in questa pagina o [operazioni Q# e funzioni in ](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="4c8c8-318">For more information on callables, see [Callable expressions](#callable-expressions)  on this page or [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

## <a name="conditional-expressions"></a><span data-ttu-id="4c8c8-319">Espressioni condizionali</span><span class="sxs-lookup"><span data-stu-id="4c8c8-319">Conditional Expressions</span></span>

<span data-ttu-id="4c8c8-320">Date due espressioni dello stesso tipo e di un'espressione booleana, formano un'espressione condizionale usando il punto interrogativo, `?` e la barra verticale `|` .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-320">Given two expressions of the same type and a Boolean expression, form a conditional expression using the question mark, `?`, and the vertical bar `|`.</span></span> <span data-ttu-id="4c8c8-321">Dato `a==b ? c | d` , il valore dell'espressione condizionale è `c` se `a==b` è true e `d` se è false.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-321">Given `a==b ? c | d`, the value of the conditional expression is `c` if `a==b` is true and `d` if it is false.</span></span>

### <a name="conditional-expressions-with-callables"></a><span data-ttu-id="4c8c8-322">Espressioni condizionali con Callable</span><span class="sxs-lookup"><span data-stu-id="4c8c8-322">Conditional expressions with callables</span></span>

<span data-ttu-id="4c8c8-323">Le espressioni condizionali possono restituire operazioni con gli stessi input e output ma supportano funtori diversi.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-323">Conditional expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span> <span data-ttu-id="4c8c8-324">In questo caso, il tipo dell'espressione condizionale è un'operazione con input e output che supportano qualsiasi funtori supportato da entrambe le espressioni.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-324">In this case, the type of the conditional expression is an operation with inputs and outputs that support any functors supported by both expressions.</span></span>
<span data-ttu-id="4c8c8-325">Se, ad esempio `Op1` ,, `Op2` e `Op3` sono tutti `Qubit[]=>Unit` , ma `Op1` supporta, supporta e supporta `Adjoint` `Op2` `Controlled` `Op3` entrambi:</span><span class="sxs-lookup"><span data-stu-id="4c8c8-325">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="4c8c8-326">`flag ? Op1 | Op2` è un' `(Qubit[] => Unit)` operazione.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-326">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="4c8c8-327">`flag ? Op1 | Op3` è un' `(Qubit[] => Unit is Adj)` operazione.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-327">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="4c8c8-328">`flag ? Op2 | Op3` è un' `(Qubit[] => Unit is Ctl)` operazione.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-328">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="4c8c8-329">Se una delle due espressioni di risultato possibili include una funzione o una chiamata a un'operazione, la chiamata viene eseguita solo se il risultato è quello che corrisponde al valore della chiamata.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-329">If either of the two possible result expressions include a function or operation call, that call only takes place if that result is the one that is the value of the call.</span></span> <span data-ttu-id="4c8c8-330">Nel caso, ad esempio, `a==b ? C(qs) | D(qs)` se `a==b` è true, `C` viene richiamata l'operazione e se è false, `D` viene richiamata solo l'operazione.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-330">For example, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true, then the `C` operation is invoked, and if it is false then only the `D` operation is invoked.</span></span> <span data-ttu-id="4c8c8-331">Questo approccio è simile a *un cortocircuito in altri* linguaggi.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-331">This approach is similar to *short-circuiting* in other languages.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="4c8c8-332">Espressioni richiamabili</span><span class="sxs-lookup"><span data-stu-id="4c8c8-332">Callable Expressions</span></span>

<span data-ttu-id="4c8c8-333">Un valore letterale chiamabile è il nome di un'operazione o di una funzione definita nell'ambito di compilazione.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-333">A callable literal is the name of an operation or function defined in the compilation scope.</span></span> <span data-ttu-id="4c8c8-334">Ad esempio, `X` è un valore letterale di operazione che fa riferimento all'operazione della libreria standard `X` e `Message` è un valore letterale di funzione che fa riferimento alla funzione della libreria standard `Message` .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-334">For example, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="4c8c8-335">Se un'operazione supporta il `Adjoint` functor, `Adjoint op` è un'espressione dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-335">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="4c8c8-336">Analogamente, se l'operazione supporta il `Controlled` functor, `Controlled op` è un'espressione dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-336">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="4c8c8-337">Per ulteriori informazioni sui tipi di queste espressioni, vedere la pagina relativa alle [specializzazioni delle operazioni di chiamata](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span><span class="sxs-lookup"><span data-stu-id="4c8c8-337">For more information about the types of these expressions, see [Calling operation specializations](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span></span>

<span data-ttu-id="4c8c8-338">Funtori ( `Adjoint` e `Controlled` ) vengono associati in modo più accurato rispetto a tutti gli altri operatori, ad eccezione dell'operatore Unwrap `!` e dell'indicizzazione della matrice con `[ ]` .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-338">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with `[ ]`.</span></span>
<span data-ttu-id="4c8c8-339">Pertanto, tutti i seguenti sono validi, presupponendo che le operazioni supportino i funtori utilizzati:</span><span class="sxs-lookup"><span data-stu-id="4c8c8-339">Thus, the following are all valid, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a><span data-ttu-id="4c8c8-340">Espressioni chiamabili con parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="4c8c8-340">Type-parameterized callable expressions</span></span>

<span data-ttu-id="4c8c8-341">È possibile usare un valore letterale chiamabile come valore, ad esempio, per assegnarlo a una variabile o passarlo a un altro oggetto chiamabile.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-341">You can use a callable literal as a value, for example, to assign it to a variable or pass it to another callable.</span></span> <span data-ttu-id="4c8c8-342">In questo caso, se l'oggetto chiamabile dispone di [parametri di tipo](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), è necessario fornire i parametri come parte del valore chiamabile.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-342">In this case, if the callable has [type parameters](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), you must provide the parameters as part of the callable value.</span></span>

<span data-ttu-id="4c8c8-343">Un valore chiamabile non può avere parametri di tipo non specificati.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-343">A callable value cannot have any unspecified type parameters.</span></span> <span data-ttu-id="4c8c8-344">Ad esempio, se `Fun` è una funzione con la firma `'T1->Unit` :</span><span class="sxs-lookup"><span data-stu-id="4c8c8-344">For example, if `Fun` is a function with the signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomeOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="4c8c8-345">Espressioni di chiamata chiamabili</span><span class="sxs-lookup"><span data-stu-id="4c8c8-345">Callable Invocation Expressions</span></span>

<span data-ttu-id="4c8c8-346">Data un'espressione chiamabile (operazione o funzione) e un'espressione di tupla del tipo di input della firma richiamabile, è possibile formare un' *espressione di chiamata* aggiungendo l'espressione di tupla all'espressione chiamabile.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-346">Given a callable expression (operation or function) and a tuple expression of the input type of the callable's signature, you can form an *invocation expression* by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="4c8c8-347">Il tipo dell'espressione di chiamata è il tipo di output della firma richiamabile.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-347">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="4c8c8-348">Se, ad esempio, `Op` è un'operazione con la firma `((Int, Qubit) => Double)` , `Op(3, qubit1)` è un'espressione di tipo `Double` .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-348">For example, if `Op` is an operation with the signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="4c8c8-349">Analogamente, se `Sin` è una funzione con la firma `(Double -> Double)` , `Sin(0.1)` è un'espressione di tipo `Double` .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-349">Similarly, if `Sin` is a function with the signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="4c8c8-350">Infine, se `Builder` è una funzione con la firma `(Int -> (Int -> Int))` , `Builder(3)` è una funzione da `Int` a `Int` .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-350">Finally, if `Builder` is a function with the signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from `Int` to `Int`.</span></span>

<span data-ttu-id="4c8c8-351">Per richiamare il risultato di un'espressione con valori richiamabili è necessaria una coppia aggiuntiva di parentesi intorno all'espressione chiamabile.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-351">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="4c8c8-352">Pertanto, per richiamare il risultato della chiamata `Builder` dal paragrafo precedente, la sintassi corretta è la seguente:</span><span class="sxs-lookup"><span data-stu-id="4c8c8-352">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="4c8c8-353">Quando si richiama un oggetto chiamabile con [parametri di tipo](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) , è possibile specificare i parametri di tipo effettivi tra parentesi acute `< >` dopo l'espressione chiamabile.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-353">When invoking a [type-parameterized](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) callable, you can specify the actual type parameters within angle brackets `< >` after the callable expression.</span></span>
<span data-ttu-id="4c8c8-354">Questa azione non è in genere necessaria perché il Q# compilatore deduce i tipi effettivi.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-354">This action is usually unnecessary as the Q# compiler infers the actual types.</span></span>
<span data-ttu-id="4c8c8-355">Tuttavia, è *necessario per* l' [applicazione parziale](xref:microsoft.quantum.guide.operationsfunctions#partial-application) se un argomento con parametri di tipo non è specificato.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-355">However, it *is* required for [partial application](xref:microsoft.quantum.guide.operationsfunctions#partial-application) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="4c8c8-356">È utile anche quando si passano operazioni con diversi supporti di un functor a un oggetto chiamabile.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-356">It is also useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="4c8c8-357">Ad esempio, se `Func` ha `('T1, 'T2, 'T1) -> 'T2` la firma `Op1` e `Op2` hanno `(Qubit[] => Unit is Adj)` la firma e `Op3` ha `(Qubit[] => Unit)` la firma, per richiamare `Func` con `Op1` come primo argomento, `Op2` come secondo e `Op3` come terzo:</span><span class="sxs-lookup"><span data-stu-id="4c8c8-357">For example, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="4c8c8-358">La specifica del tipo è obbligatoria perché `Op3` e `Op1` hanno tipi diversi, pertanto il compilatore lo considererà ambiguo senza la specifica.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-358">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="4c8c8-359">Ordine di precedenza degli operatori</span><span class="sxs-lookup"><span data-stu-id="4c8c8-359">Operator Precedence</span></span>

* <span data-ttu-id="4c8c8-360">Tutti gli operatori binari sono associativi a destra, ad eccezione di `^` .</span><span class="sxs-lookup"><span data-stu-id="4c8c8-360">All binary operators are right-associative, except for `^`.</span></span>

* <span data-ttu-id="4c8c8-361">Le parentesi quadre, `[ ]` , per il sezionamento e l'indicizzazione della matrice, vengono associate prima di qualsiasi operatore.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-361">Brackets, `[ ]`, for array slicing and indexing, bind before any operator.</span></span>

* <span data-ttu-id="4c8c8-362">Funtori `Adjoint` e `Controlled` Bind dopo l'indicizzazione della matrice ma prima di tutti gli altri operatori.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-362">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

* <span data-ttu-id="4c8c8-363">Anche le parentesi per la chiamata di operazioni e funzioni vengono associate prima di qualsiasi operatore, ma dopo l'indicizzazione della matrice e funtori.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-363">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="4c8c8-364">Q# operatori in ordine di precedenza, dal più alto al più basso:</span><span class="sxs-lookup"><span data-stu-id="4c8c8-364">Q# operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="4c8c8-365">Operatore</span><span class="sxs-lookup"><span data-stu-id="4c8c8-365">Operator</span></span> | <span data-ttu-id="4c8c8-366">Grado</span><span class="sxs-lookup"><span data-stu-id="4c8c8-366">Arity</span></span> | <span data-ttu-id="4c8c8-367">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4c8c8-367">Description</span></span> | <span data-ttu-id="4c8c8-368">Tipi di operando</span><span class="sxs-lookup"><span data-stu-id="4c8c8-368">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="4c8c8-369">finali `!`</span><span class="sxs-lookup"><span data-stu-id="4c8c8-369">trailing `!`</span></span> | <span data-ttu-id="4c8c8-370">Unario</span><span class="sxs-lookup"><span data-stu-id="4c8c8-370">Unary</span></span> | <span data-ttu-id="4c8c8-371">Unwrap</span><span class="sxs-lookup"><span data-stu-id="4c8c8-371">Unwrap</span></span> | <span data-ttu-id="4c8c8-372">Qualsiasi tipo definito dall'utente</span><span class="sxs-lookup"><span data-stu-id="4c8c8-372">Any user-defined type</span></span>
 <span data-ttu-id="4c8c8-373">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="4c8c8-373">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="4c8c8-374">Unario</span><span class="sxs-lookup"><span data-stu-id="4c8c8-374">Unary</span></span> | <span data-ttu-id="4c8c8-375">Valore numerico negativo, complemento bit per bit, negazione logica</span><span class="sxs-lookup"><span data-stu-id="4c8c8-375">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="4c8c8-376">`Int`, `BigInt` o `Double` per `-` , `Int` o `BigInt` per `~~~` , `Bool` per `not`</span><span class="sxs-lookup"><span data-stu-id="4c8c8-376">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="4c8c8-377">Binary</span><span class="sxs-lookup"><span data-stu-id="4c8c8-377">Binary</span></span> | <span data-ttu-id="4c8c8-378">Potenza intera</span><span class="sxs-lookup"><span data-stu-id="4c8c8-378">Integer power</span></span> | <span data-ttu-id="4c8c8-379">`Int` o `BigInt` per la base, `Int` per l'esponente</span><span class="sxs-lookup"><span data-stu-id="4c8c8-379">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="4c8c8-380">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="4c8c8-380">`/`, `*`, `%`</span></span> | <span data-ttu-id="4c8c8-381">Binary</span><span class="sxs-lookup"><span data-stu-id="4c8c8-381">Binary</span></span> | <span data-ttu-id="4c8c8-382">Divisione, moltiplicazione, modulo Integer</span><span class="sxs-lookup"><span data-stu-id="4c8c8-382">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="4c8c8-383">`Int`, `BigInt` oppure `Double` per `/` e `*` `Int` o `BigInt` per `%`</span><span class="sxs-lookup"><span data-stu-id="4c8c8-383">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="4c8c8-384">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="4c8c8-384">`+`, `-`</span></span> | <span data-ttu-id="4c8c8-385">Binary</span><span class="sxs-lookup"><span data-stu-id="4c8c8-385">Binary</span></span> | <span data-ttu-id="4c8c8-386">Aggiunta o concatenazione di stringhe e matrici, sottrazione</span><span class="sxs-lookup"><span data-stu-id="4c8c8-386">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="4c8c8-387">`Int``BigInt`o `Double` , inoltre, `String` o qualsiasi tipo di matrice per`+`</span><span class="sxs-lookup"><span data-stu-id="4c8c8-387">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="4c8c8-388">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="4c8c8-388">`<<<`, `>>>`</span></span> | <span data-ttu-id="4c8c8-389">Binary</span><span class="sxs-lookup"><span data-stu-id="4c8c8-389">Binary</span></span> | <span data-ttu-id="4c8c8-390">Spostamento a sinistra, spostamento a destra</span><span class="sxs-lookup"><span data-stu-id="4c8c8-390">Left shift, right shift</span></span> | <span data-ttu-id="4c8c8-391">`Int` o `BigInt`</span><span class="sxs-lookup"><span data-stu-id="4c8c8-391">`Int` or `BigInt`</span></span>
 <span data-ttu-id="4c8c8-392">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="4c8c8-392">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="4c8c8-393">Binary</span><span class="sxs-lookup"><span data-stu-id="4c8c8-393">Binary</span></span> | <span data-ttu-id="4c8c8-394">Confronti minore di, minore di o uguale a, maggiore di, maggiore di o uguale a</span><span class="sxs-lookup"><span data-stu-id="4c8c8-394">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="4c8c8-395">`Int`, `BigInt` o `Double`</span><span class="sxs-lookup"><span data-stu-id="4c8c8-395">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="4c8c8-396">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="4c8c8-396">`==`, `!=`</span></span> | <span data-ttu-id="4c8c8-397">Binary</span><span class="sxs-lookup"><span data-stu-id="4c8c8-397">Binary</span></span> | <span data-ttu-id="4c8c8-398">confronti uguali, non uguali</span><span class="sxs-lookup"><span data-stu-id="4c8c8-398">equal, not-equal comparisons</span></span> | <span data-ttu-id="4c8c8-399">qualsiasi tipo primitivo</span><span class="sxs-lookup"><span data-stu-id="4c8c8-399">any primitive type</span></span>
 `&&&` | <span data-ttu-id="4c8c8-400">Binary</span><span class="sxs-lookup"><span data-stu-id="4c8c8-400">Binary</span></span> | <span data-ttu-id="4c8c8-401">AND bit per bit</span><span class="sxs-lookup"><span data-stu-id="4c8c8-401">Bitwise AND</span></span> | <span data-ttu-id="4c8c8-402">`Int` o `BigInt`</span><span class="sxs-lookup"><span data-stu-id="4c8c8-402">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="4c8c8-403">Binary</span><span class="sxs-lookup"><span data-stu-id="4c8c8-403">Binary</span></span> | <span data-ttu-id="4c8c8-404">XOR bit per bit</span><span class="sxs-lookup"><span data-stu-id="4c8c8-404">Bitwise XOR</span></span> | <span data-ttu-id="4c8c8-405">`Int` o `BigInt`</span><span class="sxs-lookup"><span data-stu-id="4c8c8-405">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="4c8c8-406">Binary</span><span class="sxs-lookup"><span data-stu-id="4c8c8-406">Binary</span></span> | <span data-ttu-id="4c8c8-407">OR bit per bit</span><span class="sxs-lookup"><span data-stu-id="4c8c8-407">Bitwise OR</span></span> | <span data-ttu-id="4c8c8-408">`Int` o `BigInt`</span><span class="sxs-lookup"><span data-stu-id="4c8c8-408">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="4c8c8-409">Binary</span><span class="sxs-lookup"><span data-stu-id="4c8c8-409">Binary</span></span> | <span data-ttu-id="4c8c8-410">AND logico</span><span class="sxs-lookup"><span data-stu-id="4c8c8-410">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="4c8c8-411">Binary</span><span class="sxs-lookup"><span data-stu-id="4c8c8-411">Binary</span></span> | <span data-ttu-id="4c8c8-412">OR logico</span><span class="sxs-lookup"><span data-stu-id="4c8c8-412">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="4c8c8-413">Binario/ternario</span><span class="sxs-lookup"><span data-stu-id="4c8c8-413">Binary/Ternary</span></span> | <span data-ttu-id="4c8c8-414">Operatore Range</span><span class="sxs-lookup"><span data-stu-id="4c8c8-414">Range operator</span></span> | `Int`
 <span data-ttu-id="4c8c8-415">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="4c8c8-415">`?` `|`</span></span> | <span data-ttu-id="4c8c8-416">Ternario</span><span class="sxs-lookup"><span data-stu-id="4c8c8-416">Ternary</span></span> | <span data-ttu-id="4c8c8-417">Condizionale</span><span class="sxs-lookup"><span data-stu-id="4c8c8-417">Conditional</span></span> | <span data-ttu-id="4c8c8-418">`Bool` per il lato sinistro</span><span class="sxs-lookup"><span data-stu-id="4c8c8-418">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="4c8c8-419">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="4c8c8-419">`w/` `<-`</span></span> | <span data-ttu-id="4c8c8-420">Ternario</span><span class="sxs-lookup"><span data-stu-id="4c8c8-420">Ternary</span></span> | <span data-ttu-id="4c8c8-421">Copia e aggiornamento</span><span class="sxs-lookup"><span data-stu-id="4c8c8-421">Copy-and-update</span></span> | <span data-ttu-id="4c8c8-422">Vedere [espressioni di copia e aggiornamento](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="4c8c8-422">See [Copy-and-update expressions](#copy-and-update-expressions)</span></span>

## <a name="next-steps"></a><span data-ttu-id="4c8c8-423">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="4c8c8-423">Next steps</span></span>

<span data-ttu-id="4c8c8-424">Ora che è possibile usare le espressioni in Q# , passare a [ Q# operazioni e funzioni in](xref:microsoft.quantum.guide.operationsfunctions) per informazioni su come definire e chiamare operazioni e funzioni.</span><span class="sxs-lookup"><span data-stu-id="4c8c8-424">Now that you can work with expressions in Q#, move on to [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions) to learn how to define and call operations and functions.</span></span>
