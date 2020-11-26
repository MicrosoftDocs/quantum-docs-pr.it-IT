---
title: 'Q # Introduzione'
description: 'Introduzione rapida ai programmi Quantum in Q #'
author: beheim
ms.author: beheim
ms.date: 11/08/2020
ms.topic: article
uid: microsoft.quantum.guide.programs
ms.openlocfilehash: 975bcda5e0042406b465a83f17f1d2d3f5a1ec4f
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96233978"
---
# <a name="q-quantum-programming-language"></a>Linguaggio di programmazione Quantum Q #

Tutto ciò che è necessario sapere sul linguaggio di programmazione Q # è illustrato in dettaglio nella [Guida del linguaggio q #](xref:microsoft.quantum.qsharp.index). Come qualsiasi altra cosa, il [processo di progettazione del linguaggio](https://github.com/microsoft/qsharp-language#q-language-and-core-libraries-design) è open source e i contributi sono benvenuti.
Per informazioni più dettagliate sulle fondamenta e la motivazione alla base di Q #, vedere [perché è necessario q #?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).  
Q # viene fornito come parte del quantum Development Kit (QDK) per una rapida panoramica, vedere [che cos'è QDK?](xref:microsoft.quantum.overview.q-sharp). 

## <a name="what-is-a-quantum-program"></a>Che cos'è un programma Quantum?

Un programma quantum può essere considerato come un particolare set di subroutine classiche che, quando chiamato, eseguono un calcolo interagendo con un sistema quantico; un programma scritto in Q # non modella direttamente lo stato del quantum, bensì descrive il modo in cui un computer di controllo classico interagisce con qubits.
Ciò consente di essere completamente agnostico sullo stato del *Quantum anche in ogni computer di destinazione* , che potrebbe avere interpretazioni diverse a seconda del computer. 

Una conseguenza importante è che Q # non è in grado di analizzare nello stato di un qubit o di altre proprietà di Quantum Mechanics direttamente, il che garantisce che un programma Q # possa essere eseguito fisicamente su un computer Quantum.
Al contrario, un programma può chiamare operazioni come [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) per estrarre le informazioni classiche da un qubit.

Una volta allocato, un qubit può essere passato a operazioni e funzioni, denominate anche *Callable*. In un certo senso, questo è tutto ciò che può fare un programma Q # con un qubit. Tutte le azioni dirette sullo stato di una qubit sono tutte definite da chiamabili *intrinseci* , ad esempio e, ad [`X`](xref:Microsoft.Quantum.Intrinsic.X) [`H`](xref:Microsoft.Quantum.Intrinsic.H) esempio Callable le cui implementazioni non sono definite in Q # ma sono invece definite dal computer di destinazione. Le operazioni effettivamente eseguite dal computer di *destinazione vengono usate* solo per eseguire il programma Q # specifico.

Ad esempio, se si esegue il programma nel [simulatore a stato completo](xref:microsoft.quantum.machines.full-state-simulator), il simulatore esegue le operazioni matematiche corrispondenti al sistema Quantum simulato.
Tuttavia, guardando il futuro, quando il computer di destinazione è un computer Quantum reale, la chiamata di tali operazioni in Q # indirizza il computer Quantum a eseguire le operazioni *effettive* corrispondenti sul sistema Quantum *reale* , ad esempio gli impulsi laser temporizzati.

Un programma Q # ricombina queste operazioni in base a quanto definito da un computer di destinazione per creare nuove operazioni di livello superiore per esprimere il calcolo quantistico.
In questo modo, Q # rende più semplice esprimere gli algoritmi quantistici e Quantum sottostanti alla logica, oltre a essere generali rispetto alla struttura di un computer o di un simulatore di destinazione.

Un semplice esempio è il programma seguente, che alloca un qubit nello stato $ \ket {0} $, quindi applica un'operazione Hadamard `H` e misura il risultato in `PauliZ` base a.

```qsharp
@EntryPoint()
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now we measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // we reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, we return the result of the measurement.
        return result;
    }
}
```

I [Kata di Quantum](https://github.com/microsoft/QuantumKatas#introduction) forniscono una corretta introduzione ai [concetti relativi al quantum computing](https://github.com/microsoft/QuantumKatas#quantum-computing-concepts-qubits-and-gates) , ad esempio le operazioni Quantum comuni e come manipolare qubits. Altri esempi sono disponibili anche in [operazioni e funzioni intrinseche](xref:microsoft.quantum.libraries.standard.prelude).



