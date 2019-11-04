---
title: Struttura di file | Microsoft Docs
description: 'Struttura del file Q #'
author: QuantumWriter
uid: microsoft.quantum.language.file-structure
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 40b2e7ddf5def6285250dffe130b152429dce1f8
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185189"
---
# <a name="file-structure"></a><span data-ttu-id="73102-103">Struttura file</span><span class="sxs-lookup"><span data-stu-id="73102-103">File Structure</span></span>

<span data-ttu-id="73102-104">Un file Q # è costituito da una sequenza di dichiarazioni dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="73102-104">A Q# file consists of a sequence of namespace declarations.</span></span>
<span data-ttu-id="73102-105">Ogni dichiarazione dello spazio dei nomi contiene dichiarazioni per i tipi, le operazioni e le funzioni definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="73102-105">Each namespace declaration contains declarations for user-defined types, operations, and functions.</span></span>
<span data-ttu-id="73102-106">Una dichiarazione dello spazio dei nomi può contenere un numero qualsiasi di ogni tipo di dichiarazione e in qualsiasi ordine.</span><span class="sxs-lookup"><span data-stu-id="73102-106">A namespace declaration may contain any number of each type of declaration, and in any order.</span></span>
<span data-ttu-id="73102-107">L'unico testo che può essere visualizzato al di fuori di una dichiarazione dello spazio dei nomi è comment.</span><span class="sxs-lookup"><span data-stu-id="73102-107">The only text that can appear outside of a namespace declaration is comments.</span></span>
<span data-ttu-id="73102-108">In particolare, i commenti relativi alla documentazione per uno spazio dei nomi precedono la dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="73102-108">In particular, documentation comments for a namespace precede the declaration.</span></span>

## <a name="namespace-declarations"></a><span data-ttu-id="73102-109">Dichiarazioni dello spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="73102-109">Namespace Declarations</span></span>

<span data-ttu-id="73102-110">Un file Q # includerà in genere una sola dichiarazione dello spazio dei nomi, ma potrebbe avere nessuna (ed essere vuota o contenere solo commenti) oppure può contenere più spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="73102-110">A Q# file will typically have exactly one namespace declaration, but may have none (and be empty or just contain comments) or may contain multiple namespaces.</span></span>
<span data-ttu-id="73102-111">Le dichiarazioni dello spazio dei nomi non possono essere nidificate.</span><span class="sxs-lookup"><span data-stu-id="73102-111">Namespace declarations may not be nested.</span></span>

<span data-ttu-id="73102-112">Lo stesso spazio dei nomi può essere dichiarato in più file Q # compilati insieme, purché non esistano dichiarazioni di tipo, operazione o funzione con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="73102-112">The same namespace may be declared in multiple Q# files that are compiled together, as long as there are no type, operation, or function declarations with the same name.</span></span>
<span data-ttu-id="73102-113">In particolare, non è valido definire lo stesso tipo nello stesso spazio dei nomi in più file, anche se le dichiarazioni sono identiche.</span><span class="sxs-lookup"><span data-stu-id="73102-113">In particular, it is invalid to define the same type in the same namespace in multiple files, even if the declarations are identical.</span></span>

<span data-ttu-id="73102-114">Una dichiarazione dello spazio dei nomi è costituita dalla parola chiave `namespace`, seguita dal nome dello spazio dei nomi, da una parentesi graffa aperta `{`, dalle dichiarazioni contenute nello spazio dei nomi e da una parentesi graffa di chiusura `}`.</span><span class="sxs-lookup"><span data-stu-id="73102-114">A namespace declaration consists of the keyword `namespace`, followed by the name of the namespace, an open brace `{`, the declarations contained in the namespace, and a close brace `}`.</span></span>
<span data-ttu-id="73102-115">I nomi degli spazi dei nomi seguono il modello .NET di una sequenza di uno o più simboli validi separati da punti `.`.</span><span class="sxs-lookup"><span data-stu-id="73102-115">Namespace names follow the .NET pattern of a sequence of one or more legal symbols separated by periods `.`.</span></span>
<span data-ttu-id="73102-116">Ad esempio, `MyQuantumStuff` e `Microsoft.Quantum.Canon` sono nomi di spazio dei nomi validi.</span><span class="sxs-lookup"><span data-stu-id="73102-116">For instance, `MyQuantumStuff` and `Microsoft.Quantum.Canon` are valid namespace names.</span></span>
<span data-ttu-id="73102-117">Per convenzione, i simboli in un nome di spazio dei nomi sono in maiuscolo, ma ciò non è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="73102-117">By convention, the symbols in a namespace name are capitalized, but this is not required.</span></span>

<span data-ttu-id="73102-118">Le dichiarazioni possono essere visualizzate in qualsiasi ordine in una dichiarazione dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="73102-118">Declarations may appear in any order in a namespace declaration.</span></span>
<span data-ttu-id="73102-119">I riferimenti a tipi o chiamabili dichiarati più in basso in un file vengono risolti correttamente; non è necessario che il tipo, l'operazione o la dichiarazione di funzione precedano un riferimento ad esso.</span><span class="sxs-lookup"><span data-stu-id="73102-119">References to types or callables declared further down in a file are resolved properly; there is no need for the type, operation, or function declaration to precede a reference to it.</span></span>

## <a name="open-directives"></a><span data-ttu-id="73102-120">Direttive Open</span><span class="sxs-lookup"><span data-stu-id="73102-120">Open Directives</span></span>

<span data-ttu-id="73102-121">All'interno di un blocco dello spazio dei nomi, è possibile usare la direttiva `open` per importare tutti i tipi e le chiamabili definiti in un determinato spazio dei nomi e farvi riferimento in base al nome non qualificato.</span><span class="sxs-lookup"><span data-stu-id="73102-121">Within a namespace block, the `open` directive may be used to import all types and callables defined in a certain namespace and refer to them by their unqualified name.</span></span> 

<span data-ttu-id="73102-122">Una direttiva di questo tipo `open` è costituita dalla parola chiave `open`, seguita dallo spazio dei nomi da aprire e da un punto e virgola di terminazione.</span><span class="sxs-lookup"><span data-stu-id="73102-122">Such an `open` directive consists of the `open` keyword, followed by the namespace to be opened and a terminating semicolon.</span></span>

<span data-ttu-id="73102-123">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="73102-123">For instance,</span></span>

```qsharp
open Microsoft.Quantum.Canon;
```

<span data-ttu-id="73102-124">Facoltativamente, è possibile definire un nome breve per lo spazio dei nomi aperto in modo che tutti gli elementi di tale spazio dei nomi possano (e devono) essere qualificati dal nome breve definito.</span><span class="sxs-lookup"><span data-stu-id="73102-124">Optionally, a short name for the opened namespace may be defined such that all elements from that namespace can (and need) to be qualified by the defined short name.</span></span> <span data-ttu-id="73102-125">Tale nome breve viene definito aggiungendo la parola chiave `as` seguito dal nome breve desiderato prima del punto e virgola in una direttiva `open`:</span><span class="sxs-lookup"><span data-stu-id="73102-125">Such a short name is defined by adding the keyword `as` followed by the desired short name before the semicolon in an `open` directive:</span></span>

```qsharp
open Microsoft.Quantum.Math as Math;
```

<span data-ttu-id="73102-126">Tutte le direttive di `open` devono essere visualizzate prima di qualsiasi dichiarazione di `function`, `operation`o `newtype` nel blocco dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="73102-126">All `open` directives must appear before any `function`, `operation`, or `newtype` declarations in the namespace block.</span></span>
<span data-ttu-id="73102-127">La direttiva `open` si applica all'intero blocco dello spazio dei nomi all'interno di un file.</span><span class="sxs-lookup"><span data-stu-id="73102-127">The `open` directive applies to the entire namespace block within a file.</span></span>

## <a name="user-defined-type-declarations"></a><span data-ttu-id="73102-128">Dichiarazioni di tipi definiti dall'utente</span><span class="sxs-lookup"><span data-stu-id="73102-128">User-Defined Type Declarations</span></span>

<span data-ttu-id="73102-129">Q # consente agli utenti di dichiarare nuovi tipi definiti dall'utente, come descritto nella sezione modello di [tipo q #](xref:microsoft.quantum.language.type-model) .</span><span class="sxs-lookup"><span data-stu-id="73102-129">Q# provides a way for users to declare new user-defined types, as described in the [Q# type model](xref:microsoft.quantum.language.type-model) section.</span></span>
<span data-ttu-id="73102-130">I tipi definiti dall'utente sono distinti anche se i tipi di base sono identici.</span><span class="sxs-lookup"><span data-stu-id="73102-130">User-defined types are distinct even if the base types are identical.</span></span>
<span data-ttu-id="73102-131">In particolare, non viene eseguita alcuna conversione automatica tra i valori di due tipi definiti dall'utente, anche se i tipi sottostanti sono identici.</span><span class="sxs-lookup"><span data-stu-id="73102-131">In particular, there is no automatic conversion between values of two user-defined types even if the underlying types are identical.</span></span>

<span data-ttu-id="73102-132">Una dichiarazione di tipo definito dall'utente è costituita dalla parola chiave `newtype`, seguita dal nome del tipo definito dall'utente, da un `=`, da una specifica del tipo valida e da un punto e virgola di terminazione.</span><span class="sxs-lookup"><span data-stu-id="73102-132">A user-defined type declaration consists of the keyword `newtype`, followed by the name of the user-defined type, an `=`, a valid type specification, and a terminating semicolon.</span></span>

<span data-ttu-id="73102-133">ad esempio:</span><span class="sxs-lookup"><span data-stu-id="73102-133">For example:</span></span>

```qsharp
newtype PairOfInts = (Int, Int);
```

<span data-ttu-id="73102-134">Ogni file di origine Q # può dichiarare un numero qualsiasi di tipi definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="73102-134">Each Q# source file may declare any number of user-defined types.</span></span>
<span data-ttu-id="73102-135">I nomi dei tipi devono essere univoci all'interno di uno spazio dei nomi e non possono entrare in conflitto con i nomi di funzione e</span><span class="sxs-lookup"><span data-stu-id="73102-135">Type names must be unique within a namespace and may not conflict with operation and function names.</span></span>

<span data-ttu-id="73102-136">Non è possibile definire dipendenze circolari tra tipi definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="73102-136">It is not possible to define circular dependencies between user defined types.</span></span> <span data-ttu-id="73102-137">I tipi ricorsivi non sono pertanto possibili entro Q #.</span><span class="sxs-lookup"><span data-stu-id="73102-137">Recursive types are thus not possible within Q#.</span></span>

## <a name="operation-declarations"></a><span data-ttu-id="73102-138">Dichiarazioni di operazione</span><span class="sxs-lookup"><span data-stu-id="73102-138">Operation Declarations</span></span>

<span data-ttu-id="73102-139">Le operazioni sono il nucleo di Q #, approssimativamente analogo alle funzioni in altri linguaggi.</span><span class="sxs-lookup"><span data-stu-id="73102-139">Operations are the core of Q#, roughly analogous to functions in other languages.</span></span>
<span data-ttu-id="73102-140">Ogni file di origine Q # può definire un numero qualsiasi di operazioni.</span><span class="sxs-lookup"><span data-stu-id="73102-140">Each Q# source file may define any number of operations.</span></span>

<span data-ttu-id="73102-141">I nomi delle operazioni devono essere univoci all'interno di uno spazio dei nomi e non possono entrare in conflitto con i nomi dei tipi e</span><span class="sxs-lookup"><span data-stu-id="73102-141">Operation names must be unique within a namespace and may not conflict with type and function names.</span></span>

<span data-ttu-id="73102-142">Una dichiarazione di operazione è costituita dalla parola chiave `operation`, seguita dal simbolo che rappresenta il nome dell'operazione, una tupla di identificatori tipizzati che definisce gli argomenti per l'operazione, due punti `:`, un'annotazione di tipo che descrive il tipo di risultato dell'operazione. Facoltativamente, un'annotazione con le caratteristiche dell'operazione, una parentesi graffa aperta `{`, il corpo della dichiarazione dell'operazione e una parentesi graffa di chiusura finale `}`.</span><span class="sxs-lookup"><span data-stu-id="73102-142">An operation declarations consists of the keyword `operation`, followed by the symbol that is the operation’s name, a typed identifier tuple that defines the arguments to the operation, a colon `:`, a type annotation that describes the operation’s result type, optionally an annotation with the operation characteristics, an open brace `{`, the body of the operation declaration, and a final closing brace `}`.</span></span>

<span data-ttu-id="73102-143">Il corpo della dichiarazione dell'operazione è costituito dall'implementazione predefinita o da un elenco di specializzazioni.</span><span class="sxs-lookup"><span data-stu-id="73102-143">The body of the operation declaration either consists of the default implementation or of a list of specializations.</span></span>
<span data-ttu-id="73102-144">L'implementazione predefinita può essere specificata direttamente nella dichiarazione se è necessario specificare in modo esplicito solo l'implementazione della specializzazione del corpo predefinita.</span><span class="sxs-lookup"><span data-stu-id="73102-144">The default implementation can be specified directly within the declaration if only the implementation of the default body specialization needs to specified explicitly.</span></span>
<span data-ttu-id="73102-145">In questo caso, un'annotazione con le caratteristiche dell'operazione nella dichiarazione è utile per garantire che il compilatore generi automaticamente altre specializzazioni in base all'implementazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="73102-145">In this case, an annotation with the operation characteristics in the declaration is useful to ensure that the compiler auto-generates other specializations based on the default implementation.</span></span> 

<span data-ttu-id="73102-146">Ad esempio</span><span class="sxs-lookup"><span data-stu-id="73102-146">For example</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

<span data-ttu-id="73102-147">Le caratteristiche dell'operazione definiscono i tipi di funtori che possono essere applicati all'operazione dichiarata e l'effetto che hanno.</span><span class="sxs-lookup"><span data-stu-id="73102-147">Operation characteristics define what kinds of functors can be applied to the declared operation, and what effect they have.</span></span> <span data-ttu-id="73102-148">Se un'operazione implementa una trasformazione unitaria, è possibile definire il modo in cui l'operazione agisce quando *adjointed* o *controllata*.</span><span class="sxs-lookup"><span data-stu-id="73102-148">If an operation implements a unitary transformation, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span>
<span data-ttu-id="73102-149">L'esistenza di queste specializzazioni può essere dichiarata come parte della firma dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="73102-149">The existence of these specializations can be declared as part of the operation signature.</span></span> <span data-ttu-id="73102-150">L'implementazione corrispondente per ogni specializzazione dichiarata in modo implicito viene quindi generata dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="73102-150">The corresponding implementation for each such implicitly declared specialization is then generated by the compiler.</span></span> <span data-ttu-id="73102-151">Nell'esempio precedente, un oggetto adiacente, un controllo e una specializzazione contigua controllata vengono generati dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="73102-151">In the example above, an adjoint, a controlled, and a controlled adjoint specialization are generated by the compiler.</span></span> 

<span data-ttu-id="73102-152">Nel caso in cui l'implementazione non possa essere generata dal compilatore, può essere specificata in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="73102-152">In the case where the implementation cannot be generated by the compiler, it can be explicitly specified.</span></span> <span data-ttu-id="73102-153">Tali dichiarazioni di specializzazione esplicita possono essere costituite da una direttiva di generazione adatta che chiarisce come deve essere compilata una determinata specializzazione o da un'implementazione definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="73102-153">Such explicit specialization declarations can either consist of a suitable generation directive that clarify how a certain specialization is to be built, or a user defined implementation.</span></span> <span data-ttu-id="73102-154">Il codice nell'`PrepareEntangledPair` precedente, ad esempio, equivale al codice riportato di seguito contenente dichiarazioni di specializzazione esplicite:</span><span class="sxs-lookup"><span data-stu-id="73102-154">The code in `PrepareEntangledPair` above for example is equivalent to the code below containing explicit specialization declarations:</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
<span data-ttu-id="73102-155">La parola chiave `auto` indica che il compilatore deve determinare come generare l'implementazione della specializzazione.</span><span class="sxs-lookup"><span data-stu-id="73102-155">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>
<span data-ttu-id="73102-156">Se il compilatore non è in grado di generare l'implementazione per una determinata specializzazione senza altre istruzioni, ad esempio una direttiva di generazione più precisa, oppure se è possibile fornire un'implementazione più efficiente, l'implementazione può anche essere definita manualmente.</span><span class="sxs-lookup"><span data-stu-id="73102-156">If the compiler cannot generate the implementation for a certain specialization without further instructions - like a more precise generation directive -, or if a more efficient implementation can be given, then the implementation may also be manually defined.</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```

<span data-ttu-id="73102-157">Nell'esempio precedente, `adjoint invert;` indica che la specializzazione contigua deve essere generata invertendo l'implementazione del corpo e `controlled adjoint invert;` indica che la specializzazione contigua controllata deve essere generata invertendo l'implementazione specificata di. specializzazione controllata.</span><span class="sxs-lookup"><span data-stu-id="73102-157">In the example above, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="73102-158">Per eseguire un'operazione per supportare l'applicazione del `Adjoint` e/o `Controlled` functor, è necessario `Unit`il tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="73102-158">For an operation to support application of the `Adjoint` and/or `Controlled` functor, its return type necessarily needs to be `Unit`.</span></span> 


### <a name="explicit-specialization-declarations"></a><span data-ttu-id="73102-159">Dichiarazioni di specializzazione esplicite</span><span class="sxs-lookup"><span data-stu-id="73102-159">Explicit Specialization Declarations</span></span>

<span data-ttu-id="73102-160">Le operazioni Q # possono contenere le seguenti dichiarazioni di specializzazione esplicite:</span><span class="sxs-lookup"><span data-stu-id="73102-160">Q# operations may contain the following explicit specialization declarations:</span></span>

- <span data-ttu-id="73102-161">La specializzazione `body` specifica l'implementazione dell'operazione senza funtori applicata.</span><span class="sxs-lookup"><span data-stu-id="73102-161">The `body` specialization specifies the implementation of the operation with no functors applied.</span></span>
- <span data-ttu-id="73102-162">La specializzazione `adjoint` specifica l'implementazione dell'operazione con l'`Adjoint` functor applicato.</span><span class="sxs-lookup"><span data-stu-id="73102-162">The `adjoint` specialization specifies the implementation of the operation with the `Adjoint` functor applied.</span></span>
- <span data-ttu-id="73102-163">La specializzazione `controlled` specifica l'implementazione dell'operazione con l'`Controlled` functor applicato.</span><span class="sxs-lookup"><span data-stu-id="73102-163">The `controlled` specialization specifies the implementation of the operation with the `Controlled` functor applied.</span></span>
- <span data-ttu-id="73102-164">La specializzazione `controlled adjoint` specifica l'implementazione dell'operazione con la `Adjoint` e `Controlled` funtori applicati.</span><span class="sxs-lookup"><span data-stu-id="73102-164">The `controlled adjoint` specialization specifies the implementation of the operation with both the `Adjoint` and `Controlled` functors applied.</span></span>
  <span data-ttu-id="73102-165">Questa specializzazione può anche essere denominata `adjoint controlled`, dal momento che i due funtori del commutatore.</span><span class="sxs-lookup"><span data-stu-id="73102-165">This specialization can also be named `adjoint controlled`, since the two functors commute.</span></span>


<span data-ttu-id="73102-166">Una specializzazione di operazione è costituita dal tag di specializzazione, ad esempio `body`o `adjoint`e così via, seguito da uno dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="73102-166">An operation specialization consists of the specialization tag (like e.g. `body`, or `adjoint`, etc.) followed by one of:</span></span>

- <span data-ttu-id="73102-167">Dichiarazione esplicita, come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="73102-167">An explicit declaration as described below.</span></span>
- <span data-ttu-id="73102-168">Direttiva che indica al compilatore come generare la specializzazione, una tra le seguenti:</span><span class="sxs-lookup"><span data-stu-id="73102-168">A directive that tells the compiler how to generate the specialization, one of:</span></span>
  - <span data-ttu-id="73102-169">`intrinsic`, che indica che la specializzazione viene fornita dal computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="73102-169">`intrinsic`, which indicates that the specialization is provided by the target machine.</span></span>
  - <span data-ttu-id="73102-170">`distribute`, che può essere usato con le specializzazioni `controlled` e `controlled adjoint`.</span><span class="sxs-lookup"><span data-stu-id="73102-170">`distribute`, which may be used with the `controlled` and `controlled adjoint` specializations.</span></span>
    <span data-ttu-id="73102-171">Quando viene usato con `controlled`, indica che il compilatore deve calcolare la specializzazione applicando `Controlled` a tutte le operazioni nella `body`.</span><span class="sxs-lookup"><span data-stu-id="73102-171">When used with `controlled`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `body`.</span></span>
    <span data-ttu-id="73102-172">Se usato con `controlled adjoint`, indica che il compilatore deve calcolare la specializzazione applicando `Controlled` a tutte le operazioni nella specializzazione `adjoint`.</span><span class="sxs-lookup"><span data-stu-id="73102-172">When used with `controlled adjoint`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `adjoint` specialization.</span></span>
  - <span data-ttu-id="73102-173">`invert`, che indica che il compilatore deve calcolare la specializzazione del `adjoint` invertendo la `body`, ovvero invertendo l'ordine delle operazioni e applicando il contiguo a ognuna.</span><span class="sxs-lookup"><span data-stu-id="73102-173">`invert`, which indicates that the compiler should compute the `adjoint` specialization by inverting the `body`, i.e. reversing the order of operations and applying the adjoint to each one.</span></span>
    <span data-ttu-id="73102-174">Se usato con `adjoint controlled`, indica che il compilatore deve calcolare la specializzazione invertendo la specializzazione `controlled`.</span><span class="sxs-lookup"><span data-stu-id="73102-174">When used with `adjoint controlled`, this indicates that the compiler should compute the specialization by inverting the `controlled` specialization.</span></span>
  - <span data-ttu-id="73102-175">`self`, per indicare che la specializzazione contigua è uguale alla specializzazione `body`.</span><span class="sxs-lookup"><span data-stu-id="73102-175">`self`, to indicate that the adjoint specialization is the the same as the `body` specialization.</span></span>
    <span data-ttu-id="73102-176">Questa operazione è valida per le specializzazioni `adjoint` e `adjoint controlled`.</span><span class="sxs-lookup"><span data-stu-id="73102-176">This is legal for the `adjoint` and `adjoint controlled` specializations.</span></span>
    <span data-ttu-id="73102-177">Per `adjoint controlled`, `self` implica che la specializzazione del `adjoint controlled` è uguale alla specializzazione `controlled`.</span><span class="sxs-lookup"><span data-stu-id="73102-177">For `adjoint controlled`, `self` implies that the `adjoint controlled` specialization is the same as the `controlled` specialization.</span></span>
  - <span data-ttu-id="73102-178">`auto`, per indicare che il compilatore deve selezionare una direttiva appropriata da applicare.</span><span class="sxs-lookup"><span data-stu-id="73102-178">`auto`, to indicate that the compiler should select an appropriate directive to apply.</span></span>
    <span data-ttu-id="73102-179">non è possibile usare `auto` per la specializzazione `body`.</span><span class="sxs-lookup"><span data-stu-id="73102-179">`auto` may not be used for the `body` specialization.</span></span>

<span data-ttu-id="73102-180">Per le direttive e `auto` è necessario un punto e virgola `;`di chiusura.</span><span class="sxs-lookup"><span data-stu-id="73102-180">The directives and `auto` all require a closing semi-colon `;`.</span></span>
<span data-ttu-id="73102-181">La direttiva `auto` viene risolta nella direttiva di generazione seguente se viene fornita una dichiarazione esplicita del `body`:</span><span class="sxs-lookup"><span data-stu-id="73102-181">The `auto` directive resolves to the following generation directive if an explicit declaration of the `body` is provided:</span></span>

- <span data-ttu-id="73102-182">La specializzazione del `adjoint` viene generata in base alla `invert`della direttiva.</span><span class="sxs-lookup"><span data-stu-id="73102-182">The `adjoint` specialization is generated according to the directive `invert`.</span></span>
- <span data-ttu-id="73102-183">La specializzazione del `controlled` viene generata in base alla `distribute`della direttiva.</span><span class="sxs-lookup"><span data-stu-id="73102-183">The `controlled` specialization is generated according to the directive `distribute`.</span></span>
- <span data-ttu-id="73102-184">La specializzazione `adjoint controlled` viene generata in base alla direttiva `invert` se viene fornita una dichiarazione esplicita per `controlled`, ma non una per `adjoint`e `distribute` in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="73102-184">The `adjoint controlled` specialization is generated according to the directive `invert` if an explicit declaration for `controlled` is given but not one for `adjoint`, and `distribute` otherwise.</span></span>

> [!TIP]   
> <span data-ttu-id="73102-185">Se un'operazione è autonoma, specificare in modo esplicito la specializzazione contigua o controllata tramite la direttiva di generazione `self` per consentire al compilatore di utilizzare tali informazioni a scopo di ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="73102-185">If an operation is self-adjoint, explicitly specify either the adjoint or the controlled adjoint specialization via the generation directive `self` to allow the compiler to make use of that information for optimization purposes.</span></span>

<span data-ttu-id="73102-186">Una dichiarazione di specializzazione contenente un'implementazione definita dall'utente è costituita da una tupla di argomenti seguita da un blocco di istruzioni con il codice Q # che implementa la specializzazione.</span><span class="sxs-lookup"><span data-stu-id="73102-186">A specialization declaration containing a user defined implementation consists of an argument tuple followed by a statement block with the Q# code that implements the specialization.</span></span>
<span data-ttu-id="73102-187">Nell'elenco di argomenti, `...` viene usato per rappresentare gli argomenti dichiarati per l'intera operazione.</span><span class="sxs-lookup"><span data-stu-id="73102-187">In the argument list, `...` is used to represent the arguments declared for the operation as a whole.</span></span>
<span data-ttu-id="73102-188">Per `body` e `adjoint`, l'elenco di argomenti deve essere sempre `(...)`; per `controlled` e `adjoint controlled`, l'elenco di argomenti deve essere un simbolo che rappresenta la matrice di qubits del controllo, seguito da `...`, racchiuso tra parentesi. ad esempio, `(controls,...)`.</span><span class="sxs-lookup"><span data-stu-id="73102-188">For `body` and `adjoint`, the argument list should always be `(...)`; for `controlled` and `adjoint controlled`, the argument list should be a symbol that represents the array of control qubits, followed by `...`, enclosed in parentheses; for example, `(controls,...)`.</span></span>

<span data-ttu-id="73102-189">Se una o più specializzazioni oltre al corpo predefinito devono essere dichiarate in modo esplicito, l'implementazione del corpo predefinito deve essere racchiusa anche in una dichiarazione di specializzazione adatta:</span><span class="sxs-lookup"><span data-stu-id="73102-189">If one or more specializations besides the default body need to be explicitly declared, then the implementation for the default body needs to be wrapped into a suitable specialization declaration as well:</span></span>

```qsharp
operation CountOnes(qs: Qubit[]) : Int {

    body (...) // default body specialization
    {
        mutable n = 0;
        for (q in qs) {
            set n += M(q) == One ? 1 | 0;
        }
        return n;
    }

    ...
```

### <a name="adjoint"></a><span data-ttu-id="73102-190">Adjoint</span><span class="sxs-lookup"><span data-stu-id="73102-190">Adjoint</span></span>

<span data-ttu-id="73102-191">Il contiguo di un'operazione specifica il modo in cui viene implementata la trasponente del coniugato complesso dell'operazione, ovvero il modo in cui l'operazione agisce quando viene eseguita in ordine inverso.</span><span class="sxs-lookup"><span data-stu-id="73102-191">The adjoint of an operation specifies how the complex conjugate transpose of the operation is implemented, i.e. how the operation acts when "run in reverse".</span></span>
<span data-ttu-id="73102-192">È lecito specificare un'operazione senza contiguo; ad esempio, le operazioni di misurazione non hanno elementi contigui perché non sono invertibili.</span><span class="sxs-lookup"><span data-stu-id="73102-192">It is legal to specify an operation with no adjoint; for instance, measurement operations have no adjoint because they are not invertible.</span></span>
<span data-ttu-id="73102-193">Un'operazione supporta il `Adjoint` functor se la relativa dichiarazione contiene una dichiarazione implicita o esplicita di una specializzazione contigua.</span><span class="sxs-lookup"><span data-stu-id="73102-193">An operation supports the `Adjoint` functor if its declaration contains an implicit or explicit declaration of an adjoint specialization.</span></span>
<span data-ttu-id="73102-194">Una specializzazione contigua controllata dichiarata in modo esplicito implica l'esistenza di una specializzazione contigua.</span><span class="sxs-lookup"><span data-stu-id="73102-194">An explicitly declared controlled adjoint specialization implies the existence of an adjoint specialization.</span></span> 

<span data-ttu-id="73102-195">Per l'operazione il cui corpo contiene cicli repeat-until-Success, istruzioni set, misure, istruzioni return o chiamate ad altre operazioni che non supportano il `Adjoint` functor, la generazione automatica di una specializzazione contigua dopo l'`invert` o @no__ la direttiva t_2_ non è possibile.</span><span class="sxs-lookup"><span data-stu-id="73102-195">For operation whose body contains repeat-until-success loops, set statements, measurements, return statements, or calls to other operations that do not support the `Adjoint` functor, auto-generating an adjoint specialization following the `invert` or `auto` directive is not possible.</span></span>

### <a name="controlled"></a><span data-ttu-id="73102-196">Controllato</span><span class="sxs-lookup"><span data-stu-id="73102-196">Controlled</span></span>

<span data-ttu-id="73102-197">La versione controllata di un'operazione specifica il modo in cui viene implementata una versione controllata da Quantum dell'operazione, ovvero il modo in cui un'operazione viene applicata quando viene applicato lo stato di un registro quantico.</span><span class="sxs-lookup"><span data-stu-id="73102-197">The controlled version of an operation specifies how a quantum-controlled version of the operation is implemented, i.e. how an operation acts when applied conditioned on the state of a quantum register.</span></span>
<span data-ttu-id="73102-198">Una descrizione più completa viene fornita nella sezione [controllata](xref:microsoft.quantum.language.type-model#controlled) .</span><span class="sxs-lookup"><span data-stu-id="73102-198">A more complete description is provided in the [Controlled](xref:microsoft.quantum.language.type-model#controlled) section.</span></span>

<span data-ttu-id="73102-199">È lecito specificare un'operazione senza una versione controllata. ad esempio, le operazioni di misurazione non hanno una versione controllata perché non sono controllabili.</span><span class="sxs-lookup"><span data-stu-id="73102-199">It is legal to specify an operation with no controlled version; for instance, measurement operations have no controlled version because they are not controllable.</span></span>
<span data-ttu-id="73102-200">Un'operazione supporta il `Controlled` functor solo se la relativa dichiarazione contiene una dichiarazione implicita o esplicita di una specializzazione controllata.</span><span class="sxs-lookup"><span data-stu-id="73102-200">An operation supports the `Controlled` functor if and only if its declaration contains an implicit or explicit declaration of a controlled specialization.</span></span>
<span data-ttu-id="73102-201">Una specializzazione sottoposta a controllo dichiarata in modo esplicito implica l'esistenza di una specializzazione controllata.</span><span class="sxs-lookup"><span data-stu-id="73102-201">An explicitly declared controlled adjoint specialization implies the existence of a controlled specialization.</span></span> 

<span data-ttu-id="73102-202">Per un'operazione il cui corpo contiene chiamate ad altre operazioni che non supportano il `Controlled` functor, la generazione automatica di una specializzazione controllata che segue la direttiva `distribute` o `auto` non è possibile.</span><span class="sxs-lookup"><span data-stu-id="73102-202">For an operation whose body contains calls to other operations that does not support the `Controlled` functor, auto-generating a controlled specialization following the `distribute` or `auto` directive is not possible.</span></span>

### <a name="controlled-adjoint"></a><span data-ttu-id="73102-203">Contiguo controllato</span><span class="sxs-lookup"><span data-stu-id="73102-203">Controlled Adjoint</span></span>

<span data-ttu-id="73102-204">La versione controllata contigua di un'operazione specifica il modo in cui viene implementata una versione controllata da Quantum del contiguo dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="73102-204">The controlled adjoint version of an operation specifies how a quantum-controlled version of the adjoint of the operation is implemented.</span></span>
<span data-ttu-id="73102-205">È lecito specificare un'operazione senza una versione controllata contigua. ad esempio, le operazioni di misurazione non hanno una versione controllata contigua, perché non sono controllabili né invertibili.</span><span class="sxs-lookup"><span data-stu-id="73102-205">It is legal to specify an operation with no controlled adjoint version; for instance, measurement operations have no controlled adjoint version because they are neither controllable nor invertible.</span></span>

<span data-ttu-id="73102-206">Una specializzazione contigua controllata per un'operazione deve esistere solo se sono presenti sia una specializzazione contigua che una specializzazione controllata.</span><span class="sxs-lookup"><span data-stu-id="73102-206">A controlled adjoint specialization for an operation needs to exist if and only if both an adjoint and a controlled specialization exist.</span></span> <span data-ttu-id="73102-207">In tal caso, viene dedotta l'esistenza della specializzazione contigua controllata e una specializzazione appropriata viene generata dal compilatore se nessuna implementazione è stata definita in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="73102-207">In that case, the existence of the controlled adjoint specialization is inferred and an appropriate specialization is generated by the compiler if no implementation has been defined explicitly.</span></span> 

<span data-ttu-id="73102-208">Per un'operazione il cui corpo contiene chiamate ad altre operazioni che non dispongono di una versione controllata contigua, la generazione automatica di una specializzazione contigua dopo la `invert`, `distribute` o `auto` direttiva non è possibile.</span><span class="sxs-lookup"><span data-stu-id="73102-208">For an operation whose body contains calls to other operations that do not have a controlled adjoint version, auto-generating an adjoint specialization following the `invert`, `distribute` or `auto` directive is not possible.</span></span>


### <a name="examples"></a><span data-ttu-id="73102-209">esempi</span><span class="sxs-lookup"><span data-stu-id="73102-209">Examples</span></span>

<span data-ttu-id="73102-210">Una dichiarazione di operazione potrebbe essere semplice come la seguente, che definisce l'operazione di Pauli X primitiva:</span><span class="sxs-lookup"><span data-stu-id="73102-210">An operation declaration might be as simple as the following, which defines the primitive Pauli X operation:</span></span>

```qsharp
operation X (q : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```

<span data-ttu-id="73102-211">Di seguito viene definita l'operazione Teleport.</span><span class="sxs-lookup"><span data-stu-id="73102-211">The following defines the teleport operation.</span></span>

```qsharp
// Entangle two qubits.
// Assumes that both qubits are in the |0> state.
operation EPR (q1 : Qubit, q2 : Qubit) : Unit 
is Adj + Ctl {
    H(q2);
    CNOT(q2, q1);
}

// Teleport the quantum state of the source to the target.
// Assumes that the target is in the |0> state.
operation Teleport (source : Qubit, target : Qubit) : Unit {

    // Get a temporary for the Bell pair
    using (ancilla = Qubit())
    {
        // Create a Bell pair between the temporary and the target
        EPR(target, ancilla);

        // Do the teleportation
        Adjoint EPR (ancilla, source);

        if (MResetZ(source) == One) {
            X(target);
        }
        if (MResetZ(ancilla) == One) {
            Z(target);
        }
    }
}
```

## <a name="function-declarations"></a><span data-ttu-id="73102-212">Dichiarazioni di funzione</span><span class="sxs-lookup"><span data-stu-id="73102-212">Function Declarations</span></span>

<span data-ttu-id="73102-213">Le funzioni sono routine puramente classiche in Q #.</span><span class="sxs-lookup"><span data-stu-id="73102-213">Functions are purely classical routines in Q#.</span></span>
<span data-ttu-id="73102-214">Ogni file di origine Q # può definire un numero qualsiasi di funzioni.</span><span class="sxs-lookup"><span data-stu-id="73102-214">Each Q# source file may define any number of functions.</span></span>

<span data-ttu-id="73102-215">Una dichiarazione di funzione è costituita dalla parola chiave `function`, seguita dal simbolo che rappresenta il nome della funzione, da una tupla identificatore tipizzata, da un'annotazione di tipo che descrive il tipo restituito della funzione e da un blocco di istruzioni che descrive l'implementazione del funzione.</span><span class="sxs-lookup"><span data-stu-id="73102-215">A function declaration consists of the keyword `function`, followed by the symbol that is the function’s name, a typed identifier tuple, a type annotation that describes the function's return type, and a statement block that describes the implementation of the function.</span></span>

<span data-ttu-id="73102-216">Il blocco di istruzioni che definisce una funzione deve essere racchiuso tra `{` e `}` come qualsiasi altro blocco di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="73102-216">The statement block defining a function must be enclosed in `{` and `}` like any other statement block.</span></span>

<span data-ttu-id="73102-217">I nomi di funzione devono essere univoci all'interno di uno spazio dei nomi e non possono entrare in conflitto con i nomi di operazione e</span><span class="sxs-lookup"><span data-stu-id="73102-217">Function names must be unique within a namespace and may not conflict with operation and type names.</span></span>
<span data-ttu-id="73102-218">Le funzioni non possono allocare o prendere in prestito qubits o chiamare operazioni.</span><span class="sxs-lookup"><span data-stu-id="73102-218">Functions may not allocate or borrow qubits, or call operations.</span></span> <span data-ttu-id="73102-219">L'applicazione parziale di operazioni o il passaggio di valori tipizzati dell'operazione è un'operazione soddisfacente.</span><span class="sxs-lookup"><span data-stu-id="73102-219">Partial application of operations or passing around operation typed values is fine.</span></span>

<span data-ttu-id="73102-220">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="73102-220">For example,</span></span>

```qsharp
function DotProduct(a : Double[], b : Double[]) : Double {
    if (Length(a) != Length(b)) {
        fail "Arrays are not compatible";
    }

    mutable accum = 0.0;
    for (i in 0..Length(a)-1) {
        set accum += a[i] * b[i];
    }
    return accum;
}
```
