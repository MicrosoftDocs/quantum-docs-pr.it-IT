---
title: 'Sviluppare con notebook Q # Jupyter'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: b7276f9b273f601f30e4938018398353b6a9102d
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76831070"
---
# <a name="develop-with-q-jupyter-notebooks"></a>Sviluppare con notebook Q # Jupyter

Installare QDK per lo sviluppo di operazioni Q # nei notebook Q # Jupyter.

I notebook di Jupyter consentono l'esecuzione di codice sul posto insieme a istruzioni, note e altro contenuto. Questo ambiente è ideale per la scrittura di codice Q # con spiegazioni incorporate o esercitazioni interattive di quantum computing. Ecco cosa occorre fare per iniziare a creare notebook Q#.

IQ # (pronunciato i-q-sharp) è un'estensione usata principalmente da Jupyter e Python in .NET Core SDK che fornisce le funzionalità essenziali per la compilazione e la simulazione di operazioni Q#.

> [!NOTE]
> * Nei notebook Q # Jupyter è possibile eseguire solo il codice Q # e non è possibile chiamare le operazioni da programmi host esterni, ad esempio Python o C# file. Questo ambiente non è appropriato se l'obiettivo consiste nel combinare un programma host classico esterno con il programma Quantum.

1. Prerequisiti

    - [Python](https://www.python.org/downloads/) 3.6 o versione successiva
    - [Notebook di Jupyter](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 3,1 o versione successiva](https://www.microsoft.com/net/download)

1. Installare il pacchetto `iqsharp`

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Verificare l'installazione creando un'applicazione `Hello World`

    - Eseguire il comando seguente per avviare il server Notebook:

        ```bash
        jupyter notebook
        ```

    - Per aprire la copia del notebook di Jupyter e incollare l'URL fornito dalla riga di comando nel browser.

    - Creare un notebook Jupyter con un kernel Q# e aggiungere il codice seguente alla prima cella del notebook:

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - Eseguire la cella del notebook:

        ![Cella di notebook di Jupyter con codice Q#](~/media/install-guide-jupyter.png)

        Nell'output della cella verrà visualizzato `SayHello`. Quando è in esecuzione nei notebook Jupyter, il codice Q# viene compilato e il notebook restituisce il nome delle operazioni trovate.


    - In una nuova cella, eseguire l'operazione appena creata (in un simulatore) usando il comando `%simulate`:

        ![Cella di notebook di Jupyter con il magic %simulate](~/media/install-guide-jupyter-simulate.png)

        Dovrebbe essere visualizzato il messaggio stampato sullo schermo insieme al risultato dell'operazione richiamata (in questo caso, viene visualizzata la tupla vuota `()` perché l'operazione restituisce semplicemente un tipo di `Unit`).

## <a name="whats-next"></a>Potrai anche

Ora che è stato installato Quantum Development Kit nell'ambiente preferito, è possibile scrivere ed eseguire [il primo programma quantistico](xref:microsoft.quantum.write-program).
