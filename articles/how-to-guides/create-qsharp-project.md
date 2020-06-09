---
title: 'Informazioni su come creare un progetto Q # con Quantum Development Kit (QDK)'
description: "Inizializzare un progetto per lo sviluppo di Quantum con QDK e Q # nell'ambiente di sviluppo scelto"
author: natke
ms.author: nakersha
ms.date: 10/19/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.howto.createproject
ms.openlocfilehash: 8af8e3288aab731520ede984d5f89644de292385
ms.sourcegitcommit: c8ebc5d7d8581444754f5d7bfaca2f25601f1b14
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84578212"
---
# <a name="create-a-q-project-in-your-development-environment"></a>Creare un progetto Q # nell'ambiente di sviluppo

Informazioni su come creare un progetto Q # con QDK.

Un progetto Q # contiene file Q # contenenti codice quantico, oltre a un programma host per l'esecuzione del programma Quantum. È possibile scrivere il programma host in linguaggi .NET, ad esempio C# o Python. È anche possibile eseguire il codice Q # in una Jupyter Notebook usando il kernel IQ #.

Scegliere l'ambiente di sviluppo e la lingua dalle sezioni seguenti:

* [Python](#create-a-python-project)
* [Jupyter Notebooks in Q#](#create-a-q-jupyter-notebook-project)
* [C# con Visual Studio](#create-a-c-project-on-windows-using-visual-studio)
* [C# con VS Code](#create-a-c-project-using-vs-code)
* [C# con la riga di comando](#create-a-c-project-using-the-dotnet-command-line-tool)

## <a name="create-a-python-project"></a>Creare un progetto Python

1. Prerequisiti

     * Installare [Quantum Development Kit per Python](xref:microsoft.quantum.install.python)

1. Creare una cartella per il progetto e passare a tale cartella

1. Creare un file Q # denominato `Operation.qs` e aggiungervi il codice q #. Ad esempio:

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

1. Creare un file host Python denominato `host.py` per chiamare l'operazione Q #. Ad esempio:

    ```python
    import qsharp

    from HelloWorld import SayHello

    SayHello.simulate()
    ```

1. Eseguire il programma:

    ```
    python host.py
    ```

1. Verificare l'output. Il programma restituirà le righe seguenti:

    ```
    Hello from quantum world!
    0
    ```

È ora possibile continuare a sviluppare il programma Quantum.

## <a name="create-a-q-jupyter-notebook-project"></a>Creare un progetto Q # Jupyter Notebook

1. Prerequisiti

    * Installare [Quantum Development Kit per notebook di Jupyter](xref:microsoft.quantum.install.jupyter)

1. Eseguire il comando seguente per avviare il server Notebook:

    ```
    jupyter notebook
    ```

1. Passare all'URL visualizzato nella riga di comando. Ad esempio: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]

1. Nel browser viene visualizzata una pagina Jupyter. Nella scheda **file** selezionare **nuovo**  >  **Q #** per creare un Jupyter notebook con un kernel q #. Aggiungere il codice seguente alla prima cella del notebook:

    ```qsharp
    operation SayHello() : Unit {
        Message("Hello from quantum world!");
    }
    ```

1. Selezionare **cella**  >  **esecuzione celle** per eseguire il notebook. `SayHello`verrà visualizzato a breve nell'output della cella:

    ![Jupyter Notebook cella con codice Q #](~/media/install-guide-jupyter.png)

    Quando è in esecuzione in Jupyter notebook, il codice Q # viene compilato e il notebook restituisce il nome delle operazioni trovate.

1. In una nuova cella simulare in un computer quantistico l'esecuzione dell'operazione appena creata usando il magic `%simulate`:

    ![Jupyter Notebook cella con% simulare Magic](~/media/install-guide-jupyter-simulate.png)

    Il messaggio verrà visualizzato sullo schermo insieme al risultato dell'operazione richiamata (in questo caso, vuoto).

È ora possibile aggiungere altre operazioni Q # per continuare lo sviluppo del quantum.

## <a name="create-a-c-project-on-windows-using-visual-studio"></a>Creare un progetto C# in Windows con Visual Studio

1. Prerequisiti

    * Installare l' [estensione Quantum Development Kit per Visual Studio](xref:microsoft.quantum.install.cs)

1. Creare una nuova applicazione Q#

    * Vai a **file**  ->  **nuovo**  ->  **progetto**
    * Digitare `Q#` nella casella di ricerca
    * Selezionare **Applicazione Q#**
    * Selezionare **Avanti**
    * Scegliere un nome e una posizione per l'applicazione
    * Selezionare **Crea**

1. Esaminare il progetto

    Si noterà che sono stati creati due file: `Driver.cs`, ovvero l'applicazione host C# e `Operation.qs`, ovvero un programma Q# che definisce una semplice operazione per stampare un messaggio nella console.

1. Eseguire l'applicazione

    * Selezionare **debug**  ->  **Avvia senza eseguire debug**
    * Verrà visualizzato il testo `Hello quantum world!` stampato in una finestra della console.

È ora possibile continuare lo sviluppo di Quantum con Visual Studio

> [!NOTE]
> * Se sono presenti più progetti all'interno di una soluzione di Visual Studio, è necessario che tutti i progetti contenuti nella soluzione si trovino nella stessa cartella della soluzione o in una delle relative sottocartelle.  

## <a name="create-a-c-project-using-vs-code"></a>Creare un progetto C#, usando VS Code

1. Prerequisiti

    * Installare l' [estensione del kit di sviluppo di Quantum per vs code](xref:microsoft.quantum.install.cs)

1. Creare un nuovo progetto:

    * Vai a **Visualizza**  ->  **riquadro comandi**
    * Selezionare **Q #: Crea nuovo progetto**
    * Seleziona **applicazione console autonoma**
    * Passare al percorso del file system in cui si vuole creare l'applicazione
    * Al termine della creazione del progetto, fare clic sul pulsante **Apri nuovo progetto...**

1. Eseguire l'applicazione:

    * Vai a **Terminal**  ->  **New Terminal**
    * Immettere `dotnet run`
    * Nella finestra di output verrà visualizzato il testo seguente: `Hello quantum world!`

È ora possibile continuare lo sviluppo di Quantum usando Visual Studio Code.

> [!NOTE]
> * Le aree di lavoro con più cartelle radice non sono attualmente supportate dall'estensione Visual Studio Code. Se sono presenti più progetti all'interno di un'area di lavoro di Visual Studio Code, è necessario che tutti i progetti siano contenuti all'interno della stessa cartella radice.

## <a name="create-a-c-project-using-the-dotnet-command-line-tool"></a>Creare un progetto C#, usando lo `dotnet` strumento da riga di comando

1. Prerequisiti

    * Installare [Quantum Development Kit per la riga di comando](xref:microsoft.quantum.install.standalone)

1. Creare una nuova applicazione

    ```dotnetcli
    dotnet new console -lang Q# -o <project name>
    ```

1. Passare alla directory della nuova applicazione

    ```
    cd <project name>
    ```

    Si noterà che sono stati creati due file, insieme ai file di progetto dell'applicazione: un file Q# (`Operation.qs`) e un file host C# (`Driver.cs`).

1. Eseguire l'applicazione

    ```dotnetcli
    dotnet run
    ```

    Verrà visualizzato l'output seguente: `Hello quantum world!`

È ora possibile continuare lo sviluppo di Quantum, usando gli strumenti da riga di comando.

## <a name="next-steps"></a>Passaggi successivi

Ora che è stato creato un progetto nell'ambiente preferito, è possibile continuare lo sviluppo di Quantum.
