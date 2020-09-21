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
# <a name="no-locq-file-structure"></a>Q# Struttura di file

Un Q# file è costituito da una sequenza di *dichiarazioni dello spazio dei nomi*.
Ogni dichiarazione dello spazio dei nomi contiene dichiarazioni per tipi, operazioni e funzioni definiti dall'utente e può contenere un numero qualsiasi di ogni tipo di dichiarazione e in qualsiasi ordine.
Per altre informazioni sulle dichiarazioni all'interno di uno spazio dei nomi, vedere [tipi definiti dall'utente](xref:microsoft.quantum.guide.types#user-defined-types), [operazioni](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)e [funzioni](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions).

L'unico testo che può essere visualizzato al di fuori di una dichiarazione dello spazio dei nomi è comment.
In particolare, i commenti relativi alla documentazione per uno spazio dei nomi precedono la dichiarazione. Per ulteriori informazioni, vedere la [documentazione relativa ai commenti](#documentation-comments) in questo articolo. 

## <a name="namespace-declarations"></a>Dichiarazioni dello spazio dei nomi

Un Q# file ha in genere una sola dichiarazione dello spazio dei nomi, ma potrebbe avere nessuna (ed essere vuota o contenere solo commenti) o contenere più spazi dei nomi.
Non è possibile nidificare le dichiarazioni dello spazio dei nomi.

È possibile dichiarare lo stesso spazio dei nomi in più Q# file compilati insieme, purché non esistano dichiarazioni di tipo, operazione o funzione con lo stesso nome.
In particolare, non è valido definire lo stesso tipo nello stesso spazio dei nomi in più file, anche se le dichiarazioni sono identiche.

Una dichiarazione dello spazio dei nomi è costituita dalla parola chiave `namespace` , seguita dal nome dello spazio dei nomi e dalle dichiarazioni contenute nello spazio dei nomi racchiuso tra parentesi graffe `{ }` .
I nomi degli spazi dei nomi seguono il modello .NET di una sequenza di uno o più simboli validi separati da punti `.` .
Ad esempio, `MyQuantumStuff` e `Microsoft.Quantum.Intrinsic` sono nomi di spazio dei nomi validi.
Per convenzione, è tuttavia necessario capitalizzare i simboli in un nome di spazio dei nomi.

I riferimenti a tipi o chiamabili dichiarati più in basso in un file vengono risolti correttamente; non è necessario che il tipo, l'operazione o la dichiarazione di funzione precedano un riferimento ad esso.

## <a name="open-directives"></a>Direttive Open

All'interno di un blocco dello spazio dei nomi, utilizzare la `open` direttiva per importare tutti i tipi e le chiamabili dichiarati in un determinato spazio dei nomi e farvi riferimento in base al nome non qualificato.
Tale `open` direttiva è costituita dalla `open` parola chiave, seguita dallo spazio dei nomi da aprire e da un punto e virgola di terminazione.

> [!NOTE] 
> Tutte le `open` direttive devono essere visualizzate `function` prima `operation` di qualsiasi dichiarazione, o `newtype` nel blocco dello spazio dei nomi.

Facoltativamente, è possibile definire un nome breve per lo spazio dei nomi aperto. Se viene definito un nome breve, è necessario qualificare tutti gli elementi da tale spazio dei nomi in base al nome breve definito. Ad esempio, date le seguenti dichiarazioni dello spazio dei nomi e le direttive Open,

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

Se un'operazione dichiarata utilizza un'operazione `Op` da `Microsoft.Quantum.Intrinsic` , è possibile chiamarla semplicemente utilizzando `Op` .
Tuttavia, per chiamare una determinata funzione `Fn` da `Microsoft.Quantum.Math` , è necessario chiamarla usando `Math.Fn` .

La `open` direttiva si applica all'intero blocco dello spazio dei nomi all'interno di un file.
Di conseguenza, se si definisce uno spazio dei nomi aggiuntivo nello stesso Q# file `NS` precedente, le operazioni, le funzioni e i tipi definiti nel secondo spazio dei nomi non avranno accesso a nulla da `Microsoft.Quantum.Intrinsic` o a meno che non siano `Microsoft.Quantum.Math` state ripetute le direttive aperte in esso contenute. 

Per fare riferimento a un tipo o chiamabile definito in un altro spazio dei nomi *non* aperto nello spazio dei nomi corrente, è necessario farvi riferimento con il nome completo.
Ad esempio, data un'operazione denominata `Op` dallo `X.Y` spazio dei nomi:

* È necessario farvi riferimento tramite il nome completo, a `X.Y.Op` meno che lo `X.Y` spazio dei nomi non sia stato aperto in precedenza nel blocco corrente. 
* Anche se lo `X` spazio dei nomi è aperto, non è possibile fare riferimento all'operazione come `Y.Op` .
* Se è stato definito il nome breve `Z` per `X.Y` nello spazio dei nomi e nel file, è necessario fare riferimento a `Op` `Z.Op` . 

In genere è preferibile includere uno spazio dei nomi utilizzando una `open` direttiva.
L'utilizzo di un nome completo è obbligatorio se due spazi dei nomi definiscono costrutti con lo stesso nome e l'origine corrente utilizza costrutti di entrambi.

Q# segue le stesse regole per la denominazione di altri linguaggi .NET.
Tuttavia, non Q# supporta riferimenti relativi agli spazi dei nomi.
Ad esempio, se lo spazio dei nomi `a.b` è aperto, un riferimento a un'operazione denominata non viene `c.d` risolto in un'operazione con nome completo *not* `a.b.c.d` .

## <a name="formatting"></a>Formattazione

La maggior parte delle Q# istruzioni e delle direttive termina con un punto e virgola di terminazione `;` .
Le istruzioni e le dichiarazioni come `for` e `operation` che terminano con un blocco di istruzioni (vedere la sezione seguente) non richiedono un punto e virgola di terminazione.
Ogni descrizione dell'istruzione indica se il punto e virgola di terminazione è obbligatorio.

Le istruzioni, come espressioni, dichiarazioni e direttive, possono essere suddivise in più righe.
Evitare di inserire più istruzioni su una sola riga.

## <a name="statement-blocks"></a>Blocchi di istruzioni

Q# le istruzioni sono raggruppate in blocchi di istruzioni, che sono racchiusi tra parentesi graffe `{ }` . Un blocco di istruzioni inizia con un'apertura `{` e termina con una chiusura `}` .

Un blocco di istruzioni racchiuso in modo lessicale all'interno di un altro blocco viene considerato un sottoblocco del blocco contenitore; gli elementi e i sottoblocchi sono denominati anche blocchi esterni e interni.

## <a name="comments"></a>Commenti

I commenti iniziano con due barre, `//` , e continuano fino alla fine della riga.
Un commento può essere visualizzato in qualsiasi punto di un Q# file di origine.

## <a name="documentation-comments"></a>Commenti sulla documentazione

I commenti che iniziano con tre barre, `///` , vengono trattati in modo speciale dal compilatore quando appaiono immediatamente prima di uno spazio dei nomi, un'operazione, una specializzazione, una funzione o una definizione di tipo.
In tal caso, il compilatore li considera come la documentazione per il tipo definito chiamabile o definito dall'utente, come per gli altri linguaggi .NET.

All'interno `///` dei commenti, il testo da visualizzare come parte della documentazione dell'API è formattato come [Markdown](https://daringfireball.net/projects/markdown/syntax), con diverse parti della documentazione indicata da intestazioni con nome specifico.
In Markdown, utilizzare l' `@"<ref target>"` estensione per le operazioni di riferimento incrociato, le funzioni e i tipi definiti dall'utente in Q# . Sostituire `<ref target>` con il nome completo dell'oggetto di codice a cui si fa riferimento.
Diversi motori di documentazione possono supportare anche estensioni Markdown aggiuntive.

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

I nomi seguenti sono validi come intestazioni di commento della documentazione.

- **Riepilogo**: breve riepilogo del comportamento di una funzione o di un'operazione o dello scopo di un tipo. Il primo paragrafo del riepilogo viene usato per le informazioni sul passaggio del mouse. Dovrebbe essere testo normale.
- **Descrizione**: Descrizione del comportamento di una funzione o di un'operazione o dello scopo di un tipo. Insieme, il riepilogo e la descrizione formano il file di documentazione generato per la funzione, l'operazione o il tipo.
  La descrizione supporta simboli e equazioni in-line in formato LaTeX.
- **Input**: Descrizione della tupla di input per un'operazione o una funzione.
  Può contenere sottosezioni Markdown aggiuntive che indicano ogni elemento della tupla di input.
- **Output**: Descrizione della tupla restituita da un'operazione o da una funzione.
- **Parametri di tipo**: una sezione vuota che contiene una sottosezione aggiuntiva per ogni parametro di tipo generico.
- **Esempio**: un breve esempio dell'operazione, della funzione o del tipo in uso.
- **Note**: prosa Miscellanea che descrive alcuni aspetti dell'operazione, della funzione o del tipo.
- **Vedere anche**: elenco di nomi completi che indicano funzioni correlate, operazioni o tipi definiti dall'utente.
- **Riferimenti**: un elenco di riferimenti e citazioni per l'elemento documentato.

## <a name="next-steps"></a>Passaggi successivi

Informazioni sulle [operazioni e sulle funzioni](xref:microsoft.quantum.guide.operationsfunctions) in Q# .