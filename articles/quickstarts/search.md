---
title: Eseguire l'algoritmo di ricerca di Grover in Q# - Quantum Development Kit
description: Compilare un progetto Q# che dimostra l'algoritmo di Grover, uno degli algoritmi quantistici canonici.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
ms.openlocfilehash: 0e64fcd56929fa33397c45bf1b2e99bf687eca6f
ms.sourcegitcommit: 7d350db4b5e766cd243633aee7d0a839b6274bd6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "77906951"
---
# <a name="quickstart-implement-grovers-search-algorithm-in-q"></a>Guida introduttiva: Implementare l'algoritmo di ricerca di Grover in Q#

In questa esercitazione dell'avvio rapido si apprenderà a creare e a eseguire una ricerca di Grover per accelerare la ricerca di dati non strutturati.  La ricerca di Grover è uno degli algoritmi di calcolo quantistico più diffusi e questa implementazione Q# relativamente ridotta consente di farsi un'idea dei vantaggi della programmazione di soluzioni quantistiche con un linguaggio di programmazione quantistico Q# generale per esprimere gli algoritmi quantistici.  Alla fine della guida si osserverà che l'output della simulazione dimostra come viene restituita una stringa specifica tra un elenco di voci non ordinate in una frazione del tempo necessario per eseguire una ricerca nell'elenco completo con un computer classico.

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

1. Usando Quantum Development Kit, [creare un nuovo progetto Q#](xref:microsoft.quantum.howto.createproject) denominato `Grover` nell'ambiente di sviluppo preferito.

1. Nel nuovo progetto aggiungere il codice seguente al file `Operations.qs`:

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-40":::

1. Per definire l'elenco in cui verrà eseguita la ricerca, creare un nuovo file `Reflections.qs` e incollare il codice seguente al suo interno:

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    L'operazione `ReflectAboutMarked` definisce l'input contrassegnato che si sta cercando: la stringa di zeri e uno alternati. In questo esempio l'input contrassegnato è hardcoded e può essere esteso per cercare input diversi o generalizzato per qualsiasi input.

1. Eseguire quindi il nuovo programma Q# per trovare l'elemento contrassegnato da `ReflectAboutMarked`.

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[Python con Visual Studio Code o riga di comando](#tab/tabid-python)

    Per eseguire il nuovo programma Q# da Python, salvare il codice seguente come `host.py`:

    :::code language="python" source="~/quantum/samples/algorithms/simple-grover/host.py" range="9-14":::

    È quindi possibile eseguire il programma host Python dalla riga di comando:

    ```bash
    $ python host.py
    Preparing Q# environment...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    [0, 1, 0, 1, 0]
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[C# con Visual Studio Code o riga di comando](#tab/tabid-csharp)

    Per eseguire il nuovo programma Q# da C#, modificare `Driver.cs` per includere il codice C# seguente:

    :::code language="csharp" source="~/quantum/samples/algorithms/simple-grover/Host.cs" range="4-23":::

    È quindi possibile eseguire il programma host C# dalla riga di comando:

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```

    ### <a name="c-with-visual-studio-2019"></a>[C# con Visual Studio 2019](#tab/tabid-vs2019)

    Per eseguire il nuovo programma Q# da C# in Visual Studio, modificare `Driver.cs` per includere il codice C# seguente:

    :::code language="csharp" source="~/quantum/samples/algorithms/simple-grover/Host.cs" range="4-23":::

    Premere quindi F5. L'esecuzione del programma verrà avviata e verrà visualizzata una nuova finestra con i risultati seguenti: 

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```
    ***

    L'operazione `ReflectAboutMarked` viene chiamata solo quattro volte, ma il programma Q# è riuscito a trovare l'input "01010" tra $2 ^{5} = $32 di possibili input.

## <a name="next-steps"></a>Passaggi successivi

Se questa guida di avvio rapido è stata interessante, è possibile consultare alcune delle risorse riportate di seguito per altre informazioni su come usare Q# per scrivere applicazioni quantistiche personalizzate:

- [Tornare alla guida Introduzione a QDK](xref:microsoft.quantum.welcome)
- Provare un [esempio](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search) di algoritmo di ricerca di Grover più generale
- [Altre informazioni sulla ricerca di Grover con la serie Quantum Katas](xref:microsoft.quantum.overview.katas)
- Altre informazioni sull'[amplificazione dell'ampiezza](xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification), la tecnica di calcolo quantistico alla base dell'algoritmo di ricerca di Grover
- [Concetti di calcolo quantistico](xref:microsoft.quantum.concepts.intro)
- [Esempi di Quantum Development Kit](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
