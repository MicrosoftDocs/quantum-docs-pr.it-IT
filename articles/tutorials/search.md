---
title: Eseguire l'algoritmo di ricerca di Grover in Q# -Quantum Development Kit
description: Compilare un Q# progetto che illustra l'algoritmo di Grover, uno degli algoritmi quantistici canonici.
author: cgranade
ms.author: chgranad
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
no-loc:
- Q#
- $$v
ms.openlocfilehash: 86c6a651a117b788eb4c8fdd805ead7ab8f54dd7
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834806"
---
# <a name="tutorial-implement-grovers-search-algorithm-in-q"></a>Esercitazione: Implementare l'algoritmo di ricerca di Grover in Q\#

In questa esercitazione si apprenderà a creare e a eseguire una ricerca di Grover per accelerare la ricerca di dati non strutturati.  La ricerca di Grover è uno degli algoritmi di calcolo quantum più diffusi e questa implementazione relativamente piccola Q# offre un'idea di alcuni dei vantaggi della programmazione di soluzioni Quantum con un Q# linguaggio di programmazione quantistica di alto livello per esprimere gli algoritmi quantistici.  Alla fine della guida si osserverà che l'output della simulazione dimostra come viene restituita una stringa specifica tra un elenco di voci non ordinate in una frazione del tempo necessario per eseguire una ricerca nell'elenco completo con un computer classico.

L'algoritmo di Grover esegue la ricerca di elementi specifici in un elenco di dati non strutturati. Ad esempio, può rispondere alla domanda: Questa carta estratta da un mazzo di carte è un asso di cuori? L'assegnazione di etichette all'elemento specifico viene chiamata _input contrassegnato_.

Usando l'algoritmo di ricerca di Grover, un computer quantistico garantisce l'esecuzione di questa ricerca in un minor numero di passaggi rispetto al numero di elementi nell'elenco in cui viene eseguita la ricerca, risultato che nessun algoritmo classico può raggiungere. L'aumento della velocità nel caso di un mazzo di carte è trascurabile. Tuttavia, negli elenchi contenenti milioni o miliardi di elementi, diventa significativo.

È possibile creare l'algoritmo di ricerca di Grover con solo poche righe di codice.

## <a name="prerequisites"></a>Prerequisiti

- Microsoft [Quantum Development Kit][install].

## <a name="what-does-grovers-search-algorithm-do"></a>Che cosa fa l'algoritmo di ricerca di Grover?

L'algoritmo di Grover chiede se un elemento in un elenco è quello che si sta cercando. A tale scopo, costruisce una sovrapposizione quantistica degli indici dell'elenco con ogni coefficiente, o ampiezza di probabilità, che rappresenta la probabilità che l'indice specifico sia quello che si sta cercando.

Il nucleo dell'algoritmo è costituito da due passaggi che aumentano in modo incrementale il coefficiente dell'indice cercato, fino a quando l'ampiezza di probabilità di tale coefficiente non si avvicina a uno.

Il numero di aumenti incrementali è minore del numero di elementi nell'elenco. Questo è il motivo per cui l'algoritmo di ricerca di Grover esegue la ricerca in un minor numero di passaggi rispetto a qualsiasi algoritmo classico.

![Diagramma funzionale dell'algoritmo di ricerca di Grover](~/media/grover.png)

## <a name="write-the-code"></a>Scrivere il codice

1. Utilizzando Quantum Development Kit, [creare un nuovo Q# progetto per l'applicazione](xref:microsoft.quantum.install.standalone). Assegnare al progetto il titolo `Grover`.

1. Nel nuovo progetto aggiungere il codice seguente al file `Program.qs`:

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-41":::

1. Per definire l'elenco in cui verrà eseguita la ricerca, creare un nuovo file `Reflections.qs` e incollare il codice seguente al suo interno:

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    L'operazione `ReflectAboutMarked` definisce l'input contrassegnato che si sta cercando: la stringa di zeri e uno alternati. In questo esempio l'input contrassegnato è hardcoded e può essere esteso per cercare input diversi o generalizzato per qualsiasi input.

1. Eseguire quindi il nuovo Q# programma per trovare l'elemento contrassegnato da `ReflectAboutMarked` .

### <a name="no-locq-applications-with-visual-studio-or-visual-studio-code"></a>Q# applicazioni con Visual Studio o Visual Studio Code

Il programma eseguirà l'operazione o la funzione contrassegnata con l' `@EntryPoint()` attributo in un simulatore o in un estimatore di risorse, a seconda della configurazione del progetto e delle opzioni della riga di comando.

In Visual Studio è sufficiente premere CTRL + F5 per eseguire lo script.

In VS Code compilare `Program.qs` per la prima volta digitando quanto segue nel terminale:

```Command line
dotnet build
```

Per le esecuzioni successive non è necessario ripetere la compilazione. Per eseguirlo, digitare il comando seguente e premere INVIO:

```Command line
dotnet run --no-build
```

Nel terminale dovrebbe essere visualizzato il messaggio seguente:

```
operations.qs:
This operation applies Grover's algorithm to search all possible inputs to an operation to find a particular marked state.
Usage:
operations.qs [options] [command]

--n-qubits <n-qubits> (REQUIRED)
-s, --simulator <simulator>         The name of the simulator to use.
--version                           Show version information
-?, -h, --help                      Show help and usage information
Commands:
```

Questo perché non è stato specificato il numero di qubits che si voleva usare, quindi il terminale Mostra i comandi disponibili per il programma eseguibile. Se si vuole usare 5 qubits, è necessario digitare quanto segue:

```Command line
dotnet run --n-qubits 5
```

Premendo INVIO verrà visualizzato l'output seguente:

```
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
[Zero,One,Zero,One,Zero]
```

## <a name="next-steps"></a>Passaggi successivi

Se questa esercitazione è stata apprezzata, consultare alcune delle risorse riportate di seguito per ulteriori informazioni su come utilizzare Q# per scrivere le proprie applicazioni Quantum:

- [Tornare alla guida Introduzione a QDK](xref:microsoft.quantum.welcome)
- Provare un [esempio](https://github.com/microsoft/Quantum/tree/main/samples/algorithms/database-search) di algoritmo di ricerca di Grover più generale
- [Altre informazioni sulla ricerca di Grover con la serie Quantum Katas](xref:microsoft.quantum.overview.katas)
- Altre informazioni sull'[amplificazione dell'ampiezza][amplitude-amplification], la tecnica di calcolo quantistico alla base dell'algoritmo di ricerca di Grover
- [Concetti di calcolo quantistico](xref:microsoft.quantum.concepts.intro)
- [Esempi di Quantum Development Kit](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
[amplitude-amplification]: xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification
