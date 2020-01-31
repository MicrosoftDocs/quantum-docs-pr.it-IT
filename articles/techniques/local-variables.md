---
title: 'Variabili locali-tecniche Q # | Microsoft Docs'
description: 'Variabili locali-tecniche Q #'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.local-variables
ms.openlocfilehash: 8b1de5c096210fb36a81c127a8bbbe1b39522741
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820182"
---
# <a name="local-variables"></a>Variabili locali #

Un valore di qualsiasi tipo in Q # può essere assegnato a una variabile per il riutilizzo all'interno di un'operazione o funzione tramite la parola chiave `let`.
Ad esempio:

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

Questa operazione assegna una matrice specifica di operatori Pauli a una variabile denominata `measurementOperator`.

> [!TIP]
> Si noti che non è stato necessario specificare in modo esplicito il tipo della nuova variabile, poiché l'espressione a destra dell'istruzione `let` non è ambigua e il tipo viene dedotto dal compilatore. 

Le variabili in Q # sono non *modificabili*, ovvero una volta che una variabile è stata definita in questo modo, non può più essere modificata in alcun modo.
Ciò consente di eseguire diverse ottimizzazioni utili, inclusa l'ottimizzazione della logica classica che agisce sulle variabili da riordinare per l'applicazione del `Adjoint` variante di un'operazione.

Le variabili definite tramite il binding `let` come sopra sono locali rispetto a un ambito specifico, ad esempio il corpo di un'operazione o il contenuto di un ciclo di `for`.


## <a name="mutability"></a>Modificabilità ##

In alternativa alla creazione di una variabile con `let`, la parola chiave `mutable` creerà una variabile speciale modificabile che può essere riassociata dopo che è stata creata inizialmente usando la parola chiave `set`.

```qsharp
operation RandomInts(maxInt : Int, nrSamples : Int) : Int[] {
    mutable samples = new Int[0];
    for (i in 1 .. nrSamples) {
        set samples += [RandomInt(maxInt)];
    }
    return samples;
}
```

Tutti i tipi in Q #, incluse le matrici, seguono la semantica del valore. In particolare, non è possibile aggiornare gli elementi della matrice. Per modificare una matrice esistente, è necessario utilizzare un meccanismo di copia e aggiornamento simile a quello per i record in F#. Usando gli strumenti di libreria per le matrici fornite in [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays), è possibile, ad esempio, definire una funzione che restituisce una matrice di Paulis in cui Pauli in index `i` accetta il valore specificato e tutte le altre voci sono l'identità: 

```qsharp
function EmbedPauli (pauli : Pauli, i : Int, n : Int) : Pauli[] {
    
    let arr = ConstantArray(n, PauliI); // creates an array of filled with PauliI
    return arr w/ i <- pauli; // constructs a new array based on arr except that entry i is set to pauli
}
```

Verranno approfondite le procedure per l'utilizzo delle matrici quando si discutono le istruzioni e le espressioni Q #. 

La mutevolezza in Q # è un concetto che si applica a un *simbolo* anziché a un tipo o a un valore. In particolare, non dispone di una rappresentazione nel sistema di tipi, in modo implicito o esplicito e indipendentemente dal fatto che un'associazione sia modificabile (come indicato dalla parola chiave `mutable`) o immutabile (come indicato da `let`) non modifichi il tipo della variabile associata. Questo fornisce un modo importante per isolare la mutabilità all'interno di funzioni e operazioni specializzate.
In particolare, anche se una specializzazione contigua per un'operazione che usa una variabile modificabile non può essere generata automaticamente, la generazione automatica funziona correttamente per un'operazione che chiama una funzione che usa la mutabilità.
Per questo motivo, è consigliabile rendere le funzioni e le operazioni che usano la mutabilità il più breve e compatto possibile, in modo che il resto del programma Quantum possa essere scritto usando variabili non modificabili ordinarie.


## <a name="deconstruction"></a>Decostruzione ##

Oltre ad assegnare una singola variabile, le parole chiave `let` e `mutable`, o in realtà qualsiasi altro costrutto di associazione, consentono anche di decomprimere il contenuto di un [tipo di tupla](xref:microsoft.quantum.language.type-model#tuple-types).
Un'assegnazione di questo form è detta *decostruzione* degli elementi di tale tupla.
Ad esempio, se si modella un termine in un'Hamiltoniana da una tupla, è possibile usare la decostruzione per accedere ai diversi dati che è necessario simulare in questo periodo:

```qsharp
// Represents H = 3.1 X_0 Z_1.
let (_, (paulis, idxQubits)) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // paulis and idxQubits are both immutable variables
mutable ((c1, c2), _) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // c1 and c2 are both mutable variables
```


