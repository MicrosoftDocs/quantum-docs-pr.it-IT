---
title: 'Nozioni di base su Q #'
description: 'Concetti di base di Q #'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
ms.openlocfilehash: 45e6f2f33dafc2aec177091d3cfa94aca14fbf0a
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415361"
---
# <a name="q-basics"></a>Nozioni di base su Q #

Questo articolo presenta una breve introduzione ai componenti di base di Q #.

Per una panoramica delle funzionalità di Q # e del punto in cui si integra come componente fondamentale del quantum Development Kit, vedere [che cos'è q #?](xref:microsoft.quantum.overview.q-sharp). 

## <a name="what-is-a-quantum-program"></a>Che cos'è un programma Quantum?

Dal punto di vista tecnico, un programma Quantum è un particolare set di subroutine classiche che, quando chiamate, eseguono determinate operazioni in un sistema Quantum.
Una conseguenza importante di tale visualizzazione è che un programma Q # non modella direttamente qubits, ma descrive in che modo un computer controllato dal classico interagisce con tali qubits.
Per impostazione predefinita, Q # non definisce gli Stati Quantum o altre proprietà dei meccanismi Quantum direttamente.
Si consideri, ad esempio, lo stato $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ illustrato nella Guida ai [concetti relativi al quantum computing](xref:microsoft.quantum.concepts.intro) .
Per preparare questo stato in Q #, iniziare con i fatti che qubits vengono inizializzati nello stato $ \ket {0} $ e che $ \ket{+} = H\ket {0} $, dove $H $ è la [trasformazione Hadamard](xref:microsoft.quantum.glossary#hadamard), implementata dall' [ `H` operazione](xref:microsoft.quantum.intrinsic.h). Il codice Q # di base per inizializzare e trasformare un qubit, quindi, ha un aspetto simile al seguente:

```qsharp
using (qubit = Qubit()) {
    // At this point, the qubit is in the state |0⟩.
    H(qubit);
    // H is now applied, such that the qubit is in H|0⟩ = |+⟩, as desired.
}
```
Per ulteriori informazioni sull'inizializzazione o l' *allocazione*di qubits, vedere [utilizzo di qubits](xref:microsoft.quantum.guide.qubits).

## <a name="quantum-states-in-q"></a>Stati Quantum in Q #

In particolare, il programma precedente non fa riferimento in modo esplicito allo stato all'interno di Q #, ma descrive il modo in cui il programma ha *trasformato* lo stato.
Con questo approccio, è possibile essere completamente agnostico sullo *stato del quantum anche in ogni* computer di destinazione, che può avere interpretazioni diverse a seconda del computer. 

Un programma Q # non può analizzare nello stato di un qubit.
Un programma può invece chiamare operazioni come [`Measure`](xref:microsoft.quantum.intrinsic.measure) per ottenere informazioni da un qubit e chiamare operazioni come [`X`](xref:microsoft.quantum.intrinsic.x) e [`H`](xref:microsoft.quantum.intrinsic.h) per agire sullo stato di un qubit.
Le *operazioni effettivamente eseguite* da queste operazioni sono concretate solo dal computer di destinazione usato per eseguire il programma Q # specifico.
Ad esempio, se si esegue il programma nel [simulatore a stato completo](xref:microsoft.quantum.machines.full-state-simulator), il simulatore esegue le operazioni matematiche corrispondenti al sistema Quantum simulato.
Tuttavia, guardando il futuro, quando il computer di destinazione è un computer Quantum reale, la chiamata di tali operazioni in Q # indirizza il computer Quantum a eseguire le operazioni *effettive* corrispondenti sul sistema Quantum *reale* , ad esempio gli impulsi laser temporizzati.

Un programma Q # ricombina queste operazioni in base a quanto definito da un computer di destinazione per creare nuove operazioni di livello superiore per esprimere il calcolo quantistico.
In questo modo, Q # rende più semplice esprimere gli algoritmi quantistici e Quantum sottostanti alla logica, oltre a essere generali rispetto alla struttura di un computer o di un simulatore di destinazione.

## <a name="q-operations-and-functions"></a>Operazioni e funzioni Q #

In concreto, un programma Q # comprende *operazioni*, *funzioni*e qualsiasi tipo definito dall'utente. 

Le operazioni vengono usate per descrivere le trasformazioni dei sistemi quantum e costituiscono il blocco predefinito più fondamentale dei programmi Q #. Ogni operazione definita in Q # può quindi chiamare un numero qualsiasi di altre operazioni.

Diversamente dalle operazioni, le funzioni vengono usate per descrivere il comportamento classico puramente *deterministico* e non hanno alcun effetto oltre al calcolo dei valori classici. Si supponga, ad esempio, di voler misurare il qubits alla fine di un programma e aggiungere i risultati della misurazione a una matrice.
In questo caso, `Measure` è un' *operazione* che indica al computer di destinazione di eseguire una misurazione sulla qubits (reale o simulata). Allo stesso tempo, le *funzioni* gestiscono il processo classico di aggiunta dei risultati restituiti a una matrice.

Insieme, le operazioni e le funzioni sono note come *chiamabili*. La struttura e il comportamento sottostanti vengono introdotti e descritti in dettaglio in [operazioni e funzioni in Q #](xref:microsoft.quantum.guide.operationsfunctions).


## <a name="q-syntax-overview"></a>Cenni preliminari sulla sintassi Q #

La sintassi di un linguaggio descrive le diverse combinazioni di simboli che formano un programma sintatticamente corretto.
In Q # gli elementi di sintassi sono classificati in tre gruppi diversi: tipi, espressioni e istruzioni.

### <a name="types"></a>Tipi
Q # è un linguaggio fortemente tipizzato, in modo che l'utilizzo accurato dei tipi possa aiutare il compilatore a fornire garanzie complesse sui programmi Q # in fase di compilazione.
Oltre ai tipi primitivi predefiniti standard e specifici di Quantum, ad esempio,,, `Int` `Bool` `Qubit` e `Result` , Q # fornisce supporto per i tipi definiti dall'utente.

Per le descrizioni di tutti i tipi primitivi, i dettagli per i tipi di matrice e di tupla e i passaggi per definire nuovi tipi in un file Q #, vedere [tipi in q #](xref:microsoft.quantum.guide.types).

### <a name="expressions"></a>Espressioni
Un'espressione in un linguaggio di programmazione è una combinazione di una o più costanti, variabili, operatori e funzioni che il linguaggio di programmazione interpreta e restituisce un valore specifico.
Più semplicemente, per ogni tipo in un linguaggio, le espressioni di quel tipo possono essere *valori letterali* o simboli associati a un valore di quel tipo.
Ad esempio, `5` è un valore `Int` letterale (quindi anche un'espressione di tipo `Int` ) e se il simbolo `count` è associato al valore integer `5` , `count` è anche un'espressione Integer.

Inoltre, un'espressione può essere costituita da altre espressioni combinate da determinati operatori.
Ad esempio, un'altra `Int` espressione che restituisce `5` è `2+3` .

Per ulteriori informazioni sulle espressioni e gli operatori compatibili in Q #, vedere [espressioni di tipo in q #](xref:microsoft.quantum.guide.expressions). 

### <a name="statements"></a>Istruzioni 
Un'istruzione è un'unità sintattica di un linguaggio di programmazione imperativo che esprime un'azione da eseguire. Le istruzioni sono in contrasto con le espressioni presenti nelle istruzioni che non restituiscono risultati e vengono eseguite esclusivamente per gli effetti collaterali. Le espressioni, tuttavia, restituiscono sempre un risultato e spesso non hanno effetti collaterali. In breve, le istruzioni Q # vengono eseguite, mentre le espressioni vengono valutate.

Un semplice esempio di istruzione in Q # consiste nell'assegnare un simbolo a un'espressione:
```qsharp
let count = 5;
```

Un esempio più interessante è l' `for` istruzione che supporta l'iterazione e include un *blocco di istruzioni*.
`qubits`Si supponga che sia il simbolo associato a un registro di qubits (tecnicamente di tipo `Qubit[]` o una matrice di `Qubit` tipi). Risultato
```qsharp
for (qubit in qubits) {
    H(qubit);
}
```
è un'istruzione che esegue l'iterazione di ogni qubit nel registro, eseguendo l' `H` operazione su ciascuna di esse. Si noti che `H(qubit);` si tratta anche di un'istruzione.

È possibile usare qualsiasi espressione chiamata di tipo `Unit` (un `Unit` tipo non restituisce alcuna informazione) come istruzione.
Questo tipo di espressione è utile quando si chiamano le operazioni su qubits che restituiscono `Unit` perché lo scopo dell'istruzione è modificare lo stato quantum implicito.
Le istruzioni di valutazione dell'espressione richiedono un punto e virgola di terminazione.

Si usano istruzioni per compilare quasi ogni aspetto di un programma Q # e nessuna pagina può includere tutte le informazioni correlate.
Per ulteriori informazioni sulla struttura lessicale e la formattazione, vedere la pagina relativa alla [struttura dei file Q #](xref:microsoft.quantum.guide.filestructure). per l'assegnazione di associazioni di simboli e l'ambito, vedere [variabili in Q #](xref:microsoft.quantum.guide.variables); per i cicli del flusso di controllo `for` , ad esempio, vedere [flusso di controllo in Q #](xref:microsoft.quantum.guide.controlflow).

## <a name="next-steps"></a>Passaggi successivi

Inizia a conoscere i [tipi in Q #](xref:microsoft.quantum.guide.types).

Per informazioni più dettagliate sulle fondamenta e la motivazione alla base di Q #, vedere [perché è necessario q #?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).
