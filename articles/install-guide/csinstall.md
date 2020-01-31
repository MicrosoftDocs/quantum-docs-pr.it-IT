---
title: 'Sviluppare con Q # +C#'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 1fd829c684502092bb7491b0f46b5f690320c941
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76831019"
---
# <a name="develop-with-q--c"></a>Sviluppare con Q # +C#

Installare QDK per sviluppare C# programmi host per chiamare le operazioni Q #.

Q # è progettato per essere eseguito correttamente con i linguaggi .NET, C#in particolare. È possibile utilizzare questa associazione all'interno di diversi ambienti di sviluppo:

- [Domande e risposte C# con Visual Studio (Windows)](#VS)
- [Domande e risposte C# con Visual Studio Code (Windows, Linux e Mac)](#VSC)
- [Q # + C# uso dello strumento da riga di comando `dotnet`](#command)

## Sviluppare con Q # + C# con Visual Studio<a name="VS"></a>

Visual Studio offre un ambiente completo per lo sviluppo di programmi Q #. L'estensione Q # di Visual Studio contiene i modelli per i file e i progetti Q #, nonché l'evidenziazione della sintassi, il completamento del codice e il supporto IntelliSense.


1. Prerequisiti

    - [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, con il carico di lavoro per lo sviluppo multipiattaforma .NET Core abilitato

1. Installare l'estensione di Visual Studio per Q#

    - Scaricare e installare l' [estensione di Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)

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

## Sviluppare con Q # + C# usando Visual Studio Code<a name="VSC"></a>

Visual Studio Code (VS Code) offre un ambiente completo per lo sviluppo di programmi Q # in Windows, Linux e Mac.  L'estensione Q # VS Code include il supporto per l'evidenziazione della sintassi Q #, il completamento del codice e i frammenti di codice Q #.

1. Prerequisiti

   - [Visual Studio Code](https://code.visualstudio.com/download)
   - [.NET Core SDK 3,1 o versione successiva](https://www.microsoft.com/net/download)

1. Installare l'estensione Visual Studio Code per il calcolo quantistico

    - Installare l'[estensione Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)

1. Installare i modelli di progetto di calcolo quantistico:

   - Passare a **Visualizza** -> **Riquadro comandi**
   - Selezionare **Q #: installare i modelli di progetto**

    Quantum Development Kit è ora installato e pronto per l'uso nelle applicazioni e nelle librerie.

1. Verificare l'installazione creando un'applicazione `Hello World`

    - Creare un nuovo progetto:

        - Passare a **Visualizza** -> **Riquadro comandi**
        - Selezionare **Q #: Crea nuovo progetto**
        - Seleziona **applicazione console autonoma**
        - Passare al percorso del file system in cui si vuole creare l'applicazione
        - Al termine della creazione del progetto, fare clic sul pulsante **Apri nuovo progetto...**

    - Se non si ha già l' C# estensione per vs code installata, verrà visualizzato un popup. Installare l'estensione. 

    - Eseguire l'applicazione:

        - Vai al **terminale** -> **nuovo terminale**
        - Immettere `dotnet run`
        - Nella finestra di output verrà visualizzato il testo seguente: `Hello quantum world!`


> [!NOTE]
> * Le aree di lavoro con più cartelle radice non sono attualmente supportate dall'estensione Visual Studio Code. Se sono presenti più progetti all'interno di un'area di lavoro di Visual Studio Code, è necessario che tutti i progetti siano contenuti all'interno della stessa cartella radice.

## Sviluppare con Q # + C# usando lo strumento da riga di comando `dotnet`<a name="command"></a>

Naturalmente, è anche possibile compilare ed eseguire programmi Q# dalla riga di comando installando semplicemente .NET Core SDK e i modelli di progetto QDK. 

1. Prerequisiti

    - [.NET Core SDK 3,1 o versione successiva](https://www.microsoft.com/net/download)

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

    
## <a name="whats-next"></a>Potrai anche

Ora che è stato installato Quantum Development Kit nell'ambiente preferito, è possibile scrivere ed eseguire [il primo programma quantistico](xref:microsoft.quantum.write-program).
