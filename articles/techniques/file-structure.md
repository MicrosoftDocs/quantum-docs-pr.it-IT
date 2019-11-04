---
title: Introduzione alle tecniche di sviluppo Quantum | Microsoft Docs
description: Introduzione alle tecniche di sviluppo Quantum
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 702d23293a1c340ddd3d7032d0e05294345469b2
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442563"
---
# <a name="q-program-overview"></a>Panoramica del programma Q #

Q # è un linguaggio di programmazione scalabile, multiparadigma e specifico di dominio per quantum computing. Q # è un linguaggio di programmazione Quantum in quanto può essere usato per descrivere il modo in cui vengono eseguite le istruzioni sui computer Quantum. I computer che possono essere assegnati da simulatori a hardware Quantum effettivo. Q # è scalabile: può essere usato per scrivere semplici programmi dimostrativi, ad esempio Teleport, eseguiti in pochi qubits, ma supporta anche la scrittura di programmi di grandi dimensioni, ad esempio simulazioni di molecole complesse che richiedono computer di grandi dimensioni con milioni di qubits. Anche se i computer fisici di grandi dimensioni sono ancora in futuro, Q # consente a un programmatore di programmare ora algoritmi quantistici complessi. Q # supporta varie attività, come il debug, la profilatura, la stima delle risorse e alcune simulazioni per scopi specifici in modo scalabile. 

Dal punto di vista tecnico, un programma quantum può essere considerato come un particolare set di funzioni classiche che, quando chiamato, generano circuiti Quantum come effetti collaterali. Una conseguenza importante di tale visualizzazione è che un programma scritto in Q # non modella direttamente qubits, ma descrive in che modo un computer di controllo classico interagisce con tali qubits.
Per impostazione predefinita, Q # non definisce gli Stati del quantum o altre proprietà di meccanica quantistica direttamente, bensì indirettamente tramite l'azione delle varie subroutine definite nel linguaggio.
Si consideri, ad esempio, lo stato $ \ket{+} = \left (\ket{0} + \ket{1}\right)/\sqrt{2}$ descritti nella Guida ai [concetti relativi al quantum computing](xref:microsoft.quantum.concepts.intro) .
Per preparare questo stato in Q #, si usano i fatti che i qubits vengono inizializzati nello stato $ \ket{0}$ e che $ \ket{+} = H\ket{0}$, dove $H $ è la trasformazione Hadamard:

```qsharp
using (qubit = Qubit()) {
    // At this point, qubit is in the state |0〉.
    H(qubit);
    // We've now applied H, such that our qubit is in H|0〉 = |+〉, as we wanted.
}
```
## <a name="q-tranformations-of-quantum-states"></a>Q # trasformazioni degli Stati Quantum

In particolare, nella scrittura del programma precedente, non è stato fatto riferimento in modo esplicito allo stato entro Q #, ma è stato invece descritto come lo stato è stato *trasformato* dal programma.
In modo analogo a come un programma shader grafico accumula una descrizione delle trasformazioni in ogni vertice, un programma Quantum in Q # accumula le trasformazioni negli Stati Quantum.
Ciò consente di essere completamente agnostico sullo stato del *Quantum anche in ogni computer di destinazione* , che potrebbe avere interpretazioni diverse a seconda del computer. 

Dal punto di vista di un programma Q #, un qubit è un riferimento completamente opaco alla struttura interna di un computer di destinazione.
Un programma Q # non è in grado di analizzare lo stato di un qubit, la relativa rappresentazione in un computer di destinazione o anche se si tratta dello stesso qubit di qualsiasi altro qubit disponibile per il programma.
Un programma può invece chiamare operazioni come `Measure` per apprendere le informazioni da un qubit e chiamare operazioni quali `X` e `H` per agire sullo stato di un qubit.
Queste operazioni non hanno una definizione intrinseca all'interno del linguaggio e sono rese concrete solo dal computer di destinazione usato per eseguire un particolare programma Q #.
Un programma Q # ricombina queste operazioni in base a quanto definito da un computer di destinazione per creare nuove operazioni di livello superiore per esprimere il calcolo quantistico.
In questo modo, Q # rende più semplice esprimere gli algoritmi Quantum e ibrido della logica sottostanti, oltre a essere generali rispetto alla struttura di un computer o di un simulatore di destinazione.

## <a name="q-operations-and-functions"></a>Operazioni e funzioni Q #

In concreto, un programma Q # è costituito da una o più *operazioni*, una o più *funzioni*e tipi definiti dall'utente. Le operazioni vengono usate per descrivere le trasformazioni dello stato di un computer Quantum e costituiscono il blocco predefinito più semplice dei programmi Q #. Ogni operazione definita in Q # può quindi chiamare un numero qualsiasi di altre operazioni, incluse le operazioni *intrinseche* predefinite implementate da un computer di destinazione.
Quando viene compilata, ogni operazione viene rappresentata come tipo di classe .NET che può essere fornita ai computer di destinazione.

Diversamente dalle operazioni, le funzioni vengono usate per descrivere il comportamento puramente classico e non hanno effetti oltre al calcolo dei valori di output classici. Q # è un linguaggio fortemente tipizzato ed è dotato di un set di tipi primitivi incorporati, nonché del supporto per i tipi definiti dall'utente. 

Nella parte restante di questa guida, si vedrà come usare concetti e costrutti di linguaggio diversi per semplificare la definizione di programmi Quantum complessi mediante i blocchi predefiniti di base di operazioni, funzioni e tipi. 

## <a name="structure-of-q-source-files"></a>Struttura dei file di origine Q #

Almeno un file di origine Q # è costituito da una *dichiarazione dello spazio dei nomi*, che specifica uno spazio dei nomi .NET che conterrà le definizioni nel file di origine.
Le definizioni di altri file di origine e librerie Q # possono essere incluse usando l'istruzione `open`.
Ad esempio, la maggior parte delle operazioni che definiscono i controlli di base sono definite nello spazio dei nomi <xref:microsoft.quantum.intrinsic>.
Per renderlo disponibile al codice, è sufficiente `open` lo spazio dei nomi nella parte superiore di ogni file:

```qsharp
namespace Example {
    open Microsoft.Quantum.Intrinsic;

    // ...
}
```

All'interno di uno spazio dei nomi, ogni file di origine Q # può definire qualsiasi combinazione di *operazioni*, *funzioni*e *tipi definiti dall'utente*.
Nella parte restante di questa sezione verranno descritti ciascuno a sua volta e verranno forniti esempi di come possono essere usati in pratica per creare programmi Quantum utili.
