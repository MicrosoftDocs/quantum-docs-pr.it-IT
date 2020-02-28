---
title: 'Struttura del file Q #'
description: "Informazioni su come strutturare spazi dei nomi, operazioni, funzioni e dichiarazioni di tipo definito dall'utente in programmi e librerie Q #."
author: QuantumWriter
uid: microsoft.quantum.language.file-structure
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: b4bb7d4d70677dbd5d921a9f68313760499a56a1
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907393"
---
# <a name="file-structure"></a>Struttura di Archiviazione file

Un file Q # è costituito da una sequenza di dichiarazioni dello spazio dei nomi.
Ogni dichiarazione dello spazio dei nomi contiene dichiarazioni per i tipi, le operazioni e le funzioni definiti dall'utente.
Una dichiarazione dello spazio dei nomi può contenere un numero qualsiasi di ogni tipo di dichiarazione e in qualsiasi ordine.
L'unico testo che può essere visualizzato al di fuori di una dichiarazione dello spazio dei nomi è comment.
In particolare, i commenti relativi alla documentazione per uno spazio dei nomi precedono la dichiarazione.

## <a name="namespace-declarations"></a>Dichiarazioni dello spazio dei nomi

Un file Q # includerà in genere una sola dichiarazione dello spazio dei nomi, ma potrebbe avere nessuna (ed essere vuota o contenere solo commenti) oppure può contenere più spazi dei nomi.
Le dichiarazioni dello spazio dei nomi non possono essere nidificate.

Lo stesso spazio dei nomi può essere dichiarato in più file Q # compilati insieme, purché non esistano dichiarazioni di tipo, operazione o funzione con lo stesso nome.
In particolare, non è valido definire lo stesso tipo nello stesso spazio dei nomi in più file, anche se le dichiarazioni sono identiche.

Una dichiarazione dello spazio dei nomi è costituita dalla parola chiave `namespace`, seguita dal nome dello spazio dei nomi, da una parentesi graffa aperta `{`, dalle dichiarazioni contenute nello spazio dei nomi e da una parentesi graffa di chiusura `}`.
I nomi degli spazi dei nomi seguono il modello .NET di una sequenza di uno o più simboli validi separati da punti `.`.
Ad esempio, `MyQuantumStuff` e `Microsoft.Quantum.Canon` sono nomi di spazio dei nomi validi.
Per convenzione, i simboli in un nome di spazio dei nomi sono in maiuscolo, ma ciò non è obbligatorio.

Le dichiarazioni possono essere visualizzate in qualsiasi ordine in una dichiarazione dello spazio dei nomi.
I riferimenti a tipi o chiamabili dichiarati più in basso in un file vengono risolti correttamente; non è necessario che il tipo, l'operazione o la dichiarazione di funzione precedano un riferimento ad esso.

## <a name="open-directives"></a>Direttive Open

All'interno di un blocco dello spazio dei nomi, è possibile usare la direttiva `open` per importare tutti i tipi e le chiamabili definiti in un determinato spazio dei nomi e farvi riferimento in base al nome non qualificato. 

Una direttiva di questo tipo `open` è costituita dalla parola chiave `open`, seguita dallo spazio dei nomi da aprire e da un punto e virgola di terminazione.

Ad esempio,

```qsharp
open Microsoft.Quantum.Canon;
```

Facoltativamente, è possibile definire un nome breve per lo spazio dei nomi aperto in modo che tutti gli elementi di tale spazio dei nomi possano (e devono) essere qualificati dal nome breve definito. Tale nome breve viene definito aggiungendo la parola chiave `as` seguito dal nome breve desiderato prima del punto e virgola in una direttiva `open`:

```qsharp
open Microsoft.Quantum.Math as Math;
```

Tutte le direttive di `open` devono essere visualizzate prima di qualsiasi dichiarazione di `function`, `operation`o `newtype` nel blocco dello spazio dei nomi.
La direttiva `open` si applica all'intero blocco dello spazio dei nomi all'interno di un file.

## <a name="user-defined-type-declarations"></a>Dichiarazioni di tipi definiti dall'utente

Q # consente agli utenti di dichiarare nuovi tipi definiti dall'utente, come descritto nella sezione modello di [tipo q #](xref:microsoft.quantum.language.type-model) .
I tipi definiti dall'utente sono distinti anche se i tipi di base sono identici.
In particolare, non viene eseguita alcuna conversione automatica tra i valori di due tipi definiti dall'utente, anche se i tipi sottostanti sono identici.

Una dichiarazione di tipo definito dall'utente è costituita dalla parola chiave `newtype`, seguita dal nome del tipo definito dall'utente, da un `=`, da una specifica del tipo valida e da un punto e virgola di terminazione.

Ad esempio,

```qsharp
newtype PairOfInts = (Int, Int);
```

Ogni file di origine Q # può dichiarare un numero qualsiasi di tipi definiti dall'utente.
I nomi dei tipi devono essere univoci all'interno di uno spazio dei nomi e non possono entrare in conflitto con i nomi di funzione e

Non è possibile definire dipendenze circolari tra tipi definiti dall'utente. I tipi ricorsivi non sono pertanto possibili entro Q #.

## <a name="operation-declarations"></a>Dichiarazioni di operazione

Le operazioni sono il nucleo di Q #, approssimativamente analogo alle funzioni in altri linguaggi.
Ogni file di origine Q # può definire un numero qualsiasi di operazioni.

I nomi delle operazioni devono essere univoci all'interno di uno spazio dei nomi e non possono entrare in conflitto con i nomi dei tipi e

Una dichiarazione di operazione è costituita dalla parola chiave `operation`, seguita dal simbolo che rappresenta il nome dell'operazione, una tupla di identificatori tipizzati che definisce gli argomenti per l'operazione, due punti `:`, un'annotazione di tipo che descrive il tipo di risultato dell'operazione, facoltativamente un'annotazione con le caratteristiche dell'operazione, una parentesi graffa di apertura `{`, il corpo della `}`dichiarazione

Il corpo della dichiarazione dell'operazione è costituito dall'implementazione predefinita o da un elenco di specializzazioni.
L'implementazione predefinita può essere specificata direttamente nella dichiarazione se è necessario specificare in modo esplicito solo l'implementazione della specializzazione del corpo predefinita.
In questo caso, un'annotazione con le caratteristiche dell'operazione nella dichiarazione è utile per garantire che il compilatore generi automaticamente altre specializzazioni in base all'implementazione predefinita. 

Ad esempio: 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

Le caratteristiche dell'operazione definiscono i tipi di funtori che possono essere applicati all'operazione dichiarata e l'effetto che hanno. Se un'operazione implementa una trasformazione unitaria, è possibile definire il modo in cui l'operazione agisce quando *adjointed* o *controllata*.
L'esistenza di queste specializzazioni può essere dichiarata come parte della firma dell'operazione. L'implementazione corrispondente per ogni specializzazione dichiarata in modo implicito viene quindi generata dal compilatore. Nell'esempio precedente, un oggetto adiacente, un controllo e una specializzazione contigua controllata vengono generati dal compilatore. 

Nel caso in cui l'implementazione non possa essere generata dal compilatore, può essere specificata in modo esplicito. Tali dichiarazioni di specializzazione esplicita possono essere costituite da una direttiva di generazione adatta che chiarisce come deve essere compilata una determinata specializzazione o da un'implementazione definita dall'utente. Il codice nell'`PrepareEntangledPair` precedente, ad esempio, equivale al codice riportato di seguito contenente dichiarazioni di specializzazione esplicite: 

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
La parola chiave `auto` indica che il compilatore deve determinare come generare l'implementazione della specializzazione.
Se il compilatore non è in grado di generare l'implementazione per una determinata specializzazione senza altre istruzioni, ad esempio una direttiva di generazione più precisa, oppure se è possibile fornire un'implementazione più efficiente, l'implementazione può anche essere definita manualmente.

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

Nell'esempio precedente, `adjoint invert;` indica che la specializzazione contigua deve essere generata invertendo l'implementazione del corpo e `controlled adjoint invert;` indica che la specializzazione contigua controllata deve essere generata invertendo l'implementazione specificata della specializzazione controllata.

Per eseguire un'operazione per supportare l'applicazione del `Adjoint` e/o `Controlled` functor, è necessario `Unit`il tipo restituito. 


### <a name="explicit-specialization-declarations"></a>Dichiarazioni di specializzazione esplicite

Le operazioni Q # possono contenere le seguenti dichiarazioni di specializzazione esplicite:

- La specializzazione `body` specifica l'implementazione dell'operazione senza funtori applicata.
- La specializzazione `adjoint` specifica l'implementazione dell'operazione con l'`Adjoint` functor applicato.
- La specializzazione `controlled` specifica l'implementazione dell'operazione con l'`Controlled` functor applicato.
- La specializzazione `controlled adjoint` specifica l'implementazione dell'operazione con la `Adjoint` e `Controlled` funtori applicati.
  Questa specializzazione può anche essere denominata `adjoint controlled`, dal momento che i due funtori del commutatore.


Una specializzazione di operazione è costituita dal tag di specializzazione, ad esempio `body`o `adjoint`e così via, seguito da uno dei seguenti elementi:

- Dichiarazione esplicita, come descritto di seguito.
- Direttiva che indica al compilatore come generare la specializzazione, una tra le seguenti:
  - `intrinsic`, che indica che la specializzazione viene fornita dal computer di destinazione.
  - `distribute`, che può essere usato con le specializzazioni `controlled` e `controlled adjoint`.
    Quando viene usato con `controlled`, indica che il compilatore deve calcolare la specializzazione applicando `Controlled` a tutte le operazioni nella `body`.
    Se usato con `controlled adjoint`, indica che il compilatore deve calcolare la specializzazione applicando `Controlled` a tutte le operazioni nella specializzazione `adjoint`.
  - `invert`, che indica che il compilatore deve calcolare la specializzazione del `adjoint` invertendo la `body`, ovvero invertendo l'ordine delle operazioni e applicando il contiguo a ognuna.
    Se usato con `adjoint controlled`, indica che il compilatore deve calcolare la specializzazione invertendo la specializzazione `controlled`.
  - `self`, per indicare che la specializzazione contigua è uguale alla specializzazione `body`.
    Questa operazione è valida per le specializzazioni `adjoint` e `adjoint controlled`.
    Per `adjoint controlled`, `self` implica che la specializzazione del `adjoint controlled` è uguale alla specializzazione `controlled`.
  - `auto`, per indicare che il compilatore deve selezionare una direttiva appropriata da applicare.
    non è possibile usare `auto` per la specializzazione `body`.

Per le direttive e `auto` è necessario un punto e virgola `;`di chiusura.
La direttiva `auto` viene risolta nella direttiva di generazione seguente se viene fornita una dichiarazione esplicita del `body`:

- La specializzazione del `adjoint` viene generata in base alla `invert`della direttiva.
- La specializzazione del `controlled` viene generata in base alla `distribute`della direttiva.
- La specializzazione `adjoint controlled` viene generata in base alla direttiva `invert` se viene fornita una dichiarazione esplicita per `controlled`, ma non una per `adjoint`e `distribute` in caso contrario.

> [!TIP]   
> Se un'operazione è autonoma, specificare in modo esplicito la specializzazione contigua o controllata tramite la direttiva di generazione `self` per consentire al compilatore di utilizzare tali informazioni a scopo di ottimizzazione.

Una dichiarazione di specializzazione contenente un'implementazione definita dall'utente è costituita da una tupla di argomenti seguita da un blocco di istruzioni con il codice Q # che implementa la specializzazione.
Nell'elenco di argomenti, `...` viene usato per rappresentare gli argomenti dichiarati per l'intera operazione.
Per `body` e `adjoint`, l'elenco di argomenti deve essere sempre `(...)`; per `controlled` e `adjoint controlled`, l'elenco di argomenti deve essere un simbolo che rappresenta la matrice di qubits del controllo, seguito da `...`, racchiuso tra parentesi. ad esempio, `(controls,...)`.

Se una o più specializzazioni oltre al corpo predefinito devono essere dichiarate in modo esplicito, l'implementazione del corpo predefinito deve essere racchiusa anche in una dichiarazione di specializzazione adatta:

```qsharp
operation CountOnes(qubits: Qubit[]) : Int {

    body (...) // default body specialization
    {
        mutable n = 0;
        for (qubit in qubits) {
            set n += M(q) == One ? 1 | 0;
        }
        return n;
    }

    ...
```

### <a name="adjoint"></a>Adjoint

Il contiguo di un'operazione specifica il modo in cui viene implementata la trasponente del coniugato complesso dell'operazione, ovvero il modo in cui l'operazione agisce quando viene eseguita in ordine inverso.
È lecito specificare un'operazione senza contiguo; ad esempio, le operazioni di misurazione non hanno elementi contigui perché non sono invertibili.
Un'operazione supporta il `Adjoint` functor se la relativa dichiarazione contiene una dichiarazione implicita o esplicita di una specializzazione contigua.
Una specializzazione contigua controllata dichiarata in modo esplicito implica l'esistenza di una specializzazione contigua. 

Per l'operazione il cui corpo contiene cicli repeat-until-Success, istruzioni set, misure, istruzioni return o chiamate ad altre operazioni che non supportano il `Adjoint` functor, la generazione automatica di una specializzazione contigua che segue la direttiva `invert` o `auto` non è possibile.

### <a name="controlled"></a>Controllato

La versione controllata di un'operazione specifica il modo in cui viene implementata una versione controllata da Quantum dell'operazione, ovvero il modo in cui un'operazione viene applicata quando viene applicato lo stato di un registro quantico.
Una descrizione più completa viene fornita nella sezione [controllata](xref:microsoft.quantum.language.type-model#controlled) .

È lecito specificare un'operazione senza una versione controllata. ad esempio, le operazioni di misurazione non hanno una versione controllata perché non sono controllabili.
Un'operazione supporta il `Controlled` functor solo se la relativa dichiarazione contiene una dichiarazione implicita o esplicita di una specializzazione controllata.
Una specializzazione sottoposta a controllo dichiarata in modo esplicito implica l'esistenza di una specializzazione controllata. 

Per un'operazione il cui corpo contiene chiamate ad altre operazioni che non supportano il `Controlled` functor, la generazione automatica di una specializzazione controllata che segue la direttiva `distribute` o `auto` non è possibile.

### <a name="controlled-adjoint"></a>Contiguo controllato

La versione controllata contigua di un'operazione specifica il modo in cui viene implementata una versione controllata da Quantum del contiguo dell'operazione.
È lecito specificare un'operazione senza una versione controllata contigua. ad esempio, le operazioni di misurazione non hanno una versione controllata contigua, perché non sono controllabili né invertibili.

Una specializzazione contigua controllata per un'operazione deve esistere solo se sono presenti sia una specializzazione contigua che una specializzazione controllata. In tal caso, viene dedotta l'esistenza della specializzazione contigua controllata e una specializzazione appropriata viene generata dal compilatore se nessuna implementazione è stata definita in modo esplicito. 

Per un'operazione il cui corpo contiene chiamate ad altre operazioni che non dispongono di una versione controllata contigua, la generazione automatica di una specializzazione contigua dopo la `invert`, `distribute` o `auto` direttiva non è possibile.


### <a name="examples"></a>Esempi

Una dichiarazione di operazione potrebbe essere semplice come la seguente, che definisce l'operazione di Pauli X primitiva:

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```

Di seguito viene definita l'operazione Teleport.

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

## <a name="function-declarations"></a>Dichiarazioni di funzioni

Le funzioni sono routine puramente classiche in Q #.
Ogni file di origine Q # può definire un numero qualsiasi di funzioni.

Una dichiarazione di funzione è costituita dalla parola chiave `function`, seguita dal simbolo che rappresenta il nome della funzione, da una tupla identificatore tipizzata, da un'annotazione di tipo che descrive il tipo restituito della funzione e da un blocco di istruzioni che descrive l'implementazione della funzione.

Il blocco di istruzioni che definisce una funzione deve essere racchiuso tra `{` e `}` come qualsiasi altro blocco di istruzioni.

I nomi di funzione devono essere univoci all'interno di uno spazio dei nomi e non possono entrare in conflitto con i nomi di operazione e
Le funzioni non possono allocare o prendere in prestito qubits o chiamare operazioni. L'applicazione parziale di operazioni o il passaggio di valori tipizzati dell'operazione è un'operazione soddisfacente.

Ad esempio,

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
