---
title: Informazioni su come installare Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 3ec53934436b47908fd4d794a98933010f6059a7
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035295"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>Installare Microsoft Quantum Development Kit (QDK)

Informazioni su come installare il Microsoft Quantum Development Kit (QDK), per iniziare a sviluppare con la programmazione quantistica. Contenuto del QDK:

- linguaggio di programmazione Q#
- set di librerie che estrapolano le funzionalità complesse in Q#
- applicazione host (scritta in Python o in un linguaggio .NET) che esegue operazioni quantistiche scritte in Q#
- strumenti per facilitare lo sviluppo

A seconda dell'ambiente di sviluppo scelto, sono disponibili procedure di installazione diverse. Scegliere l'ambiente nelle sezioni seguenti.

## <a name="develop-with-python"></a>Sviluppare con Python

1. Prerequisiti

    - [Python](https://www.python.org/downloads/) 3.6 o versione successiva
    - Gestione pacchetti Python [PIP](https://pip.pypa.io/en/stable/installing)
    - [.NET Core SDK 2.1 o versione successiva](https://www.microsoft.com/net/download)

1. Installare il pacchetto `iqsharp`

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Installare il pacchetto `qsharp`

    ```bash
    pip install qsharp
    ```

1. Verificare l'installazione creando un'applicazione `Hello World`

    - Creare un'operazione Q# minima creando un file denominato `Operation.qs` e aggiungendovi il codice seguente:

        ```qsharp
        namespace HelloWorld
        {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Result {
                Message("Hello from quantum world!");
                return Zero;
            }
        }
        ```

    - Creare un programma Python denominato `hello_world.py` per chiamare l'operazione `SayHello()` Q#:

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - Eseguire il programma:

        ```bash
        python hello_world.py
        ```

    - Verificare l'output. Il programma restituirà le righe seguenti:

        ```bash
        Hello from quantum world!
       0
       ```

## <a name="develop-with-jupyter-notebooks"></a>Sviluppare con Jupyter Notebooks

1. Prerequisiti

    - [Python](https://www.python.org/downloads/) 3.6 o versione successiva
    - [Notebook di Jupyter](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 2.1 o versione successiva](https://www.microsoft.com/net/download)

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

    - Passare all'URL visualizzato nella riga di comando. Ad esempio: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]

    - Creare un notebook Jupyter con un kernel Q# e aggiungere il codice seguente alla prima cella del notebook:

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - Eseguire la cella del notebook:

        ![Cella del notebook Jupyter](~/media/install-guide-jupyter.png)

        Nell'output della cella verrà visualizzato `SayHello`. Quando è in esecuzione nei notebook Jupyter, il codice Q# viene compilato e il notebook restituisce il nome delle operazioni trovate.

## <a name="develop-with-c-on-windows-using-visual-studio"></a>Sviluppare con C# in Windows, usando Visual Studio

1. Prerequisiti

    - [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, con il carico di lavoro per lo sviluppo multipiattaforma .NET Core abilitato

1. Installare l'estensione di Visual Studio per Q#

    - Scaricare l'[estensione di Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)
    - Aggiungere l'estensione a Visual Studio

1. Verificare l'installazione creando un'applicazione `Hello World`

    - Creare una nuova applicazione Q#

        - Passare a **File** -> **Nuovo** -> **Progetto**
        - Digitare `Q#` nella casella di ricerca
        - Selezionare **Applicazione Q#**
        - Selezionare **Avanti**
        - Scegliere un nome e una posizione per l'applicazione
        - Selezionare **Crea**

    - Esaminare il progetto

        Si noterà che sono stati creati due file: `Driver.cs`, ovvero l'applicazione host C# e `Operation.qs`, ovvero un programma Q# che definisce una semplice operazione per stampare un messaggio nella console.

    - Eseguire l'applicazione

        - Selezionare **Debug** -> **Avvia senza eseguire il debug**
        - Verrà visualizzato il testo `Hello quantum world!` stampato in una finestra della console.

> [!NOTE]
> * Se sono presenti più progetti all'interno di una soluzione di Visual Studio, è necessario che tutti i progetti contenuti nella soluzione si trovino nella stessa cartella della soluzione o in una delle relative sottocartelle.  

## <a name="develop-with-c-using-vs-code"></a>Sviluppare con C# usando Visual Studio Code

1. Prerequisiti

   - [Visual Studio Code](https://code.visualstudio.com/download)
   - [.NET Core SDK 2.1 o versione successiva](https://www.microsoft.com/net/download)

1. Installare l'estensione Visual Studio Code per il calcolo quantistico

    - Installare l'[estensione Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)

1. Installare i modelli di progetto di calcolo quantistico:

   - Passare a **Visualizza** -> **Riquadro comandi**
   - Selezionare **Q#: Installa modelli di progetto**

    Quantum Development Kit è ora installato e pronto per l'uso nelle applicazioni e nelle librerie.

1. Verificare l'installazione creando un'applicazione `Hello World`

    - Creare un nuovo progetto:

        - Passare a **Visualizza** -> **Riquadro comandi**
        - Selezionare **Q#: Crea nuovo progetto**
        - Passare al percorso del file system in cui si vuole creare l'applicazione
        - Al termine della creazione del progetto, fare clic sul pulsante **Apri nuovo progetto...**

    - Eseguire l'applicazione:

        - Passare a **Debug** -> **Avvia senza eseguire il debug**
        - Nella finestra di output verrà visualizzato il testo seguente: `Hello quantum world!`

> [!NOTE]
> * > * Le aree di lavoro con più cartelle radice non sono attualmente supportate dall'estensione Visual Studio Code. Se sono presenti più progetti all'interno di un'area di lavoro di Visual Studio Code, è necessario che tutti i progetti siano contenuti all'interno della stessa cartella radice.

## <a name="develop-with-c-using-the-dotnet-command-line-tool"></a>Sviluppare con C# usando lo strumento da riga di comando `dotnet`

1. Prerequisiti

    - [.NET Core SDK 2.1 o versione successiva](https://www.microsoft.com/net/download)

1. Installare i modelli di progetto di calcolo quantistico per .NET

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    Quantum Development Kit è ora installato e pronto per l'uso nelle applicazioni e nelle librerie.

1. Verificare l'installazione creando un'applicazione `Hello World`

    - Creare una nuova applicazione

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - Passare alla directory della nuova applicazione

       ```bash
       cd runSayHello
       ```

    Si noterà che sono stati creati due file, insieme ai file di progetto dell'applicazione: un file Q# (`Operation.qs`) e un file host C# (`Driver.cs`).

    - Eseguire l'applicazione

        ```bash
        dotnet run
        ```

        Verrà visualizzato l'output seguente: `Hello quantum world!`

## <a name="whats-next"></a>Passaggi successivi

Ora che è stato installato Quantum Development Kit nell'ambiente preferito, è possibile scrivere ed eseguire [il primo programma quantistico](xref:microsoft.quantum.write-program).
