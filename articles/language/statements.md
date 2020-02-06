---
title: 'Istruzioni Q # | Microsoft Docs'
description: 'Istruzioni Q #'
author: QuantumWriter
uid: microsoft.quantum.language.statements
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 9a6f5d53ec21090d0c13f4369e0270d264cd1e9b
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036492"
---
# <a name="statements-and-other-constructs"></a><span data-ttu-id="6669d-103">Istruzioni e altri costrutti</span><span class="sxs-lookup"><span data-stu-id="6669d-103">Statements and Other Constructs</span></span>

## <a name="comments"></a><span data-ttu-id="6669d-104">Commenti</span><span class="sxs-lookup"><span data-stu-id="6669d-104">Comments</span></span>

<span data-ttu-id="6669d-105">I commenti iniziano con due barre, `//`e continuano fino alla fine della riga.</span><span class="sxs-lookup"><span data-stu-id="6669d-105">Comments begin with two forward slashes, `//`, and continue until the end of line.</span></span>
<span data-ttu-id="6669d-106">Un commento può essere visualizzato in qualsiasi punto di un file di origine Q #.</span><span class="sxs-lookup"><span data-stu-id="6669d-106">A comment may appear anywhere in a Q# source file.</span></span>

### <a name="documentation-comments"></a><span data-ttu-id="6669d-107">Commenti sulla documentazione</span><span class="sxs-lookup"><span data-stu-id="6669d-107">Documentation Comments</span></span>

<span data-ttu-id="6669d-108">I commenti che iniziano con tre barre, `///`, vengono trattati in modo speciale dal compilatore quando vengono visualizzati immediatamente prima di uno spazio dei nomi, un'operazione, una specializzazione, una funzione o una definizione di tipo.</span><span class="sxs-lookup"><span data-stu-id="6669d-108">Comments that begin with three forward slashes, `///`, are treated specially by the compiler when they appear immediately before a namespace, operation, specialization, function, or type definition.</span></span>
<span data-ttu-id="6669d-109">In tal caso, il contenuto viene considerato come documentazione per il tipo definito chiamabile o definito dall'utente, come per altri linguaggi .NET.</span><span class="sxs-lookup"><span data-stu-id="6669d-109">In that case, their contents are taken as documentation for the defined callable or user-defined type, as for other .NET languages.</span></span>

<span data-ttu-id="6669d-110">All'interno `///` commenti, il testo da visualizzare come parte della documentazione dell'API è formattato come [Markdown](https://daringfireball.net/projects/markdown/syntax), con diverse parti della documentazione indicate da intestazioni con nome specifico.</span><span class="sxs-lookup"><span data-stu-id="6669d-110">Within `///` comments, text to appear as a part of API documentation is formatted as [Markdown](https://daringfireball.net/projects/markdown/syntax), with different parts of the documentation being indicated by specially-named headers.</span></span>
<span data-ttu-id="6669d-111">Come estensione di Markdown, è possibile includere riferimenti incrociati a operazioni, funzioni e tipi definiti dall'utente in Q # usando il `@"<ref target>"`, in cui `<ref target>` viene sostituito dal nome completo dell'oggetto di codice a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="6669d-111">As an extension to Markdown, cross references to operations, functions and user-defined types in Q# can be included using the `@"<ref target>"`, where `<ref target>` is replaced by the fully qualified name of the code object being referenced.</span></span>
<span data-ttu-id="6669d-112">Facoltativamente, un motore di documentazione può supportare anche estensioni Markdown aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="6669d-112">Optionally, a documentation engine may also support additional Markdown extensions.</span></span>

<span data-ttu-id="6669d-113">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6669d-113">For example:</span></span>

```qsharp
/// # Summary
/// Given an operation and a target for that operation,
/// applies the given operation twice.
///
/// # Input
/// ## op
/// The operation to be applied.
/// ## target
/// The target to which the operation is to be applied.
///
/// # Type Parameters
/// ## 'T
/// The type expected by the given operation as its input.
///
/// # Example
/// ```Q#
/// // Should be equivalent to the identity.
/// ApplyTwice(H, qubit);
/// ```
///
/// # See Also
/// - Microsoft.Quantum.Intrinsic.H
operation ApplyTwice<'T>(op : ('T => Unit), target : 'T) : Unit {
    op(target);
    op(target);
}
```

<span data-ttu-id="6669d-114">I nomi seguenti sono riconosciuti come intestazioni di commento della documentazione.</span><span class="sxs-lookup"><span data-stu-id="6669d-114">The following names are recognized as documentation comment headers.</span></span>

- <span data-ttu-id="6669d-115">**Riepilogo**: breve riepilogo del comportamento di una funzione o di un'operazione o dello scopo di un tipo.</span><span class="sxs-lookup"><span data-stu-id="6669d-115">**Summary**: A short summary of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="6669d-116">Il primo paragrafo del riepilogo viene usato per le informazioni sul passaggio del mouse.</span><span class="sxs-lookup"><span data-stu-id="6669d-116">The first paragraph of the summary is used for hover information.</span></span> <span data-ttu-id="6669d-117">Dovrebbe essere testo normale.</span><span class="sxs-lookup"><span data-stu-id="6669d-117">It should be plain text.</span></span>
- <span data-ttu-id="6669d-118">**Descrizione**: Descrizione del comportamento di una funzione o di un'operazione o dello scopo di un tipo.</span><span class="sxs-lookup"><span data-stu-id="6669d-118">**Description**: A description of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="6669d-119">Il riepilogo e la descrizione vengono concatenati per formare il file di documentazione generato per la funzione, l'operazione o il tipo.</span><span class="sxs-lookup"><span data-stu-id="6669d-119">The summary and description are concatenated to form the generated documentation file for the function, operation, or type.</span></span>
  <span data-ttu-id="6669d-120">La descrizione può contenere simboli e equazioni inline in formato LaTeX.</span><span class="sxs-lookup"><span data-stu-id="6669d-120">The description may contain in-line LaTeX-formatted symbols and equations.</span></span>
- <span data-ttu-id="6669d-121">**Input**: Descrizione della tupla di input per un'operazione o una funzione.</span><span class="sxs-lookup"><span data-stu-id="6669d-121">**Input**: A description of the input tuple for an operation or function.</span></span>
  <span data-ttu-id="6669d-122">Può contenere sottosezioni Markdown aggiuntive che indicano ogni singolo elemento della tupla di input.</span><span class="sxs-lookup"><span data-stu-id="6669d-122">May contain additional Markdown subsections indicating each individual element of the input tuple.</span></span>
- <span data-ttu-id="6669d-123">**Output**: Descrizione della tupla restituita da un'operazione o da una funzione.</span><span class="sxs-lookup"><span data-stu-id="6669d-123">**Output**: A description of the tuple returned by an operation or function.</span></span>
- <span data-ttu-id="6669d-124">**Parametri di tipo**: una sezione vuota contenente una sottosezione aggiuntiva per ogni parametro di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="6669d-124">**Type Parameters**: An empty section which contains one additional subsection for each generic type parameter.</span></span>
- <span data-ttu-id="6669d-125">**Esempio**: un breve esempio dell'operazione, della funzione o del tipo in uso.</span><span class="sxs-lookup"><span data-stu-id="6669d-125">**Example**: A short example of the operation, function or type in use.</span></span>
- <span data-ttu-id="6669d-126">**Note**: prosa Miscellanea che descrive alcuni aspetti dell'operazione, della funzione o del tipo.</span><span class="sxs-lookup"><span data-stu-id="6669d-126">**Remarks**: Miscellaneous prose describing some aspect of the operation, function, or type.</span></span>
- <span data-ttu-id="6669d-127">**Vedere anche**: elenco di nomi completi che indicano funzioni correlate, operazioni o tipi definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="6669d-127">**See Also**: A list of fully qualified names indicating related functions, operations, or user-defined types.</span></span>
- <span data-ttu-id="6669d-128">**Riferimenti**: un elenco di riferimenti e citazioni per l'elemento da documentare.</span><span class="sxs-lookup"><span data-stu-id="6669d-128">**References**: A list of references and citations for the item being documented.</span></span>

## <a name="namespaces"></a><span data-ttu-id="6669d-129">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="6669d-129">Namespaces</span></span>

<span data-ttu-id="6669d-130">Ogni operazione Q #, funzione e tipo definito dall'utente viene definita all'interno di uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="6669d-130">Every Q# operation, function, and user-defined type is defined within a namespace.</span></span>
<span data-ttu-id="6669d-131">Q # segue le stesse regole per la denominazione degli altri linguaggi .NET.</span><span class="sxs-lookup"><span data-stu-id="6669d-131">Q# follows the same rules for naming as other .NET languages.</span></span>
<span data-ttu-id="6669d-132">Tuttavia, Q # non supporta riferimenti relativi agli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="6669d-132">However, Q# does not support relative references to namespaces.</span></span>
<span data-ttu-id="6669d-133">Ovvero, se lo spazio dei nomi `a.b` è stato aperto, un riferimento a un nome di operazione `c.d` non verrà risolto in un'operazione con nome completo `a.b.c.d`.</span><span class="sxs-lookup"><span data-stu-id="6669d-133">That is, if the namespace `a.b` has been opened, a reference to an operation names `c.d` will not be resolved to an operation with full name `a.b.c.d`.</span></span>

<span data-ttu-id="6669d-134">All'interno di un blocco dello spazio dei nomi, è possibile usare la direttiva `open` per importare tutti i tipi e chiamabili dichiarati in un determinato spazio dei nomi e farvi riferimento in base al nome non qualificato.</span><span class="sxs-lookup"><span data-stu-id="6669d-134">Within a namespace block, the `open` directive may be used to import all types and callables declared in a certain namespace and refer to them by their unqualified name.</span></span> <span data-ttu-id="6669d-135">Facoltativamente, è possibile definire un nome breve per lo spazio dei nomi aperto in modo che tutti gli elementi di tale spazio dei nomi possano (e devono) essere qualificati dal nome breve definito.</span><span class="sxs-lookup"><span data-stu-id="6669d-135">Optionally, a short name for the opened namespace may be defined such that all elements from that namespace can (and need) to be qualified by the defined short name.</span></span> <span data-ttu-id="6669d-136">La direttiva `open` si applica all'intero blocco dello spazio dei nomi all'interno di un file.</span><span class="sxs-lookup"><span data-stu-id="6669d-136">The `open` directive applies to the entire namespace block within a file.</span></span>

<span data-ttu-id="6669d-137">Il nome completo di un tipo o di una chiamabile definito in un altro spazio dei nomi non aperto nello spazio dei nomi corrente deve essere usato come riferimento.</span><span class="sxs-lookup"><span data-stu-id="6669d-137">A type or callable defined in another namespace that is not opened in the current namespace must be referenced by its fully-qualified name.</span></span>
<span data-ttu-id="6669d-138">Ad esempio, è necessario fare riferimento a un'operazione denominata `Op` nello spazio dei nomi `X.Y` mediante il nome completo `X.Y.Op`, a meno che lo spazio dei nomi `X.Y` non sia stato aperto in precedenza nel blocco corrente.</span><span class="sxs-lookup"><span data-stu-id="6669d-138">For example, an operation named `Op` in the `X.Y` namespace must be referenced by its fully-qualified name `X.Y.Op`, unless the `X.Y` namespace has been opened earlier in the current block.</span></span> <span data-ttu-id="6669d-139">Come indicato in precedenza, anche se lo spazio dei nomi `X` è stato aperto, non è possibile fare riferimento all'operazione come `Y.Op`.</span><span class="sxs-lookup"><span data-stu-id="6669d-139">As mentioned above, even if the `X` namespace has been opened, it is not possible to reference the operation as `Y.Op`.</span></span>
<span data-ttu-id="6669d-140">Se nel file e nello spazio dei nomi è stato definito un nome breve `Z` per `X.Y`, `Op` necessario denominarlo `Z.Op`.</span><span class="sxs-lookup"><span data-stu-id="6669d-140">If a short name `Z` for `X.Y` has been defined in that namespace and file, then `Op` needs to be referred to as `Z.Op`.</span></span> 

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace
}
```

<span data-ttu-id="6669d-141">In genere è preferibile includere uno spazio dei nomi utilizzando una direttiva `open`.</span><span class="sxs-lookup"><span data-stu-id="6669d-141">It is usually better to include a namespace by using an `open` directive.</span></span>
<span data-ttu-id="6669d-142">L'utilizzo di un nome completo è obbligatorio se due spazi dei nomi definiscono costrutti con lo stesso nome e l'origine corrente utilizza costrutti di entrambi.</span><span class="sxs-lookup"><span data-stu-id="6669d-142">Using a fully-qualified name is required if two namespaces define constructs with the same name, and the current source uses constructs from both.</span></span>

## <a name="formatting"></a><span data-ttu-id="6669d-143">Formattazione</span><span class="sxs-lookup"><span data-stu-id="6669d-143">Formatting</span></span>

<span data-ttu-id="6669d-144">La maggior parte delle istruzioni e le direttive Q # terminano con un punto e virgola di terminazione `;`.</span><span class="sxs-lookup"><span data-stu-id="6669d-144">Most Q# statements and directives end with a terminating semicolon, `;`.</span></span>
<span data-ttu-id="6669d-145">Le istruzioni e le dichiarazioni, ad esempio `for` e `operation` che terminano con un blocco di istruzioni, non richiedono un punto e virgola di terminazione.</span><span class="sxs-lookup"><span data-stu-id="6669d-145">Statements and declarations such as `for` and `operation` that end with a statement block do not require a terminating semicolon.</span></span>
<span data-ttu-id="6669d-146">Ogni descrizione dell'istruzione indica se il punto e virgola di terminazione è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="6669d-146">Each statement description notes whether the terminating semicolon is required.</span></span>

<span data-ttu-id="6669d-147">Le istruzioni, come espressioni, dichiarazioni e direttive, possono essere suddivise in più righe.</span><span class="sxs-lookup"><span data-stu-id="6669d-147">Statements, like expressions, declarations, and directives, may be broken out across multiple lines.</span></span>
<span data-ttu-id="6669d-148">Evitare di avere più istruzioni su una sola riga.</span><span class="sxs-lookup"><span data-stu-id="6669d-148">Having multiple statements on a single line should be avoided.</span></span>

## <a name="statement-blocks"></a><span data-ttu-id="6669d-149">Blocchi di istruzioni</span><span class="sxs-lookup"><span data-stu-id="6669d-149">Statement Blocks</span></span>

<span data-ttu-id="6669d-150">Le istruzioni Q # sono raggruppate in blocchi di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="6669d-150">Q# statements are grouped into statement blocks.</span></span>
<span data-ttu-id="6669d-151">Un blocco di istruzioni inizia con un `{` di apertura e termina con una `}`di chiusura.</span><span class="sxs-lookup"><span data-stu-id="6669d-151">A statement block starts with an opening `{` and ends with a closing `}`.</span></span>

<span data-ttu-id="6669d-152">Un blocco di istruzioni racchiuso in modo lessicale all'interno di un altro blocco viene considerato un sottoblocco del blocco contenitore; gli elementi e i sottoblocchi sono denominati anche blocchi esterni e interni.</span><span class="sxs-lookup"><span data-stu-id="6669d-152">A statement block that is lexically enclosed within another block is considered to be a sub-block of the containing block; containing and sub-blocks are also called outer and inner blocks.</span></span>

## <a name="symbol-binding-and-assignment"></a><span data-ttu-id="6669d-153">Associazione di simboli e assegnazione</span><span class="sxs-lookup"><span data-stu-id="6669d-153">Symbol Binding and Assignment</span></span>

<span data-ttu-id="6669d-154">Q # distingue tra simboli modificabili e non modificabili.</span><span class="sxs-lookup"><span data-stu-id="6669d-154">Q# distinguishes between mutable and immutable symbols.</span></span>
<span data-ttu-id="6669d-155">In generale, l'uso di simboli non modificabili è consigliato perché consente al compilatore di eseguire altre ottimizzazioni.</span><span class="sxs-lookup"><span data-stu-id="6669d-155">In general, the use of immutable symbols is encouraged because it allows the compiler to perform more optimizations.</span></span>

<span data-ttu-id="6669d-156">Il lato sinistro dell'associazione è costituito da una tupla di simboli e dalla parte destra di un'espressione.</span><span class="sxs-lookup"><span data-stu-id="6669d-156">The left-hand-side of the binding consists of a symbol tuple, and the right hand side of an expression.</span></span>

<span data-ttu-id="6669d-157">Poiché tutti i tipi Q # sono tipi di valore, con il qubits che prende un ruolo speciale in modo formale, una "copia" viene creata quando un valore è associato a un simbolo o quando un simbolo viene riassociato.</span><span class="sxs-lookup"><span data-stu-id="6669d-157">Since all Q# types are value types - with the qubits taking a somewhat special role - formally a "copy" is created when a value is bound to a symbol, or when a symbol is rebound.</span></span> <span data-ttu-id="6669d-158">Ovvero, il comportamento di Q # è identico a quello in cui è stata creata una copia durante l'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="6669d-158">That is to say, the behavior of Q# is the same as if a copy were created on assignment.</span></span> <span data-ttu-id="6669d-159">Questo in particolare include anche matrici.</span><span class="sxs-lookup"><span data-stu-id="6669d-159">This in particular also includes arrays.</span></span> <span data-ttu-id="6669d-160">Naturalmente, in pratica, solo le parti pertinenti vengono effettivamente ricreate in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="6669d-160">Of course in practice only the relevant pieces are actually recreated as needed.</span></span> 

### <a name="tuple-deconstruction"></a><span data-ttu-id="6669d-161">Decostruzione di Tuple</span><span class="sxs-lookup"><span data-stu-id="6669d-161">Tuple Deconstruction</span></span>

<span data-ttu-id="6669d-162">Se il lato destro dell'associazione è una tupla, la tupla può essere decostruita al momento dell'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="6669d-162">If the right-hand side of the binding is a tuple, then that tuple may be deconstructed upon assignment.</span></span>
<span data-ttu-id="6669d-163">Tali decostruzioni possono coinvolgere Tuple nidificate e qualsiasi decostruzione completa o parziale è valida purché la forma della tupla sulla parte destra sia compatibile con la forma della tupla di simboli.</span><span class="sxs-lookup"><span data-stu-id="6669d-163">Such deconstructions may involve nested tuples, and any full or partial deconstruction is valid as long as the shape of the tuple on the right hand side is compatible with the shape of the symbol tuple.</span></span>
<span data-ttu-id="6669d-164">La decostruzione di tuple può essere utilizzata in particolare quando il lato destro del `=` è un'espressione con valori di tupla.</span><span class="sxs-lookup"><span data-stu-id="6669d-164">Tuple deconstruction can in particular also be used when the right-hand side of the `=` is a tuple-valued expression.</span></span>

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

### <a name="immutable-symbols"></a><span data-ttu-id="6669d-165">Simboli non modificabili</span><span class="sxs-lookup"><span data-stu-id="6669d-165">Immutable Symbols</span></span>

<span data-ttu-id="6669d-166">I simboli non modificabili vengono associati utilizzando l'istruzione `let`.</span><span class="sxs-lookup"><span data-stu-id="6669d-166">Immutable symbols are bound using the `let` statement.</span></span>
<span data-ttu-id="6669d-167">Questo è approssimativamente equivalente alla dichiarazione di variabile e all'inizializzazione in C#linguaggi come, ad eccezione del fatto che i simboli Q #, una volta associati, non possono essere modificati; le associazioni `let` non sono modificabili.</span><span class="sxs-lookup"><span data-stu-id="6669d-167">This is roughly equivalent to variable declaration and initialization in languages such as C#, except that Q# symbols, once bound, may not be changed; `let` bindings are immutable.</span></span>

<span data-ttu-id="6669d-168">Un'associazione non modificabile è costituita dalla parola chiave `let`, seguita da un simbolo o da una tupla di simboli, un segno di uguale `=`, un'espressione a cui associare i simboli e un punto e virgola di terminazione.</span><span class="sxs-lookup"><span data-stu-id="6669d-168">An immutable binding consists of the keyword `let`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>
<span data-ttu-id="6669d-169">Il tipo dei simboli associati viene dedotto in base all'espressione sul lato destro.</span><span class="sxs-lookup"><span data-stu-id="6669d-169">The type of the bound symbol(s) is inferred based on the expression on the right hand side.</span></span>

### <a name="mutable-symbols"></a><span data-ttu-id="6669d-170">Simboli modificabili</span><span class="sxs-lookup"><span data-stu-id="6669d-170">Mutable Symbols</span></span>

<span data-ttu-id="6669d-171">I simboli modificabili vengono definiti e inizializzati utilizzando l'istruzione `mutable`.</span><span class="sxs-lookup"><span data-stu-id="6669d-171">Mutable symbols are defined and initialized using the `mutable` statement.</span></span>
<span data-ttu-id="6669d-172">I simboli dichiarati e associati come parte di un'istruzione `mutable` possono essere riassociati a un valore diverso in un secondo momento nel codice.</span><span class="sxs-lookup"><span data-stu-id="6669d-172">Symbols declared and bound as part of a `mutable` statement may be rebound to a different value later in the code.</span></span> 

<span data-ttu-id="6669d-173">Un'istruzione di associazione modificabile è costituita dalla parola chiave `mutable`, seguita da un simbolo o da una tupla di simboli, un segno di uguale `=`, un'espressione a cui associare i simboli e un punto e virgola di terminazione.</span><span class="sxs-lookup"><span data-stu-id="6669d-173">A mutable binding statement consists of the keyword `mutable`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>
<span data-ttu-id="6669d-174">Il tipo dei simboli associati viene dedotto in base all'espressione sul lato destro.</span><span class="sxs-lookup"><span data-stu-id="6669d-174">The type of the bound symbol(s) is inferred based on the expression on the right hand side.</span></span> <span data-ttu-id="6669d-175">Se un simbolo viene riassociato in un secondo momento nel codice, il relativo tipo non viene modificato e il valore associato deve essere compatibile con tale tipo.</span><span class="sxs-lookup"><span data-stu-id="6669d-175">If a symbol is rebound later in the code, its type does not change, and the bound value needs to be compatible with that type.</span></span>

### <a name="rebinding-of-mutable-symbols"></a><span data-ttu-id="6669d-176">Riassociazione di simboli modificabili</span><span class="sxs-lookup"><span data-stu-id="6669d-176">Rebinding of Mutable Symbols</span></span>

<span data-ttu-id="6669d-177">Una variabile modificabile può essere riassociata usando un'istruzione `set`.</span><span class="sxs-lookup"><span data-stu-id="6669d-177">A mutable variable may be rebound using a `set` statement.</span></span>
<span data-ttu-id="6669d-178">Tale riassociazione è costituita dalla parola chiave `set`, seguita da un simbolo o da una tupla di simboli, un segno di uguale `=`, un'espressione per riassociare i simboli a e un punto e virgola di terminazione.</span><span class="sxs-lookup"><span data-stu-id="6669d-178">Such a rebinding consists of the keyword `set`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to rebind the symbol(s) to, and a terminating semicolon.</span></span>
<span data-ttu-id="6669d-179">Il valore deve essere compatibile con i tipi dei simboli a cui è associata.</span><span class="sxs-lookup"><span data-stu-id="6669d-179">The value must be compatible with the type(s) of the symbol(s) it is bound to.</span></span>

#### <a name="apply-and-reassign-statement"></a><span data-ttu-id="6669d-180">Istruzione Apply-and-reassign</span><span class="sxs-lookup"><span data-stu-id="6669d-180">Apply-and-Reassign Statement</span></span>

<span data-ttu-id="6669d-181">Un particolare tipo di set-Statement a cui si fa riferimento come istruzione Apply-and-reassign fornisce un modo pratico per la concatenazione se il lato destro è costituito dall'applicazione di un operatore binario e il risultato deve essere riassociato all'argomento a sinistra per l'operatore.</span><span class="sxs-lookup"><span data-stu-id="6669d-181">A particular kind of set-statement we refer to as an apply-and-reassign statement provides a convenient way of concatenation if the right hand side consists of the application of a binary operator and the result is to be rebound to the left argument to the operator.</span></span> <span data-ttu-id="6669d-182">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="6669d-182">For example,</span></span>
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
<span data-ttu-id="6669d-183">incrementa il valore del contatore `counter` in ogni iterazione del ciclo di `for`.</span><span class="sxs-lookup"><span data-stu-id="6669d-183">increments the value of the counter `counter` in each iteration of the `for` loop.</span></span> <span data-ttu-id="6669d-184">Il codice precedente è equivalente a</span><span class="sxs-lookup"><span data-stu-id="6669d-184">The code above is equivalent to</span></span> 
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```
<span data-ttu-id="6669d-185">Sono disponibili istruzioni simili per tutti gli operatori binari in cui il tipo della parte sinistra corrisponde al tipo di espressione.</span><span class="sxs-lookup"><span data-stu-id="6669d-185">Similar statements are available for all binary operators in which the type of the left-hand-side matches the expression type.</span></span> <span data-ttu-id="6669d-186">In questo modo, ad esempio, viene fornito un modo pratico per accumulare i valori:</span><span class="sxs-lookup"><span data-stu-id="6669d-186">This provides for example a convenient way to accumulate values:</span></span>
```qsharp
mutable results = new Result[0];
for (qubit in qubits) {
    set results += [M(q)];
    // ...
}
```
#### <a name="update-and-reassign-statement"></a><span data-ttu-id="6669d-187">Istruzione Update-and-reassign</span><span class="sxs-lookup"><span data-stu-id="6669d-187">Update-and-Reassign Statement</span></span>

<span data-ttu-id="6669d-188">Esiste una concatenazione simile per le espressioni di copia e aggiornamento sul lato destro.</span><span class="sxs-lookup"><span data-stu-id="6669d-188">A similar concatenation exists for copy-and-update expressions on the right hand side.</span></span> <span data-ttu-id="6669d-189">Per gli elementi denominati nei tipi definiti dall'utente e per gli elementi della matrice sono disponibili le istruzioni Update e reassign corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="6669d-189">Correspondingly, update-and-reassign statements exist for named items in user-defined types as well as for array items.</span></span>  

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

<span data-ttu-id="6669d-190">Nel caso di matrici, le librerie standard contengono gli strumenti necessari per molte esigenze comuni di inizializzazione e manipolazione degli array, evitando così di dover aggiornare gli elementi della matrice in primo luogo.</span><span class="sxs-lookup"><span data-stu-id="6669d-190">In the case of arrays, our standard libraries contain the necessary tools for many common array initialization and manipulation needs, and thus help avoid having to update array items in the first place.</span></span> <span data-ttu-id="6669d-191">Le istruzioni Update-and-reassign forniscono un'alternativa se necessario:</span><span class="sxs-lookup"><span data-stu-id="6669d-191">Update-and-reassign statements provide an alternative if needed:</span></span>

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

> [!TIP]   
> <span data-ttu-id="6669d-192">Evitare l'uso non necessario di istruzioni Update e reassign usando gli strumenti disponibili in <xref:microsoft.quantum.arrays>.</span><span class="sxs-lookup"><span data-stu-id="6669d-192">Avoid unnecessary use of update-and-reassign statements by leveraging the tools provided in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="6669d-193">Funzione</span><span class="sxs-lookup"><span data-stu-id="6669d-193">The function</span></span>
```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];
    for (index in 0 .. length - 1) {
        set pauliArray w/= index <- 
            index == location ? pauli | PauliI;
    }    
    return pauliArray;
}
```
<span data-ttu-id="6669d-194">ad esempio, può essere semplicemente semplificato usando la funzione `ConstantArray` in `Microsoft.Quantum.Arrays`e restituendo un'espressione di copia e aggiornamento:</span><span class="sxs-lookup"><span data-stu-id="6669d-194">for example can simply be simplified using the function `ConstantArray` in `Microsoft.Quantum.Arrays`, and returning a copy-and-update expression:</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

### <a name="binding-scopes"></a><span data-ttu-id="6669d-195">Ambiti di associazione</span><span class="sxs-lookup"><span data-stu-id="6669d-195">Binding Scopes</span></span>

<span data-ttu-id="6669d-196">In generale, le associazioni di simboli non rientrano nell'ambito e diventano inattive alla fine del blocco di istruzioni in cui si verificano.</span><span class="sxs-lookup"><span data-stu-id="6669d-196">In general, symbol bindings go out of scope and become inoperative at the end of the statement block they occur in.</span></span>
<span data-ttu-id="6669d-197">Sono previste due eccezioni a questa regola:</span><span class="sxs-lookup"><span data-stu-id="6669d-197">There are two exceptions to this rule:</span></span>

- <span data-ttu-id="6669d-198">Il binding della variabile del ciclo di un ciclo di `for` è nell'ambito del corpo del ciclo for, ma non dopo la fine del ciclo.</span><span class="sxs-lookup"><span data-stu-id="6669d-198">The binding of the loop variable of a `for` loop is in scope for the body of the for loop, but not after the end of the loop.</span></span>
- <span data-ttu-id="6669d-199">Tutte e tre le parti di un `repeat`/ciclo `until` (il corpo, il test e la correzione) vengono considerati come un singolo ambito, quindi i simboli associati nel corpo sono disponibili nel test e nella correzione.</span><span class="sxs-lookup"><span data-stu-id="6669d-199">All three portions of a `repeat`/`until` loop (the body, the test, and the fixup) are treated as a single scope, so symbols that are bound in the body are available in the test and in the fixup.</span></span>

<span data-ttu-id="6669d-200">Per entrambi i tipi di cicli, ognuno passa attraverso il ciclo viene eseguito nel proprio ambito, quindi le associazioni da un passaggio precedente non sono disponibili in un passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="6669d-200">For both types of loops, each pass through the loop executes in its own scope, so bindings from an earlier pass are not available in a later pass.</span></span>

<span data-ttu-id="6669d-201">Le associazioni di simboli dei blocchi esterni vengono ereditate da blocchi interni.</span><span class="sxs-lookup"><span data-stu-id="6669d-201">Symbol bindings from outer blocks are inherited by inner blocks.</span></span>
<span data-ttu-id="6669d-202">Un simbolo può essere associato una sola volta per blocco; non è consentito definire un simbolo con lo stesso nome di un altro simbolo incluso nell'ambito (Nessuna ombreggiatura).</span><span class="sxs-lookup"><span data-stu-id="6669d-202">A symbol may only be bound once per block; it is illegal to define a symbol with the same name as another symbol that is within scope (no "shadowing").</span></span>
<span data-ttu-id="6669d-203">Le sequenze seguenti sarebbero valide:</span><span class="sxs-lookup"><span data-stu-id="6669d-203">The following sequences would be legal:</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

<span data-ttu-id="6669d-204">e</span><span class="sxs-lookup"><span data-stu-id="6669d-204">and</span></span>

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
```

<span data-ttu-id="6669d-205">Ma non è valido:</span><span class="sxs-lookup"><span data-stu-id="6669d-205">But this would be illegal:</span></span>

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

<span data-ttu-id="6669d-206">come:</span><span class="sxs-lookup"><span data-stu-id="6669d-206">as would:</span></span>

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="control-flow"></a><span data-ttu-id="6669d-207">Flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="6669d-207">Control Flow</span></span>

### <a name="for-loop"></a><span data-ttu-id="6669d-208">Ciclo For</span><span class="sxs-lookup"><span data-stu-id="6669d-208">For Loop</span></span>

<span data-ttu-id="6669d-209">L'istruzione `for` supporta l'iterazione su un intervallo di interi o su una matrice.</span><span class="sxs-lookup"><span data-stu-id="6669d-209">The `for` statement supports iteration over an integer range or over an array.</span></span>
<span data-ttu-id="6669d-210">L'istruzione è costituita dalla parola chiave `for`, da una parentesi di apertura `(`, seguita da un simbolo o da una tupla di simboli, dalla parola chiave `in`, da un'espressione di tipo `Range` o matrice, da una parentesi di chiusura `)`e da un blocco di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="6669d-210">The statement consists of the keyword `for`, an open parenthesis `(`, followed by a symbol or symbol tuple, the keyword `in`, an expression of type `Range` or array, a close parenthesis `)`, and a statement block.</span></span>

<span data-ttu-id="6669d-211">Il blocco di istruzioni (il corpo del ciclo) viene eseguito ripetutamente con i simboli definiti (le variabili del ciclo) associati a ogni valore nell'intervallo o nella matrice.</span><span class="sxs-lookup"><span data-stu-id="6669d-211">The statement block (the body of the loop) is executed repeatedly, with the defined symbol(s) (the loop variable(s)) bound to each value in the range or array.</span></span>
<span data-ttu-id="6669d-212">Si noti che se l'espressione di intervallo restituisce un intervallo o una matrice vuota, il corpo non verrà eseguito affatto.</span><span class="sxs-lookup"><span data-stu-id="6669d-212">Note that if the range expression evaluates to an empty range or array, the body will not be executed at all.</span></span>
<span data-ttu-id="6669d-213">L'espressione viene valutata completamente prima dell'immissione del ciclo e non verrà modificata durante l'esecuzione del ciclo.</span><span class="sxs-lookup"><span data-stu-id="6669d-213">The expression is fully evaluated before entering the loop, and will not change while the loop is executing.</span></span>

<span data-ttu-id="6669d-214">L'associazione dei simboli dichiarati non è modificabile e segue le stesse regole di altre associazioni variabili.</span><span class="sxs-lookup"><span data-stu-id="6669d-214">The binding of the declared symbol(s) is immutable and follows the same rules as other variable bindings.</span></span> <span data-ttu-id="6669d-215">In particolare, è possibile Destruct, ad esempio, gli elementi di matrice per un'iterazione su una matrice al momento dell'assegnazione alle variabili del ciclo.</span><span class="sxs-lookup"><span data-stu-id="6669d-215">In particular, it is possible to destruct e.g. array items for an iteration over an array upon assignment to the loop variable(s).</span></span>

<span data-ttu-id="6669d-216">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="6669d-216">For example,</span></span>

```qsharp
// ...
for (qubit in qubits) { // qubits contains a Qubit[]
    H(qubit);
}

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {
    set results w/= index <- (index, M(qubits[index]));
}

mutable accumulated = 0;
for ((index, measured) in results) {
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```

<span data-ttu-id="6669d-217">La variabile del ciclo è associata a ogni ingresso al corpo del ciclo e non è associata alla fine del corpo.</span><span class="sxs-lookup"><span data-stu-id="6669d-217">The loop variable is bound at each entrance to the loop body, and unbound at the end of the body.</span></span>
<span data-ttu-id="6669d-218">In particolare, la variabile di ciclo non è associata dopo il completamento del ciclo for.</span><span class="sxs-lookup"><span data-stu-id="6669d-218">In particular, the loop variable is not bound after the for loop is completed.</span></span>

### <a name="repeat-until-success-loop"></a><span data-ttu-id="6669d-219">Ciclo repeat-until-Success</span><span class="sxs-lookup"><span data-stu-id="6669d-219">Repeat-Until-Success Loop</span></span>

<span data-ttu-id="6669d-220">L'istruzione `repeat` supporta il modello quantum "repeat until Success".</span><span class="sxs-lookup"><span data-stu-id="6669d-220">The `repeat` statement supports the quantum “repeat until success” pattern.</span></span>
<span data-ttu-id="6669d-221">È costituito dalla parola chiave `repeat`, seguita da un blocco di istruzioni (Body del _ciclo_ ), dalla parola chiave `until`, da un'espressione booleana e da un punto e virgola di terminazione o dalla parola chiave `fixup` seguito da un altro blocco di istruzioni (la _correzione_).</span><span class="sxs-lookup"><span data-stu-id="6669d-221">It consists of the keyword `repeat`, followed by a statement block (the _loop_ body), the keyword `until`, a Boolean expression, and either a terminating semicolon or the keyword `fixup` followed by another statement block (the _fixup_).</span></span>
<span data-ttu-id="6669d-222">Il corpo del ciclo, la condizione e la correzione sono tutti considerati come un singolo ambito, quindi i simboli associati al corpo sono disponibili nella condizione e nella correzione.</span><span class="sxs-lookup"><span data-stu-id="6669d-222">The loop body, condition, and fixup are all considered to be a single scope, so symbols bound in the body are available in the condition and fixup.</span></span>

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

<span data-ttu-id="6669d-223">Il corpo del ciclo viene eseguito, quindi la condizione viene valutata.</span><span class="sxs-lookup"><span data-stu-id="6669d-223">The loop body is executed, and then the condition is evaluated.</span></span>
<span data-ttu-id="6669d-224">Se la condizione è true, l'istruzione viene completata; in caso contrario, la correzione viene eseguita e l'istruzione viene eseguita di nuovo a partire dal corpo del ciclo.</span><span class="sxs-lookup"><span data-stu-id="6669d-224">If the condition is true, then the statement is completed; otherwise, the fixup is executed, and the statement is re-executed starting with the loop body.</span></span>
<span data-ttu-id="6669d-225">Si noti che il completamento dell'esecuzione della correzione termina l'ambito dell'istruzione, in modo che le associazioni di simboli effettuate durante il corpo o la correzione non siano disponibili nelle ripetizioni successive.</span><span class="sxs-lookup"><span data-stu-id="6669d-225">Note that completing the execution of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="6669d-226">Il codice seguente, ad esempio, è un circuito probabilistico che implementa un controllo di rotazione importante $V _3 = (\boldone + 2 i Z)/\sqrt{5}$ usando i cancelli Hadamard e T.</span><span class="sxs-lookup"><span data-stu-id="6669d-226">For example, the following code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the Hadamard and T gates.</span></span>
<span data-ttu-id="6669d-227">Il ciclo termina in $ \frac{8}{5}$ ripetizioni in media.</span><span class="sxs-lookup"><span data-stu-id="6669d-227">The loop terminates in $\frac{8}{5}$ repetitions on average.</span></span>
<span data-ttu-id="6669d-228">Per informazioni dettagliate, vedere [*repeat-until-Success: scomposizione non deterministica di single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Papini e Svore, 2014).</span><span class="sxs-lookup"><span data-stu-id="6669d-228">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for details.</span></span>

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

> [!TIP]   
> <span data-ttu-id="6669d-229">Evitare l'utilizzo di cicli repeat-until-Success all'interno di funzioni.</span><span class="sxs-lookup"><span data-stu-id="6669d-229">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="6669d-230">La funzionalità corrispondente viene fornita dai cicli while nelle funzioni.</span><span class="sxs-lookup"><span data-stu-id="6669d-230">The corresponding functionality is provided by while loops in functions.</span></span> 

### <a name="while-loop"></a><span data-ttu-id="6669d-231">Ciclo while</span><span class="sxs-lookup"><span data-stu-id="6669d-231">While Loop</span></span>

<span data-ttu-id="6669d-232">I modelli repeat-until-Success hanno una connotazione molto specifica del quantum.</span><span class="sxs-lookup"><span data-stu-id="6669d-232">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="6669d-233">Sono ampiamente usati in particolari classi di algoritmi quantistici, di conseguenza il costrutto di linguaggio dedicato in Q #.</span><span class="sxs-lookup"><span data-stu-id="6669d-233">They are widely used in particular classes of quantum algorithms -- hence the dedicated language construct in Q#.</span></span> <span data-ttu-id="6669d-234">Tuttavia, i cicli che si interrompono in base a una condizione e la cui lunghezza di esecuzione risultano pertanto sconosciuti in fase di compilazione devono essere gestiti con particolare attenzione in un runtime Quantum.</span><span class="sxs-lookup"><span data-stu-id="6669d-234">However, loops that break based on a condition and whose execution length is thus unknown at compile time need to be handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="6669d-235">Il loro utilizzo all'interno delle funzioni non è problematico, dal momento che contengono solo codice che verrà eseguito su hardware convenzionale (non Quantum).</span><span class="sxs-lookup"><span data-stu-id="6669d-235">Their use within functions on the other hand is unproblematic, since these only contain code that will be executed on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="6669d-236">Q # supporta pertanto l'utilizzo dei cicli while solo all'interno di funzioni.</span><span class="sxs-lookup"><span data-stu-id="6669d-236">Q# therefore supports to use of while loops within functions only.</span></span> <span data-ttu-id="6669d-237">Un'istruzione `while` è costituita dalla parola chiave `while`, da una parentesi di apertura `(`, da una condizione (ovvero un'espressione booleana), da una parentesi di chiusura `)`e da un blocco di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="6669d-237">A `while` statement consists of the keyword `while`, an open parenthesis `(`, a condition (i.e. a Boolean expression), a close parenthesis `)`, and a statement block.</span></span>
<span data-ttu-id="6669d-238">Il blocco di istruzioni (il corpo del ciclo) viene eseguito finché la condizione restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="6669d-238">The statement block (the body of the loop) is executed as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

### <a name="conditional-statement"></a><span data-ttu-id="6669d-239">Istruzione condizionale</span><span class="sxs-lookup"><span data-stu-id="6669d-239">Conditional Statement</span></span>

<span data-ttu-id="6669d-240">L'istruzione `if` supporta l'esecuzione condizionale.</span><span class="sxs-lookup"><span data-stu-id="6669d-240">The `if` statement supports conditional execution.</span></span>
<span data-ttu-id="6669d-241">È costituito dalla parola chiave `if`, da una parentesi di apertura `(`, da un'espressione booleana, da una parentesi di chiusura `)`e da un blocco di istruzioni (il blocco _then_ ).</span><span class="sxs-lookup"><span data-stu-id="6669d-241">It consists of the keyword `if`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="6669d-242">Questo può essere seguito da un numero qualsiasi di clausole else-if, ciascuna delle quali è costituita dalla parola chiave `elif`, da una parentesi di apertura `(`, da un'espressione booleana, da una parentesi di chiusura `)`e da un blocco di istruzioni (il blocco _else-if_ ).</span><span class="sxs-lookup"><span data-stu-id="6669d-242">This may be followed by any number of else-if clauses, each of which consists of the keyword `elif`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="6669d-243">Infine, l'istruzione può terminare facoltativamente con una clausola else, che è costituita dalla parola chiave `else` seguita da un altro blocco Statement (il blocco _else_ ).</span><span class="sxs-lookup"><span data-stu-id="6669d-243">Finally, the statement may optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>
<span data-ttu-id="6669d-244">La condizione viene valutata e, se è true, il blocco then viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="6669d-244">The condition is evaluated, and if it is true, the then block is executed.</span></span>
<span data-ttu-id="6669d-245">Se la condizione è false, viene valutata la prima condizione else-if; Se è true, il blocco else-if viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="6669d-245">If the condition is false, then the first else-if condition is evaluated; if it is true, that else-if block is executed.</span></span>
<span data-ttu-id="6669d-246">In caso contrario, viene testato il secondo blocco else-if, quindi il terzo e così via fino a quando non viene rilevata una clausola con una condizione true o non sono presenti altre clausole else-if.</span><span class="sxs-lookup"><span data-stu-id="6669d-246">Otherwise, the second else-if block is tested, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="6669d-247">Se la condizione if originale e tutte le clausole else-if restituiscono false, il blocco Else viene eseguito se ne è stato fornito uno.</span><span class="sxs-lookup"><span data-stu-id="6669d-247">If the original if condition and all else-if clauses evaluate to false, the else block is executed if one was provided.</span></span>

<span data-ttu-id="6669d-248">Si noti che qualsiasi blocco eseguito viene eseguito nel proprio ambito.</span><span class="sxs-lookup"><span data-stu-id="6669d-248">Note that whichever block is executed is executed in its own scope.</span></span>
<span data-ttu-id="6669d-249">Le associazioni eseguite all'interno di un blocco then, else-if o else non sono visibili dopo la fine dell'istruzione if.</span><span class="sxs-lookup"><span data-stu-id="6669d-249">Bindings made inside of a then, else-if, or else block are not visible after the end of the if statement.</span></span>

<span data-ttu-id="6669d-250">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="6669d-250">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
} 
```

<span data-ttu-id="6669d-251">o</span><span class="sxs-lookup"><span data-stu-id="6669d-251">or</span></span>

```qsharp
if (i == 1) {
    X(target);
} elif (i == 2) {
    Y(target);
} else {
    Z(target);
}
```

### <a name="return"></a><span data-ttu-id="6669d-252">Return</span><span class="sxs-lookup"><span data-stu-id="6669d-252">Return</span></span>

<span data-ttu-id="6669d-253">L'istruzione return termina l'esecuzione di un'operazione o di una funzione e restituisce un valore al chiamante.</span><span class="sxs-lookup"><span data-stu-id="6669d-253">The return statement ends execution of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="6669d-254">È costituito dalla parola chiave `return`, seguita da un'espressione del tipo appropriato e da un punto e virgola di terminazione.</span><span class="sxs-lookup"><span data-stu-id="6669d-254">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="6669d-255">Oggetto chiamabile che restituisce una tupla vuota, `()`, non richiede un'istruzione return.</span><span class="sxs-lookup"><span data-stu-id="6669d-255">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
<span data-ttu-id="6669d-256">Se si desidera una prima uscita, in questo caso `return ()` possibile utilizzare.</span><span class="sxs-lookup"><span data-stu-id="6669d-256">If an early exit is desired, `return ()` may be used in this case.</span></span>
<span data-ttu-id="6669d-257">Le Callable che restituiscono qualsiasi altro tipo richiedono un'istruzione return finale.</span><span class="sxs-lookup"><span data-stu-id="6669d-257">Callables that return any other type require a final return statement.</span></span>

<span data-ttu-id="6669d-258">Non esiste un numero massimo di istruzioni return all'interno di un'operazione.</span><span class="sxs-lookup"><span data-stu-id="6669d-258">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="6669d-259">Il compilatore può generare un avviso se le istruzioni seguono un'istruzione return all'interno di un blocco.</span><span class="sxs-lookup"><span data-stu-id="6669d-259">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

<span data-ttu-id="6669d-260">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="6669d-260">For example,</span></span>

```qsharp
return 1;
```

<span data-ttu-id="6669d-261">o</span><span class="sxs-lookup"><span data-stu-id="6669d-261">or</span></span>

```qsharp
return ();
```

<span data-ttu-id="6669d-262">o</span><span class="sxs-lookup"><span data-stu-id="6669d-262">or</span></span>

```qsharp
return (results, qubits);
```

### <a name="fail"></a><span data-ttu-id="6669d-263">Esito negativo</span><span class="sxs-lookup"><span data-stu-id="6669d-263">Fail</span></span>

<span data-ttu-id="6669d-264">L'istruzione Fail termina l'esecuzione di un'operazione e restituisce un valore di errore al chiamante.</span><span class="sxs-lookup"><span data-stu-id="6669d-264">The fail statement ends execution of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="6669d-265">È costituito dalla parola chiave `fail`, seguita da una stringa e da un punto e virgola di terminazione.</span><span class="sxs-lookup"><span data-stu-id="6669d-265">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="6669d-266">La stringa viene restituita al driver classico come messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="6669d-266">The string is returned to the classical driver as the error message.</span></span>

<span data-ttu-id="6669d-267">Non esiste alcuna restrizione sul numero di istruzioni fail in un'operazione.</span><span class="sxs-lookup"><span data-stu-id="6669d-267">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="6669d-268">Il compilatore può generare un avviso se le istruzioni seguono un'istruzione Fail all'interno di un blocco.</span><span class="sxs-lookup"><span data-stu-id="6669d-268">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="6669d-269">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="6669d-269">For example,</span></span>

```qsharp
fail $"Impossible state reached";
```

<span data-ttu-id="6669d-270">o</span><span class="sxs-lookup"><span data-stu-id="6669d-270">or</span></span>

```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="qubit-management"></a><span data-ttu-id="6669d-271">Gestione qubit</span><span class="sxs-lookup"><span data-stu-id="6669d-271">Qubit Management</span></span>

<span data-ttu-id="6669d-272">Si noti che nessuna di queste istruzioni è consentita all'interno del corpo di una funzione.</span><span class="sxs-lookup"><span data-stu-id="6669d-272">Note that none of these statements are allowed within the body of a function.</span></span>
<span data-ttu-id="6669d-273">Sono valide solo all'interno delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="6669d-273">They are only valid within operations.</span></span>

### <a name="clean-qubits"></a><span data-ttu-id="6669d-274">Pulisci qubits</span><span class="sxs-lookup"><span data-stu-id="6669d-274">Clean Qubits</span></span>

<span data-ttu-id="6669d-275">L'istruzione `using` viene utilizzata per acquisire nuovi qubits da utilizzare durante un blocco di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="6669d-275">The `using` statement is used to acquire new qubits for use during a statement block.</span></span>
<span data-ttu-id="6669d-276">L'inizializzazione di qubits è garantita per lo stato `Zero` computazionale.</span><span class="sxs-lookup"><span data-stu-id="6669d-276">The qubits are guaranteed to be initialized to the computational `Zero` state.</span></span>
<span data-ttu-id="6669d-277">Il qubits deve trovarsi nello stato del `Zero` computazionale alla fine del blocco di istruzioni; i simulatori sono invitati a applicare questa operazione.</span><span class="sxs-lookup"><span data-stu-id="6669d-277">The qubits should be in the computational `Zero` state at the end of the statement block; simulators are encouraged to enforce this.</span></span>

<span data-ttu-id="6669d-278">L'istruzione è costituita dalla parola chiave `using`, seguita da una parentesi di apertura `(`, da un'associazione, da una parentesi di chiusura `)`e dal blocco di istruzioni in cui qubits sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="6669d-278">The statement consists of the keyword `using`, followed by an open parenthesis `(`, a binding, a close parenthesis `)`, and the statement block within which the qubits will be available.</span></span>
<span data-ttu-id="6669d-279">Il binding segue lo stesso modello delle istruzioni `let`: un singolo simbolo o una tupla di simboli, seguito da un segno di uguale `=`e da un singolo valore o da una tupla corrispondente di inizializzatori.</span><span class="sxs-lookup"><span data-stu-id="6669d-279">The binding follows the same pattern as `let` statements: either a single symbol or a tuple of symbols, followed by an equals sign `=`, and either a single value or a matching tuple of initializers.</span></span>
<span data-ttu-id="6669d-280">Gli inizializzatori sono disponibili per un singolo qubit, indicato come `Qubit()`, o una matrice di qubits, indicata da `Qubit[`, un'espressione `Int` e `]`.</span><span class="sxs-lookup"><span data-stu-id="6669d-280">Initializers are available either for a single qubit, indicated as `Qubit()`, or an array of qubits, indicated by `Qubit[`, an `Int` expression, and `]`.</span></span>

<span data-ttu-id="6669d-281">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="6669d-281">For example,</span></span>

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

### <a name="borrowed-qubits"></a><span data-ttu-id="6669d-282">Qubits preso in prestito</span><span class="sxs-lookup"><span data-stu-id="6669d-282">Borrowed Qubits</span></span>

<span data-ttu-id="6669d-283">L'istruzione `borrowing` viene utilizzata per ottenere qubits per l'utilizzo temporaneo.</span><span class="sxs-lookup"><span data-stu-id="6669d-283">The `borrowing` statement is used to obtain qubits for temporary use.</span></span> <span data-ttu-id="6669d-284">L'istruzione è costituita dalla parola chiave `borrowing`, seguita da una parentesi di apertura `(`, da un'associazione, da una parentesi di chiusura `)`e dal blocco di istruzioni in cui qubits sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="6669d-284">The statement consists of the keyword `borrowing`, followed by an open parenthesis `(`, a binding, a close parenthesis `)`, and the statement block within which the qubits will be available.</span></span>
<span data-ttu-id="6669d-285">L'associazione segue lo stesso modello e le stesse regole di un'istruzione `using`.</span><span class="sxs-lookup"><span data-stu-id="6669d-285">The binding follows the same pattern and rules as the one in a `using` statement.</span></span>

<span data-ttu-id="6669d-286">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="6669d-286">For example,</span></span>

```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

<span data-ttu-id="6669d-287">I qubits presi in prestito sono in uno stato sconosciuto e non rientrano nell'ambito alla fine del blocco di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="6669d-287">The borrowed qubits are in an unknown state and go out of scope at the end of the statement block.</span></span>
<span data-ttu-id="6669d-288">Il mutuatario si impegna a lasciare il qubits nello stesso stato in cui si trovavano quando sono state prese in prestito, ovvero il proprio stato all'inizio e alla fine del blocco di istruzioni deve essere lo stesso.</span><span class="sxs-lookup"><span data-stu-id="6669d-288">The borrower commits to leaving the qubits in the same state they were in when they were borrowed, i.e. their state at the beginning and at the end of the statement block is expected to be the same.</span></span>
<span data-ttu-id="6669d-289">Questo stato in particolare non è necessariamente uno stato classico, in modo che nella maggior parte dei casi gli ambiti in prestito non contengano misurazioni.</span><span class="sxs-lookup"><span data-stu-id="6669d-289">This state in particular is not necessarily a classical state, such that in most cases, borrowing scopes should not contain measurements.</span></span> 

<span data-ttu-id="6669d-290">Per un esempio di uso di Svore in prestito, vedere [*factoring using 2n + 2 qubits with Toffoli Modular based Moltiplication*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler e qubit 2017).</span><span class="sxs-lookup"><span data-stu-id="6669d-290">See [*Factoring using 2n+2 qubits with Toffoli based modular multiplication*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler, and Svore 2017) for an example of borrowed qubit use.</span></span>

<span data-ttu-id="6669d-291">Quando si prendono in prestito qubits, il sistema tenterà innanzitutto di compilare la richiesta da qubits in uso, ma non è possibile accedervi durante il corpo dell'istruzione `borrowing`.</span><span class="sxs-lookup"><span data-stu-id="6669d-291">When borrowing qubits, the system will first try to fill the request from qubits that are in use but that are not accessed during the body of the `borrowing` statement.</span></span>
<span data-ttu-id="6669d-292">Se il qubits non è sufficiente, verrà allocato il nuovo qubits per completare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="6669d-292">If there aren't enough such qubits, then it will allocate new qubits to complete the request.</span></span>

## <a name="conjugations"></a><span data-ttu-id="6669d-293">Coniugazioni</span><span class="sxs-lookup"><span data-stu-id="6669d-293">Conjugations</span></span>

<span data-ttu-id="6669d-294">A differenza dei bit classici, il rilascio della memoria quantistica è leggermente più coinvolto, perché la reimpostazione cieca di qubits può avere effetti indesiderati sul calcolo rimanente se il qubits è ancora stato impigliato.</span><span class="sxs-lookup"><span data-stu-id="6669d-294">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="6669d-295">Questa operazione può essere evitata eseguendo correttamente i calcoli eseguiti prima di rilasciare la memoria.</span><span class="sxs-lookup"><span data-stu-id="6669d-295">This can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="6669d-296">Un modello comune in quantum computing è quindi il seguente:</span><span class="sxs-lookup"><span data-stu-id="6669d-296">A common pattern in quantum computing is hence the following:</span></span> 

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

<span data-ttu-id="6669d-297">: nuovo: a partire dalla versione 0,9, è supportata un'istruzione di coniugazione che implementa la trasformazione sopra.</span><span class="sxs-lookup"><span data-stu-id="6669d-297">:new: Starting with our 0.9 release, we support a conjugation statement that implements the transformation above.</span></span> <span data-ttu-id="6669d-298">Utilizzando tale istruzione, l'operazione `ApplyWith` può essere implementata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="6669d-298">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

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
<span data-ttu-id="6669d-299">Tale istruzione di coniugazione, ovviamente, diventa molto più utile se la trasformazione esterna e interna non è immediatamente disponibile come operazione, ma è più semplice da descrivere da un blocco composto da diverse istruzioni.</span><span class="sxs-lookup"><span data-stu-id="6669d-299">Such a conjugation statement obviously becomes far more useful if the outer and inner transformation are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="6669d-300">La trasformazione inversa per le istruzioni definite nel blocco interno viene generata automaticamente dal compilatore ed eseguita al termine del blocco Apply.</span><span class="sxs-lookup"><span data-stu-id="6669d-300">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and executed after the apply-block completes.</span></span> <span data-ttu-id="6669d-301">Poiché le variabili modificabili usate come parte del blocco all'interno non possono essere riassociati nel blocco Apply, la trasformazione generata è sicuramente l'elemento contiguo del calcolo nel blocco all'interno.</span><span class="sxs-lookup"><span data-stu-id="6669d-301">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 

## <a name="expression-evaluation-statements"></a><span data-ttu-id="6669d-302">Istruzioni di valutazione delle espressioni</span><span class="sxs-lookup"><span data-stu-id="6669d-302">Expression Evaluation Statements</span></span>

<span data-ttu-id="6669d-303">Qualsiasi espressione di chiamata di tipo `Unit` può essere utilizzata come un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="6669d-303">Any call expression of type `Unit` may be used as a statement.</span></span>
<span data-ttu-id="6669d-304">Questa operazione viene utilizzata principalmente quando si chiamano le operazioni su qubits che restituiscono `Unit` perché lo scopo dell'istruzione è modificare lo stato quantum implicito.</span><span class="sxs-lookup"><span data-stu-id="6669d-304">This is primarily of use when calling operations on qubits that return `Unit` because the purpose of the statement is to modify the implicit quantum state.</span></span>
<span data-ttu-id="6669d-305">Le istruzioni di valutazione dell'espressione richiedono un punto e virgola di terminazione.</span><span class="sxs-lookup"><span data-stu-id="6669d-305">Expression evaluation statements require a terminating semicolon.</span></span>

<span data-ttu-id="6669d-306">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="6669d-306">For example,</span></span>

```qsharp
X(q);
CNOT(control, target);
Adjoint T(q);
```
