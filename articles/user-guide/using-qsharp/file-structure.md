---
title: 'Struttura del file Q #'
description: 'Descrive la struttura e la sintassi di un file Q #.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
ms.openlocfilehash: b8c24dae6cc8d8f37ad4f1f74017c05cabe3a4b4
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327459"
---
# <a name="q-file-structure"></a>Struttura del file Q #

Ogni operazione Q #, funzione e tipo definito dall'utente viene definita all'interno di uno spazio dei nomi.

Un file Q # è costituito da una sequenza di *dichiarazioni dello spazio dei nomi*.
Ogni dichiarazione dello spazio dei nomi contiene dichiarazioni per i tipi, le operazioni e le funzioni definiti dall'utente.
Una dichiarazione dello spazio dei nomi può contenere un numero qualsiasi di ogni tipo di dichiarazione e in qualsiasi ordine.
Per ulteriori informazioni sulla dichiarazione di tipi, [operazioni](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)e [funzioni](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions) [definiti dall'utente](xref:microsoft.quantum.guide.types#user-defined-types)all'interno di uno spazio dei nomi, attenersi ai collegamenti seguenti.

L'unico testo che può essere visualizzato al di fuori di una dichiarazione dello spazio dei nomi è comment.
In particolare, i commenti relativi alla documentazione (altri dettagli di seguito) per uno spazio dei nomi precedono la dichiarazione.

## <a name="namespace-declarations"></a>Dichiarazioni dello spazio dei nomi

Un file Q # includerà in genere una sola dichiarazione dello spazio dei nomi, ma potrebbe avere nessuna (ed essere vuota o contenere solo commenti) oppure può contenere più spazi dei nomi.
Le dichiarazioni dello spazio dei nomi non possono essere nidificate.

Lo stesso spazio dei nomi può essere dichiarato in più file Q # compilati insieme, purché non esistano dichiarazioni di tipo, operazione o funzione con lo stesso nome.
In particolare, non è valido definire lo stesso tipo nello stesso spazio dei nomi in più file, anche se le dichiarazioni sono identiche.

Una dichiarazione dello spazio dei nomi è costituita dalla parola chiave `namespace` , seguita dal nome dello spazio dei nomi, da una parentesi graffa aperta `{` , dalle dichiarazioni contenute nello spazio dei nomi e da una parentesi graffa di chiusura `}` .
I nomi degli spazi dei nomi seguono il modello .NET di una sequenza di uno o più simboli validi separati da punti `.` .
Ad esempio, `MyQuantumStuff` e `Microsoft.Quantum.Intrinsic` sono nomi di spazio dei nomi validi.
Per convenzione, i simboli in un nome di spazio dei nomi sono in maiuscolo, ma ciò non è obbligatorio.

I riferimenti a tipi o chiamabili dichiarati più in basso in un file vengono risolti correttamente; non è necessario che il tipo, l'operazione o la dichiarazione di funzione precedano un riferimento ad esso.

## <a name="open-directives"></a>Direttive Open

All'interno di un blocco dello spazio dei nomi, `open` è possibile usare la direttiva per importare tutti i tipi e le chiamabili dichiarati in un determinato spazio dei nomi e farvi riferimento in base al nome non qualificato.
Tale `open` direttiva è costituita dalla `open` parola chiave, seguita dallo spazio dei nomi da aprire e da un punto e virgola di terminazione.

> [!NOTE] 
> Tutte le `open` direttive devono essere visualizzate `function` prima `operation` di qualsiasi dichiarazione, o `newtype` nel blocco dello spazio dei nomi.

Facoltativamente, è possibile definire un nome breve per lo spazio dei nomi aperto in modo che tutti gli elementi di tale spazio dei nomi possano (e devono) essere qualificati dal nome breve definito. Ad esempio, date le seguenti dichiarazioni dello spazio dei nomi e le direttive Open,

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

Se un'operazione dichiarata usa un'operazione `Op` da `Microsoft.Quantum.Intrinsic` , è possibile chiamarla semplicemente usando `Op` .
Tuttavia, se si vuole chiamare una determinata funzione `Fn` da `Microsoft.Quantum.Math` , è necessario chiamarla usando `Math.Fn` .

La `open` direttiva si applica all'intero blocco dello spazio dei nomi all'interno di un file.
Di conseguenza, se si definisce uno spazio dei nomi aggiuntivo nello stesso file Q # come `NS` indicato in precedenza, qualsiasi operazione/funzione/tipo definito nel secondo spazio dei nomi non avrà accesso a nulla da `Microsoft.Quantum.Intrinsic` o a `Microsoft.Quantum.Math` meno che non vengano ripetute le direttive aperte in esso contenute. 

Il nome completo di un tipo o di una chiamabile definito in un altro spazio dei nomi *non* aperto nello spazio dei nomi corrente deve essere usato come riferimento.
Ad esempio, è necessario fare riferimento a un'operazione denominata `Op` dallo `X.Y` spazio dei nomi con il nome completo `X.Y.Op` , a meno che `X.Y` lo spazio dei nomi non sia stato aperto in precedenza nel blocco corrente. Come indicato in precedenza, anche se lo `X` spazio dei nomi è stato aperto, non è possibile fare riferimento all'operazione come `Y.Op` .
Se un nome breve `Z` per `X.Y` è stato definito nello spazio dei nomi e nel file, `Op` deve essere indicato come `Z.Op` . 

In genere è preferibile includere uno spazio dei nomi utilizzando una `open` direttiva.
L'utilizzo di un nome completo è obbligatorio se due spazi dei nomi definiscono costrutti con lo stesso nome e l'origine corrente utilizza costrutti di entrambi.

Q # segue le stesse regole per la denominazione degli altri linguaggi .NET.
Tuttavia, Q # non supporta riferimenti relativi agli spazi dei nomi.
Ovvero, se lo spazio dei nomi `a.b` è stato aperto, un riferimento a un'operazione `c.d` denominata *non* verrà risolto in un'operazione con nome completo `a.b.c.d` .

## <a name="formatting"></a>Formattazione

La maggior parte delle istruzioni e le direttive Q # terminano con un punto e virgola di terminazione `;` .
Le istruzioni e le dichiarazioni come `for` e `operation` che terminano con un blocco di istruzioni (vedere di seguito) non richiedono un punto e virgola di terminazione.
Ogni descrizione dell'istruzione indica se il punto e virgola di terminazione è obbligatorio.

Le istruzioni, come espressioni, dichiarazioni e direttive, possono essere suddivise in più righe.
Evitare di avere più istruzioni su una sola riga.

## <a name="statement-blocks"></a>Blocchi di istruzioni

Le istruzioni Q # sono raggruppate in blocchi di istruzioni.
Un blocco di istruzioni inizia con un'apertura `{` e termina con una chiusura `}` .

Un blocco di istruzioni racchiuso in modo lessicale all'interno di un altro blocco viene considerato un sottoblocco del blocco contenitore; gli elementi e i sottoblocchi sono denominati anche blocchi esterni e interni.

## <a name="comments"></a>Commenti

I commenti iniziano con due barre, `//` , e continuano fino alla fine della riga.
Un commento può essere visualizzato in qualsiasi punto di un file di origine Q #.

## <a name="documentation-comments"></a>Commenti sulla documentazione

I commenti che iniziano con tre barre, `///` , vengono trattati in modo speciale dal compilatore quando appaiono immediatamente prima di uno spazio dei nomi, un'operazione, una specializzazione, una funzione o una definizione di tipo.
In tal caso, il contenuto viene considerato come documentazione per il tipo definito chiamabile o definito dall'utente, come per altri linguaggi .NET.

All'interno `///` dei commenti, il testo da visualizzare come parte della documentazione dell'API è formattato come [Markdown](https://daringfireball.net/projects/markdown/syntax), con diverse parti della documentazione indicate da intestazioni con nome specifico.
Come estensione di Markdown, è possibile includere riferimenti incrociati a operazioni, funzioni e tipi definiti dall'utente in Q # usando `@"<ref target>"` , dove `<ref target>` viene sostituito dal nome completo dell'oggetto di codice a cui si fa riferimento.
Facoltativamente, un motore di documentazione può supportare anche estensioni Markdown aggiuntive.

Ad esempio:

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

I nomi seguenti sono riconosciuti come intestazioni di commento della documentazione.

- **Riepilogo**: breve riepilogo del comportamento di una funzione o di un'operazione o dello scopo di un tipo. Il primo paragrafo del riepilogo viene usato per le informazioni sul passaggio del mouse. Dovrebbe essere testo normale.
- **Descrizione**: Descrizione del comportamento di una funzione o di un'operazione o dello scopo di un tipo. Il riepilogo e la descrizione vengono concatenati per formare il file di documentazione generato per la funzione, l'operazione o il tipo.
  La descrizione può contenere simboli e equazioni inline in formato LaTeX.
- **Input**: Descrizione della tupla di input per un'operazione o una funzione.
  Può contenere sottosezioni Markdown aggiuntive che indicano ogni singolo elemento della tupla di input.
- **Output**: Descrizione della tupla restituita da un'operazione o da una funzione.
- **Parametri di tipo**: una sezione vuota contenente una sottosezione aggiuntiva per ogni parametro di tipo generico.
- **Esempio**: un breve esempio dell'operazione, della funzione o del tipo in uso.
- **Note**: prosa Miscellanea che descrive alcuni aspetti dell'operazione, della funzione o del tipo.
- **Vedere anche**: elenco di nomi completi che indicano funzioni correlate, operazioni o tipi definiti dall'utente.
- **Riferimenti**: un elenco di riferimenti e citazioni per l'elemento da documentare.

## <a name="next-steps"></a>Passaggi successivi

Informazioni sulle [operazioni e sulle funzioni](xref:microsoft.quantum.guide.operationsfunctions) in Q #.