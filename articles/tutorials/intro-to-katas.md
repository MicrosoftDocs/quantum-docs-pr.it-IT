---
title: Introduzione alle esercitazioni della serie Quantum Katas
description: Informazioni sui kata (esercizi di formazione) forniti con il Microsoft Quantum Development Kit (QDK)
author: bradben
ms.author: bradben
ms.date: 06/02/2020
ms.topic: overview
uid: microsoft.quantum.overview.katas
ms.openlocfilehash: 1c4dfa5c47aa38935cd5936cd256e357b6605371
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85276222"
---
# <a name="learn-quantum-computing-with-the-quantum-katas"></a>Apprendere il calcolo quantistico con i Quantum Katas

[I Kata di Quantum](https://github.com/Microsoft/QuantumKatas/) sono esercitazioni di programmazione open source e autonoma che mirano ad insegnare gli elementi del quantum computing e la programmazione Q # allo stesso tempo.

## <a name="learning-by-doing"></a>Formazione pratica

Le esercitazioni e gli esercizi raccolti in questo progetto puntano sulla formazione pratica, con attività di programmazione correlate ad argomenti specifici che passano da un livello molto semplice a un livello relativamente complesso. Per ogni attività è necessario compilare codice. Le prime attività potrebbero richiedere solo una riga, mentre le ultime potrebbero richiedere un frammento di codice considerevole.

In particolare, i Kata includono Framework di test che configurano, eseguono e convalidano le soluzioni per le attività. In questo modo è possibile ottenere un feedback immediato sulla soluzione e rivalutare l'approccio se non è corretto.

È possibile usare i Kata per l'apprendimento nell'ambiente preferito:

* Jupyter Notebook online nell'ambiente Binder
* Jupyter Notebooks in esecuzione nel computer locale
* Visual Studio
* Visual Studio Code

## <a name="what-can-i-learn-with-the-quantum-katas"></a>Formazione offerta dalle esercitazioni della serie Quantum Katas

Scopri le nozioni di base e le nozioni fondamentali di quantum computing o approfondimenti su algoritmi e protocolli quantistici. È consigliabile seguire questo percorso di apprendimento dall'inizio per assicurarsi di avere acquisito conoscenze approfondite sui concetti fondamentali del calcolo quantistico. Naturalmente, è possibile ignorare gli argomenti con cui si ha familiarità, ad esempio l'aritmetica complessa, e apprendere gli algoritmi nell'ordine desiderato.

### <a name="introduction-to-quantum-computing-concepts"></a>Introduzione ai concetti del calcolo quantistico

| Kata | Descrizione |
|:-----|-------------|
|[Aritmetica complessa](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ComplexArithmetic)|Questa esercitazione illustra alcuni degli aspetti matematici richiesti per lavorare con l'elaborazione quantistica, ad esempio numeri immaginari e complessi.|
|[Algebra lineare](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/LinearAlgebra)|L'algebra lineare viene usata per rappresentare gli Stati e le operazioni del quantum nell'elaborazione quantistica. Questa esercitazione illustra le nozioni di base, tra cui matrici e vettori.|
|[Concetto di qubit](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/Qubit)|Informazioni su qubits: uno dei concetti di base di quantum computing. |
|[Gate quantistici a singolo qubit](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/SingleQubitGates)|Questa esercitazione introduce le attività di controllo dei quantum qubit, che fungono da blocchi predefiniti degli algoritmi quantistici e trasformano gli Stati qubit di Quantum in diversi modi.|
|[Sistemi a più qubit](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/MultiQubitSystems)|Questa esercitazione introduce i sistemi qubit, la relativa rappresentazione in notazione matematica e il codice Q #, oltre al concetto di groviglio.|
|[Controlli Quantum multiqubit](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/MultiQubitGates)|Questa esercitazione segue l'esercitazione su [Quantum Gates Single-qubit](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/SingleQubitGates) e si concentra sull'applicazione di controlli Quantum ai sistemi multiqubit.|

### <a name="quantum-computing-fundamentals"></a>Concetti fondamentali sul calcolo quantistico

| Kata | Descrizione |
|:-----|-------------|
|[Riconoscimento di gate quantistici](https://github.com/microsoft/QuantumKatas/tree/master/BasicGates)|Una serie di esercizi progettati per acquisire familiarità con i cancelli Quantum di base in Q #. Include gli esercizi per le attività di base Single-qubit e qubit, le attività di controllo adiacenti e controllate e come usare le attività di controllo per modificare lo stato di un qubit.|
|[Creazione di una sovrapposizione quantistica](https://github.com/microsoft/QuantumKatas/tree/master/Superposition)|Usare questi esercizi per acquisire familiarità con il concetto di superposizione e programmazione in Q #. Include gli esercizi per le attività di base Single-qubit e qubit, la superposizione e il controllo di flusso e la ricorsione in Q #.|
|[Distinzione degli stati quantistici mediante le misure](https://github.com/microsoft/QuantumKatas/tree/master/Measurements)|Risolvere questi esercizi durante l'apprendimento della misurazione quantistica e degli Stati ortogonali e non ortogonali. |
|[Misure congiunte](https://github.com/microsoft/QuantumKatas/tree/master/JointMeasurements)|Informazioni sulle misurazioni di parità congiunta e su come usare l'operazione di [misurazione](xref:microsoft.quantum.intrinsic.measure) per distinguere gli Stati Quantum.|

### <a name="algorithms"></a>Algoritmi

| Kata | Descrizione |
|:-----|-------------|
|[Teletrasporto quantistico](https://github.com/microsoft/QuantumKatas/tree/master/Teleportation)|Questo Kata Esplora il protocollo di teletrasmissione quantistica, un protocollo che consente la comunicazione di uno stato quantico usando solo la comunicazione classica e l'intrico dei quantum condivisi in precedenza.|
|[Codifica superdensa](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding)|La codifica superdensa è un protocollo che consente di trasmettere due bit di informazioni classiche inviando un solo qubit usando l'intrico di Quantum condiviso in precedenza.  |
|[Algoritmo di Deutsch-Jozsa](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ExploringDeutschJozsaAlgorithm)|Questo algoritmo è famoso per essere uno dei primi esempi di un algoritmo Quantum che è esponenzialmente più veloce rispetto a qualsiasi algoritmo classico deterministico.|
|[Esplorazione delle proprietà generali dell'algoritmo di ricerca di Grover](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ExploringGroversAlgorithm)|Introduzione generale a uno degli algoritmi più famosi del quantum computing. Viene risolto il problema di ricerca di un input per un black box (Oracle) che produce un output specifico. |
|[Implementazione dell'algoritmo di ricerca di Grover](https://github.com/microsoft/QuantumKatas/tree/master/GroversAlgorithm)|Questo Kata si immerge nell'algoritmo di ricerca di Grover e illustra la scrittura di Oracle, l'esecuzione di passaggi dell'algoritmo e infine l'inserimento di tutti gli elementi.|
|[Risoluzione dei problemi reali con l'algoritmo di Grover: problemi SAT](https://github.com/microsoft/QuantumKatas/tree/master/SolveSATWithGrover)|Una serie di esercizi che usano l'algoritmo di Grover per risolvere i problemi realistici, usando i [problemi soddisfacibilità booleani](https://en.wikipedia.org/wiki/Boolean_satisfiability_problem) (SAT) come esempio.  |
|[Risoluzione dei problemi reali usando l'algoritmo di Grover: problemi di colorazione dei grafi](https://github.com/microsoft/QuantumKatas/tree/master/GraphColoring)| Questo Kata Esplora ulteriormente l'algoritmo di Grover, questo tempo per risolvere i [problemi di soddisfazione dei vincoli](https://en.wikipedia.org/wiki/Constraint_satisfaction_problem), usando un problema di colorazione del grafo come esempio. |

### <a name="protocols-and-libraries"></a>Protocolli e librerie

| Kata | Descrizione |
|:-----|-------------|
|[Protocollo BB84 per la distribuzione delle chiavi quantistiche](https://github.com/microsoft/QuantumKatas/tree/master/KeyDistribution_BB84)|Informazioni su come implementare un protocollo di distribuzione delle chiavi Quantum, [BB84](https://en.wikipedia.org/wiki/BB84), che usa qubits per scambiare le chiavi crittografiche. |
|[Bit-flip Error correzione del codice](https://github.com/microsoft/QuantumKatas/tree/master/QEC_BitFlipCode)|Esplorare la correzione degli errori quantistici con il più semplice codice di correzione degli errori Quantum (QEC), ovvero il codice a scorrimento bit qubit a tre bit.|
|[Stima delle fasi](https://github.com/microsoft/QuantumKatas/blob/master/PhaseEstimation)|Gli algoritmi di stima delle fasi sono alcuni dei blocchi predefiniti più importanti del quantum computing. Informazioni sulla valutazione della fase con questi esercizi che coprono la stima della fase quantistica e come preparare ed eseguire routine di stima della fase in Q #.|
|[Aritmetica quantistica: compilazione di ripple-portare i Viper](https://github.com/microsoft/QuantumKatas/blob/master/RippleCarryAdder)|Una serie di esercizi approfonditi che esplorano l'aggiunta di [Ripple](https://en.wikipedia.org/wiki/Adder_(electronics)#Ripple-carry_adder) in un computer Quantum. Creare una vipera quantistica sul posto, espanderla con un algoritmo diverso e infine creare un sottotrattore quantistico sul posto.   |

### <a name="entanglement-games"></a>Giochi di entanglement

| Kata | Descrizione |
|:-----|-------------|
|[Gioco CHSH](https://github.com/microsoft/QuantumKatas/tree/master/CHSHGame)|Esplorare il groviglio di Quantum con un'implementazione del gioco [chsh](https://en.wikipedia.org/wiki/CHSH_inequality) . Questo gioco non [locale](https://en.wikipedia.org/wiki/Quantum_refereed_game) illustra in che modo è possibile usare l'aggiunta quantistica per aumentare le probabilità dei giocatori di vincere oltre quello che sarebbe possibile con una strategia puramente classica.|
|[Gioco GHZ](https://github.com/microsoft/QuantumKatas/tree/master/GHZGame)|Il gioco GHZ è un altro gioco non locale, ma coinvolge tre giocatori.|
|[Gioco del quadrato magico di Mermin-Peres](https://github.com/microsoft/QuantumKatas/tree/master/MagicSquareGame)|Una serie di esercizi che esplorano la [pseudo-](https://en.wikipedia.org/wiki/Quantum_pseudo-telepathy#The_Mermin%E2%80%93Peres_magic_square_game) telemetria quantistica per risolvere un gioco magico quadrato.  |

## <a name="resources"></a>Risorse

Vedere la serie completa di [Quantum Katas](https://github.com/microsoft/QuantumKatas)

[Eseguire i kata online](https://aka.ms/try-quantum-katas)