---
title: 'Informazioni su come creare un progetto Q # con Quantum Development Kit (QDK)'
description: "Inizializzare un progetto per lo sviluppo di Quantum con QDK e Q # nell'ambiente di sviluppo scelto"
author: natke
ms.author: nakersha
ms.date: 10/19/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.howto.createproject
ms.openlocfilehash: b4bec5e7a174b7e2d588331dd2093c7b23a728b0
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2019
ms.locfileid: "73444175"
---
# <a name="create-a-q-project-in-your-development-environment"></a>Creare un progetto Q # nell'ambiente di sviluppo

Informazioni su come creare un progetto Q # con QDK.

Un progetto Q # contiene file Q # contenenti codice quantico, oltre a un programma host per l'esecuzione del programma Quantum. È possibile scrivere il programma host nei linguaggi .NET C#, ad esempio, o in Python. È anche possibile eseguire il codice Q # in un notebook di Jupyter usando il kernel IQ #.

Scegliere l'ambiente di sviluppo e la lingua dalle sezioni seguenti:

* [Python](#create-a-python-project)
* [Notebook Jupyter](#create-a-jupyter-notebook-project)
* [C#con Visual Studio](#create-a-c-project-on-windows-using-visual-studio)
* [C#con VS Code](#create-a-c-project-using-vs-code)
* [C#con la riga di comando](#create-a-c-project-using-the-dotnet-command-line-tool)

## <a name="create-a-python-project"></a>Creare un progetto Python

1. Prerequisiti

     * [Quantum Development Kit per Python](xref:microsoft.quantum.install#develop-with-python)

1. Creare una cartella per il progetto e passare a tale cartella

1. Creare un file Q # denominato `Operation.qs`e aggiungervi il codice Q #. ad esempio:

    ```qsharp
    namespace HelloWorld {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation SayHello() : Result {
            Message("Hello from quantum world!");
            return Zero;
        }
    }
    ```

1. Creare un file host Python denominato `host.py` per chiamare l'operazione Q #. ad esempio:

    ```python
    import qsharp

    from HelloWorld import SayHello

    SayHello.simulate()
    ```

1. Eseguire il programma:

    ```bash
    python host.py
    ```

1. Verificare l'output. Il programma restituirà le righe seguenti:

    ```bash
    Hello from quantum world!
    0
    ```

È ora possibile continuare a sviluppare il programma Quantum.

## <a name="create-a-jupyter-notebook-project"></a>Creare un progetto di Jupyter Notebook

1. Prerequisiti

    * [Quantum Development Kit per notebook di Jupyter](xref:microsoft.quantum.install#develop-with-jupyter-notebooks)

1. Eseguire il comando seguente per avviare il server Notebook:

    ```bash
    jupyter notebook
    ```

1. Passare all'URL visualizzato nella riga di comando. Ad esempio: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]

1. Nel browser viene visualizzata una pagina Jupyter. Nella scheda **file** selezionare **nuovo** > **Q #** per creare un notebook di Jupyter con un kernel Q #. Aggiungere il codice seguente alla prima cella del notebook:

    ```qsharp
    operation SayHello() : Unit {
        Message("Hello from quantum world!");
    }
    ```

1. Selezionare **cella** > **eseguire celle** per eseguire il notebook. `SayHello` verrà visualizzato a breve nell'output della cella:

    ![Cella Jupyter notebook con codice Q #](~/media/install-guide-jupyter.png)

    Quando è in esecuzione in Jupyter notebook, il codice Q # viene compilato e il notebook restituisce il nome delle operazioni trovate.

1. In una nuova cella, simulare l'esecuzione in un computer Quantum dell'operazione appena creata usando il `%simulate` Magic:

    ![Cella Jupyter notebook con% simulare Magic](~/media/install-guide-jupyter-simulate.png)

    Il messaggio verrà visualizzato sullo schermo insieme al risultato dell'operazione richiamata (in questo caso, vuoto).

È ora possibile aggiungere altre operazioni Q # per continuare lo sviluppo del quantum.

## <a name="create-a-c-project-on-windows-using-visual-studio"></a>Creare un C# progetto in Windows con Visual Studio

1. Prerequisiti

    * [Quantum Development Kit per Visual Studio](xref:microsoft.quantum.install#develop-with-c-on-windows-using-visual-studio)

1. Creare una nuova applicazione Q#

    * Passare a **File** -> **Nuovo** -> **Progetto**
    * Digitare `Q#` nella casella di ricerca
    * Selezionare **Applicazione Q#**
    * Selezionare **Avanti**
    * Scegliere un nome e una posizione per l'applicazione
    * Selezionare **Crea**

1. Esaminare il progetto

    Si noterà che sono stati creati due file: `Driver.cs`, ovvero l'applicazione host C# e `Operation.qs`, ovvero un programma Q# che definisce una semplice operazione per stampare un messaggio nella console.

1. Eseguire l'applicazione

    * Selezionare **Debug** -> **Avvia senza eseguire il debug**
    * Verrà visualizzato il testo `Hello quantum world!` stampato in una finestra della console.

È ora possibile continuare lo sviluppo di Quantum con Visual Studio

> [!NOTE]
> * Se sono presenti più progetti all'interno di una soluzione di Visual Studio, è necessario che tutti i progetti contenuti nella soluzione si trovino nella stessa cartella della soluzione o in una delle relative sottocartelle.  

## <a name="create-a-c-project-using-vs-code"></a>Creare un C# progetto utilizzando vs code

1. Prerequisiti

    * [Quantum Development Kit per vs code](xref:microsoft.quantum.install#develop-with-c-using-visual-studio-code)

1. Creare un nuovo progetto:

    * Passare a **Visualizza** -> **Riquadro comandi**
    * Selezionare **Q #: Crea nuovo progetto**
    * Passare al percorso del file system in cui si vuole creare l'applicazione
    * Al termine della creazione del progetto, fare clic sul pulsante **Apri nuovo progetto...**

1. Eseguire l'applicazione:

    * Passare a **Debug** -> **Avvia senza eseguire il debug**
    * Nella finestra di output verrà visualizzato il testo seguente: `Hello quantum world!`

È ora possibile continuare lo sviluppo di Quantum usando Visual Studio Code.

> [!NOTE]
> * Le aree di lavoro con più cartelle radice non sono attualmente supportate dall'estensione Visual Studio Code. Se sono presenti più progetti all'interno di un'area di lavoro di Visual Studio Code, è necessario che tutti i progetti siano contenuti all'interno della stessa cartella radice.

## <a name="create-a-c-project-using-the-dotnet-command-line-tool"></a>Creare un C# progetto, usando lo strumento da riga di comando `dotnet`

1. Prerequisiti

    * [Quantum Development Kit per la riga di comando](xref:microsoft.quantum.install#develop-with-c-using-the-dotnet-command-line-tool)

1. Creare una nuova applicazione

    ```bash
    dotnet new console -lang Q# -o <project name>
    ```

1. Passare alla directory della nuova applicazione

    ```bash
    cd <project name>
    ```

    Si noterà che sono stati creati due file, insieme ai file di progetto dell'applicazione: un file Q# (`Operation.qs`) e un file host C# (`Driver.cs`).

1. Eseguire l'applicazione

    ```bash
    dotnet run
    ```

    Verrà visualizzato l'output seguente: `Hello quantum world!`

È ora possibile continuare lo sviluppo di Quantum, usando gli strumenti da riga di comando.

## <a name="whats-next"></a>Potrai anche

Ora che è stato creato un progetto nell'ambiente preferito, è possibile continuare lo sviluppo di Quantum.
