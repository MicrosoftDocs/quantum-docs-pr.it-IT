---
title: 'Struttura del file Q #'
description: 'Descrive la struttura e la sintassi di un file Q #.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
ms.openlocfilehash: cbee92c6d7e765237a7a42532dd7012b51421708
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430969"
---
# <a name="q-file-structure"></a><span data-ttu-id="91d99-103">Struttura del file Q #</span><span class="sxs-lookup"><span data-stu-id="91d99-103">Q# File Structure</span></span>

<span data-ttu-id="91d99-104">Ogni operazione Q #, funzione e tipo definito dall'utente viene definita all'interno di uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="91d99-104">Every Q# operation, function, and user-defined type is defined within a namespace.</span></span>

<span data-ttu-id="91d99-105">Un file Q # è costituito da una sequenza di *dichiarazioni dello spazio dei nomi*.</span><span class="sxs-lookup"><span data-stu-id="91d99-105">A Q# file consists of a sequence of *namespace declarations*.</span></span>
<span data-ttu-id="91d99-106">Ogni dichiarazione dello spazio dei nomi contiene dichiarazioni per i tipi, le operazioni e le funzioni definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="91d99-106">Each namespace declaration contains declarations for user-defined types, operations, and functions.</span></span>
<span data-ttu-id="91d99-107">Una dichiarazione dello spazio dei nomi può contenere un numero qualsiasi di ogni tipo di dichiarazione e in qualsiasi ordine.</span><span class="sxs-lookup"><span data-stu-id="91d99-107">A namespace declaration may contain any number of each type of declaration, and in any order.</span></span>
<span data-ttu-id="91d99-108">Per ulteriori informazioni sulla dichiarazione di tipi, [operazioni](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)e [funzioni](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions) [definiti dall'utente](xref:microsoft.quantum.guide.types#user-defined-types)all'interno di uno spazio dei nomi, attenersi ai collegamenti seguenti.</span><span class="sxs-lookup"><span data-stu-id="91d99-108">Follow these links for more details on declaring [user-defined types](xref:microsoft.quantum.guide.types#user-defined-types), [operations](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations), and [functions](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions) within a namespace.</span></span>

<span data-ttu-id="91d99-109">L'unico testo che può essere visualizzato al di fuori di una dichiarazione dello spazio dei nomi è comment.</span><span class="sxs-lookup"><span data-stu-id="91d99-109">The only text that can appear outside of a namespace declaration is comments.</span></span>
<span data-ttu-id="91d99-110">In particolare, i commenti relativi alla documentazione (altri dettagli di seguito) per uno spazio dei nomi precedono la dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="91d99-110">In particular, documentation comments (more details below) for a namespace precede the declaration.</span></span>

## <a name="namespace-declarations"></a><span data-ttu-id="91d99-111">Dichiarazioni dello spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="91d99-111">Namespace Declarations</span></span>

<span data-ttu-id="91d99-112">Un file Q # includerà in genere una sola dichiarazione dello spazio dei nomi, ma potrebbe avere nessuna (ed essere vuota o contenere solo commenti) oppure può contenere più spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="91d99-112">A Q# file will typically have exactly one namespace declaration, but may have none (and be empty or just contain comments) or may contain multiple namespaces.</span></span>
<span data-ttu-id="91d99-113">Le dichiarazioni dello spazio dei nomi non possono essere nidificate.</span><span class="sxs-lookup"><span data-stu-id="91d99-113">Namespace declarations may not be nested.</span></span>

<span data-ttu-id="91d99-114">Lo stesso spazio dei nomi può essere dichiarato in più file Q # compilati insieme, purché non esistano dichiarazioni di tipo, operazione o funzione con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="91d99-114">The same namespace may be declared in multiple Q# files that are compiled together, as long as there are no type, operation, or function declarations with the same name.</span></span>
<span data-ttu-id="91d99-115">In particolare, non è valido definire lo stesso tipo nello stesso spazio dei nomi in più file, anche se le dichiarazioni sono identiche.</span><span class="sxs-lookup"><span data-stu-id="91d99-115">In particular, it is invalid to define the same type in the same namespace in multiple files, even if the declarations are identical.</span></span>

<span data-ttu-id="91d99-116">Una dichiarazione dello spazio dei nomi è costituita dalla parola chiave `namespace` , seguita dal nome dello spazio dei nomi, da una parentesi graffa aperta `{` , dalle dichiarazioni contenute nello spazio dei nomi e da una parentesi graffa di chiusura `}` .</span><span class="sxs-lookup"><span data-stu-id="91d99-116">A namespace declaration consists of the keyword `namespace`, followed by the name of the namespace, an open brace `{`, the declarations contained in the namespace, and a close brace `}`.</span></span>
<span data-ttu-id="91d99-117">I nomi degli spazi dei nomi seguono il modello .NET di una sequenza di uno o più simboli validi separati da punti `.` .</span><span class="sxs-lookup"><span data-stu-id="91d99-117">Namespace names follow the .NET pattern of a sequence of one or more legal symbols separated by periods `.`.</span></span>
<span data-ttu-id="91d99-118">Ad esempio, `MyQuantumStuff` e `Microsoft.Quantum.Intrinsic` sono nomi di spazio dei nomi validi.</span><span class="sxs-lookup"><span data-stu-id="91d99-118">For instance, `MyQuantumStuff` and `Microsoft.Quantum.Intrinsic` are valid namespace names.</span></span>
<span data-ttu-id="91d99-119">Per convenzione, i simboli in un nome di spazio dei nomi sono in maiuscolo, ma ciò non è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="91d99-119">By convention, the symbols in a namespace name are capitalized, but this is not required.</span></span>

<span data-ttu-id="91d99-120">I riferimenti a tipi o chiamabili dichiarati più in basso in un file vengono risolti correttamente; non è necessario che il tipo, l'operazione o la dichiarazione di funzione precedano un riferimento ad esso.</span><span class="sxs-lookup"><span data-stu-id="91d99-120">References to types or callables declared further down in a file are resolved properly; there is no need for the type, operation, or function declaration to precede a reference to it.</span></span>

## <a name="open-directives"></a><span data-ttu-id="91d99-121">Direttive Open</span><span class="sxs-lookup"><span data-stu-id="91d99-121">Open Directives</span></span>

<span data-ttu-id="91d99-122">All'interno di un blocco dello spazio dei nomi, `open` è possibile usare la direttiva per importare tutti i tipi e le chiamabili dichiarati in un determinato spazio dei nomi e farvi riferimento in base al nome non qualificato.</span><span class="sxs-lookup"><span data-stu-id="91d99-122">Within a namespace block, the `open` directive may be used to import all types and callables declared in a certain namespace and refer to them by their unqualified name.</span></span>
<span data-ttu-id="91d99-123">Tale `open` direttiva è costituita dalla `open` parola chiave, seguita dallo spazio dei nomi da aprire e da un punto e virgola di terminazione.</span><span class="sxs-lookup"><span data-stu-id="91d99-123">Such an `open` directive consists of the `open` keyword, followed by the namespace to be opened and a terminating semicolon.</span></span>

> [!NOTE] 
> <span data-ttu-id="91d99-124">Tutte le `open` direttive devono essere visualizzate `function` prima `operation` di qualsiasi dichiarazione, o `newtype` nel blocco dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="91d99-124">All `open` directives must appear before any `function`, `operation`, or `newtype` declarations in the namespace block.</span></span>

<span data-ttu-id="91d99-125">Facoltativamente, è possibile definire un nome breve per lo spazio dei nomi aperto in modo che tutti gli elementi di tale spazio dei nomi possano (e devono) essere qualificati dal nome breve definito.</span><span class="sxs-lookup"><span data-stu-id="91d99-125">Optionally, a short name for the opened namespace may be defined such that all elements from that namespace can (and need) to be qualified by the defined short name.</span></span> <span data-ttu-id="91d99-126">Ad esempio, date le seguenti dichiarazioni dello spazio dei nomi e le direttive Open,</span><span class="sxs-lookup"><span data-stu-id="91d99-126">For example, given the following namespace declaration and open directives,</span></span>

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

<span data-ttu-id="91d99-127">Se un'operazione dichiarata usa un'operazione `Op` da `Microsoft.Quantum.Intrinsic` , è possibile chiamarla semplicemente usando `Op` .</span><span class="sxs-lookup"><span data-stu-id="91d99-127">if an operation we declare uses an operation `Op` from `Microsoft.Quantum.Intrinsic`, we would call it by simply using `Op`.</span></span>
<span data-ttu-id="91d99-128">Tuttavia, se si vuole chiamare una determinata funzione `Fn` da `Microsoft.Quantum.Math` , è necessario chiamarla usando `Math.Fn` .</span><span class="sxs-lookup"><span data-stu-id="91d99-128">However, if we wanted a call a certain function `Fn` from `Microsoft.Quantum.Math`, we would need to call it using `Math.Fn`.</span></span>

<span data-ttu-id="91d99-129">La `open` direttiva si applica all'intero blocco dello spazio dei nomi all'interno di un file.</span><span class="sxs-lookup"><span data-stu-id="91d99-129">The `open` directive applies to the entire namespace block within a file.</span></span>
<span data-ttu-id="91d99-130">Di conseguenza, se si definisce uno spazio dei nomi aggiuntivo nello stesso file Q # come `NS` indicato in precedenza, qualsiasi operazione/funzione/tipo definito nel secondo spazio dei nomi non avrà accesso a nulla da `Microsoft.Quantum.Intrinsic` o a `Microsoft.Quantum.Math` meno che non vengano ripetute le direttive aperte in esso contenute.</span><span class="sxs-lookup"><span data-stu-id="91d99-130">Hence, if we were to define an additional namespace in the same Q# file as `NS` above, then any operations/functions/types defined in the second namespace would not have access to anything from `Microsoft.Quantum.Intrinsic` or `Microsoft.Quantum.Math` unless we repeated the open directives therein.</span></span> 

<span data-ttu-id="91d99-131">Il nome completo di un tipo o di una chiamabile definito in un altro spazio dei nomi *non* aperto nello spazio dei nomi corrente deve essere usato come riferimento.</span><span class="sxs-lookup"><span data-stu-id="91d99-131">A type or callable defined in another namespace that is *not* opened in the current namespace must be referenced by its fully-qualified name.</span></span>
<span data-ttu-id="91d99-132">Ad esempio, è necessario fare riferimento a un'operazione denominata `Op` dallo `X.Y` spazio dei nomi con il nome completo `X.Y.Op` , a meno che `X.Y` lo spazio dei nomi non sia stato aperto in precedenza nel blocco corrente.</span><span class="sxs-lookup"><span data-stu-id="91d99-132">For example, an operation named `Op` from the `X.Y` namespace must be referenced by its fully-qualified name `X.Y.Op`, unless the `X.Y` namespace has been opened earlier in the current block.</span></span> <span data-ttu-id="91d99-133">Come indicato in precedenza, anche se lo `X` spazio dei nomi è stato aperto, non è possibile fare riferimento all'operazione come `Y.Op` .</span><span class="sxs-lookup"><span data-stu-id="91d99-133">As mentioned above, even if the `X` namespace has been opened, it is not possible to reference the operation as `Y.Op`.</span></span>
<span data-ttu-id="91d99-134">Se un nome breve `Z` per `X.Y` è stato definito nello spazio dei nomi e nel file, `Op` deve essere indicato come `Z.Op` .</span><span class="sxs-lookup"><span data-stu-id="91d99-134">If a short name `Z` for `X.Y` has been defined in that namespace and file, then `Op` needs to be referred to as `Z.Op`.</span></span> 

<span data-ttu-id="91d99-135">In genere è preferibile includere uno spazio dei nomi utilizzando una `open` direttiva.</span><span class="sxs-lookup"><span data-stu-id="91d99-135">It is usually better to include a namespace by using an `open` directive.</span></span>
<span data-ttu-id="91d99-136">L'utilizzo di un nome completo è obbligatorio se due spazi dei nomi definiscono costrutti con lo stesso nome e l'origine corrente utilizza costrutti di entrambi.</span><span class="sxs-lookup"><span data-stu-id="91d99-136">Using a fully-qualified name is required if two namespaces define constructs with the same name, and the current source uses constructs from both.</span></span>

<span data-ttu-id="91d99-137">Q # segue le stesse regole per la denominazione degli altri linguaggi .NET.</span><span class="sxs-lookup"><span data-stu-id="91d99-137">Q# follows the same rules for naming as other .NET languages.</span></span>
<span data-ttu-id="91d99-138">Tuttavia, Q # non supporta riferimenti relativi agli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="91d99-138">However, Q# does not support relative references to namespaces.</span></span>
<span data-ttu-id="91d99-139">Ovvero, se lo spazio dei nomi `a.b` è stato aperto, un riferimento a un'operazione `c.d` denominata *non* verrà risolto in un'operazione con nome completo `a.b.c.d` .</span><span class="sxs-lookup"><span data-stu-id="91d99-139">That is, if the namespace `a.b` has been opened, a reference to an operation named `c.d` will *not* be resolved to an operation with full name `a.b.c.d`.</span></span>

## <a name="formatting"></a><span data-ttu-id="91d99-140">Formattazione</span><span class="sxs-lookup"><span data-stu-id="91d99-140">Formatting</span></span>

<span data-ttu-id="91d99-141">La maggior parte delle istruzioni e le direttive Q # terminano con un punto e virgola di terminazione `;` .</span><span class="sxs-lookup"><span data-stu-id="91d99-141">Most Q# statements and directives end with a terminating semicolon, `;`.</span></span>
<span data-ttu-id="91d99-142">Le istruzioni e le dichiarazioni come `for` e `operation` che terminano con un blocco di istruzioni (vedere di seguito) non richiedono un punto e virgola di terminazione.</span><span class="sxs-lookup"><span data-stu-id="91d99-142">Statements and declarations such as `for` and `operation` that end with a statement block (see below) do not require a terminating semicolon.</span></span>
<span data-ttu-id="91d99-143">Ogni descrizione dell'istruzione indica se il punto e virgola di terminazione è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="91d99-143">Each statement description notes whether the terminating semicolon is required.</span></span>

<span data-ttu-id="91d99-144">Le istruzioni, come espressioni, dichiarazioni e direttive, possono essere suddivise in più righe.</span><span class="sxs-lookup"><span data-stu-id="91d99-144">Statements, like expressions, declarations, and directives, may be broken out across multiple lines.</span></span>
<span data-ttu-id="91d99-145">Evitare di avere più istruzioni su una sola riga.</span><span class="sxs-lookup"><span data-stu-id="91d99-145">Having multiple statements on a single line should be avoided.</span></span>

## <a name="statement-blocks"></a><span data-ttu-id="91d99-146">Blocchi di istruzioni</span><span class="sxs-lookup"><span data-stu-id="91d99-146">Statement Blocks</span></span>

<span data-ttu-id="91d99-147">Le istruzioni Q # sono raggruppate in blocchi di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="91d99-147">Q# statements are grouped into statement blocks.</span></span>
<span data-ttu-id="91d99-148">Un blocco di istruzioni inizia con un'apertura `{` e termina con una chiusura `}` .</span><span class="sxs-lookup"><span data-stu-id="91d99-148">A statement block starts with an opening `{` and ends with a closing `}`.</span></span>

<span data-ttu-id="91d99-149">Un blocco di istruzioni racchiuso in modo lessicale all'interno di un altro blocco viene considerato un sottoblocco del blocco contenitore; gli elementi e i sottoblocchi sono denominati anche blocchi esterni e interni.</span><span class="sxs-lookup"><span data-stu-id="91d99-149">A statement block that is lexically enclosed within another block is considered to be a sub-block of the containing block; containing and sub-blocks are also called outer and inner blocks.</span></span>

## <a name="comments"></a><span data-ttu-id="91d99-150">Commenti</span><span class="sxs-lookup"><span data-stu-id="91d99-150">Comments</span></span>

<span data-ttu-id="91d99-151">I commenti iniziano con due barre, `//` , e continuano fino alla fine della riga.</span><span class="sxs-lookup"><span data-stu-id="91d99-151">Comments begin with two forward slashes, `//`, and continue until the end of line.</span></span>
<span data-ttu-id="91d99-152">Un commento può essere visualizzato in qualsiasi punto di un file di origine Q #.</span><span class="sxs-lookup"><span data-stu-id="91d99-152">A comment may appear anywhere in a Q# source file.</span></span>

## <a name="documentation-comments"></a><span data-ttu-id="91d99-153">Commenti sulla documentazione</span><span class="sxs-lookup"><span data-stu-id="91d99-153">Documentation Comments</span></span>

<span data-ttu-id="91d99-154">I commenti che iniziano con tre barre, `///` , vengono trattati in modo speciale dal compilatore quando appaiono immediatamente prima di uno spazio dei nomi, un'operazione, una specializzazione, una funzione o una definizione di tipo.</span><span class="sxs-lookup"><span data-stu-id="91d99-154">Comments that begin with three forward slashes, `///`, are treated specially by the compiler when they appear immediately before a namespace, operation, specialization, function, or type definition.</span></span>
<span data-ttu-id="91d99-155">In tal caso, il contenuto viene considerato come documentazione per il tipo definito chiamabile o definito dall'utente, come per altri linguaggi .NET.</span><span class="sxs-lookup"><span data-stu-id="91d99-155">In that case, their contents are taken as documentation for the defined callable or user-defined type, as for other .NET languages.</span></span>

<span data-ttu-id="91d99-156">All'interno `///` dei commenti, il testo da visualizzare come parte della documentazione dell'API è formattato come [Markdown](https://daringfireball.net/projects/markdown/syntax), con diverse parti della documentazione indicate da intestazioni con nome specifico.</span><span class="sxs-lookup"><span data-stu-id="91d99-156">Within `///` comments, text to appear as a part of API documentation is formatted as [Markdown](https://daringfireball.net/projects/markdown/syntax), with different parts of the documentation being indicated by specially-named headers.</span></span>
<span data-ttu-id="91d99-157">Come estensione di Markdown, è possibile includere riferimenti incrociati a operazioni, funzioni e tipi definiti dall'utente in Q # usando `@"<ref target>"` , dove `<ref target>` viene sostituito dal nome completo dell'oggetto di codice a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="91d99-157">As an extension to Markdown, cross references to operations, functions and user-defined types in Q# can be included using the `@"<ref target>"`, where `<ref target>` is replaced by the fully qualified name of the code object being referenced.</span></span>
<span data-ttu-id="91d99-158">Facoltativamente, un motore di documentazione può supportare anche estensioni Markdown aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="91d99-158">Optionally, a documentation engine may also support additional Markdown extensions.</span></span>

<span data-ttu-id="91d99-159">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="91d99-159">For example:</span></span>

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

<span data-ttu-id="91d99-160">I nomi seguenti sono riconosciuti come intestazioni di commento della documentazione.</span><span class="sxs-lookup"><span data-stu-id="91d99-160">The following names are recognized as documentation comment headers.</span></span>

- <span data-ttu-id="91d99-161">**Riepilogo**: breve riepilogo del comportamento di una funzione o di un'operazione o dello scopo di un tipo.</span><span class="sxs-lookup"><span data-stu-id="91d99-161">**Summary**: A short summary of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="91d99-162">Il primo paragrafo del riepilogo viene usato per le informazioni sul passaggio del mouse.</span><span class="sxs-lookup"><span data-stu-id="91d99-162">The first paragraph of the summary is used for hover information.</span></span> <span data-ttu-id="91d99-163">Dovrebbe essere testo normale.</span><span class="sxs-lookup"><span data-stu-id="91d99-163">It should be plain text.</span></span>
- <span data-ttu-id="91d99-164">**Descrizione**: Descrizione del comportamento di una funzione o di un'operazione o dello scopo di un tipo.</span><span class="sxs-lookup"><span data-stu-id="91d99-164">**Description**: A description of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="91d99-165">Il riepilogo e la descrizione vengono concatenati per formare il file di documentazione generato per la funzione, l'operazione o il tipo.</span><span class="sxs-lookup"><span data-stu-id="91d99-165">The summary and description are concatenated to form the generated documentation file for the function, operation, or type.</span></span>
  <span data-ttu-id="91d99-166">La descrizione può contenere simboli e equazioni inline in formato LaTeX.</span><span class="sxs-lookup"><span data-stu-id="91d99-166">The description may contain in-line LaTeX-formatted symbols and equations.</span></span>
- <span data-ttu-id="91d99-167">**Input**: Descrizione della tupla di input per un'operazione o una funzione.</span><span class="sxs-lookup"><span data-stu-id="91d99-167">**Input**: A description of the input tuple for an operation or function.</span></span>
  <span data-ttu-id="91d99-168">Può contenere sottosezioni Markdown aggiuntive che indicano ogni singolo elemento della tupla di input.</span><span class="sxs-lookup"><span data-stu-id="91d99-168">May contain additional Markdown subsections indicating each individual element of the input tuple.</span></span>
- <span data-ttu-id="91d99-169">**Output**: Descrizione della tupla restituita da un'operazione o da una funzione.</span><span class="sxs-lookup"><span data-stu-id="91d99-169">**Output**: A description of the tuple returned by an operation or function.</span></span>
- <span data-ttu-id="91d99-170">**Parametri di tipo**: una sezione vuota contenente una sottosezione aggiuntiva per ogni parametro di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="91d99-170">**Type Parameters**: An empty section which contains one additional subsection for each generic type parameter.</span></span>
- <span data-ttu-id="91d99-171">**Esempio**: un breve esempio dell'operazione, della funzione o del tipo in uso.</span><span class="sxs-lookup"><span data-stu-id="91d99-171">**Example**: A short example of the operation, function or type in use.</span></span>
- <span data-ttu-id="91d99-172">**Note**: prosa Miscellanea che descrive alcuni aspetti dell'operazione, della funzione o del tipo.</span><span class="sxs-lookup"><span data-stu-id="91d99-172">**Remarks**: Miscellaneous prose describing some aspect of the operation, function, or type.</span></span>
- <span data-ttu-id="91d99-173">**Vedere anche**: elenco di nomi completi che indicano funzioni correlate, operazioni o tipi definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="91d99-173">**See Also**: A list of fully qualified names indicating related functions, operations, or user-defined types.</span></span>
- <span data-ttu-id="91d99-174">**Riferimenti**: un elenco di riferimenti e citazioni per l'elemento da documentare.</span><span class="sxs-lookup"><span data-stu-id="91d99-174">**References**: A list of references and citations for the item being documented.</span></span>

## <a name="whats-next"></a><span data-ttu-id="91d99-175">Operazioni successive</span><span class="sxs-lookup"><span data-stu-id="91d99-175">What's Next?</span></span>
<span data-ttu-id="91d99-176">Informazioni sulle [operazioni e sulle funzioni](xref:microsoft.quantum.guide.operationsfunctions) in Q #.</span><span class="sxs-lookup"><span data-stu-id="91d99-176">Learn about [Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions) in Q#.</span></span>