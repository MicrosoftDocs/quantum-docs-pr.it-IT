---
title: Sviluppare con Q# + Jupyter Notebooks
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: b80d95a160b5f46c1132d3428ba32ad6dcd5656e
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630339"
---
# <a name="develop-with-q-jupyter-notebooks"></a>Sviluppare con Q# + Jupyter Notebooks

Installare QDK per lo sviluppo di operazioni Q # nei notebook Q # Jupyter.

I notebook di Jupyter consentono l'esecuzione di codice sul posto insieme a istruzioni, note e altro contenuto. Questo ambiente è ideale per la scrittura di codice Q # con spiegazioni incorporate o esercitazioni interattive di quantum computing. Ecco cosa occorre fare per iniziare a creare notebook Q#.

IQ # (pronunciato i-q-sharp) è un'estensione usata principalmente da Jupyter e Python in .NET Core SDK che fornisce le funzionalità essenziali per la compilazione e la simulazione di operazioni Q#.

> [!NOTE]
> * Nei notebook Q # Jupyter è possibile eseguire solo il codice Q # e non è possibile chiamare le operazioni da programmi host esterni, ad esempio file Python o C#. Questo ambiente non è appropriato se l'obiettivo consiste nel combinare un programma host classico esterno con il programma Quantum.

1. Prerequisiti

    - [Python](https://www.python.org/downloads/) 3,6 o versione successiva
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. Installare il pacchetto `iqsharp`

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > Se viene visualizzato un errore durante il `dotnet iqsharp install` passaggio, aprire una nuova finestra del terminale e riprovare.
    > Se questa operazione non funziona ancora, provare a individuare lo `dotnet-iqsharp` strumento installato (in Windows `dotnet-iqsharp.exe` ) e a eseguire:
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > dove `/path/to/dotnet-iqsharp` deve essere sostituito con il percorso assoluto dello `dotnet-iqsharp` strumento nel file System.
    > Questa operazione si trova in genere `.dotnet/tools` nella cartella del profilo utente.

1. Verificare l'installazione creando un'applicazione `Hello World`

    - Eseguire il comando seguente per avviare il server Notebook:

        ```
        jupyter notebook
        ```

    - Per aprire la Jupyter Notebook, copiare e incollare l'URL fornito dalla riga di comando nel browser.

    - Creare una Jupyter Notebook con un kernel Q # e aggiungere il codice seguente alla prima cella del notebook:

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - Eseguire la cella del notebook:

        ![Jupyter Notebook cella con codice Q #](~/media/install-guide-jupyter.png)

        Nell'output della cella verrà visualizzato `SayHello`. Quando è in esecuzione in Jupyter Notebook, il codice Q # viene compilato e il notebook restituisce il nome delle operazioni trovate.


    - In una nuova cella, eseguire l'operazione appena creata (in un simulatore) usando il `%simulate` comando:

        ![Jupyter Notebook cella con% simulare Magic](~/media/install-guide-jupyter-simulate.png)

        Dovrebbe essere visualizzato il messaggio stampato sullo schermo insieme al risultato dell'operazione richiamata (in questo caso, viene visualizzata la tupla vuota `()` perché l'operazione restituisce semplicemente un `Unit` tipo).

## <a name="next-steps"></a>Passaggi successivi

Ora che è stato installato il QDK per i notebook Q # Jupyter, è possibile scrivere ed eseguire [il primo programma Quantum](xref:microsoft.quantum.quickstarts.qrng) scrivendo il codice Q # direttamente all'interno dell'ambiente Jupyter notebook.

Per altri esempi sulle operazioni che è possibile eseguire con i notebook Q # Jupyter, vedere:
- [Introduzione a Q # e Jupyter notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/). Qui sarà disponibile un Jupyter Notebook Q # che Mostra come usare Q # in questo ambiente.
- [Quantum Katas](xref:microsoft.quantum.overview.katas), una raccolta Open Source di esercitazioni autosufficienti e set di esercizi di programmazione sotto forma di notebook Q # Jupyter. I [notebook di Quantum Katas tutorial](https://github.com/microsoft/QuantumKatas#tutorial-topics) sono un valido punto di partenza. I Kata Quantum hanno lo scopo di insegnare gli elementi del quantum computing e la programmazione Q # allo stesso tempo. Si tratta di un ottimo esempio del tipo di contenuto che è possibile creare con i notebook Q # Jupyter.
