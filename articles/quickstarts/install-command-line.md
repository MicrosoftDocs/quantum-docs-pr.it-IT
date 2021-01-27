---
title: Sviluppare con applicazioni Q# in un IDE
description: Informazioni su come creare un'applicazione Q# che viene eseguita dal prompt dei comandi.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: quickstart
uid: microsoft.quantum.install.standalone
no-loc:
- Q#
- $$v
ms.openlocfilehash: 3e4f1e97477ecb0547b1586b1c7603c8a9954584
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844325"
---
# <a name="develop-with-no-locq-applications-in-an-ide"></a>Sviluppare con applicazioni Q# in un IDE

I programmi Q# possono essere eseguiti autonomamente, senza un driver in un linguaggio host come C#, F# o Python. È possibile sviluppare applicazioni Q# in Visual Studio Code (VS Code), Visual Studio, Visual Studio Codespaces o con qualsiasi editor/IDE ed eseguire applicazioni dalla console .NET. 

## <a name="prerequisites-for-all-environments"></a>Prerequisiti per tutti gli ambienti

- [.NET Core SDK 3.1 o versione successiva](https://www.microsoft.com/net/download)

## <a name="installation"></a>Installazione

Anche se è possibile compilare applicazioni Q# in qualsiasi IDE, è consigliabile usare Visual Studio Code (VS Code) o l'IDE di Visual Studio per sviluppare le applicazioni Q# in locale. Per sviluppare nel cloud tramite il Web browser, è consigliabile usare Visual Studio Codespaces. Per lo sviluppo in questi ambienti vengono sfruttate le funzionalità avanzate dell'estensione QDK, tra cui avvisi, evidenziazione della sintassi, modelli di progetto e altro ancora. 

### <a name="to-configure-for-vs-code"></a>Per eseguire la configurazione per VS Code:

1. Scaricare e installare [VS Code](https://code.visualstudio.com/download) (Windows, Linux e Mac).
2. Installare [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

### <a name="to-configure-for-visual-studio"></a>Per eseguire la configurazione per Visual Studio:

1. Scaricare e installare [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 o versione successiva, con il carico di lavoro per lo sviluppo multipiattaforma .NET Core abilitato.
2. Scaricare e installare [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).

### <a name="to-configure-for-another-environment"></a>Per eseguire la configurazione per un altro ambiente: 

1. Al prompt dei comandi immettere quanto segue

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

### <a name="to-configure-for-visual-studio-codespaces"></a>Per eseguire la configurazione per Visual Studio Codespaces:

1. Creare un [account Azure](https://azure.microsoft.com/free/).
2. Creare un ambiente Codespaces. Seguire la [guida di avvio rapido](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser). Quando si crea il codespace, è consigliabile immettere `microsoft/Quantum` nel campo "Repository GIT" per caricare le impostazioni specifiche di QDK.
3. È ora possibile avviare il nuovo ambiente e iniziare a sviluppare nel browser tramite l'[IDE cloud di VS Codespaces](https://online.visualstudio.com/environments). In alternativa, è possibile usare l'installazione locale di VS Code e usare Codespaces come [ambiente remoto](https://docs.microsoft.com/visualstudio/online/how-to/vscode).

## <a name="develop-with-no-locq"></a>Sviluppare con Q#

Seguire le istruzioni riportate nella scheda corrispondente al proprio ambiente di sviluppo.

### <a name="vs-code"></a>[Visual Studio Code](#tab/tabid-vscode)

Per creare un nuovo progetto:

1. Fare clic su **Visualizza** -> **Riquadro comandi** e selezionare **Q#: Create New Project**(ASA: Crea nuovo progetto).
2. Click **Standalone console application** (Applicazione console autonoma).
3. Passare alla posizione in cui salvare il progetto. Immettere il nome del progetto e fare clic su **Crea progetto**.
4. Al termine dell'operazione, fare clic su **Open new project** (Apri nuovo progetto) in basso a destra.

Esaminare il progetto. Dovrebbe essere visualizzato un file di origine denominato `Program.qs`, che corrisponde a un programma Q# in cui viene definita una semplice operazione per stampare un messaggio nella console.

Per eseguire l'applicazione:

1. Fare clic su **Terminale** -> **Nuovo terminale**.
2. Al prompt del terminale, immettere `dotnet run`.
3. Nella finestra di output verrà visualizzato il testo seguente: `Hello quantum world!`

> [!NOTE]
> Le aree di lavoro con più cartelle radice non sono attualmente supportate dall'estensione VS Code per Q#. Se sono presenti più progetti all'interno di un'area di lavoro di Visual Studio Code, è necessario che tutti i progetti siano contenuti all'interno della stessa cartella radice.

### <a name="visual-studio"></a>[Visual Studio](#tab/tabid-vs)

Verificare l'installazione di Visual Studio creando un'applicazione `Hello World` Q#.

Per creare una nuova applicazione Q#:

1. Aprire Visual Studio e fare clic su **File** -> **Nuovo** -> **Progetto**.
2. Digitare `Q#` nella casella di ricerca, selezionare **Q# Application** (Applicazione Q#) e quindi fare clic su **Avanti**.
3. Immettere un nome e un percorso per l'applicazione e fare clic su **Crea**.


Esaminare il progetto. Dovrebbe essere visualizzato un file di origine denominato `Program.qs`, che corrisponde a un programma Q# in cui viene definita una semplice operazione per stampare un messaggio nella console.

Per eseguire l'applicazione:

1. Selezionare **Debug** -> **Avvia senza eseguire debug**.
2. Verrà visualizzato il testo `Hello quantum world!` stampato in una finestra della console.

> [!NOTE]
> Se sono presenti più progetti all'interno di una soluzione di Visual Studio, è necessario che tutti i progetti contenuti nella soluzione si trovino nella stessa cartella della soluzione o in una delle relative sottocartelle.  

### <a name="other-editors-with-the-command-prompt"></a>[Altri editor con il prompt dei comandi](#tab/tabid-cmdline)

Verificare l'installazione creando un'applicazione `Hello World` Q#.

1. Creare una nuova applicazione:

    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. Passare alla directory dell'applicazione:

    ```dotnetcli
    cd runSayHello
    ```

    Questa directory dovrebbe ora contenere un file `Program.qs`, che corrisponde a un programma Q# in cui viene definita una semplice operazione per stampare un messaggio nella console. È possibile modificare questo modello con un editor di testo e sovrascriverlo con le proprie applicazioni quantistiche. 

1. Eseguire il programma:

    ```dotnetcli
    dotnet run
    ```

1. Verrà visualizzato il testo seguente: `Hello quantum world!`

***

## <a name="next-steps"></a>Passaggi successivi

Ora che è stato installato Quantum Development Kit nell'ambiente preferito, è possibile scrivere ed eseguire [il primo programma quantistico](xref:microsoft.quantum.quickstarts.qrng).
