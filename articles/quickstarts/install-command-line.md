---
title: Sviluppare con le applicazioni della riga di comando di Q#
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
no-loc:
- Q#
- $$v
ms.openlocfilehash: 630dc7b8acf2dd8f258eb27dfbc367b812cd1c19
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867608"
---
# <a name="develop-with-no-locq-command-line-applications"></a>Sviluppare con le applicazioni della riga di comando di Q#

I programmi Q# possono essere eseguiti autonomamente, senza un driver in un linguaggio host come C#, F# o Python.

## <a name="prerequisites"></a>Prerequisiti

- [.NET Core SDK 3.1 o versione successiva](https://www.microsoft.com/net/download)

## <a name="installation"></a>Installazione

Anche se è possibile compilare applicazioni della riga di comando di Q# in qualsiasi IDE, è consigliabile usare Visual Studio Code (VS Code) o l'IDE di Visual Studio per sviluppare le applicazioni Q# in locale. Per sviluppare nel cloud tramite il Web browser, è consigliabile usare Visual Studio Codespaces. Lo sviluppo in questi ambienti include le funzionalità avanzate dell'estensione QDK, tra cui avvisi, evidenziazione della sintassi, modelli di progetto e altro ancora. 

Per configurare VS Code:

1. Scaricare e installare [VS Code](https://code.visualstudio.com/download) (Windows, Linux e Mac).
2. Installare [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

Per configurare Visual Studio:

1. Scaricare e installare [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 o versione successiva, con il carico di lavoro per lo sviluppo multipiattaforma .NET Core abilitato.
2. Scaricare e installare [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).

Per configurare Visual Studio Codespaces:

1. Creare un [account Azure](https://azure.microsoft.com/free/).
2. Creare un ambiente Codespaces. Seguire la [guida di avvio rapido](https://docs.microsoft.com/visualstudio/online/quickstarts/browser). Quando si crea il codespace, è consigliabile immettere `microsoft/Quantum` nel campo "Repository GIT" per caricare le impostazioni specifiche di QDK.
3. È ora possibile avviare il nuovo ambiente e iniziare a sviluppare nel browser tramite l'[IDE cloud di VS Codespaces](https://online.visualstudio.com/environments). In alternativa, è possibile usare l'installazione locale di VS Code e usare Codespaces come [ambiente remoto](https://docs.microsoft.com/visualstudio/online/how-to/vscode).


Per installare QDK per un altro ambiente, immettere quanto segue nella riga di comando:

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-no-locq"></a>Sviluppare con Q#

Seguire le istruzioni riportate nella scheda corrispondente al proprio ambiente.

### <a name="vs-code"></a>[Visual Studio Code](#tab/tabid-vscode)

Per creare un nuovo progetto:

1. Fare clic su **Visualizza** -> **Riquadro comandi** e selezionare **Q#: Create New Project**(ASA: Crea nuovo progetto).
2. Click **Standalone console application** (Applicazione console autonoma).
3. Passare al percorso in cui salvare il progetto e fare clic su **Create Project** (Crea progetto).
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

### <a name="other-editors-with-the-command-line"></a>[Altri editor con la riga di comando](#tab/tabid-cmdline)

Verificare l'installazione creando un'applicazione `Hello World` Q#.

1. Installare i modelli di progetto.

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

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
