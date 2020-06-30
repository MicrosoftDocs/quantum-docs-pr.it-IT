---
title: Sviluppare con notebook di Jupyter Q#
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 5c613d29c03525d29893307684f13ccd32d4d4eb
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274094"
---
# <a name="develop-with-q-jupyter-notebooks"></a>Sviluppare con notebook di Jupyter Q#

Installare il QDK per sviluppare operazioni Q# nei notebook di Jupyter Q#.

I notebook di Jupyter consentono l'esecuzione di codice sul posto, unitamente a istruzioni, note e altro contenuto. Questo ambiente è ideale per la scrittura di codice Q# con spiegazioni incorporate o esercitazioni interattive sul calcolo quantistico. Ecco cosa occorre fare per iniziare a creare notebook Q#.

IQ# (pronunciato i-q-sharp) è un'estensione usata principalmente da Jupyter e Python in .NET Core SDK che fornisce le funzionalità essenziali per la compilazione e la simulazione di operazioni Q#.

> [!NOTE]
> * Nei notebook di Jupyter Q# è possibile eseguire solo il codice Q# e non è possibile chiamare operazioni da programmi host esterni, ad esempio file Python o C#. Questo ambiente non è appropriato se si intende combinare un programma host classico esterno con il programma quantistico.

1. Prerequisiti

    - [Python](https://www.python.org/downloads/) 3.6 o versione successiva
    - [Notebook di Jupyter](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. Installare il pacchetto `iqsharp`

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > Se durante il passaggio `dotnet iqsharp install` viene visualizzato un errore, aprire una nuova finestra del terminale e riprovare.
    > Se il problema persiste, provare a individuare lo strumento `dotnet-iqsharp` installato (in Windows `dotnet-iqsharp.exe`) ed eseguire:
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > dove `/path/to/dotnet-iqsharp` deve essere sostituito con il percorso assoluto dello strumento `dotnet-iqsharp` nel file system.
    > Tale strumento si trova in genere in `.dotnet/tools` nella cartella del profilo utente.

1. Verificare l'installazione creando un'applicazione `Hello World`

    - Eseguire il comando seguente per avviare il server Notebook:

        ```
        jupyter notebook
        ```

    - Per aprire il notebook di Jupyter, copiare e incollare nel browser l'URL fornito dalla riga di comando.

    - Creare un notebook di Jupyter con un kernel Q# e aggiungere il codice seguente alla prima cella del notebook:

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - Eseguire la cella del notebook:

        ![Cella di notebook di Jupyter con codice Q#](~/media/install-guide-jupyter.png)

        Nell'output della cella verrà visualizzato `SayHello`. Quando è in esecuzione nel notebook di Jupyter, il codice Q# viene compilato e il notebook restituisce il nome delle operazioni trovate.


    - In una nuova cella eseguire l'operazione appena creata (in un simulatore) usando il comando `%simulate`:

        ![Cella di notebook di Jupyter con il magic %simulate](~/media/install-guide-jupyter-simulate.png)

        Il messaggio verrà visualizzato sullo schermo insieme al risultato dell'operazione richiamata. In questo caso viene visualizzata la tupla vuota `()` perché l'operazione restituisce semplicemente un tipo `Unit`.

## <a name="next-steps"></a>Passaggi successivi

Ora che è stato installato il QDK per notebook di Jupyter Q#, è possibile scrivere ed eseguire [il primo programma quantistico](xref:microsoft.quantum.quickstarts.qrng) scrivendo il codice Q# direttamente nell'ambiente Jupyter Notebook.

Per altri esempi sulle operazioni che è possibile eseguire con i notebook di Jupyter Q#, vedere:
- [Introduzione a Q# e Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/). Questo articolo include un notebook di Jupyter Q# che mostra come usare Q# in questo ambiente.
- [Quantum Katas](xref:microsoft.quantum.overview.katas), una raccolta open source di esercitazioni autogestite e set di esercizi di programmazione sotto forma di notebook di Jupyter Q#. I [notebook delle esercitazioni di Quantum Katas](https://github.com/microsoft/QuantumKatas#tutorial-topics) costituiscono un valido punto di partenza. Le esercitazioni Quantum Katas sono infatti ideali per apprendere sia i concetti del calcolo quantistico che della programmazione Q#. Si tratta di un ottimo esempio del tipo di contenuto che è possibile creare con i notebook di Jupyter Q#.
