---
title: Espressioni | Microsoft Docs
description: Espressioni
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.expressions
ms.openlocfilehash: 83fe697aa07a8ab28bd64437c8f5746bc5893b27
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036315"
---
# <a name="expressions"></a><span data-ttu-id="6d79d-103">Espressioni</span><span class="sxs-lookup"><span data-stu-id="6d79d-103">Expressions</span></span>

## <a name="grouping"></a><span data-ttu-id="6d79d-104">Raggruppamento</span><span class="sxs-lookup"><span data-stu-id="6d79d-104">Grouping</span></span>

<span data-ttu-id="6d79d-105">Dato qualsiasi espressione, la stessa espressione racchiusa tra parentesi è un'espressione dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="6d79d-105">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="6d79d-106">Ad esempio, `(7)` è un'espressione `Int`, `([1,2,3])` è un'espressione di tipo matrice di `Int`s e `((1,2))` è un'espressione con tipo `(Int, Int)`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-106">For instance, `(7)` is an `Int` expression, `([1,2,3])` is an expression of type array of `Int`s, and `((1,2))` is an expression with type `(Int, Int)`.</span></span>

<span data-ttu-id="6d79d-107">L'equivalenza tra i valori semplici e le tuple a elemento singolo descritte nel [modello di tipo](xref:microsoft.quantum.language.type-model#tuple-types) consente di rimuovere l'ambiguità tra `(6)` come gruppo e `(6)` come tupla con un solo elemento.</span><span class="sxs-lookup"><span data-stu-id="6d79d-107">The equivalence between simple values and single-element tuples described in [the type model](xref:microsoft.quantum.language.type-model#tuple-types) removes the ambiguity between `(6)` as a group and `(6)` as a single-element tuple.</span></span>

## <a name="symbols"></a><span data-ttu-id="6d79d-108">Symbols</span><span class="sxs-lookup"><span data-stu-id="6d79d-108">Symbols</span></span>

<span data-ttu-id="6d79d-109">Il nome di un simbolo associato o assegnato a un valore di tipo `'T` è un'espressione di tipo `'T`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-109">The name of a symbol bound or assigned to a value of type `'T` is an expression of type `'T`.</span></span>
<span data-ttu-id="6d79d-110">Ad esempio, se il simbolo `count` viene associato al valore integer `5`, `count` è un'espressione Integer.</span><span class="sxs-lookup"><span data-stu-id="6d79d-110">For instance, if the symbol `count` is bound to the integer value `5`, then `count` is an integer expression.</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="6d79d-111">Espressioni numeriche</span><span class="sxs-lookup"><span data-stu-id="6d79d-111">Numeric Expressions</span></span>

<span data-ttu-id="6d79d-112">Le espressioni numeriche sono espressioni di tipo `Int`, `BigInt`o `Double`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-112">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="6d79d-113">Ovvero sono numeri interi o a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="6d79d-113">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="6d79d-114">`Int` valori letterali in Q # sono identici a valori letterali integer in, ad eccezione del C#fatto che non è necessario (o consentito) la "l" o "l" finale.</span><span class="sxs-lookup"><span data-stu-id="6d79d-114">`Int` literals in Q# are identical to integer literals in C#, except that no trailing "l" or "L" is required (or allowed).</span></span>
<span data-ttu-id="6d79d-115">Gli Integer esadecimali e binari sono supportati rispettivamente con un prefisso "0x" e "0B".</span><span class="sxs-lookup"><span data-stu-id="6d79d-115">Hexadecimal and binary integers are supported with a "0x" and "0b" prefix respectively.</span></span>

<span data-ttu-id="6d79d-116">`BigInt` valori letterali in Q # sono identici alle stringhe di grandi dimensioni di tipo integer in .NET, con una "l" o "L" finale.</span><span class="sxs-lookup"><span data-stu-id="6d79d-116">`BigInt` literals in Q# are identical to big integer strings in .NET, with a trailing "l" or "L".</span></span>
<span data-ttu-id="6d79d-117">I Big Integer esadecimali sono supportati con un prefisso "0x".</span><span class="sxs-lookup"><span data-stu-id="6d79d-117">Hexadecimal big integers are supported with a "0x" prefix.</span></span>
<span data-ttu-id="6d79d-118">Di conseguenza, di seguito sono riportati tutti gli utilizzi validi dei valori letterali `BigInt`:</span><span class="sxs-lookup"><span data-stu-id="6d79d-118">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="6d79d-119">`Double` valori letterali in Q # sono identici a valori letterali doppi in, ad eccezione del C#fatto che nessun carattere "d" o "d" finale è obbligatorio (o consentito).</span><span class="sxs-lookup"><span data-stu-id="6d79d-119">`Double` literals in Q# are identical to double literals in C#, except that no trailing "d" or "D" is required (or allowed).</span></span>

<span data-ttu-id="6d79d-120">Data un'espressione di matrice di qualsiasi tipo di elemento, è possibile creare un'espressione `Int` usando la funzione incorporata `Length`, con l'espressione di matrice racchiusa tra parentesi, `(` e `)`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-120">Given an array expression of any element type, an `Int` expression may be formed using the `Length` built-in function, with the array expression enclosed in parentheses, `(` and `)`.</span></span>
<span data-ttu-id="6d79d-121">Se ad esempio `a` è associato a una matrice, `Length(a)` è un'espressione Integer.</span><span class="sxs-lookup"><span data-stu-id="6d79d-121">For instance, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="6d79d-122">Se `b` è una matrice di matrici di numeri interi, `Int[][]`, `Length(b)` è il numero di sottomatrici in `b`e `Length(b[1])` è il numero di numeri interi nella seconda matrice secondaria in `b`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-122">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="6d79d-123">Date due espressioni numeriche dello stesso tipo, è possibile usare gli operatori binari `+`, `-`, `*`e `/` per formare una nuova espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="6d79d-123">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="6d79d-124">Il tipo della nuova espressione sarà uguale ai tipi delle espressioni costituenti.</span><span class="sxs-lookup"><span data-stu-id="6d79d-124">The type of the new expression will be the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="6d79d-125">Date due espressioni Integer, l'operatore binario `^` (Power) può essere usato per formare una nuova espressione Integer.</span><span class="sxs-lookup"><span data-stu-id="6d79d-125">Given two integer expressions, the binary operator `^` (power) may be used to form a new integer expression.</span></span>
<span data-ttu-id="6d79d-126">Analogamente, è possibile usare `^` con due espressioni doppie per formare una nuova espressione doppia.</span><span class="sxs-lookup"><span data-stu-id="6d79d-126">Similarly, `^` may be used with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="6d79d-127">Infine, `^` possibile usare con un numero intero grande a sinistra e un numero intero a destra per formare una nuova espressione di tipo Integer grande.</span><span class="sxs-lookup"><span data-stu-id="6d79d-127">Finally, `^` may be used with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="6d79d-128">In questo caso, il secondo parametro deve adattarsi a 32 bit; in caso contrario, verrà generato un errore di Runtime.</span><span class="sxs-lookup"><span data-stu-id="6d79d-128">In this case, the second parameter must fit into 32 bits; if not, a runtime error will be raised.</span></span>

<span data-ttu-id="6d79d-129">Date due espressioni Integer o Big Integer, è possibile che venga creata una nuova espressione Integer o Big Integer usando gli operatori `%` (modulo), `&&&` (AND bit per bit), `|||` (OR bit per bit) o `^^^` (XOR bit per bit).</span><span class="sxs-lookup"><span data-stu-id="6d79d-129">Given two integer or big integer expressions, a new integer or big integer expression may be formed using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="6d79d-130">Dato un Integer o un'espressione di tipo Integer a sinistra e un'espressione Integer a destra, è possibile usare gli operatori `<<<` (scorrimento a sinistra aritmetico) o `>>>` (di spostamento a destra aritmetico) per creare una nuova espressione con lo stesso tipo dell'espressione di sinistra.</span><span class="sxs-lookup"><span data-stu-id="6d79d-130">Given either an integer or big integer expression on the left, and an integer expression on the right, the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators may be used to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="6d79d-131">Il secondo parametro (l'importo dello spostamento) per l'operazione di spostamento deve essere maggiore o uguale a zero; il comportamento per gli importi di spostamento negativi non è definito.</span><span class="sxs-lookup"><span data-stu-id="6d79d-131">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="6d79d-132">L'importo dello spostamento per entrambe le operazioni di spostamento deve rientrare anche in 32 bit; in caso contrario, verrà generato un errore di Runtime.</span><span class="sxs-lookup"><span data-stu-id="6d79d-132">The shift amount for either shift operation must also fit into 32 bits; if not, a runtime error will be raised.</span></span>
<span data-ttu-id="6d79d-133">Se il numero da spostare è un numero intero, l'importo dello spostamento viene interpretato `mod 64`; ovvero uno spostamento di 1 e uno spostamento di 65 hanno lo stesso effetto.</span><span class="sxs-lookup"><span data-stu-id="6d79d-133">If the number to be shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="6d79d-134">Per i valori integer e Big Integer, i turni sono aritmetici.</span><span class="sxs-lookup"><span data-stu-id="6d79d-134">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="6d79d-135">Se si sposta un valore negativo, a sinistra o a destra, viene generato un numero negativo.</span><span class="sxs-lookup"><span data-stu-id="6d79d-135">Shifting a negative value either left or right will result in a negative number.</span></span>
<span data-ttu-id="6d79d-136">Ovvero, lo spostamento di un passaggio verso sinistra o a destra è esattamente uguale alla moltiplicazione o alla divisione per 2, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="6d79d-136">That is, shifting one step to the left or right is exactly the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="6d79d-137">La divisione Integer e il modulo Integer seguono lo stesso comportamento per i C#numeri negativi di.</span><span class="sxs-lookup"><span data-stu-id="6d79d-137">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span>
<span data-ttu-id="6d79d-138">Ovvero `a % b` avrà sempre lo stesso segno di `a`e `b * (a / b) + a % b` sarà sempre uguale `a`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-138">That is, `a % b` will always have the same sign as `a`, and `b * (a / b) + a % b` will always equal `a`.</span></span>
<span data-ttu-id="6d79d-139">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6d79d-139">For example:</span></span>

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 <span data-ttu-id="6d79d-140">5</span><span class="sxs-lookup"><span data-stu-id="6d79d-140">5</span></span> | <span data-ttu-id="6d79d-141">2</span><span class="sxs-lookup"><span data-stu-id="6d79d-141">2</span></span> | <span data-ttu-id="6d79d-142">2</span><span class="sxs-lookup"><span data-stu-id="6d79d-142">2</span></span> | <span data-ttu-id="6d79d-143">1</span><span class="sxs-lookup"><span data-stu-id="6d79d-143">1</span></span>
 <span data-ttu-id="6d79d-144">5</span><span class="sxs-lookup"><span data-stu-id="6d79d-144">5</span></span> | <span data-ttu-id="6d79d-145">-2</span><span class="sxs-lookup"><span data-stu-id="6d79d-145">-2</span></span> | <span data-ttu-id="6d79d-146">-2</span><span class="sxs-lookup"><span data-stu-id="6d79d-146">-2</span></span> | <span data-ttu-id="6d79d-147">1</span><span class="sxs-lookup"><span data-stu-id="6d79d-147">1</span></span>
 <span data-ttu-id="6d79d-148">-5</span><span class="sxs-lookup"><span data-stu-id="6d79d-148">-5</span></span> | <span data-ttu-id="6d79d-149">2</span><span class="sxs-lookup"><span data-stu-id="6d79d-149">2</span></span> | <span data-ttu-id="6d79d-150">-2</span><span class="sxs-lookup"><span data-stu-id="6d79d-150">-2</span></span> | <span data-ttu-id="6d79d-151">-1</span><span class="sxs-lookup"><span data-stu-id="6d79d-151">-1</span></span>
 <span data-ttu-id="6d79d-152">-5</span><span class="sxs-lookup"><span data-stu-id="6d79d-152">-5</span></span> | <span data-ttu-id="6d79d-153">-2</span><span class="sxs-lookup"><span data-stu-id="6d79d-153">-2</span></span> | <span data-ttu-id="6d79d-154">2</span><span class="sxs-lookup"><span data-stu-id="6d79d-154">2</span></span> | <span data-ttu-id="6d79d-155">-1</span><span class="sxs-lookup"><span data-stu-id="6d79d-155">-1</span></span>

<span data-ttu-id="6d79d-156">La divisione e il modulo di Big Integer funzionano allo stesso modo.</span><span class="sxs-lookup"><span data-stu-id="6d79d-156">Big integer division and modulus works the same way.</span></span>

<span data-ttu-id="6d79d-157">Data un'espressione numerica, una nuova espressione può essere formata utilizzando l'operatore unario `-`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-157">Given any numeric expression, a new expression may be formed using the `-` unary operator.</span></span>
<span data-ttu-id="6d79d-158">La nuova espressione sarà dello stesso tipo dell'espressione costituente.</span><span class="sxs-lookup"><span data-stu-id="6d79d-158">The new expression will be the same type as the constituent expression.</span></span>

<span data-ttu-id="6d79d-159">Dato qualsiasi espressione Integer o Big Integer, è possibile formare una nuova espressione dello stesso tipo utilizzando l'operatore unario `~~~` (complemento bit per bit).</span><span class="sxs-lookup"><span data-stu-id="6d79d-159">Given any integer or big integer expression, a new expression of the same type may be formed using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="6d79d-160">Espressioni booleane</span><span class="sxs-lookup"><span data-stu-id="6d79d-160">Boolean Expressions</span></span>

<span data-ttu-id="6d79d-161">I due `Bool` valori letterali sono `true` e `false`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-161">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="6d79d-162">Date due espressioni dello stesso tipo primitivo, è possibile usare gli operatori binari `==` e `!=` per costruire un'espressione di `Bool`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-162">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="6d79d-163">L'espressione sarà true se le due espressioni sono uguali e false in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="6d79d-163">The expression will be true if the two expressions are equal, and false if not.</span></span>

<span data-ttu-id="6d79d-164">I valori dei tipi definiti dall'utente non possono essere confrontati, ma è possibile confrontare solo i valori di cui non è stato eseguito il wrapper.</span><span class="sxs-lookup"><span data-stu-id="6d79d-164">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="6d79d-165">Ad esempio, usando l'operatore "Unwrap" `!` (illustrato nella [pagina del modello Q # type](xref:microsoft.quantum.language.type-model#user-defined-types)),</span><span class="sxs-lookup"><span data-stu-id="6d79d-165">For example, using the "unwrap" operator `!` (explained in the [Q# type model page](xref:microsoft.quantum.language.type-model#user-defined-types)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="6d79d-166">Il confronto di uguaglianza per i valori `Qubit` è uguaglianza di identità; ovvero se le due espressioni identificano lo stesso qubit.</span><span class="sxs-lookup"><span data-stu-id="6d79d-166">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="6d79d-167">Lo stato dei due qubits non viene confrontato, accessibile, misurato o modificato da questo confronto.</span><span class="sxs-lookup"><span data-stu-id="6d79d-167">The state of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="6d79d-168">Il confronto di uguaglianza per i valori `Double` può essere fuorviante a causa degli effetti dell'arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="6d79d-168">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="6d79d-169">Ad esempio, `49.0 * (1.0/49.0) != 1.0`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-169">For instance, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="6d79d-170">Date due espressioni numeriche, è possibile usare gli operatori binari `>`, `<`, `>=`e `<=` per costruire una nuova espressione booleana che è true se la prima espressione è rispettivamente maggiore di, minore di, maggiore o uguale a o minore o uguale alla seconda espressione.</span><span class="sxs-lookup"><span data-stu-id="6d79d-170">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="6d79d-171">Date due espressioni booleane, è possibile usare gli operatori binari `and` e `or` per costruire una nuova espressione booleana che è true se entrambe le espressioni (risp. both o Both) sono true.</span><span class="sxs-lookup"><span data-stu-id="6d79d-171">Given any two Boolean expressions, the `and` and `or` binary operators may be used to construct a new Boolean expression that is true if both of (resp. either or both of) the two expressions are true.</span></span>

<span data-ttu-id="6d79d-172">Dato qualsiasi espressione booleana, è possibile usare l'operatore unario `not` per costruire una nuova espressione booleana che è true se l'espressione costituente è false.</span><span class="sxs-lookup"><span data-stu-id="6d79d-172">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="6d79d-173">Espressioni stringa</span><span class="sxs-lookup"><span data-stu-id="6d79d-173">String Expressions</span></span>

<span data-ttu-id="6d79d-174">Q # consente l'uso di stringhe nell'istruzione `fail` e nella funzione `Log` standard.</span><span class="sxs-lookup"><span data-stu-id="6d79d-174">Q# allows strings to be used in the `fail` statement and the `Log` standard function.</span></span>

<span data-ttu-id="6d79d-175">Le stringhe in Q # sono valori letterali o stringhe interpolate.</span><span class="sxs-lookup"><span data-stu-id="6d79d-175">Strings in Q# are either literals or interpolated strings.</span></span>
<span data-ttu-id="6d79d-176">I valori letterali stringa sono simili a valori letterali stringa semplici nella maggior parte dei linguaggi: una sequenza di caratteri Unicode racchiusi tra virgolette doppie, `"`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-176">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double quotes, `"`.</span></span>
<span data-ttu-id="6d79d-177">All'interno di una stringa, è possibile usare il carattere di barra rovesciata `\` per eseguire l'escape di un carattere virgolette doppie e inserire una nuova riga come `\n`, un ritorno a capo come `\r`e una scheda come `\t`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-177">Inside of a string, the back-slash character `\` may be used to escape a double quote character, and to insert a new-line as `\n`, a carriage return as `\r`, and a tab as `\t`.</span></span>
<span data-ttu-id="6d79d-178">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6d79d-178">For instance:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```

<span data-ttu-id="6d79d-179">La sintassi Q # per l' C# interpolazione di stringhe è un subset della sintassi 7,0; Q # non supporta le stringhe interpolate Verbatim (a più righe).</span><span class="sxs-lookup"><span data-stu-id="6d79d-179">The Q# syntax for string interpolations is a subset of the C# 7.0 syntax; Q# does not support verbatim (multi-line) interpolated strings.</span></span>
<span data-ttu-id="6d79d-180">Per la C# sintassi, vedere [*stringhe interpolate*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) .</span><span class="sxs-lookup"><span data-stu-id="6d79d-180">See [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) for the C# syntax.</span></span>

<span data-ttu-id="6d79d-181">Le espressioni all'interno di una stringa interpolata seguono la sintassi C# Q #, non la sintassi.</span><span class="sxs-lookup"><span data-stu-id="6d79d-181">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span>
<span data-ttu-id="6d79d-182">In una stringa interpolata può essere presente qualsiasi espressione Q # valida.</span><span class="sxs-lookup"><span data-stu-id="6d79d-182">Any valid Q# expression may appear in an interpolated string.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="6d79d-183">Espressioni qubit</span><span class="sxs-lookup"><span data-stu-id="6d79d-183">Qubit Expressions</span></span>

<span data-ttu-id="6d79d-184">Le uniche espressioni `Qubit` sono simboli associati a valori `Qubit` o elementi di matrice di `Qubit` matrici.</span><span class="sxs-lookup"><span data-stu-id="6d79d-184">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="6d79d-185">Nessun valore letterale `Qubit`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-185">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="6d79d-186">Espressioni di Pauli</span><span class="sxs-lookup"><span data-stu-id="6d79d-186">Pauli Expressions</span></span>

<span data-ttu-id="6d79d-187">I quattro valori `Pauli`, `PauliI`, `PauliX`, `PauliY`e `PauliZ`sono tutte espressioni di `Pauli` valide.</span><span class="sxs-lookup"><span data-stu-id="6d79d-187">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="6d79d-188">A parte questo, le uniche espressioni `Pauli` sono simboli associati a valori `Pauli` o elementi di matrice di `Pauli` matrici.</span><span class="sxs-lookup"><span data-stu-id="6d79d-188">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="6d79d-189">Espressioni risultato</span><span class="sxs-lookup"><span data-stu-id="6d79d-189">Result Expressions</span></span>

<span data-ttu-id="6d79d-190">I due valori `Result`, `One` e `Zero`, sono espressioni `Result` valide.</span><span class="sxs-lookup"><span data-stu-id="6d79d-190">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="6d79d-191">A parte questo, le uniche espressioni `Result` sono simboli associati a valori `Result` o elementi di matrice di `Result` matrici.</span><span class="sxs-lookup"><span data-stu-id="6d79d-191">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="6d79d-192">In particolare, si noti che `One` non corrisponde al `1`Integer e non esiste alcuna conversione diretta tra di essi.</span><span class="sxs-lookup"><span data-stu-id="6d79d-192">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="6d79d-193">Lo stesso vale per `Zero` e `0`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-193">The same is true for `Zero` and `0`.</span></span>

## <a name="range-expressions"></a><span data-ttu-id="6d79d-194">Espressioni di intervallo</span><span class="sxs-lookup"><span data-stu-id="6d79d-194">Range Expressions</span></span>

<span data-ttu-id="6d79d-195">Date le tre espressioni `Int` `start`, `step`e `stop``start .. step .. stop` è un'espressione di intervallo il cui primo elemento è `start`, il secondo elemento è `start+step`, il terzo elemento è `start+step+step`e così via, fino a quando non viene passato `stop`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-195">Given any three `Int` expressions `start`, `step`, and `stop`, `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, etc., until `stop` is passed.</span></span>
<span data-ttu-id="6d79d-196">Un intervallo può essere vuoto se, ad esempio, `step` è positivo e `stop < start`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-196">A range may be empty if, for instance, `step` is positive and `stop < start`.</span></span>
<span data-ttu-id="6d79d-197">L'ultimo elemento dell'intervallo verrà `stop` se la differenza tra `start` e `stop` è un multiplo integrale di `step`; ovvero, l'intervallo è incluso a entrambe le estremità.</span><span class="sxs-lookup"><span data-stu-id="6d79d-197">The last element of the range will be `stop` if the difference between `start` and `stop` is an integral multiple of `step`; that is, the range is inclusive at both ends.</span></span>

<span data-ttu-id="6d79d-198">Date due espressioni `Int` `start` e `stop`, `start .. stop` è un'espressione di intervallo uguale a `start .. 1 .. stop`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-198">Given any two `Int` expressions `start` and `stop`, `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="6d79d-199">Si noti che il `step` implicito è + 1 anche se `stop` è minore di `start`; in tal caso, l'intervallo è vuoto.</span><span class="sxs-lookup"><span data-stu-id="6d79d-199">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="6d79d-200">Alcuni intervalli di esempio sono:</span><span class="sxs-lookup"><span data-stu-id="6d79d-200">Some example ranges are:</span></span>

- <span data-ttu-id="6d79d-201">`1..3` è l'intervallo 1, 2, 3.</span><span class="sxs-lookup"><span data-stu-id="6d79d-201">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="6d79d-202">`2..2..5` è l'intervallo 2, 4.</span><span class="sxs-lookup"><span data-stu-id="6d79d-202">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="6d79d-203">`2..2..6` è l'intervallo 2, 4, 6.</span><span class="sxs-lookup"><span data-stu-id="6d79d-203">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="6d79d-204">`6..-2..2` è l'intervallo 6, 4, 2.</span><span class="sxs-lookup"><span data-stu-id="6d79d-204">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="6d79d-205">`2..1` è l'intervallo vuoto.</span><span class="sxs-lookup"><span data-stu-id="6d79d-205">`2..1` is the empty range.</span></span>
- <span data-ttu-id="6d79d-206">`2..6..7` è l'intervallo 2.</span><span class="sxs-lookup"><span data-stu-id="6d79d-206">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="6d79d-207">`2..2..1` è l'intervallo vuoto.</span><span class="sxs-lookup"><span data-stu-id="6d79d-207">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="6d79d-208">`1..-1..2` è l'intervallo vuoto.</span><span class="sxs-lookup"><span data-stu-id="6d79d-208">`1..-1..2` is the empty range.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="6d79d-209">Espressioni richiamabili</span><span class="sxs-lookup"><span data-stu-id="6d79d-209">Callable Expressions</span></span>

<span data-ttu-id="6d79d-210">Un valore letterale chiamabile è il nome di un'operazione o di una funzione definita nell'ambito di compilazione.</span><span class="sxs-lookup"><span data-stu-id="6d79d-210">A callable literal is the name of an operation or function defined in the compilation scope.</span></span>
<span data-ttu-id="6d79d-211">Ad esempio, `X` è un valore letterale dell'operazione che fa riferimento all'operazione di `X` della libreria standard e `Message` è un valore letterale di funzione che fa riferimento alla funzione di `Message` della libreria standard.</span><span class="sxs-lookup"><span data-stu-id="6d79d-211">For instance, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="6d79d-212">Se un'operazione supporta il `Adjoint` functor, `Adjoint op` è un'espressione dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="6d79d-212">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="6d79d-213">Analogamente, se l'operazione supporta il `Controlled` functor, `Controlled op` è un'espressione Operation.</span><span class="sxs-lookup"><span data-stu-id="6d79d-213">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="6d79d-214">I tipi di queste espressioni sono specificati in [funtori](xref:microsoft.quantum.language.type-model#functors).</span><span class="sxs-lookup"><span data-stu-id="6d79d-214">The types of these expressions are specified in [Functors](xref:microsoft.quantum.language.type-model#functors).</span></span>

<span data-ttu-id="6d79d-215">Funtori (`Adjoint` e `Controlled`) si associano in modo più accurato a tutti gli altri operatori, ad eccezione dell'operatore Unwrap `!` e dell'indicizzazione della matrice con `[]`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-215">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with `[]`.</span></span>
<span data-ttu-id="6d79d-216">Pertanto, di seguito sono riportate tutte le informazioni legali, supponendo che le operazioni supportino i funtori utilizzati:</span><span class="sxs-lookup"><span data-stu-id="6d79d-216">Thus, the following are all legal, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

<span data-ttu-id="6d79d-217">Un valore letterale chiamabile può essere usato come valore, ad esempio per assegnare a una variabile o per passare a un altro oggetto chiamabile.</span><span class="sxs-lookup"><span data-stu-id="6d79d-217">A callable literal may be used as a value, say to assign to a variable or to pass to another callable.</span></span>
<span data-ttu-id="6d79d-218">In questo caso, se l'oggetto chiamabile dispone di parametri di tipo, questi devono essere forniti come parte del valore chiamabile.</span><span class="sxs-lookup"><span data-stu-id="6d79d-218">In this case, if the callable has type parameters, they must be provided as part of the callable value.</span></span>
<span data-ttu-id="6d79d-219">Un valore chiamabile non può avere parametri di tipo non specificati.</span><span class="sxs-lookup"><span data-stu-id="6d79d-219">A callable value cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="6d79d-220">Ad esempio, se `Fun` è una funzione con `'T1->Unit`di firma:</span><span class="sxs-lookup"><span data-stu-id="6d79d-220">For instance, if `Fun` is a function with signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is Int->Unit.
SomeOtherFun(Fun<Double>);   // A Double->Unit is passed to SomOtherFun.
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="6d79d-221">Espressioni di chiamata chiamabili</span><span class="sxs-lookup"><span data-stu-id="6d79d-221">Callable Invocation Expressions</span></span>

<span data-ttu-id="6d79d-222">Data un'espressione chiamabile (operazione o funzione) e un'espressione di tupla del tipo di input della firma richiamabile, un'espressione di chiamata può essere formata aggiungendo l'espressione di tupla all'espressione chiamabile.</span><span class="sxs-lookup"><span data-stu-id="6d79d-222">Given a callable (operation or function) expression and a tuple expression of the input type of the callable's signature, an invocation expression may be formed by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="6d79d-223">Il tipo dell'espressione di chiamata è il tipo di output della firma richiamabile.</span><span class="sxs-lookup"><span data-stu-id="6d79d-223">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="6d79d-224">Se ad esempio `Op` è un'operazione con `((Int, Qubit) => Double)`di firma, `Op(3, qubit1)` è un'espressione di tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-224">For example, if `Op` is an operation with signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="6d79d-225">Analogamente, se `Sin` è una funzione con `(Double -> Double)`di firma, `Sin(0.1)` è un'espressione di tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-225">Similarly, if `Sin` is a function with signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="6d79d-226">Infine, se `Builder` è una funzione con `(Int -> (Int -> Int))`di firma, `Builder(3)` è una funzione da a int.</span><span class="sxs-lookup"><span data-stu-id="6d79d-226">Finally, if `Builder` is a function with signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from Into to Int.</span></span>

<span data-ttu-id="6d79d-227">Per richiamare il risultato di un'espressione con valori richiamabili è necessaria una coppia aggiuntiva di parentesi intorno all'espressione chiamabile.</span><span class="sxs-lookup"><span data-stu-id="6d79d-227">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="6d79d-228">Pertanto, per richiamare il risultato della chiamata di `Builder` dal paragrafo precedente, la sintassi corretta è la seguente:</span><span class="sxs-lookup"><span data-stu-id="6d79d-228">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="6d79d-229">Quando si richiama un oggetto chiamabile con parametri di tipo, i parametri di tipo effettivi possono essere specificati tra parentesi angolari `<` e `>` dopo l'espressione chiamabile.</span><span class="sxs-lookup"><span data-stu-id="6d79d-229">When invoking a type-parameterized callable, the actual type parameters may be specified within angle brackets `<` and `>` after the callable expression.</span></span>
<span data-ttu-id="6d79d-230">Questa operazione non è in genere necessaria perché il compilatore Q # dedurrà i tipi effettivi.</span><span class="sxs-lookup"><span data-stu-id="6d79d-230">This is usually unnecessary as the Q# compiler will infer the actual types.</span></span>
<span data-ttu-id="6d79d-231">È necessario per l'applicazione parziale (vedere di seguito) se non è specificato un argomento con parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="6d79d-231">It is required for partial application (see below) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="6d79d-232">A volte può essere utile anche quando si passano operazioni con diversi supporti functor a un oggetto chiamabile.</span><span class="sxs-lookup"><span data-stu-id="6d79d-232">It is also sometimes useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="6d79d-233">Ad esempio, se `Func` ha `('T1, 'T2, 'T1) -> 'T2`di firma, `Op1` e `Op2` hanno la firma `(Qubit[] => Unit is Adj)`e `Op3` ha la firma `(Qubit[] => Unit)`, per richiamare `Func` con `Op1` come primo argomento, `Op2` come secondo e `Op3` come terzo:</span><span class="sxs-lookup"><span data-stu-id="6d79d-233">For instance, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="6d79d-234">La specifica del tipo è necessaria perché `Op3` e `Op1` hanno tipi diversi, pertanto il compilatore lo considererà ambiguo senza la specifica.</span><span class="sxs-lookup"><span data-stu-id="6d79d-234">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>

### <a name="partial-application"></a><span data-ttu-id="6d79d-235">Applicazione parziale</span><span class="sxs-lookup"><span data-stu-id="6d79d-235">Partial Application</span></span>

<span data-ttu-id="6d79d-236">Data un'espressione chiamabile, è possibile creare un nuovo oggetto chiamabile fornendo un subset degli argomenti all'oggetto chiamabile.</span><span class="sxs-lookup"><span data-stu-id="6d79d-236">Given a callable expression, a new callable may be created by providing a subset of the arguments to the callable.</span></span>
<span data-ttu-id="6d79d-237">Questa operazione è denominata _applicazione parziale_.</span><span class="sxs-lookup"><span data-stu-id="6d79d-237">This is called _partial application_.</span></span>

<span data-ttu-id="6d79d-238">In Q # un oggetto chiamabile parzialmente applicato viene espresso scrivendo un'espressione di chiamata normale, ma usando un carattere di sottolineatura `_`per gli argomenti non specificati.</span><span class="sxs-lookup"><span data-stu-id="6d79d-238">In Q#, a partially applied callable is expressed by writing a normal invocation expression, but using an underscore, `_`, for the unspecified arguments.</span></span>
<span data-ttu-id="6d79d-239">Il richiamabile risultante ha lo stesso tipo di risultato di base Callable e le stesse specializzazioni per le operazioni.</span><span class="sxs-lookup"><span data-stu-id="6d79d-239">The resulting callable has the same result type as the base callable, and the same specializations for operations.</span></span>
<span data-ttu-id="6d79d-240">Il tipo di input dell'applicazione parziale è semplicemente il tipo originale con gli argomenti specificati rimossi.</span><span class="sxs-lookup"><span data-stu-id="6d79d-240">The input type of the partial application is simply the original type with the specified arguments removed.</span></span>

<span data-ttu-id="6d79d-241">Se una variabile modificabile viene passata come argomento specificato durante la creazione di un'applicazione parziale, viene usato il valore corrente della variabile.</span><span class="sxs-lookup"><span data-stu-id="6d79d-241">If a mutable variable is passed as a specified argument when creating a partial application, the current value of the variable is used.</span></span>
<span data-ttu-id="6d79d-242">Se successivamente si modifica il valore della variabile, l'applicazione parziale non avrà alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="6d79d-242">Changing the value of the variable afterward will not impact the partial application.</span></span>

<span data-ttu-id="6d79d-243">Ad esempio, se `Op` dispone di tipo `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`:</span><span class="sxs-lookup"><span data-stu-id="6d79d-243">For example, if `Op` has type `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`:</span></span>

- <span data-ttu-id="6d79d-244">`Op(5,(_,_))` è di tipo `(((Qubit,Qubit), Double) => Unit is Adj)`e pertanto ha `Op(5,_)`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-244">`Op(5,(_,_))` has type `(((Qubit,Qubit), Double) => Unit is Adj)`, and so has `Op(5,_)`.</span></span>
- <span data-ttu-id="6d79d-245">il tipo di `Op(_,(_,1.0))` è `((Int, (Qubit,Qubit)) => Unit is Adj)`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-245">`Op(_,(_,1.0))` has type `((Int, (Qubit,Qubit)) => Unit is Adj)`.</span></span>
- <span data-ttu-id="6d79d-246">il tipo di `Op(_,((q1,q2),_))` è `((Int,Double) => Unit is Adj)`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-246">`Op(_,((q1,q2),_))` has type `((Int,Double) => Unit is Adj)`.</span></span>
   <span data-ttu-id="6d79d-247">Si noti che qui è stata applicata l'equivalenza della tupla singleton.</span><span class="sxs-lookup"><span data-stu-id="6d79d-247">Note that we have applied singleton tuple equivalence here.</span></span>

<span data-ttu-id="6d79d-248">Se il richiamabile parzialmente applicato dispone di parametri di tipo che non possono essere dedotti dal compilatore, è necessario che siano specificati nel sito di chiamata.</span><span class="sxs-lookup"><span data-stu-id="6d79d-248">If the partially-applied callable has type parameters that cannot be inferred by the compiler, they must be provided at the invocation site.</span></span>
<span data-ttu-id="6d79d-249">L'applicazione parziale non può avere parametri di tipo non specificati.</span><span class="sxs-lookup"><span data-stu-id="6d79d-249">The partial application cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="6d79d-250">Ad esempio, se `Op` dispone di tipo `(('T1, Qubit, 'T1) => Unit : Adjoint)`:</span><span class="sxs-lookup"><span data-stu-id="6d79d-250">For example, if `Op` has type `(('T1, Qubit, 'T1) => Unit : Adjoint)`:</span></span>

```qsharp
let f1 = Op<Int>(_, qb, _); // f1 has type ((Int,Int) => Unit is Adj)
let f2 = Op(5, qb, _);      // f2 has type (Int => Unit is Adj)
let f3 = Op(_,qb, _);       // f3 generates a compilation error
```

### <a name="recursion"></a><span data-ttu-id="6d79d-251">Ricorsione</span><span class="sxs-lookup"><span data-stu-id="6d79d-251">Recursion</span></span>

<span data-ttu-id="6d79d-252">D # i chiamabili possono essere ricorsivi direttamente o indirettamente.</span><span class="sxs-lookup"><span data-stu-id="6d79d-252">Q# callables are allowed to be directly or indirectly recursive.</span></span>
<span data-ttu-id="6d79d-253">Ovvero, un'operazione o una funzione può chiamare se stessa oppure può chiamare un altro oggetto chiamabile che chiama direttamente o indirettamente l'operazione chiamabile.</span><span class="sxs-lookup"><span data-stu-id="6d79d-253">That is, an operation or function may call itself, or it may call another callable that directly or indirectly calls the callable operation.</span></span>

<span data-ttu-id="6d79d-254">Sono tuttavia disponibili due commenti importanti sull'utilizzo della ricorsione:</span><span class="sxs-lookup"><span data-stu-id="6d79d-254">There are two important comments about the use of recursion, however:</span></span>

- <span data-ttu-id="6d79d-255">L'uso della ricorsione nelle operazioni potrebbe interferire con determinate ottimizzazioni.</span><span class="sxs-lookup"><span data-stu-id="6d79d-255">The use of recursion in operations is likely to interfere with certain optimizations.</span></span>
  <span data-ttu-id="6d79d-256">Questo può avere un notevole effetto sul tempo di esecuzione dell'algoritmo.</span><span class="sxs-lookup"><span data-stu-id="6d79d-256">This may have a substantial impact on the execution time of the algorithm.</span></span>
- <span data-ttu-id="6d79d-257">Quando si esegue su un dispositivo Quantum effettivo, lo spazio dello stack può essere limitato e pertanto la ricorsione profonda può causare un errore di Runtime.</span><span class="sxs-lookup"><span data-stu-id="6d79d-257">When executing on an actual quantum device, stack space may be limited, and so deep recursion may lead to a runtime error.</span></span>
  <span data-ttu-id="6d79d-258">In particolare, il compilatore e il runtime Q # non identificano e ottimizzano la ricorsione Tail.</span><span class="sxs-lookup"><span data-stu-id="6d79d-258">In particular, the Q# compiler and runtime do not identify and optimize tail recursion.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="6d79d-259">Espressioni di tupla</span><span class="sxs-lookup"><span data-stu-id="6d79d-259">Tuple Expressions</span></span>

<span data-ttu-id="6d79d-260">Un valore letterale di tupla è una sequenza di espressioni di elemento del tipo appropriato, separate da virgole, racchiuse tra `(` e `)`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-260">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in `(` and `)`.</span></span>
<span data-ttu-id="6d79d-261">Ad esempio, `(1, One)` è un'espressione `(Int, Result)`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-261">For instance, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="6d79d-262">Ad eccezione dei valori letterali, le uniche espressioni di tupla sono simboli associati a valori di tupla, elementi di matrice di matrici di tuple e chiamate chiamabili che restituiscono Tuple.</span><span class="sxs-lookup"><span data-stu-id="6d79d-262">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="6d79d-263">Espressioni di tipo definito dall'utente</span><span class="sxs-lookup"><span data-stu-id="6d79d-263">User-Defined Type Expressions</span></span>

<span data-ttu-id="6d79d-264">Un valore letterale di un tipo definito dall'utente è costituito dal nome del tipo seguito da un valore letterale di tupla del tipo di tupla di base del tipo.</span><span class="sxs-lookup"><span data-stu-id="6d79d-264">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="6d79d-265">Se ad esempio `IntPair` è un tipo definito dall'utente basato su `(Int, Int)`, `IntPair(2,3)` sarebbe un valore letterale valido di quel tipo.</span><span class="sxs-lookup"><span data-stu-id="6d79d-265">For instance, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2,3)` would be a valid literal of that type.</span></span>

<span data-ttu-id="6d79d-266">Ad eccezione dei valori letterali, le uniche espressioni di un tipo definito dall'utente sono i simboli associati a valori di quel tipo, gli elementi di matrice delle matrici di quel tipo e le chiamate richiamabili che restituiscono quel tipo.</span><span class="sxs-lookup"><span data-stu-id="6d79d-266">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="6d79d-267">Espressioni Unwrap</span><span class="sxs-lookup"><span data-stu-id="6d79d-267">Unwrap Expressions</span></span>

<span data-ttu-id="6d79d-268">In Q # l'operatore Unwrap è un punto esclamativo finale `!`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-268">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="6d79d-269">Se, ad esempio, `IntPair` è un tipo definito dall'utente con tipo sottostante `(Int, Int)`e `s` è una variabile con valore `IntPair(2,3)`, `s!` verrebbe `(2,3)`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-269">For instance, if `IntPair` is a user-defined type with underlying type `(Int, Int)`, and `s` was a variable with value `IntPair(2,3)`, then `s!` would be `(2,3)`.</span></span>

<span data-ttu-id="6d79d-270">Per i tipi definiti dall'utente definiti in termini di altri tipi definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="6d79d-270">For user-defined types defined in terms of other user-defined types.</span></span> <span data-ttu-id="6d79d-271">l'operatore Unwrap può essere ripetuto; ad esempio, `s!!` indica il valore con doppia incapsulamento di `s`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-271">the unwrap operator may be repeated; for instance, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="6d79d-272">Pertanto, se `WrappedPair` è un tipo definito dall'utente con il tipo sottostante `IntPair`e `t` è una variabile con valore `WrappedPair(IntPair(1,2))`, `t!!` verrebbe `(1,2)`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-272">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` would be `(1,2)`.</span></span>

<span data-ttu-id="6d79d-273">L'operatore `!` ha precedenza maggiore rispetto a tutti gli altri operatori diversi da `[]` per l'indicizzazione e il sezionamento di matrici.</span><span class="sxs-lookup"><span data-stu-id="6d79d-273">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="6d79d-274">`!` e `[]` eseguire l'associazione posizionale; Ciò significa che `a[i]![3]` deve essere letto come `((a[i])!)[3]`: prendere il `i`"esimo elemento di `a`, annullare il wrapping e quindi ottenere il terzo elemento del valore di cui non è stato eseguito il wrapping (che deve essere una matrice).</span><span class="sxs-lookup"><span data-stu-id="6d79d-274">`!` and `[]` bind positionally; that is, `a[i]![3]` should be read as `((a[i])!)[3]`: take the `i`'th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="6d79d-275">La precedenza dell'operatore `!` ha un effetto che potrebbe non essere ovvio.</span><span class="sxs-lookup"><span data-stu-id="6d79d-275">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="6d79d-276">Se una funzione o un'operazione restituisce un valore che viene quindi sottoposto a wrapping, la funzione o la chiamata dell'operazione deve essere racchiusa tra parentesi in modo che la tupla dell'argomento venga associata alla chiamata anziché all'annullamento del wrapping.</span><span class="sxs-lookup"><span data-stu-id="6d79d-276">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="6d79d-277">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6d79d-277">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="6d79d-278">Espressioni di matrice</span><span class="sxs-lookup"><span data-stu-id="6d79d-278">Array Expressions</span></span>

<span data-ttu-id="6d79d-279">Un valore letterale di matrice è una sequenza di una o più espressioni di elemento, separate da virgole, racchiuse tra `[` e `]`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-279">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in `[` and `]`.</span></span>
<span data-ttu-id="6d79d-280">Tutti gli elementi devono essere compatibili con lo stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="6d79d-280">All elements must be compatible with the same type.</span></span>

<span data-ttu-id="6d79d-281">Se il tipo di elemento comune è un'operazione o un tipo di funzione, tutti gli elementi devono avere gli stessi tipi di input e di output.</span><span class="sxs-lookup"><span data-stu-id="6d79d-281">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
<span data-ttu-id="6d79d-282">Il tipo di elemento della matrice supporterà qualsiasi funtori supportato da tutti gli elementi.</span><span class="sxs-lookup"><span data-stu-id="6d79d-282">The element type of the array will support any functors that are supported by all of the elements.</span></span>
<span data-ttu-id="6d79d-283">Ad esempio, se `Op1`, `Op2`e `Op3` sono tutti `Qubit[] => Unit`, ma `Op1` supporta `Adjoint`, `Op2` supporta `Controlled`e `Op3` supporta entrambi:</span><span class="sxs-lookup"><span data-stu-id="6d79d-283">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="6d79d-284">`[Op1, Op2]` è una matrice di operazioni `(Qubit[] => Unit)`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-284">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
- <span data-ttu-id="6d79d-285">`[Op1, Op3]` è una matrice di operazioni `(Qubit[] => Unit is Adj)`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-285">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
- <span data-ttu-id="6d79d-286">`[Op2, Op3]` è una matrice di operazioni `(Qubit[] => Unit is Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-286">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="6d79d-287">I valori letterali di matrice vuoti, `[]`, non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="6d79d-287">Empty array literals, `[]`, are not allowed.</span></span>
<span data-ttu-id="6d79d-288">Utilizzando invece `new ★[0]`, dove `★` è come segnaposto per un tipo adatto, consente a di creare la matrice desiderata di lunghezza zero.</span><span class="sxs-lookup"><span data-stu-id="6d79d-288">Instead using `new ★[0]`, where `★` is as placeholder for a suitable type, allows to create the desired array of length zero.</span></span>

<span data-ttu-id="6d79d-289">Date due matrici dello stesso tipo, è possibile usare l'operatore Binary `+` per formare una nuova matrice che rappresenta la concatenazione delle due matrici.</span><span class="sxs-lookup"><span data-stu-id="6d79d-289">Given two arrays of the same type, the binary `+` operator may be used to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="6d79d-290">Ad esempio, `[1,2,3] + [4,5,6]` è `[1,2,3,4,5,6]`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-290">For instance, `[1,2,3] + [4,5,6]` is `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="6d79d-291">Creazione di matrici</span><span class="sxs-lookup"><span data-stu-id="6d79d-291">Array Creation</span></span>

<span data-ttu-id="6d79d-292">Dato un tipo e un'espressione `Int`, l'operatore `new` può essere usato per allocare una nuova matrice della dimensione specificata.</span><span class="sxs-lookup"><span data-stu-id="6d79d-292">Given a type and an `Int` expression, the `new` operator may be used to allocate a new array of the given size.</span></span>
<span data-ttu-id="6d79d-293">Ad esempio, `new Int[i+1]` alloca una nuova matrice di `Int` con `i+1` elementi.</span><span class="sxs-lookup"><span data-stu-id="6d79d-293">For instance, `new Int[i+1]` would allocate a new `Int` array with `i+1` elements.</span></span>

<span data-ttu-id="6d79d-294">Gli elementi di una nuova matrice vengono inizializzati su un valore predefinito dipendente dal tipo.</span><span class="sxs-lookup"><span data-stu-id="6d79d-294">The elements of a new array are initialized to a type-dependent default value.</span></span>
<span data-ttu-id="6d79d-295">Nella maggior parte dei casi si tratta di una variante di zero.</span><span class="sxs-lookup"><span data-stu-id="6d79d-295">In most cases this is some variation of zero.</span></span>

<span data-ttu-id="6d79d-296">Per qubits e callable, che sono riferimenti a entità, non esiste un valore predefinito ragionevole.</span><span class="sxs-lookup"><span data-stu-id="6d79d-296">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="6d79d-297">Pertanto, per questi tipi, il valore predefinito è un riferimento non valido che non può essere utilizzato senza causare un errore di Runtime.</span><span class="sxs-lookup"><span data-stu-id="6d79d-297">Thus, for these types, the default is an invalid reference that cannot be used without causing a runtime error.</span></span>
<span data-ttu-id="6d79d-298">Questa operazione è simile a un riferimento null in linguaggi come C# o Java.</span><span class="sxs-lookup"><span data-stu-id="6d79d-298">This is similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="6d79d-299">Le matrici contenenti qubits o Callable devono essere inizializzate correttamente con valori non predefiniti prima che i relativi elementi possano essere usati in modo sicuro.</span><span class="sxs-lookup"><span data-stu-id="6d79d-299">Arrays containing qubits or callables must be properly initialized with non-default values before their elements may be safely used.</span></span> <span data-ttu-id="6d79d-300">È possibile trovare routine di inizializzazione appropriate in <xref:microsoft.quantum.arrays>.</span><span class="sxs-lookup"><span data-stu-id="6d79d-300">Suitable initialization routines can be found in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="6d79d-301">I valori predefiniti per ogni tipo sono:</span><span class="sxs-lookup"><span data-stu-id="6d79d-301">The default values for each type are:</span></span>

<span data-ttu-id="6d79d-302">Type</span><span class="sxs-lookup"><span data-stu-id="6d79d-302">Type</span></span> | <span data-ttu-id="6d79d-303">Predefinito</span><span class="sxs-lookup"><span data-stu-id="6d79d-303">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="6d79d-304">_Qubit non valido_</span><span class="sxs-lookup"><span data-stu-id="6d79d-304">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="6d79d-305">Intervallo vuoto, `1..1..0`</span><span class="sxs-lookup"><span data-stu-id="6d79d-305">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="6d79d-306">_chiamabile non valido_</span><span class="sxs-lookup"><span data-stu-id="6d79d-306">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="6d79d-307">I tipi di tupla sono elemento per elemento inizializzato.</span><span class="sxs-lookup"><span data-stu-id="6d79d-307">Tuple types are initialized element-by-element.</span></span>


### <a name="jagged-arrays"></a><span data-ttu-id="6d79d-308">Matrici irregolari</span><span class="sxs-lookup"><span data-stu-id="6d79d-308">Jagged Arrays</span></span>

<span data-ttu-id="6d79d-309">Una matrice di matrici, talvolta denominata "matrice di matrici", è una matrice i cui elementi sono matrici.</span><span class="sxs-lookup"><span data-stu-id="6d79d-309">A jagged array, sometimes called an "array of arrays", is an array whose elements are arrays.</span></span> <span data-ttu-id="6d79d-310">Gli elementi di una matrice irregolare possono avere dimensioni diverse.</span><span class="sxs-lookup"><span data-stu-id="6d79d-310">The elements of a jagged array can be of different sizes.</span></span> <span data-ttu-id="6d79d-311">Nell'esempio seguente viene illustrato come dichiarare e inizializzare una matrice di matrici che rappresenta una tabella di moltiplicazione.</span><span class="sxs-lookup"><span data-stu-id="6d79d-311">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

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


### <a name="array-slices"></a><span data-ttu-id="6d79d-312">Sezioni di matrici</span><span class="sxs-lookup"><span data-stu-id="6d79d-312">Array Slices</span></span>

<span data-ttu-id="6d79d-313">Data un'espressione di matrice e un'espressione `Range`, è possibile che venga creata una nuova espressione utilizzando l'operatore di sezionamento di `[` e `]`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-313">Given an array expression and a `Range` expression, a new expression may be formed using the `[` and `]` array slice operator.</span></span>
<span data-ttu-id="6d79d-314">La nuova espressione sarà dello stesso tipo della matrice e conterrà gli elementi della matrice indicizzati dagli elementi del `Range`, nell'ordine definito dall'`Range`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-314">The new expression will be the same type as the array and will contain the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="6d79d-315">Se, ad esempio, `a` è associato a una matrice di `Double`s, `a[3..-1..0]` è un'espressione `Double[]` che contiene i primi quattro elementi di `a` ma nell'ordine inverso come appaiono in `a`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-315">For instance, if `a` is bound to an array of `Double`s, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="6d79d-316">Se la `Range` è vuota, la sezione della matrice risultante avrà una lunghezza pari a zero.</span><span class="sxs-lookup"><span data-stu-id="6d79d-316">If the `Range` is empty, then the resulting array slice will be zero length.</span></span>

<span data-ttu-id="6d79d-317">Se l'espressione di matrice non è un identificatore semplice, deve essere racchiusa tra parentesi per eseguire il sezionamento.</span><span class="sxs-lookup"><span data-stu-id="6d79d-317">If the array expression is not a simple identifier, it must be enclosed it parentheses in order to slice.</span></span>
<span data-ttu-id="6d79d-318">Ad esempio, se `a` e `b` sono entrambe matrici di `Int`s, una sezione della concatenazione verrebbe espressa come:</span><span class="sxs-lookup"><span data-stu-id="6d79d-318">For instance, if `a` and `b` are both arrays of `Int`s, a slice from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

<span data-ttu-id="6d79d-319">Tutte le matrici in Q # sono in base zero.</span><span class="sxs-lookup"><span data-stu-id="6d79d-319">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="6d79d-320">Ovvero il primo elemento di una matrice `a` è sempre `a[0]`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-320">That is, the first element of an array `a` is always `a[0]`.</span></span>

<span data-ttu-id="6d79d-321">A partire dalla versione 0,8, sono supportate le espressioni contestuali per il sezionamento dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="6d79d-321">Starting with our 0.8 release, we support contextual expressions for range slicing.</span></span> <span data-ttu-id="6d79d-322">In particolare, i valori iniziale e finale dell'intervallo possono essere omessi nel contesto di un'espressione di sezionamento dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="6d79d-322">In particular, range start and end values may be omitted in the context of a range slicing expression.</span></span> <span data-ttu-id="6d79d-323">In tal caso, il compilatore applicherà le regole seguenti per dedurre i delimitatori previsti per l'intervallo.</span><span class="sxs-lookup"><span data-stu-id="6d79d-323">In that case, the compiler will apply the following rules to infer the intended delimiters for the range.</span></span> 

<span data-ttu-id="6d79d-324">Ad esempio, se il valore iniziale dell'intervallo viene omesso, il valore di inizio derivato</span><span class="sxs-lookup"><span data-stu-id="6d79d-324">For example, if the range start value is omitted, then the inferred start value</span></span> 
- <span data-ttu-id="6d79d-325">è zero se non è specificato alcun passaggio oppure il passaggio specificato è positivo e</span><span class="sxs-lookup"><span data-stu-id="6d79d-325">is zero if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="6d79d-326">lunghezza della matrice sezionata meno uno se il passaggio specificato è negativo.</span><span class="sxs-lookup"><span data-stu-id="6d79d-326">is the length of sliced array minus one if the specified step is negative.</span></span> 

<span data-ttu-id="6d79d-327">Se il valore finale dell'intervallo viene omesso, il valore di fine derivato</span><span class="sxs-lookup"><span data-stu-id="6d79d-327">If the range end value is omitted, then the inferred end value</span></span> 
- <span data-ttu-id="6d79d-328">lunghezza della matrice sezionata meno uno se non si specifica alcun passaggio oppure il passaggio specificato è positivo e</span><span class="sxs-lookup"><span data-stu-id="6d79d-328">is the length of sliced array minus one if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="6d79d-329">è zero se il passaggio specificato è negativo.</span><span class="sxs-lookup"><span data-stu-id="6d79d-329">is zero if the specified step is negative.</span></span> 

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

## <a name="array-element-expressions"></a><span data-ttu-id="6d79d-330">Espressioni di elementi di matrice</span><span class="sxs-lookup"><span data-stu-id="6d79d-330">Array Element Expressions</span></span>

<span data-ttu-id="6d79d-331">Data un'espressione di matrice e un'espressione `Int`, è possibile che venga creata una nuova espressione usando l'operatore `[` e `]` elemento Array.</span><span class="sxs-lookup"><span data-stu-id="6d79d-331">Given an array expression and an `Int` expression, a new expression may be formed using the `[` and `]` array element operator.</span></span>
<span data-ttu-id="6d79d-332">La nuova espressione sarà dello stesso tipo del tipo di elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="6d79d-332">The new expression will be the same type as the element type of the array.</span></span>
<span data-ttu-id="6d79d-333">Se ad esempio `a` è associato a una matrice di `Double`s, `a[4]` è un'espressione `Double`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-333">For instance, if `a` is bound to an array of `Double`s, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="6d79d-334">Se l'espressione di matrice non è un identificatore semplice, deve essere racchiusa tra parentesi per selezionare un elemento.</span><span class="sxs-lookup"><span data-stu-id="6d79d-334">If the array expression is not a simple identifier, it must be enclosed it parentheses in order to select an element.</span></span>
<span data-ttu-id="6d79d-335">Ad esempio, se `a` e `b` sono entrambe matrici di `Int`s, un elemento dalla concatenazione verrebbe espresso come:</span><span class="sxs-lookup"><span data-stu-id="6d79d-335">For instance, if `a` and `b` are both arrays of `Int`s, an element from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[13]
```

<span data-ttu-id="6d79d-336">Tutte le matrici in Q # sono in base zero.</span><span class="sxs-lookup"><span data-stu-id="6d79d-336">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="6d79d-337">Ovvero il primo elemento di una matrice `a` è sempre `a[0]`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-337">That is, the first element of an array `a` is always `a[0]`.</span></span>


## <a name="copy-and-update-expressions"></a><span data-ttu-id="6d79d-338">Espressioni di copia e aggiornamento</span><span class="sxs-lookup"><span data-stu-id="6d79d-338">Copy-and-Update Expressions</span></span>

<span data-ttu-id="6d79d-339">È possibile creare nuove matrici da quelle esistenti tramite espressioni di copia e aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="6d79d-339">New arrays can be created from existing ones via copy-and-update expressions.</span></span>
<span data-ttu-id="6d79d-340">Un'espressione di copia e aggiornamento è un'espressione nel formato `expression1 w/ expression2 <- expression3`, dove `expression1` deve essere di tipo `T[]` per alcuni tipi `T`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-340">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where `expression1` has to be of type `T[]` for some type `T`.</span></span> <span data-ttu-id="6d79d-341">Il secondo `expression2` definisce gli indici degli elementi da modificare rispetto alla matrice in `expression1` e deve essere di tipo `Int` o di tipo `Range`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-341">The second `expression2` defines the indices of the element(s) to modify compared to the array in `expression1` and has to be either of type `Int` or of type `Range`.</span></span> <span data-ttu-id="6d79d-342">Se `expression2` è di tipo `Int`, `expression3` deve essere di tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-342">If `expression2` is of type `Int`, `expression3` has to be of type `T`.</span></span> <span data-ttu-id="6d79d-343">Se `expression2` è di tipo `Range`, `expression3` deve essere di tipo `T[]`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-343">If `expression2` is of type `Range`, `expression3` has to be of type `T[]`.</span></span>

<span data-ttu-id="6d79d-344">Un'espressione di copia e aggiornamento `arr w/ idx <- value` crea una nuova matrice con tutti gli elementi impostati sull'elemento corrispondente in `arr`, ad eccezione degli elementi in `idx`, che vengono impostati su uno o più elementi in `value`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-344">A copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding element in `arr`, except for the element(s) at `idx`, which are set to the one(s) in `value`.</span></span> <span data-ttu-id="6d79d-345">Se, ad esempio, `arr` contiene una matrice `[0,1,2,3]`,</span><span class="sxs-lookup"><span data-stu-id="6d79d-345">For example, if `arr` contains an array `[0,1,2,3]`, then</span></span> 
- <span data-ttu-id="6d79d-346">`arr w/ 0 <- 10` è l'`[10,1,2,3]`di matrici.</span><span class="sxs-lookup"><span data-stu-id="6d79d-346">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="6d79d-347">`arr w/ 2 <- 10` è l'`[0,1,10,3]`di matrici.</span><span class="sxs-lookup"><span data-stu-id="6d79d-347">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="6d79d-348">`arr w/ 0..2..3 <- [10,12]` è l'`[10,1,12,3]`di matrici.</span><span class="sxs-lookup"><span data-stu-id="6d79d-348">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

<span data-ttu-id="6d79d-349">Sono presenti espressioni simili per gli elementi denominati in tipi definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="6d79d-349">Similar expressions exist for named items in user-defined types.</span></span> <span data-ttu-id="6d79d-350">Si consideri ad esempio il tipo</span><span class="sxs-lookup"><span data-stu-id="6d79d-350">Consider for example the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="6d79d-351">Se `c` contiene il valore di tipo `Complex(1.,-1.)`, `c w/ Re <- 0.` è un'espressione di tipo `Complex` che restituisce `Complex(0.,-1.)`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-351">If `c` contains the value of type `Complex(1.,-1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0.,-1.)`.</span></span>

## <a name="conditional-expressions"></a><span data-ttu-id="6d79d-352">Espressioni condizionali</span><span class="sxs-lookup"><span data-stu-id="6d79d-352">Conditional Expressions</span></span>

<span data-ttu-id="6d79d-353">Date due altre espressioni dello stesso tipo e di un'espressione booleana, l'espressione condizionale può essere formata usando il punto interrogativo `?` e la barra verticale `|`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-353">Given two other expressions of the same type and a Boolean expression, the conditional expression may be formed using the question mark `?` and the vertical bar `|`.</span></span>
<span data-ttu-id="6d79d-354">Ad esempio, `a==b ? c | d`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-354">For instance, `a==b ? c | d`.</span></span>
<span data-ttu-id="6d79d-355">In questo esempio, il valore dell'espressione condizionale verrà `c` se `a==b` è true e `d` se è false.</span><span class="sxs-lookup"><span data-stu-id="6d79d-355">In this example, the value of the conditional expression will be `c` if `a==b` is true and `d` if it is false.</span></span>

<span data-ttu-id="6d79d-356">Le due espressioni possono restituire operazioni con gli stessi input e output ma supportano funtori diversi.</span><span class="sxs-lookup"><span data-stu-id="6d79d-356">The two expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span>
<span data-ttu-id="6d79d-357">In questo caso, il tipo dell'espressione condizionale è un'operazione con gli input e gli output che supportano qualsiasi funtori supportato da entrambe le espressioni.</span><span class="sxs-lookup"><span data-stu-id="6d79d-357">In this case, the type of the conditional expression is an operation with those inputs and outputs that supports any functors supported by both expressions.</span></span>
<span data-ttu-id="6d79d-358">Ad esempio, se `Op1`, `Op2`e `Op3` sono tutti `Qubit[]=>Unit`, ma `Op1` supporta `Adjoint`, `Op2` supporta `Controlled`e `Op3` supporta entrambi:</span><span class="sxs-lookup"><span data-stu-id="6d79d-358">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="6d79d-359">`flag ? Op1 | Op2` è un'operazione di `(Qubit[] => Unit)`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-359">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="6d79d-360">`flag ? Op1 | Op3` è un'operazione di `(Qubit[] => Unit is Adj)`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-360">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="6d79d-361">`flag ? Op2 | Op3` è un'operazione di `(Qubit[] => Unit is Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-361">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="6d79d-362">Se una delle due espressioni di risultato possibili include una funzione o una chiamata a un'operazione, la chiamata verrà eseguita solo se il risultato è quello che sarà il valore della chiamata.</span><span class="sxs-lookup"><span data-stu-id="6d79d-362">If either of the two possible result expressions include a function or operation call, that call will only take place if that result is the one that will be the value of the call.</span></span>
<span data-ttu-id="6d79d-363">Ad esempio, nel caso `a==b ? C(qs) | D(qs)`, se `a==b` è true, l'operazione di `C` verrà richiamata e se è false, verrà richiamato solo `D`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-363">For instance, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true then the `C` operation will be invoked, and if it is false then only `D` will be invoked.</span></span>
<span data-ttu-id="6d79d-364">Questa operazione è simile a un cortocircuito in altri linguaggi.</span><span class="sxs-lookup"><span data-stu-id="6d79d-364">This is similar to short-circuiting in other languages.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="6d79d-365">Ordine di precedenza degli operatori</span><span class="sxs-lookup"><span data-stu-id="6d79d-365">Operator Precedence</span></span>

<span data-ttu-id="6d79d-366">Tutti gli operatori binari sono associativi a destra, ad eccezione di `^`.</span><span class="sxs-lookup"><span data-stu-id="6d79d-366">All binary operators are right-associative, except for `^`.</span></span>

<span data-ttu-id="6d79d-367">Le parentesi quadre, `[` e `]`, per l'indicizzazione e l'indicizzazione della matrice, vengono associate prima di qualsiasi operatore.</span><span class="sxs-lookup"><span data-stu-id="6d79d-367">Brackets, `[` and `]`, for array slicing and indexing, bind before any operator.</span></span>

<span data-ttu-id="6d79d-368">Funtori `Adjoint` e `Controlled` eseguire l'associazione dopo l'indicizzazione della matrice, ma prima di tutti gli altri operatori.</span><span class="sxs-lookup"><span data-stu-id="6d79d-368">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

<span data-ttu-id="6d79d-369">Anche le parentesi per la chiamata di operazioni e funzioni vengono associate prima di qualsiasi operatore, ma dopo l'indicizzazione della matrice e funtori.</span><span class="sxs-lookup"><span data-stu-id="6d79d-369">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="6d79d-370">Operatori in ordine di precedenza, dal più alto al più basso:</span><span class="sxs-lookup"><span data-stu-id="6d79d-370">Operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="6d79d-371">Operatore</span><span class="sxs-lookup"><span data-stu-id="6d79d-371">Operator</span></span> | <span data-ttu-id="6d79d-372">Grado</span><span class="sxs-lookup"><span data-stu-id="6d79d-372">Arity</span></span> | <span data-ttu-id="6d79d-373">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6d79d-373">Description</span></span> | <span data-ttu-id="6d79d-374">Tipi di operando</span><span class="sxs-lookup"><span data-stu-id="6d79d-374">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="6d79d-375">`!` finali</span><span class="sxs-lookup"><span data-stu-id="6d79d-375">trailing `!`</span></span> | <span data-ttu-id="6d79d-376">Unaria</span><span class="sxs-lookup"><span data-stu-id="6d79d-376">Unary</span></span> | <span data-ttu-id="6d79d-377">Unwrap</span><span class="sxs-lookup"><span data-stu-id="6d79d-377">Unwrap</span></span> | <span data-ttu-id="6d79d-378">Qualsiasi tipo definito dall'utente</span><span class="sxs-lookup"><span data-stu-id="6d79d-378">Any user-defined type</span></span>
 <span data-ttu-id="6d79d-379">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="6d79d-379">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="6d79d-380">Unaria</span><span class="sxs-lookup"><span data-stu-id="6d79d-380">Unary</span></span> | <span data-ttu-id="6d79d-381">Valore numerico negativo, complemento bit per bit, negazione logica</span><span class="sxs-lookup"><span data-stu-id="6d79d-381">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="6d79d-382">`Int`, `BigInt` o `Double` per `-`, `Int` o `BigInt` per `~~~`, `Bool` per `not`</span><span class="sxs-lookup"><span data-stu-id="6d79d-382">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="6d79d-383">Binary</span><span class="sxs-lookup"><span data-stu-id="6d79d-383">Binary</span></span> | <span data-ttu-id="6d79d-384">Potenza intera</span><span class="sxs-lookup"><span data-stu-id="6d79d-384">Integer power</span></span> | <span data-ttu-id="6d79d-385">`Int` o `BigInt` per la base, `Int` per l'esponente</span><span class="sxs-lookup"><span data-stu-id="6d79d-385">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="6d79d-386">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="6d79d-386">`/`, `*`, `%`</span></span> | <span data-ttu-id="6d79d-387">Binary</span><span class="sxs-lookup"><span data-stu-id="6d79d-387">Binary</span></span> | <span data-ttu-id="6d79d-388">Divisione, moltiplicazione, modulo Integer</span><span class="sxs-lookup"><span data-stu-id="6d79d-388">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="6d79d-389">`Int`, `BigInt` o `Double` per `/` e `*`, `Int` o `BigInt` per `%`</span><span class="sxs-lookup"><span data-stu-id="6d79d-389">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="6d79d-390">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="6d79d-390">`+`, `-`</span></span> | <span data-ttu-id="6d79d-391">Binary</span><span class="sxs-lookup"><span data-stu-id="6d79d-391">Binary</span></span> | <span data-ttu-id="6d79d-392">Aggiunta o concatenazione di stringhe e matrici, sottrazione</span><span class="sxs-lookup"><span data-stu-id="6d79d-392">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="6d79d-393">`Int`, `BigInt` o `Double`, `String` o qualsiasi tipo di matrice per `+`</span><span class="sxs-lookup"><span data-stu-id="6d79d-393">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="6d79d-394">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="6d79d-394">`<<<`, `>>>`</span></span> | <span data-ttu-id="6d79d-395">Binary</span><span class="sxs-lookup"><span data-stu-id="6d79d-395">Binary</span></span> | <span data-ttu-id="6d79d-396">Spostamento a sinistra, spostamento a destra</span><span class="sxs-lookup"><span data-stu-id="6d79d-396">Left shift, right shift</span></span> | <span data-ttu-id="6d79d-397">`Int` o `BigInt`</span><span class="sxs-lookup"><span data-stu-id="6d79d-397">`Int` or `BigInt`</span></span>
 <span data-ttu-id="6d79d-398">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="6d79d-398">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="6d79d-399">Binary</span><span class="sxs-lookup"><span data-stu-id="6d79d-399">Binary</span></span> | <span data-ttu-id="6d79d-400">Confronti minore di, minore di o uguale a, maggiore di, maggiore di o uguale a</span><span class="sxs-lookup"><span data-stu-id="6d79d-400">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="6d79d-401">`Int`, `BigInt` o `Double`</span><span class="sxs-lookup"><span data-stu-id="6d79d-401">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="6d79d-402">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="6d79d-402">`==`, `!=`</span></span> | <span data-ttu-id="6d79d-403">Binary</span><span class="sxs-lookup"><span data-stu-id="6d79d-403">Binary</span></span> | <span data-ttu-id="6d79d-404">confronti uguali, non uguali</span><span class="sxs-lookup"><span data-stu-id="6d79d-404">equal, not-equal comparisons</span></span> | <span data-ttu-id="6d79d-405">qualsiasi tipo primitivo</span><span class="sxs-lookup"><span data-stu-id="6d79d-405">any primitive type</span></span>
 `&&&` | <span data-ttu-id="6d79d-406">Binary</span><span class="sxs-lookup"><span data-stu-id="6d79d-406">Binary</span></span> | <span data-ttu-id="6d79d-407">AND bit per bit</span><span class="sxs-lookup"><span data-stu-id="6d79d-407">Bitwise AND</span></span> | <span data-ttu-id="6d79d-408">`Int` o `BigInt`</span><span class="sxs-lookup"><span data-stu-id="6d79d-408">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="6d79d-409">Binary</span><span class="sxs-lookup"><span data-stu-id="6d79d-409">Binary</span></span> | <span data-ttu-id="6d79d-410">XOR bit per bit</span><span class="sxs-lookup"><span data-stu-id="6d79d-410">Bitwise XOR</span></span> | <span data-ttu-id="6d79d-411">`Int` o `BigInt`</span><span class="sxs-lookup"><span data-stu-id="6d79d-411">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="6d79d-412">Binary</span><span class="sxs-lookup"><span data-stu-id="6d79d-412">Binary</span></span> | <span data-ttu-id="6d79d-413">OR bit per bit</span><span class="sxs-lookup"><span data-stu-id="6d79d-413">Bitwise OR</span></span> | <span data-ttu-id="6d79d-414">`Int` o `BigInt`</span><span class="sxs-lookup"><span data-stu-id="6d79d-414">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="6d79d-415">Binary</span><span class="sxs-lookup"><span data-stu-id="6d79d-415">Binary</span></span> | <span data-ttu-id="6d79d-416">AND logico</span><span class="sxs-lookup"><span data-stu-id="6d79d-416">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="6d79d-417">Binary</span><span class="sxs-lookup"><span data-stu-id="6d79d-417">Binary</span></span> | <span data-ttu-id="6d79d-418">OR logico</span><span class="sxs-lookup"><span data-stu-id="6d79d-418">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="6d79d-419">Binario/ternario</span><span class="sxs-lookup"><span data-stu-id="6d79d-419">Binary/Ternary</span></span> | <span data-ttu-id="6d79d-420">Operatore Range</span><span class="sxs-lookup"><span data-stu-id="6d79d-420">Range operator</span></span> | `Int`
 <span data-ttu-id="6d79d-421">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="6d79d-421">`?` `|`</span></span> | <span data-ttu-id="6d79d-422">Ternario</span><span class="sxs-lookup"><span data-stu-id="6d79d-422">Ternary</span></span> | <span data-ttu-id="6d79d-423">Condizionale</span><span class="sxs-lookup"><span data-stu-id="6d79d-423">Conditional</span></span> | <span data-ttu-id="6d79d-424">`Bool` per il lato sinistro</span><span class="sxs-lookup"><span data-stu-id="6d79d-424">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="6d79d-425">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="6d79d-425">`w/` `<-`</span></span> | <span data-ttu-id="6d79d-426">Ternario</span><span class="sxs-lookup"><span data-stu-id="6d79d-426">Ternary</span></span> | <span data-ttu-id="6d79d-427">Copia e aggiornamento</span><span class="sxs-lookup"><span data-stu-id="6d79d-427">Copy-and-update</span></span> | <span data-ttu-id="6d79d-428">vedere [espressioni di copia e aggiornamento](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="6d79d-428">see [copy-and-update expressions](#copy-and-update-expressions)</span></span>
