---
title: 'Nozioni di base su Q #'
description: 'Concetti di base di Q #'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
ms.openlocfilehash: fd0ea47f00b1456ec460808ef7d451c8427677cd
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431156"
---
# <a name="q-basics"></a>Nozioni di base su Q #

In questa sezione viene presentata una breve introduzione ai blocchi predefiniti di base di Q #.

Per una rapida panoramica delle funzionalità di Q # e del punto in cui si integra come componente fondamentale del quantum Development Kit, è possibile vedere [che cos'è q #?](xref:microsoft.quantum.overview.q-sharp). 

## <a name="what-is-a-quantum-program"></a>Che cos'è un programma Quantum?

Dal punto di vista tecnico, un programma quantum può essere considerato come un particolare set di subroutine classiche che, quando chiamato, eseguono determinate operazioni in un sistema Quantum.
Una conseguenza importante di tale visualizzazione è che un programma scritto in Q # non modella direttamente qubits, ma descrive in che modo un computer di controllo classico interagisce con tali qubits.
Per impostazione predefinita, Q # non definisce gli Stati del quantum o altre proprietà di meccanica quantistica direttamente.
Si consideri, ad esempio, lo stato $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ illustrato nella Guida ai [concetti relativi al quantum computing](xref:microsoft.quantum.concepts.intro) .
Per preparare questo stato in Q #, si usano i fatti che qubits vengono inizializzati nello stato $ \ket {0} $ e che $ \ket{+} = H\ket {0} $, dove $H $ è la trasformazione Hadamard, implementata da [ `H` Operation] (] (xrif: Microsoft. Quantum. Intrinsic. H):

```qsharp
using (qubit = Qubit()) {
    // At this point, qubit is in the state |0⟩.
    H(qubit);
    // We've now applied H, such that our qubit is in H|0⟩ = |+⟩, as we wanted.
}
```

## <a name="quantum-states-in-q"></a>Stati Quantum in Q #

In particolare, nella scrittura del programma precedente, non è stato fatto riferimento in modo esplicito allo stato entro Q #, ma è stato invece descritto come lo stato è stato *trasformato* dal programma.
Ciò consente di essere completamente agnostico sullo stato del *Quantum anche in ogni computer di destinazione* , che potrebbe avere interpretazioni diverse a seconda del computer. 

Un programma Q # non è in grado di analizzare nello stato di un qubit.
Un programma può invece chiamare operazioni come [`Measure`](xref:microsoft.quantum.intrinsic.measure) per ottenere informazioni da un qubit e chiamare operazioni come [`X`](xref:microsoft.quantum.intrinsic.x) e [`H`](xref:microsoft.quantum.intrinsic.h) per agire sullo stato di un qubit.
Le operazioni effettivamente eseguite dal computer di *destinazione vengono usate* solo per eseguire il programma Q # specifico.
Ad esempio, se si esegue il programma nel [simulatore a stato completo](xref:microsoft.quantum.machines.full-state-simulator), il simulatore eseguirà le operazioni matematiche corrispondenti al sistema Quantum simulato.
Tuttavia, guardando il futuro, quando il computer di destinazione è un computer Quantum reale, la chiamata di tali operazioni in Q # indirizza il computer Quantum a eseguire le operazioni *effettive* corrispondenti sul sistema Quantum *reale* , ad esempio gli impulsi laser temporizzati.

Un programma Q # ricombina queste operazioni in base a quanto definito da un computer di destinazione per creare nuove operazioni di livello superiore per esprimere il calcolo quantistico.
In questo modo, Q # rende più semplice esprimere gli algoritmi quantistici e Quantum sottostanti alla logica, oltre a essere generali rispetto alla struttura di un computer o di un simulatore di destinazione.

## <a name="q-operations-and-functions"></a>Operazioni e funzioni Q #

In concreto, un programma Q # è costituito da *operazioni*, *funzioni*e qualsiasi tipo definito dall'utente. 

Le operazioni vengono usate per descrivere le trasformazioni dei sistemi quantum e costituiscono il blocco predefinito più elementare dei programmi Q #. Ogni operazione definita in Q # può quindi chiamare un numero qualsiasi di altre operazioni.

Diversamente dalle operazioni, le funzioni vengono usate per descrivere il comportamento classico puramente *deterministico* e non hanno alcun effetto oltre al calcolo dei valori classici. Si supponga, ad esempio, di voler misurare i qubits alla fine di un programma e aggiungere i risultati della misurazione a una matrice.
In questo caso `Measure` si tratta di un' *operazione* che indica al computer di destinazione di eseguire una misurazione sulla qubits (reale o simulata) e il processo classico di aggiunta dei risultati restituiti a una matrice verrà gestito da *funzioni*.

Insieme, le operazioni e le funzioni vengono definite *chiamabili*e la struttura e il comportamento sottostanti sono introdotti nelle [operazioni e nelle funzioni nella pagina Q #](xref:microsoft.quantum.guide.operationsfunctions) .


## <a name="q-syntax-overview"></a>Cenni preliminari sulla sintassi Q #

La sintassi di un linguaggio descrive le diverse combinazioni di simboli che formano un programma sintatticamente corretto.
In Q # è possibile classificare gli elementi della relativa sintassi in tre gruppi diversi: tipi, espressioni e istruzioni.

### <a name="types"></a>Tipi
Q # è un linguaggio fortemente tipizzato, in modo che l'utilizzo accurato dei tipi possa aiutare il compilatore a fornire garanzie complesse sui programmi Q # in fase di compilazione.
Oltre ai tipi primitivi predefiniti standard e specifici di Quantum (ad esempio,, `Int` `Bool` `Qubit` e `Result` ), Q # fornisce supporto per i tipi definiti dall'utente.
Tutti i tipi primitivi di Q # sono descritti nella pagina dei [tipi nella pagina q #](xref:microsoft.quantum.guide.types) , insieme ai dettagli sui tipi di matrice e di tupla, nonché su come definire nuovi tipi all'interno di un file q #.

### <a name="expressions"></a>Espressioni
Un'espressione in un linguaggio di programmazione è una combinazione di una o più costanti, variabili, operatori e funzioni che il linguaggio di programmazione interpreta e restituisce un valore specifico.
Più semplicemente, per ogni tipo in un linguaggio, le espressioni di quel tipo possono essere *valori letterali* o simboli associati a un valore di quel tipo.
Ad esempio, `5` è un valore `Int` letterale (quindi anche un'espressione di tipo `Int` ) e se il simbolo `count` è associato al valore integer `5` , `count` è anche un'espressione Integer.

Inoltre, un'espressione può essere costituita da altre espressioni combinate con determinati operatori.
Di conseguenza, un altro esempio di `Int` espressione che restituisce `5` è `2+3` .

Le possibili espressioni dei tipi in Q #, nonché gli operatori compatibili che possono essere usati per formarli, sono descritte in dettaglio nelle [espressioni di tipo nella pagina q #](xref:microsoft.quantum.guide.expressions) . 

### <a name="statements"></a>Istruzioni 
Un'istruzione è un'unità sintattica di un linguaggio di programmazione imperativo che esprime un'azione da eseguire. Le istruzioni sono in contrasto con le espressioni presenti nelle istruzioni che non restituiscono risultati e vengono eseguite esclusivamente per gli effetti collaterali, mentre le espressioni restituiscono sempre un risultato e spesso non hanno effetti collaterali.
Questa distinzione viene spesso osservata nel testo: un'espressione viene valutata, mentre viene eseguita un'istruzione.

Un esempio molto semplice di un'istruzione in Q # consiste nell'assegnare un simbolo a un'espressione:
```qsharp
let count = 5;
```

Un esempio leggermente più interessante è l' `for` istruzione che supporta l'iterazione e include un *blocco di istruzioni*.
`qubits`Si supponga che sia il simbolo associato a un registro di qubits (tecnicamente di tipo `Qubit[]` , ad esempio una matrice di `Qubit` tipi). Risultato
```qsharp
for (qubit in qubits) {
    H(qubit);
}
```
è un'istruzione che scorre ogni qubit nel registro, eseguendo l' `H` operazione su ognuno di essi. Si noti che `H(qubit);` si tratta anche di un'istruzione.

In realtà, qualsiasi espressione chiamata di tipo `Unit` (che non restituiscono informazioni) può essere usata come un'istruzione.
Questa operazione viene utilizzata principalmente quando si chiamano le operazioni su qubits che restituiscono `Unit` perché lo scopo dell'istruzione è modificare lo stato quantum implicito.
Le istruzioni di valutazione dell'espressione richiedono un punto e virgola di terminazione.

Quasi tutti gli aspetti di un programma Q # vengono compilati usando le istruzioni, quindi nessuna singola pagina può includere tutte le informazioni relative a esse.
Tuttavia, la struttura lessicale e la formattazione sono descritte nella pagina della [struttura di file q #](xref:microsoft.quantum.guide.filestructure) , nell'assegnazione di associazioni di simboli e nell'ambito alle [variabili in q #](xref:microsoft.quantum.guide.variables)e nei cicli del flusso di controllo, ad esempio nel `for` flusso di [controllo in q #](xref:microsoft.quantum.guide.controlflow).


## <a name="whats-next"></a>Quali sono le operazioni successive?
Nella parte restante di questa guida verrà illustrato come usare Q # per creare programmi Quantum complessi attraverso i blocchi predefiniti di base di operazioni, funzioni e tipi.

Per iniziare, è possibile iniziare a imparare a usare i [tipi in Q #](xref:microsoft.quantum.guide.types).

Se si è interessati a saperne di più sulle fondamenta e la motivazione dietro Q #, vedere [perché è necessario q #?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).
