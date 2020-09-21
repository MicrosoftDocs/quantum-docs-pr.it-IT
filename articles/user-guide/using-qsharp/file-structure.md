---
title: Q# Struttura di file
description: Descrive la struttura e la sintassi di un Q# file.
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
no-loc:
- Q#
- $$v
ms.openlocfilehash: 98b3a2e35186989b8191cc566a5d5310bc26eafc
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833306"
---
# <a name="no-locq-file-structure"></a><span data-ttu-id="73a92-103">Q# Struttura di file</span><span class="sxs-lookup"><span data-stu-id="73a92-103">Q# File Structure</span></span>

<span data-ttu-id="73a92-104">Un Q# file è costituito da una sequenza di *dichiarazioni dello spazio dei nomi*.</span><span class="sxs-lookup"><span data-stu-id="73a92-104">A Q# file consists of a sequence of *namespace declarations*.</span></span>
<span data-ttu-id="73a92-105">Ogni dichiarazione dello spazio dei nomi contiene dichiarazioni per tipi, operazioni e funzioni definiti dall'utente e può contenere un numero qualsiasi di ogni tipo di dichiarazione e in qualsiasi ordine.</span><span class="sxs-lookup"><span data-stu-id="73a92-105">Each namespace declaration contains declarations for user-defined types, operations, and functions, and can contain any number of each type of declaration and in any order.</span></span>
<span data-ttu-id="73a92-106">Per altre informazioni sulle dichiarazioni all'interno di uno spazio dei nomi, vedere [tipi definiti dall'utente](xref:microsoft.quantum.guide.types#user-defined-types), [operazioni](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)e [funzioni](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions).</span><span class="sxs-lookup"><span data-stu-id="73a92-106">For more information on declarations within a namespace, see [user-defined types](xref:microsoft.quantum.guide.types#user-defined-types), [operations](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations), and [functions](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions).</span></span>

<span data-ttu-id="73a92-107">L'unico testo che può essere visualizzato al di fuori di una dichiarazione dello spazio dei nomi è comment.</span><span class="sxs-lookup"><span data-stu-id="73a92-107">The only text that can appear outside of a namespace declaration is comments.</span></span>
<span data-ttu-id="73a92-108">In particolare, i commenti relativi alla documentazione per uno spazio dei nomi precedono la dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="73a92-108">In particular, documentation comments for a namespace precede the declaration.</span></span> <span data-ttu-id="73a92-109">Per ulteriori informazioni, vedere la [documentazione relativa ai commenti](#documentation-comments) in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="73a92-109">For more information, see [Documentation comments](#documentation-comments) in this article.</span></span> 

## <a name="namespace-declarations"></a><span data-ttu-id="73a92-110">Dichiarazioni dello spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="73a92-110">Namespace Declarations</span></span>

<span data-ttu-id="73a92-111">Un Q# file ha in genere una sola dichiarazione dello spazio dei nomi, ma potrebbe avere nessuna (ed essere vuota o contenere solo commenti) o contenere più spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="73a92-111">A Q# file typically has just one namespace declaration, but could have none (and be empty or just contain comments) or could contain multiple namespaces.</span></span>
<span data-ttu-id="73a92-112">Non è possibile nidificare le dichiarazioni dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="73a92-112">Namespace declarations can not be nested.</span></span>

<span data-ttu-id="73a92-113">È possibile dichiarare lo stesso spazio dei nomi in più Q# file compilati insieme, purché non esistano dichiarazioni di tipo, operazione o funzione con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="73a92-113">You can declare the same namespace in multiple Q# files that are compiled together, as long as there are no type, operation, or function declarations with the same name.</span></span>
<span data-ttu-id="73a92-114">In particolare, non è valido definire lo stesso tipo nello stesso spazio dei nomi in più file, anche se le dichiarazioni sono identiche.</span><span class="sxs-lookup"><span data-stu-id="73a92-114">In particular, it is invalid to define the same type in the same namespace in multiple files, even if the declarations are identical.</span></span>

<span data-ttu-id="73a92-115">Una dichiarazione dello spazio dei nomi è costituita dalla parola chiave `namespace` , seguita dal nome dello spazio dei nomi e dalle dichiarazioni contenute nello spazio dei nomi racchiuso tra parentesi graffe `{ }` .</span><span class="sxs-lookup"><span data-stu-id="73a92-115">A namespace declaration consists of the keyword `namespace`, followed by the name of the namespace, and the declarations contained in the namespace enclosed in braces `{ }`.</span></span>
<span data-ttu-id="73a92-116">I nomi degli spazi dei nomi seguono il modello .NET di una sequenza di uno o più simboli validi separati da punti `.` .</span><span class="sxs-lookup"><span data-stu-id="73a92-116">Namespace names follow the .NET pattern of a sequence of one or more legal symbols separated by periods `.`.</span></span>
<span data-ttu-id="73a92-117">Ad esempio, `MyQuantumStuff` e `Microsoft.Quantum.Intrinsic` sono nomi di spazio dei nomi validi.</span><span class="sxs-lookup"><span data-stu-id="73a92-117">For example, `MyQuantumStuff` and `Microsoft.Quantum.Intrinsic` are valid namespace names.</span></span>
<span data-ttu-id="73a92-118">Per convenzione, è tuttavia necessario capitalizzare i simboli in un nome di spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="73a92-118">By convention, capitalize the symbols in a namespace name, however, this is not required.</span></span>

<span data-ttu-id="73a92-119">I riferimenti a tipi o chiamabili dichiarati più in basso in un file vengono risolti correttamente; non è necessario che il tipo, l'operazione o la dichiarazione di funzione precedano un riferimento ad esso.</span><span class="sxs-lookup"><span data-stu-id="73a92-119">References to types or callables declared further down in a file resolve properly; there is no need for the type, operation, or function declaration to precede a reference to it.</span></span>

## <a name="open-directives"></a><span data-ttu-id="73a92-120">Direttive Open</span><span class="sxs-lookup"><span data-stu-id="73a92-120">Open Directives</span></span>

<span data-ttu-id="73a92-121">All'interno di un blocco dello spazio dei nomi, utilizzare la `open` direttiva per importare tutti i tipi e le chiamabili dichiarati in un determinato spazio dei nomi e farvi riferimento in base al nome non qualificato.</span><span class="sxs-lookup"><span data-stu-id="73a92-121">Within a namespace block, use the `open` directive to import all types and callables declared in a certain namespace and refer to them by their unqualified name.</span></span>
<span data-ttu-id="73a92-122">Tale `open` direttiva è costituita dalla `open` parola chiave, seguita dallo spazio dei nomi da aprire e da un punto e virgola di terminazione.</span><span class="sxs-lookup"><span data-stu-id="73a92-122">Such an `open` directive consists of the `open` keyword, followed by the namespace to be opened and a terminating semicolon.</span></span>

> [!NOTE] 
> <span data-ttu-id="73a92-123">Tutte le `open` direttive devono essere visualizzate `function` prima `operation` di qualsiasi dichiarazione, o `newtype` nel blocco dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="73a92-123">All `open` directives must appear before any `function`, `operation`, or `newtype` declarations in the namespace block.</span></span>

<span data-ttu-id="73a92-124">Facoltativamente, è possibile definire un nome breve per lo spazio dei nomi aperto.</span><span class="sxs-lookup"><span data-stu-id="73a92-124">Optionally, you can define a short name for the opened namespace.</span></span> <span data-ttu-id="73a92-125">Se viene definito un nome breve, è necessario qualificare tutti gli elementi da tale spazio dei nomi in base al nome breve definito.</span><span class="sxs-lookup"><span data-stu-id="73a92-125">If a short name is defined, you must qualify all elements from that namespace by the defined short name.</span></span> <span data-ttu-id="73a92-126">Ad esempio, date le seguenti dichiarazioni dello spazio dei nomi e le direttive Open,</span><span class="sxs-lookup"><span data-stu-id="73a92-126">For example, given the following namespace declaration and open directives,</span></span>

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

<span data-ttu-id="73a92-127">Se un'operazione dichiarata utilizza un'operazione `Op` da `Microsoft.Quantum.Intrinsic` , è possibile chiamarla semplicemente utilizzando `Op` .</span><span class="sxs-lookup"><span data-stu-id="73a92-127">if a declared operation uses an operation `Op` from `Microsoft.Quantum.Intrinsic`, you call it by simply using `Op`.</span></span>
<span data-ttu-id="73a92-128">Tuttavia, per chiamare una determinata funzione `Fn` da `Microsoft.Quantum.Math` , è necessario chiamarla usando `Math.Fn` .</span><span class="sxs-lookup"><span data-stu-id="73a92-128">However, to call a certain function `Fn` from `Microsoft.Quantum.Math`, you must call it using `Math.Fn`.</span></span>

<span data-ttu-id="73a92-129">La `open` direttiva si applica all'intero blocco dello spazio dei nomi all'interno di un file.</span><span class="sxs-lookup"><span data-stu-id="73a92-129">The `open` directive applies to the entire namespace block within a file.</span></span>
<span data-ttu-id="73a92-130">Di conseguenza, se si definisce uno spazio dei nomi aggiuntivo nello stesso Q# file `NS` precedente, le operazioni, le funzioni e i tipi definiti nel secondo spazio dei nomi non avranno accesso a nulla da `Microsoft.Quantum.Intrinsic` o a meno che non siano `Microsoft.Quantum.Math` state ripetute le direttive aperte in esso contenute.</span><span class="sxs-lookup"><span data-stu-id="73a92-130">Hence, if you define an additional namespace in the same Q# file as `NS` earlier, then any operations/functions/types defined in the second namespace would not have access to anything from `Microsoft.Quantum.Intrinsic` or `Microsoft.Quantum.Math` unless you repeated the open directives therein.</span></span> 

<span data-ttu-id="73a92-131">Per fare riferimento a un tipo o chiamabile definito in un altro spazio dei nomi *non* aperto nello spazio dei nomi corrente, è necessario farvi riferimento con il nome completo.</span><span class="sxs-lookup"><span data-stu-id="73a92-131">To reference a type or callable defined in another namespace that is *not* opened in the current namespace, you must reference it by its fully-qualified name.</span></span>
<span data-ttu-id="73a92-132">Ad esempio, data un'operazione denominata `Op` dallo `X.Y` spazio dei nomi:</span><span class="sxs-lookup"><span data-stu-id="73a92-132">For example, given an operation named `Op` from the `X.Y` namespace:</span></span>

* <span data-ttu-id="73a92-133">È necessario farvi riferimento tramite il nome completo, a `X.Y.Op` meno che lo `X.Y` spazio dei nomi non sia stato aperto in precedenza nel blocco corrente.</span><span class="sxs-lookup"><span data-stu-id="73a92-133">You must reference it by its fully-qualified name `X.Y.Op`, unless the `X.Y` namespace has been opened earlier in the current block.</span></span> 
* <span data-ttu-id="73a92-134">Anche se lo `X` spazio dei nomi è aperto, non è possibile fare riferimento all'operazione come `Y.Op` .</span><span class="sxs-lookup"><span data-stu-id="73a92-134">Even if the `X` namespace is opened, it is not possible to reference the operation as `Y.Op`.</span></span>
* <span data-ttu-id="73a92-135">Se è stato definito il nome breve `Z` per `X.Y` nello spazio dei nomi e nel file, è necessario fare riferimento a `Op` `Z.Op` .</span><span class="sxs-lookup"><span data-stu-id="73a92-135">If you defined the short name `Z` for `X.Y` in that namespace and file, you must reference `Op` as `Z.Op`.</span></span> 

<span data-ttu-id="73a92-136">In genere è preferibile includere uno spazio dei nomi utilizzando una `open` direttiva.</span><span class="sxs-lookup"><span data-stu-id="73a92-136">It is usually better to include a namespace by using an `open` directive.</span></span>
<span data-ttu-id="73a92-137">L'utilizzo di un nome completo è obbligatorio se due spazi dei nomi definiscono costrutti con lo stesso nome e l'origine corrente utilizza costrutti di entrambi.</span><span class="sxs-lookup"><span data-stu-id="73a92-137">Using a fully-qualified name is required if two namespaces define constructs with the same name, and the current source uses constructs from both.</span></span>

<span data-ttu-id="73a92-138">Q# segue le stesse regole per la denominazione di altri linguaggi .NET.</span><span class="sxs-lookup"><span data-stu-id="73a92-138">Q# follows the same rules for naming as other .NET languages.</span></span>
<span data-ttu-id="73a92-139">Tuttavia, non Q# supporta riferimenti relativi agli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="73a92-139">However, Q# does not support relative references to namespaces.</span></span>
<span data-ttu-id="73a92-140">Ad esempio, se lo spazio dei nomi `a.b` è aperto, un riferimento a un'operazione denominata non viene `c.d` risolto in un'operazione con nome completo *not* `a.b.c.d` .</span><span class="sxs-lookup"><span data-stu-id="73a92-140">For example, if the namespace `a.b` is open, a reference to an operation named `c.d` does *not* resolve to an operation with full name `a.b.c.d`.</span></span>

## <a name="formatting"></a><span data-ttu-id="73a92-141">Formattazione</span><span class="sxs-lookup"><span data-stu-id="73a92-141">Formatting</span></span>

<span data-ttu-id="73a92-142">La maggior parte delle Q# istruzioni e delle direttive termina con un punto e virgola di terminazione `;` .</span><span class="sxs-lookup"><span data-stu-id="73a92-142">Most Q# statements and directives end with a terminating semicolon, `;`.</span></span>
<span data-ttu-id="73a92-143">Le istruzioni e le dichiarazioni come `for` e `operation` che terminano con un blocco di istruzioni (vedere la sezione seguente) non richiedono un punto e virgola di terminazione.</span><span class="sxs-lookup"><span data-stu-id="73a92-143">Statements and declarations such as `for` and `operation` that end with a statement block (see the following section) do not require a terminating semicolon.</span></span>
<span data-ttu-id="73a92-144">Ogni descrizione dell'istruzione indica se il punto e virgola di terminazione è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="73a92-144">Each statement description notes whether the terminating semicolon is required.</span></span>

<span data-ttu-id="73a92-145">Le istruzioni, come espressioni, dichiarazioni e direttive, possono essere suddivise in più righe.</span><span class="sxs-lookup"><span data-stu-id="73a92-145">Statements, like expressions, declarations, and directives, can be broken out across multiple lines.</span></span>
<span data-ttu-id="73a92-146">Evitare di inserire più istruzioni su una sola riga.</span><span class="sxs-lookup"><span data-stu-id="73a92-146">Avoid putting multiple statements on a single line.</span></span>

## <a name="statement-blocks"></a><span data-ttu-id="73a92-147">Blocchi di istruzioni</span><span class="sxs-lookup"><span data-stu-id="73a92-147">Statement Blocks</span></span>

<span data-ttu-id="73a92-148">Q# le istruzioni sono raggruppate in blocchi di istruzioni, che sono racchiusi tra parentesi graffe `{ }` .</span><span class="sxs-lookup"><span data-stu-id="73a92-148">Q# statements are grouped into statement blocks, which are contained with braces `{ }`.</span></span> <span data-ttu-id="73a92-149">Un blocco di istruzioni inizia con un'apertura `{` e termina con una chiusura `}` .</span><span class="sxs-lookup"><span data-stu-id="73a92-149">A statement block starts with an opening `{` and ends with a closing `}`.</span></span>

<span data-ttu-id="73a92-150">Un blocco di istruzioni racchiuso in modo lessicale all'interno di un altro blocco viene considerato un sottoblocco del blocco contenitore; gli elementi e i sottoblocchi sono denominati anche blocchi esterni e interni.</span><span class="sxs-lookup"><span data-stu-id="73a92-150">A statement block that is lexically enclosed within another block is considered to be a sub-block of the containing block; containing and sub-blocks are also called outer and inner blocks.</span></span>

## <a name="comments"></a><span data-ttu-id="73a92-151">Commenti</span><span class="sxs-lookup"><span data-stu-id="73a92-151">Comments</span></span>

<span data-ttu-id="73a92-152">I commenti iniziano con due barre, `//` , e continuano fino alla fine della riga.</span><span class="sxs-lookup"><span data-stu-id="73a92-152">Comments begin with two forward slashes, `//`, and continue until the end of the line.</span></span>
<span data-ttu-id="73a92-153">Un commento può essere visualizzato in qualsiasi punto di un Q# file di origine.</span><span class="sxs-lookup"><span data-stu-id="73a92-153">A comment can appear anywhere in a Q# source file.</span></span>

## <a name="documentation-comments"></a><span data-ttu-id="73a92-154">Commenti sulla documentazione</span><span class="sxs-lookup"><span data-stu-id="73a92-154">Documentation Comments</span></span>

<span data-ttu-id="73a92-155">I commenti che iniziano con tre barre, `///` , vengono trattati in modo speciale dal compilatore quando appaiono immediatamente prima di uno spazio dei nomi, un'operazione, una specializzazione, una funzione o una definizione di tipo.</span><span class="sxs-lookup"><span data-stu-id="73a92-155">Comments that begin with three forward slashes, `///`, are treated specially by the compiler when they appear immediately before a namespace, operation, specialization, function, or type definition.</span></span>
<span data-ttu-id="73a92-156">In tal caso, il compilatore li considera come la documentazione per il tipo definito chiamabile o definito dall'utente, come per gli altri linguaggi .NET.</span><span class="sxs-lookup"><span data-stu-id="73a92-156">In that case, the compiler treats them as documentation for the defined callable or user-defined type, the same as other .NET languages.</span></span>

<span data-ttu-id="73a92-157">All'interno `///` dei commenti, il testo da visualizzare come parte della documentazione dell'API è formattato come [Markdown](https://daringfireball.net/projects/markdown/syntax), con diverse parti della documentazione indicata da intestazioni con nome specifico.</span><span class="sxs-lookup"><span data-stu-id="73a92-157">Within `///` comments, text to appear as a part of API documentation is formatted as [Markdown](https://daringfireball.net/projects/markdown/syntax), with different parts of the documentation indicated by specially-named headers.</span></span>
<span data-ttu-id="73a92-158">In Markdown, utilizzare l' `@"<ref target>"` estensione per le operazioni di riferimento incrociato, le funzioni e i tipi definiti dall'utente in Q# .</span><span class="sxs-lookup"><span data-stu-id="73a92-158">In Markdown, use the `@"<ref target>"` extension to cross-reference operations, functions, and user-defined types in Q#.</span></span> <span data-ttu-id="73a92-159">Sostituire `<ref target>` con il nome completo dell'oggetto di codice a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="73a92-159">Replace `<ref target>` with the fully qualified name of the referenced code object.</span></span>
<span data-ttu-id="73a92-160">Diversi motori di documentazione possono supportare anche estensioni Markdown aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="73a92-160">Different documentation engines may also support additional Markdown extensions.</span></span>

<span data-ttu-id="73a92-161">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="73a92-161">For example:</span></span>

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

<span data-ttu-id="73a92-162">I nomi seguenti sono validi come intestazioni di commento della documentazione.</span><span class="sxs-lookup"><span data-stu-id="73a92-162">The following names are valid as documentation comment headers.</span></span>

- <span data-ttu-id="73a92-163">**Riepilogo**: breve riepilogo del comportamento di una funzione o di un'operazione o dello scopo di un tipo.</span><span class="sxs-lookup"><span data-stu-id="73a92-163">**Summary**: A short summary of the behavior of a function or operation, or the purpose of a type.</span></span> <span data-ttu-id="73a92-164">Il primo paragrafo del riepilogo viene usato per le informazioni sul passaggio del mouse.</span><span class="sxs-lookup"><span data-stu-id="73a92-164">The first paragraph of the summary is used for hover information.</span></span> <span data-ttu-id="73a92-165">Dovrebbe essere testo normale.</span><span class="sxs-lookup"><span data-stu-id="73a92-165">It should be plain text.</span></span>
- <span data-ttu-id="73a92-166">**Descrizione**: Descrizione del comportamento di una funzione o di un'operazione o dello scopo di un tipo.</span><span class="sxs-lookup"><span data-stu-id="73a92-166">**Description**: A description of the behavior of a function or operation, or the purpose of a type.</span></span> <span data-ttu-id="73a92-167">Insieme, il riepilogo e la descrizione formano il file di documentazione generato per la funzione, l'operazione o il tipo.</span><span class="sxs-lookup"><span data-stu-id="73a92-167">Together, the summary and description form the generated documentation file for the function, operation, or type.</span></span>
  <span data-ttu-id="73a92-168">La descrizione supporta simboli e equazioni in-line in formato LaTeX.</span><span class="sxs-lookup"><span data-stu-id="73a92-168">The description supports in-line LaTeX-formatted symbols and equations.</span></span>
- <span data-ttu-id="73a92-169">**Input**: Descrizione della tupla di input per un'operazione o una funzione.</span><span class="sxs-lookup"><span data-stu-id="73a92-169">**Input**: A description of the input tuple for an operation or function.</span></span>
  <span data-ttu-id="73a92-170">Può contenere sottosezioni Markdown aggiuntive che indicano ogni elemento della tupla di input.</span><span class="sxs-lookup"><span data-stu-id="73a92-170">Can contain additional Markdown subsections indicating each element of the input tuple.</span></span>
- <span data-ttu-id="73a92-171">**Output**: Descrizione della tupla restituita da un'operazione o da una funzione.</span><span class="sxs-lookup"><span data-stu-id="73a92-171">**Output**: A description of the tuple returned by an operation or function.</span></span>
- <span data-ttu-id="73a92-172">**Parametri di tipo**: una sezione vuota che contiene una sottosezione aggiuntiva per ogni parametro di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="73a92-172">**Type Parameters**: An empty section that contains one additional subsection for each generic type parameter.</span></span>
- <span data-ttu-id="73a92-173">**Esempio**: un breve esempio dell'operazione, della funzione o del tipo in uso.</span><span class="sxs-lookup"><span data-stu-id="73a92-173">**Example**: A short example of the operation, function, or type in use.</span></span>
- <span data-ttu-id="73a92-174">**Note**: prosa Miscellanea che descrive alcuni aspetti dell'operazione, della funzione o del tipo.</span><span class="sxs-lookup"><span data-stu-id="73a92-174">**Remarks**: Miscellaneous prose describing some aspect of the operation, function, or type.</span></span>
- <span data-ttu-id="73a92-175">**Vedere anche**: elenco di nomi completi che indicano funzioni correlate, operazioni o tipi definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="73a92-175">**See Also**: A list of fully qualified names indicating related functions, operations, or user-defined types.</span></span>
- <span data-ttu-id="73a92-176">**Riferimenti**: un elenco di riferimenti e citazioni per l'elemento documentato.</span><span class="sxs-lookup"><span data-stu-id="73a92-176">**References**: A list of references and citations for the documented item.</span></span>

## <a name="next-steps"></a><span data-ttu-id="73a92-177">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="73a92-177">Next steps</span></span>

<span data-ttu-id="73a92-178">Informazioni sulle [operazioni e sulle funzioni](xref:microsoft.quantum.guide.operationsfunctions) in Q# .</span><span class="sxs-lookup"><span data-stu-id="73a92-178">Learn about [Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions) in Q#.</span></span>