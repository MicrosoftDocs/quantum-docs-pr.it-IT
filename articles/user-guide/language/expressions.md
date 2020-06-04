---
title: 'Espressioni di tipo in Q #'
description: 'Informazioni su come specificare, fare riferimento e combinare costanti, variabili, operatori, operazioni e funzioni come espressioni in Q #.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
ms.openlocfilehash: c4b2cc0bed44ffdfb191ba522d6526959e7c6708
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327306"
---
# <a name="type-expressions-in-q"></a><span data-ttu-id="b813a-103">Espressioni di tipo in Q #</span><span class="sxs-lookup"><span data-stu-id="b813a-103">Type Expressions in Q#</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="b813a-104">Espressioni numeriche</span><span class="sxs-lookup"><span data-stu-id="b813a-104">Numeric Expressions</span></span>

<span data-ttu-id="b813a-105">Le espressioni numeriche sono espressioni di tipo `Int` , `BigInt` o `Double` .</span><span class="sxs-lookup"><span data-stu-id="b813a-105">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="b813a-106">Ovvero sono numeri interi o a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="b813a-106">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="b813a-107">`Int`i valori letterali in Q # vengono scritti semplicemente come una sequenza di cifre.</span><span class="sxs-lookup"><span data-stu-id="b813a-107">`Int` literals in Q# are written simply as a sequence of digits.</span></span>
<span data-ttu-id="b813a-108">Gli Integer esadecimali e binari sono supportati rispettivamente con un `0x` `0b` prefisso e.</span><span class="sxs-lookup"><span data-stu-id="b813a-108">Hexadecimal and binary integers are supported with a `0x` and `0b` prefix, respectively.</span></span>

<span data-ttu-id="b813a-109">`BigInt`i valori letterali in Q # vengono scritti con un `l` `L` suffisso o finale.</span><span class="sxs-lookup"><span data-stu-id="b813a-109">`BigInt` literals in Q# are written with a trailing `l` or `L` suffix.</span></span>
<span data-ttu-id="b813a-110">I Big Integer esadecimali sono supportati con un prefisso "0x".</span><span class="sxs-lookup"><span data-stu-id="b813a-110">Hexadecimal big integers are supported with a "0x" prefix.</span></span>
<span data-ttu-id="b813a-111">Di conseguenza, di seguito sono riportati tutti gli utilizzi validi dei `BigInt` valori letterali:</span><span class="sxs-lookup"><span data-stu-id="b813a-111">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="b813a-112">`Double`i valori letterali in Q # sono numeri a virgola mobile scritti con cifre decimali.</span><span class="sxs-lookup"><span data-stu-id="b813a-112">`Double` literals in Q# are floating-point numbers written using decimal digits.</span></span>
<span data-ttu-id="b813a-113">Possono essere scritti con un separatore decimale, `.` e/o una parte esponenziale indicata con "e" o "e" (dopo il quale sono validi solo un possibile segno negativo e cifre decimali).</span><span class="sxs-lookup"><span data-stu-id="b813a-113">They can be written with a decimal point, `.`, and/or an exponential part indicated with 'e' or 'E' (after which only a possible negative sign and decimal digits are valid).</span></span>
<span data-ttu-id="b813a-114">I valori letterali validi sono i seguenti `Double` : `0.0` , `1.2e5` , `1e-5` .</span><span class="sxs-lookup"><span data-stu-id="b813a-114">The following are valid `Double` literals: `0.0`, `1.2e5`, `1e-5`.</span></span>

<span data-ttu-id="b813a-115">Data un'espressione di matrice di qualsiasi tipo di elemento, un' `Int` espressione può essere formata usando la [`Length`](xref:microsoft.quantum.core.length) funzione predefinita, con l'espressione di matrice racchiusa tra parentesi, `(` e `)` .</span><span class="sxs-lookup"><span data-stu-id="b813a-115">Given an array expression of any element type, an `Int` expression may be formed using the [`Length`](xref:microsoft.quantum.core.length) built-in function, with the array expression enclosed in parentheses, `(` and `)`.</span></span>
<span data-ttu-id="b813a-116">Ad esempio, se `a` è associato a una matrice, `Length(a)` è un'espressione Integer.</span><span class="sxs-lookup"><span data-stu-id="b813a-116">For instance, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="b813a-117">Se `b` è una matrice di matrici di numeri interi, `Int[][]` , `Length(b)` è il numero di sottomatrici in `b` e `Length(b[1])` è il numero di numeri interi nella seconda sottomatrice di `b` .</span><span class="sxs-lookup"><span data-stu-id="b813a-117">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="b813a-118">Date due espressioni numeriche dello stesso tipo, gli operatori binari `+` , `-` , `*` e `/` possono essere usati per formare una nuova espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="b813a-118">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="b813a-119">Il tipo della nuova espressione sarà uguale ai tipi delle espressioni costituenti.</span><span class="sxs-lookup"><span data-stu-id="b813a-119">The type of the new expression will be the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="b813a-120">Date due espressioni Integer, l'operatore binario `^` (Power) può essere usato per formare una nuova espressione Integer.</span><span class="sxs-lookup"><span data-stu-id="b813a-120">Given two integer expressions, the binary operator `^` (power) may be used to form a new integer expression.</span></span>
<span data-ttu-id="b813a-121">Analogamente, `^` può essere usato con due espressioni doppie per formare una nuova espressione doppia.</span><span class="sxs-lookup"><span data-stu-id="b813a-121">Similarly, `^` may be used with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="b813a-122">Infine, `^` può essere usato con un Big Integer a sinistra e un numero intero a destra per formare una nuova espressione di tipo Integer grande.</span><span class="sxs-lookup"><span data-stu-id="b813a-122">Finally, `^` may be used with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="b813a-123">In questo caso, il secondo parametro deve adattarsi a 32 bit; in caso contrario, verrà generato un errore di Runtime.</span><span class="sxs-lookup"><span data-stu-id="b813a-123">In this case, the second parameter must fit into 32 bits; if not, a runtime error will be raised.</span></span>

<span data-ttu-id="b813a-124">Date due espressioni Integer o Big Integer, è possibile formare una nuova espressione Integer o Big Integer usando gli `%` operatori (modulo), `&&&` (and bit per bit), `|||` (OR bit per bit) o `^^^` (XOR bit per bit).</span><span class="sxs-lookup"><span data-stu-id="b813a-124">Given two integer or big integer expressions, a new integer or big integer expression may be formed using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="b813a-125">Data un'espressione Integer o Big Integer a sinistra e un'espressione Integer a destra, `<<<` `>>>` per creare una nuova espressione con lo stesso tipo dell'espressione a sinistra, è possibile usare gli operatori (spostamento aritmetico a sinistra) o (spostamento a destra aritmetico).</span><span class="sxs-lookup"><span data-stu-id="b813a-125">Given either an integer or big integer expression on the left, and an integer expression on the right, the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators may be used to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="b813a-126">Il secondo parametro (l'importo dello spostamento) per l'operazione di spostamento deve essere maggiore o uguale a zero; il comportamento per gli importi di spostamento negativi non è definito.</span><span class="sxs-lookup"><span data-stu-id="b813a-126">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="b813a-127">L'importo dello spostamento per entrambe le operazioni di spostamento deve rientrare anche in 32 bit; in caso contrario, verrà generato un errore di Runtime.</span><span class="sxs-lookup"><span data-stu-id="b813a-127">The shift amount for either shift operation must also fit into 32 bits; if not, a runtime error will be raised.</span></span>
<span data-ttu-id="b813a-128">Se il numero da spostare è un numero intero, l'importo dello spostamento viene interpretato, `mod 64` ovvero uno spostamento di 1 e uno spostamento di 65 hanno lo stesso effetto.</span><span class="sxs-lookup"><span data-stu-id="b813a-128">If the number to be shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="b813a-129">Per i valori integer e Big Integer, i turni sono aritmetici.</span><span class="sxs-lookup"><span data-stu-id="b813a-129">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="b813a-130">Se si sposta un valore negativo, a sinistra o a destra, viene generato un numero negativo.</span><span class="sxs-lookup"><span data-stu-id="b813a-130">Shifting a negative value either left or right will result in a negative number.</span></span>
<span data-ttu-id="b813a-131">Ovvero, lo spostamento di un passaggio verso sinistra o a destra è esattamente uguale alla moltiplicazione o alla divisione per 2, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="b813a-131">That is, shifting one step to the left or right is exactly the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="b813a-132">La divisione Integer e il modulo Integer seguono lo stesso comportamento per i numeri negativi in C#.</span><span class="sxs-lookup"><span data-stu-id="b813a-132">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span>
<span data-ttu-id="b813a-133">Ovvero, `a % b` avrà sempre lo stesso segno di `a` e `b * (a / b) + a % b` sarà sempre uguale `a` .</span><span class="sxs-lookup"><span data-stu-id="b813a-133">That is, `a % b` will always have the same sign as `a`, and `b * (a / b) + a % b` will always equal `a`.</span></span>
<span data-ttu-id="b813a-134">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b813a-134">For example:</span></span>

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 <span data-ttu-id="b813a-135">5</span><span class="sxs-lookup"><span data-stu-id="b813a-135">5</span></span> | <span data-ttu-id="b813a-136">2</span><span class="sxs-lookup"><span data-stu-id="b813a-136">2</span></span> | <span data-ttu-id="b813a-137">2</span><span class="sxs-lookup"><span data-stu-id="b813a-137">2</span></span> | <span data-ttu-id="b813a-138">1</span><span class="sxs-lookup"><span data-stu-id="b813a-138">1</span></span>
 <span data-ttu-id="b813a-139">5</span><span class="sxs-lookup"><span data-stu-id="b813a-139">5</span></span> | <span data-ttu-id="b813a-140">-2</span><span class="sxs-lookup"><span data-stu-id="b813a-140">-2</span></span> | <span data-ttu-id="b813a-141">-2</span><span class="sxs-lookup"><span data-stu-id="b813a-141">-2</span></span> | <span data-ttu-id="b813a-142">1</span><span class="sxs-lookup"><span data-stu-id="b813a-142">1</span></span>
 <span data-ttu-id="b813a-143">-5</span><span class="sxs-lookup"><span data-stu-id="b813a-143">-5</span></span> | <span data-ttu-id="b813a-144">2</span><span class="sxs-lookup"><span data-stu-id="b813a-144">2</span></span> | <span data-ttu-id="b813a-145">-2</span><span class="sxs-lookup"><span data-stu-id="b813a-145">-2</span></span> | <span data-ttu-id="b813a-146">-1</span><span class="sxs-lookup"><span data-stu-id="b813a-146">-1</span></span>
 <span data-ttu-id="b813a-147">-5</span><span class="sxs-lookup"><span data-stu-id="b813a-147">-5</span></span> | <span data-ttu-id="b813a-148">-2</span><span class="sxs-lookup"><span data-stu-id="b813a-148">-2</span></span> | <span data-ttu-id="b813a-149">2</span><span class="sxs-lookup"><span data-stu-id="b813a-149">2</span></span> | <span data-ttu-id="b813a-150">-1</span><span class="sxs-lookup"><span data-stu-id="b813a-150">-1</span></span>

<span data-ttu-id="b813a-151">La divisione e il modulo di Big Integer funzionano allo stesso modo.</span><span class="sxs-lookup"><span data-stu-id="b813a-151">Big integer division and modulus works the same way.</span></span>

<span data-ttu-id="b813a-152">Data un'espressione numerica, una nuova espressione può essere formata usando l' `-` operatore unario.</span><span class="sxs-lookup"><span data-stu-id="b813a-152">Given any numeric expression, a new expression may be formed using the `-` unary operator.</span></span>
<span data-ttu-id="b813a-153">La nuova espressione sarà dello stesso tipo dell'espressione costituente.</span><span class="sxs-lookup"><span data-stu-id="b813a-153">The new expression will be the same type as the constituent expression.</span></span>

<span data-ttu-id="b813a-154">Dato qualsiasi espressione Integer o Big Integer, è possibile formare una nuova espressione dello stesso tipo utilizzando l' `~~~` operatore unario (complemento bit per bit).</span><span class="sxs-lookup"><span data-stu-id="b813a-154">Given any integer or big integer expression, a new expression of the same type may be formed using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="b813a-155">Espressioni booleane</span><span class="sxs-lookup"><span data-stu-id="b813a-155">Boolean Expressions</span></span>

<span data-ttu-id="b813a-156">I due `Bool` valori letterali sono `true` e `false` .</span><span class="sxs-lookup"><span data-stu-id="b813a-156">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="b813a-157">Date due espressioni dello stesso tipo primitivo, gli `==` `!=` operatori binari e possono essere usati per costruire un' `Bool` espressione.</span><span class="sxs-lookup"><span data-stu-id="b813a-157">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="b813a-158">L'espressione sarà true se le due espressioni sono uguali e false in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="b813a-158">The expression will be true if the two expressions are equal, and false if not.</span></span>

<span data-ttu-id="b813a-159">I valori dei tipi definiti dall'utente non possono essere confrontati, ma è possibile confrontare solo i valori di cui non è stato eseguito il wrapper.</span><span class="sxs-lookup"><span data-stu-id="b813a-159">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="b813a-160">Ad esempio, usando l'operatore "Unwrap" `!` (illustrato in dettaglio nei [tipi in Q #](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span><span class="sxs-lookup"><span data-stu-id="b813a-160">For example, using the "unwrap" operator `!` (explained in detail at [Types in Q#](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="b813a-161">Il confronto di uguaglianza per `Qubit` i valori è uguaglianza di identità, ovvero se le due espressioni identificano lo stesso qubit.</span><span class="sxs-lookup"><span data-stu-id="b813a-161">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="b813a-162">Lo stato dei due qubits non viene confrontato, accessibile, misurato o modificato da questo confronto.</span><span class="sxs-lookup"><span data-stu-id="b813a-162">The state of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="b813a-163">Il confronto di uguaglianza per `Double` i valori può essere fuorviante a causa degli effetti dell'arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="b813a-163">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="b813a-164">Ad esempio, `49.0 * (1.0/49.0) != 1.0` .</span><span class="sxs-lookup"><span data-stu-id="b813a-164">For instance, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="b813a-165">Date due espressioni numeriche, gli operatori binari `>` , `<` , `>=` e `<=` possono essere usati per costruire una nuova espressione booleana che è true se la prima espressione è rispettivamente maggiore di, minore di, maggiore o uguale a o minore o uguale alla seconda espressione.</span><span class="sxs-lookup"><span data-stu-id="b813a-165">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="b813a-166">Date due espressioni booleane, gli `and` `or` operatori binari e possono essere usati per costruire una nuova espressione booleana che è true se entrambe le espressioni (resp. both o entrambe) sono true.</span><span class="sxs-lookup"><span data-stu-id="b813a-166">Given any two Boolean expressions, the `and` and `or` binary operators may be used to construct a new Boolean expression that is true if both of (resp. either or both of) the two expressions are true.</span></span>

<span data-ttu-id="b813a-167">Dato qualsiasi espressione booleana, l' `not` operatore unario può essere usato per costruire una nuova espressione booleana che è true se l'espressione costituente è false.</span><span class="sxs-lookup"><span data-stu-id="b813a-167">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="b813a-168">Espressioni stringa</span><span class="sxs-lookup"><span data-stu-id="b813a-168">String Expressions</span></span>

<span data-ttu-id="b813a-169">Q # consente di usare le stringhe nell' `fail` istruzione (illustrate in [flusso di controllo](xref:microsoft.quantum.guide.controlflow#fail-statement)) e nella [`Message`](xref:microsoft.quantum.intrinsic.message) funzione standard.</span><span class="sxs-lookup"><span data-stu-id="b813a-169">Q# allows strings to be used in the `fail` statement (explained at [Control Flow](xref:microsoft.quantum.guide.controlflow#fail-statement)) and in the [`Message`](xref:microsoft.quantum.intrinsic.message) standard function.</span></span>
<span data-ttu-id="b813a-170">Il comportamento specifico di quest'ultimo dipende dal simulatore usato, ma in genere scrive un messaggio nella console host quando viene chiamato durante un programma Q #.</span><span class="sxs-lookup"><span data-stu-id="b813a-170">The specific behavior of the latter depends on the simulator being used, but typically writes a message to the host console when called during a Q# program.</span></span>

<span data-ttu-id="b813a-171">Le stringhe in Q # sono valori letterali o stringhe interpolate.</span><span class="sxs-lookup"><span data-stu-id="b813a-171">Strings in Q# are either literals or interpolated strings.</span></span>

<span data-ttu-id="b813a-172">I valori letterali stringa sono simili a valori letterali stringa semplici nella maggior parte dei linguaggi: una sequenza di caratteri Unicode racchiusi tra virgolette doppie, `"` .</span><span class="sxs-lookup"><span data-stu-id="b813a-172">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double quotes, `"`.</span></span>
<span data-ttu-id="b813a-173">All'interno di una stringa, il carattere barra rovesciata `\` può essere utilizzato per eseguire l'escape di un carattere virgolette doppie e per inserire una nuova riga come `\n` , un ritorno a capo come `\r` e una tabulazione come `\t` .</span><span class="sxs-lookup"><span data-stu-id="b813a-173">Inside of a string, the back-slash character `\` may be used to escape a double quote character, and to insert a new-line as `\n`, a carriage return as `\r`, and a tab as `\t`.</span></span>
<span data-ttu-id="b813a-174">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b813a-174">For instance:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a><span data-ttu-id="b813a-175">Stringhe interpolate</span><span class="sxs-lookup"><span data-stu-id="b813a-175">Interpolated strings</span></span>

<span data-ttu-id="b813a-176">La sintassi Q # per l'interpolazione di stringhe è un subset della sintassi C#, ma vengono riepilogati i punti chiave che riguardano Q #.</span><span class="sxs-lookup"><span data-stu-id="b813a-176">The Q# syntax for string interpolations is a subset of the C# syntax, but we summarize here the key points as they pertain to Q#.</span></span>
<span data-ttu-id="b813a-177">Le distinzioni principali sono illustrate di seguito.</span><span class="sxs-lookup"><span data-stu-id="b813a-177">The main distinctions are discussed below.</span></span>

<span data-ttu-id="b813a-178">Per identificare un valore letterale stringa come stringa interpolata, anteporre a questa il simbolo `$`.</span><span class="sxs-lookup"><span data-stu-id="b813a-178">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span>
<span data-ttu-id="b813a-179">Non è possibile avere spazi vuoti tra `$` e `"` che avvia un valore letterale stringa.</span><span class="sxs-lookup"><span data-stu-id="b813a-179">You cannot have any white space between the `$`and the `"` that starts a string literal.</span></span>

<span data-ttu-id="b813a-180">Di seguito è riportato un esempio di base [`Message`](xref:microsoft.quantum.intrinsic.message) che usa la funzione per scrivere il risultato di una misurazione nella console, insieme ad altre espressioni Q #.</span><span class="sxs-lookup"><span data-stu-id="b813a-180">The following is a basic example using the [`Message`](xref:microsoft.quantum.intrinsic.message) function to write the result of a measurement to the console, alongside other Q# expressions.</span></span>

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```
<span data-ttu-id="b813a-181">In una stringa interpolata può essere presente qualsiasi espressione Q # valida.</span><span class="sxs-lookup"><span data-stu-id="b813a-181">Any valid Q# expression may appear in an interpolated string.</span></span>

<span data-ttu-id="b813a-182">Altre informazioni sulla sintassi di C# sono disponibili in [*stringhe interpolate*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span><span class="sxs-lookup"><span data-stu-id="b813a-182">Further details on the C# syntax can be found at [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span></span>
<span data-ttu-id="b813a-183">La differenza più importante è che Q # non supporta le stringhe interpolate Verbatim (a più righe).</span><span class="sxs-lookup"><span data-stu-id="b813a-183">The most notable distinction is that Q# does not support verbatim (multi-line) interpolated strings.</span></span>
<span data-ttu-id="b813a-184">Le espressioni all'interno di una stringa interpolata seguono la sintassi Q #, non la sintassi C#.</span><span class="sxs-lookup"><span data-stu-id="b813a-184">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span>

## <a name="range-expressions"></a><span data-ttu-id="b813a-185">Espressioni di intervallo</span><span class="sxs-lookup"><span data-stu-id="b813a-185">Range Expressions</span></span>

<span data-ttu-id="b813a-186">Date le tre `Int` espressioni `start` , `step` , e `stop` , `start .. step .. stop` è un'espressione di intervallo il cui primo elemento è `start` , il secondo elemento è `start+step` , il terzo elemento è `start+step+step` e così via, fino a quando non `stop` viene passato.</span><span class="sxs-lookup"><span data-stu-id="b813a-186">Given any three `Int` expressions `start`, `step`, and `stop`, `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, etc., until `stop` is passed.</span></span>
<span data-ttu-id="b813a-187">Un intervallo può essere vuoto se, ad esempio, `step` è positivo e `stop < start` .</span><span class="sxs-lookup"><span data-stu-id="b813a-187">A range may be empty if, for instance, `step` is positive and `stop < start`.</span></span>
<span data-ttu-id="b813a-188">L'ultimo elemento dell'intervallo sarà `stop` se la differenza tra `start` e `stop` è un multiplo integrale di `step` , ovvero l'intervallo è incluso a entrambe le estremità.</span><span class="sxs-lookup"><span data-stu-id="b813a-188">The last element of the range will be `stop` if the difference between `start` and `stop` is an integral multiple of `step`; that is, the range is inclusive at both ends.</span></span>

<span data-ttu-id="b813a-189">Date due `Int` espressioni qualsiasi `start` e `stop` , `start .. stop` è un'espressione di intervallo uguale a `start .. 1 .. stop` .</span><span class="sxs-lookup"><span data-stu-id="b813a-189">Given any two `Int` expressions `start` and `stop`, `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="b813a-190">Si noti che il valore implicito `step` è + 1 anche se `stop` è minore di `start` ; in tal caso, l'intervallo è vuoto.</span><span class="sxs-lookup"><span data-stu-id="b813a-190">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="b813a-191">Alcuni intervalli di esempio sono:</span><span class="sxs-lookup"><span data-stu-id="b813a-191">Some example ranges are:</span></span>

- <span data-ttu-id="b813a-192">`1..3`è l'intervallo 1, 2, 3.</span><span class="sxs-lookup"><span data-stu-id="b813a-192">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="b813a-193">`2..2..5`è l'intervallo 2, 4.</span><span class="sxs-lookup"><span data-stu-id="b813a-193">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="b813a-194">`2..2..6`è l'intervallo 2, 4, 6.</span><span class="sxs-lookup"><span data-stu-id="b813a-194">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="b813a-195">`6..-2..2`è l'intervallo 6, 4, 2.</span><span class="sxs-lookup"><span data-stu-id="b813a-195">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="b813a-196">`2..1`intervallo vuoto.</span><span class="sxs-lookup"><span data-stu-id="b813a-196">`2..1` is the empty range.</span></span>
- <span data-ttu-id="b813a-197">`2..6..7`è l'intervallo 2.</span><span class="sxs-lookup"><span data-stu-id="b813a-197">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="b813a-198">`2..2..1`intervallo vuoto.</span><span class="sxs-lookup"><span data-stu-id="b813a-198">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="b813a-199">`1..-1..2`intervallo vuoto.</span><span class="sxs-lookup"><span data-stu-id="b813a-199">`1..-1..2` is the empty range.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="b813a-200">Espressioni qubit</span><span class="sxs-lookup"><span data-stu-id="b813a-200">Qubit Expressions</span></span>

<span data-ttu-id="b813a-201">Le uniche `Qubit` espressioni sono simboli associati a `Qubit` valori o elementi di matrice di `Qubit` matrici.</span><span class="sxs-lookup"><span data-stu-id="b813a-201">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="b813a-202">Nessun `Qubit` valore letterale.</span><span class="sxs-lookup"><span data-stu-id="b813a-202">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="b813a-203">Espressioni di Pauli</span><span class="sxs-lookup"><span data-stu-id="b813a-203">Pauli Expressions</span></span>

<span data-ttu-id="b813a-204">I quattro `Pauli` valori, `PauliI` , `PauliX` , `PauliY` e `PauliZ` , sono tutte espressioni valide `Pauli` .</span><span class="sxs-lookup"><span data-stu-id="b813a-204">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="b813a-205">A parte questo, le uniche `Pauli` espressioni sono i simboli associati a `Pauli` valori o elementi di matrice di `Pauli` matrici.</span><span class="sxs-lookup"><span data-stu-id="b813a-205">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="b813a-206">Espressioni risultato</span><span class="sxs-lookup"><span data-stu-id="b813a-206">Result Expressions</span></span>

<span data-ttu-id="b813a-207">I due `Result` valori, `One` e `Zero` , sono `Result` espressioni valide.</span><span class="sxs-lookup"><span data-stu-id="b813a-207">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="b813a-208">A parte questo, le uniche `Result` espressioni sono i simboli associati a `Result` valori o elementi di matrice di `Result` matrici.</span><span class="sxs-lookup"><span data-stu-id="b813a-208">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="b813a-209">In particolare, si noti che `One` non è uguale al numero intero `1` e non esiste alcuna conversione diretta tra di essi.</span><span class="sxs-lookup"><span data-stu-id="b813a-209">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="b813a-210">Lo stesso vale per `Zero` e `0` .</span><span class="sxs-lookup"><span data-stu-id="b813a-210">The same is true for `Zero` and `0`.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="b813a-211">Espressioni di tupla</span><span class="sxs-lookup"><span data-stu-id="b813a-211">Tuple Expressions</span></span>

<span data-ttu-id="b813a-212">Un valore letterale di tupla è una sequenza di espressioni di elemento del tipo appropriato, separate da virgole, racchiuse tra `(` e `)` .</span><span class="sxs-lookup"><span data-stu-id="b813a-212">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in `(` and `)`.</span></span>
<span data-ttu-id="b813a-213">Ad esempio, `(1, One)` è un' `(Int, Result)` espressione.</span><span class="sxs-lookup"><span data-stu-id="b813a-213">For instance, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="b813a-214">Ad eccezione dei valori letterali, le uniche espressioni di tupla sono simboli associati a valori di tupla, elementi di matrice di matrici di tuple e chiamate chiamabili che restituiscono Tuple.</span><span class="sxs-lookup"><span data-stu-id="b813a-214">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="b813a-215">Espressioni di tipo definito dall'utente</span><span class="sxs-lookup"><span data-stu-id="b813a-215">User-Defined Type Expressions</span></span>

<span data-ttu-id="b813a-216">Un valore letterale di un tipo definito dall'utente è costituito dal nome del tipo seguito da un valore letterale di tupla del tipo di tupla di base del tipo.</span><span class="sxs-lookup"><span data-stu-id="b813a-216">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="b813a-217">Se, ad esempio, `IntPair` è un tipo definito dall'utente basato su `(Int, Int)` , `IntPair(2, 3)` sarà un valore letterale valido di tale tipo.</span><span class="sxs-lookup"><span data-stu-id="b813a-217">For instance, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2, 3)` would be a valid literal of that type.</span></span>

<span data-ttu-id="b813a-218">Ad eccezione dei valori letterali, le uniche espressioni di un tipo definito dall'utente sono i simboli associati a valori di quel tipo, gli elementi di matrice delle matrici di quel tipo e le chiamate richiamabili che restituiscono quel tipo.</span><span class="sxs-lookup"><span data-stu-id="b813a-218">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="b813a-219">Espressioni Unwrap</span><span class="sxs-lookup"><span data-stu-id="b813a-219">Unwrap Expressions</span></span>

<span data-ttu-id="b813a-220">In Q # l'operatore Unwrap è un punto esclamativo finale `!` .</span><span class="sxs-lookup"><span data-stu-id="b813a-220">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="b813a-221">Se, ad esempio, `IntPair` è un tipo definito dall'utente con tipo sottostante `(Int, Int)` ed `s` è una variabile con valore `IntPair(2, 3)` , `s!` sarà `(2, 3)` .</span><span class="sxs-lookup"><span data-stu-id="b813a-221">For instance, if `IntPair` is a user-defined type with underlying type `(Int, Int)`, and `s` was a variable with value `IntPair(2, 3)`, then `s!` would be `(2, 3)`.</span></span>

<span data-ttu-id="b813a-222">Per i tipi definiti dall'utente definiti in termini di altri tipi definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="b813a-222">For user-defined types defined in terms of other user-defined types.</span></span> <span data-ttu-id="b813a-223">l'operatore Unwrap può essere ripetuto; ad esempio, `s!!` indica il valore con doppia incapsulamento di `s` .</span><span class="sxs-lookup"><span data-stu-id="b813a-223">the unwrap operator may be repeated; for instance, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="b813a-224">Se, pertanto, `WrappedPair` è un tipo definito dall'utente con tipo sottostante `IntPair` e `t` è una variabile con valore `WrappedPair(IntPair(1,2))` , `t!!` sarà `(1,2)` .</span><span class="sxs-lookup"><span data-stu-id="b813a-224">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` would be `(1,2)`.</span></span>

<span data-ttu-id="b813a-225">L' `!` operatore ha una precedenza più alta rispetto a tutti gli altri operatori diversi da `[]` per l'indicizzazione e il sezionamento di matrici.</span><span class="sxs-lookup"><span data-stu-id="b813a-225">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="b813a-226">`!`e si `[]` associano in modo posizionale, ovvero `a[i]![3]` devono essere lette come `((a[i])!)[3]` : prendere il `i` ' esimo elemento di, annullare il `a` wrapping e quindi ottenere il terzo elemento del valore di cui non è stato eseguito il wrapping (che deve essere una matrice).</span><span class="sxs-lookup"><span data-stu-id="b813a-226">`!` and `[]` bind positionally; that is, `a[i]![3]` should be read as `((a[i])!)[3]`: take the `i`'th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="b813a-227">La precedenza dell' `!` operatore ha un effetto che potrebbe non essere ovvio.</span><span class="sxs-lookup"><span data-stu-id="b813a-227">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="b813a-228">Se una funzione o un'operazione restituisce un valore che viene quindi sottoposto a wrapping, la funzione o la chiamata dell'operazione deve essere racchiusa tra parentesi in modo che la tupla dell'argomento venga associata alla chiamata anziché all'annullamento del wrapping.</span><span class="sxs-lookup"><span data-stu-id="b813a-228">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="b813a-229">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b813a-229">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="b813a-230">Espressioni di matrice</span><span class="sxs-lookup"><span data-stu-id="b813a-230">Array Expressions</span></span>

<span data-ttu-id="b813a-231">Un valore letterale di matrice è una sequenza di una o più espressioni di elementi, separate da virgole, racchiuse tra `[` e `]` .</span><span class="sxs-lookup"><span data-stu-id="b813a-231">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in `[` and `]`.</span></span>
<span data-ttu-id="b813a-232">Tutti gli elementi devono essere compatibili con lo stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="b813a-232">All elements must be compatible with the same type.</span></span>

<span data-ttu-id="b813a-233">Date due matrici dello stesso tipo, l' `+` operatore binario può essere usato per formare una nuova matrice che rappresenta la concatenazione delle due matrici.</span><span class="sxs-lookup"><span data-stu-id="b813a-233">Given two arrays of the same type, the binary `+` operator may be used to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="b813a-234">Ad esempio, `[1,2,3] + [4,5,6]` è `[1,2,3,4,5,6]` .</span><span class="sxs-lookup"><span data-stu-id="b813a-234">For instance, `[1,2,3] + [4,5,6]` is `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="b813a-235">Creazione di matrici</span><span class="sxs-lookup"><span data-stu-id="b813a-235">Array Creation</span></span>

<span data-ttu-id="b813a-236">Dato un tipo e un' `Int` espressione, l' `new` operatore può essere usato per allocare una nuova matrice della dimensione specificata.</span><span class="sxs-lookup"><span data-stu-id="b813a-236">Given a type and an `Int` expression, the `new` operator may be used to allocate a new array of the given size.</span></span>
<span data-ttu-id="b813a-237">Ad esempio, `new Int[i + 1]` alloca una nuova `Int` matrice con `i + 1` gli elementi.</span><span class="sxs-lookup"><span data-stu-id="b813a-237">For instance, `new Int[i + 1]` would allocate a new `Int` array with `i + 1` elements.</span></span>

<span data-ttu-id="b813a-238">I valori letterali di matrice vuoti, `[]` , non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="b813a-238">Empty array literals, `[]`, are not allowed.</span></span>
<span data-ttu-id="b813a-239">In alternativa, `new ★[0]` se si usa, dove `★` è come segnaposto per un tipo adatto, consente a di creare la matrice desiderata di lunghezza zero.</span><span class="sxs-lookup"><span data-stu-id="b813a-239">Instead using `new ★[0]`, where `★` is as placeholder for a suitable type, allows to create the desired array of length zero.</span></span>

<span data-ttu-id="b813a-240">Gli elementi di una nuova matrice vengono inizializzati su un valore predefinito dipendente dal tipo.</span><span class="sxs-lookup"><span data-stu-id="b813a-240">The elements of a new array are initialized to a type-dependent default value.</span></span>
<span data-ttu-id="b813a-241">Nella maggior parte dei casi si tratta di una variante di zero.</span><span class="sxs-lookup"><span data-stu-id="b813a-241">In most cases this is some variation of zero.</span></span>

<span data-ttu-id="b813a-242">Per qubits e callable, che sono riferimenti a entità, non esiste un valore predefinito ragionevole.</span><span class="sxs-lookup"><span data-stu-id="b813a-242">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="b813a-243">Pertanto, per questi tipi, il valore predefinito è un riferimento non valido che non può essere utilizzato senza causare un errore di Runtime.</span><span class="sxs-lookup"><span data-stu-id="b813a-243">Thus, for these types, the default is an invalid reference that cannot be used without causing a runtime error.</span></span>
<span data-ttu-id="b813a-244">Questa operazione è simile a un riferimento null in linguaggi come C# o Java.</span><span class="sxs-lookup"><span data-stu-id="b813a-244">This is similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="b813a-245">Le matrici contenenti qubits o Callable devono essere inizializzate correttamente con valori non predefiniti prima che i relativi elementi possano essere usati in modo sicuro.</span><span class="sxs-lookup"><span data-stu-id="b813a-245">Arrays containing qubits or callables must be properly initialized with non-default values before their elements may be safely used.</span></span> <span data-ttu-id="b813a-246">È possibile trovare routine di inizializzazione appropriate in <xref:microsoft.quantum.arrays> .</span><span class="sxs-lookup"><span data-stu-id="b813a-246">Suitable initialization routines can be found in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="b813a-247">I valori predefiniti per ogni tipo sono:</span><span class="sxs-lookup"><span data-stu-id="b813a-247">The default values for each type are:</span></span>

<span data-ttu-id="b813a-248">Type</span><span class="sxs-lookup"><span data-stu-id="b813a-248">Type</span></span> | <span data-ttu-id="b813a-249">Predefinito</span><span class="sxs-lookup"><span data-stu-id="b813a-249">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="b813a-250">_Qubit non valido_</span><span class="sxs-lookup"><span data-stu-id="b813a-250">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="b813a-251">Intervallo vuoto,`1..1..0`</span><span class="sxs-lookup"><span data-stu-id="b813a-251">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="b813a-252">_chiamabile non valido_</span><span class="sxs-lookup"><span data-stu-id="b813a-252">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="b813a-253">I tipi di tupla sono elemento per elemento inizializzato.</span><span class="sxs-lookup"><span data-stu-id="b813a-253">Tuple types are initialized element-by-element.</span></span>


### <a name="array-elements"></a><span data-ttu-id="b813a-254">Elementi di matrice</span><span class="sxs-lookup"><span data-stu-id="b813a-254">Array Elements</span></span>

<span data-ttu-id="b813a-255">Data un'espressione di matrice e un' `Int` espressione, è possibile che venga creata una nuova espressione usando l' `[` `]` operatore di elemento della matrice e.</span><span class="sxs-lookup"><span data-stu-id="b813a-255">Given an array expression and an `Int` expression, a new expression may be formed using the `[` and `]` array element operator.</span></span>
<span data-ttu-id="b813a-256">La nuova espressione sarà dello stesso tipo del tipo di elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="b813a-256">The new expression will be the same type as the element type of the array.</span></span>
<span data-ttu-id="b813a-257">Ad esempio, se `a` è associato a una matrice di `Double` , `a[4]` è un' `Double` espressione.</span><span class="sxs-lookup"><span data-stu-id="b813a-257">For instance, if `a` is bound to an array of `Double`s, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="b813a-258">Se l'espressione di matrice non è un identificatore semplice, deve essere racchiusa tra parentesi per selezionare un elemento.</span><span class="sxs-lookup"><span data-stu-id="b813a-258">If the array expression is not a simple identifier, it must be enclosed in parentheses in order to select an element.</span></span>
<span data-ttu-id="b813a-259">Se, ad esempio, `a` e `b` sono entrambe matrici di `Int` , un elemento della concatenazione verrebbe espresso come:</span><span class="sxs-lookup"><span data-stu-id="b813a-259">For instance, if `a` and `b` are both arrays of `Int`s, an element from the concatenation would be expressed as:</span></span>

```qsharp
(a + b)[13]
```

<span data-ttu-id="b813a-260">Tutte le matrici in Q # sono in base zero.</span><span class="sxs-lookup"><span data-stu-id="b813a-260">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="b813a-261">Ovvero il primo elemento di una matrice `a` è sempre `a[0]` .</span><span class="sxs-lookup"><span data-stu-id="b813a-261">That is, the first element of an array `a` is always `a[0]`.</span></span>


### <a name="array-slices"></a><span data-ttu-id="b813a-262">Sezioni di matrici</span><span class="sxs-lookup"><span data-stu-id="b813a-262">Array Slices</span></span>

<span data-ttu-id="b813a-263">Data un'espressione di matrice e un' `Range` espressione, è possibile che venga creata una nuova espressione usando l' `[` operatore e la `]` sezione di matrici.</span><span class="sxs-lookup"><span data-stu-id="b813a-263">Given an array expression and a `Range` expression, a new expression may be formed using the `[` and `]` array slice operator.</span></span>
<span data-ttu-id="b813a-264">La nuova espressione sarà dello stesso tipo della matrice e conterrà gli elementi della matrice indicizzati dagli elementi dell'oggetto `Range` , nell'ordine definito da `Range` .</span><span class="sxs-lookup"><span data-stu-id="b813a-264">The new expression will be the same type as the array and will contain the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="b813a-265">Ad esempio, se `a` è associato a una matrice di `Double` , `a[3..-1..0]` è un' `Double[]` espressione che contiene i primi quattro elementi di, `a` ma in ordine inverso come appaiono in `a` .</span><span class="sxs-lookup"><span data-stu-id="b813a-265">For instance, if `a` is bound to an array of `Double`s, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="b813a-266">Se `Range` è vuoto, la sezione della matrice risultante avrà una lunghezza pari a zero.</span><span class="sxs-lookup"><span data-stu-id="b813a-266">If the `Range` is empty, then the resulting array slice will be zero length.</span></span>

<span data-ttu-id="b813a-267">Come per fare riferimento a elementi della matrice, se l'espressione di matrice non è un identificatore semplice, deve essere racchiusa tra parentesi per sezionare.</span><span class="sxs-lookup"><span data-stu-id="b813a-267">Just as with referencing array elements, if the array expression is not a simple identifier, it must be enclosed it parentheses in order to slice.</span></span>
<span data-ttu-id="b813a-268">Se `a` e `b` sono entrambe matrici di `Int` , una sezione della concatenazione verrebbe espressa come:</span><span class="sxs-lookup"><span data-stu-id="b813a-268">If `a` and `b` are both arrays of `Int`s, a slice from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a><span data-ttu-id="b813a-269">Valori di inizio/fine dedotti</span><span class="sxs-lookup"><span data-stu-id="b813a-269">Inferred start/end values</span></span>

<span data-ttu-id="b813a-270">A partire dalla versione 0,8, sono supportate le espressioni contestuali per il sezionamento dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="b813a-270">Starting with our 0.8 release, we support contextual expressions for range slicing.</span></span> <span data-ttu-id="b813a-271">In particolare, i valori iniziale e finale dell'intervallo possono essere omessi nel contesto di un'espressione di sezionamento dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="b813a-271">In particular, range start and end values may be omitted in the context of a range slicing expression.</span></span> <span data-ttu-id="b813a-272">In tal caso, il compilatore applicherà le regole seguenti per dedurre i delimitatori previsti per l'intervallo.</span><span class="sxs-lookup"><span data-stu-id="b813a-272">In that case, the compiler will apply the following rules to infer the intended delimiters for the range.</span></span> 

<span data-ttu-id="b813a-273">Ad esempio, se il valore iniziale dell'intervallo viene omesso, il valore di inizio derivato</span><span class="sxs-lookup"><span data-stu-id="b813a-273">For example, if the range start value is omitted,  then the inferred start value</span></span> 
- <span data-ttu-id="b813a-274">è zero se non è specificato alcun passaggio oppure il passaggio specificato è positivo e</span><span class="sxs-lookup"><span data-stu-id="b813a-274">is zero if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="b813a-275">lunghezza della matrice sezionata meno uno se il passaggio specificato è negativo.</span><span class="sxs-lookup"><span data-stu-id="b813a-275">is the length of sliced array minus one if the specified step is negative.</span></span> 

<span data-ttu-id="b813a-276">Se il valore finale dell'intervallo viene omesso, il valore di fine derivato</span><span class="sxs-lookup"><span data-stu-id="b813a-276">If the range end value is omitted,  then the inferred end value</span></span> 
- <span data-ttu-id="b813a-277">lunghezza della matrice sezionata meno uno se non si specifica alcun passaggio oppure il passaggio specificato è positivo e</span><span class="sxs-lookup"><span data-stu-id="b813a-277">is the length of sliced array minus one if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="b813a-278">è zero se il passaggio specificato è negativo.</span><span class="sxs-lookup"><span data-stu-id="b813a-278">is zero if the specified step is negative.</span></span> 

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

### <a name="copy-and-update-expressions"></a><span data-ttu-id="b813a-279">Espressioni di copia e aggiornamento</span><span class="sxs-lookup"><span data-stu-id="b813a-279">Copy-and-Update Expressions</span></span>

<span data-ttu-id="b813a-280">Poiché tutti i tipi Q # sono tipi di valore, con qubits che assumono un ruolo particolare, formalmente una "copia" viene creata quando un valore è associato a un simbolo o quando un simbolo viene riassociato.</span><span class="sxs-lookup"><span data-stu-id="b813a-280">Since all Q# types are value types — with the qubits taking a somewhat special role —formally a "copy" is created when a value is bound to a symbol, or when a symbol is rebound.</span></span> <span data-ttu-id="b813a-281">Ovvero, il comportamento di Q # è identico a quello in cui è stata creata una copia durante l'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="b813a-281">That is to say, the behavior of Q# is the same as if a copy were created on assignment.</span></span>
<span data-ttu-id="b813a-282">Naturalmente, in pratica, solo le parti pertinenti vengono effettivamente ricreate in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="b813a-282">Of course in practice only the relevant pieces are actually recreated as needed.</span></span> 

<span data-ttu-id="b813a-283">Questo in particolare include anche matrici.</span><span class="sxs-lookup"><span data-stu-id="b813a-283">This in particular also includes arrays.</span></span>
<span data-ttu-id="b813a-284">In particolare, non è possibile aggiornare gli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="b813a-284">In particular, it is not possible to update array items.</span></span> <span data-ttu-id="b813a-285">Per modificare una matrice esistente, è necessario sfruttare un meccanismo di *copia e aggiornamento* .</span><span class="sxs-lookup"><span data-stu-id="b813a-285">To modify an existing array requires leveraging a *copy-and-update* mechanism.</span></span>

<span data-ttu-id="b813a-286">È possibile creare nuove matrici da quelle esistenti tramite espressioni di *copia e aggiornamento* .</span><span class="sxs-lookup"><span data-stu-id="b813a-286">New arrays can be created from existing ones via *copy-and-update* expressions.</span></span>
<span data-ttu-id="b813a-287">Un'espressione di copia e aggiornamento è un'espressione nel formato `expression1 w/ expression2 <- expression3` , dove `expression1` deve essere di tipo `T[]` per un certo tipo `T` .</span><span class="sxs-lookup"><span data-stu-id="b813a-287">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where `expression1` has to be of type `T[]` for some type `T`.</span></span>
<span data-ttu-id="b813a-288">Il secondo `expression2` definisce gli indici degli elementi da modificare rispetto alla matrice in `expression1` e deve essere di tipo `Int` o di tipo `Range` .</span><span class="sxs-lookup"><span data-stu-id="b813a-288">The second `expression2` defines the indices of the element(s) to modify compared to the array in `expression1` and has to be either of type `Int` or of type `Range`.</span></span>
<span data-ttu-id="b813a-289">Se `expression2` è di tipo `Int` , `expression3` deve essere di tipo `T` .</span><span class="sxs-lookup"><span data-stu-id="b813a-289">If `expression2` is of type `Int`, `expression3` has to be of type `T`.</span></span> <span data-ttu-id="b813a-290">Se `expression2` è di tipo `Range` , `expression3` deve essere di tipo `T[]` .</span><span class="sxs-lookup"><span data-stu-id="b813a-290">If `expression2` is of type `Range`, `expression3` has to be of type `T[]`.</span></span>

<span data-ttu-id="b813a-291">Un'espressione di copia e aggiornamento `arr w/ idx <- value` costruisce una nuova matrice con tutti gli elementi impostati sull'elemento corrispondente in `arr` , ad eccezione degli elementi in `idx` , che sono impostati su uno o più elementi in `value` .</span><span class="sxs-lookup"><span data-stu-id="b813a-291">A copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding element in `arr`, except for the element(s) at `idx`, which are set to the one(s) in `value`.</span></span> <span data-ttu-id="b813a-292">Se, ad esempio, `arr` contiene una matrice `[0,1,2,3]` ,</span><span class="sxs-lookup"><span data-stu-id="b813a-292">For example, if `arr` contains an array `[0,1,2,3]`, then</span></span> 
- <span data-ttu-id="b813a-293">`arr w/ 0 <- 10`è la matrice `[10,1,2,3]` .</span><span class="sxs-lookup"><span data-stu-id="b813a-293">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="b813a-294">`arr w/ 2 <- 10`è la matrice `[0,1,10,3]` .</span><span class="sxs-lookup"><span data-stu-id="b813a-294">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="b813a-295">`arr w/ 0..2..3 <- [10,12]`è la matrice `[10,1,12,3]` .</span><span class="sxs-lookup"><span data-stu-id="b813a-295">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

#### <a name="copy-and-update-expressions-for-named-items"></a><span data-ttu-id="b813a-296">Espressioni di copia e aggiornamento per gli elementi denominati</span><span class="sxs-lookup"><span data-stu-id="b813a-296">Copy-and-update expressions for named items</span></span>

<span data-ttu-id="b813a-297">Sono presenti espressioni simili per gli elementi denominati in tipi definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="b813a-297">Similar expressions exist for named items in user-defined types.</span></span> 

<span data-ttu-id="b813a-298">Si consideri ad esempio il tipo</span><span class="sxs-lookup"><span data-stu-id="b813a-298">Consider for example the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="b813a-299">Se `c` contiene il valore di tipo `Complex(1., -1.)` , `c w/ Re <- 0.` è un'espressione di tipo `Complex` che restituisce `Complex(0., -1.)` .</span><span class="sxs-lookup"><span data-stu-id="b813a-299">If `c` contains the value of type `Complex(1., -1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0., -1.)`.</span></span>

### <a name="jagged-arrays"></a><span data-ttu-id="b813a-300">Matrici irregolari</span><span class="sxs-lookup"><span data-stu-id="b813a-300">Jagged Arrays</span></span>

<span data-ttu-id="b813a-301">Una matrice di matrici, talvolta denominata "matrice di matrici", è una matrice i cui elementi sono matrici.</span><span class="sxs-lookup"><span data-stu-id="b813a-301">A jagged array, sometimes called an "array of arrays," is an array whose elements are arrays.</span></span>
<span data-ttu-id="b813a-302">Gli elementi di una matrice irregolare possono avere dimensioni diverse.</span><span class="sxs-lookup"><span data-stu-id="b813a-302">The elements of a jagged array can be of different sizes.</span></span>
<span data-ttu-id="b813a-303">Nell'esempio seguente viene illustrato come dichiarare e inizializzare una matrice di matrici che rappresenta una tabella di moltiplicazione.</span><span class="sxs-lookup"><span data-stu-id="b813a-303">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

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

### <a name="arrays-of-callables"></a><span data-ttu-id="b813a-304">Matrici di chiamabili</span><span class="sxs-lookup"><span data-stu-id="b813a-304">Arrays of callables</span></span> 

<span data-ttu-id="b813a-305">Si noti che altre informazioni sui tipi richiamabili sono disponibili di seguito, nonché nella pagina successiva, [operazioni e funzioni in Q #](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="b813a-305">Note that more details on callable types can be found below, as well as on the next page, [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

<span data-ttu-id="b813a-306">Se il tipo di elemento comune è un'operazione o un tipo di funzione, tutti gli elementi devono avere gli stessi tipi di input e di output.</span><span class="sxs-lookup"><span data-stu-id="b813a-306">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
<span data-ttu-id="b813a-307">Il tipo di elemento della matrice supporterà qualsiasi funtori supportato da tutti gli elementi.</span><span class="sxs-lookup"><span data-stu-id="b813a-307">The element type of the array will support any functors that are supported by all of the elements.</span></span>
<span data-ttu-id="b813a-308">Se, ad esempio `Op1` ,, `Op2` e `Op3` sono tutti `Qubit[] => Unit` , ma `Op1` supporta, supporta e supporta `Adjoint` `Op2` `Controlled` `Op3` entrambi:</span><span class="sxs-lookup"><span data-stu-id="b813a-308">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="b813a-309">`[Op1, Op2]`è una matrice di `(Qubit[] => Unit)` operazioni.</span><span class="sxs-lookup"><span data-stu-id="b813a-309">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
- <span data-ttu-id="b813a-310">`[Op1, Op3]`è una matrice di `(Qubit[] => Unit is Adj)` operazioni.</span><span class="sxs-lookup"><span data-stu-id="b813a-310">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
- <span data-ttu-id="b813a-311">`[Op2, Op3]`è una matrice di `(Qubit[] => Unit is Ctl)` operazioni.</span><span class="sxs-lookup"><span data-stu-id="b813a-311">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="b813a-312">Tuttavia, mentre `(Qubit[] => Unit is Adj)` le `(Qubit[] => Unit is Ctl)` operazioni e hanno il tipo di base comune di `(Qubit[] => Unit)` , si noti che le matrici *di* questi operatori non condividono un tipo di base comune.</span><span class="sxs-lookup"><span data-stu-id="b813a-312">However, while `(Qubit[] => Unit is Adj)` and  `(Qubit[] => Unit is Ctl)` operations have the common base type of `(Qubit[] => Unit)`, note that arrays *of* these operators do not share a common base type.</span></span> <span data-ttu-id="b813a-313">Al momento, ad esempio, `[[Op1], [Op2]]` genera un errore perché tenta di creare una matrice di tipi di matrici incompatibili `(Qubit[] => Unit is Adj)[]` e `(Qubit[] => Unit is Ctl)[]` .</span><span class="sxs-lookup"><span data-stu-id="b813a-313">For example, `[[Op1], [Op2]]` would currently raise an error because it is attempting to create an array of the incompatible array types `(Qubit[] => Unit is Adj)[]` and `(Qubit[] => Unit is Ctl)[]`.</span></span>


## <a name="conditional-expressions"></a><span data-ttu-id="b813a-314">Espressioni condizionali</span><span class="sxs-lookup"><span data-stu-id="b813a-314">Conditional Expressions</span></span>

<span data-ttu-id="b813a-315">Date due altre espressioni dello stesso tipo e di un'espressione booleana, l'espressione condizionale può essere formata usando il punto interrogativo `?` e la barra verticale `|` .</span><span class="sxs-lookup"><span data-stu-id="b813a-315">Given two other expressions of the same type and a Boolean expression, the conditional expression may be formed using the question mark `?` and the vertical bar `|`.</span></span>
<span data-ttu-id="b813a-316">Ad esempio, `a==b ? c | d` .</span><span class="sxs-lookup"><span data-stu-id="b813a-316">For instance, `a==b ? c | d`.</span></span>
<span data-ttu-id="b813a-317">In questo esempio, il valore dell'espressione condizionale sarà `c` se `a==b` è true e `d` se è false.</span><span class="sxs-lookup"><span data-stu-id="b813a-317">In this example, the value of the conditional expression will be `c` if `a==b` is true and `d` if it is false.</span></span>

### <a name="conditional-expressions-with-callables"></a><span data-ttu-id="b813a-318">Espressioni condizionali con Callable</span><span class="sxs-lookup"><span data-stu-id="b813a-318">Conditional expressions with callables</span></span>

<span data-ttu-id="b813a-319">Le due espressioni possono restituire operazioni con gli stessi input e output ma supportano funtori diversi.</span><span class="sxs-lookup"><span data-stu-id="b813a-319">The two expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span>
<span data-ttu-id="b813a-320">In questo caso, il tipo dell'espressione condizionale è un'operazione con gli input e gli output che supportano qualsiasi funtori supportato da entrambe le espressioni.</span><span class="sxs-lookup"><span data-stu-id="b813a-320">In this case, the type of the conditional expression is an operation with those inputs and outputs that supports any functors supported by both expressions.</span></span>
<span data-ttu-id="b813a-321">Se, ad esempio `Op1` ,, `Op2` e `Op3` sono tutti `Qubit[]=>Unit` , ma `Op1` supporta, supporta e supporta `Adjoint` `Op2` `Controlled` `Op3` entrambi:</span><span class="sxs-lookup"><span data-stu-id="b813a-321">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="b813a-322">`flag ? Op1 | Op2`è un' `(Qubit[] => Unit)` operazione.</span><span class="sxs-lookup"><span data-stu-id="b813a-322">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="b813a-323">`flag ? Op1 | Op3`è un' `(Qubit[] => Unit is Adj)` operazione.</span><span class="sxs-lookup"><span data-stu-id="b813a-323">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="b813a-324">`flag ? Op2 | Op3`è un' `(Qubit[] => Unit is Ctl)` operazione.</span><span class="sxs-lookup"><span data-stu-id="b813a-324">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="b813a-325">Se una delle due espressioni di risultato possibili include una funzione o una chiamata a un'operazione, la chiamata verrà eseguita solo se il risultato è quello che sarà il valore della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b813a-325">If either of the two possible result expressions include a function or operation call, that call will only take place if that result is the one that will be the value of the call.</span></span>
<span data-ttu-id="b813a-326">Nel caso, ad esempio, `a==b ? C(qs) | D(qs)` se `a==b` è true, l' `C` operazione verrà richiamata e se è false verrà `D` richiamato solo.</span><span class="sxs-lookup"><span data-stu-id="b813a-326">For instance, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true then the `C` operation will be invoked, and if it is false then only `D` will be invoked.</span></span>
<span data-ttu-id="b813a-327">Questa operazione è simile a un cortocircuito in altri linguaggi.</span><span class="sxs-lookup"><span data-stu-id="b813a-327">This is similar to short-circuiting in other languages.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="b813a-328">Espressioni richiamabili</span><span class="sxs-lookup"><span data-stu-id="b813a-328">Callable Expressions</span></span>

<span data-ttu-id="b813a-329">Un valore letterale chiamabile è il nome di un'operazione o di una funzione definita nell'ambito di compilazione.</span><span class="sxs-lookup"><span data-stu-id="b813a-329">A callable literal is the name of an operation or function defined in the compilation scope.</span></span>
<span data-ttu-id="b813a-330">Ad esempio, `X` è un valore letterale di operazione che fa riferimento all'operazione della libreria standard `X` e `Message` è un valore letterale di funzione che fa riferimento alla funzione della libreria standard `Message` .</span><span class="sxs-lookup"><span data-stu-id="b813a-330">For instance, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="b813a-331">Se un'operazione supporta il `Adjoint` functor, `Adjoint op` è un'espressione dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="b813a-331">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="b813a-332">Analogamente, se l'operazione supporta il `Controlled` functor, `Controlled op` è un'espressione dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="b813a-332">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="b813a-333">I tipi di queste espressioni vengono specificati durante le [specializzazioni delle operazioni di chiamata](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span><span class="sxs-lookup"><span data-stu-id="b813a-333">The types of these expressions are specified at [Calling operation specializations](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span></span>

<span data-ttu-id="b813a-334">Funtori ( `Adjoint` e `Controlled` ) vengono associati in modo più accurato rispetto a tutti gli altri operatori, ad eccezione dell'operatore Unwrap `!` e dell'indicizzazione della matrice con []'.</span><span class="sxs-lookup"><span data-stu-id="b813a-334">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with []\`.</span></span>
<span data-ttu-id="b813a-335">Pertanto, di seguito sono riportate tutte le informazioni legali, supponendo che le operazioni supportino i funtori utilizzati:</span><span class="sxs-lookup"><span data-stu-id="b813a-335">Thus, the following are all legal, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a><span data-ttu-id="b813a-336">Espressioni chiamabili con parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="b813a-336">Type-parameterized callable expressions</span></span>

<span data-ttu-id="b813a-337">Un valore letterale chiamabile può essere usato come valore, ad esempio per assegnare a una variabile o per passare a un altro oggetto chiamabile.</span><span class="sxs-lookup"><span data-stu-id="b813a-337">A callable literal may be used as a value, say to assign to a variable or to pass to another callable.</span></span>
<span data-ttu-id="b813a-338">In questo caso, se l'oggetto chiamabile dispone di [parametri di tipo](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), questi devono essere forniti come parte del valore chiamabile.</span><span class="sxs-lookup"><span data-stu-id="b813a-338">In this case, if the callable has [type parameters](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), they must be provided as part of the callable value.</span></span>
<span data-ttu-id="b813a-339">Un valore chiamabile non può avere parametri di tipo non specificati.</span><span class="sxs-lookup"><span data-stu-id="b813a-339">A callable value cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="b813a-340">Ad esempio, se `Fun` è una funzione con firma `'T1->Unit` :</span><span class="sxs-lookup"><span data-stu-id="b813a-340">For instance, if `Fun` is a function with signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="b813a-341">Espressioni di chiamata chiamabili</span><span class="sxs-lookup"><span data-stu-id="b813a-341">Callable Invocation Expressions</span></span>

<span data-ttu-id="b813a-342">Data un'espressione chiamabile (operazione o funzione) e un'espressione di tupla del tipo di input della firma richiamabile, un'espressione di chiamata può essere formata aggiungendo l'espressione di tupla all'espressione chiamabile.</span><span class="sxs-lookup"><span data-stu-id="b813a-342">Given a callable (operation or function) expression and a tuple expression of the input type of the callable's signature, an invocation expression may be formed by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="b813a-343">Il tipo dell'espressione di chiamata è il tipo di output della firma richiamabile.</span><span class="sxs-lookup"><span data-stu-id="b813a-343">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="b813a-344">Se, ad esempio, `Op` è un'operazione con firma `((Int, Qubit) => Double)` , `Op(3, qubit1)` è un'espressione di tipo `Double` .</span><span class="sxs-lookup"><span data-stu-id="b813a-344">For example, if `Op` is an operation with signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="b813a-345">Analogamente, se `Sin` è una funzione con firma `(Double -> Double)` , `Sin(0.1)` è un'espressione di tipo `Double` .</span><span class="sxs-lookup"><span data-stu-id="b813a-345">Similarly, if `Sin` is a function with signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="b813a-346">Infine, se `Builder` è una funzione con firma `(Int -> (Int -> Int))` , `Builder(3)` è una funzione da a int.</span><span class="sxs-lookup"><span data-stu-id="b813a-346">Finally, if `Builder` is a function with signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from Into to Int.</span></span>

<span data-ttu-id="b813a-347">Per richiamare il risultato di un'espressione con valori richiamabili è necessaria una coppia aggiuntiva di parentesi intorno all'espressione chiamabile.</span><span class="sxs-lookup"><span data-stu-id="b813a-347">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="b813a-348">Pertanto, per richiamare il risultato della chiamata `Builder` dal paragrafo precedente, la sintassi corretta è la seguente:</span><span class="sxs-lookup"><span data-stu-id="b813a-348">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="b813a-349">Quando si richiama un oggetto chiamabile con [parametri di tipo](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) , i parametri di tipo effettivi possono essere specificati tra parentesi angolari `<` e `>` dopo l'espressione chiamabile.</span><span class="sxs-lookup"><span data-stu-id="b813a-349">When invoking a [type-parameterized](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) callable, the actual type parameters may be specified within angle brackets `<` and `>` after the callable expression.</span></span>
<span data-ttu-id="b813a-350">Questa operazione non è in genere necessaria perché il compilatore Q # dedurrà i tipi effettivi.</span><span class="sxs-lookup"><span data-stu-id="b813a-350">This is usually unnecessary as the Q# compiler will infer the actual types.</span></span>
<span data-ttu-id="b813a-351">Tuttavia, è *necessario per* l' [applicazione parziale](xref:microsoft.quantum.guide.operationsfunctions#partial-application) se un argomento con parametri di tipo non è specificato.</span><span class="sxs-lookup"><span data-stu-id="b813a-351">However, it *is* required for [partial application](xref:microsoft.quantum.guide.operationsfunctions#partial-application) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="b813a-352">A volte può essere utile anche quando si passano operazioni con diversi supporti functor a un oggetto chiamabile.</span><span class="sxs-lookup"><span data-stu-id="b813a-352">It is also sometimes useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="b813a-353">Ad esempio, se `Func` ha `('T1, 'T2, 'T1) -> 'T2` la firma `Op1` e `Op2` hanno `(Qubit[] => Unit is Adj)` la firma e `Op3` ha `(Qubit[] => Unit)` la firma, da richiamare `Func` con `Op1` come primo argomento, `Op2` come secondo e `Op3` come terzo:</span><span class="sxs-lookup"><span data-stu-id="b813a-353">For instance, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="b813a-354">La specifica del tipo è obbligatoria perché `Op3` e `Op1` hanno tipi diversi, pertanto il compilatore lo considererà ambiguo senza la specifica.</span><span class="sxs-lookup"><span data-stu-id="b813a-354">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="b813a-355">Ordine di precedenza degli operatori</span><span class="sxs-lookup"><span data-stu-id="b813a-355">Operator Precedence</span></span>

<span data-ttu-id="b813a-356">Tutti gli operatori binari sono associativi a destra, ad eccezione di `^` .</span><span class="sxs-lookup"><span data-stu-id="b813a-356">All binary operators are right-associative, except for `^`.</span></span>

<span data-ttu-id="b813a-357">Le parentesi quadre `[` e, `]` per l'indicizzazione e l'indicizzazione della matrice, vengono associate prima di qualsiasi operatore.</span><span class="sxs-lookup"><span data-stu-id="b813a-357">Brackets, `[` and `]`, for array slicing and indexing, bind before any operator.</span></span>

<span data-ttu-id="b813a-358">Funtori `Adjoint` e `Controlled` Bind dopo l'indicizzazione della matrice ma prima di tutti gli altri operatori.</span><span class="sxs-lookup"><span data-stu-id="b813a-358">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

<span data-ttu-id="b813a-359">Anche le parentesi per la chiamata di operazioni e funzioni vengono associate prima di qualsiasi operatore, ma dopo l'indicizzazione della matrice e funtori.</span><span class="sxs-lookup"><span data-stu-id="b813a-359">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="b813a-360">Operatori in ordine di precedenza, dal più alto al più basso:</span><span class="sxs-lookup"><span data-stu-id="b813a-360">Operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="b813a-361">Operatore</span><span class="sxs-lookup"><span data-stu-id="b813a-361">Operator</span></span> | <span data-ttu-id="b813a-362">Grado</span><span class="sxs-lookup"><span data-stu-id="b813a-362">Arity</span></span> | <span data-ttu-id="b813a-363">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b813a-363">Description</span></span> | <span data-ttu-id="b813a-364">Tipi di operando</span><span class="sxs-lookup"><span data-stu-id="b813a-364">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="b813a-365">finali`!`</span><span class="sxs-lookup"><span data-stu-id="b813a-365">trailing `!`</span></span> | <span data-ttu-id="b813a-366">Unaria</span><span class="sxs-lookup"><span data-stu-id="b813a-366">Unary</span></span> | <span data-ttu-id="b813a-367">Unwrap</span><span class="sxs-lookup"><span data-stu-id="b813a-367">Unwrap</span></span> | <span data-ttu-id="b813a-368">Qualsiasi tipo definito dall'utente</span><span class="sxs-lookup"><span data-stu-id="b813a-368">Any user-defined type</span></span>
 <span data-ttu-id="b813a-369">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="b813a-369">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="b813a-370">Unaria</span><span class="sxs-lookup"><span data-stu-id="b813a-370">Unary</span></span> | <span data-ttu-id="b813a-371">Valore numerico negativo, complemento bit per bit, negazione logica</span><span class="sxs-lookup"><span data-stu-id="b813a-371">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="b813a-372">`Int`, `BigInt` o `Double` per `-` , `Int` o `BigInt` per `~~~` , `Bool` per`not`</span><span class="sxs-lookup"><span data-stu-id="b813a-372">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="b813a-373">Binario</span><span class="sxs-lookup"><span data-stu-id="b813a-373">Binary</span></span> | <span data-ttu-id="b813a-374">Potenza intera</span><span class="sxs-lookup"><span data-stu-id="b813a-374">Integer power</span></span> | <span data-ttu-id="b813a-375">`Int`o `BigInt` per la base, `Int` per l'esponente</span><span class="sxs-lookup"><span data-stu-id="b813a-375">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="b813a-376">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="b813a-376">`/`, `*`, `%`</span></span> | <span data-ttu-id="b813a-377">Binario</span><span class="sxs-lookup"><span data-stu-id="b813a-377">Binary</span></span> | <span data-ttu-id="b813a-378">Divisione, moltiplicazione, modulo Integer</span><span class="sxs-lookup"><span data-stu-id="b813a-378">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="b813a-379">`Int`, `BigInt` oppure `Double` per `/` e `*` `Int` o `BigInt` per`%`</span><span class="sxs-lookup"><span data-stu-id="b813a-379">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="b813a-380">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="b813a-380">`+`, `-`</span></span> | <span data-ttu-id="b813a-381">Binario</span><span class="sxs-lookup"><span data-stu-id="b813a-381">Binary</span></span> | <span data-ttu-id="b813a-382">Aggiunta o concatenazione di stringhe e matrici, sottrazione</span><span class="sxs-lookup"><span data-stu-id="b813a-382">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="b813a-383">`Int``BigInt`o `Double` , inoltre, `String` o qualsiasi tipo di matrice per`+`</span><span class="sxs-lookup"><span data-stu-id="b813a-383">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="b813a-384">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="b813a-384">`<<<`, `>>>`</span></span> | <span data-ttu-id="b813a-385">Binario</span><span class="sxs-lookup"><span data-stu-id="b813a-385">Binary</span></span> | <span data-ttu-id="b813a-386">Spostamento a sinistra, spostamento a destra</span><span class="sxs-lookup"><span data-stu-id="b813a-386">Left shift, right shift</span></span> | <span data-ttu-id="b813a-387">`Int` o `BigInt`</span><span class="sxs-lookup"><span data-stu-id="b813a-387">`Int` or `BigInt`</span></span>
 <span data-ttu-id="b813a-388">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="b813a-388">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="b813a-389">Binario</span><span class="sxs-lookup"><span data-stu-id="b813a-389">Binary</span></span> | <span data-ttu-id="b813a-390">Confronti minore di, minore di o uguale a, maggiore di, maggiore di o uguale a</span><span class="sxs-lookup"><span data-stu-id="b813a-390">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="b813a-391">`Int``BigInt`o`Double`</span><span class="sxs-lookup"><span data-stu-id="b813a-391">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="b813a-392">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="b813a-392">`==`, `!=`</span></span> | <span data-ttu-id="b813a-393">Binario</span><span class="sxs-lookup"><span data-stu-id="b813a-393">Binary</span></span> | <span data-ttu-id="b813a-394">confronti uguali, non uguali</span><span class="sxs-lookup"><span data-stu-id="b813a-394">equal, not-equal comparisons</span></span> | <span data-ttu-id="b813a-395">qualsiasi tipo primitivo</span><span class="sxs-lookup"><span data-stu-id="b813a-395">any primitive type</span></span>
 `&&&` | <span data-ttu-id="b813a-396">Binario</span><span class="sxs-lookup"><span data-stu-id="b813a-396">Binary</span></span> | <span data-ttu-id="b813a-397">AND bit per bit</span><span class="sxs-lookup"><span data-stu-id="b813a-397">Bitwise AND</span></span> | <span data-ttu-id="b813a-398">`Int` o `BigInt`</span><span class="sxs-lookup"><span data-stu-id="b813a-398">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="b813a-399">Binario</span><span class="sxs-lookup"><span data-stu-id="b813a-399">Binary</span></span> | <span data-ttu-id="b813a-400">XOR bit per bit</span><span class="sxs-lookup"><span data-stu-id="b813a-400">Bitwise XOR</span></span> | <span data-ttu-id="b813a-401">`Int` o `BigInt`</span><span class="sxs-lookup"><span data-stu-id="b813a-401">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="b813a-402">Binario</span><span class="sxs-lookup"><span data-stu-id="b813a-402">Binary</span></span> | <span data-ttu-id="b813a-403">OR bit per bit</span><span class="sxs-lookup"><span data-stu-id="b813a-403">Bitwise OR</span></span> | <span data-ttu-id="b813a-404">`Int` o `BigInt`</span><span class="sxs-lookup"><span data-stu-id="b813a-404">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="b813a-405">Binario</span><span class="sxs-lookup"><span data-stu-id="b813a-405">Binary</span></span> | <span data-ttu-id="b813a-406">AND logico</span><span class="sxs-lookup"><span data-stu-id="b813a-406">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="b813a-407">Binario</span><span class="sxs-lookup"><span data-stu-id="b813a-407">Binary</span></span> | <span data-ttu-id="b813a-408">OR logico</span><span class="sxs-lookup"><span data-stu-id="b813a-408">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="b813a-409">Binario/ternario</span><span class="sxs-lookup"><span data-stu-id="b813a-409">Binary/Ternary</span></span> | <span data-ttu-id="b813a-410">Operatore Range</span><span class="sxs-lookup"><span data-stu-id="b813a-410">Range operator</span></span> | `Int`
 <span data-ttu-id="b813a-411">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="b813a-411">`?` `|`</span></span> | <span data-ttu-id="b813a-412">Ternario</span><span class="sxs-lookup"><span data-stu-id="b813a-412">Ternary</span></span> | <span data-ttu-id="b813a-413">Condizionale</span><span class="sxs-lookup"><span data-stu-id="b813a-413">Conditional</span></span> | <span data-ttu-id="b813a-414">`Bool`per il lato sinistro</span><span class="sxs-lookup"><span data-stu-id="b813a-414">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="b813a-415">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="b813a-415">`w/` `<-`</span></span> | <span data-ttu-id="b813a-416">Ternario</span><span class="sxs-lookup"><span data-stu-id="b813a-416">Ternary</span></span> | <span data-ttu-id="b813a-417">Copia e aggiornamento</span><span class="sxs-lookup"><span data-stu-id="b813a-417">Copy-and-update</span></span> | <span data-ttu-id="b813a-418">vedere [espressioni di copia e aggiornamento](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="b813a-418">see [copy-and-update expressions](#copy-and-update-expressions)</span></span>

## <a name="next-steps"></a><span data-ttu-id="b813a-419">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="b813a-419">Next steps</span></span>

<span data-ttu-id="b813a-420">Ora che è possibile usare le espressioni in Q #, è possibile passare alle [operazioni e alle funzioni in q #](xref:microsoft.quantum.guide.operationsfunctions) per informazioni su come definire e chiamare operazioni e funzioni.</span><span class="sxs-lookup"><span data-stu-id="b813a-420">Now that you can work with expressions in Q#, you can head to [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions) to learn how to define and call operations and functions.</span></span>
