---
title: Circuiti Quantum | Microsoft Docs
description: Circuiti quantistici
author: QuantumWriter
uid: microsoft.quantum.concepts.circuits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: fe845aa0dde7c780ea6721dfe2559119e90b4aa5
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820794"
---
# <a name="quantum-circuits"></a>Circuiti Quantum
Prendere in considerazione per un attimo la trasformazione unitaria $ \Text{CNOT} _{01}(H\otimes 1) $.
Questa sequenza di controllo è di importanza fondamentale per l'elaborazione quantistica, perché crea uno stato qubit con un massimo di due:

$ $ \mathrm{CNOT}_{01}(H\otimes 1) \ket{00} = \frac{1}{\sqrt{2}} \left (\ket{00} + \ket{11} \right), $ $

Le operazioni con questa o maggiore complessità sono onnipresenti negli algoritmi quantistici e nella correzione degli errori quantistici, quindi dovrebbe essere molto importante ottenere un metodo semplice per la visualizzazione denominata *diagramma del circuito quantistico*.
Il diagramma di circuito per la preparazione di questo stato quantico con la massima correlazione è:

<!--- ![](.\media\1.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/Concepts1.png)

## <a name="quantum-circuit-diagram-conventions"></a>Convenzioni del diagramma del circuito quantistico
Questo linguaggio visivo per le operazioni quantum può essere più facilmente digeribile rispetto alla scrittura della matrice equivalente dopo aver compreso le convenzioni per esprimere un circuito Quantum.
Queste convenzioni sono riportate di seguito.

In un diagramma di circuito ogni linea continua raffigura un qubit o più in generale un registro qubit.
Per convenzione, la riga superiore è qubit register $0 $ e il resto è contrassegnato in modo sequenziale. Il circuito di esempio precedente viene illustrato come agendo su due qubits (o due registri equivalenti costituiti da un qubit).
Le attività di controllo che agiscono su uno o più registri qubit sono denotate come box.
Ad esempio, il simbolo

<!--- ![](.\media\2.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_2.png)

è il [Hadamard](xref:microsoft.quantum.intrinsic.h) Gate che agisce su un singolo qubit Register.

Le attività di controllo Quantum sono ordinate in ordine cronologico con il Gate più a sinistra quando il Gate viene applicato per primo a qubits.
In altre parole, se si immaginano i cavi con lo stato quantum, i fili portano lo stato del quantum attraverso ogni controllo nel diagramma da sinistra a destra.
Ovvero 

<!--- ![](.\media\3.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_3.png)

matrice unitaria $CBA $.
La moltiplicazione di matrici rispetta la convenzione opposta: viene applicata per prima la matrice più a destra. Nei diagrammi del circuito quantistico, tuttavia, viene applicato per primo il Gate più a sinistra.
Questa differenza può talvolta comportare confusione, quindi è importante notare questa differenza significativa tra la notazione algebrica lineare e i diagrammi del circuito quantistico.

## <a name="inputs-and-outputs-of-quantum-circuits"></a>Input e output dei circuiti Quantum
Tutti gli esempi precedenti forniti hanno avuto esattamente lo stesso numero di fili (qubits) di input in un controllo Quantum come il numero di fili fuori dal controllo Quantum.
Potrebbe sembrare ragionevole che i circuiti Quantum possano avere più o meno output degli input in generale.
Questo non è possibile, tuttavia, perché tutte le operazioni Quantum, il salvataggio della misura, sono unitarie e pertanto reversibili.
Se non hanno lo stesso numero di output degli input, non sarebbero reversibili e, di conseguenza, non si trattasse di una contraddizione.
Per questo motivo, qualsiasi casella disegnata in un diagramma di circuito deve avere esattamente lo stesso numero di fili che li immette come uscita.

I diagrammi di circuito multiqubit seguono convenzioni simili a quelle a qubit singolo.
Come esempio chiarificante, è possibile definire un'operazione unitaria a due qubit $B $ come $ (H S\otimes X) $ ed esprimere il circuito in modo equivalente come

<!--- ![](.\media\4.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_4.png)

È anche possibile visualizzare $B $ come avente un'azione su un singolo registro qubit anziché 2 1 qubit a seconda del contesto in cui viene usato il circuito. Probabilmente la proprietà più utile di questi diagrammi di circuito astratti è che consentono di descrivere algoritmi quantistici complessi a un livello elevato senza doverli compilare fino a controlli fondamentali.
Ciò significa che è possibile ottenere un'intuizione sul flusso di dati per un algoritmo Quantum di grandi dimensioni senza che sia necessario comprendere tutti i dettagli sul funzionamento di ciascuna subroutine all'interno dell'algoritmo.

## <a name="controlled-gates"></a>Controlli di controllo
L'altro costrutto incorporato nei diagrammi di circuito Quantum multiqubit è il controllo.
L'azione di un controllo Quantum controllato singolarmente, indicato $ \Lambda (G) $, in cui il valore di un singolo qubit controlla l'applicazione di $G $, può essere compreso osservando l'esempio seguente di un input di stato del prodotto $ \Lambda (G) (\Alpha \ket{0} + \beta \ket{1}) \ket{\psi} = \Alpha \ket{0} \ket{\psi} + \beta \ket{1} G\ket {\ psi} $.
Ovvero, il controllo controllato si applica $G $ al registro contenente $ \psi $ se e solo se il qubit del controllo accetta il valore $1 $.
In generale, le operazioni controllate nei diagrammi di circuito sono descritte come

<!--- ![](.\media\5.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_5.png)

Qui il cerchio nero indica il bit del quantum su cui è controllato il controllo e un cavo verticale indica l'elemento unitario applicato quando il qubit del controllo accetta il valore $1 $.
Per i casi speciali in cui $G = X $ e $G = Z $ introduciamo la notazione seguente per descrivere la versione controllata delle attività di controllo (si noti che il controllo X controllato è il [$CNOT $ Gate](xref:microsoft.quantum.intrinsic.cnot)):

<!--- ![](.\media\6.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_6.png)

Q # fornisce metodi per generare automaticamente la versione controllata di un'operazione, che consente di salvare il programmatore dalla necessità di scrivere codice per queste operazioni. Un esempio è illustrato di seguito:

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a>Operatore di misurazione
L'operazione rimanente da visualizzare nei diagrammi di circuito è la misurazione.
La misurazione accetta un registro qubit, lo misura e restituisce il risultato come informazioni classiche.
Un'operazione di misurazione è indicata da un simbolo del contatore e accetta sempre come input un registro qubit (indicato da una linea continua) e restituisce informazioni classiche (indicate da una doppia riga).
In particolare, questo sottocircuito ha un aspetto simile al seguente:

<!--- ![](.\media\7.svg) ---->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![circuito di misurazione](~/media/concepts_7.png)

Q # implementa un [operatore di misura](xref:microsoft.quantum.intrinsic.measure) a questo scopo.
Per ulteriori informazioni, vedere la [sezione sulle misurazioni](xref:microsoft.quantum.libraries.standard.prelude#measurements) .

Analogamente, il sottocircuito

<!--- ![](.\media\8.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_8.png)

fornisce un controllo classico, in cui $G $ viene applicato condizionato al bit del controllo classico valore $1 $.

## <a name="teleportation-circuit-diagram"></a>Diagramma del circuito di Teleportation
La [teleportazione quantistica](xref:microsoft.quantum.techniques.puttingittogether) è probabilmente l'algoritmo Quantum migliore per illustrare questi componenti.
La telemetria quantistica è un metodo per lo scorrimento dei dati all'interno di un computer quantistico (o anche tra computer Quantum lontani in una rete quantistica) tramite l'uso di un nodo e una misurazione.
È interessante notare che è effettivamente in grado di trasferire uno stato quantico, ad indicare il valore in un determinato qubit, da un qubit a un altro, senza nemmeno conoscere il valore di qubit.
Questa operazione è necessaria affinché il protocollo funzioni in base alle leggi di Quantum Mechanics.
Il circuito di Teleportation Quantum è riportato di seguito. viene anche fornita una versione con annotazioni del circuito per illustrare come leggere il circuito Quantum.

<!--- ![](.\media\tp2.svg){ width=50% } --->
![](~/media/concepts_tp2.png)
